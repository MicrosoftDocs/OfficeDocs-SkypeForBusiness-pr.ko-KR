---
title: 사용자 및 그룹에 정책 할당
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft Teams의 사용자 및 그룹에 정책을 할당하는 다양한 방법에 대해 알아보습니다.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 6b0db8c3da93e561bf374b32d08750d705ded8a2
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574354"
---
# <a name="assign-policies-to-users-and-groups"></a><span data-ttu-id="c5d22-103">사용자 및 그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c5d22-103">Assign policies to users and groups</span></span>

<span data-ttu-id="c5d22-104">이 문서에서는 Microsoft Teams의 사용자 및 그룹에 정책을 할당하는 다양한 방법을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-104">This article reviews the different ways to assign policies to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="c5d22-105">읽기 전에 Teams에서 정책 할당 - 시작 을 [읽어야 합니다.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c5d22-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="c5d22-106">개별 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c5d22-106">Assign a policy to individual users</span></span>

<span data-ttu-id="c5d22-107">다음 단계에 따라 개별 사용자 또는 소수의 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-107">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="c5d22-108">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="c5d22-108">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="c5d22-109">사용자에게 정책을 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="c5d22-109">To assign a policy to a user:</span></span>

1. <span data-ttu-id="c5d22-110">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자로** 이동한 다음 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-110">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="c5d22-111">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 다음 설정 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d22-111">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="c5d22-112">할당할 정책을 선택한 다음 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d22-112">Select the policy you want to assign, and then select **Apply**.</span></span>

![Teams 관리 센터의 사용자에게 정책 할당](media/assign-policy-user.png)

<span data-ttu-id="c5d22-114">또는 다음을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-114">Or, you can also do the following:</span></span>

1. <span data-ttu-id="c5d22-115">Microsoft Teams 관리 센터의 왼쪽 탐색에서 정책 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-115">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="c5d22-116">정책 이름의 왼쪽을 클릭하여 할당할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-116">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="c5d22-117">**사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-117">Select **Manage users**.</span></span>
4. <span data-ttu-id="c5d22-118">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="c5d22-118">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="c5d22-119">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-119">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="c5d22-120">사용자 추가가 완료되면 적용 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d22-120">When you're finished adding users, select **Apply**.</span></span>

![두 번째 방법을 통해 Teams 관리 센터의 사용자에게 정책 할당](media/assign-policy-user2.png)

### <a name="use-powershell"></a><span data-ttu-id="c5d22-122">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="c5d22-122">Use PowerShell</span></span>

<span data-ttu-id="c5d22-123">각 정책 유형에는 관리하기 위한 자체 cmdlet 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-123">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="c5d22-124">특정 정책 유형에 ```Grant-``` 대한 cmdlet을 사용하여 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-124">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="c5d22-125">예를 들어 cmdlet을 사용하여 사용자에게 Teams 모임 정책을 ```Grant-CsTeamsMeetingPolicy``` 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-125">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="c5d22-126">이러한 cmdlet은 Teams PowerShell 모듈에 포함되어 있으며 [비즈니스용 Skype cmdlet](https://docs.microsoft.com/powershell/skype)참조에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-126">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype).</span></span>

 <span data-ttu-id="c5d22-127">[Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 공개 릴리스(아직 없는 경우)를 다운로드하여 설치한 다음 다음을 실행하여 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-127">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="c5d22-128">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-128">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="c5d22-129">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-129">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="c5d22-130">이 예제에서는 학생 모임 정책이라는 Teams 모임 정책을 Reda라는 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-130">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="c5d22-131">자세한 내용은 [PowerShell을 통해 정책 관리 를 읽어보아야 합니다.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="c5d22-131">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="c5d22-132">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c5d22-132">Assign a policy to a group</span></span>

<span data-ttu-id="c5d22-133">그룹에 정책 할당을 사용하면 보안 그룹 또는 메일 그룹과 같은 사용자 그룹에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-133">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="c5d22-134">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-134">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="c5d22-135">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-135">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="c5d22-136">그룹에 대한 정책 할당은 최대 50,000명까지의 그룹에 권장되지만 더 큰 그룹에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-136">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="c5d22-137">정책을 할당하면 그룹에 즉시 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-137">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="c5d22-138">그러나 그룹의 구성원에게 정책 할당의 전파는 백그라운드 작업으로 수행됩니다. 그룹 크기에 따라 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-138">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="c5d22-139">그룹에서 정책이 부가되지 않은 경우나 구성원이 그룹에 추가되거나 그룹에서 제거될 때도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-139">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="c5d22-140">그룹 정책 할당은 그룹의 직접 구성원인 사용자에게만 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-140">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="c5d22-141">할당은 중첩된 그룹의 구성원에게 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-141">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="c5d22-142">그룹에 정책 할당에 대해 알아야 할 정보</span><span class="sxs-lookup"><span data-stu-id="c5d22-142">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="c5d22-143">시작하기 전에 우선 순위 규칙 및 그룹 할당 순위를 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-143">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="c5d22-144">우선 순위 규칙</span><span class="sxs-lookup"><span data-stu-id="c5d22-144">Precedence rules</span></span>

<span data-ttu-id="c5d22-145">주어진 정책 형식의 경우 사용자의 유효 정책은 다음에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-145">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="c5d22-146">사용자에게 직접 할당되는 정책은 그룹에 할당된 동일한 유형의 다른 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-146">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="c5d22-147">즉, 사용자가 지정된 형식의 정책을 직접 할당하는 경우 해당 사용자는 그룹에서 동일한 형식의 정책을 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-147">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="c5d22-148">즉, 사용자에게 직접 할당된 지정된 형식의 정책이 있는 경우 그룹에서 동일한 형식의 정책을 상속하려면 먼저 사용자로부터 해당 정책을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-148">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="c5d22-149">사용자에게 직접 할당된 정책이 없고 두 개 이상의 그룹의 구성원이고 각 그룹에 할당된 동일한 유형의 정책이 있는 경우 사용자는 가장 높은 순위를 가지는 그룹 할당의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-149">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="c5d22-150">사용자가 정책이 할당된 그룹의 구성원이 아닌 경우 해당 정책 유형에 대한 전역(Org-wide default) 정책이 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-150">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="c5d22-151">사용자의 유효 정책은 다음 규칙에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-151">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="c5d22-152">사용자가 정책에 할당된 그룹에 추가되거나 제거될 때</span><span class="sxs-lookup"><span data-stu-id="c5d22-152">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="c5d22-153">그룹에서 정책이 부가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-153">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="c5d22-154">사용자에게 직접 할당된 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-154">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="c5d22-155">그룹 할당 순위</span><span class="sxs-lookup"><span data-stu-id="c5d22-155">Group assignment ranking</span></span>

<span data-ttu-id="c5d22-156">그룹에 정책을 할당할 때 그룹 할당에 대한 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-156">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="c5d22-157">이 정책은 사용자가 두 개 이상의 그룹의 구성원이고 각 그룹에 동일한 유형의 정책이 할당된 경우 사용자가 효과적인 정책으로 상속해야 하는 정책을 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-157">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="c5d22-158">그룹 할당 순위는 동일한 유형의 다른 그룹 할당과 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-158">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="c5d22-159">예를 들어 두 그룹에 호출 정책을 할당하는 경우 한 할당의 순위를 1로, 다른 할당은 2로, 1은 가장 높은 순위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-159">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="c5d22-160">그룹 할당 순위는 상속과 관련하여 다른 그룹 멤버 자격보다 더 중요하거나 관련성이 높은 그룹 멤버 자격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-160">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="c5d22-161">예를 들어 직원 저장소 및 스토어 관리자의 두 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-161">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="c5d22-162">두 그룹에는 각각 Teams 호출 정책, 스토어 직원 호출 정책 및 저장소 관리자 호출 정책이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-162">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="c5d22-163">두 그룹에 있는 저장소 관리자의 경우 관리자 역할은 직원 역할보다 관련성이 높기 때문에 Store Managers 그룹에 할당된 호출 정책은 순위가 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-163">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="c5d22-164">그룹</span><span class="sxs-lookup"><span data-stu-id="c5d22-164">Group</span></span> |<span data-ttu-id="c5d22-165">정책 이름을 호출하는 팀</span><span class="sxs-lookup"><span data-stu-id="c5d22-165">Teams calling policy name</span></span>  |<span data-ttu-id="c5d22-166">순위</span><span class="sxs-lookup"><span data-stu-id="c5d22-166">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="c5d22-167">Store Managers</span><span class="sxs-lookup"><span data-stu-id="c5d22-167">Store Managers</span></span>   |<span data-ttu-id="c5d22-168">스토어 관리자 호출 정책</span><span class="sxs-lookup"><span data-stu-id="c5d22-168">Store Managers Calling Policy</span></span>         |<span data-ttu-id="c5d22-169">1</span><span class="sxs-lookup"><span data-stu-id="c5d22-169">1</span></span>|
|<span data-ttu-id="c5d22-170">직원 저장</span><span class="sxs-lookup"><span data-stu-id="c5d22-170">Store Employees</span></span>    |<span data-ttu-id="c5d22-171">직원 호출 정책 저장</span><span class="sxs-lookup"><span data-stu-id="c5d22-171">Store Employees Calling Policy</span></span>      |<span data-ttu-id="c5d22-172">2</span><span class="sxs-lookup"><span data-stu-id="c5d22-172">2</span></span>|

<span data-ttu-id="c5d22-173">순위를 지정하지 않으면 정책 할당에 가장 낮은 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-173">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="c5d22-174">Teams 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="c5d22-174">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="c5d22-175">현재 Microsoft Teams 관리 센터를 사용하는 그룹에 대한 정책 할당은 Teams 호출 정책, Teams 호출 공원 정책, Teams 정책, Teams 라이브 이벤트 정책, Teams 모임 정책 및 Teams 메시징 정책에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-175">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="c5d22-176">다른 정책 형식의 경우 PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-176">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="c5d22-177">Microsoft Teams 관리 센터의 왼쪽 탐색에서 정책 유형 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-177">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="c5d22-178">예를 들어 모임 모임 정책  >  **으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d22-178">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="c5d22-179">그룹 정책 **할당 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-179">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="c5d22-180">그룹 **추가를 선택한** 다음  그룹화 정책 할당 창에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-180">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="c5d22-181">정책을 할당할 그룹을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-181">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="c5d22-182">그룹 할당의 순위를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-182">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="c5d22-183">할당할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-183">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="c5d22-184">적용 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d22-184">Select **Apply**.</span></span>
    
![Teams 관리 센터의 그룹에 정책 할당](media/assign-policy-group.png)

<span data-ttu-id="c5d22-186">그룹 정책 할당을 제거하려면  정책 페이지의 그룹 정책 할당 탭에서 그룹 할당을 선택한 다음 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d22-186">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="c5d22-187">그룹 할당의 순위를 변경하려면 먼저 그룹 정책 할당을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-187">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="c5d22-188">그런 다음 위의 단계를 수행하여 그룹에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-188">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="c5d22-189">PowerShell 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="c5d22-189">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="c5d22-190">현재 PowerShell을 사용하는 그룹에 대한 정책 할당은 모든 Teams 정책 유형에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-190">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="c5d22-191">지원되는 정책 유형 목록에 대한 [New-CsGroupPolicyAssignment를](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5d22-191">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="c5d22-192">Microsoft Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="c5d22-192">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="c5d22-193">단계별 지침은 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="c5d22-193">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="c5d22-194">사용자 그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c5d22-194">Assign a policy to a group of users</span></span>

<span data-ttu-id="c5d22-195">[New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-195">Use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="c5d22-196">개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-196">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="c5d22-197">이 예제에서는 할당 순위가 1인 그룹에 Retail Managers 모임 정책이라는 Teams 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-197">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="c5d22-198">그룹에 대한 정책 할당을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-198">Get policy assignments for a group</span></span>

<span data-ttu-id="c5d22-199">[Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 할당된 모든 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-199">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="c5d22-200">그룹은 정책을 할당하는 데 SIP 주소 또는 전자 메일 주소를 사용하는 경우에도 항상 그룹 ID로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-200">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="c5d22-201">이 예제에서는 특정 그룹에 할당된 모든 정책을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-201">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="c5d22-202">이 예제에서는 Teams 모임 정책이 할당된 모든 그룹을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-202">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="c5d22-203">그룹에서 정책 제거</span><span class="sxs-lookup"><span data-stu-id="c5d22-203">Remove a policy from a group</span></span>

<span data-ttu-id="c5d22-204">[Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet을 사용하여 그룹에서 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-204">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="c5d22-205">그룹에서 정책을 제거하면 해당 그룹에 할당된 동일한 유형의 다른 정책의 우선 순위가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-205">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="c5d22-206">예를 들어 순위가 2인 정책을 제거하면 순위가 3과 4인 정책이 업데이트되어 새 순위가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-206">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="c5d22-207">다음 두 표에는 이 예제가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-207">The following two tables show this example.</span></span>

<span data-ttu-id="c5d22-208">다음은 Teams 모임 정책에 대한 정책 할당 및 우선 순위 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-208">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="c5d22-209">그룹 이름</span><span class="sxs-lookup"><span data-stu-id="c5d22-209">Group name</span></span>  |<span data-ttu-id="c5d22-210">정책 이름</span><span class="sxs-lookup"><span data-stu-id="c5d22-210">Policy name</span></span>  |<span data-ttu-id="c5d22-211">순위</span><span class="sxs-lookup"><span data-stu-id="c5d22-211">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="c5d22-212">영업</span><span class="sxs-lookup"><span data-stu-id="c5d22-212">Sales</span></span>    |<span data-ttu-id="c5d22-213">판매 정책</span><span class="sxs-lookup"><span data-stu-id="c5d22-213">Sales policy</span></span>       | <span data-ttu-id="c5d22-214">1</span><span class="sxs-lookup"><span data-stu-id="c5d22-214">1</span></span>        |
|<span data-ttu-id="c5d22-215">서부 지역</span><span class="sxs-lookup"><span data-stu-id="c5d22-215">West Region</span></span>     |<span data-ttu-id="c5d22-216">서부 지역 정책</span><span class="sxs-lookup"><span data-stu-id="c5d22-216">West Region policy</span></span>         |<span data-ttu-id="c5d22-217">2</span><span class="sxs-lookup"><span data-stu-id="c5d22-217">2</span></span>         |
|<span data-ttu-id="c5d22-218">디비전</span><span class="sxs-lookup"><span data-stu-id="c5d22-218">Division</span></span>    |<span data-ttu-id="c5d22-219">분할 정책</span><span class="sxs-lookup"><span data-stu-id="c5d22-219">Division policy</span></span>         |<span data-ttu-id="c5d22-220">3</span><span class="sxs-lookup"><span data-stu-id="c5d22-220">3</span></span>         |
|<span data-ttu-id="c5d22-221">자회사</span><span class="sxs-lookup"><span data-stu-id="c5d22-221">Subsidiary</span></span>   |<span data-ttu-id="c5d22-222">자회사 정책</span><span class="sxs-lookup"><span data-stu-id="c5d22-222">Subsidiary policy</span></span>        |<span data-ttu-id="c5d22-223">4</span><span class="sxs-lookup"><span data-stu-id="c5d22-223">4</span></span>         |

<span data-ttu-id="c5d22-224">서부 지역 그룹에서 서부 지역 정책을 제거하는 경우 정책 할당 및 우선 순위는 다음과 같이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-224">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="c5d22-225">그룹 이름</span><span class="sxs-lookup"><span data-stu-id="c5d22-225">Group name</span></span>  |<span data-ttu-id="c5d22-226">정책 이름</span><span class="sxs-lookup"><span data-stu-id="c5d22-226">Policy name</span></span>  |<span data-ttu-id="c5d22-227">순위</span><span class="sxs-lookup"><span data-stu-id="c5d22-227">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="c5d22-228">영업</span><span class="sxs-lookup"><span data-stu-id="c5d22-228">Sales</span></span>    |<span data-ttu-id="c5d22-229">판매 정책</span><span class="sxs-lookup"><span data-stu-id="c5d22-229">Sales policy</span></span>       | <span data-ttu-id="c5d22-230">1</span><span class="sxs-lookup"><span data-stu-id="c5d22-230">1</span></span>        |
|<span data-ttu-id="c5d22-231">디비전</span><span class="sxs-lookup"><span data-stu-id="c5d22-231">Division</span></span>    |<span data-ttu-id="c5d22-232">분할 정책</span><span class="sxs-lookup"><span data-stu-id="c5d22-232">Division policy</span></span>         |<span data-ttu-id="c5d22-233">2</span><span class="sxs-lookup"><span data-stu-id="c5d22-233">2</span></span>         |
|<span data-ttu-id="c5d22-234">자회사</span><span class="sxs-lookup"><span data-stu-id="c5d22-234">Subsidiary</span></span>   |<span data-ttu-id="c5d22-235">자회사 정책</span><span class="sxs-lookup"><span data-stu-id="c5d22-235">Subsidiary policy</span></span>        |<span data-ttu-id="c5d22-236">3</span><span class="sxs-lookup"><span data-stu-id="c5d22-236">3</span></span>        |

<span data-ttu-id="c5d22-237">이 예제에서는 그룹에서 Teams 모임 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-237">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="c5d22-238">그룹에 대한 정책 할당 변경</span><span class="sxs-lookup"><span data-stu-id="c5d22-238">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="c5d22-239">[Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 곧 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-239">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="c5d22-240">그 동안 그룹 정책 할당을 변경하려면 그룹에서 현재 정책 할당을 제거한 다음 새 정책 할당을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-240">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="c5d22-241">그룹에 정책을 할당한 후 [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 사용하여 해당 그룹의 정책 할당을 다음과 같이 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-241">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="c5d22-242">순위 변경</span><span class="sxs-lookup"><span data-stu-id="c5d22-242">Change the ranking</span></span>
- <span data-ttu-id="c5d22-243">주어진 정책 형식의 정책 변경</span><span class="sxs-lookup"><span data-stu-id="c5d22-243">Change the policy of a given policy type</span></span>
- <span data-ttu-id="c5d22-244">주어진 정책 유형 및 순위의 정책 변경</span><span class="sxs-lookup"><span data-stu-id="c5d22-244">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="c5d22-245">이 예제에서는 그룹의 Teams 호출 공원 정책을 SupportCallPark라는 정책으로 변경하고 할당 순위를 3으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-245">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="c5d22-246">사용자에 대한 유효 정책 변경</span><span class="sxs-lookup"><span data-stu-id="c5d22-246">Change the effective policy for a user</span></span>

<span data-ttu-id="c5d22-247">정책에 직접 할당된 사용자에 대한 효과적인 정책을 변경하는 방법에 대한 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-247">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="c5d22-248">먼저 [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet과 매개 변수를 함께 사용하여 사용자와 연결된 Teams 모임 브로드캐스트 정책에 대한 세부 정보를 ```PolicySource``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-248">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="c5d22-249">출력은 사용자가 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트라는 정책보다 우선하는 Employee Events라는 Teams 모임 브로드캐스트 정책을 직접 할당했다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-249">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="c5d22-250">이제 사용자에서 Employee Events 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-250">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="c5d22-251">즉, 사용자에게 더 이상 Teams 모임 브로드캐스트 정책이 직접 할당되지 않고 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-251">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="c5d22-252">이 작업을 위해 비즈니스용 Skype PowerShell 모듈에서 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-252">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="c5d22-253">Teams PowerShell 모듈에서 다음 cmdlet을 사용하여 일괄 처리 정책 할당이 $users 사용자 목록인 대규모로 이 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="c5d22-253">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="c5d22-254">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c5d22-254">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="c5d22-255">관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="c5d22-255">Use the admin center</span></span>

<span data-ttu-id="c5d22-256">사용자에게 정책을 대량으로 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="c5d22-256">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="c5d22-257">Microsoft Teams 관리 센터의 왼쪽 탐색에서 사용자를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d22-257">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="c5d22-258">정책을 할당할 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-258">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="c5d22-259">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-259">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="c5d22-260">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-260">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="c5d22-261">설정 **편집을 선택하고** 원하는 내용을 변경한 다음 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d22-261">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="c5d22-262">정책 할당의 상태를 확인하려면 적용을 선택한 후 사용자 페이지  맨 위에  나타나는 배너에서 활동 **로그를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d22-262">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="c5d22-263">또는 Microsoft Teams 관리 센터의 왼쪽 탐색에서 대시보드로 이동한 다음 활동 로그에서 **세부** 정보 **보기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="c5d22-263">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="c5d22-264">활동 로그는 지난 30일 동안 Microsoft Teams 관리 센터를 통해 20명 이상의 사용자 일괄 처리에 대한 정책 할당을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-264">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="c5d22-265">자세한 내용은 활동 로그에서 정책 할당 [보기를 참조합니다.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="c5d22-265">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="c5d22-266">PowerShell 메서드 사용</span><span class="sxs-lookup"><span data-stu-id="c5d22-266">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="c5d22-267">현재 PowerShell을 사용하는 일괄 처리 정책 할당은 모든 Teams 정책 유형에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-267">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="c5d22-268">지원되는 정책 유형 목록은 [New-CsBatchPolicyAssignmentOperation을](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5d22-268">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="c5d22-269">일괄 처리 정책 할당을 사용하면 스크립트를 사용하지 않고도 동시에 대규모 사용자 집합에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-269">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="c5d22-270">[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 사용자 일괄 처리 및 할당하려는 정책을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-270">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="c5d22-271">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-271">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="c5d22-272">그런 다음 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 과제의 진행률 및 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-272">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="c5d22-273">개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-273">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="c5d22-274">사용자의 SIP 주소는 종종 UPN(사용자 주체 이름) 또는 전자 메일 주소와 동일한 값을 지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-274">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="c5d22-275">사용자가 UPN 또는 전자 메일을 사용하여 지정되지만 해당 SIP 주소와 다른 값이 있는 경우 사용자에게 정책 할당이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-275">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="c5d22-276">일괄 처리에 중복 사용자가 포함된 경우 처리 전에 일괄 처리에서 중복된 사용자가 제거되고 일괄 처리에 남아 있는 고유 사용자에게만 상태가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-276">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="c5d22-277">배치에는 최대 5천 명의 사용자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-277">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="c5d22-278">최상의 결과를 얻기 위해 한 번에 몇 개 이상의 일괄 처리를 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-278">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="c5d22-279">더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-279">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="c5d22-280">Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="c5d22-280">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="c5d22-281">다음을 실행하여 [Microsoft Teams PowerShell 모듈을 설치합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="c5d22-281">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="c5d22-282">버전 1.0.5 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-282">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="c5d22-283">다음을 실행하여 Teams에 연결하고 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-283">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="c5d22-284">메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-284">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="c5d22-285">Azure AD PowerShell for Graph 모듈 설치 및 연결(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="c5d22-285">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="c5d22-286">또한 Azure [AD PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 모듈(아직 없는 경우)을 다운로드하여 설치하고 조직의 사용자 목록을 검색할 수 있도록 Azure AD에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-286">You might also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="c5d22-287">다음을 실행하여 Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-287">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="c5d22-288">메시지가 표시될 때 Teams에 연결하는 데 사용한 동일한 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-288">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="c5d22-289">사용자 일괄 처리에 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="c5d22-289">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="c5d22-290">이 예제에서는 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 Users_ids.text 파일에 나열된 사용자 일괄 처리에 HR 앱 설정 정책이라는 앱 설치 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-290">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="c5d22-291">이 예제에서는 Azure AD에 연결하여 사용자 컬렉션을 검색한 다음, SIP 주소를 사용하여 지정된 사용자 일괄 처리에 새 고용 메시징 정책이라는 메시징 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-291">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="c5d22-292">일괄 처리 할당의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="c5d22-292">Get the status of a batch assignment</span></span>

<span data-ttu-id="c5d22-293">다음을 실행하여 일괄 처리 할당의 상태를 얻습니다. 여기서 OperationId는 주어진 일괄 처리에 대해 cmdlet에서 반환되는 작업 ```New-CsBatchPolicyAssignmentOperation``` ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-293">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="c5d22-294">출력에서 오류가 발생한 것으로 표시되는 경우 다음을 실행하여 속성에 있는 오류에 대한 자세한 정보를 ```UserState``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="c5d22-294">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="c5d22-295">자세한 내용은 [Get-CsBatchPolicyAssignmentOperation 을 참조합니다.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="c5d22-295">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c5d22-296">관련 항목</span><span class="sxs-lookup"><span data-stu-id="c5d22-296">Related topics</span></span>

- [<span data-ttu-id="c5d22-297">정책으로 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="c5d22-297">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="c5d22-298">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="c5d22-298">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="c5d22-299">Teams에서 정책 할당 - 시작</span><span class="sxs-lookup"><span data-stu-id="c5d22-299">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
