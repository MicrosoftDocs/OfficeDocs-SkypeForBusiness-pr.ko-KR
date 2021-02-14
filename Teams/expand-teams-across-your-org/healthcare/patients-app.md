---
title: 환자 앱 개요
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: FHIR API를 사용하여 Electronic Healthcare Records를 Microsoft Teams Patients 앱에 통합하는 방법을 배워야 합니다.
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 594375959a8cd7cbbfc21c6b9d5ceb6c0f8a8dac
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803546"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="a0deb-103">Microsoft Teams에 전자 의료 레코드 통합</span><span class="sxs-lookup"><span data-stu-id="a0deb-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="a0deb-104">2020년 10월 30일부로 환자 앱은 사용 중지되고 Teams의 [목록](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 앱으로 대체됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-104">Effective October 30, 2020, the Patients app has been retired and replaced by the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams.</span></span> <span data-ttu-id="a0deb-105">환자 앱 데이터는 팀을 백업하는 Office 365 그룹의 그룹 사서함에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="a0deb-106">환자 앱과 연결된 모든 데이터는 이 그룹에 유지되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-106">All data associated with the Patients app is retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="a0deb-107">사용자는 목록 앱을 사용하여 목록을 다시 [만들 수 있습니다.](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)</span><span class="sxs-lookup"><span data-stu-id="a0deb-107">Users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="a0deb-108">목록을 사용하여 의료 조직의 관리 팀은 라운드 및학 간 팀 모임에서 일반 환자 모니터링에 이르는 시나리오에 대한 환자 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-108">With Lists, care teams in your healthcare organization can create patient lists for scenarios ranging from rounds and interdisciplinary team meetings to general patient monitoring.</span></span> <span data-ttu-id="a0deb-109">시작을 위해 목록에서 환자 서식 파일을 확인해 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0deb-109">Check out the Patients template in Lists to get started.</span></span> <span data-ttu-id="a0deb-110">조직에서 목록 앱을 관리하는 방법에 대한 자세한 내용은 목록 앱 [관리를 참조하세요.](../../manage-lists-app.md)</span><span class="sxs-lookup"><span data-stu-id="a0deb-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

<span data-ttu-id="a0deb-111">이 문서는 의료 정보 시스템 위에 FHIR API를 사용하여 Microsoft Teams에 연결하는 데 관심이 있는 일반 의료 IT 개발자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="a0deb-112">이렇게 하면 의료 조직의 요구와 일치하는 관리 조정 시나리오를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="a0deb-113">연결된 문서에서는 Microsoft Teams Patients 앱에 대한 FHIR 인터페이스 사양을 문서화하고, 다음 섹션에서는 FHIR 서버를 설정하고 개발 환경 또는 테넌트에서 Patients 앱에 연결하는 데 필요한 것을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="a0deb-114">또한 지원되는 옵션 중 하나에 해당해야 하는 선택한 FHIR 서버의 설명서를 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>

- <span data-ttu-id="a0deb-115">Datica(CMI [](https://datica.com/compliant-managed-integration/) 제품을 통해)</span><span class="sxs-lookup"><span data-stu-id="a0deb-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="a0deb-116">Infor Cloverleaf(Infor [FHIR 브리지를 통해)](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)</span><span class="sxs-lookup"><span data-stu-id="a0deb-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="a0deb-117">[Redox(R^FHIR 서버를 통해)](https://www.redoxengine.com/fhir/)</span><span class="sxs-lookup"><span data-stu-id="a0deb-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="a0deb-118">[Dapasoft(FHIR의 Corolar를 통해)](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/)</span><span class="sxs-lookup"><span data-stu-id="a0deb-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="a0deb-119">이 프로세스에는 Microsoft Teams 관리 센터 또는 PowerShell cmdlet을 사용하여 기능을 사용하도록 설정하는 단계가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="a0deb-120">구성은 FHIR 서버/서비스 쪽 및 Patients 앱 클라이언트에서 전적으로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="a0deb-121">아래 그림은 Patients 앱의 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-121">Illustrated below is the architecture of the Patients app:</span></span>

![환자 앱 아키텍처 다이어그램](../../media/patients-app-architecture.png)

<span data-ttu-id="a0deb-123">다음 섹션에서는 환자 앱과 통합하기 위해 FHIR 서버(또는 EHR 사용 FHIR API)가 충족해야 하는 환자 앱에 대한 FHIR 전용 데이터 액세스 계층의 요구 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="a0deb-124">사용자 인증에 대한 기대치</span><span class="sxs-lookup"><span data-stu-id="a0deb-124">Expectations around user authentication</span></span>
- <span data-ttu-id="a0deb-125">통합 인터페이스의 기능 및 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0deb-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="a0deb-126">성능 및 안정성에 대한 기대치</span><span class="sxs-lookup"><span data-stu-id="a0deb-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="a0deb-127">환자 앱에 지원될 FHIR 리소스에 대한 기대치</span><span class="sxs-lookup"><span data-stu-id="a0deb-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="a0deb-128">통합 프로세스 및 예상 계약 모델</span><span class="sxs-lookup"><span data-stu-id="a0deb-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="a0deb-129">FHIR 및 환자 앱에 직면한 몇 가지 일반적인 과제를 시작하는 방법</span><span class="sxs-lookup"><span data-stu-id="a0deb-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="a0deb-130">환자 앱의 다음에 실행하기 위한 향후 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0deb-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="a0deb-131">다음 섹션에서 "partner" 또는 "Interop partner"라는 단어는 FHIR을 통해 환자 앱에 대한 EHR 시스템에 통합할 수 있는 모든 제3자 조직을 참조하는 데 사용되어 나열된 사양과 일치하게 FHIR 서버를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="a0deb-132">기능 및 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a0deb-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="a0deb-133">인증</span><span class="sxs-lookup"><span data-stu-id="a0deb-133">Authentication</span></span>  

<span data-ttu-id="a0deb-134">사용자 수준  권한 부여를 지원하지 않는 앱 수준 권한 부여는 EHR 시스템에서 사용자 수준 권한 부여를 구현할 수 있는 경우에도 FHIR을 통해 데이터 변환을 수행하고 EHR 데이터에 대한 연결을 노출하는 가장 일반적으로 지원되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="a0deb-135">Interop Service(파트너)는 EHR 데이터에 대한 상승된 액세스를 얻게 하며, 적절한 FHIR 리소스와 동일한 데이터를 노출하면 Interop Service 또는 플랫폼과 통합된 Interop Service Consumer(환자 앱)에 전달된 권한 부여 컨텍스트가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="a0deb-136">환자 앱은 사용자 수준 권한 부여를 적용할 수 없지만 Patients 앱과 Interop 파트너의 서비스 간에 애플리케이션 인증을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="a0deb-137">애플리케이션-애플리케이션 인증 모델은 아래에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="a0deb-138">서비스 대 서비스 인증은 OAuth 2.0 클라이언트 자격 증명 [흐름을 통해 수행해야 합니다.](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)</span><span class="sxs-lookup"><span data-stu-id="a0deb-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="a0deb-139">파트너 서비스는 다음을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="a0deb-140">파트너 서비스를 사용하면 환자 앱이 파트너와 계정을 만들 수 있습니다. 이를 통해 환자 앱은 파트너의 인증 서버에서 인증 등록 포털을 통해 관리되는 client_id client_secret 및 앱을 생성하고 소유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>

2. <span data-ttu-id="a0deb-141">파트너 서비스는 제공된 클라이언트 자격 증명을 수락하고 확인(인증)하는 인증/권한 부여 시스템을 소유하며 아래 설명된 바와 같이 범위에 테넌트 힌트를 사용하여 액세스 토큰을 다시 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>

3. <span data-ttu-id="a0deb-142">보안상의 이유로 또는 비밀 위반의 경우 Patients 앱은 비밀을 다시 생성하고 이전 비밀을 무효화하거나 삭제할 수 있습니다(예: Azure Portal - AAD 앱 등록에서 동일하게 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="a0deb-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>

4. <span data-ttu-id="a0deb-143">준수 문을 호스팅하는 메타데이터 엔드포인트는 인증되지 않고 인증 토큰 없이 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>

5. <span data-ttu-id="a0deb-144">파트너 서비스는 환자 앱에 대한 토큰 엔드포인트를 제공하여 클라이언트 자격 증명 흐름을 사용하여 액세스 토큰을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="a0deb-145">권한 부여 서버에 따라 토큰 URL은 다음 예제와 같은 FHIR 서버의 메타데이터에서 페치된 FHIR 준수(기능) 문의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-145">The token URL as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

    ```
    {
        "resourceType": "CapabilityStatement",
        .
        .
        .
        "rest": [
            {
                "mode": "server",
                "security": {
                    "extension": [
                        {
                            "extension": [
                                {
                                    "url": "token",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"
                                },
                                {
                                    "url": "authorize",
                                    "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize"
                                }
                            ],
                            "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"
                        }
                    ],
                    "service": [
                        {
                            "coding": [
                                {
                                    "system": "https://hl7.org/fhir/ValueSet/restful-security-service",
                                    "code": "OAuth"
                                }
                            ]
                        }
                    ]
                },
                .
                .
                .
            }
        ]
    }
    ```

<span data-ttu-id="a0deb-146">액세스 토큰에 대한 요청은 다음 매개 변수로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-146">A request for an access token consists of the following parameters:</span></span>

```http
POST /token HTTP/1.1
Host: authorization-server.com

grant-type=client_credentials
&client_id=xxxxxxxxxx
&client_secret=xxxxxxxxxx
```

<span data-ttu-id="a0deb-147">파트너 서비스는 파트너 client_id client_secret Auth 등록 포털을 통해 관리되는 환자 앱에 대한 데이터 및 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-147">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="a0deb-148">파트너 서비스는 클라이언트 자격 증명 흐름을 사용하여 액세스 토큰을 요청하는 엔드포인트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-148">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="a0deb-149">성공적인 응답에는 매개 변수 token_type, access_token 및 expires_in 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-149">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="a0deb-150">라우팅: 공급자 엔드포인트에 AAD 테넌트 매핑</span><span class="sxs-lookup"><span data-stu-id="a0deb-150">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="a0deb-151">환자 앱은 단일 엔드포인트를 통해 파트너 서비스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-151">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="a0deb-152">파트너 서비스는 파트너 서비스가 작업하는 각 Microsoft 고객(AAD 테넌트 ID)을 해당 FHIR 서버(의료 공급자)에 매핑하는 메커니즘을 소유하고 유지 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-152">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="a0deb-153">공급자 엔드포인트에 AAD 테넌트 매핑은 AAD 테넌트 ID(GUID)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-153">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="a0deb-154">환자 앱은 각 요청에 대한 액세스 토큰을 요청하는 동안 범위에서 테넌트 ID를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-154">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="a0deb-155">파트너 서비스는 테넌트 ID를 공급자 엔드포인트로 매핑하고 테넌트 ID에 따라 공급자 엔드포인트로 요청을 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-155">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="a0deb-156">이를 위해 파트너는 수동으로 또는 포털을 통해 Interop 플랫폼에 공급자 조직의 온보드의 일부로 구성을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-156">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="a0deb-157">인증 및 라우팅 워크플로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-157">The Authentication and Routing workflow is shown below:</span></span>

![인증 및 라우팅 워크플로 다이어그램](../../media/Patient-app-6.png)

1. <span data-ttu-id="a0deb-159">전송하여 앱 액세스 토큰에 대한 요청:</span><span class="sxs-lookup"><span data-stu-id="a0deb-159">Request for app access token by sending:</span></span>
 
    ```
    {   grant_type: client_credentials,
        client_id: xxxxxx, 
        client_secret: xxxxxx,
        scope: {Provider Identifier, Ex: tenant ID}
    }
    ```

2. <span data-ttu-id="a0deb-160">앱 토큰으로 회신:</span><span class="sxs-lookup"><span data-stu-id="a0deb-160">Reply with an app token:</span></span>

    ```
    {  access_token: {JWT, with scope: tenant ID},
       expires_in: 156678,
       token_type: "Bearer",
    }
    ```

3. <span data-ttu-id="a0deb-161">Access 토큰을 사용하여 보호된 데이터를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-161">Request protected data with Access token.</span></span>

4. <span data-ttu-id="a0deb-162">권한 부여 메시지: 범위의 테넌트 ID에서 라우팅할 적절한 FHIR 서버를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-162">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope.</span></span>

5. <span data-ttu-id="a0deb-163">앱 토큰으로 인증한 후 인증된 FHIR 서버에서 앱 보호 데이터를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-163">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="a0deb-164">인터페이스</span><span class="sxs-lookup"><span data-stu-id="a0deb-164">Interfaces</span></span>

<span data-ttu-id="a0deb-165">환자 앱에서 사용하는 특정 호출 및 필드는 다음 문서에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-165">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="a0deb-166">FHIR 서버/FHIR API에 적용할 인터페이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-166">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="a0deb-167">DSTU2 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="a0deb-167">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="a0deb-168">STU3 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="a0deb-168">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="a0deb-169">성능 및 안정성</span><span class="sxs-lookup"><span data-stu-id="a0deb-169">Performance and Reliability</span></span>

<span data-ttu-id="a0deb-170">Patients 앱은 비공개 미리 보기 상태인 반면 종단적 성능에 대한 보장은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-170">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="a0deb-171">성능의 요인에는 워크플로와 관련된 모든 홉의 상대적 대기 시간(상태 시스템 환경의 EHR에서 시작하여 FHIR 서버를 포함한 Interop 파트너 및 해당fra, Office 365 에코시스템 및 환자 앱까지)에 대한 상대적 대기 시간이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-171">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Interop 파트너 성능 그림](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="a0deb-173">FHIR 시작</span><span class="sxs-lookup"><span data-stu-id="a0deb-173">Get started with FHIR</span></span>  

<span data-ttu-id="a0deb-174">FHIR을 사용하는 경우 Microsoft Teams EHR 통합 인터페이스에 노출할 수 있는 FHIR 서버에 쉽게 액세스해야 하는 경우 Microsoft는 모든 개발자가 사용할 수 있는 오픈 소스 FHIR 서버를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-174">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="a0deb-175">Microsoft에서 사용할 수 있는 오픈 소스 FHIR Server에 대해 자세히 알아보고 조직에 배포하는 방법을 알아보는 [Azure용 FHIR Server란?](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0deb-175">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="a0deb-176">HSPC Open 샌드박스 EHR 환경을 사용하여 열린 FHIR 서버를 지원하는 EHR을 만들고 이 환경을 사용하여 Patients 앱을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-176">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="a0deb-177">HSPC 샌드박스 설명서를 [읽어보는 것이 좋습니다.](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)</span><span class="sxs-lookup"><span data-stu-id="a0deb-177">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="a0deb-178">샌드박스는 환자를 만들고, 추가하고, 편집하는 간편하고 UI 지향적인 사용자 친화적인 방법을 제공할 뿐만 아니라 시작하는 데 필요한 몇 가지 샘플을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0deb-178">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 
