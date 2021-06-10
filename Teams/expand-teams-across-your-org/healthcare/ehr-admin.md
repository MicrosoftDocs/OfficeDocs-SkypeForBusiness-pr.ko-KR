---
title: 가상 방문을 위한 Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: Microsoft Teams를 사용하여 가상 방문 시스템 설정
ms.openlocfilehash: 9c002a90cd91014ca4887386ca5834a4b5b41266
ms.sourcegitcommit: d73dc8505a5cc5af29635a50cbbf0f25bbb17eac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52705252"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="89058-103">Teams를 사용하여 가상 방문 - EHR에 통</span><span class="sxs-lookup"><span data-stu-id="89058-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="89058-104">Microsoft Teams EHR(Electronic Health Record) 커넥터를 사용하면 임상의가 EHR 시스템에서 직접 가상 환자 방문 또는 상담을 Teams 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-104">Microsoft Teams Electronic Health Record (EHR) connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="89058-105">Microsoft 365 클라우드를 기반으로 구축된 Microsoft Teams는 HIPAA, HITECH 인증 준수를 지원하는 단일 허브에서 채팅, 비디오, 음성, 의료 도구를 사용하여 간단하고 안전하게 공동 작업 및 커뮤니케이션을 수행할 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="89058-106">Teams의 통신 및 공동 작업 플랫폼을 사용하면 임상의들이 파편화된 시스템의 어수선한 작업을 손쉽게 제거하여 최상의 서비스를 제공하는 데 시간을 투자할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="89058-107">Microsoft Teams EHR(전자 상태 레코드) 커넥터는 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-107">Microsoft Teams Electronic Health Record (EHR) connector can:</span></span>

- <span data-ttu-id="89058-108">통합된 Teams EHR 시스템에서 가상 방문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-108">Launch Teams virtual visits from the provider EHR system with an integrated clinical workflow.</span></span>
- <span data-ttu-id="89058-109">환자 포털 내에서 가상 Teams 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-109">Enable patients to join Teams virtual visits from within the patient portal.</span></span>
- <span data-ttu-id="89058-110">참석자 연결 및 연결을 끊고 자동 감사 및 레코드 유지를 사용하도록 설정하는 Teams 가상 방문과 관련하여 EHR 시스템에 다시 메타데이터를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-110">Write metadata back to the EHR system regarding Teams virtual visits to record when attendees connect and disconnect and enable automatic auditing and record keeping.</span></span>

  <span data-ttu-id="89058-111">EHR 포털에서 가상 방문을 관리하는 방법에 대한 비디오를 시청해 보세요.</span><span class="sxs-lookup"><span data-stu-id="89058-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="89058-112">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="89058-112">Before you begin</span></span>

<span data-ttu-id="89058-113">EHR 커넥터를 통합하기 전에 다음과 같은 필수 구성 요소가 갖춰져 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="89058-114">[Epic의 App Orchard 마켓 플레이스](https://apporchard.epic.com/Gallery?id=6153)의 Microsoft Teams 앱에 대한 액세스.</span><span class="sxs-lookup"><span data-stu-id="89058-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="89058-115">Microsoft Cloud for Healthcare에 대한 활성 구독 또는 EHR Microsoft Teams 독립 실행형 제품(프로덕션 테스트 중에만 적용)에 대한 구독입니다.</span><span class="sxs-lookup"><span data-stu-id="89058-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="89058-116">사용자에게 Microsoft Teams 모임을 포함하는 적절한 Microsoft 365 또는 Office 365 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="89058-117">조직 내부에서 Microsoft Teams를 채택하고 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="89058-118">조직에 2018년 11월 버전 이상이 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="89058-119">시스템이 모든 [소프트웨어 및 브라우저 필수 요구 사항](../../hardware-requirements-for-the-teams-app.md)을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-119">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

<span data-ttu-id="89058-120">또한 조직의 다음 사용자로부터 정보를 제공 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="89058-121">Microsoft 365 관리자</span><span class="sxs-lookup"><span data-stu-id="89058-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="89058-122">Epic 고객 분석가</span><span class="sxs-lookup"><span data-stu-id="89058-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="89058-123">Epic 기술 전문가와 함께 [Epic-Microsoft 팀 원격 상태 통합 가이드](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357)를 검토해 보세요.</span><span class="sxs-lookup"><span data-stu-id="89058-123">Review the [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) with your Epic technical specialist.</span></span> <span data-ttu-id="89058-124">모든 사전 준비를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-124">Make sure that all pre-requisites are completed.</span></span> 

## <a name="connector-setup"></a><span data-ttu-id="89058-125">커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="89058-125">Connector setup</span></span>

<span data-ttu-id="89058-126">커넥터를 설정하려면 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-126">The connector setup requires that you:</span></span>

- [<span data-ttu-id="89058-127">EHR 커넥터 구성 포털 시작</span><span class="sxs-lookup"><span data-stu-id="89058-127">Launch the EHR connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="89058-128">구성 정보</span><span class="sxs-lookup"><span data-stu-id="89058-128">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="89058-129">구성 승인 또는 보기</span><span class="sxs-lookup"><span data-stu-id="89058-129">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="89058-130">구성 검토 및 완료</span><span class="sxs-lookup"><span data-stu-id="89058-130">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="89058-131">EHR 커넥터 구성 포털 시작</span><span class="sxs-lookup"><span data-stu-id="89058-131">Launch the EHR connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="89058-132">EHR 커넥터 구성 포털을 시작하여 Microsoft Teams 가상 방문을 시작하려면 의료 조직을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-132">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR connector configuration portal.</span></span> <span data-ttu-id="89058-133">단일 조직 또는 여러 조직을 구성하여 통합을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-133">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="89058-134">구성 포털에서 테스트 및 프로덕션 URL을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-134">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="89058-135">프로덕션 환경으로 이동하기 전에, Epic의 테스트 환경에서의 통합을 테스트하세요.</span><span class="sxs-lookup"><span data-stu-id="89058-135">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="89058-136">EHR 커넥터 구성 URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="89058-136">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="89058-137">조직의 Microsoft 365 관리자 및 Epic 고객 관리 분석가가 구성 포털의 정보 및 통합 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-137">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="89058-138">Epic 구성 단계에 대한 자세한 내용은 조직에 할당된 Epic 기술 전문가 리소스에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="89058-138">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="89058-139">구성 정보</span><span class="sxs-lookup"><span data-stu-id="89058-139">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="89058-140">이 단계는 **Microsoft 365 관리자** 가 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-140">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="89058-141">Microsoft 365 관리자는 커넥터 구성 포털을 시작하고 Microsoft 자격 증명으로 로그인하여 구성 프로세스를 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-141">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="89058-142">이 단계를 완료하려면 Microsoft 365 관리자가 사용자의 사이트에 있는 Epic 기술 전문가로부터 유효한 FHIR(전자 의료 기록 교환) 기본 URL과 구성을 승인할 Epic 고객 분석가의 사용자 이름을 제공 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-142">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="89058-143">Microsoft 365 관리자는 커넥터 구성 페이지를 시작하고 Microsoft 자격 증명으로 로그인하여 구성 프로세스를 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-143">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="89058-144">FHIR 기본 URL은 서버 FHIR API 끝점에 해당하는 정적 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="89058-144">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="89058-145">예제 URL은 `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`입니다.</span><span class="sxs-lookup"><span data-stu-id="89058-145">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="89058-146">구성 승인자 이름은 다음 단계에서 구성 승인을 담당할 Epic 고객 분석가의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="89058-146">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="89058-147">Epic 고객 분석가는 Epic에 대한 로그인 권한이 있는 조직 내 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="89058-147">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![구성 승인자의 이름이 EHR 커넥터의 목록에서 선택됩니다.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="89058-149">구성 승인 또는 보기</span><span class="sxs-lookup"><span data-stu-id="89058-149">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="89058-150">승인자로 추가된 의료 조직의 에픽 고객 분석가는 이제 이전 단계에서와 동일한 EHR 커넥터 URL을 사용하여 해당 자격 증명을 사용하여 로그인해야 Microsoft 365 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-150">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="89058-151">유효성 검사가 완료되면, 승인자는 Epic 자격 증명을 사용하여 로그인하여 Epic 조직의 유효성을 검사하라는 요청을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89058-151">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="89058-152">조직의 Microsoft 365 관리자 및 Epic 고객 관리 분석가가 같은 사람일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-152">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="89058-153">이 경우 사용자 이름을 승인자로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-153">In that case, add your own username as approver.</span></span> <span data-ttu-id="89058-154">액세스의 유효성을 검사하려면 여전히 Epic에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-154">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="89058-155">Epic 로그인은 FHIR 기본 URL의 유효성을 검사하는 데만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="89058-155">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="89058-156">Microsoft는 이 로그인을 통해 자격 증명을 저장하거나 EHR 데이터에 액세스하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-156">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![자격 증명 구성을 확인하고 승인합니다.](../../media/approve-view-configuration.png)

<span data-ttu-id="89058-158">로그인이 성공적으로 완료된 후에는 Epic 고객 분석가가 **반드시** 구성을 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-158">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="89058-159">구성이 올바르지 않은 경우 Microsoft 365 관리자는 Microsoft EHR 커넥터 포털에 다시 로그인하여 원래 구성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-159">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![EHR 커넥터가 구성되어 있는지 확인하고 구성을 변경하는 옵션을 선택합니다.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="89058-161">구성 검토 및 완료</span><span class="sxs-lookup"><span data-stu-id="89058-161">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="89058-162">Epic 관리자가 구성 정보를 승인하면 환자 및 공급자 출시에 대한 통합 레코드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="89058-162">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="89058-163">이러한 레코드는 Epic의 가상 방문 구성을 완료하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-163">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="89058-164">자세한 내용은 Microsoft Teams 원격의료 통합 가이드를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="89058-164">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="89058-165">필요한 경우 Microsoft 365 또는 Epic 고객 관리 분석가가 구성 포털에 로그인하여 통합 레코드를 보고 조직 구성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-165">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![통합 정보가 표시됩니다.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="89058-167">앞의 Microsoft 관리자가 구성한 모든 FHIR URL에 대해 Epic 고객 관리 분석가가 승인 프로세스를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-167">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![구성 정보가 승인됩니다.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="89058-169">Teams 가상 방문 시작</span><span class="sxs-lookup"><span data-stu-id="89058-169">Launch Teams virtual visits</span></span>

<span data-ttu-id="89058-170">EHR 커넥터 단계 및 에픽 구성을 완료한 후 조직에서 비디오 방문을 지원할 준비가 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="89058-170">After completing the EHR connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="89058-171">가상 방문 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="89058-171">Virtual visit prerequisites</span></span>

- <span data-ttu-id="89058-172">시스템이 모든 [소프트웨어 및 브라우저 필수 요구 사항](../../hardware-requirements-for-the-teams-app.md)을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-172">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

- <span data-ttu-id="89058-173">의료 조직은 Epic 조직과 Microsoft 365 조직 간의 설정을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-173">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="89058-174">공급자 환경</span><span class="sxs-lookup"><span data-stu-id="89058-174">Provider experience</span></span>

<span data-ttu-id="89058-175">조직의 의료 공급자는 Epic 공급자 응용 프로그램 (Hyperspace, Haiku, Canto)에서 Microsoft Teams와 함께 가상 방문에 참여할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-175">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="89058-176">**가상 방문 시작** 단추는 공급자 흐름에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-176">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="89058-177">공급자 환경의 주요 기능:</span><span class="sxs-lookup"><span data-stu-id="89058-177">Key features of the provider experience:</span></span>

- <span data-ttu-id="89058-178">공급자는 지원되는 브라우저 또는 Microsoft Teams 응용 프로그램을 사용하여 가상 방문에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-178">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="89058-179">공급자는 가상 방문에 처음 참여할 때 Microsoft 365 계정으로 1회 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-179">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="89058-p114">1회 로그인 후 공급자는 Microsoft Teams의 가상 약속으로 바로 이동합니다. (공급자는 Microsoft Teams에 로그인해야 합니다.)</span><span class="sxs-lookup"><span data-stu-id="89058-p114">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams. (Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="89058-182">공급자는 주어진 약속에 대한 참가자의 연결 및 연결 해제 실시간 업데이트를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-182">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="89058-183">공급자는 환자가 가상 방문에 연결된 시점을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-183">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![환자가 가상으로 방문하는 공급자 환경](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="89058-185">환자 환경</span><span class="sxs-lookup"><span data-stu-id="89058-185">Patient experience</span></span>

<span data-ttu-id="89058-186">커넥터는 MyChart 웹 및 모바일을 통해 가상 방문에 참여하는 환자를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-186">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="89058-187">약속 시점에 환자는 **가상 방문 시작** 단추를 사용하여 MyChart에서 가상 방문을 시작할 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-187">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="89058-188">환자 환경의 주요 기능:</span><span class="sxs-lookup"><span data-stu-id="89058-188">Key features of the patient experience:</span></span>

- <span data-ttu-id="89058-189">환자는 앱을 설치하지 않고도 데스크톱 및 모바일의 최신 웹 브라우저에서 가상 방문에 참여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-189">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="89058-190">환자는 클릭 한 번으로 가상 방문에 참여할 수 있으며 다른 계정이나 로그인이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-190">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="89058-191">환자는 Microsoft 계정을 만들거나 가상 방문을 시작하기 위해 로그인할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-191">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="89058-192">의료 공급자가 약속에 참여하고 가상 방문을 인정할 때까지 환자는 대기실에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-192">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="89058-193">가상 방문에 참가하기 전에 대기실에서 비디오와 마이크를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-193">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![가상 방문의 환자 환경](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="89058-195">Epic, MyChart, Haiku 및 Canto는 Epic Systems Corporation의 상표입니다.</span><span class="sxs-lookup"><span data-stu-id="89058-195">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="89058-196">개인 정보 및 데이터의 위치</span><span class="sxs-lookup"><span data-stu-id="89058-196">Privacy and location of data</span></span>

<span data-ttu-id="89058-197">Teams와 EHR 시스템의 통합은 통합 및 가상 방문 흐름 중에 사용 및 저장되는 데이터의 양을 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="89058-197">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="89058-198">이 솔루션은 전체 Teams 개인 정보 보호 및 데이터 관리 원칙과 Teams 개인 정보에 설명된 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="89058-198">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="89058-199">Microsoft Teams EHR 커넥터는 EHR 시스템에서 식별할 수 있는 개인 데이터나 환자 또는 의료 공급자의 건강 기록을 저장하거나 전송하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89058-199">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="89058-200">EHR 커넥터에 의해 저장되는 데이터는 팀 모임 설정 중에 사용되는 EHR 사용자의 고유 ID뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="89058-200">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="89058-201">EHR 사용자의 고유 ID는 [Microsoft 365 고객 데이터가 저장되는 위치](/microsoft-365/enterprise/o365-data-locations)에 설명된 세 가지 지역 중 하나에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="89058-201">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations).</span></span> <span data-ttu-id="89058-202">모임 참가자가 Teams에 입력한 모든 채팅, 녹음/녹화 및 기타 데이터는 기존 저장소 정책에 따라 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="89058-202">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="89058-203">Microsoft Teams의 데이터 위치에 대해 자세히 알아보려면 [Teams의 데이터 위치](../../location-of-data-in-teams.md)를 방문하세요.</span><span class="sxs-lookup"><span data-stu-id="89058-203">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](../../location-of-data-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="89058-204">관련 항목</span><span class="sxs-lookup"><span data-stu-id="89058-204">Related topics</span></span>

[<span data-ttu-id="89058-205">Teams 가상 방문</span><span class="sxs-lookup"><span data-stu-id="89058-205">Teams virtual visits</span></span>](ehr-admin-reports.md)