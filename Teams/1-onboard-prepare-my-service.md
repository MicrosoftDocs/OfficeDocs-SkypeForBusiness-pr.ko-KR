---
title: Microsoft 팀 클라우드 음성 서비스 배포 준비
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 온 보 딩 검사 목록을 사용 하 여 팀을 위한 Office 365을 준비 하 고 팀 핵심 기능, 네트워킹, 클라우드 음성 작업을 구성 합니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 653b5cf46e0b079af47c282b4110b181e76be915
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37517066"
---
# <a name="prepare-my-service"></a><span data-ttu-id="a9684-103">내 서비스 준비</span><span class="sxs-lookup"><span data-stu-id="a9684-103">Prepare my service</span></span>

<span data-ttu-id="a9684-104">이 문서에서는 조직에 대 한 클라우드 음성 서비스를 준비 하기 위한 요구 사항을 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="a9684-105">올바르게 준비 하면 조직에 클라우드 음성 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="a9684-106">Microsoft 팀의 온 보 딩 검사 목록 음성 작업 부하</span><span class="sxs-lookup"><span data-stu-id="a9684-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="a9684-107">다음 검사 목록은 Microsoft 팀에서 오디오 회의, 통화 요금제 ("통화 요금제"), 전화 시스템 직접 라우팅 ("다이렉트 라우팅") 기능을 구현 하는 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="a9684-108">팀 용 Office 365 준비</span><span class="sxs-lookup"><span data-stu-id="a9684-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="a9684-109">팀 핵심 기능 구성</span><span class="sxs-lookup"><span data-stu-id="a9684-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="a9684-110">네트워킹 구성</span><span class="sxs-lookup"><span data-stu-id="a9684-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="a9684-111">팀에서 클라우드 음성 작업 부하 구성</span><span class="sxs-lookup"><span data-stu-id="a9684-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="a9684-112">팀에서 직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="a9684-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="a9684-113">이러한 검사 목록의 작업 및 활동은 팀과 클라우드 음성 기능의 모든 배포에 적용 되는 핵심 "할 일" 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="a9684-114">자신의 팀에서 여행 하는 작업과 관련 된 활동과 작업을 포함 하도록 검사 목록을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="a9684-115">이 가이드는 통화 요금제, 오디오 회의 및 직접 라우팅에만 초점을 둔 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="a9684-116">팀을 처음 접하는 경우 [Microsoft 팀 개요](teams-overview.md)를 검토 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9684-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="a9684-117">팀 배포 계획에 대 한 일반적인 지침은 [Microsoft 팀에서 채팅, 팀, 채널 및 앱 배포](deploy-chat-teams-channels-microsoft-teams-landing-page.md)를 시작 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9684-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="a9684-118">제공 된 검사 목록을 사용 하 여 개별 활동 및 작업의 상태를 추적 하 고 중요 한 단계를 건너뛰지 않았는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="a9684-119">각 활동에는 필요한 작업에 대 한 자세한 설명과 해당 활동을 완료 하는 데 사용할 수 있는 추가 정보에 대 한 참조가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="a9684-120">검사 목록을 순서 대로 수행 하는 것이 좋지만 정확한 순서는 배포의 범위와 환경의 구성 및 복잡도에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="a9684-121">이는 "greenfield" 팀 배포 (비즈니스용 Skype Online 현재 상태를 포함 하지 않음) 또는 비즈니스용 Skype Online에서 팀으로 마이그레이션을 지원 하도록 구성 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="a9684-122">비즈니스용 Skype Online에서 마이그레이션하는 경우 이미 이러한 활동 중 일부를 완료 했 고 지금 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="a9684-123">사이트 별로 온 보 딩 사용자는 이러한 검사 목록의 보조 가이드로 [음성 (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 을 사용 하 여 사이트를 Playbook 하는 방법을 사용할 것을 적극 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="a9684-124">대부분의 구성 설정은 팀과 비즈니스용 Skype Online 간에 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="a9684-125">Microsoft 365 관리 센터 및 Microsoft 팀 관리 센터를 사용 하 여 해당 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="a9684-126">결정 사항</span><span class="sxs-lookup"><span data-stu-id="a9684-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="a9684-127">온 보 딩 검사 완료에 대 한 책임은 누가 overseeing?</span><span class="sxs-lookup"><span data-stu-id="a9684-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="a9684-128">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a9684-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="a9684-129">온 보 딩 검사 목록을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="a9684-130">조직의 배포 계획에 따라 온 보 딩 검사 목록 항목을 단계별로 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="a9684-131">온 보 딩 계속</span><span class="sxs-lookup"><span data-stu-id="a9684-131">Continue onboarding</span></span>

<span data-ttu-id="a9684-132">이러한 검사 목록을 완료 하면 팀 배포에 음성 기능을 추가 하는 데 성공 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="a9684-133">다음 단계로, [Playbook (Playbook) 사이트](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 사용을 위해 각 사이트의 사용자를 등록 하 고 중요 한 사이트별 작업을 계획 하 고 실행 하도록 도와 보세요.</span><span class="sxs-lookup"><span data-stu-id="a9684-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="a9684-134">사이트 출시 계획으로 준비 된 사이트</span><span class="sxs-lookup"><span data-stu-id="a9684-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="a9684-135">서비스 관리 프로세스 설정</span><span class="sxs-lookup"><span data-stu-id="a9684-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="a9684-136">테스트 및 재구성 실행</span><span class="sxs-lookup"><span data-stu-id="a9684-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="a9684-137">팀에서 클라우드 음성 작업 부하 테스트</span><span class="sxs-lookup"><span data-stu-id="a9684-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="a9684-138">구상 단계의 일부로 팀 구름 음성 비즈니스 성공 및 기술 구현 계획을 정의 하 고 문서화 하 고 관리 센터에서 원하는 구성을 수행 하는 경우 다음 단계는 조직의 예측 및 요구 사항은 기능, 기능 및 유용성을 통해 충족 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="a9684-139">프로덕션 환경에서 파일럿 또는 최종 배포를 배포 하기 전에이 유효성 검사 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="a9684-140">구상 단계에서 정의한 비즈니스 성공 계획을 활용 하 여 테스트 단계 중 평가할 활동, 기대, 기능/기능 테스트 사례 및 전체 범위를 결정 하는 기준으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="a9684-141">테스트 접근 방법 정의</span><span class="sxs-lookup"><span data-stu-id="a9684-141">Define your testing approach</span></span>

<span data-ttu-id="a9684-142">가장 간단한 형태의 테스트 접근 방법은 오디오 회의, 통화 계획 또는 직접 라우팅 서비스의 기능을 검토 하 고 사용자가 범위 내에서 기능 요구 사항이 충족 되는지 확인 하기 위해 테스트 계획을 개발 하는 것을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="a9684-143">다음은 오디오 회의 구현의 온보드 단계에 대 한 테스트 계획 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="a9684-144">테스트를 위한 오디오 회의 기능</span><span class="sxs-lookup"><span data-stu-id="a9684-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="a9684-145">결과 요약</span><span class="sxs-lookup"><span data-stu-id="a9684-145">Results summary</span></span> | <span data-ttu-id="a9684-146">추가 참고 사항</span><span class="sxs-lookup"><span data-stu-id="a9684-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="a9684-147">오디오 회의 전화 접속 정보가 포함 된 임시 팀 모임 예약</span><span class="sxs-lookup"><span data-stu-id="a9684-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="a9684-148">합격/불합격</span><span class="sxs-lookup"><span data-stu-id="a9684-148">Pass/Fail</span></span>   | <span data-ttu-id="a9684-149">TBD</span><span class="sxs-lookup"><span data-stu-id="a9684-149">TBD</span></span> |
| <span data-ttu-id="a9684-150">제공 되는 전화 접속 정보를 사용 하 여 PSTN에서 모임에 전화를 걸어 모임 오디오를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="a9684-151">합격/불합격</span><span class="sxs-lookup"><span data-stu-id="a9684-151">Pass/Fail</span></span> | <span data-ttu-id="a9684-152">TBD</span><span class="sxs-lookup"><span data-stu-id="a9684-152">TBD</span></span> |
| <span data-ttu-id="a9684-153">PSTN을 통해 전화를 걸어 기존 모임에 다른 사용자에 게 참가</span><span class="sxs-lookup"><span data-stu-id="a9684-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="a9684-154">합격/불합격</span><span class="sxs-lookup"><span data-stu-id="a9684-154">Pass/Fail</span></span> | <span data-ttu-id="a9684-155">TBD</span><span class="sxs-lookup"><span data-stu-id="a9684-155">TBD</span></span> |



| <span data-ttu-id="a9684-156">테스트에 대 한 통화 계획 또는 다이렉트 라우팅 기능</span><span class="sxs-lookup"><span data-stu-id="a9684-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="a9684-157">결과 요약</span><span class="sxs-lookup"><span data-stu-id="a9684-157">Results summary</span></span> | <span data-ttu-id="a9684-158">추가 참고 사항</span><span class="sxs-lookup"><span data-stu-id="a9684-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="a9684-159">PSTN 번호를 사용 하 여 PSTN 전화 걸기</span><span class="sxs-lookup"><span data-stu-id="a9684-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="a9684-160">합격/불합격</span><span class="sxs-lookup"><span data-stu-id="a9684-160">Pass/Fail</span></span>       | <span data-ttu-id="a9684-161">TBD</span><span class="sxs-lookup"><span data-stu-id="a9684-161">TBD</span></span> |
| <span data-ttu-id="a9684-162">외부 회선 (휴대 전화, 유선전화)에서 PSTN 번호를 눌러 PSTN 통화 받기</span><span class="sxs-lookup"><span data-stu-id="a9684-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="a9684-163">합격/불합격</span><span class="sxs-lookup"><span data-stu-id="a9684-163">Pass/Fail</span></span> | <span data-ttu-id="a9684-164">TBD</span><span class="sxs-lookup"><span data-stu-id="a9684-164">TBD</span></span>|
| <span data-ttu-id="a9684-165">한 팀 사용자의 PSTN 통화를 다른 사람에 게 전송</span><span class="sxs-lookup"><span data-stu-id="a9684-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="a9684-166">합격/불합격</span><span class="sxs-lookup"><span data-stu-id="a9684-166">Pass/Fail</span></span> | <span data-ttu-id="a9684-167">TBD</span><span class="sxs-lookup"><span data-stu-id="a9684-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="a9684-168">테스트 사례를 시작 지점으로 만들기 위해 [팀 모임 및 통화](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)에서 사용할 수 있는 사용자 지침 목록을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9684-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="a9684-169">팀에 대 한 클라우드 음성 작업 부하 설정</span><span class="sxs-lookup"><span data-stu-id="a9684-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="a9684-170">테스트 접근 방식을 정의 했으므로 다음 단계는 팀 클라우드 음성 기능에 대 한 범위에서 서비스 환경 및 사용자를 구성 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="a9684-171">추가 정보는 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9684-171">For additional information, see:</span></span>

- [<span data-ttu-id="a9684-172">오디오 회의를 위한 기술 계획</span><span class="sxs-lookup"><span data-stu-id="a9684-172">Technical Planning for Audio Conferencing</span></span>](cloud-voice-deployment.md)

- [<span data-ttu-id="a9684-173">Microsoft 팀을 위한 오디오 회의 설정</span><span class="sxs-lookup"><span data-stu-id="a9684-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="a9684-174">통화 요금제를 사용 하 여 전화 시스템에 대 한 기술 계획</span><span class="sxs-lookup"><span data-stu-id="a9684-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="a9684-175">비즈니스용 Skype 및 Microsoft 팀에 대 한 통화 계획 설정</span><span class="sxs-lookup"><span data-stu-id="a9684-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="a9684-176">직접 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="a9684-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="a9684-177">직접 라우팅 구성</span><span class="sxs-lookup"><span data-stu-id="a9684-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="a9684-178">테스트 계획 실행</span><span class="sxs-lookup"><span data-stu-id="a9684-178">Execute the test plan</span></span>

[//]: # (편집 하 시겠습니까? "사용자"가 조금 불확실 한 것 같습니다.)
<span data-ttu-id="a9684-180">사용자 환경과 서비스가 구성 되 면 테스트의 마지막 단계에서는 기능 및 기능 유효성 검사에 대 한 포커스가 있는 테스트 계획 실행을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="a9684-181">**범위에서 사용자 및 사이트에 대 한 필수 구성 요소 및 가정을 테스트 하는 오디오 회의:**</span><span class="sxs-lookup"><span data-stu-id="a9684-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="a9684-182">오디오 회의 서비스에 대 한 비즈니스 사용 사례 정의가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="a9684-183">오디오 회의에 필요한 라이선스를 사용할 수 있으며 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="a9684-184">조직 사이트 및 사용자 그룹 목록이 식별 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="a9684-185">언어 기본 설정이 있는 전용 및 공유 오디오 회의 전화 접속 번호 목록이 식별 되 고 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="a9684-186">조직에 대해 [통신 크레딧을](what-are-communications-credits.md) 설정 했습니다 (필요한 경우).</span><span class="sxs-lookup"><span data-stu-id="a9684-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="a9684-187">오디오 회의 회의 브리지 설정이 식별 되 고 구성 되었습니다 (PIN 길이, 입력/종료 알림, 사용 알림 기본 설정).</span><span class="sxs-lookup"><span data-stu-id="a9684-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="a9684-188">오디오 회의 전화 접속 시나리오를 지 원하는 테 넌 트 회의 정책 및 다이얼 플랜 설정은 확인, 구성 및 적용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="a9684-189">오디오 회의 준수 요구 사항이 식별 되 고 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="a9684-190">**범위에서 사용자 및 사이트에 대 한 요구 사항 및 전제 조건을 테스트 하는 통화 계획:**</span><span class="sxs-lookup"><span data-stu-id="a9684-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="a9684-191">통화 계획 서비스에 대 한 비즈니스 사용 사례 정의가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="a9684-192">통화 요금제에 필요한 라이선스를 사용할 수 있으며 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="a9684-193">조직 사이트 및 사용자 그룹 목록이 식별 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="a9684-194">사용자에 게 할당 될 전화 번호를 Microsoft로 구입 또는 이식 했으며, 테 넌 트 포털에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="a9684-195">조직에 대해 [통신 크레딧을](what-are-communications-credits.md) 설정 했습니다 (필요한 경우).</span><span class="sxs-lookup"><span data-stu-id="a9684-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="a9684-196">호출 계획 시나리오를 지 원하는 테 넌 트 사용자 정책 및 다이얼 플랜 설정은 식별, 구성 및 적용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="a9684-197">통화 계획 준수 요구 사항이 식별 되 고 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="a9684-198">**범위에서 사용자 및 사이트에 대 한 직접 라우팅 테스트 선행 조건과 가정:**</span><span class="sxs-lookup"><span data-stu-id="a9684-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="a9684-199">다이렉트 라우팅 서비스에 대 한 비즈니스 사용 사례 정의가 완료 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="a9684-200">직접 라우팅에 필요한 라이선스를 사용할 수 있으며 할당 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="a9684-201">조직 사이트 및 사용자 그룹 목록이 식별 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="a9684-202">일반 [SBC (인증 된 세션 경계 컨트롤러)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) 는 전화 시스템을 사용 하 여 배포, 구성 및 페어링 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="a9684-203">Enterprise voice가 사용 하도록 설정 되 고 전화 번호가 지정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="a9684-204">음성 라우팅 정책을 확인 하 고 구성 하 고 할당 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="a9684-205">Microsoft 팀은 범위 내의 사용자에 대 한 기본 호출 클라이언트로 설정 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="a9684-206">직접적인 라우팅 준수 요구 사항이 식별 되 고 구성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="a9684-207">결정 사항</span><span class="sxs-lookup"><span data-stu-id="a9684-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="a9684-208">배포할 오디오 회의 기능 기능을 결정 합니다 (서비스 의사 결정).</span><span class="sxs-lookup"><span data-stu-id="a9684-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="a9684-209">오디오 회의에 대 한 사용자 기능 요구 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="a9684-210">오디오 회의에 대 한 서비스 구성 요구 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="a9684-211">직접 라우팅 또는 호출 계획이 배포 되 고 구성 되는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="a9684-212">어떤 전화 시스템 기능 기능을 배포할지 결정 합니다 (서비스 의사 결정).</span><span class="sxs-lookup"><span data-stu-id="a9684-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="a9684-213">통화 요금제 또는 직접 라우팅에 대 한 사용자 기능 요구 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="a9684-214">통화 요금제 또는 직접 라우팅에 대 한 서비스 구성 요구 사항을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="a9684-215">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a9684-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="a9684-216">테스트 계획 방법을 개발 하 고 문서화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="a9684-217">오디오 회의 기능을 위한 범위 내에서 서비스 환경과 사용자를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="a9684-218">서비스 환경 및 사용자를 통화 계획 또는 다이렉트 라우팅 기능에 대 한 범위 내에서 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="a9684-219">사용 하도록 설정할 오디오 회의 기능에 대 한 테스트 유효성 검사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="a9684-220">사용 하도록 설정 하려는 호출 계획 또는 직접 라우팅 기능에 대 한 테스트 유효성 검사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="a9684-221">테스트 실패에 대 한 구성이 올바른지 확인 하 고 커뮤니티 문서를 검토 하 고 필요한 경우 지원 사례를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="a9684-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="a9684-222">팀에서 오디오 회의 테스트를 수행 하는 방법에 대 한 자세한 지침은 [오디오 회의에 대 한 자세한 테스트 가이드](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9684-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="a9684-223">팀에서 통화 계획에 대 한 테스트를 수행 하는 방법에 대 한 자세한 내용은 [전화 시스템에 대 한 자세한 테스트 가이드](onboarding-test-plan-for-enterprises-Phone-System.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9684-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
