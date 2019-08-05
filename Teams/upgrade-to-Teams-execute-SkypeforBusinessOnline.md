---
title: 비즈니스용 Skype Online을 Microsoft 팀으로 업그레이드 | 배치
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 비즈니스용 Skype Online에서 팀으로 업그레이드 하기 위한 고려 사항
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9994bb8efa862cc66cb1e081d0ca8136b4fb1871
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "36185216"
---
<span data-ttu-id="ab695-103">![여행 다이어그램 업그레이드, 배포 및 구현 강조] (media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계")</span><span class="sxs-lookup"><span data-stu-id="ab695-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="ab695-104">이 문서는 업그레이드 여행 배포 및 구현 단계의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="ab695-105">계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="ab695-106">프로젝트 이해 관계자 참여</span><span class="sxs-lookup"><span data-stu-id="ab695-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="ab695-107">프로젝트 범위 정의</span><span class="sxs-lookup"><span data-stu-id="ab695-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="ab695-108">비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해</span><span class="sxs-lookup"><span data-stu-id="ab695-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="ab695-109">업그레이드 여행 선택</span><span class="sxs-lookup"><span data-stu-id="ab695-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="ab695-110">환경 준비</span><span class="sxs-lookup"><span data-stu-id="ab695-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="ab695-111">조직 준비</span><span class="sxs-lookup"><span data-stu-id="ab695-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="ab695-112">파일럿 수행</span><span class="sxs-lookup"><span data-stu-id="ab695-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="ab695-113">비즈니스용 Skype Online에서 팀으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="ab695-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="ab695-114">Skype for business Online을 완전히 구축한 경우 비즈니스용 Skype에서 팀으로 사용자를 업그레이드 하려면이 문서의 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ab695-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="ab695-115">사용자에 게 적절 한 공존 및 업그레이드 모드를 지정 하 여 조직에서 선택한 업그레이드 여행에 따라 사용자를 선택적으로 또는 모두 in으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab695-116">비즈니스용 Skype Online은 2021 년 7 월 31 일에 만료 되며, 그 이후에는 더 이상 접근성 또는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="ab695-117">조직의 혜택 실현을 최대화 하 고 업그레이드를 구현 하는 데 적절 한 시간을 확보 하려면 지금 Microsoft 팀으로 여행을 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="ab695-118">성공적으로 업그레이드 하면 기술 및 사용자의 준비가 정렬 되므로 Microsoft 팀으로 여행을 이동할 때이 가이드의 지침을 활용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="ab695-119">공존 및 업그레이드 모드 지정</span><span class="sxs-lookup"><span data-stu-id="ab695-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="ab695-120">Microsoft 팀 관리 센터 또는 비즈니스용 Skype 원격 Windows Powershell 세션을 사용 하 여 수행할 수 있는 TeamsUpgradePolicy의 UpgradeToTeams 인스턴스를 할당 하 여 사용자를 TeamsOnly 모드로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="ab695-121">이 작업은 사용자별로 수행 하거나 전체 테 넌 트를 한 번에 업그레이드 하려는 경우 테 넌 트를 기준으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="ab695-122">자세한 내용은 [공존 및 업그레이드 설정](https://aka.ms/SkypeToTeams-SetCoexistence) 및 TeamsUpgradePolicy 설정 ( [마이그레이션 및 공존 관리](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab695-122">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="ab695-123">한 번에 모든 사용자를 팀으로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="ab695-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="ab695-124">모든 사용자를 한 번에 팀으로 업그레이드 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ab695-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="ab695-125">1 단계: 사용자에 게 변경 내용 알리기 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ab695-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="ab695-126">Microsoft 팀 관리 센터에서 **조직 전체 설정** > **팀 업그레이드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="ab695-127">**공존 모드**에서 **비즈니스용 Skype 사용자에 게 업그레이드를 사용할 수 있는 사람에 게 알림** ( **On**으로 전환)을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="ab695-128">2 단계: 조직에 대해서만 공존 모드를 TeamsOnly로 설정</span><span class="sxs-lookup"><span data-stu-id="ab695-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="ab695-129">Microsoft 팀 관리 센터에서 **조직 전체 설정을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="ab695-130">**공존 모드** 드롭다운 목록에서 **팀 전용** 모드를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="ab695-131">단계에서 사용자 업그레이드</span><span class="sxs-lookup"><span data-stu-id="ab695-131">Upgrade users in stages</span></span>

<span data-ttu-id="ab695-132">사용자를 팀 전용으로 점진적으로 업그레이드 하려는 경우 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="ab695-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="ab695-133">1 단계: 업그레이드할 사용자 그룹 식별</span><span class="sxs-lookup"><span data-stu-id="ab695-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="ab695-134">조직에서 사용자의 성공으로 조직에 대 한 업그레이드를 선택 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="ab695-135">Microsoft 팀 관리 센터에서 이러한 사용자를 쉽게 검색할 수 있도록 먼저 해당 사용자를 식별 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="ab695-136">또는 PowerShell을 사용 하 여 더 효율적으로 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="ab695-137">지정 된 업그레이드 웨이브에 대 한 사용자 집합을 식별 한 후 나머지 단계를 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="ab695-138">2 단계: 현재 업그레이드 웨이브의 사용자에 대 한 알림 설정 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ab695-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="ab695-139">Microsoft 팀 관리 센터를 사용 하는 경우 한 번에 최대 20 명의 사용자에 대해 TeamsUpgradePolicy을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="ab695-140">Microsoft 팀 관리 센터에서 **사용자**를 선택 하 고, 업그레이드 해야 하는 최대 20 명의 사용자에 대 한 확인란을 선택 하 고 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="ab695-141">Listview의 왼쪽 위 모서리에서 **설정 편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="ab695-142">오른쪽의 **설정 편집** 창에서 **팀 업그레이드**아래에서 **비즈니스용 Skype 사용자 전환 알림을** **설정**으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="ab695-143">참고: 공존 모드의 값이 "조직 전체 설정 사용" 인 경우에는이 스위치가 표시 되지 않으므로 먼저 해당 사용자의 공존 모드를 조직에 대 한 기본값에 대 한 기본 값으로 명시적으로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="ab695-144">또는 사용자 그룹에 대해 PowerShell을 사용 하 여 한 번에 알림을 사용 하는 것이 더 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="ab695-145">3 단계: 사용자에 대 한 공존 모드를 팀에만 설정</span><span class="sxs-lookup"><span data-stu-id="ab695-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="ab695-146">팀을 유일한 응용 프로그램으로 사용 하도록 현재 웨이브의 사용자를 업그레이드할 준비가 되었으면 사용자의 공존 모드를 팀 전용으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="ab695-147">Microsoft 팀 관리 센터를 사용 하는 경우 한 번에 최대 20 명의 사용자에 대해 TeamsUpgradePolicy을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="ab695-148">Microsoft 팀 관리 센터에서 **사용자**를 선택한 다음 최대 20 명의 사용자에 대 한 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="ab695-149">Listview의 왼쪽 위 모서리에서 **설정 편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="ab695-150">오른쪽의 **설정 편집** 창에서 **팀 업그레이드** 섹션의 드롭다운 목록에 있는 **팀에만** 공존 모드를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="ab695-151">또는 PowerShell을 사용 하 여 한 번에 사용자 그룹을 업그레이드 하는 것이 더 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="ab695-152">4 단계: 후속 사용자를 위해 1-3 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="ab695-153">팀 전용 모드로의 업그레이드를 확인 하 고 확장할 준비가 되 면 이전 단계를 반복 하 여 다른 사용자 에게만 팀을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="ab695-154">전화 시스템 및 팀 업그레이드</span><span class="sxs-lookup"><span data-stu-id="ab695-154">Phone System and Teams upgrade</span></span>

<span data-ttu-id="ab695-155">비즈니스용 Skype Online 배포에 전화 요금제가 포함 되어 있고 Microsoft가 공공 교환 통신망 (PSTN) 인 경우 팀으로의 사용자 업그레이드는 자동으로 인바운드 PSTN 통화를 팀으로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab695-155">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="ab695-156">비즈니스용 Skype Online 배포에 클라우드 커넥터 버전이 있는 전화 시스템이 포함 된 경우 [전화 시스템 다이렉트 라우팅에 대 한 추가 고려 사항을](2-envision-make-my-service-decisions-direct-routing.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab695-156">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
