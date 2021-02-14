---
title: 비즈니스용 Skype-프레미스 배포에서 Teams로 업그레이드 - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: bec5c2b10dc2e09092cd7c26284c04868982e287
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533605"
---
# <a name="implement-your-upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a><span data-ttu-id="7b95b-103">비즈니스용 Skype에서 IT 관리자용 Teams로 업그레이드 &mdash; 구현</span><span class="sxs-lookup"><span data-stu-id="7b95b-103">Implement your upgrade from Skype for Business to Teams &mdash; for IT administrators</span></span>

<span data-ttu-id="7b95b-104">이 문서에서는 업그레이드를 구현하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-104">This article describes how to implement your upgrade.</span></span> <span data-ttu-id="7b95b-105">이 문서는 IT 관리자를 위한 업그레이드 개념 및 구현을 설명하는 다섯 번째 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-105">This article is the fifth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="7b95b-106">개요</span><span class="sxs-lookup"><span data-stu-id="7b95b-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="7b95b-107">업그레이드 방법</span><span class="sxs-lookup"><span data-stu-id="7b95b-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="7b95b-108">업그레이드를 관리하기 위한 도구</span><span class="sxs-lookup"><span data-stu-id="7b95b-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- [<span data-ttu-id="7b95b-109">비즈니스용 Skype가 있는 조직에 대한 추가 고려 사항</span><span class="sxs-lookup"><span data-stu-id="7b95b-109">Additional considerations for organizations with Skype for Business on-premises</span></span>](upgrade-to-teams-on-prem-considerations.md)
- <span data-ttu-id="7b95b-110">**업그레이드 구현(이** 문서)</span><span class="sxs-lookup"><span data-stu-id="7b95b-110">**Implement your upgrade** (this article)</span></span>
- [<span data-ttu-id="7b95b-111">PSTN(공용 전환 전화 네트워크) 고려 사항</span><span class="sxs-lookup"><span data-stu-id="7b95b-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="7b95b-112">또한 다음 문서에서는 중요한 업그레이드 개념 및 공존 동작을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="7b95b-113">Teams 및 비즈니스용 Skype의 공존</span><span class="sxs-lookup"><span data-stu-id="7b95b-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="7b95b-114">공존 모드 - 참조</span><span class="sxs-lookup"><span data-stu-id="7b95b-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="7b95b-115">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="7b95b-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="7b95b-116">업그레이드 옵션</span><span class="sxs-lookup"><span data-stu-id="7b95b-116">Upgrade options</span></span>

<span data-ttu-id="7b95b-117">이 섹션에서는 다음 업그레이드 옵션 중 하나를 사용하여 업그레이드를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-117">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="7b95b-118">겹치는 기능 업그레이드(제도 모드 사용)</span><span class="sxs-lookup"><span data-stu-id="7b95b-118">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="7b95b-119">Teams 사용을 아직 시작하지 않은 조직의 선택 기능 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7b95b-119">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="7b95b-120">이미 제도 모드에서 Teams를 사용하고 있는 조직의 선택 기능 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7b95b-120">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="7b95b-121">옵션에 대한 자세한 정보가 필요한 경우 업그레이드 방법을 이미 [읽어야 합니다.](upgrade-to-teams-on-prem-upgrade-methods.md)</span><span class="sxs-lookup"><span data-stu-id="7b95b-121">If you need more information about the options, make sure you have already read [Upgrade methods](upgrade-to-teams-on-prem-upgrade-methods.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="7b95b-122">겹치는 기능 업그레이드(제도 모드 사용)</span><span class="sxs-lookup"><span data-stu-id="7b95b-122">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="7b95b-123">겹치는 기능 업그레이드 옵션의 경우:</span><span class="sxs-lookup"><span data-stu-id="7b95b-123">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="7b95b-124">전체 조직에 대해 빠른 업그레이드를 할 수 있는 경우 이 옵션을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-124">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="7b95b-125">두 클라이언트를 모두 실행하는 최종 사용자에게 혼동이 발생할 가능성이 있는 경우 사용자가 두 클라이언트를 모두 실행해야 하는 기간을 최소화할 수 있는 것이 가장 좋은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-125">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="7b95b-126">사용자가 두 클라이언트를 모두 실행하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-126">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="7b95b-127">이 옵션은 바로 사용할 수 있는 모델로, Microsoft 365 또는 Office 365 라이선스를 할당하는 것 외에는 Teams를 시작하는 관리자 작업이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-127">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="7b95b-128">사용자에게 비즈니스용 Skype Online이 이미 있는 경우 이미 이 모델에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-128">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="7b95b-129">기능 모드가 겹치고 TeamsOnly로 이동하는 것은 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-129">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="7b95b-130">업그레이드된 사용자는 Teams를 통해서만 통신하기 때문에 해당 사용자와 통신하는 조직의 다른 사용자는 Teams를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-130">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="7b95b-131">Teams 사용을 시작하지 않은 사용자가 있는 경우 누락된 메시지에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-131">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="7b95b-132">또한 비즈니스용 Skype에서는 TeamsOnly 사용자가 온라인에서 볼 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-132">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="7b95b-133">일부 조직에서는 이를 방지하기 위해 테넌트 전역 정책을 사용하여 테넌트 전체 업그레이드를 수행하기로 선택하기도 하지만, 모든 사용자를 업그레이드할 준비가 될 때까지 기다리는 것뿐만 아니라 선행 계획이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-133">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="7b95b-134">Teams 사용을 아직 시작하지 않은 조직의 선택 기능 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7b95b-134">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="7b95b-135">조직에 아직 Teams에 활성 사용자가 없는 경우 첫 번째 단계는 TeamsUpgradePolicy에 대한 기본 테넌트 전체 정책을 비즈니스용 Skype 모드 중 하나(예: SfbWithTeamsCollab) 중 하나로 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-135">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="7b95b-136">Teams 사용을 아직 시작하지 않은 사용자는 동작의 차이를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-136">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="7b95b-137">그러나 테넌트 수준에서 이 정책을 설정하면 사용자를 TeamsOnly 모드로 업그레이드하기 시작할 수 있으며 업그레이드된 사용자가 업그레이드되지 않은 사용자와 계속 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-137">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="7b95b-138">파일럿 사용자를 식별한 후 TeamsOnly로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-138">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="7b95b-139">이 경우 Move-CsUser를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-139">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="7b95b-140">온라인인 경우 Grant-CsTeamsUpgradePolicy를 사용하여 TeamsOnly 모드를 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-140">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="7b95b-141">기본적으로 이러한 사용자가 예약한 비즈니스용 Skype 모임은 Teams로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-141">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="7b95b-142">다음은 주요 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-142">Following are the key commands:</span></span>

1. <span data-ttu-id="7b95b-143">다음과 같이 테넌트 전체의 기본값을 SfbWithTeamsCollab 모드로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-143">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="7b95b-144">다음과 같이 파일럿 사용자를 TeamsOnly로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-144">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="7b95b-145">온라인인 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="7b95b-145">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="7b95b-146">On-premises에 있는 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="7b95b-146">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="7b95b-147">참고</span><span class="sxs-lookup"><span data-stu-id="7b95b-147">Notes</span></span>
 
- <span data-ttu-id="7b95b-148">테넌트 전체 정책을 SfbWithTeamsCollab으로 설정하는 대신 SfbWithTeamsCollabAndMeetings로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-148">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="7b95b-149">이렇게 하면 모든 사용자가 Teams에서 모든 새 모임을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-149">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="7b95b-150">`Move-CsUser` 은(는)</span><span class="sxs-lookup"><span data-stu-id="7b95b-150">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="7b95b-151">전환을 `MoveToTeams` 사용하려면 비즈니스용 Skype Server 2019 또는 CU8 이상이 있는 비즈니스용 Skype Server 2015가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-151">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="7b95b-152">이전 버전을 사용하는 경우 먼저 사용자를 비즈니스용 Skype Online으로 이동한 다음 TeamsOnly 모드를 해당 사용자에게 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-152">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="7b95b-153">기본적으로 비즈니스용 Skype 모임은 TeamsOnly 모드로 업그레이드하거나 SfbWithTeamsCollabAndMeetings 모드를 할당할 때 Teams로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-153">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

<span data-ttu-id="7b95b-154">아래 다이어그램은 Teams를 사전 사용하는 조직에 대한 선택 기능 업그레이드의 개념적 단계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-154">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="7b95b-155">막대의 높이는 사용자 수를 나타 내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-155">The height of the bars represents number of users.</span></span> <span data-ttu-id="7b95b-156">업그레이드 단계 중에는 모든 사용자가 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-156">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="7b95b-157">비즈니스용 Skype 사용자는 Interop을 사용하여 TeamsOnly 사용자와 통신하고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-157">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="7b95b-158">제도 모드의 사용자는 두 클라이언트를 모두 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-158">Users in Islands mode must be sure to run both clients.</span></span>

![Teams를 이전에 사용하지 않습니다. 선택 기능 업그레이드를 보여 주는 다이어그램](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="7b95b-160">이미 제도 모드에서 Teams를 사용하고 있는 조직의 선택 기능 업그레이드</span><span class="sxs-lookup"><span data-stu-id="7b95b-160">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="7b95b-161">조직의 일부 사용자가 제도 모드에서 Teams를 적극적으로 사용하는 경우 기존 사용자로부터 기능을 제거하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-161">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="7b95b-162">따라서 테넌트 전체 정책을 변경하기 전에 추가 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-162">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="7b95b-163">해결 방법은 테넌트 전체 정책을 SfbWithTeamsCollab으로 설정하기 전에 이러한 기존 활성 Teams 사용자를 제도 모드로 "조부"하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-163">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="7b95b-164">이렇게 하면 위와 같은 배포를 진행할 수 있습니다. 그러나 TeamsOnly로 이동하는 두 개의 사용자 그룹이 있습니다. Teams에서 활성 상태인 사용자는 제도 모드이고 나머지 사용자는 SfbWithTeamsCollab 모드에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-164">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="7b95b-165">이러한 사용자를 TeamsOnly 모드로 점진적으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-165">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="7b95b-166">Teams에서 활성 상태인 사용자를 다음과 같이 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-166">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="7b95b-167">Microsoft 365 관리 센터의 왼쪽 탐색 모음에서 보고서로 이동한 다음 사용 현황으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="7b95b-167">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="7b95b-168">"보고서 선택" 드롭다운에서 Microsoft Teams를 선택한 다음 사용자 활동을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-168">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="7b95b-169">그러면 Teams에서 활성 상태인 내보낼 수 있는 사용자 테이블이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-169">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="7b95b-170">내보내기, Excel 열기 및 필터링을 클릭하여 Teams에서 활성 상태인 사용자만 보여 주게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-170">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="7b95b-171">1단계에서 찾은 각 활성 Teams 사용자에 대해 원격 PowerShell에서 제도 모드를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-171">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="7b95b-172">이렇게 하면 다음 단계로 이동하고 사용자 환경을 변경하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-172">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="7b95b-173">테넌트 전체 정책을 SfbWithTeamsCollab으로 설정:</span><span class="sxs-lookup"><span data-stu-id="7b95b-173">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="7b95b-174">선택한 사용자를 TeamsOnly 모드로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-174">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="7b95b-175">사용자가 제도 모드에 있을 때 발생할 수 있는 혼동 가능성을 최소화하기 위해 먼저 제도 모드에서 사용자를 업그레이드하는 우선 순위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-175">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="7b95b-176">비즈니스용 Skype Online에 있는 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="7b95b-176">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="7b95b-177">비즈니스용 Skype Server에 있는 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="7b95b-177">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="7b95b-178">아래 다이어그램은 시작 시 활성 제도 사용자가 있는 선택 기능 전환의 개념 단계를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-178">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="7b95b-179">막대의 높이는 사용자 수를 나타 내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-179">The height of the bars represents the number of users.</span></span> <span data-ttu-id="7b95b-180">업그레이드 단계 중에는 모든 사용자가 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-180">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="7b95b-181">비즈니스용 Skype 사용자는 Interop을 사용하여 TeamsOnly 사용자와 통신하고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="7b95b-181">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![제도 모드에서 활성 사용자로 기능 업그레이드 선택을 보여주는 다이어그램](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="7b95b-183">관련 링크</span><span class="sxs-lookup"><span data-stu-id="7b95b-183">Related links</span></span>

[<span data-ttu-id="7b95b-184">비즈니스용 Skype와 함께 Teams를 사용하는 조직을 위한 마이그레이션 및 상호 연동성 지침</span><span class="sxs-lookup"><span data-stu-id="7b95b-184">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="7b95b-185">비즈니스용 Skype Server와 Microsoft 365 또는 Office 365 간의 하이브리드 연결 구성</span><span class="sxs-lookup"><span data-stu-id="7b95b-185">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="7b95b-186">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="7b95b-186">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="7b95b-187">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="7b95b-187">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="7b95b-188">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="7b95b-188">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="7b95b-189">MMS(모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="7b95b-189">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

