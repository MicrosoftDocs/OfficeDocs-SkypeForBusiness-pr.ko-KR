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
description: Microsoft 팀 환자 앱에 전자 의료 기록 통합에 대 한 자세한 내용을 보려면 Api를 사용 하세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2af20b0c95f85d00269ac34b0768e4118793879b
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905520"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="6e446-103">Microsoft Teams에 전자 의료 레코드 통합</span><span class="sxs-lookup"><span data-stu-id="6e446-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="6e446-104">개인 미리 보기에 참여 하려면 [비공개 미리 보기에 등록](#enroll-in-the-private-preview)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e446-104">To participate in the private preview, see [Enroll in the private preview](#enroll-in-the-private-preview).</span></span>

<span data-ttu-id="6e446-105">이 문서는 Microsoft 팀에 연결 하기 위해 의료 정보 시스템의 맨 위에 FA r Api를 사용 하는 데 관심이 있는 일반 의료 IT 개발자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-105">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="6e446-106">이는 의료 조직의 요구 사항에 맞는 의료 조정 시나리오를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-106">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="6e446-107">연결 된 문서 Microsoft 팀 환자 앱에 대 한 f r 인터페이스 사양을 문서화 하 고, 다음 섹션에서는 f r 서버를 설정 하 고 개발 환경 또는 테 넌 트에서 환자 앱에 연결 하는 데 필요한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-107">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="6e446-108">또한 지원 되는 옵션 중 하나 여야 하는 선택한 FE r server의 설명서에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-108">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="6e446-109">Datica ( [CMI](https://datica.com/compliant-managed-integration/) 제공)</span><span class="sxs-lookup"><span data-stu-id="6e446-109">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="6e446-110">Cloverleaf ( [INFOR FA r 브리지](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)를 통해)</span><span class="sxs-lookup"><span data-stu-id="6e446-110">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="6e446-111">Redox ( [r ^ FA r 서버](https://www.redoxengine.com/fhir/)통과)</span><span class="sxs-lookup"><span data-stu-id="6e446-111">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="6e446-112">Dapasoft ( [FA r의 Corolar](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="6e446-112">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="6e446-113">이 프로세스에는 Microsoft 팀 관리 센터 또는 PowerShell cmdlet을 사용 하 여 기능을 사용 하도록 설정 하는 단계가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-113">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="6e446-114">이 구성은 모두 FTO r 서버/서비스 쪽 및 환자 앱 클라이언트에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-114">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="6e446-115">아래에는 환자 앱의 아키텍처가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-115">Illustrated below is the architecture of the Patients app:</span></span>

![환자 앱 아키텍처의 다이어그램](../../media/patients-app-architecture.png)

<span data-ttu-id="6e446-117">다음 섹션에서는 환자 앱에 대 한 FA r 전용 데이터 액세스 계층의 요구 사항에 대해 설명 하며,이는 다음을 포함 하 여 환자 앱과 통합 하기 위해 f r 서버 (또는 EHR enabled FA r Api)가 충족 해야 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-117">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="6e446-118">사용자 인증 관련 예측</span><span class="sxs-lookup"><span data-stu-id="6e446-118">Expectations around user authentication</span></span>
- <span data-ttu-id="6e446-119">통합 인터페이스의 기능 및 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e446-119">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="6e446-120">성능 및 안정성에 대 한 기대</span><span class="sxs-lookup"><span data-stu-id="6e446-120">Expectations around performance and reliability</span></span>
- <span data-ttu-id="6e446-121">환자 앱에 대해 지원 되는 f r 리소스에 대 한 기대</span><span class="sxs-lookup"><span data-stu-id="6e446-121">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="6e446-122">통합 프로세스 및 예상 되는 계약 모델</span><span class="sxs-lookup"><span data-stu-id="6e446-122">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="6e446-123">환자 앱의 비공개 미리 보기에서 사용자 및 고객을 등록 하는 방법</span><span class="sxs-lookup"><span data-stu-id="6e446-123">How to enroll yourself and your customer in the private preview of the Patients app</span></span>
- <span data-ttu-id="6e446-124">환자 앱을 사용 하 여 시작 하는 방법 및 몇 가지 일반적인 과제에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-124">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="6e446-125">환자 앱의 다음 반복에 대 한 향후 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e446-125">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="6e446-126">다음 섹션에서는 "partner" 또는 "Interop 파트너" 라는 단어를 사용 하 여 환자 앱에 대 한 EHR 시스템과 통합할 수 있는 타사 조직을 참조 하 고 나열 된 사양과 일치 하도록 FA r 서버를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-126">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="6e446-127">기능적 및 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6e446-127">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="6e446-128">인증</span><span class="sxs-lookup"><span data-stu-id="6e446-128">Authentication</span></span>  

<span data-ttu-id="6e446-129">*사용자 수준 권한 부여를 지원 하지 않는* 앱 수준 권한 부여는 EHR 시스템에서 사용자 수준 권한 부여를 구현할 수 있지만 데이터 변환을 수행 하 고 EHR 데이터에 대 한 연결을 표시 하는 데 더 일반적으로 지원 되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-129">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="6e446-130">Interop 서비스 (파트너)는 EHR 데이터에 대 한 액세스 권한을 강화 하 고, 해당 데이터를 적절 한 f r 리소스와 동일 하 게 표시 하는 경우 interop 서비스 소비자 (환자 앱)에 전달 된 권한 부여 컨텍스트가 Interop 서비스 또는 플랫폼과 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-130">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="6e446-131">환자 앱은 사용자 수준 권한 부여를 적용할 수 없지만 환자 앱과 Interop 파트너의 서비스 간에는 응용 프로그램 인증을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-131">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="6e446-132">응용 프로그램 인증 모델에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e446-132">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="6e446-133">OAuth 2.0 [클라이언트 자격 증명 흐름](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)을 통해 서비스에 대 한 서비스 인증을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-133">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="6e446-134">파트너 서비스는 다음을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-134">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="6e446-135">파트너 서비스를 사용 하면 환자 앱이 파트너와 계정을 만들 수 있으므로 환자 앱에서 파트너의 인증 서버에 있는 Auth registration portal을 통해 관리 되는 client_id 및 client_secret를 생성 하 고 소유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-135">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>
2. <span data-ttu-id="6e446-136">파트너 서비스는 제공 된 클라이언트 자격 증명을 허용 하 고 확인 (인증) 하는 인증/인증 시스템을 소유 하 고 아래 설명 된 대로 범위에서 테 넌 트 힌트를 사용 하 여 액세스 토큰을 다시 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-136">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="6e446-137">보안상의 이유로 또는 비밀 침해의 경우, 환자 앱이 비밀을 다시 생성 하 고, 이전 비밀을 무효로 만들거나 삭제할 수 있습니다 (예를 들어 Azure Portal-AAD 앱 등록에서 사용할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="6e446-137">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>
4. <span data-ttu-id="6e446-138">준수 문을 호스트 하는 메타 데이터 끝점은 인증 되지 않은 토큰 없이 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-138">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="6e446-139">파트너 서비스는 환자 앱에 대 한 토큰 끝점을 제공 하 여 클라이언트 자격 증명 흐름을 사용 하 여 액세스 토큰을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-139">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="6e446-140">권한 부여 서버에 대 한 토큰 url은 다음 예제와 같이 FTO r 서버의 메타 데이터에서 가져온 FE r 준수 (기능) 문의 일부 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-140">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

* * *
    <span data-ttu-id="6e446-141">{"resourceType": "CapabilityStatement",.</span><span class="sxs-lookup"><span data-stu-id="6e446-141">{ "resourceType": "CapabilityStatement", .</span></span>
        <span data-ttu-id="6e446-142">.</span><span class="sxs-lookup"><span data-stu-id="6e446-142">.</span></span>
        <span data-ttu-id="6e446-143">.</span><span class="sxs-lookup"><span data-stu-id="6e446-143">.</span></span>
        <span data-ttu-id="6e446-144">"rest": [{"모드": "서버", "보안": {"확장명": [{"확장명": [{"url": "token", "valueuri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token"}, {"url": "권한 부여", "valueuri":https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize""}http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris"," "서비스": [{"코딩": [{"시스템": "https://hl7.org/fhir/ValueSet/restful-security-service", "코드": "OAuth"}]}]},.</span><span class="sxs-lookup"><span data-stu-id="6e446-144">"rest": [ { "mode": "server", "security": { "extension": [ { "extension": [ { "url": "token", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" }, { "url": "authorize", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize" } ], "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris" } ], "service": [ { "coding": [ { "system": "https://hl7.org/fhir/ValueSet/restful-security-service", "code": "OAuth" } ] } ] }, .</span></span>
                <span data-ttu-id="6e446-145">.</span><span class="sxs-lookup"><span data-stu-id="6e446-145">.</span></span>
                <span data-ttu-id="6e446-146">.</span><span class="sxs-lookup"><span data-stu-id="6e446-146">.</span></span>
            <span data-ttu-id="6e446-147">} ] }</span><span class="sxs-lookup"><span data-stu-id="6e446-147">} ] }</span></span>

* * *

<span data-ttu-id="6e446-148">액세스 토큰에 대 한 요청은 다음 매개 변수로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-148">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="6e446-149">게시/토큰 HTTP/1.1 호스트: authorization-server.com</span><span class="sxs-lookup"><span data-stu-id="6e446-149">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="6e446-150">grant-type = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="6e446-150">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="6e446-151">파트너 서비스는 파트너 측의 Auth registration 포털을 통해 관리 되는 환자 앱에 대 한 client_id 및 client_secret를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-151">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="6e446-152">파트너 서비스는 끝점을 제공 하 여 클라이언트 자격 증명 흐름을 사용 하 여 액세스 토큰을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-152">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="6e446-153">성공적인 응답에는 token_type, access_token expires_in 매개 변수가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-153">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="6e446-154">라우팅: AAD 테 넌 트를 공급자 끝점으로 매핑</span><span class="sxs-lookup"><span data-stu-id="6e446-154">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="6e446-155">환자 앱은 단일 끝점을 통해 파트너 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-155">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="6e446-156">파트너 서비스는 각 Microsoft 고객 (AAD 테 넌 트 ID)을 파트너 서비스가 작동 하는 각 건강 보험 공급자 (FA r)에 매핑하는 메커니즘을 소유 하 고 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-156">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="6e446-157">AAD 테 넌 트를 공급자 끝점에 매핑하면 AAD 테 넌 트 ID (GUID)가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-157">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="6e446-158">환자 앱은 범위에서 테 넌 트 ID를 전달 하 고 각 요청에 대해 액세스 토큰을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-158">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="6e446-159">파트너 서비스는 공급자 끝점에 테 넌 트 ID 매핑을 유지 하 고 테 넌 트 ID에 따라 요청을 공급자 끝점으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-159">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="6e446-160">이를 위해 파트너는 해당 사용자의 끝점에 대 한 구성을 수동으로 지원 하거나 (공급자 조직을 해당 Interop 플랫폼에 온 보 딩 하는 방법으로 포털을 통해).</span><span class="sxs-lookup"><span data-stu-id="6e446-160">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="6e446-161">인증 및 라우팅 워크플로가 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-161">The Authentication and Routing workflow is shown below:</span></span>

![인증 및 라우팅 워크플로 다이어그램](../../media/Patient-app-6.png)

1. <span data-ttu-id="6e446-163">보내는 방법으로 앱 액세스 토큰 요청:</span><span class="sxs-lookup"><span data-stu-id="6e446-163">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="6e446-164">앱 토큰을 사용 하 여 회신:</span><span class="sxs-lookup"><span data-stu-id="6e446-164">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="6e446-165">액세스 토큰을 사용 하 여 보호 된 데이터를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-165">Request protected data with Access token.</span></span>
4. <span data-ttu-id="6e446-166">인증 메시지: 범위에서 테 넌 트 ID에서 라우팅할 적절 한 FA r 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-166">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="6e446-167">앱 토큰을 사용 하 여 인증 한 후 권한 있는 FA r 서버에서 보호 된 데이터를 앱에서 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-167">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="6e446-168">인터페이스</span><span class="sxs-lookup"><span data-stu-id="6e446-168">Interfaces</span></span>

<span data-ttu-id="6e446-169">환자 앱에서 사용 되는 특정 통화 및 필드는 다음 문서에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-169">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="6e446-170">해당 인터페이스를 선택 하 여 FE r server/FA r (Api)에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-170">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="6e446-171">DSTU2 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="6e446-171">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="6e446-172">STU3 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="6e446-172">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="6e446-173">성능 및 안정성</span><span class="sxs-lookup"><span data-stu-id="6e446-173">Performance and Reliability</span></span>

<span data-ttu-id="6e446-174">환자 앱은 비공개 미리 보기에 있지만 종단 간 성능이 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-174">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="6e446-175">성능 요인에는 상태 시스템 환경의 EHR에서 시작 하 여 워크플로 관련 모든 홉의 상대적 대기 시간이 포함 되며,이는 f r 서버를 비롯 하 여 Office 365 에코 시스템과 환자 앱을 포함 하는 Interop 파트너 및 해당 infra에 대해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-175">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Interop 파트너 성능 그림](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="6e446-177">이력서 시작 하기</span><span class="sxs-lookup"><span data-stu-id="6e446-177">Get started with FHIR</span></span>  

<span data-ttu-id="6e446-178">FA r을 처음 사용 하는 경우 Microsoft 팀 EHR 통합 인터페이스에 노출할 수 있는 FA r 서버에 대 한 액세스 권한이 필요한 경우 Microsoft는 모든 개발자가 사용할 수 있는 오픈 소스 FA r 서버를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-178">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="6e446-179">Microsoft에서 제공 하는 오픈 소스 FTO r 서버에 대 한 자세한 정보를 확인 하 고 조직에 대해 배포 하는 방법에 대해 자세히 알아보려면 다음 [항목](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e446-179">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="6e446-180">HSPC Open 샌드박스 EHR environment를 사용 하 여 열려 있는 FHIR 서버를 지원 하 고이를 사용 하 여 환자 앱에서 재생 하는 EHR를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-180">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="6e446-181">[Hspc 샌드박스 설명서](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)를 참조 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-181">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="6e446-182">샌드박스는 손쉽게 환자를 만들고, 추가 하 고, 편집할 수 있는 방법을 제공 하는 것이 아니라 몇 가지 샘플을 사용 하 여 시작 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-182">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span>  

## <a name="enroll-in-the-private-preview"></a><span data-ttu-id="6e446-183">개인 미리 보기에서 등록</span><span class="sxs-lookup"><span data-stu-id="6e446-183">Enroll in the private preview</span></span>

<span data-ttu-id="6e446-184">오픈 소스 FA r 서버를 만든 후에는 아래 언급 된 단계에 따라 테 넌 트 내에서 환자 앱에 연결 하는 것이 매우 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-184">Once you've created the open source FHIR Server, it's really easy to connect to the Patients app inside of your tenant by following the steps mentioned below:</span></span>

1. <span data-ttu-id="6e446-185">다음 초기 세부 정보로 [문의 하세요](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview) .</span><span class="sxs-lookup"><span data-stu-id="6e446-185">[Contact us](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20private%20preview) with the following initial details:</span></span>  
    - <span data-ttu-id="6e446-186">사용자 이름</span><span class="sxs-lookup"><span data-stu-id="6e446-186">Your Name</span></span>
    - <span data-ttu-id="6e446-187">위치</span><span class="sxs-lookup"><span data-stu-id="6e446-187">Your Position</span></span>
    - <span data-ttu-id="6e446-188">대표 하는 회사나 조직</span><span class="sxs-lookup"><span data-stu-id="6e446-188">The company or organization you represent</span></span>
    - <span data-ttu-id="6e446-189">환자 앱에서 EHR 통합용으로 관심이 있는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="6e446-189">Why you are interested in the Patients app for EHR integration</span></span>

    <span data-ttu-id="6e446-190">더 많은 질문을 포함 하 여 즉시 사용자에 게 다시 전화를 걸고 개인 미리 보기를 설정 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-190">We will get back to you as soon as possible with more questions and guide you through a process to get set up for the private preview.</span></span>

2. <span data-ttu-id="6e446-191">환자 앱을 사용해 보려는 테 넌 트에서 사용자 지정 앱의 테스트용 로드를 사용 하도록 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-191">Ensure that sideloading of custom apps is enabled in the tenant where you are going to try out the Patients app.</span></span> <span data-ttu-id="6e446-192">사용자 또는 고객의 테 넌 트에 대 한 팀 관리 센터에서이 기능을 설정 하는 방법을 알아보려면 [앱 권한 정책을](../../admin-settings.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6e446-192">Please refer to [App permission policies](../../admin-settings.md) to learn how to turn this on from the Teams Admin center for your or your customer's tenant.</span></span>

3. <span data-ttu-id="6e446-193">Microsoft에서 테스트용으로 로드 (전자 메일을 처리 한 후)에서 제공 하는 환자 앱 매니페스트를 테 넌 트에서 조심 스럽게 조정 하 고 환자 반올림 시나리오에 사용할 팀으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-193">Sideload the Patients app manifest that you will get from Microsoft (after we process your email to us) into a team in the tenant that is going to be used for care-coordination and patient rounding scenarios.</span></span> <span data-ttu-id="6e446-194">앱을 로드 하는 방법에 대 한 자세한 지침은 [Microsoft 팀에 앱 패키지 업로드](/microsoftteams/platform/concepts/apps/apps-upload) 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6e446-194">Detailed instructions around how to side-load an app are in [Upload an app package to Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload)</span></span>

4. <span data-ttu-id="6e446-195">팀 소유자로 일반 채널로 이동한 다음 환자 탭을 클릭 합니다. EHR 모드 및 수동 모드와 같은 두 가지 옵션을 제공 하는 첫 실행 환경이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-195">Navigate to the general channel as the Team owner and then click on the Patients tab. You should see a first run experience that will present two options i.e. EHR Mode and Manual Mode.</span></span> <span data-ttu-id="6e446-196">**EHR 모드** 를 선택 하 고, 앞에 있는 모든 필수 데이터 및 리소스를 사용 하 여 위의 사양에 따라 설치 하는 것 처럼 표시 되는 Fe r server 끝점을 링크 필드에 복사 하 고 연결에 f r 서버를 잘 나타내는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-196">Please select the **EHR mode** and copy the FHIR Server endpoint (that you've just setup earlier with all the required data and resources per the specifications above) into the Link field and give the connection a name that well represents the FHIR Server.</span></span> <span data-ttu-id="6e446-197">연결을 클릭 하면 모든 준비가 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-197">Click on Connect, and everything should be ready to go.</span></span>

    ![환자 app server 설정 스크린샷](../../media/patients-server.png)

5. <span data-ttu-id="6e446-199">앱을 사용 하 여 FHIR Server/EHR에서 환자를 검색 하 고 목록에 추가 하 고 문제가 해결 되지 않는 경우 [피드백을 제공](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback) 해 주세요.</span><span class="sxs-lookup"><span data-stu-id="6e446-199">Start using the app to search for Patients from the FHIR Server/EHR and add them to a list and please [give us feedback](mailto:Teamsforhealthcare@service.microsoft.com?subject=Microsoft%20Teams%20Patients%20App%20feedback) if something doesn't work.</span></span> <span data-ttu-id="6e446-200">또한, 환자 app-> f r Server flow의 완전히 인증 된 버전을 설정 하려면 Microsoft 팀에서 의료 제품 엔지니어링을 위해 앞에서 언급 한 전자 메일 요청을 통해 요구 사항을 명확 하 게 설명 하 고이를 사용 하 여 앞에서 설명한 인증 요구 사항에 따라이를 지원 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e446-200">Also, to establish a fully authenticated version of the Patients app -> FHIR Server flow, please engage in offline dialogue with Microsoft Teams for healthcare product engineering, through the email request mentioned earlier to clarify requirements and we will help enable this for you per the Authentication requirements described above in the FHIR Interface document.</span></span>  
