---
title: Teams 정책 패키지
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 정부 조직에 대한 Teams 정책 패키지를 사용 및 관리하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 41ae937323b37948c03128efd565f40c02bbd6a2
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796872"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="fba07-103">Teams 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="fba07-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="fba07-104">정책 패키지는 현재 고가 또는 DoD Microsoft 365 정부 GCC 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="fba07-105">개요</span><span class="sxs-lookup"><span data-stu-id="fba07-105">Overview</span></span>

<span data-ttu-id="fba07-106">Microsoft Teams의 [정책 패키지](manage-policy-packages.md)는 조직에서 유사한 역할을 가진 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="fba07-107">정책 패키지는 정책 관리 시 이를 단순화 및 간소화하고 일관성을 제공하도록 돕습니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="fba07-108">사용자의 요구 사항에 맞게 패키지의 정책 설정을 사용자 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="fba07-109">정책 패키지의 정책 설정을 변경하면 해당 패키지에 할당된 모든 사용자에게 업데이트된 설정이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="fba07-110">Microsoft Teams 관리자 센터 또는 PowerShell을 사용하여 정책 패키지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="fba07-111">정책 패키지는 패키지에 따라 다음에 대한 정책을 미리 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="fba07-112">메시지</span><span class="sxs-lookup"><span data-stu-id="fba07-112">Messaging</span></span>
- <span data-ttu-id="fba07-113">모임</span><span class="sxs-lookup"><span data-stu-id="fba07-113">Meetings</span></span>
- <span data-ttu-id="fba07-114">통화</span><span class="sxs-lookup"><span data-stu-id="fba07-114">Calling</span></span>
- <span data-ttu-id="fba07-115">앱 설정</span><span class="sxs-lookup"><span data-stu-id="fba07-115">App setup</span></span>
- <span data-ttu-id="fba07-116">라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="fba07-116">Live events</span></span>

<span data-ttu-id="fba07-117">Teams 정부에 대한 다음 정책 패키지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="fba07-118">Microsoft Teams 관리 센터의 패키지 이름</span><span class="sxs-lookup"><span data-stu-id="fba07-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="fba07-119">최적 용도</span><span class="sxs-lookup"><span data-stu-id="fba07-119">Best used for</span></span>|<span data-ttu-id="fba07-120">설명</span><span class="sxs-lookup"><span data-stu-id="fba07-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="fba07-121">공공 안전 책임자</span><span class="sxs-lookup"><span data-stu-id="fba07-121">Public safety officer</span></span>  |<span data-ttu-id="fba07-122">정부 조직의 공공 안전 책임자</span><span class="sxs-lookup"><span data-stu-id="fba07-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="fba07-123">조직의 공공 안전 책임자에 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="fba07-124">프런트라인 관리자</span><span class="sxs-lookup"><span data-stu-id="fba07-124">Frontline manager</span></span>  |<span data-ttu-id="fba07-125">정부 조직의 프런트라인 관리자</span><span class="sxs-lookup"><span data-stu-id="fba07-125">Frontline Managers in your government organization</span></span> |<span data-ttu-id="fba07-126">정책 집합을 만들고 해당 설정을 조직의 Frontline Manager에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-126">Creates a set of policies and applies those settings to Frontline Managers in your organization.</span></span>|
|<span data-ttu-id="fba07-127">프런트라인 작업자</span><span class="sxs-lookup"><span data-stu-id="fba07-127">Frontline worker</span></span>  |<span data-ttu-id="fba07-128">정부 조직의 프런트라인 작업자</span><span class="sxs-lookup"><span data-stu-id="fba07-128">Frontline Workers in your government organization</span></span> |<span data-ttu-id="fba07-129">정책 집합을 만들고 해당 설정을 조직의 Frontline Workers에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-129">Creates a set of policies and applies those settings to Frontline Workers in your organization.</span></span>|

![의료 정책 패키지 스크린샷](media/policy-packages-gov.png)

<span data-ttu-id="fba07-131">각 개별 정책은 정책 패키지의 이름이 지정되며 정책 패키지에 연결된 정책을 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="fba07-132">예를 들어 조직의 사용자에게 공용 안전 책임자 정책 패키지를 할당하면 패키지의 각 PublicSafety_Officer 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![의료 임상 연구원 패키지의 정책 스크린샷](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="fba07-134">정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="fba07-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="fba07-135">보기</span><span class="sxs-lookup"><span data-stu-id="fba07-135">View</span></span>

<span data-ttu-id="fba07-136">패키지를 할당하기 전에 정책 패키지에서 각 정책의 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="fba07-137">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지** 를 선택하고 패키지 이름을 선택한 다음 정책 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="fba07-138">미리 정의된 값이 조직에 적합한지 또는 조직의 요구 사항에 따라 더 엄격하거나 관대하게 사용자 지정해야하는지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="fba07-139">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="fba07-139">Customize</span></span>

<span data-ttu-id="fba07-140">필요한 경우, 조직의 요구 사항에 맞게 정책 패키지에서 정책의 설정을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="fba07-141">정책 설정에 대한 모든 변경 내용은 패키지가 할당된 사용자에게 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="fba07-142">정책 패키지에서 정책 설정을 편집하려면 Microsoft Teams 관리 센터에서 정책 패키지를 선택하고 편집하려는 정책 이름을 선택한 다음 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="fba07-143">정책 패키지를 할당한 다음에도 패키지에서 정책 설정을 변경할 수 있다는 점을 잊지 마세요.</span><span class="sxs-lookup"><span data-stu-id="fba07-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="fba07-144">자세한 내용은 [정책 패키지에서 정책 사용자 지정](manage-policy-packages.md#customize-policies-in-a-policy-package)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fba07-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="fba07-145">할당</span><span class="sxs-lookup"><span data-stu-id="fba07-145">Assign</span></span>

<span data-ttu-id="fba07-p106">정책 패키지를 사용자에 할당합니다. 사용자에게 정책이 할당된 후 나중에 다른 정책을 할당하는 경우 가장 최근의 할당이 우선됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-p106">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

> [!NOTE]
> <span data-ttu-id="fba07-148">각 사용자는 사용자 지정 정책 패키지 할당을 받기 위해 고급 통신 추가 기능을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-148">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="fba07-149">자세한 내용은 에 대한 고급 통신 [추가 기능을 Microsoft Teams.](/microsoftteams/teams-add-on-licensing/advanced-communications)</span><span class="sxs-lookup"><span data-stu-id="fba07-149">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="fba07-150">한 명의 사용자나 여러 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="fba07-150">Assign a policy package to one or several users</span></span>

<span data-ttu-id="fba07-151">한 명의 사용자나 여러 사용자에게 정책 패키지를 할당하려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 **정책 패키지** 로 이동한 다음 **사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-151">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![관리 센터에서 정책 패키지를 할당하는 방법을 보여 주는 스크린샷](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="fba07-153">자세한 내용은 [정책 패키지 할당](manage-policy-packages.md#assign-a-policy-package)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fba07-153">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="fba07-154">사용자에게 정책이 할당된 후 나중에 다른 정책을 할당하는 경우 가장 최근의 할당이 우선됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-154">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="fba07-155">그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="fba07-155">Assign a policy package to a group</span></span>

<span data-ttu-id="fba07-156">**이 기능은 비공개 리미 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fba07-156">**This feature is in private preview**</span></span>

<span data-ttu-id="fba07-157">그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-157">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="fba07-158">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-158">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="fba07-159">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-159">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="fba07-160">이 방법은 최대 50,000명의 사용자가 있는 그룹에 적합하지만, 더 큰 그룹에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-160">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="fba07-161">자세한 내용은 [그룹에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-group)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fba07-161">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="fba07-162">대규모 사용자 집합(배치)에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="fba07-162">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="fba07-163">한 번에 많은 사용자에게 정책 패키지를 할당하려면 배치 정책 패키지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-163">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="fba07-164">[New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet을 사용하여 대규모 사용자와 할당하려는 정책 패키지를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-164">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="fba07-165">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-165">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="fba07-166">배치에는 최대 5천 명의 사용자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-166">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="fba07-167">개체 ID, UPN, SIP 주소 또는 전자 메일 주소로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fba07-167">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="fba07-168">자세한 내용은 [배치 사용자에게 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fba07-168">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="fba07-169">관련 주제</span><span class="sxs-lookup"><span data-stu-id="fba07-169">Related topics</span></span>

[<span data-ttu-id="fba07-170">Teams에서 정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="fba07-170">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="fba07-171">사용자 및 그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="fba07-171">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
