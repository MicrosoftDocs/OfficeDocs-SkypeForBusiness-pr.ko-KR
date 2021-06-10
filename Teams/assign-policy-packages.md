---
title: 사용자 및 그룹에 정책 패키지 할당
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
description: 정책 패키지를 사용자 및 그룹에 할당하는 다양한 방법을 Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 820cc280e7168dee5a0e059005a1b7e6cebf5ff1
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856427"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="b9e97-103">사용자 및 그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b9e97-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="b9e97-104">이 문서에서는 사용자 및 그룹에 정책 패키지를 할당하는 다양한 방법을 Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b9e97-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="b9e97-105">읽기 전에 에서 정책 할당을 Teams [을 읽어야 합니다.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b9e97-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b9e97-106">사용자 지정 정책 패키지 할당을 받으려면 각 사용자에게 고급 통신 추가 기능이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-106">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="b9e97-107">자세한 내용은 [Microsoft Teams를 위한 고급 통신 추가 기능](/microsoftteams/teams-add-on-licensing/advanced-communications)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9e97-107">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="b9e97-108">사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b9e97-108">Assign a policy package to users</span></span>

<span data-ttu-id="b9e97-109">Teams 정책 패키지는 조직에서 동일하거나 유사한 역할을 하는 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-109">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="b9e97-110">각 정책 패키지는 사용자 역할을 중심으로 설계하며 해당 역할에 대한 일반적인 활동을 지원하는 미리 정의된 정책 및 정책 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-110">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="b9e97-111">정책 패키지의 몇 가지 예로는 교육(교사) 패키지 및 Healthcare(임상 작업자) 패키지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-111">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="b9e97-112">자세한 내용은 에서 정책 [패키지 관리를 Teams.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="b9e97-112">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="b9e97-113">한 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b9e97-113">Assign a policy package to one user</span></span>

1. <span data-ttu-id="b9e97-114">관리 센터의 왼쪽 Microsoft Teams 사용자로 이동한 다음 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-114">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="b9e97-115">사용자의 페이지에서 정책 **을** 선택한 다음 정책 패키지 옆에 **있는** **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9e97-115">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="b9e97-116">정책 **패키지** 할당 창에서 할당할 패키지를 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9e97-116">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Teams 패키지 할당에 대한 관리자 센터 스크린샷](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="b9e97-118">여러 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b9e97-118">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="b9e97-119">관리 센터의 왼쪽 Microsoft Teams 정책 패키지로 이동한 다음, 패키지 이름의 왼쪽을 클릭하여 할당할 정책 패키지를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="b9e97-119">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="b9e97-120">**사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-120">Select **Manage users**.</span></span>
3. <span data-ttu-id="b9e97-121">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="b9e97-121">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b9e97-122">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-122">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="b9e97-123">사용자 추가가 완료되면 저장 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9e97-123">When you're finished adding users, select **Save**.</span></span>

![Teams 관리 센터 스크린샷을 사용하여 여러 사용자에게 정책 패키지 할당](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="b9e97-125">그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b9e97-125">Assign a policy package to a group</span></span>

<span data-ttu-id="b9e97-126">그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-126">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="b9e97-127">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-127">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="b9e97-128">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-128">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="b9e97-129">최대 50,000명까지의 그룹에 대해 그룹에 정책 패키지 할당을 할당하는 것이 좋습니다. 하지만 더 큰 그룹에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-129">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="b9e97-130">정책 패키지를 할당하면 그룹에 즉시 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-130">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="b9e97-131">그러나 그룹의 구성원에게 정책 할당의 전파는 백그라운드 작업으로 수행됩니다. 그룹 크기에 따라 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-131">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="b9e97-132">그룹에서 정책이 부가되지 않은 경우나 구성원이 그룹에 추가되거나 그룹에서 제거될 때도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-132">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9e97-133">시작하기 전에 (우선 순위[규칙)](assign-policies-users-and-groups.md#precedence-rules)및 (그룹 할당[순위)를](assign-policies-users-and-groups.md#group-assignment-ranking)이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-133">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="b9e97-134">이 문서의 앞부분에 있는[](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)개념(그룹에 정책 할당에 대해 알아야 할 것)을 읽고 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-134">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="b9e97-135">관리 센터의 사용자 그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b9e97-135">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="b9e97-136">Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-136">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="b9e97-137">왼쪽 탐색에서 정책 패키지 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-137">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="b9e97-138">그룹 정책 할당 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-138">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="b9e97-139">그룹 **추가를 선택한** 다음 정책 패키지 할당에서 그룹 창을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-139">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="b9e97-140">a.</span><span class="sxs-lookup"><span data-stu-id="b9e97-140">a.</span></span> <span data-ttu-id="b9e97-141">정책 패키지를 할당할 그룹을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-141">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="b9e97-142">b.</span><span class="sxs-lookup"><span data-stu-id="b9e97-142">b.</span></span> <span data-ttu-id="b9e97-143">정책 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-143">Select a policy package.</span></span>

    <span data-ttu-id="b9e97-144">c.</span><span class="sxs-lookup"><span data-stu-id="b9e97-144">c.</span></span> <span data-ttu-id="b9e97-145">각 정책 유형에 대한 순위를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-145">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="b9e97-146">d.</span><span class="sxs-lookup"><span data-stu-id="b9e97-146">d.</span></span> <span data-ttu-id="b9e97-147">적용 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b9e97-147">Select **Apply**.</span></span>

![그룹 정책 할당을 보여줍니다.](media/group-pkg-assignment.png)

5. <span data-ttu-id="b9e97-149">특정 정책 유형에 대한 순위를 관리하기 위해 특정 정책 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-149">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="b9e97-150">정책 패키지를 그룹에 다시 할당하려면 먼저 그룹 정책 할당을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-150">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="b9e97-151">그런 다음 위의 단계를 수행하여 그룹에 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-151">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="b9e97-152">PowerShell 작업</span><span class="sxs-lookup"><span data-stu-id="b9e97-152">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="b9e97-153">PowerShell Teams</span><span class="sxs-lookup"><span data-stu-id="b9e97-153">Get the Teams PowerShell module</span></span>

<span data-ttu-id="b9e97-154">단계별 지침은 [PowerShell Teams 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="b9e97-154">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="b9e97-155">사용자 그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b9e97-155">Assign a policy package to a group of users</span></span>

<span data-ttu-id="b9e97-156">[Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet을 사용하여 그룹에 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-156">Use the [Grant-CsGroupPolicyPackageAssignment](/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="b9e97-157">개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-157">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="b9e97-158">정책 패키지를 할당할 때 정책 패키지의 각 정책 유형에 대해[(그룹](assign-policies-users-and-groups.md#group-assignment-ranking)할당 순위)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-158">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="b9e97-159">이 예제에서는 TeamsAppSetupPolicy 및 TeamsMeetingBroadcastPolicy에 대한 할당 순위가 1이고 TeamsMeetingPolicy에 대한 2 순위가 있는 그룹에 Education_Teacher 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-159">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="b9e97-160">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b9e97-160">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="b9e97-161">일괄 처리 정책 패키지 할당을 사용하면 스크립트를 사용하지 않고도 동시에 대규모 사용자 집합에 정책 패키지를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-161">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="b9e97-162">[New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 사용자 일괄 처리 및 할당하려는 정책 패키지를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-162">You use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="b9e97-163">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="b9e97-164">그런 다음 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 과제의 진행률 및 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-164">You can then use the [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="b9e97-165">개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-165">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="b9e97-166">사용자의 SIP 주소는 종종 UPN(사용자 주체 이름) 또는 전자 메일 주소와 동일한 값을 지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-166">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="b9e97-167">사용자가 UPN 또는 전자 메일을 사용하여 지정되지만 해당 SIP 주소와 다른 값이 있는 경우 사용자에게 정책 할당이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-167">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="b9e97-168">일괄 처리에 중복 사용자가 포함된 경우 처리 전에 일괄 처리에서 중복된 사용자가 제거되고 일괄 처리에 남아 있는 고유 사용자에게만 상태가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-168">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="b9e97-169">일괄 처리에는 최대 5,000명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-169">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="b9e97-170">최상의 결과를 얻기 위해 한 번에 몇 개 이상의 일괄 처리를 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-170">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="b9e97-171">더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-171">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="b9e97-172">PowerShell Teams 사용</span><span class="sxs-lookup"><span data-stu-id="b9e97-172">Use the Teams PowerShell module</span></span>

<span data-ttu-id="b9e97-173">다음을 실행하여 Microsoft Teams [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 모듈을 설치합니다(아직 없는 경우).</span><span class="sxs-lookup"><span data-stu-id="b9e97-173">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="b9e97-174">버전 1.0.5 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-174">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b9e97-175">다음을 실행하여 Teams 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-175">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="b9e97-176">메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-176">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="b9e97-177">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b9e97-177">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="b9e97-178">이 예제에서는 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 사용자 일괄 처리에 Education_PrimaryStudent 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-178">In this example, we use the [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="b9e97-179">일괄 처리 할당의 상태 보기</span><span class="sxs-lookup"><span data-stu-id="b9e97-179">See the status of a batch assignment</span></span>

<span data-ttu-id="b9e97-180">다음을 실행하여 일괄 처리 할당의 상태를 얻습니다. 여기서 OperationId는 주어진 일괄 처리에 대해 cmdlet에서 반환되는 작업 ```New-CsBatchPolicyAssignmentOperation``` ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-180">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="b9e97-181">출력에서 오류가 발생한 것으로 표시되는 경우 다음을 실행하여 속성에 있는 오류에 대한 자세한 정보를 ```UserState``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="b9e97-181">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="b9e97-182">자세한 내용은 [Get-CsBatchPolicyAssignmentOperation 을 참조합니다.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="b9e97-182">To learn more, see [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b9e97-183">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b9e97-183">Related topics</span></span>

- [<span data-ttu-id="b9e97-184">정책으로 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="b9e97-184">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="b9e97-185">정책 패키지 관리 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9e97-185">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="b9e97-186">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="b9e97-186">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="b9e97-187">Teams 정책 할당 - 시작</span><span class="sxs-lookup"><span data-stu-id="b9e97-187">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)
