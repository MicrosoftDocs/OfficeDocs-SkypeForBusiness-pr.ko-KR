---
title: Microsoft 팀에서 정책 패키지 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 정책 패키지를 사용 하 고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: d9e18f662f96d4021cf4878ba5130decb40bb9e4
ms.sourcegitcommit: b6e17a6690011917c8fc14e98a49af654441a204
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2019
ms.locfileid: "37889857"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="81aef-103">Microsoft 팀에서 정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="81aef-103">Manage policy packages in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="81aef-104">Microsoft 팀의 정책 패키지는 조직에서 유사한 역할을 갖는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="81aef-105">조직의 사용자 그룹에 대 한 정책을 관리할 때 일관성을 단순화 하 고 합리화 하 고 사용할 수 있도록 하는 정책 패키지를 작성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="81aef-106">정책 패키지를 사용자에 게 할당 하면 패키지의 정책이 만들어지고 해당 조직의 요구 사항에 맞게 패키지의 정책 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="81aef-107">정책 패키지 란?</span><span class="sxs-lookup"><span data-stu-id="81aef-107">What is a policy package?</span></span>

<span data-ttu-id="81aef-108">정책 패키지를 사용 하 여 조직 내 특정 사용자 집합에 허용 하거나 제한할 팀 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="81aef-109">팀의 각 정책 패키지는 사용자 역할을 중심으로 설계 되며, 해당 역할에 일반적으로 사용 되는 공동 작업 및 통신 작업을 지 원하는 미리 정의 된 정책 및 정책 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="81aef-110">현재 팀에는 다음 정책 패키지가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="81aef-111">**패키지 이름**</span><span class="sxs-lookup"><span data-stu-id="81aef-111">**Package name**</span></span>  |<span data-ttu-id="81aef-112">**설명**</span><span class="sxs-lookup"><span data-stu-id="81aef-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="81aef-113">Education_Teacher 패키지</span><span class="sxs-lookup"><span data-stu-id="81aef-113">Education_Teacher package</span></span>     |<span data-ttu-id="81aef-114">교사에 게 적용할 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-114">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="81aef-115">Education_PrimaryStudent 패키지</span><span class="sxs-lookup"><span data-stu-id="81aef-115">Education_PrimaryStudent package</span></span>    |<span data-ttu-id="81aef-116">기본 학생에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="81aef-117">Education_SecondaryStudent 패키지</span><span class="sxs-lookup"><span data-stu-id="81aef-117">Education_SecondaryStudent package</span></span>    |<span data-ttu-id="81aef-118">보조 학생에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="81aef-119">Education_HigherEducationStudent 패키지</span><span class="sxs-lookup"><span data-stu-id="81aef-119">Education_HigherEducationStudent package</span></span>    |<span data-ttu-id="81aef-120">높은 교육 학생 들에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-120">Creates a set of policies and policy settings that apply to higher education students.</span></span>|

> [!NOTE]
> <span data-ttu-id="81aef-121">팀의 향후 릴리스에서 정책 패키지를 더 추가 하 게 되므로 최신 정보를 다시 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="81aef-121">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="81aef-122">정책 패키지에 연결 된 정책을 쉽게 식별할 수 있도록 각 개별 정책에 정책 패키지의 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-122">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="81aef-123">예를 들어 학교에 Education_Teacher 정책 패키지를 할당 하면 패키지의 각 정책에 대해 Education_Teacher 이라는 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-123">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher 정책 패키지 스크린샷](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="81aef-125">정책 패키지를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="81aef-125">How to use policy packages</span></span>

<span data-ttu-id="81aef-126">다음 개요에는 조직에서 정책 패키지를 사용 하는 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-126">The following outlines how to use policy packages in your organization.</span></span>

![정책 패키지 사용 방법 개요](media/manage-policy-packages-overview.png)

- <span data-ttu-id="81aef-128">**[보기](#view-the-settings-of-a-policy-in-a-policy-package)**: 패키지를 할당 하기 전에 정책 패키지의 각 정책에 대 한 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-128">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="81aef-129">각 설정을 이해 하 고 미리 정의 된 값이 조직에 적합 한지, 아니면 조직의 요구 사항에 따라이를 변경 하는 것이 적절 한지 또는 lenient 결정 해야 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-129">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="81aef-130">정책이 삭제 된 경우에도 설정을 볼 수 있지만 설정을 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-130">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="81aef-131">정책 패키지를 할당할 때 미리 정의 된 설정을 사용 하 여 삭제 된 정책이 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-131">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="81aef-132">**[Assign](#assign-a-policy-package)**: 사용자에 게 정책 패키지를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-132">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="81aef-133">패키지를 할당할 때까지 정책 패키지의 정책이 만들어지지 않으며 그 이후에는 패키지의 개별 정책 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-133">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="81aef-134">**[사용자 지정](#customize-policies-in-a-policy-package)**: 조직의 요구에 맞게 정책 패키지의 정책 설정을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-134">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="81aef-135">정책 설정에 대 한 변경 내용은 패키지를 할당 한 사용자에 게 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-135">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="81aef-136">Microsoft 팀 관리 센터에서 정책 패키지를 보고 할당 하 고 사용자 지정 하는 방법에 대 한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-136">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="81aef-137">정책 패키지의 정책 설정 보기</span><span class="sxs-lookup"><span data-stu-id="81aef-137">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="81aef-138">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **정책 패키지**를 클릭 한 다음 패키지 이름 왼쪽을 클릭 하 여 정책 패키지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-138">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="81aef-139">보려는 정책을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-139">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="81aef-140">정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="81aef-140">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="81aef-141">한 사용자에 게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="81aef-141">Assign a policy package to one user</span></span>

1. <span data-ttu-id="81aef-142">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 다음 사용자를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-142">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="81aef-143">사용자의 페이지에서 **정책을**클릭 한 다음 **정책 패키지**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-143">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="81aef-144">**정책 패키지 할당** 창에서 할당할 패키지를 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-144">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="81aef-145">여러 사용자에 게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="81aef-145">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="81aef-146">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **정책 패키지로**이동한 다음 패키지 이름 왼쪽을 클릭 하 여 할당 하려는 정책 패키지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="81aef-147">**사용자 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-147">Click **Manage users**.</span></span>
3. <span data-ttu-id="81aef-148">**사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-148">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="81aef-149">추가 하려는 각 사용자에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-149">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="81aef-150">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-150">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="81aef-151">정책 패키지의 정책 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="81aef-151">Customize policies in a policy package</span></span>

<span data-ttu-id="81aef-152">정책 **패키지** 페이지를 통해 또는 Microsoft 팀 관리 센터의 정책 페이지로 직접 이동 하 여 정책의 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-152">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="81aef-153">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-153">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="81aef-154">**정책 패키지**를 클릭 한 다음 패키지 이름 왼쪽을 클릭 하 여 정책 패키지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-154">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="81aef-155">정책 유형을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-155">Click the policy type.</span></span>  <span data-ttu-id="81aef-156">예를 들어 **메시지 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-156">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="81aef-157">편집 하려는 정책을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-157">Click the policy you want to edit.</span></span> <span data-ttu-id="81aef-158">정책 패키지에 연결 된 정책에는 정책 패키지와 동일한 이름이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-158">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="81aef-159">원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-159">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="81aef-160">해결사</span><span class="sxs-lookup"><span data-stu-id="81aef-160">Troubleshooting</span></span>

<span data-ttu-id="81aef-161">**정책 패키지를 할당할 때 오류가 표시 되는 경우**</span><span class="sxs-lookup"><span data-stu-id="81aef-161">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="81aef-162">패키지에서 하나 이상의 정책이 성공적으로 만들어지거나 적용 되지 않은 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-162">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="81aef-163">정책 패키지를 사용자에 게 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-163">Reassign the policy package to your users.</span></span> <span data-ttu-id="81aef-164">작업을 다시 시도 하면 일반적으로이 문제가 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81aef-164">Retrying the operation typically fixes this issue.</span></span>
