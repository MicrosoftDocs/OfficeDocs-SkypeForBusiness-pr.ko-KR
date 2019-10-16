---
title: Microsoft 팀 클라우드 음성 서비스 배포
author: rmw2890
ms.author: Rowille
manager: serdars
audience: admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 사이트 사용 Playbook을 다운로드 하 여 팀의 출시를 계획 하 고 사용자 채택을 향상 하 고 최적화 하며, 품질 및 만족도를 높입니다.
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 760beb6b5f786367c76ce9ac2b66d808fa10c6de
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516764"
---
# <a name="deploy-my-service"></a><span data-ttu-id="9b0f3-103">내 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="9b0f3-103">Deploy my service</span></span>

<span data-ttu-id="9b0f3-104">이 문서에서는 클라우드 음성 서비스를 올바르게 배포 하기 위한 요구 사항에 대해 간략하게 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="9b0f3-105">클라우드 음성 서비스 배포에 대 한 규범적인 지침을 따라 모든 요구 사항을 성공적으로 설명 하 고 반복 가능한 결과를 제공할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="9b0f3-106">Microsoft 팀의 사이트 playbook 음성 작업 부하</span><span class="sxs-lookup"><span data-stu-id="9b0f3-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="9b0f3-107">이 playbook를 사용 하 여 조직에서 사이트별로 Microsoft 팀 음성 기능 롤아웃을 성공적으로 계획 하 고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="9b0f3-108">이 playbook는 필요한 모든 활동, 권장 시간 표시 막대, 각 활동에 대 한 해당 지침에 대 한 링크를 포함 하 여 특정 사이트에 대 한 팀 음성 배포를 성공적으로 수행 하는 데 도움이 되는 중요 한 요소에 초점을 맞추어 종단간 지침을 다룹니다. 사용자에 게</span><span class="sxs-lookup"><span data-stu-id="9b0f3-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="9b0f3-109">이 playbook의 활동을 완료 하 여 조직에서 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="9b0f3-110">팀 출시를 효과적으로 계획 하 고 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="9b0f3-111">사용자 채택을 가속화 하 고 최적화 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="9b0f3-112">지원 요구를 줄이고 사용자 만족도를 높입니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="9b0f3-113">이 문서 및 관련 playbook는 서비스 사용 또는 특정 사이트에 발신음을 제공 하는 데 필요한 모든 기술 구성 단계를 설명 하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="9b0f3-114">대신 사용자가 쉽게 사용할 수 있도록 하는 작업 및 작업에 중점을 두 며, 지원 요구 사항을 최소화 하면서, 채택 률이 높은 빠른 전환 및 원활한 전환을 통해 팀 음성 작업량을 소모 하기 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="9b0f3-115">팀 음성 기능을 최적으로 구성 하는 방법에 대 한 기술 지침은 팀 [음성 작업을 구성](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)하기 위한 온 보 딩 검사 목록, [팀에서 직접 라우팅 구성](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [팀 core](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)기술, 네트워킹을 참조 하세요. [ ](onboarding-checklist-configure-networking.md) [Office 365를 사용 하도록 설정](onboarding-checklist-enable-office-365.md)하 고 팀에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](onboarding-checklist-configure-networking.md), and [enabling Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="9b0f3-116">Playbook 포커스 영역</span><span class="sxs-lookup"><span data-stu-id="9b0f3-116">Playbook focus areas</span></span>

<span data-ttu-id="9b0f3-117">Playbook의 초점은 팀 음성 배포의 사용자의 인식에 영향을 주는 요소를 처리 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="9b0f3-118">활동 및 작업은 다음 포커스 영역으로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="9b0f3-119">서비스 준비 상태 확인</span><span class="sxs-lookup"><span data-stu-id="9b0f3-119">Validation of service readiness</span></span>
    - <span data-ttu-id="9b0f3-120">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="9b0f3-120">Audio Conferencing</span></span>
    - <span data-ttu-id="9b0f3-121">통화 요금제</span><span class="sxs-lookup"><span data-stu-id="9b0f3-121">Calling Plans</span></span>
    - <span data-ttu-id="9b0f3-122">직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="9b0f3-122">Direct Routing</span></span>

-   <span data-ttu-id="9b0f3-123">사용자 사용</span><span class="sxs-lookup"><span data-stu-id="9b0f3-123">User enablement</span></span>

-   <span data-ttu-id="9b0f3-124">끝점</span><span class="sxs-lookup"><span data-stu-id="9b0f3-124">Endpoints</span></span>

-   <span data-ttu-id="9b0f3-125">사용 및 품질</span><span class="sxs-lookup"><span data-stu-id="9b0f3-125">Usage and quality</span></span>

-   <span data-ttu-id="9b0f3-126">도입할</span><span class="sxs-lookup"><span data-stu-id="9b0f3-126">Adoption</span></span>

<span data-ttu-id="9b0f3-127">[Playbook (Playbook) 사이트를 사용할 수 있도록](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) Microsoft Excel 통합 문서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="9b0f3-128">이러한 다섯 가지 포커스 영역은 통합 문서의 개별 시트 이며 각 배포 작업 및 활동은 이러한 시트 중 하나로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="9b0f3-129">![사이트 활용 playbook](media/deploy-my-service-image1.png "스크린샷 playbook") 스크린샷</span><span class="sxs-lookup"><span data-stu-id="9b0f3-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="9b0f3-130">팀 배포 범위에서 각 사이트에 대 한 playbook의 개별 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="9b0f3-131">Playbook를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="9b0f3-131">How to use the playbook</span></span>

<span data-ttu-id="9b0f3-132">위치에 대 한 크기와 복잡도에 관계 없이 각 사이트를 사용 하도록 설정 하면 작업 및 활동을 초기에 계획 하 고 실제 서비스 출시 전, 중, 그리고 그 후에 최적의 순서로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="9b0f3-133">Microsoft 팀 음성으로 직접 여행을 계획 하 고 실행할 때 다음 단계를 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="9b0f3-134">Microsoft 팀 음성에 대 한 [Playbook (Playbook)의 비즈니스용 전화](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 를 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="9b0f3-135">각 사이트에 대 한 playbook의 별도 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="9b0f3-136">**{Sitename-code}에 대 한 Playbook**이라는 시트의 탭에서 **{sitename-code}** 를 관련 사이트 이름 및/또는 사이트 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="9b0f3-137">아래 그림과 같이 **사이트 이름, 사이트 코드**및 **계획 된 시작 날짜**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="9b0f3-138">이것은 playbook의 모든 활동에 대해 권장 되는 마감 기한을 조정 하기 때문에 중요 한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="9b0f3-139">사이트 ![이름, 사이트 코드 및 계획 된 시작 날짜](media/deploy-my-service-image2.png "예제 (뉴욕의 사이트 이름, 사이트 코드 NY01, 계획 된 시작 날짜/년 3 월 20 일)")</span><span class="sxs-lookup"><span data-stu-id="9b0f3-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="9b0f3-140">각 활동을 검토 하 고 필요한 작업을 수행 하 고 시간 표시 막대를 진행할 때 상태를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="9b0f3-141">상태는 아래에 설명 된 대로 그래픽으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="9b0f3-142">![녹색 확인 표시](media/deploy-my-service-image3.png) **예, 적용 되지 않음 (녹색):** 활동이 완료 되었거나이 사이트에 적용 되지 않으며 추가 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="9b0f3-143">![노란색 느낌표](media/deploy-my-service-image4.png) 그림 <strong>활동은 아직 완료 되지 않음 (노란색):</strong> 작업이 아직 완료 되지 않았으므로 해당 일정의 예 또는 아니요로 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="9b0f3-144">![](media/deploy-my-service-image5.png) <strong>아니요 (빨강)</strong> 를 표시 하는 빨간색 X 그림: 문제로 인해 작업을 완료할 수 없어 프로젝트 상태 모임에 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="9b0f3-145">상태가 각 섹션 내에 겹쳐서 표시 되 고 섹션 제목에 다음 상태 표시기 중 하나로 서식이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="9b0f3-146">**주간 상태** 도 자동으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="9b0f3-147">(media/deploy-my-service-image6.png "Playbook의 주간 상태 롤업에 대 한 playbook 스크린샷") 의 ![주간 상태 롤업 스크린샷]</span><span class="sxs-lookup"><span data-stu-id="9b0f3-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="9b0f3-148">사용 중인 모든 위치에 대해 위 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9b0f3-149">일부 단계는 일부 위치 및 사이트에 적용 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="9b0f3-150">특정 활동이 사이트와 관련이 없는 경우이 활동에는 **해당 하지 않음** 을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="9b0f3-151">Playbook에서 행을 **삭제 하지 마세요** . 이렇게 하면 상태 롤업 수식이 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="9b0f3-152">전화 번호 포팅, 조달 활동 등 예정 보다 시간이 더 걸릴 수 있는 활동에 주의를 기울여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="9b0f3-153">이러한 활동은 사이트 배포 시간 표시 막대에 부정적인 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="9b0f3-154">활동 목록과 관련 시간 표시 막대를 매주 검토 하 고 업데이트 한 후, 관계자가 각 사이트의 상태와 배포 일정의 가능한 편차를 알 수 있도록 개체를 [조종 위원회 모임](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) 에 제시 하세요.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="9b0f3-155">결정 사항</span><span class="sxs-lookup"><span data-stu-id="9b0f3-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="9b0f3-156">배포에 사이트 Playbook 필요한 지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="9b0f3-157">배포할 모든 사이트에 대해 Microsoft 팀의 사이트 이용 Playbook 사용자 지정을 담당할 사용자를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="9b0f3-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9b0f3-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="9b0f3-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">사이트 Playbook를 다운로드</a>합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="9b0f3-160">첫 번째 사이트의 사이트 Playbook을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="9b0f3-161">추가 사이트에 대해 필요에 따라 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b0f3-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->