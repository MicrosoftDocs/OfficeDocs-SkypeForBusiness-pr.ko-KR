---
title: 클라우드 Microsoft Teams 서비스 배포
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 사이트 사용 플레이북을 다운로드하여 Teams 계획하고 사용자 채택, 품질 인식 및 만족도를 가속화하고 최적화합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112634"
---
# <a name="deploy-my-service"></a><span data-ttu-id="007bd-103">내 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="007bd-103">Deploy my service</span></span>

<span data-ttu-id="007bd-104">이 문서에서는 클라우드 음성 서비스를 올바르게 배포하기 위한 요구 사항에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="007bd-105">클라우드 음성 서비스를 배포하기 위한 지침에 따라 모든 요구 사항을 성공적으로 고려하고 반복 가능한 결과를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="007bd-106">음성 워크로드에 대한 사이트 Microsoft Teams 플레이북</span><span class="sxs-lookup"><span data-stu-id="007bd-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="007bd-107">이 플레이북을 사용하여 조직에서 사이트 Microsoft Teams 음성 기능의 롤아웃을 성공적으로 계획하고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="007bd-108">필요한 모든 활동, 권장 시간 표시 막대 및 각 활동에 대한 해당 지침에 대한 링크를 포함하여 이 플레이북은 사용자에게 중요한 요소에 초점을 맞추고, 주어진 Teams 음성 배포의 성공을 보장하는 데 도움이 되는 종단-종단 지침에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="007bd-109">이 플레이북에서 활동을 완료하면 조직에서 다음을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="007bd-110">롤아웃을 효과적으로 계획하고 Teams 예약합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="007bd-111">사용자 채택을 가속화하고 최적화합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="007bd-112">지원 요구를 줄이고 사용자 만족도를 높입니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="007bd-113">이 문서 및 관련 플레이북은 서비스 사용 또는 특정 사이트에 전화 걸기 톤을 제공하는 데 필요한 모든 기술 구성 단계를 설명하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="007bd-114">대신 사용자가 쉽게 온보드하는 데 권장되는 활동 및 작업에 집중하고 채택률이 높고 Teams 신속하고 원활한 전환을 통해 음성 워크로드를 사용하게 하면서 지원 요구 사항을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="007bd-115">음성에 대한 환경을 가장 잘 구성하는 방법에 대한 기술 지침은 Teams 음성 [](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)워크로드 구성, Teams 직접 라우팅 구성 [Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)Teams 핵심 [](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)기능, Teams 네트워킹 [](prepare-network.md)및 Microsoft 365 또는 [Office 365.를 참조하세요.](onboarding-checklist-enable-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="007bd-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](prepare-network.md), and [enabling Microsoft 365 or Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="007bd-116">플레이북 포커스 영역</span><span class="sxs-lookup"><span data-stu-id="007bd-116">Playbook focus areas</span></span>

<span data-ttu-id="007bd-117">플레이북의 초점은 음성 배포에 대한 사용자의 인식에 영향을 주는 요인을 Teams 것입니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="007bd-118">활동 및 작업은 다음 포커스 영역으로 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="007bd-119">서비스 준비의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="007bd-119">Validation of service readiness</span></span>
    - <span data-ttu-id="007bd-120">오디오 회의</span><span class="sxs-lookup"><span data-stu-id="007bd-120">Audio Conferencing</span></span>
    - <span data-ttu-id="007bd-121">통화 플랜</span><span class="sxs-lookup"><span data-stu-id="007bd-121">Calling Plans</span></span>
    - <span data-ttu-id="007bd-122">직접 라우팅</span><span class="sxs-lookup"><span data-stu-id="007bd-122">Direct Routing</span></span>

-   <span data-ttu-id="007bd-123">사용자 사용</span><span class="sxs-lookup"><span data-stu-id="007bd-123">User enablement</span></span>

-   <span data-ttu-id="007bd-124">엔드포인트</span><span class="sxs-lookup"><span data-stu-id="007bd-124">Endpoints</span></span>

-   <span data-ttu-id="007bd-125">사용 현황 및 품질</span><span class="sxs-lookup"><span data-stu-id="007bd-125">Usage and quality</span></span>

-   <span data-ttu-id="007bd-126">채택</span><span class="sxs-lookup"><span data-stu-id="007bd-126">Adoption</span></span>

<span data-ttu-id="007bd-127">음성용 사이트 사용 [플레이북(Playbook)은](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) Microsoft Excel 통합 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="007bd-128">이러한 5개의 포커스 영역 각각은 통합 문서의 별도 시트로, 각 배포 작업 및 활동은 이러한 시트 중 하나에 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="007bd-129">![사이트 사용 플레이북 스크린샷](media/deploy-my-service-image1.png "플레이북 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="007bd-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="007bd-130">각 사이트에 대해 플레이북의 별도 인스턴스를 생성하여 롤아웃 범위에 Teams 있습니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="007bd-131">플레이북을 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="007bd-131">How to use the playbook</span></span>

<span data-ttu-id="007bd-132">위치의 크기와 복잡성에 관계없이 각 사이트를 사용하도록 설정하려면 작업 및 활동을 충분히 일찍 계획하고 실제 서비스 롤아웃 전, 중 및 후에 최적의 순서로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="007bd-133">음성을 통해 사용자 자신의 여정을 계획하고 실행할 때 다음 단계를 Microsoft Teams 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="007bd-134">음성용 [사이트](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 사용 플레이북(Playbook)을 Microsoft Teams 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="007bd-135">각 사이트에 대해 플레이북의 별도 복사본을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="007bd-136">**{SiteName-Code}의 Playbook이라는** 시트의 탭에서 **{SiteName-Code}를** 관련 사이트 이름 및/또는 사이트 코드로 바 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="007bd-137">아래와 같은 사이트 **이름, 사이트** 코드 및 **계획된** 시작 날짜를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="007bd-138">이는 플레이북의 모든 활동에 권장되는 마감일을 조정하기 때문에 중요한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="007bd-139">![사이트 이름, 사이트 코드 및 계획된 출시 날짜가 있는 예제](media/deploy-my-service-image2.png "뉴욕의 사이트 이름, 사이트 코드 NY01 및 예정된 출시 날짜가 20-3월 18일인 예제")</span><span class="sxs-lookup"><span data-stu-id="007bd-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="007bd-140">각 활동을 검토하고, 필요한 작업을 수행하고, 타임라인을 진행할 때 상태를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="007bd-141">상태는 아래에 설명된 바와 같이 그래픽으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="007bd-142">![녹색 확인 표시 ](media/deploy-my-service-image3.png) **예(녹색)의 그림:** 작업이 완료되거나 이 사이트에 적용되지 않습니다. 추가 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="007bd-143">![노란색 느낌표의 그림: 활동이 아직 완료되지 않았습니다(노란색): 활동이 아직 완료되지 않았고 일정에 따라 예 또는 아니요로 ](media/deploy-my-service-image4.png) <strong></strong> 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="007bd-144">![아니요(빨간색)를 나타내는 빨간색 X 그림: 문제로 활동을 완료할 수 없습니다. 프로젝트 상태 모임으로 ](media/deploy-my-service-image5.png) <strong></strong> 진행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="007bd-145&quot;>상태는 각 섹션 내에서 롤업됩니다. 섹션 제목은 이러한 상태 표시기 중 하나를 통해 서식이 지정됩니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;007bd-145&quot;>The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id=&quot;007bd-146&quot;>**주간 상태도** 자동으로 업데이트됩니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;007bd-146&quot;>**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id=&quot;007bd-147&quot;>![플레이북의 주간 상태 롤업 스크린샷](media/deploy-my-service-image6.png &quot;플레이북의 주간 상태 롤업 스크린샷")</span><span class="sxs-lookup"><span data-stu-id="007bd-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="007bd-148">모든 위치에 대해 위의 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="007bd-149">일부 단계는 일부 위치 및 사이트에 적용되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="007bd-150">특정 활동이 사이트와 관련이 없는 경우 이 활동에 적용할 수 없습니다를 **선택해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="007bd-151">**플레이북의** 행을 삭제하지 않습니다. 이 경우 상태 롤업 수식이 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="007bd-152">숫자 포터링 및 조달 활동과 같이 계획보다 시간이 더 걸릴 수 있는 활동에 주의를 기울입니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="007bd-153">이러한 활동은 사이트 배포 타임라인에 부정적인 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="007bd-154">활동 목록 및 관련 타임라인을 매주 검토하고 업데이트하고 운영 [](./envision-steering-committee-complete-guide.md) 위원회 모임에서 발표하여 관계자가 각 사이트의 상태와 배포 일정에서 가능한 일차를 인식할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](./envision-steering-committee-complete-guide.md) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="007bd-155">의사 결정 지점</span><span class="sxs-lookup"><span data-stu-id="007bd-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="007bd-156">배포에 사이트 사용 플레이북이 필요한지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="007bd-157">배포할 모든 사이트에 대해 사이트 사용 Microsoft Teams 사용자 지정을 담당할 사용자 지정을 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="007bd-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="007bd-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="007bd-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">사이트 사용 플레이북을 다운로드합니다.</a></span><span class="sxs-lookup"><span data-stu-id="007bd-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="007bd-160">첫 번째 사이트에 대한 사이트 사용 플레이북을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="007bd-161">필요에 따라 추가 사이트에 대해 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="007bd-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->