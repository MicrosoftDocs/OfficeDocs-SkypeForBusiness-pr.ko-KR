---
title: 온라인에서 비즈니스용 Skype 온라인에서 Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 조직을 온라인 배포에서 Microsoft Teams 업그레이드하는 비즈니스용 Skype 설명합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c35909bf7787242a07f89d1442a25365348c91a
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282105"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="97997-103">온라인에서 비즈니스용 Skype 업그레이드합니다Teams</span><span class="sxs-lookup"><span data-stu-id="97997-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="97997-104">![배포 및 구현을 강조하는 업그레이드 여정 다이어그램](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계")</span><span class="sxs-lookup"><span data-stu-id="97997-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="97997-105">이 문서는 업그레이드 단계의 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="97997-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="97997-106">계속하기 전에 다음 작업을 완료한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="97997-107">프로젝트 관계자 인리스트</span><span class="sxs-lookup"><span data-stu-id="97997-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="97997-108">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="97997-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="97997-109">비즈니스용 Skype 및 상호운용성을 Teams</span><span class="sxs-lookup"><span data-stu-id="97997-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="97997-110">업그레이드 여정을 선택했습니다.</span><span class="sxs-lookup"><span data-stu-id="97997-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="97997-111">환경 준비</span><span class="sxs-lookup"><span data-stu-id="97997-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="97997-112">조직 준비</span><span class="sxs-lookup"><span data-stu-id="97997-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="97997-113">파일럿 수행</span><span class="sxs-lookup"><span data-stu-id="97997-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="97997-114">온라인에서 전체적으로 배포한 비즈니스용 Skype 사용자 업그레이드를 원하는 경우 이 문서의 지침을 비즈니스용 Skype Teams.</span><span class="sxs-lookup"><span data-stu-id="97997-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="97997-115">조직에서 선택한 업그레이드 여정에 따라 사용자에게 적절한 공존 및 업그레이드 모드를 할당하여 사용자를 선택적으로 또는 올인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97997-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="97997-116">비즈니스용 Skype Online은 2021년 7월 31일에 서비스가 종료되며 이후에는 더 이상 액세스할 수 없게 되거나 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97997-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="97997-117">혜택 현실화를 최대화하고 조직에서 업그레이드를 구현할 적절한 시간을 확보하기 위해 현재 업그레이드를 위한 여정을 Microsoft Teams 권장됩니다.</span><span class="sxs-lookup"><span data-stu-id="97997-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="97997-118">성공적인 업그레이드는 기술 및 사용자 준비를 일치시 하도록 설정하기 때문에 다음 지침을 활용하여 업그레이드를 진행하는 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="97997-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="97997-119">공존 및 업그레이드 모드 할당</span><span class="sxs-lookup"><span data-stu-id="97997-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="97997-120">TeamsUpgradePolicy의 UpgradeToTeams 인스턴스를 할당하여 사용자를 TeamsOnly 모드로 업그레이드할 수 있습니다. 이 인스턴스는 Microsoft Teams 관리 센터 또는 원격 비즈니스용 Skype Windows PowerShell 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97997-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows PowerShell session.</span></span> <span data-ttu-id="97997-121">한 단계로 전체 테넌트를 업그레이드하려는 경우 사용자당 또는 테넌트 전체에서 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97997-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="97997-122">자세한 내용은 [공존](./setting-your-coexistence-and-upgrade-settings.md) 및 업그레이드 설정 및 [TeamsUpgradePolicy:](upgrade-to-teams-on-prem-tools.md)마이그레이션 및 공존 관리 를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97997-122">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="97997-123">모든 사용자를 한 Teams 업그레이드</span><span class="sxs-lookup"><span data-stu-id="97997-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="97997-124">다음 단계를 수행하여 모든 사용자를 한 Teams 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="97997-125">1단계: 변경 내용을 사용자에게 알릴 수 있습니다(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="97997-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="97997-126">Microsoft Teams 관리 센터에서 업그레이드 에서 **org-wide**  >  **Teams 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="97997-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="97997-127">**공존** 모드 아래에서 비즈니스용 Skype 업그레이드가 켜지도록 Teams 사용자에게 알림 **을 으로** **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="97997-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="97997-128">2단계: 조직에 대해 TeamsOnly에 공존 모드 설정</span><span class="sxs-lookup"><span data-stu-id="97997-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="97997-129">Microsoft Teams 관리 센터에서 **Org-wide 설정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="97997-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="97997-130">공존 **Teams** 드롭다운 목록에서 전용 모드를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="97997-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="97997-131">단계적 사용자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="97997-131">Upgrade users in stages</span></span>

<span data-ttu-id="97997-132">사용자를 TeamsOnly로 점진적으로 업그레이드하려는 경우 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="97997-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="97997-133">1단계: 업그레이드할 사용자 그룹 식별</span><span class="sxs-lookup"><span data-stu-id="97997-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="97997-134">종종 조직은 사용자의 성공을 위해 조직을 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97997-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="97997-135">관리 센터에서 쉽게 검색할 수 있도록 먼저 이러한 사용자를 Microsoft Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="97997-136">또는 PowerShell을 사용하여 이 작업을 보다 효율적으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97997-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="97997-137">특정 업그레이드 웨이브에 대한 사용자 집합을 확인한 후 나머지 단계를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="97997-138">2단계: 현재 업그레이드 웨이브의 사용자에 대한 알림 설정(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="97997-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="97997-139">관리 센터를 Microsoft Teams 경우 최대 20명까지 한 번씩 TeamsUpgradePolicy를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97997-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="97997-140">Microsoft Teams 관리 센터에서 사용자 **및** 를 선택하고 업그레이드해야 하는 최대 20명에 대한 확인란을 찾아 다중으로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="97997-141">목록 **보기의** 왼쪽 위 모서리에서 설정 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="97997-142">오른쪽의  설정 편집 창에서 업그레이드 Teams **에서**  사용자 비즈니스용 Skype 으로 **변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="97997-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="97997-143">참고: 공존 모드 값이 "Org-wide 설정 사용"인 경우 이 스위치가 표시되지 않습니다. 따라서 먼저 이러한 사용자에 대한 공존 모드를 기본적으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="97997-144">또는 PowerShell을 사용하여 한 번씩 사용자 그룹에 대한 알림을 사용하도록 설정하는 것이 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="97997-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="97997-145">3단계: 사용자만 사용할 수 있도록 공존 모드 Teams 설정</span><span class="sxs-lookup"><span data-stu-id="97997-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="97997-146">현재 웨이브에서 사용자를 유일한 애플리케이션으로 사용할 수 있도록 Teams 경우 사용자에 대한 공존 모드를 Teams만 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="97997-147">관리 센터를 Microsoft Teams 경우 최대 20명까지 한 번씩 TeamsUpgradePolicy를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97997-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="97997-148">관리 Microsoft Teams 관리 센터에서 사용자를 선택한 다음 최대 20명에 대한 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="97997-149">목록 **보기의** 왼쪽 위 모서리에서 설정 편집을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="97997-150">오른쪽의  설정 편집 창에서 업그레이드  Teams 섹션에서 공존 모드를 드롭다운 **목록에서만** Teams 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="97997-151">또는 PowerShell을 사용하여 한 번씩 사용자 그룹을 업그레이드하는 것이 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="97997-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="97997-152">4단계: 연속된 사용자 파동에 대해 1-3단계 반복</span><span class="sxs-lookup"><span data-stu-id="97997-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="97997-153">전용 모드로 Teams 업그레이드의 유효성을 검사하고 확장할 준비가 되면 이전 단계를 반복하여 TeamsOnly를 더 많은 사용자에게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="97997-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="97997-154">전화 시스템 및 PSTN 연결 옵션</span><span class="sxs-lookup"><span data-stu-id="97997-154">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="97997-155">전화 시스템 Teams TeamsOnly 모드에 있는 후에 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="97997-155">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="97997-156">(사용자가 제도 모드인 경우 전화 시스템 지원되는 비즈니스용 Skype.)</span><span class="sxs-lookup"><span data-stu-id="97997-156">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span>  

### <a name="pstn-connectivity-options"></a><span data-ttu-id="97997-157">PSTN 연결 옵션</span><span class="sxs-lookup"><span data-stu-id="97997-157">PSTN connectivity options</span></span>

<span data-ttu-id="97997-158">PSTN(공용 전환 전화 네트워크) 연결 옵션을 고려할 때 온라인에서 TeamsOnly 모드로 이동하는 비즈니스용 Skype 가능한 두 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97997-158">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business Online to TeamsOnly mode:</span></span>

- <span data-ttu-id="97997-159">Microsoft 통화 비즈니스용 Skype 있는 온라인 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="97997-159">A user in Skype for Business Online, with a Microsoft Calling Plan.</span></span> <span data-ttu-id="97997-160">업그레이드 시 이 사용자는 Microsoft 통화 계획을 계속 하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97997-160">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span> <span data-ttu-id="97997-161">이 시나리오는 몇 단계만 요구하는 가장 간단한 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="97997-161">This is the simplest scenario requiring only a couple of steps.</span></span> <span data-ttu-id="97997-162">자세한 내용은 Microsoft 호출 [비즈니스용 Skype 온라인에서 를 참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="97997-162">For more information, see [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span>

- <span data-ttu-id="97997-163">프레미스 비즈니스용 Skype Cloud Connector Edition을 통해 비즈니스용 Skype 음성 기능이 있는 온라인 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="97997-163">A user in Skype for Business Online, with on-premises voice functionality through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="97997-164">사용자의 업그레이드를 Teams 직접 라우팅으로의 마이그레이션과 조정해야 TeamsOnly 사용자에게 PSTN 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97997-164">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>  <span data-ttu-id="97997-165">자세한 내용은 온라인에서 비즈니스용 Skype [음성을 참조하세요.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)</span><span class="sxs-lookup"><span data-stu-id="97997-165">For more information see, [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span></span>