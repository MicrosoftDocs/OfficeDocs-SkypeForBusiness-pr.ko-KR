---
title: 클라우드 음성 서비스 배포 준비
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 온보더링 검사 목록을 사용하여 Teams용 Microsoft 365 또는 Office 365를 준비하고 Teams 핵심 기능, 네트워킹 및 클라우드 음성 워크로드를 구성합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3c805e8ff14ddb1c46f83db819c5dd8a2c305914
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610070"
---
# <a name="prepare-my-service"></a><span data-ttu-id="1b411-103">내 서비스 준비</span><span class="sxs-lookup"><span data-stu-id="1b411-103">Prepare my service</span></span>

<span data-ttu-id="1b411-104">이 문서에서는 조직에 대한 클라우드 음성 서비스를 준비하기 위한 요구 사항에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="1b411-105">제대로 준비하면 조직에 클라우드 음성 기능을 제공할 준비가 되었는지 확신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-105">By preparing properly, you can be sure you're ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="1b411-106">Microsoft Teams 음성 워크로드에 대한 온보드 검사 목록</span><span class="sxs-lookup"><span data-stu-id="1b411-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="1b411-107">다음 검사 목록은 Microsoft Teams에서 오디오 회의, 통화 계획("통화 계획")이 있는 전화 시스템 및 전화 시스템 직접 라우팅("직접 라우팅") 기능을 구현하는 단계를 단계로 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans ("Calling Plans"), and Phone System Direct Routing ("Direct Routing") capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="1b411-108">Teams용 Microsoft 365 또는 Office 365 준비</span><span class="sxs-lookup"><span data-stu-id="1b411-108">Prepare Microsoft 365 or Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="1b411-109">Teams 핵심 기능 구성</span><span class="sxs-lookup"><span data-stu-id="1b411-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="1b411-110">네트워크 준비</span><span class="sxs-lookup"><span data-stu-id="1b411-110">Prepare your network</span></span>](prepare-network.md)

*  [<span data-ttu-id="1b411-111">Teams에서 클라우드 음성 워크로드 구성</span><span class="sxs-lookup"><span data-stu-id="1b411-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="1b411-112">Teams에서 직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="1b411-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="1b411-113">이러한 검사 목록의 작업 및 활동은 Teams를 통해 클라우드 음성 기능을 배포하는 모든 배포에 적용되는 핵심 "할 일" 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-113">The tasks and activities in these checklists are the core "to-do" items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="1b411-114">검사 목록을 사용자 지정하여 자신의 Teams 여정에 특정한 활동 및 작업을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="1b411-115">이 지침은 통화 계획, 오디오 회의 및 직접 라우팅에만 중점을 습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="1b411-116">Teams를 새로운 사용자인 경우 [Microsoft Teams 개요를 검토하세요.](teams-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1b411-116">If you're new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="1b411-117">Teams 배포를 계획하기 위한 일반적인 지침은 [Microsoft Teams에서 채팅, 팀, 채널](deploy-chat-teams-channels-microsoft-teams-landing-page.md)및 앱 배포로 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="1b411-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="1b411-118">제공된 검사 목록을 사용하여 각 개별 활동 및 작업의 상태를 추적하고 중요한 단계를 건너뛴 것이 없는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven't skipped any critical steps.</span></span> <span data-ttu-id="1b411-119">각 활동에는 필요한 작업에 대한 자세한 설명과 해당 작업을 완료하는 데 사용할 수 있는 추가 정보에 대한 참조가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="1b411-120">검사 목록을 순서대로 따르는 것이 좋습니다. 정확한 순서는 배포 범위 및 환경의 구성 및 복잡성에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="1b411-121">"녹색" Teams 배포(이전의 비즈니스용 Skype Online 현재 상태 없음) 또는 비즈니스용 Skype Online에서 Teams로 마이그레이션을 지원하기 위해 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-121">They're organized to support either a "greenfield" Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="1b411-122">비즈니스용 Skype Online에서 마이그레이션하는 경우 이러한 활동 중 일부를 이미 완료한 경우 지금 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-122">If you're migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="1b411-123">사이트당 사용자를 온보드할 때 이러한 검사 목록에 대한 보조 가이드로 음성용 [사이트](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 사용 플레이북(플레이북)을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-123">When you're onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="1b411-124">대부분의 구성 설정은 Teams와 비즈니스용 Skype Online 간에 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="1b411-125">Microsoft 365 관리 센터 및 Microsoft Teams 관리 센터를 사용하여 이러한 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="1b411-126">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="1b411-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="1b411-127">온보더링 검사 목록의 완료를 책임져야 하는 사람</span><span class="sxs-lookup"><span data-stu-id="1b411-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="1b411-128">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1b411-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="1b411-129">온보더링 검사 목록을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="1b411-130">조직의 배포 계획에 따라 온보드 검사 목록 항목을 단계별으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-130">Work through the onboarding checklist items step-by-step in accordance with your organization's deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="1b411-131">온보드 계속</span><span class="sxs-lookup"><span data-stu-id="1b411-131">Continue onboarding</span></span>

<span data-ttu-id="1b411-132">이러한 검사 목록을 완료하면 Teams 배포에 음성 기능이 성공적으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-132">After you complete these checklists, you'll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="1b411-133">다음 단계로, 각 [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 사이트에 사용자를 온보드하고 중요한 사이트별 활동을 계획하고 실행하는 데 도움이 되도록 사이트 사용 플레이북(플레이북)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1b411-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="1b411-134">사이트 롤아웃 계획에 따라 준비된 사이트</span><span class="sxs-lookup"><span data-stu-id="1b411-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="1b411-135">서비스 관리 프로세스 설정</span><span class="sxs-lookup"><span data-stu-id="1b411-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="1b411-136">테스트 및 수정 실행</span><span class="sxs-lookup"><span data-stu-id="1b411-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="1b411-137">Teams에서 클라우드 음성 워크로드 테스트</span><span class="sxs-lookup"><span data-stu-id="1b411-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="1b411-138">Teams 클라우드 음성 비즈니스 성공 및 기술 구현 계획을 구상 단계의 일부로 정의하고 문서화하고 관리 센터에서 원하는 구성을 실행한 후 다음 단계는 기능, 기능 및 사용성을 통해 조직의 기대와 요구 사항을 충족하는지 유효성을 검사하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-138">After you've defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization's expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="1b411-139">프로덕션 환경에서 파일럿 또는 최종 배포를 배포하기 전에 이 유효성 검사 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="1b411-140">계획 단계에서 정의한 비즈니스 성공 계획을 활용하여 테스트 단계에서 평가할 활동, 기대치, 기능/기능 테스트 사례 및 전체 범위를 결정하는 기초 역할을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="1b411-141">테스트 방법 정의</span><span class="sxs-lookup"><span data-stu-id="1b411-141">Define your testing approach</span></span>

<span data-ttu-id="1b411-142">가장 간단한 형식의 테스트 접근 방식은 오디오 회의, 통화 계획 또는 직접 라우팅 서비스의 기능 기능을 검토하고 범위 내 사용자에 대한 기능 요구 사항이 충족하는지 확인하는 테스트 계획을 개발하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="1b411-143">다음은 오디오 회의 구현의 온보드 단계에 대한 테스트 계획 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="1b411-144">테스트할 오디오 회의 기능</span><span class="sxs-lookup"><span data-stu-id="1b411-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="1b411-145">결과 요약</span><span class="sxs-lookup"><span data-stu-id="1b411-145">Results summary</span></span> | <span data-ttu-id="1b411-146">추가 참고 사항</span><span class="sxs-lookup"><span data-stu-id="1b411-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="1b411-147">오디오 회의 전화 접속 정보가 포함된 추가 Teams 모임 예약</span><span class="sxs-lookup"><span data-stu-id="1b411-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="1b411-148">통과/실패</span><span class="sxs-lookup"><span data-stu-id="1b411-148">Pass/Fail</span></span>   | <span data-ttu-id="1b411-149">TBD</span><span class="sxs-lookup"><span data-stu-id="1b411-149">TBD</span></span> |
| <span data-ttu-id="1b411-150">제공된 전화 접속 정보를 사용하여 PSTN에서 모임에 전화를 걸면 전화기를 사용하여 오디오를 모임에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="1b411-151">통과/실패</span><span class="sxs-lookup"><span data-stu-id="1b411-151">Pass/Fail</span></span> | <span data-ttu-id="1b411-152">TBD</span><span class="sxs-lookup"><span data-stu-id="1b411-152">TBD</span></span> |
| <span data-ttu-id="1b411-153">PSTN을 통해 전화를 걸고 다른 사용자와 기존 모임에 참가</span><span class="sxs-lookup"><span data-stu-id="1b411-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="1b411-154">통과/실패</span><span class="sxs-lookup"><span data-stu-id="1b411-154">Pass/Fail</span></span> | <span data-ttu-id="1b411-155">TBD</span><span class="sxs-lookup"><span data-stu-id="1b411-155">TBD</span></span> |



| <span data-ttu-id="1b411-156">테스트할 계획 또는 직접 라우팅 기능 호출</span><span class="sxs-lookup"><span data-stu-id="1b411-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="1b411-157">결과 요약</span><span class="sxs-lookup"><span data-stu-id="1b411-157">Results summary</span></span> | <span data-ttu-id="1b411-158">추가 참고 사항</span><span class="sxs-lookup"><span data-stu-id="1b411-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="1b411-159">PSTN 번호로 전화를 걸고 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="1b411-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="1b411-160">통과/실패</span><span class="sxs-lookup"><span data-stu-id="1b411-160">Pass/Fail</span></span>       | <span data-ttu-id="1b411-161">TBD</span><span class="sxs-lookup"><span data-stu-id="1b411-161">TBD</span></span> |
| <span data-ttu-id="1b411-162">외부 전화(휴대폰, 유선전화)에서 PSTN 번호로 전화를 걸면 PSTN 통화 수신</span><span class="sxs-lookup"><span data-stu-id="1b411-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="1b411-163">통과/실패</span><span class="sxs-lookup"><span data-stu-id="1b411-163">Pass/Fail</span></span> | <span data-ttu-id="1b411-164">TBD</span><span class="sxs-lookup"><span data-stu-id="1b411-164">TBD</span></span>|
| <span data-ttu-id="1b411-165">한 Teams 사용자에서 다른 Teams로 PSTN 통화 전송</span><span class="sxs-lookup"><span data-stu-id="1b411-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="1b411-166">통과/실패</span><span class="sxs-lookup"><span data-stu-id="1b411-166">Pass/Fail</span></span> | <span data-ttu-id="1b411-167">TBD</span><span class="sxs-lookup"><span data-stu-id="1b411-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="1b411-168">테스트 사례 생성을 시작점으로 지원하기 위해 Teams 모임 및 통화에서 사용할 수 있는 사용자 지침 [목록을 참조하세요.](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)</span><span class="sxs-lookup"><span data-stu-id="1b411-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="1b411-169">Teams에 대한 클라우드 음성 워크로드 설정</span><span class="sxs-lookup"><span data-stu-id="1b411-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="1b411-170">테스트 방법을 정의한 후 다음 단계는 Teams 클라우드 음성 기능에 대한 범위에서 서비스 환경 및 사용자를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-170">Now that you've defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="1b411-171">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1b411-171">For additional information, see:</span></span>

- [<span data-ttu-id="1b411-172">오디오 회의에 대한 기술 계획</span><span class="sxs-lookup"><span data-stu-id="1b411-172">Technical Planning for Audio Conferencing</span></span>](cloud-voice-deployment.md)

- [<span data-ttu-id="1b411-173">Microsoft Teams용 오디오 회의 설정하기</span><span class="sxs-lookup"><span data-stu-id="1b411-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="1b411-174">통화 요금제가 있는 전화 시스템에 대한 기술 계획</span><span class="sxs-lookup"><span data-stu-id="1b411-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="1b411-175">비즈니스용 Skype 및 Microsoft Teams에 대한 통화 요금제 설정</span><span class="sxs-lookup"><span data-stu-id="1b411-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="1b411-176">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="1b411-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="1b411-177">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="1b411-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="1b411-178">테스트 계획 실행</span><span class="sxs-lookup"><span data-stu-id="1b411-178">Execute the test plan</span></span>

[//]: # (편집해도 괜찮나요? "사용자"가 약간 모호해 보임.)
<span data-ttu-id="1b411-180">사용자 환경 및 서비스가 구성된 후 테스트의 마지막 단계에서는 기능 및 기능 유효성 검사에 중점을 두는 테스트 계획 실행을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="1b411-181">**범위 내 사용자 및 사이트에 대한 오디오 회의 테스트의 전제 사항 및 가정:**</span><span class="sxs-lookup"><span data-stu-id="1b411-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="1b411-182">오디오 회의 서비스에 대한 비즈니스 사용 사례 정의가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="1b411-183">오디오 회의에 필요한 라이선스를 사용할 수 있으며 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="1b411-184">조직 사이트 및 사용자 그룹 목록이 식별되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="1b411-185">언어 기본 설정이 있는 번호의 전용 및 공유 오디오 회의 다이얼 목록이 식별되고 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="1b411-186">[조직에 대해](what-are-communications-credits.md) 통신 크레딧(필요한 경우)이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="1b411-187">오디오 회의 회의 브리지 설정이 식별되고 구성되었습니다(PIN 길이, 진입/종료 알림, 사용 설정 알림 기본 설정).</span><span class="sxs-lookup"><span data-stu-id="1b411-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="1b411-188">오디오 회의 전화 접속 시나리오를 지원하는 테넌트 회의 정책 및 다이얼 플랜 설정이 식별, 구성 및 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="1b411-189">오디오 회의 규정 준수 요구 사항이 식별되고 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="1b411-190">**범위 내 사용자 및 사이트에 대한 계획 테스트 전제 사항 및 가정 호출:**</span><span class="sxs-lookup"><span data-stu-id="1b411-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="1b411-191">통화 계획 서비스에 대한 비즈니스 사용 사례 정의가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="1b411-192">통화 요금제에 필요한 라이선스를 사용할 수 있으며 할당되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="1b411-193">조직 사이트 및 사용자 그룹 목록이 식별되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="1b411-194">사용자에게 할당할 전화 번호는 Microsoft로 획득되거나 이식되고 테넌트 포털에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="1b411-195">[조직에 대해](what-are-communications-credits.md) 통신 크레딧(필요한 경우)이 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="1b411-196">통화 계획 시나리오를 지원하는 테넌트 사용자 정책 및 전화 요금제 설정이 식별, 구성 및 적용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="1b411-197">호출 계획 규정 준수 요구 사항이 식별되고 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="1b411-198">**범위 내 사용자 및 사이트에 대한 직접 라우팅 테스트 전제 사항 및 가정:**</span><span class="sxs-lookup"><span data-stu-id="1b411-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="1b411-199">직접 라우팅 서비스에 대한 비즈니스 사용 사례 정의가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="1b411-200">직접 라우팅에 필요한 라이선스를 사용할 수 있으며 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="1b411-201">조직 사이트 및 사용자 그룹 목록이 식별되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="1b411-202">인증된 [SBC(세션](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) 테두리 컨트롤러)가 휴대폰 시스템과 배포, 구성 및 쌍으로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="1b411-203">엔터프라이즈 음성이 활성화되고 전화 번호가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="1b411-204">음성 라우팅 정책이 식별, 구성 및 할당되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="1b411-205">Microsoft Teams는 범위 내 사용자에 대한 기본 통화 클라이언트로 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="1b411-206">직접 라우팅 준수 요구 사항이 식별되고 구성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="1b411-207">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="1b411-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="1b411-208">배포할 오디오 회의 기능(서비스 결정)을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="1b411-209">오디오 회의에 대한 사용자 기능 요구 사항을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="1b411-210">오디오 회의에 대한 서비스 구성 요구 사항을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="1b411-211">직접 라우팅 또는 통화 요금제가 배포 및 구성될지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="1b411-212">배포할 전화 시스템 기능(서비스 결정)을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="1b411-213">통화 계획 또는 직접 라우팅에 대한 사용자 기능 요구 사항을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="1b411-214">요금제 또는 직접 라우팅에 대한 서비스 구성 요구 사항을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="1b411-215">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1b411-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="1b411-216">테스트 계획 접근 방식을 개발하고 문서화합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="1b411-217">오디오 회의 기능에 대한 범위에서 서비스 환경 및 사용자를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="1b411-218">통화 계획 또는 직접 라우팅 기능에 대한 범위에서 서비스 환경 및 사용자를 준비합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="1b411-219">사용하도록 설정하려는 오디오 회의 기능에 대한 테스트 유효성 검사를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="1b411-220">사용하도록 설정하려는 통화 계획 또는 직접 라우팅 기능에 대한 테스트 유효성 검사를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="1b411-221">테스트 오류가 발생하면 구성이 올바른지 확인하고, 커뮤니티 문서를 검토하고, 필요한 경우 지원 사례를 제기합니다.</span><span class="sxs-lookup"><span data-stu-id="1b411-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="1b411-222">Teams에서 오디오 회의 테스트를 수행하는 방법에 대한 자세한 지침은 오디오 회의에 대한 자세한 테스트 가이드를 [참조하세요.](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="1b411-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="1b411-223">Teams에서 통화 계획 테스트를 수행하는 방법에 대한 자세한 지침은 전화 시스템에 대한 자세한 테스트 [가이드를 참조하세요.](onboarding-test-plan-for-enterprises-Phone-System.md)</span><span class="sxs-lookup"><span data-stu-id="1b411-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
