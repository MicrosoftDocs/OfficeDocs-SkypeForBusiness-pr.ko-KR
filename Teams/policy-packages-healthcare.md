---
title: 의료용 Teams 정책 패키지
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
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: 의료 조직의 Teams 정책 패키지를 사용하고 관리하는 방법에 대해 알아 보세요.
ms.openlocfilehash: 830b8fc5f6938f84f188f5f5d732a3ecfd6eb5b1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117766"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="4cd2b-103">의료용 Teams 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="4cd2b-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="4cd2b-104">개요</span><span class="sxs-lookup"><span data-stu-id="4cd2b-104">Overview</span></span>

<span data-ttu-id="4cd2b-105">Microsoft Teams의 [정책 패키지](manage-policy-packages.md)는 조직에서 유사한 역할을 가진 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="4cd2b-106">정책 패키지는 정책 관리 시 이를 단순화 및 간소화하고 일관성을 제공하도록 돕습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="4cd2b-107">사용자의 요구 사항에 맞게 패키지의 정책 설정을 사용자 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="4cd2b-108">정책 패키지의 정책 설정을 변경하면 해당 패키지에 할당된 모든 사용자에게 업데이트된 설정이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="4cd2b-109">Microsoft Teams 관리자 센터 또는 PowerShell을 사용하여 정책 패키지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="4cd2b-110">정책 패키지는 패키지에 따라 다음에 대한 정책을 미리 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="4cd2b-111">메시지</span><span class="sxs-lookup"><span data-stu-id="4cd2b-111">Messaging</span></span>
- <span data-ttu-id="4cd2b-112">모임</span><span class="sxs-lookup"><span data-stu-id="4cd2b-112">Meetings</span></span>
- <span data-ttu-id="4cd2b-113">통화</span><span class="sxs-lookup"><span data-stu-id="4cd2b-113">Calling</span></span>
- <span data-ttu-id="4cd2b-114">앱 설정</span><span class="sxs-lookup"><span data-stu-id="4cd2b-114">App setup</span></span>
- <span data-ttu-id="4cd2b-115">라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="4cd2b-115">Live events</span></span>

<span data-ttu-id="4cd2b-116">Teams는 현재 다음 의료 정책 패키지를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="4cd2b-117">Microsoft Teams 관리 센터의 패키지 이름</span><span class="sxs-lookup"><span data-stu-id="4cd2b-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="4cd2b-118">최적 용도</span><span class="sxs-lookup"><span data-stu-id="4cd2b-118">Best used for</span></span>|<span data-ttu-id="4cd2b-119">설명</span><span class="sxs-lookup"><span data-stu-id="4cd2b-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="4cd2b-120">의료 임상 연구원</span><span class="sxs-lookup"><span data-stu-id="4cd2b-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="4cd2b-121">의료 조직의 임상 연구원</span><span class="sxs-lookup"><span data-stu-id="4cd2b-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="4cd2b-122">등록된 간호사, 유료 간호사, 의사 및 사회복지사와 같은 의료진에게 채팅, 통화, 이동 관리 및 회의에 대한 완전한 액세스를 제공하는 정책 및 정책 설정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="4cd2b-123">의료 정보 직원</span><span class="sxs-lookup"><span data-stu-id="4cd2b-123">Healthcare information worker</span></span>  |<span data-ttu-id="4cd2b-124">의료 조직의 정보 연구원</span><span class="sxs-lookup"><span data-stu-id="4cd2b-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="4cd2b-125">IT 직원, 정보 전문가, 재무 담당자 및 규정 준수 담당자와 같은 정보 직원에게 채팅, 통화 및 모임에 대한 전체 액세스 권한을 부여하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="4cd2b-126">의료 환자실</span><span class="sxs-lookup"><span data-stu-id="4cd2b-126">Healthcare patient room</span></span>  |<span data-ttu-id="4cd2b-127">환자실 장치</span><span class="sxs-lookup"><span data-stu-id="4cd2b-127">Patient room devices</span></span>|<span data-ttu-id="4cd2b-128">의료 조직의 환자실에 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![의료 정책 패키지 스크린샷](media/policy-packages-healthcare.png)

<span data-ttu-id="4cd2b-130">각 개별 정책은 정책 패키지의 이름이 지정되며 정책 패키지에 연결된 정책을 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="4cd2b-131">예를 들어 조직의 임상 연구원에게 의료 임상 작업자 정책 패키지를 할당할 때 패키지의 각 정책에 대해 Healthcare_ClinicalWorker라는 정책이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![의료 임상 연구원 패키지의 정책 스크린샷](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="4cd2b-133">정책 패키지로 시작</span><span class="sxs-lookup"><span data-stu-id="4cd2b-133">Get started with policy packages</span></span>

<span data-ttu-id="4cd2b-134">의료 정책 패키지를 시작하려면 Microsoft 관리 센터 온보드 허브에서 **의료** 를 선택한 다음 **역할별 정책 설정 할당** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="4cd2b-135">시작할 준비가 되었으면 조직의 개인을 할당할 정책 패키지를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="4cd2b-136">패키지의 특정 정책과 해당 설정에 대해 자세히 알아보려면 **정책 세부 정보 보기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="4cd2b-137">Teams 관리 센터에서 할당한 후 [사용자 정의할 수 있습니다](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="4cd2b-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="4cd2b-138">할당할 패키지를 하나 또는 여러 개 선택하고 **다음** 을 누르세요.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="4cd2b-139">역할에 가장 적합한 정책 패키지를 검색하여 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="4cd2b-140">개인은 한 번에 둘 이상의 정책 패키지에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="4cd2b-141">올바른 정책 패키지에 사용자를 추가하면 선택사항이 **완료** 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="4cd2b-142">Microsoft Teams 관리자 센터에서 정책 패키지를 계속 사용자 정의하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="4cd2b-143">정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="4cd2b-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="4cd2b-144">보기</span><span class="sxs-lookup"><span data-stu-id="4cd2b-144">View</span></span>

<span data-ttu-id="4cd2b-145">패키지를 할당하기 전에 정책 패키지에서 각 정책의 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="4cd2b-146">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지** 로 이동하고 패키지 이름을 선택한 다음 정책 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="4cd2b-147">미리 정의된 값이 조직에 적합한지 또는 조직의 요구 사항에 따라 더 엄격하거나 관대하게 사용자 지정해야하는지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="4cd2b-148">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4cd2b-148">Customize</span></span>

<span data-ttu-id="4cd2b-149">필요한 경우, 조직의 요구 사항에 맞게 정책 패키지에서 정책의 설정을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="4cd2b-150">정책 설정에 대한 모든 변경 내용은 패키지가 할당된 사용자에게 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="4cd2b-151">정책 패키지의 정책 설정을 편집하려면 Microsoft Teams 관리자 센터의 왼쪽 탐색에서 **정책 패키지** 로 이동하여 정책 패키지를 선택하고 편집할 정책 이름을 선택한 다음 **편집** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="4cd2b-152">정책 패키지를 할당한 다음에도 패키지에서 정책 설정을 변경할 수 있다는 점을 잊지 마세요.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="4cd2b-153">자세한 내용은 [정책 패키지에서 정책 사용자 지정](manage-policy-packages.md#customize-policies-in-a-policy-package)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="4cd2b-154">할당</span><span class="sxs-lookup"><span data-stu-id="4cd2b-154">Assign</span></span>

<span data-ttu-id="4cd2b-p110">정책 패키지를 사용자에 할당합니다. 사용자에게 정책이 할당된 후 나중에 다른 정책을 할당하는 경우 가장 최근의 할당이 우선됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-p110">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="4cd2b-157">한 명의 사용자나 여러 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="4cd2b-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="4cd2b-158">한 명의 사용자나 여러 사용자에게 정책 패키지를 할당하려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 **정책 패키지** 로 이동한 다음 **사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![관리 센터에서 정책 패키지를 할당하는 방법을 보여 주는 스크린샷](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="4cd2b-160">자세한 내용은 [정책 패키지 할당](manage-policy-packages.md#assign-a-policy-package)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="4cd2b-161">사용자에게 정책이 할당된 후 나중에 다른 정책을 할당하는 경우 가장 최근의 할당이 우선됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="4cd2b-162">그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="4cd2b-162">Assign a policy package to a group</span></span>

<span data-ttu-id="4cd2b-163">**이 기능은 비공개 리미 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4cd2b-163">**This feature is in private preview**</span></span>

<span data-ttu-id="4cd2b-164">그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="4cd2b-165">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="4cd2b-166">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="4cd2b-167">이 방법은 최대 50,000명의 사용자가 있는 그룹에 적합하지만, 더 큰 그룹에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="4cd2b-168">자세한 내용은 [그룹에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-group)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="4cd2b-169">대규모 사용자 집합(배치)에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="4cd2b-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="4cd2b-170">한 번에 많은 사용자에게 정책 패키지를 할당하려면 배치 정책 패키지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="4cd2b-171">[New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet을 사용하여 대규모 사용자와 할당하려는 정책 패키지를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="4cd2b-172">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="4cd2b-173">배치에는 최대 5천 명의 사용자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="4cd2b-174">개체 ID, UPN, SIP 주소 또는 전자 메일 주소로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="4cd2b-175">자세한 내용은 [배치 사용자에게 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd2b-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4cd2b-176">관련 주제</span><span class="sxs-lookup"><span data-stu-id="4cd2b-176">Related topics</span></span>

[<span data-ttu-id="4cd2b-177">Teams에서 정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="4cd2b-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="4cd2b-178">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4cd2b-178">Assign policies to your users in Teams</span></span>](assign-policies.md)