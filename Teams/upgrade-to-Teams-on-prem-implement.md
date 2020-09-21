---
title: 비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드-Microsoft 팀
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8239d1fdbda10a61cd0846a0d56b1f1ffa62f597
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955905"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="7fb61-103">비즈니스용 Skype에서 IT 관리자를 위한 팀으로 업그레이드 구현 &mdash;</span><span class="sxs-lookup"><span data-stu-id="7fb61-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="7fb61-104">이 문서에서는 업그레이드를 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="7fb61-105">이 문서는 IT 관리자의 업그레이드 개념 및 구현에 대해 설명 하는 몇 째의 다섯 번째 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="7fb61-106">개요</span><span class="sxs-lookup"><span data-stu-id="7fb61-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="7fb61-107">업그레이드 방법</span><span class="sxs-lookup"><span data-stu-id="7fb61-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="7fb61-108">업그레이드 관리 도구</span><span class="sxs-lookup"><span data-stu-id="7fb61-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="7fb61-109">비즈니스용 Skype 온-프레미스를 사용 하는 조직에 대 한 추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="7fb61-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="7fb61-110">**업그레이드 구현** (이 문서)</span><span class="sxs-lookup"><span data-stu-id="7fb61-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="7fb61-111">PSTN (공개 통신 네트워크) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="7fb61-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="7fb61-112">또한 다음 문서에서는 중요 한 업그레이드 개념 및 공존 동작에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="7fb61-113">팀과 비즈니스용 Skype의 공존</span><span class="sxs-lookup"><span data-stu-id="7fb61-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="7fb61-114">공존 모드-참조</span><span class="sxs-lookup"><span data-stu-id="7fb61-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="7fb61-115">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="7fb61-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="7fb61-116">업그레이드 옵션</span><span class="sxs-lookup"><span data-stu-id="7fb61-116">Upgrade options</span></span>

<span data-ttu-id="7fb61-117">이 섹션에서는 다음 업그레이드 옵션 중 하나를 사용 하 여 업그레이드를 구현 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="7fb61-118">겹치는 기능 업그레이드 (아일랜드 모드 사용)</span><span class="sxs-lookup"><span data-stu-id="7fb61-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="7fb61-119">아직 팀 사용을 시작 하지 않은 조직에 대 한 선택 기능 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7fb61-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="7fb61-120">이미 아일랜드 모드에서 팀을 사용 중인 조직에 대 한 선택 기능 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7fb61-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="7fb61-121">옵션에 대 한 자세한 정보가 필요한 경우 [업그레이드 방법을](upgrade-to-teams-on-prem-upgrade-methods.md)이미 읽어 두세요.</span><span class="sxs-lookup"><span data-stu-id="7fb61-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="7fb61-122">겹치는 기능 업그레이드 (아일랜드 모드 사용)</span><span class="sxs-lookup"><span data-stu-id="7fb61-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="7fb61-123">겹치는 기능 업그레이드 옵션:</span><span class="sxs-lookup"><span data-stu-id="7fb61-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="7fb61-124">전체 조직에 대해 빠른 업그레이드를 수행할 수 있는 경우이 옵션을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fb61-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="7fb61-125">최종 사용자가 두 클라이언트를 모두 실행 하는 데 혼란을 초래할 수 있으므로 사용자가 두 클라이언트를 모두 실행 해야 하는 기간을 최소화 하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="7fb61-126">사용자가 두 클라이언트를 모두 실행 한다는 것을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="7fb61-127">이 옵션은 box 모델 이며 Microsoft 365 또는 Office 365 라이선스를 할당 하는 경우를 제외 하 고 팀을 시작 하는 데 관리자 작업이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="7fb61-128">사용자가 이미 비즈니스용 Skype Online을 사용 하 고 있는 경우이 모델에 이미 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="7fb61-129">접근 권한 모드를 종료 하 고 팀 전용으로 이동 하는 것은 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="7fb61-130">업그레이드 된 사용자는 팀을 통해서만 통신 하기 때문에 해당 사용자와 통신 하는 조직의 다른 사용자는 팀을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="7fb61-131">팀 사용을 시작 하지 않은 사용자가 있는 경우에는 누락 된 메시지에 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="7fb61-132">또한 비즈니스용 Skype에서 온라인 으로만 팀에 있는 사용자만 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="7fb61-133">일부 조직에서는이 문제를 방지 하기 위해 테 넌 트 전역 정책을 사용 하 여, 전체 사용자를 업그레이드할 준비가 될 때까지 대기 해야 하는 선행 계획을 수행 하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="7fb61-134">아직 팀 사용을 시작 하지 않은 조직에 대 한 선택 기능 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7fb61-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="7fb61-135">조직에서 아직 팀에 활성 사용자가 없는 경우 첫 번째 단계는 TeamsUpgradePolicy에 대 한 기본 테 넌 트 전역 정책을 비즈니스용 Skype 모드 중 하나 (예: SfbWithTeamsCollab)로 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="7fb61-136">팀 사용을 아직 시작 하지 않은 사용자는 동작의 차이를 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="7fb61-137">그러나 테 넌 트 수준에서이 정책을 설정 하면 사용자를 팀 전용 모드로 업그레이드 하 고 업그레이드 된 사용자가 업그레이드 되지 않은 사용자와 계속 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="7fb61-138">파일럿 사용자를 식별 한 후에는이를 팀 전용으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="7fb61-139">온-프레미스 인 경우 CsUser Move를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="7fb61-140">온라인 상태인 경우에는 CsTeamsUpgradePolicy를 사용 하 여 팀 전용 모드를 할당 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="7fb61-141">기본적으로 이러한 사용자가 예약한 모든 비즈니스용 Skype 모임은 팀으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="7fb61-142">다음은 주요 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-142">Following are the key commands:</span></span>

1. <span data-ttu-id="7fb61-143">다음과 같이 테 넌 트 전체 기본값을 mode SfbWithTeamsCollab로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="7fb61-144">다음과 같은 경우에만 파일럿 사용자를 TeamsOnly로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="7fb61-145">온라인 상태인 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="7fb61-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="7fb61-146">온-프레미스 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="7fb61-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="7fb61-147">상속자</span><span class="sxs-lookup"><span data-stu-id="7fb61-147">Notes</span></span>
 
- <span data-ttu-id="7fb61-148">테 넌 트 전체 정책을 SfbWithTeamsCollab로 설정 하는 대신 SfbWithTeamsCollabAndMeetings로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="7fb61-149">이렇게 하면 모든 사용자가 팀의 모든 새 모임을 예약 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="7fb61-150">`Move-CsUser` 온-프레미스 도구의 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="7fb61-151">이 `MoveToTeams` 스위치를 사용 하려면 비즈니스용 Skype server 2019 또는 CU8 이상과 비즈니스용 Skype server 2015이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="7fb61-152">이전 버전을 사용 하는 경우 먼저 사용자를 비즈니스용 Skype Online으로 이동한 다음 해당 사용자에 게 팀의 유일한 모드를 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="7fb61-153">기본적으로 비즈니스용 Skype 모임은 팀의 유일한 모드로 업그레이드 하거나 SfbWithTeamsCollabAndMeetings 모드를 할당할 때로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="7fb61-154">아래 다이어그램은 이전에 팀을 사용 하지 않은 조직의 조직에 대 한 선택 기능 업그레이드의 구상 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="7fb61-155">막대의 높이는 사용자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="7fb61-156">업그레이드 단계 중에는 모든 사용자가 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="7fb61-157">비즈니스용 Skype 사용자는 Interop를 사용 하는 사용자만 통신 하며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="7fb61-158">아일랜드 모드의 사용자는 두 클라이언트를 모두 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-158">Users in Islands mode must be sure to run both clients.</span></span>

![팀을 이전에 사용 하지 않고 선택 기능을 표시 하는 다이어그램](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="7fb61-160">이미 아일랜드 모드에서 팀을 사용 중인 조직에 대 한 선택 기능 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7fb61-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="7fb61-161">조직의 일부 사용자가 아일랜드 모드에서 활발 하 게 팀을 사용 하 고 있는 경우 기존 사용자의 기능을 제거 하는 것이 원하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="7fb61-162">따라서 테 넌 트 전체 정책을 변경 하기 전에 추가 단계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="7fb61-163">이 솔루션은 테 넌 트 전체 정책을 SfbWithTeamsCollab로 설정 하기 전에 이러한 기존 활성 팀 사용자를 아일랜드 모드로 "grandfather" 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="7fb61-164">이 작업을 완료 한 후에는 위에서 설명한 대로 배포를 진행할 수 있지만, 팀에서 활성 상태인 사용자는 아일랜드 모드에 있고 나머지 사용자는 SfbWithTeamsCollab 모드에 있는 두 그룹의 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="7fb61-165">이러한 사용자를 TeamsOnly 모드로 점진적으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="7fb61-166">다음과 같이 팀에서 활성 상태인 사용자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="7fb61-167">Microsoft 365 관리 센터의 왼쪽 탐색 창에서 보고서로 이동한 다음 사용 현황을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="7fb61-168">"보고서 선택" 드롭다운에서 Microsoft 팀, 사용자 활동을 차례로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="7fb61-169">팀에서 활성화 된 내보낼 수 있는 사용자 테이블을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="7fb61-170">내보내기, Excel 열기, 필터링을 차례로 클릭 하 여 팀에서 활성 상태인 사용자만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="7fb61-171">1 단계에서 찾은 각 활성 팀 사용자에 대해 원격 PowerShell에 아일랜드 모드를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="7fb61-172">이를 통해 다음 단계로 이동 하 여 사용자 환경을 변경 하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="7fb61-173">SfbWithTeamsCollab에 대해 테 넌 트 전체 정책을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="7fb61-174">선택한 사용자를 TeamsOnly 모드로 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="7fb61-175">아일랜드 모드에서 사용자를 업그레이드 하 여 사용자가 아일랜드 모드일 때 발생할 수 있는 혼동을 최소화 하는 것이 좋지만,이 경우에는 아일랜드 모드 또는 SfbWithTeamsCollab 모드에서 사용자를 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="7fb61-176">비즈니스용 Skype Online에 속한 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="7fb61-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="7fb61-177">비즈니스용 Skype Server 온-프레미스에 속한 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="7fb61-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="7fb61-178">아래 다이어그램에서는 시작에 활성 제도 사용자가 있는 선택 기능 전환의 개념적인 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="7fb61-179">막대의 높이는 사용자 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="7fb61-180">업그레이드 단계 중에는 모든 사용자가 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="7fb61-181">비즈니스용 Skype 사용자는 interop를 사용 하는 사용자만 통신 하며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="7fb61-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![아일랜드 모드에서 활성 사용자와의 선택 기능 업그레이드를 보여 주는 다이어그램](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="7fb61-183">관련 링크</span><span class="sxs-lookup"><span data-stu-id="7fb61-183">Related links</span></span>

[<span data-ttu-id="7fb61-184">비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침</span><span class="sxs-lookup"><span data-stu-id="7fb61-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="7fb61-185">비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="7fb61-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="7fb61-186">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="7fb61-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="7fb61-187">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="7fb61-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="7fb61-188">부여-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="7fb61-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="7fb61-189">MMS (모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="7fb61-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

