---
title: Microsoft 팀에서 정책 패키지 관리
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 정책 패키지를 사용 하 고 관리 하 여 사용자 그룹에 대 한 정책을 관리할 때 일관성을 간소화 하 고 간소화 하 고 해결 하는 방법을 알아봅니다.
ms.openlocfilehash: 986d64b11420877e146abc68f9f65c0503f49ff0
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48918641"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="b01af-103">Microsoft 팀에서 정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="b01af-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="b01af-104">이 문서에서 설명 하는 [사용자 지정 정책 패키지](#custom-policy-packages)의 기능 중 하나는 현재 비공개 미리 보기 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), is currently in private preview.</span></span>

<span data-ttu-id="b01af-105">Microsoft 팀의 정책 패키지는 조직에서 유사한 역할을 갖는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-105">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="b01af-106">조직의 사용자 그룹에 대 한 정책을 관리할 때 일관성을 단순화 하 고 합리화 하 고 사용할 수 있도록 하는 정책 패키지를 작성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-106">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="b01af-107">[팀에 포함 된 정책 패키지](#policy-packages-included-in-teams) 를 사용 하거나 [고유한 사용자 지정 정책 패키지](#custom-policy-packages) (비공개 미리 보기)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-107">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="관리 센터의 정책 패키지 페이지 스크린샷":::

<span data-ttu-id="b01af-109">사용자의 요구에 맞게 정책 패키지의 정책 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-109">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="b01af-110">패키지의 정책 설정을 변경 하면 해당 패키지에 할당 된 모든 사용자가 업데이트 된 설정을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-110">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="b01af-111">Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책 패키지를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-111">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="b01af-112">정책 패키지 란?</span><span class="sxs-lookup"><span data-stu-id="b01af-112">What is a policy package?</span></span>

<span data-ttu-id="b01af-113">정책 패키지를 사용 하 여 조직 내 특정 사용자 집합에 허용 하거나 제한할 팀 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-113">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="b01af-114">팀의 각 정책 패키지는 사용자 역할을 중심으로 설계 되며, 해당 역할에 일반적으로 사용 되는 공동 작업 및 통신 작업을 지 원하는 미리 정의 된 정책 및 정책 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-114">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="b01af-115">정책 패키지는 다음 팀 정책 유형을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-115">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="b01af-116">메시징 정책</span><span class="sxs-lookup"><span data-stu-id="b01af-116">Messaging policy</span></span>
- <span data-ttu-id="b01af-117">모임 정책</span><span class="sxs-lookup"><span data-stu-id="b01af-117">Meeting policy</span></span>
- <span data-ttu-id="b01af-118">앱 설정 정책</span><span class="sxs-lookup"><span data-stu-id="b01af-118">App setup policy</span></span>
- <span data-ttu-id="b01af-119">통화 정책</span><span class="sxs-lookup"><span data-stu-id="b01af-119">Calling policy</span></span>
- <span data-ttu-id="b01af-120">라이브 이벤트 정책</span><span class="sxs-lookup"><span data-stu-id="b01af-120">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="b01af-121">팀에 포함 된 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="b01af-121">Policy packages included in Teams</span></span>

<span data-ttu-id="b01af-122">현재 팀에는 다음 정책 패키지가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-122">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="b01af-123">**패키지 이름**</span><span class="sxs-lookup"><span data-stu-id="b01af-123">**Package name**</span></span>  |<span data-ttu-id="b01af-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="b01af-124">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="b01af-125">교육 (고급 교육 학생)</span><span class="sxs-lookup"><span data-stu-id="b01af-125">Education (Higher education student)</span></span>    |<span data-ttu-id="b01af-126">높은 교육 학생 들에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-126">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="b01af-127">교육 (주 학교 학생)</span><span class="sxs-lookup"><span data-stu-id="b01af-127">Education (Primary school student)</span></span>   |<span data-ttu-id="b01af-128">기본 학생에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-128">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="b01af-129">교육 (보조 학교 학생)</span><span class="sxs-lookup"><span data-stu-id="b01af-129">Education (Secondary school student)</span></span>    |<span data-ttu-id="b01af-130">보조 학생에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-130">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="b01af-131">교육 (교사)</span><span class="sxs-lookup"><span data-stu-id="b01af-131">Education (Teacher)</span></span>    |<span data-ttu-id="b01af-132">교사에 게 적용할 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-132">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="b01af-133">교육 (원격 학습을 사용 하 여 기본 학교 교사)</span><span class="sxs-lookup"><span data-stu-id="b01af-133">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="b01af-134">초등학교 교사에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-134">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="b01af-135">교육 (원격 학습을 사용 하는 기본 학교 학생)</span><span class="sxs-lookup"><span data-stu-id="b01af-135">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="b01af-136">초등학교 학생에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-136">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="b01af-137">Firstline manager</span><span class="sxs-lookup"><span data-stu-id="b01af-137">Firstline manager</span></span> |<span data-ttu-id="b01af-138">조직의 Firstline 관리자에 게 정책 집합을 만들고 해당 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-138">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span> |
|<span data-ttu-id="b01af-139">Firstline worker</span><span class="sxs-lookup"><span data-stu-id="b01af-139">Firstline worker</span></span> |<span data-ttu-id="b01af-140">정책 집합을 만들고 조직의 Firstline Worker에 해당 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-140">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span> |
|<span data-ttu-id="b01af-141">의료 임상 근로자</span><span class="sxs-lookup"><span data-stu-id="b01af-141">Healthcare clinical worker</span></span>  |<span data-ttu-id="b01af-142">등록 된 nurses, 청구 nurses, 의사, 소셜 작업자에 게 채팅, 통화, 교대 관리, 모임에 대 한 전체 액세스 등의 임상 근로자를 제공 하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-142">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="b01af-143">의료 정보 근로자</span><span class="sxs-lookup"><span data-stu-id="b01af-143">Healthcare information worker</span></span>  |<span data-ttu-id="b01af-144">IT 직원, informatics 스태프, 재무 담당자, 규정 준수 관리자, 채팅, 통화, 모임에 대 한 모든 액세스 권한을 제공 하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-144">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="b01af-145">의료 환자 실</span><span class="sxs-lookup"><span data-stu-id="b01af-145">Healthcare patient room</span></span>  |<span data-ttu-id="b01af-146">건강 관리 조직의 환자 방에 해당 하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-146">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="b01af-147">중소 기업 사용자 (비즈니스 음성)</span><span class="sxs-lookup"><span data-stu-id="b01af-147">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="b01af-148">비즈니스 음성 환경에 대 한 앱을 포함 하는 앱 설치 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-148">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="b01af-149">중소 규모 비즈니스 사용자 (비즈니스 보이스 필요 없음)</span><span class="sxs-lookup"><span data-stu-id="b01af-149">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="b01af-150">중소 규모의 비즈니스 팀 사용자 (비 비즈니스 음성 환경)와 관련 된 앱 설치 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-150">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="b01af-151">공개 안전 책임자</span><span class="sxs-lookup"><span data-stu-id="b01af-151">Public safety officer</span></span>   |<span data-ttu-id="b01af-152">조직의 공개 보안 책임자에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-152">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="b01af-153">팀의 향후 릴리스에서 정책 패키지를 더 추가 하 게 되므로 최신 정보를 다시 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="b01af-153">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="b01af-154">정책 패키지에 연결 된 정책을 쉽게 식별할 수 있도록 각 개별 정책에 정책 패키지의 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-154">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="b01af-155">예를 들어 학교에 교사 (교육) 정책 패키지를 할당 하는 경우 패키지의 각 정책에 대해 Education_Teacher 이라는 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-155">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![교사 (교육) 정책 패키지 스크린샷](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="b01af-157">사용자 지정 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="b01af-157">Custom policy packages</span></span>

<span data-ttu-id="b01af-158">**이 기능은 비공개 미리 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b01af-158">**This feature is in private preview**</span></span>

<span data-ttu-id="b01af-159">사용자 지정 정책 패키지를 사용 하 여 조직에서 비슷한 역할을 갖는 사용자에 대해 자신만의 정책 집합을 번들로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-159">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="b01af-160">필요한 정책 유형 및 정책을 추가 하 여 고유한 정책 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-160">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="b01af-161">새 사용자 지정 정책 패키지를 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-161">To create a new custom policy package:</span></span>

1. <span data-ttu-id="b01af-162">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지** 를 선택한 다음 **추가** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-162">In the left navigation of the Microsoft Teams admin center,  select **Policy packages** , and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="관리 센터의 정책 패키지 페이지에 있는 추가 단추 스크린샷":::
2. <span data-ttu-id="b01af-164">패키지의 이름과 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-164">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="새 사용자 지정 정책 패키지 추가 스크린샷":::
3. <span data-ttu-id="b01af-166">패키지에 포함할 정책 유형 및 정책 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-166">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="b01af-167">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-167">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="b01af-168">정책 패키지를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="b01af-168">How to use policy packages</span></span>

<span data-ttu-id="b01af-169">다음 개요에는 조직에서 정책 패키지를 사용 하는 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-169">The following outlines how to use policy packages in your organization.</span></span>

![정책 패키지 사용 방법 개요](media/manage-policy-packages-overview.png)

- <span data-ttu-id="b01af-171">**[보기](#view-the-settings-of-a-policy-in-a-policy-package)** : 정책 패키지의 정책을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-171">**[View](#view-the-settings-of-a-policy-in-a-policy-package)** : View the policies in a policy package.</span></span> <span data-ttu-id="b01af-172">그런 다음 패키지를 할당 하기 전에 패키지의 각 정책에 대 한 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-172">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="b01af-173">각 설정을 이해 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-173">Make sure that you understand each setting.</span></span> <span data-ttu-id="b01af-174">미리 정의 된 값이 조직에 적합 한지 아니면 조직의 요구 사항에 따라 더 엄격 하 게 또는 lenient 변경 해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-174">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="b01af-175">정책이 삭제 된 경우에도 설정을 볼 수 있지만 설정을 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-175">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="b01af-176">정책 패키지를 할당할 때 미리 정의 된 설정을 사용 하 여 삭제 된 정책이 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-176">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="b01af-177">**[사용자 지정](#customize-policies-in-a-policy-package)** : 조직의 요구에 맞게 정책 패키지의 정책 설정을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-177">**[Customize](#customize-policies-in-a-policy-package)** : Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="b01af-178">**[Assign](#assign-a-policy-package)** : 사용자에 게 정책 패키지를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-178">**[Assign](#assign-a-policy-package)** : Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="b01af-179">패키지를 할당 한 후에는 정책 패키지의 정책 설정을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-179">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="b01af-180">정책 설정에 대 한 변경 내용은 패키지를 할당 한 사용자에 게 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-180">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="b01af-181">Microsoft 팀 관리 센터에서 정책 패키지를 보고 할당 하 고 사용자 지정 하는 방법에 대 한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-181">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="b01af-182">정책 패키지의 정책 설정 보기</span><span class="sxs-lookup"><span data-stu-id="b01af-182">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="b01af-183">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지** 를 선택한 다음 패키지 이름 왼쪽을 클릭 하 여 정책 패키지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-183">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="b01af-184">보려는 정책을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-184">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="b01af-185">정책 패키지의 정책 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b01af-185">Customize policies in a policy package</span></span>

<span data-ttu-id="b01af-186">정책 **패키지** 페이지를 통해 또는 Microsoft 팀 관리 센터의 정책 페이지로 직접 이동 하 여 정책의 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-186">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="b01af-187">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-187">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="b01af-188">**정책 패키지** 를 클릭 한 다음 패키지 이름 왼쪽을 클릭 하 여 정책 패키지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-188">Click **Policy packages** , and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="b01af-189">정책 유형을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-189">Click the policy type.</span></span>  <span data-ttu-id="b01af-190">예를 들어 **메시지 정책을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-190">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="b01af-191">편집 하려는 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-191">Select the policy you want to edit.</span></span> <span data-ttu-id="b01af-192">정책 패키지에 연결 된 정책에는 정책 패키지와 동일한 이름이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-192">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="b01af-193">원하는 변경 작업을 수행한 다음 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-193">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="b01af-194">정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b01af-194">Assign a policy package</span></span> 

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="b01af-195">한 사용자에 게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b01af-195">Assign a policy package to one user</span></span>

1. <span data-ttu-id="b01af-196">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자** 로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-196">In the left navigation of the Microsoft Teams admin center, go to **Users** , and then click the user.</span></span>
2. <span data-ttu-id="b01af-197">사용자의 페이지에서 **정책을** 클릭 한 다음 **정책 패키지** 옆에 있는 **편집** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-197">On the user's page, click **Policies** , and then next to **Policy package** , click **Edit**.</span></span>
3. <span data-ttu-id="b01af-198">**정책 패키지 할당** 창에서 할당할 패키지를 선택 하 고 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-198">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="b01af-199">여러 사용자에 게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b01af-199">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="b01af-200">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **정책 패키지로** 이동한 다음 패키지 이름 왼쪽을 클릭 하 여 할당 하려는 정책 패키지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-200">In the left navigation of the Microsoft Teams admin center, go to **Policy packages** , and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="b01af-201">**사용자 관리** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-201">Click **Manage users**.</span></span>
3. <span data-ttu-id="b01af-202">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-202">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="b01af-203">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-203">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="b01af-204">사용자 추가를 마쳤으면 **저장** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-204">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="b01af-205">그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b01af-205">Assign a policy package to a group</span></span>

<span data-ttu-id="b01af-206">**이 기능은 비공개 미리 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="b01af-206">**This feature is in private preview**</span></span>

<span data-ttu-id="b01af-207">그룹에 정책 패키지 할당을 사용 하 여 보안 그룹 또는 배포 목록 등의 사용자 그룹에 여러 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-207">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="b01af-208">정책 할당은 선행 규칙에 따라 그룹의 구성원에 게 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-208">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="b01af-209">그룹에서 구성원이 추가 되거나 제거 되 면 그에 따라 상속 된 정책 할당이 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-209">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="b01af-210">이 방법은 최대 5만 사용자 그룹에 사용 하는 것이 좋지만 대규모 그룹 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-210">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="b01af-211">자세히 알아보려면 [그룹에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-group)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b01af-211">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="b01af-212">사용자의 대규모 집합 (일괄 처리)에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b01af-212">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="b01af-213">일괄 처리 정책 패키지 할당을 사용 하 여 한 번에 대규모 사용자 집합에 정책 패키지를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-213">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="b01af-214">[CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet을 사용 하 여 할당 하려는 사용자 및 정책 패키지의 일괄 처리를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-214">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="b01af-215">할당이 백그라운드 작업으로 처리 되 고 각 일괄 처리에 대 한 작업 ID가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-215">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="b01af-216">일괄 처리에는 최대 5000 명의 사용자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-216">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="b01af-217">개체 Id, UPN, SIP 주소 또는 전자 메일 주소로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-217">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="b01af-218">자세한 내용은 [사용자 일괄 처리에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b01af-218">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b01af-219">문제 해결</span><span class="sxs-lookup"><span data-stu-id="b01af-219">Troubleshooting</span></span>

<span data-ttu-id="b01af-220">**정책 패키지를 할당할 때 오류가 표시 되는 경우**</span><span class="sxs-lookup"><span data-stu-id="b01af-220">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="b01af-221">패키지에서 하나 이상의 정책이 성공적으로 만들어지거나 적용 되지 않은 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-221">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="b01af-222">정책 패키지를 사용자에 게 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-222">Reassign the policy package to your users.</span></span> <span data-ttu-id="b01af-223">작업을 다시 시도 하면 일반적으로이 문제가 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b01af-223">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="b01af-224">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b01af-224">Related topics</span></span>

[<span data-ttu-id="b01af-225">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b01af-225">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="b01af-226">.EDU 관리자를 위한 팀 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="b01af-226">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="b01af-227">의료에 대 한 팀 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="b01af-227">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="b01af-228">정부용 팀 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="b01af-228">Teams policy packages for government</span></span>](policy-packages-gov.md)
