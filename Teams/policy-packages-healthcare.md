---
title: 의료에 대 한 팀 정책 패키지
author: lanachin
ms.author: v-lanac
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
description: 의료 조직의 팀 정책 패키지를 사용 하 고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: b8317a7f860d0ab8510a6170b69a50f7a3387ebd
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908517"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="a8f78-103">의료에 대 한 팀 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="a8f78-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="a8f78-104">개요</span><span class="sxs-lookup"><span data-stu-id="a8f78-104">Overview</span></span>

<span data-ttu-id="a8f78-105">Microsoft 팀의 [정책 패키지](manage-policy-packages.md) 는 조직에서 유사한 역할을 갖는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="a8f78-106">정책 패키지는 정책 관리 시 이를 단순화 및 간소화하고 일관성을 제공하도록 돕습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="a8f78-107">사용자의 요구에 맞게 패키지의 정책 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="a8f78-108">정책 패키지의 정책 설정을 변경 하면 해당 패키지에 할당 된 모든 사용자가 업데이트 된 설정을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="a8f78-109">Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책 패키지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="a8f78-110">정책 패키지는 패키지에 따라 다음에 대 한 정책을 미리 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="a8f78-111">메시징</span><span class="sxs-lookup"><span data-stu-id="a8f78-111">Messaging</span></span>
- <span data-ttu-id="a8f78-112">모임</span><span class="sxs-lookup"><span data-stu-id="a8f78-112">Meetings</span></span>
- <span data-ttu-id="a8f78-113">통화</span><span class="sxs-lookup"><span data-stu-id="a8f78-113">Calling</span></span>
- <span data-ttu-id="a8f78-114">앱 설정</span><span class="sxs-lookup"><span data-stu-id="a8f78-114">App setup</span></span>
- <span data-ttu-id="a8f78-115">라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="a8f78-115">Live events</span></span>

<span data-ttu-id="a8f78-116">현재 팀에는 다음과 같은 건강 보험 정책 패키지가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="a8f78-117">Microsoft 팀 관리 센터의 패키지 이름</span><span class="sxs-lookup"><span data-stu-id="a8f78-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="a8f78-118">최적 용도</span><span class="sxs-lookup"><span data-stu-id="a8f78-118">Best used for</span></span>|<span data-ttu-id="a8f78-119">설명</span><span class="sxs-lookup"><span data-stu-id="a8f78-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="a8f78-120">의료 임상 근로자</span><span class="sxs-lookup"><span data-stu-id="a8f78-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="a8f78-121">건강 관리 조직의 임상 근로자</span><span class="sxs-lookup"><span data-stu-id="a8f78-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="a8f78-122">등록 된 nurses, 청구 nurses, 의사, 소셜 작업자에 게 채팅, 통화, 교대 관리, 모임에 대 한 전체 액세스 등의 임상 근로자를 제공 하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="a8f78-123">의료 정보 근로자</span><span class="sxs-lookup"><span data-stu-id="a8f78-123">Healthcare information worker</span></span>  |<span data-ttu-id="a8f78-124">건강 관리 조직의 정보 근로자</span><span class="sxs-lookup"><span data-stu-id="a8f78-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="a8f78-125">IT 직원, informatics 스태프, 재무 담당자, 규정 준수 관리자, 채팅, 통화, 모임에 대 한 모든 액세스 권한을 제공 하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="a8f78-126">의료 환자 실</span><span class="sxs-lookup"><span data-stu-id="a8f78-126">Healthcare patient room</span></span>  |<span data-ttu-id="a8f78-127">환자 실 장치</span><span class="sxs-lookup"><span data-stu-id="a8f78-127">Patient room devices</span></span>|<span data-ttu-id="a8f78-128">건강 관리 조직의 환자 방에 해당 하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![건강 보험 정책 패키지 스크린샷](media/policy-packages-healthcare.png)

<span data-ttu-id="a8f78-130">정책 패키지에 연결 된 정책을 쉽게 식별할 수 있도록 각 개별 정책에 정책 패키지의 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="a8f78-131">예를 들어 조직의 clinicians에 의료 임상 작업자 정책 패키지를 할당 하면 패키지의 각 정책에 대 한 Healthcare_ClinicalWorker 라는 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![의료 임상 작업자 패키지의 정책 스크린샷](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="a8f78-133">정책 패키지 시작</span><span class="sxs-lookup"><span data-stu-id="a8f78-133">Get started with policy packages</span></span>

<span data-ttu-id="a8f78-134">의료 정책 패키지를 시작 하려면 Microsoft 관리 센터 온 보 hub 허브에서 **건강** 관리를 선택한 다음 **역할별로 정책 설정 할당** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare** , and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="a8f78-135">시작할 준비가 되 면 조직의 사용자를 지정할 정책 패키지를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="a8f78-136">패키지의 특정 정책 및 해당 설정에 대해 자세히 알아보려면 **정책 세부 정보 보기** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="a8f78-137">팀 관리 센터에서 과제를 할당 한 후에 [사용자 지정할 수 있습니다](manage-policy-packages.md#customize-policies-in-a-policy-package) .</span><span class="sxs-lookup"><span data-stu-id="a8f78-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="a8f78-138">할당할 패키지를 하나 이상 선택 하 고 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="a8f78-139">역할에 가장 적합 한 정책 패키지를 검색 하 고 사용자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="a8f78-140">한 번에 둘 이상의 정책 패키지에 개별적으로 배정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="a8f78-141">사용자를 올바른 정책 패키지에 추가한 후에는 **완료** 가 선택 항목을 종결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="a8f78-142">Microsoft 팀 관리 센터에서 계속 해 서 정책 패키지를 사용자 지정 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="a8f78-143">정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="a8f78-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="a8f78-144">보기</span><span class="sxs-lookup"><span data-stu-id="a8f78-144">View</span></span>

<span data-ttu-id="a8f78-145">패키지를 할당 하기 전에 정책 패키지의 각 정책에 대 한 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="a8f78-146">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **정책 패키지로** 이동 하 여 패키지 이름을 선택한 다음 정책 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="a8f78-147">미리 정의 된 값이 조직에 적합 한지 아니면 조직의 요구 사항에 따라 더 엄격 하 게 또는 lenient 사용자 지정 해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="a8f78-148">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="a8f78-148">Customize</span></span>

<span data-ttu-id="a8f78-149">필요에 따라 정책 패키지의 정책 설정을 조직의 필요에 맞게 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="a8f78-150">정책 설정에 대 한 변경 내용은 패키지를 할당 한 사용자에 게 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="a8f78-151">정책 패키지의 정책 설정을 편집 하려면 Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **정책** 패키지로 이동 하 고 정책 패키지를 선택한 다음 편집 하려는 정책의 이름을 선택 하 고 **편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="a8f78-152">정책 패키지를 할당 한 후에는 패키지의 정책 설정을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="a8f78-153">자세히 알아보려면 [정책 패키지의 정책 사용자 지정](manage-policy-packages.md#customize-policies-in-a-policy-package)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8f78-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="a8f78-154">배정할</span><span class="sxs-lookup"><span data-stu-id="a8f78-154">Assign</span></span>

<span data-ttu-id="a8f78-155">사용자에 게 정책 패키지를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-155">Assign the policy package to users.</span></span> <span data-ttu-id="a8f78-156">사용자에 게 정책이 할당 된 후 나중에 다른 정책을 할당 하는 경우에는 가장 최근의 할당이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="a8f78-157">한 명 또는 여러 명의 사용자에 게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="a8f78-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="a8f78-158">한 명 또는 여러 명의 사용자에 게 정책 패키지를 할당 하려면 Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **정책 패키지로** 이동한 다음 **사용자 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select **Manage users**.</span></span>  

![관리 센터에서 정책 패키지를 할당 하는 방법 스크린샷](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="a8f78-160">자세히 알아보려면 [정책 패키지 할당](manage-policy-packages.md#assign-a-policy-package)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8f78-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="a8f78-161">사용자에 게 정책이 할당 된 후 나중에 다른 정책을 할당 하는 경우에는 가장 최근의 할당이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="a8f78-162">그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="a8f78-162">Assign a policy package to a group</span></span>

<span data-ttu-id="a8f78-163">**이 기능은 비공개 미리 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="a8f78-163">**This feature is in private preview**</span></span>

<span data-ttu-id="a8f78-164">그룹에 정책 패키지 할당을 사용 하 여 보안 그룹 또는 배포 목록 등의 사용자 그룹에 여러 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="a8f78-165">정책 할당은 선행 규칙에 따라 그룹의 구성원에 게 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="a8f78-166">그룹에서 구성원이 추가 되거나 제거 되 면 그에 따라 상속 된 정책 할당이 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="a8f78-167">이 방법은 최대 5만 사용자 그룹에 사용 하는 것이 좋지만 대규모 그룹 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="a8f78-168">자세히 알아보려면 [그룹에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-group)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8f78-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="a8f78-169">사용자의 대규모 집합 (일괄 처리)에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="a8f78-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="a8f78-170">일괄 처리 정책 패키지 할당을 사용 하 여 한 번에 대규모 사용자 집합에 정책 패키지를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="a8f78-171">[CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet을 사용 하 여 할당 하려는 사용자 및 정책 패키지의 일괄 처리를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="a8f78-172">할당이 백그라운드 작업으로 처리 되 고 각 일괄 처리에 대 한 작업 ID가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="a8f78-173">일괄 처리에는 최대 5000 명의 사용자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="a8f78-174">개체 Id, UPN, SIP 주소 또는 전자 메일 주소로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f78-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="a8f78-175">자세한 내용은 [사용자 일괄 처리에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a8f78-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a8f78-176">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a8f78-176">Related topics</span></span>

[<span data-ttu-id="a8f78-177">Teams에서 정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="a8f78-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="a8f78-178">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a8f78-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
