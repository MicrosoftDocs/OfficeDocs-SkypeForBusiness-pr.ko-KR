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
ms.openlocfilehash: 29bb5b32cdd6e2f0d819adcc610639929921d078
ms.sourcegitcommit: 3b54a56ec1fe4366580621e19cdbb6a833a01161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48361388"
---
# <a name="integrating-electronic-healthcare-records-into-microsoft-teams"></a><span data-ttu-id="5d6fc-103">Microsoft Teams에 전자 의료 레코드 통합</span><span class="sxs-lookup"><span data-stu-id="5d6fc-103">Integrating Electronic Healthcare Records into Microsoft Teams</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d6fc-104">**2020 년 10 월 15 일에는 환자 앱이 더 이상 사용 되지 않으며 사용자는 더 이상 팀 앱 스토어에서 설치할 수 없게 됩니다. 지금 팀에서 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 사용을 시작 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="5d6fc-104">**Effective October 15, 2020, the Patients app will be deprecated and users will no longer be able to install it from the Teams app store. We encourage you to start using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) in Teams today.**</span></span>
>
><span data-ttu-id="5d6fc-105">환자 앱 데이터는 팀을 백업 하는 Office 365 그룹의 그룹 사서함에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-105">Patients app data is stored in the group mailbox of the Office 365 group that backs the team.</span></span> <span data-ttu-id="5d6fc-106">환자 앱이 종료 되 면 관련 된 모든 데이터는이 그룹에 보존 되지만 사용자 인터페이스를 통해 더 이상 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-106">When the Patients app is retired, all data associated with it will be retained in this group but can no longer be accessed through the user interface.</span></span> <span data-ttu-id="5d6fc-107">현재 사용자는 [목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)을 사용 하 여 목록을 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-107">Current users can re-create their lists using the [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db).</span></span>
>
><span data-ttu-id="5d6fc-108">[목록 앱](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 은 모든 팀 사용자를 위해 사전 설치 되어 있으며 모든 팀과 채널에서 탭으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-108">The [Lists app](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) is pre-installed for all Teams users and is available as a tab in every team and channel.</span></span> <span data-ttu-id="5d6fc-109">목록에서 기본 제공 환자 서식 파일을 사용 하거나, 처음부터 또는 Excel로 데이터를 가져오면 환자 목록을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-109">With Lists, care teams can create patient lists using the built-in Patients template, from scratch, or by importing data to Excel.</span></span> <span data-ttu-id="5d6fc-110">조직에서 목록 앱을 관리 하는 방법에 대해 자세히 알아보려면 [목록 앱 관리](../../manage-lists-app.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-110">To learn more about how to manage the Lists app in your organization, see [Manage the Lists app](../../manage-lists-app.md).</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="5d6fc-111">이 문서는 Microsoft 팀에 연결 하기 위해 의료 정보 시스템의 맨 위에 FA r Api를 사용 하는 데 관심이 있는 일반 의료 IT 개발자를 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-111">This article is intended for a general healthcare IT developer interested in using FHIR APIs on top of a medical information system to connect to Microsoft Teams.</span></span> <span data-ttu-id="5d6fc-112">이는 의료 조직의 요구 사항에 맞는 의료 조정 시나리오를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-112">This would enable care coordination scenarios that match the needs of a healthcare organization.</span></span>

<span data-ttu-id="5d6fc-113">연결 된 문서 Microsoft 팀 환자 앱에 대 한 f r 인터페이스 사양을 문서화 하 고, 다음 섹션에서는 f r 서버를 설정 하 고 개발 환경 또는 테 넌 트에서 환자 앱에 연결 하는 데 필요한 사항에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-113">Linked articles document the FHIR interface specifications for the Microsoft Teams Patients app, and following sections explain what is required for setting up a FHIR server and connecting to the Patients app in your development environment or tenant.</span></span> <span data-ttu-id="5d6fc-114">또한 지원 되는 옵션 중 하나 여야 하는 선택한 FE r server의 설명서에 대해 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-114">You will also need to be familiar with the documentation of the FHIR server you have chosen, which must be one of the supported options:</span></span>
- <span data-ttu-id="5d6fc-115">Datica ( [CMI](https://datica.com/compliant-managed-integration/) 제공)</span><span class="sxs-lookup"><span data-stu-id="5d6fc-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="5d6fc-116">Cloverleaf ( [INFOR FA r 브리지](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html)를 통해)</span><span class="sxs-lookup"><span data-stu-id="5d6fc-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="5d6fc-117">Redox ( [r ^ FA r 서버](https://www.redoxengine.com/fhir/)통과)</span><span class="sxs-lookup"><span data-stu-id="5d6fc-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="5d6fc-118">Dapasoft ( [FA r의 Corolar](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="5d6fc-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

> [!NOTE]
> <span data-ttu-id="5d6fc-119">이 프로세스에는 Microsoft 팀 관리 센터 또는 PowerShell cmdlet을 사용 하 여 기능을 사용 하도록 설정 하는 단계가 포함 되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-119">This process does not includes steps that use the Microsoft Teams admin center or PowerShell cmdlets to enable features.</span></span> <span data-ttu-id="5d6fc-120">이 구성은 모두 FTO r 서버/서비스 쪽 및 환자 앱 클라이언트에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-120">The configuration is entirely done on the FHIR server/service side and in the Patients app client.</span></span>

<span data-ttu-id="5d6fc-121">아래에는 환자 앱의 아키텍처가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-121">Illustrated below is the architecture of the Patients app:</span></span>

![환자 앱 아키텍처의 다이어그램](../../media/patients-app-architecture.png)

<span data-ttu-id="5d6fc-123">다음 섹션에서는 환자 앱에 대 한 FA r 전용 데이터 액세스 계층의 요구 사항에 대해 설명 하며,이는 다음을 포함 하 여 환자 앱과 통합 하기 위해 f r 서버 (또는 EHR enabled FA r Api)가 충족 해야 하는 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-123">The following sections explain the requirements of the FHIR-only data access layer for the Patients app that a FHIR server (or EHR enabled FHIR APIs) must meet in order to integrate with the Patients app, including the following:</span></span>

- <span data-ttu-id="5d6fc-124">사용자 인증 관련 예측</span><span class="sxs-lookup"><span data-stu-id="5d6fc-124">Expectations around user authentication</span></span>
- <span data-ttu-id="5d6fc-125">통합 인터페이스의 기능 및 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d6fc-125">Functional and technical requirements of the integration interface</span></span>
- <span data-ttu-id="5d6fc-126">성능 및 안정성에 대 한 기대</span><span class="sxs-lookup"><span data-stu-id="5d6fc-126">Expectations around performance and reliability</span></span>
- <span data-ttu-id="5d6fc-127">환자 앱에 대해 지원 되는 f r 리소스에 대 한 기대</span><span class="sxs-lookup"><span data-stu-id="5d6fc-127">Expectations around FHIR resources to be supported for the Patients app</span></span>
- <span data-ttu-id="5d6fc-128">통합 프로세스 및 예상 되는 계약 모델</span><span class="sxs-lookup"><span data-stu-id="5d6fc-128">Process for integration and the expected engagement model</span></span>
- <span data-ttu-id="5d6fc-129">환자 앱을 사용 하 여 시작 하는 방법 및 몇 가지 일반적인 과제에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-129">How to get started with FHIR and some common challenges faced with the Patients app</span></span>
- <span data-ttu-id="5d6fc-130">환자 앱의 다음 반복에 대 한 향후 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d6fc-130">Future requirements for the next iteration of the Patients app</span></span>

> [!NOTE]
> <span data-ttu-id="5d6fc-131">다음 섹션에서는 "partner" 또는 "Interop 파트너" 라는 단어를 사용 하 여 환자 앱에 대 한 EHR 시스템과 통합할 수 있는 타사 조직을 참조 하 고 나열 된 사양과 일치 하도록 FA r 서버를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-131">In the following sections, the word "partner" or "Interop partner" is used to refer to any 3rd party Organization that enables integration to EHR systems for the Patients app through FHIR and is implementing a FHIR Server to match the listed specifications.</span></span>

## <a name="functional-and-technical-requirements"></a><span data-ttu-id="5d6fc-132">기능적 및 기술 요구 사항</span><span class="sxs-lookup"><span data-stu-id="5d6fc-132">Functional and technical requirements</span></span>  

### <a name="authentication"></a><span data-ttu-id="5d6fc-133">인증</span><span class="sxs-lookup"><span data-stu-id="5d6fc-133">Authentication</span></span>  

<span data-ttu-id="5d6fc-134">*사용자 수준 권한 부여를 지원 하지 않는* 앱 수준 권한 부여는 EHR 시스템에서 사용자 수준 권한 부여를 구현할 수 있지만 데이터 변환을 수행 하 고 EHR 데이터에 대 한 연결을 표시 하는 데 더 일반적으로 지원 되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-134">App-level authorization *with no support for user level authorization* is the more commonly supported way to perform data transformations and expose connections to EHR data through FHIR, even though the EHR system might implement user level authorization.</span></span> <span data-ttu-id="5d6fc-135">Interop 서비스 (파트너)는 EHR 데이터에 대 한 액세스 권한을 강화 하 고, 해당 데이터를 적절 한 f r 리소스와 동일 하 게 표시 하는 경우 interop 서비스 소비자 (환자 앱)에 전달 된 권한 부여 컨텍스트가 Interop 서비스 또는 플랫폼과 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-135">The Interop Service (Partner) gets elevated access to the EHR data, and when they expose the same data as the appropriate FHIR resources there is no authorization context passed on to the Interop Service Consumer (the Patients app) integrating with the Interop Service or Platform.</span></span> <span data-ttu-id="5d6fc-136">환자 앱은 사용자 수준 권한 부여를 적용할 수 없지만 환자 앱과 Interop 파트너의 서비스 간에는 응용 프로그램 인증을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-136">The Patients app will not be able to enforce user level authorization, but does support application to application authentication between the Patients app and the Interop partner's service.</span></span>

<span data-ttu-id="5d6fc-137">응용 프로그램 인증 모델에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-137">The Application to Application authentication model is described below:</span></span>

<span data-ttu-id="5d6fc-138">OAuth 2.0 [클라이언트 자격 증명 흐름](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/)을 통해 서비스에 대 한 서비스 인증을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-138">Service to service authentication should be done through OAuth 2.0 [Client Credential flow](https://www.oauth.com/oauth2-servers/access-tokens/client-credentials/).</span></span> <span data-ttu-id="5d6fc-139">파트너 서비스는 다음을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-139">The partner service needs to provide the following:</span></span>

1. <span data-ttu-id="5d6fc-140">파트너 서비스를 사용 하면 환자 앱이 파트너와 계정을 만들 수 있으므로 환자 앱에서 파트너의 인증 서버에 있는 Auth registration portal을 통해 관리 되는 client_id 및 client_secret를 생성 하 고 소유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-140">The Partner service enables the Patients app to create an account with the Partner, which enables the Patients app to generate and own client_id and client_secret, managed via an Auth registration portal on the partner's Authentication server.</span></span>
2. <span data-ttu-id="5d6fc-141">파트너 서비스는 제공 된 클라이언트 자격 증명을 허용 하 고 확인 (인증) 하는 인증/인증 시스템을 소유 하 고 아래 설명 된 대로 범위에서 테 넌 트 힌트를 사용 하 여 액세스 토큰을 다시 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-141">The Partner service owns the Authentication/Authorization system, which accepts and verifies (authenticates) the client credentials provided and gives back an access token with tenant hint in scope, as described below.</span></span>
3. <span data-ttu-id="5d6fc-142">보안상의 이유로 또는 비밀 침해의 경우, 환자 앱이 비밀을 다시 생성 하 고, 이전 비밀을 무효로 만들거나 삭제할 수 있습니다 (예를 들어 Azure Portal-AAD 앱 등록에서 사용할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="5d6fc-142">For security reasons or in a case of a secret breach, the Patients app can re-generate the secret and invalidate or delete the old secret (example of the same is available in Azure Portal - AAD App Registration).</span></span>
4. <span data-ttu-id="5d6fc-143">준수 문을 호스트 하는 메타 데이터 끝점은 인증 되지 않은 토큰 없이 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-143">The metadata endpoint hosting the conformance statement should be un-authenticated, it should be accessible without authentication token.</span></span>
5. <span data-ttu-id="5d6fc-144">파트너 서비스는 환자 앱에 대 한 토큰 끝점을 제공 하 여 클라이언트 자격 증명 흐름을 사용 하 여 액세스 토큰을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-144">The Partner service provides the token endpoint for the Patients app to request an access token using a client credential flow.</span></span> <span data-ttu-id="5d6fc-145">권한 부여 서버에 대 한 토큰 url은 다음 예제와 같이 FTO r 서버의 메타 데이터에서 가져온 FE r 준수 (기능) 문의 일부 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-145">The token url as per authorization server should be part of the FHIR conformance (capability) statement fetched from metadata on the FHIR server as in this example:</span></span>

* * *
    <span data-ttu-id="5d6fc-146">{"resourceType": "CapabilityStatement",.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-146">{ "resourceType": "CapabilityStatement", .</span></span>
        <span data-ttu-id="5d6fc-147">.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-147">.</span></span>
        <span data-ttu-id="5d6fc-148">.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-148">.</span></span>
        <span data-ttu-id="5d6fc-149">"rest": [{"모드": "서버", "보안": {"확장명": [{"확장명": [{"url": "token", "valueUri": " https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token "}, {"url": "권한 부여", "valueUri": ""} "," " https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris 서비스": [{"코딩": [{"시스템": "", "코드": " https://hl7.org/fhir/ValueSet/restful-security-service OAuth"}]}]},.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-149">"rest": [ { "mode": "server", "security": { "extension": [ { "extension": [ { "url": "token", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/token" }, { "url": "authorize", "valueUri": "https://login.contoso.com/145f4184-1b0b-41c7-ba24-b3c1291bfda1/oauth2/authorize" } ], "url": "http://fhir-registry.smarthealthit.org/StructureDefinition/oauth-uris" } ], "service": [ { "coding": [ { "system": "https://hl7.org/fhir/ValueSet/restful-security-service", "code": "OAuth" } ] } ] }, .</span></span>
                <span data-ttu-id="5d6fc-150">.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-150">.</span></span>
                <span data-ttu-id="5d6fc-151">.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-151">.</span></span>
            <span data-ttu-id="5d6fc-152">} ] }</span><span class="sxs-lookup"><span data-stu-id="5d6fc-152">} ] }</span></span>

* * *

<span data-ttu-id="5d6fc-153">액세스 토큰에 대 한 요청은 다음 매개 변수로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-153">A request for an access token consists of the following parameters:</span></span>

* * *

    <span data-ttu-id="5d6fc-154">게시/토큰 HTTP/1.1 호스트: authorization-server.com</span><span class="sxs-lookup"><span data-stu-id="5d6fc-154">POST /token HTTP/1.1 Host: authorization-server.com</span></span>

    <span data-ttu-id="5d6fc-155">grant-type = client_credentials &client_id = xxxxxxxxxx &client_secret = xxxxxxxxxx</span><span class="sxs-lookup"><span data-stu-id="5d6fc-155">grant-type=client_credentials &client_id=xxxxxxxxxx &client_secret=xxxxxxxxxx</span></span>

* * *

<span data-ttu-id="5d6fc-156">파트너 서비스는 파트너 측의 Auth registration 포털을 통해 관리 되는 환자 앱에 대 한 client_id 및 client_secret를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-156">The Partner service provides the client_id and client_secret for Patients app, managed via an Auth registration portal on the partner's side.</span></span> <span data-ttu-id="5d6fc-157">파트너 서비스는 끝점을 제공 하 여 클라이언트 자격 증명 흐름을 사용 하 여 액세스 토큰을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-157">The Partner service provides the endpoint to request access token using a client credential flow.</span></span> <span data-ttu-id="5d6fc-158">성공적인 응답에는 token_type, access_token expires_in 매개 변수가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-158">A successful response must include the token_type, access_token and expires_in parameters.</span></span>

### <a name="routing-mapping-aad-tenant-to-the-provider-endpoint"></a><span data-ttu-id="5d6fc-159">라우팅: AAD 테 넌 트를 공급자 끝점으로 매핑</span><span class="sxs-lookup"><span data-stu-id="5d6fc-159">Routing: Mapping AAD Tenant to the Provider endpoint</span></span>

<span data-ttu-id="5d6fc-160">환자 앱은 단일 끝점을 통해 파트너 서비스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-160">The Patients app connects to a partner service through a single endpoint.</span></span> <span data-ttu-id="5d6fc-161">파트너 서비스는 각 Microsoft 고객 (AAD 테 넌 트 ID)을 파트너 서비스가 작동 하는 각 건강 보험 공급자 (FA r)에 매핑하는 메커니즘을 소유 하 고 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-161">The Partner service owns and maintains a mechanism to map each Microsoft customer (AAD Tenant ID) to a respective healthcare Provider (FHIR server) that the Partner service is working with.</span></span>

<span data-ttu-id="5d6fc-162">AAD 테 넌 트를 공급자 끝점에 매핑하면 AAD 테 넌 트 ID (GUID)가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-162">Mapping the AAD tenant to a provider endpoint uses the AAD Tenant ID (GUID).</span></span> <span data-ttu-id="5d6fc-163">환자 앱은 범위에서 테 넌 트 ID를 전달 하 고 각 요청에 대해 액세스 토큰을 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-163">The Patients app passes the Tenant ID in scope, while requesting an access-token for each request.</span></span> <span data-ttu-id="5d6fc-164">파트너 서비스는 공급자 끝점에 테 넌 트 ID 매핑을 유지 하 고 테 넌 트 ID에 따라 요청을 공급자 끝점으로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-164">The Partner service keeps the mapping of Tenant ID to Provider endpoint and redirects requests to a provider endpoint based on the Tenant ID.</span></span> <span data-ttu-id="5d6fc-165">이를 위해 파트너는 해당 사용자의 끝점에 대 한 구성을 수동으로 지원 하거나 (공급자 조직을 해당 Interop 플랫폼에 온 보 딩 하는 방법으로 포털을 통해).</span><span class="sxs-lookup"><span data-stu-id="5d6fc-165">To do this, the partner supports the configuration on their end (manually or via a portal as part of onboarding of provider organizations to their Interop Platform).</span></span>

<span data-ttu-id="5d6fc-166">인증 및 라우팅 워크플로가 아래에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-166">The Authentication and Routing workflow is shown below:</span></span>

![인증 및 라우팅 워크플로 다이어그램](../../media/Patient-app-6.png)

1. <span data-ttu-id="5d6fc-168">보내는 방법으로 앱 액세스 토큰 요청:</span><span class="sxs-lookup"><span data-stu-id="5d6fc-168">Request for app access token by sending:</span></span>
 
        {   grant_type: client_credentials,
            client_id: xxxxxx, 
            client_secret: xxxxxx,
            scope: {Provider Identifier, Ex: tenant ID}
        }

2. <span data-ttu-id="5d6fc-169">앱 토큰을 사용 하 여 회신:</span><span class="sxs-lookup"><span data-stu-id="5d6fc-169">Reply with an app token:</span></span>

        {  access_token: {JWT, with scope: tenant ID},
           expires_in: 156678,
           token_type: "Bearer",
        }

3. <span data-ttu-id="5d6fc-170">액세스 토큰을 사용 하 여 보호 된 데이터를 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-170">Request protected data with Access token.</span></span>
4. <span data-ttu-id="5d6fc-171">인증 메시지: 범위에서 테 넌 트 ID에서 라우팅할 적절 한 FA r 서버를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-171">Authorization message: Select the appropriate FHIR server to route to from tenant ID in scope</span></span>
5. <span data-ttu-id="5d6fc-172">앱 토큰을 사용 하 여 인증 한 후 권한 있는 FA r 서버에서 보호 된 데이터를 앱에서 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-172">Sends the app protected  data from the authorized FHIR server after authenticating with the app token.</span></span>

## <a name="interfaces"></a><span data-ttu-id="5d6fc-173">인터페이스</span><span class="sxs-lookup"><span data-stu-id="5d6fc-173">Interfaces</span></span>

<span data-ttu-id="5d6fc-174">환자 앱에서 사용 되는 특정 통화 및 필드는 다음 문서에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-174">Specific calls and fields used by the Patients app are documented in the following articles.</span></span> <span data-ttu-id="5d6fc-175">해당 인터페이스를 선택 하 여 FE r server/FA r (Api)에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-175">Select the interface applicable to your FHIR server/FHIR APIs.</span></span>

- [<span data-ttu-id="5d6fc-176">DSTU2 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="5d6fc-176">DSTU2 interface specification</span></span>](dstu2-interface.md)
- [<span data-ttu-id="5d6fc-177">STU3 인터페이스 사양</span><span class="sxs-lookup"><span data-stu-id="5d6fc-177">STU3 interface specification</span></span>](stu3-interface.md)

## <a name="performance-and-reliability"></a><span data-ttu-id="5d6fc-178">성능 및 안정성</span><span class="sxs-lookup"><span data-stu-id="5d6fc-178">Performance and Reliability</span></span>

<span data-ttu-id="5d6fc-179">환자 앱은 비공개 미리 보기에 있지만 종단 간 성능이 보장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-179">While the Patients app is in private preview, there are no guarantees on the end-to-end performance.</span></span> <span data-ttu-id="5d6fc-180">성능 요인에는 상태 시스템 환경의 EHR에서 시작 하 여 워크플로 관련 모든 홉의 상대적 대기 시간이 포함 되며,이는 f r 서버를 비롯 하 여 Office 365 에코 시스템과 환자 앱을 포함 하는 Interop 파트너 및 해당 infra에 대해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-180">Factors in performance include the relative latencies of all the hops involved in the workflow, starting from the EHR in the health system's environment, to the Interop partner and their infra, including the FHIR Server and across to the Office 365 ecosystem and Patients app.</span></span>

![Interop 파트너 성능 그림](../../media/FHIR.png)

## <a name="get-started-with-fhir"></a><span data-ttu-id="5d6fc-182">이력서 시작 하기</span><span class="sxs-lookup"><span data-stu-id="5d6fc-182">Get started with FHIR</span></span>  

<span data-ttu-id="5d6fc-183">FA r을 처음 사용 하는 경우 Microsoft 팀 EHR 통합 인터페이스에 노출할 수 있는 FA r 서버에 대 한 액세스 권한이 필요한 경우 Microsoft는 모든 개발자가 사용할 수 있는 오픈 소스 FA r 서버를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-183">If you're new to FHIR and need easy access to a FHIR Server that you can expose to the Microsoft Teams EHR integration interface, Microsoft has an open-source FHIR Server available for all developers to use.</span></span> <span data-ttu-id="5d6fc-184">Microsoft에서 제공 하는 오픈 소스 FTO r 서버에 대 한 자세한 정보를 확인 하 고 조직에 대해 배포 하는 방법에 대해 자세히 알아보려면 다음 [항목](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-184">Please see the [What is FHIR Server for Azure](https://docs.microsoft.com/azure/healthcare-apis/overview-open-source-server) article to learn more about the open source FHIR Server available from Microsoft and deploy it for your organizations.</span></span>

<span data-ttu-id="5d6fc-185">HSPC Open 샌드박스 EHR environment를 사용 하 여 열려 있는 FHIR 서버를 지원 하 고이를 사용 하 여 환자 앱에서 재생 하는 EHR를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-185">You can also use the HSPC Open sandbox EHR environment to create an an EHR which also supports an open FHIR Server and use this to play around with the Patients app.</span></span> <span data-ttu-id="5d6fc-186">[Hspc 샌드박스 설명서](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox)를 참조 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-186">We recommend that you read through the [HSPC Sandbox documentation](https://healthservices.atlassian.net/wiki/spaces/HSPC/pages/64585866/HSPC+Sandbox).</span></span> <span data-ttu-id="5d6fc-187">샌드박스는 손쉽게 환자를 만들고, 추가 하 고, 편집할 수 있는 방법을 제공 하는 것이 아니라 몇 가지 샘플을 사용 하 여 시작 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d6fc-187">Not only does the sandbox provide an easy, UI oriented, and user friendly way of creating, adding and editing Patients, it also gives you several samples to get started.</span></span> 