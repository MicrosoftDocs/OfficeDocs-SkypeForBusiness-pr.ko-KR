---
title: IT 관리자를 위한 업그레이드 전략
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 이 문서는 IT 관리자를 위한 것이고, 업그레이드를 구현하기 위한 전략을 비즈니스용 Skype Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e4bfb5594b64eb06041e7f761eb0d85cec8c3e5
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52306042"
---
# <a name="upgrade-strategies-for-it-administrators"></a><span data-ttu-id="f0326-103">IT 관리자를 위한 업그레이드 전략</span><span class="sxs-lookup"><span data-stu-id="f0326-103">Upgrade strategies for IT administrators</span></span>

<span data-ttu-id="f0326-104">![배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계")</span><span class="sxs-lookup"><span data-stu-id="f0326-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="f0326-105">이 문서는 업그레이드를 구현하려는 IT 관리자를 위한 Teams 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="f0326-105">This article is for IT administrators who want to implement their upgrade to Teams from Skype for Business.</span></span>

<span data-ttu-id="f0326-106">업그레이드를 구현하기 전에 중요한 업그레이드 개념 및 공존 동작을 설명하는 다음 문서를 추천합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-106">Before implementing your upgrade, we recommend the following articles which describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="f0326-107">Microsoft Teams 및 비즈니스용 Skype 상호운용성 이해</span><span class="sxs-lookup"><span data-stu-id="f0326-107">Understand Microsoft Teams and Skype for Business coexistence and interoperability</span></span>](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="f0326-108">공존 모드 - 참조</span><span class="sxs-lookup"><span data-stu-id="f0326-108">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="f0326-109">Teams 클라이언트 환경 및 공존 모드 준수</span><span class="sxs-lookup"><span data-stu-id="f0326-109">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)

## <a name="upgrade-options"></a><span data-ttu-id="f0326-110">업그레이드 옵션</span><span class="sxs-lookup"><span data-stu-id="f0326-110">Upgrade options</span></span>

<span data-ttu-id="f0326-111">이 섹션에서는 다음 업그레이드 옵션 중 하나를 사용하여 업그레이드를 구현하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-111">This section describes how to implement your upgrade by using one of the following upgrade options:</span></span>

- [<span data-ttu-id="f0326-112">겹치는 기능 업그레이드(제도 모드 사용)</span><span class="sxs-lookup"><span data-stu-id="f0326-112">Overlapping capabilities upgrade (using Islands mode)</span></span>](#overlapping-capabilities-upgrade-using-islands-mode)
- [<span data-ttu-id="f0326-113">아직 사용이 시작되지 않은 조직의 선택 기능 업그레이드 Teams</span><span class="sxs-lookup"><span data-stu-id="f0326-113">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams)
- [<span data-ttu-id="f0326-114">아일랜드 모드에서 이미 Teams 조직에 대한 선택 기능 업그레이드</span><span class="sxs-lookup"><span data-stu-id="f0326-114">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>](#a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode)

<span data-ttu-id="f0326-115">옵션에 대한 자세한 정보가 필요한 경우 업그레이드 여정 선택을 이미 읽은 비즈니스용 Skype [Teams.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="f0326-115">If you need more information about the options, make sure you have already read [Choose your upgrade journey from Skype for Business to Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md).</span></span>

## <a name="overlapping-capabilities-upgrade-using-islands-mode"></a><span data-ttu-id="f0326-116">겹치는 기능 업그레이드(제도 모드 사용)</span><span class="sxs-lookup"><span data-stu-id="f0326-116">Overlapping capabilities upgrade (using Islands mode)</span></span>

<span data-ttu-id="f0326-117">겹치는 기능 업그레이드 옵션의 경우:</span><span class="sxs-lookup"><span data-stu-id="f0326-117">For the overlapping capabilities upgrade option:</span></span>

- <span data-ttu-id="f0326-118">전체 조직에 대해 빠른 업그레이드를 할 수 있는 경우 이 옵션을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="f0326-118">Consider this option if you can do a fast upgrade for your overall organization.</span></span>  <span data-ttu-id="f0326-119">두 클라이언트를 모두 실행하는 최종 사용자에게 혼동이 발생할 수 있는 위험이 있는 경우 두 클라이언트를 모두 실행해야 하는 기간을 최소화할 수 있는 것이 가장 최선입니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-119">Since there is potential risk of confusion for end users with running both clients, it’s best if you can minimize the time period during which users must run both clients.</span></span> <span data-ttu-id="f0326-120">사용자가 두 클라이언트를 모두 실행하도록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-120">You should ensure your users know to run both clients.</span></span>

- <span data-ttu-id="f0326-121">이 옵션은 바로 사용할 수 있는 모델로, Teams 라이선스 또는 라이선스를 할당하는 Teams 관리자 작업을 Microsoft 365 Office 365 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-121">This option is the out-of-the box model, and doesn’t require administrator action to get started with Teams except to assign the Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="f0326-122">사용자가 이미 online에 비즈니스용 Skype 경우 이 모델에 이미 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-122">If your users already have Skype for Business Online, you may already be in this model.</span></span>

- <span data-ttu-id="f0326-123">겹치는 기능 모드에서 겹치고 TeamsOnly로 이동하는 것이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-123">It can be challenging getting out of overlapping capabilities mode and moving to TeamsOnly.</span></span> <span data-ttu-id="f0326-124">업그레이드된 사용자는 해당 사용자만 Teams 통신하기 때문에 해당 사용자와 통신하는 조직의 다른 모든 사용자는 해당 사용자를 사용하여 Teams.</span><span class="sxs-lookup"><span data-stu-id="f0326-124">Because upgraded users only communicate via Teams, any other user in the organization communicating with that user must be using Teams.</span></span>  <span data-ttu-id="f0326-125">사용자를 사용하지 않은 경우 Teams 메시지에 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-125">If you have users that have not started using Teams, they will be exposed to missing messages.</span></span> <span data-ttu-id="f0326-126">또한 사용자가 온라인에서 TeamsOnly 사용자를 볼 수 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="f0326-126">Furthermore, they won’t see the TeamsOnly users online in Skype for Business.</span></span> <span data-ttu-id="f0326-127">일부 조직에서는 이를 방지하기 위해 테넌트 전역 정책을 사용하여 테넌트 전체 업그레이드를 수행하기로 하지만, 모든 사용자가 업그레이드할 준비가 될 때까지 기다리는 것뿐만 아니라 선행 계획이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-127">Some organizations choose to do a tenant-wide upgrade using the Tenant global policy to avoid this, however that requires upfront planning as well as waiting until all users are ready to be upgraded.</span></span>


## <a name="a-select-capabilities-upgrade-for-an-organization-that-has-not-yet-started-using-teams"></a><span data-ttu-id="f0326-128">아직 사용이 시작되지 않은 조직의 선택 기능 업그레이드 Teams</span><span class="sxs-lookup"><span data-stu-id="f0326-128">A select capabilities upgrade for an organization that has not yet started using Teams</span></span>

<span data-ttu-id="f0326-129">조직에 아직 활성 사용자가 Teams 경우 첫 번째 단계는 TeamsUpgradePolicy에 대한 기본 테넌트 전체 정책을 SfbWithTeamsCollab과 같은 비즈니스용 Skype 모드 중 하나로 설정하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-129">If your organization does not yet have any active users in Teams, the first step is to set the default tenant-wide policy for TeamsUpgradePolicy to one of the Skype for Business modes, for example, SfbWithTeamsCollab.</span></span>  <span data-ttu-id="f0326-130">아직 사용이 시작되지 않은 Teams 동작의 차이를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-130">Users who have not yet started using Teams won’t notice any difference in behavior.</span></span> <span data-ttu-id="f0326-131">그러나 테넌트 수준에서 이 정책을 설정하면 사용자를 TeamsOnly 모드로 업그레이드할 수 있으며 업그레이드된 사용자가 업그레이드되지 않은 사용자와 계속 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-131">However, setting this policy at the tenant level makes it possible to start upgrading users to TeamsOnly mode, and ensures that the upgraded users can still communicate with non-upgraded users.</span></span>  <span data-ttu-id="f0326-132">파일럿 사용자를 확인한 후 TeamsOnly로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-132">Once you have identified your pilot users you can upgrade them to TeamsOnly.</span></span>  <span data-ttu-id="f0326-133">이러한 사용자가 On-Premises인 경우 Move-CsUser를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-133">If they are on-premises, use Move-CsUser.</span></span> <span data-ttu-id="f0326-134">온라인이면 Grant-CsTeamsUpgradePolicy를 사용하여 TeamsOnly 모드를 할당하기만 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-134">If they are online, simply assign them TeamsOnly mode by using Grant-CsTeamsUpgradePolicy.</span></span> <span data-ttu-id="f0326-135">기본적으로 이러한 비즈니스용 Skype 사용자가 예약한 모든 모임은 기본적으로 Teams.</span><span class="sxs-lookup"><span data-stu-id="f0326-135">By default, any Skype for Business meetings scheduled by these users will be migrated to Teams.</span></span>

<span data-ttu-id="f0326-136">주요 명령은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-136">Following are the key commands:</span></span>

1. <span data-ttu-id="f0326-137">다음과 같이 테넌트 전체 기본값을 모드 SfbWithTeamsCollab으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-137">Set the tenant-wide default to mode SfbWithTeamsCollab as follows:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -PolicyName SfbWithTeamsCollab -Global
   ```

2. <span data-ttu-id="f0326-138">다음과 같이 파일럿 사용자를 TeamsOnly로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-138">Upgrade the pilot users to TeamsOnly as follows:</span></span>

   - <span data-ttu-id="f0326-139">온라인인 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="f0326-139">For a user who is online:</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $username 
     ```

   - <span data-ttu-id="f0326-140">프레미스에 있는 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="f0326-140">For a user who is on-premises:</span></span>

     ```PowerShell
     Move-CsUser -identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
     ```

<span data-ttu-id="f0326-141">참고</span><span class="sxs-lookup"><span data-stu-id="f0326-141">Notes</span></span>
 
- <span data-ttu-id="f0326-142">테넌트 전체 정책을 SfbWithTeamsCollab으로 설정하는 대신 SfbWithTeamsCollabAndMeetings로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-142">Instead of setting the tenant-wide policy to SfbWithTeamsCollab, you could set it to SfbWithTeamsCollabAndMeetings.</span></span> <span data-ttu-id="f0326-143">이렇게 하면 모든 사용자가 모든 새 모임을 예약할 Teams.</span><span class="sxs-lookup"><span data-stu-id="f0326-143">This causes all users to schedule all new meetings in Teams.</span></span>
- <span data-ttu-id="f0326-144">`Move-CsUser` 는 는 프레미스 도구의 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-144">`Move-CsUser` is a cmdlet in the on-premises tools.</span></span> <span data-ttu-id="f0326-145">스위치에는 `MoveToTeams` CU8 비즈니스용 Skype 서버 2019 또는 2015 비즈니스용 Skype 서버 2015가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-145">The `MoveToTeams` switch requires Skype for Business Server 2019 or Skype for Business Server 2015 with CU8 or later.</span></span> <span data-ttu-id="f0326-146">이전 버전을 사용하는 경우 먼저 사용자를 Online으로 비즈니스용 Skype 다음 TeamsOnly 모드를 해당 사용자에게 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-146">If you are using a prior version, you can first move the user to Skype for Business Online, and then grant TeamsOnly mode to that user.</span></span>
- <span data-ttu-id="f0326-147">기본적으로 비즈니스용 Skype 모임은 TeamsOnly 모드로 업그레이드하거나 SfbWithTeamsCollabAndMeetings 모드를 할당할 때 Teams 모임으로 마이그레이션됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-147">By default, Skype for Business meetings are migrated to Teams when upgrading to TeamsOnly mode or when assigning SfbWithTeamsCollabAndMeetings mode.</span></span>  

> [!NOTE]
> <span data-ttu-id="f0326-148">Microsoft는 예정된 온라인 사용 중지에 대비하여 비즈니스용 Skype 조직이 조직으로 이동하는 Teams 간소화할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-148">In preparation for the upcoming retirement of Skype for Business Online, Microsoft will be simplifying how organizations move to Teams in the near future.</span></span> <span data-ttu-id="f0326-149">사용자를온-프레미스에서 Teams 이동하는 경우 이제 더 이상 전환을 지정하여 사용자를 프레미스에서 `-MoveToTeams` TeamsOnly로 직접 이동하도록 지정할 필요는 `Move-CsUser` 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-149">When moving a user from on-premises to Teams, it will soon no longer be required to specify the `-MoveToTeams` switch in `Move-CsUser` to move users directly from on-premises to TeamsOnly.</span></span> <span data-ttu-id="f0326-150">현재 이 스위치가 지정되지 않은 경우 사용자는 온라인에서 비즈니스용 Skype 서버 온라인으로 비즈니스용 Skype 전환하고 해당 모드는 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-150">Currently if this switch is not specified, users transition from being homed in Skype for Business Server on-premises to Skype for Business Online, and their mode remains unchanged.</span></span> <span data-ttu-id="f0326-151">사용이 중지된 후 사용자를 클라우드로 이동하면 사용자가 TeamsOnly 모드가 자동으로 할당되고, 스위치가 실제로 지정되어 있는지 여부에 관계없이 를 Teams 모임으로 자동 `Move-CsUser` `-MoveToTeams switch had been specified` 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-151">After retirement, when moving a user from on-premises to the cloud with `Move-CsUser`, users will automatically be assigned TeamsOnly mode and their meetings from on-premises will be automtically converted to Teams meetings, just as if the `-MoveToTeams switch had been specified`, regardless of whether the switch is actually specified.</span></span> <span data-ttu-id="f0326-152">2021년 7월 31일의 실제 사용 중지 전에 이 기능을 릴리스할 것으로 예상됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-152">We expect to release this functionality before the actual retirement of July 31, 2021.</span></span>


<span data-ttu-id="f0326-153">아래 다이어그램에서는 이전 사용이 없는 조직에 대한 선택 기능 업그레이드의 개념적 단계를 Teams.</span><span class="sxs-lookup"><span data-stu-id="f0326-153">The diagram below shows the conceptual phases of select capabilities upgrade for an organization with no prior usage of Teams.</span></span> <span data-ttu-id="f0326-154">막대의 높이는 사용자 수를 나타 내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-154">The height of the bars represents number of users.</span></span> <span data-ttu-id="f0326-155">업그레이드의 모든 단계에서 모든 사용자가 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-155">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="f0326-156">비즈니스용 Skype 사용자가 Interop을 사용하여 TeamsOnly 사용자와 통신하고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-156">Skype for Business users communicate with TeamsOnly users using Interop, and vice versa.</span></span> <span data-ttu-id="f0326-157">아일랜드 모드의 사용자는 두 클라이언트를 모두 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-157">Users in Islands mode must be sure to run both clients.</span></span>

![이전에 사용되지 않습니다. 선택 기능 업그레이드를 보여주는 다이어그램 Teams](media/teams-upgrade-1.png)


## <a name="a-select-capabilities-upgrade-for-an-organization-that-is-already-using-teams-in-islands-mode"></a><span data-ttu-id="f0326-159">아일랜드 모드에서 이미 Teams 조직에 대한 선택 기능 업그레이드</span><span class="sxs-lookup"><span data-stu-id="f0326-159">A select capabilities upgrade for an organization that is already using Teams in Islands mode</span></span>

<span data-ttu-id="f0326-160">조직의 일부 사용자가 섬 모드에서 Teams 사용하는 경우 기존 사용자에서 기능을 제거하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-160">If some users in your organization are actively using Teams in Islands mode, you probably do not want to remove functionality from existing users.</span></span> <span data-ttu-id="f0326-161">따라서 테넌트 전체 정책을 변경하기 전에 추가 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-161">Therefore, an extra step is required before changing the tenant-wide policy.</span></span> <span data-ttu-id="f0326-162">이 솔루션은 테넌트 전체 정책을 SfbWithTeamsCollab으로 설정하기 전에 이러한 기존 활성 Teams 사용자를 제도 모드로 "할아버지"하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-162">The solution is to “grandfather” these existing active Teams users into Islands mode, before setting the tenant-wide policy to SfbWithTeamsCollab.</span></span>  <span data-ttu-id="f0326-163">이 경우 위에서와 같은 배포를 진행할 수 있습니다. 그러나 TeamsOnly로 이동하는 두 개의 사용자 그룹이 있습니다. 즉, 현재 활동이 Teams 사용자는 아일랜드 모드이고 나머지 사용자는 SfbWithTeamsCollab 모드로 전환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-163">Once you’ve done that, you can proceed with deployment as above, however, you’ll have two groups of users who are moving to TeamsOnly:  the users who were active in Teams will be in Islands mode, and the remaining users will be in SfbWithTeamsCollab mode.</span></span> <span data-ttu-id="f0326-164">이러한 사용자를 TeamsOnly 모드로 점진적으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-164">You can progressively move these users to TeamsOnly mode.</span></span>

1. <span data-ttu-id="f0326-165">다음과 같이 Teams 사용자를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-165">Find users who are active in Teams as follows:</span></span>

   1. <span data-ttu-id="f0326-166">관리 Microsoft 365 왼쪽 탐색에서 보고서로 이동한 다음 사용량으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-166">From the Microsoft 365 admin center, in the left-hand navigation, go to Reports, and then Usage.</span></span> 
   2. <span data-ttu-id="f0326-167">"보고서 선택" 드롭다운에서 Microsoft Teams 선택한 다음 사용자 활동을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-167">In the “Select a report” dropdown, choose Microsoft Teams, and then User Activity.</span></span> <span data-ttu-id="f0326-168">이렇게 하면 내보낼 수 있는 사용자 테이블이 Teams.</span><span class="sxs-lookup"><span data-stu-id="f0326-168">This will provide an exportable table of users who have been active in Teams.</span></span> 
   3. <span data-ttu-id="f0326-169">내보내기, Excel 열고 필터를 클릭하여 활성 상태인 사용자만 표시하려면 Teams.</span><span class="sxs-lookup"><span data-stu-id="f0326-169">Click Export, open Excel, and filter to show only the users who are active in Teams.</span></span>

2. <span data-ttu-id="f0326-170">1단계에 Teams 각 활성 사용자에 대해 원격 PowerShell에서 섬 모드를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-170">For each active Teams user found in step 1, assign them Islands mode in remote PowerShell.</span></span> <span data-ttu-id="f0326-171">이렇게 하면 다음 단계로 이동하여 사용자 환경을 변경하지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-171">This allows you to go to the next step, and ensures you don’t change the user experience.</span></span>  

   ```PowerShell
   $users=get-content “C:\MyPath\users.txt” 
    foreach ($user in $users){ 
    Grant-CsTeamsUpgradePolicy -identity $user -PolicyName Islands} 
   ```

3. <span data-ttu-id="f0326-172">테넌트 전체 정책을 SfbWithTeamsCollab으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-172">Set the tenant-wide policy to SfbWithTeamsCollab:</span></span>

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Global -PolicyName SfbWithTeamsCollab 
   ```

4. <span data-ttu-id="f0326-173">선택한 사용자를 TeamsOnly 모드로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-173">Upgrade selected users to TeamsOnly mode.</span></span> <span data-ttu-id="f0326-174">아일랜드 모드 또는 SfbWithTeamsCollab 모드에서 사용자를 업그레이드하도록 선택할 수 있습니다. 먼저 아일랜드 모드에서 사용자를 업그레이드하는 우선 순위를 지정하여 사용자가 섬 모드에 있을 때 발생할 수 있는 혼동 가능성을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-174">You can choose to upgrade either users in Islands mode or SfbWithTeamsCollab mode, although you might want to prioritize upgrading the users in Islands mode first to minimize the potential for confusion that can arise when users are in Islands mode.</span></span>   

   <span data-ttu-id="f0326-175">온라인에 비즈니스용 Skype 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="f0326-175">For users homed in Skype for Business Online:</span></span>  

   ```PowerShell
   Grant-CsTeamsUpgradePolicy -Identity $user -PolicyName UpgradeToTeams 
   ```

   <span data-ttu-id="f0326-176">프레미스에 비즈니스용 Skype 서버 사용자의 경우:</span><span class="sxs-lookup"><span data-stu-id="f0326-176">For users homed in Skype for Business Server on-premises:</span></span>  

   ```PowerShell
   Move-CsUser -Identity $user -Target sipfed.online.lync.com -MoveToTeams -credential $cred 
   ```

<span data-ttu-id="f0326-177">아래 다이어그램에서는 시작 시 활성 Islands 사용자가 있는 선택 기능 전환의 개념 단계를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-177">The diagram below shows the conceptual phases of a select capabilities transition in which there are active Islands users at the start.</span></span> <span data-ttu-id="f0326-178">막대의 높이는 사용자 수를 나타 내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-178">The height of the bars represents the number of users.</span></span> <span data-ttu-id="f0326-179">업그레이드의 모든 단계에서 모든 사용자가 서로 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-179">During any phase of the upgrade, all users can communicate with each other.</span></span>  <span data-ttu-id="f0326-180">비즈니스용 Skype 사용자가 Interop을 사용하여 TeamsOnly 사용자와 통신하고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="f0326-180">Skype for Business users communicate with TeamsOnly users using interop, and vice versa.</span></span> 


![아일랜드 모드에서 활성 사용자와 함께 선택한 기능 업그레이드를 보여주는 다이어그램](media/teams-upgrade-2.png)

   



## <a name="related-links"></a><span data-ttu-id="f0326-182">관련 링크</span><span class="sxs-lookup"><span data-stu-id="f0326-182">Related links</span></span>

[<span data-ttu-id="f0326-183">조직과 함께 Teams 조직에 대한 마이그레이션 및 상호 비즈니스용 Skype</span><span class="sxs-lookup"><span data-stu-id="f0326-183">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="f0326-184">비즈니스용 Skype 서버 및 Microsoft 365 Office 365</span><span class="sxs-lookup"><span data-stu-id="f0326-184">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="f0326-185">온-프레미스와 클라우드 간에 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="f0326-185">Move users between on-premises and cloud</span></span>](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="f0326-186">공존 및 업그레이드 설정 설정</span><span class="sxs-lookup"><span data-stu-id="f0326-186">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="f0326-187">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="f0326-187">Grant-CsTeamsUpgradePolicy</span></span>](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="f0326-188">MMS(모임 마이그레이션 서비스) 사용</span><span class="sxs-lookup"><span data-stu-id="f0326-188">Using the Meeting Migration Service (MMS)</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
