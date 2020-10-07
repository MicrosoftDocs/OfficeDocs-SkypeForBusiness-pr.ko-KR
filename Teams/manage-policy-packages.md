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
ms.openlocfilehash: 866183442d21ad91a83f3e9460ccd257902a0972
ms.sourcegitcommit: f4f5ad1391b472d64390180c81c2680f011a8a10
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48370602"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="fa6e9-103">Microsoft 팀에서 정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="fa6e9-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="fa6e9-104">[사용자 지정 정책 패키지](#custom-policy-packages),이 문서에서 설명 하는 기능 중 하나가 아직 출시 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), hasn't been released yet.</span></span> <span data-ttu-id="fa6e9-105">곧 비공개 미리 보기를 통해 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-105">It's coming soon to private preview.</span></span>

<span data-ttu-id="fa6e9-106">Microsoft 팀의 정책 패키지는 조직에서 유사한 역할을 갖는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-106">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="fa6e9-107">조직의 사용자 그룹에 대 한 정책을 관리할 때 일관성을 단순화 하 고 합리화 하 고 사용할 수 있도록 하는 정책 패키지를 작성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-107">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="fa6e9-108">[팀에 포함 된 정책 패키지](#policy-packages-included-in-teams) 를 사용 하거나 [고유한 사용자 지정 정책 패키지](#custom-policy-packages) (비공개 미리 보기)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-108">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="관리 센터의 정책 패키지 페이지 스크린샷":::

<span data-ttu-id="fa6e9-110">사용자의 요구에 맞게 정책 패키지의 정책 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-110">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="fa6e9-111">패키지의 정책 설정을 변경 하면 해당 패키지에 할당 된 모든 사용자가 업데이트 된 설정을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-111">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="fa6e9-112">Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책 패키지를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-112">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="fa6e9-113">정책 패키지 란?</span><span class="sxs-lookup"><span data-stu-id="fa6e9-113">What is a policy package?</span></span>

<span data-ttu-id="fa6e9-114">정책 패키지를 사용 하 여 조직 내 특정 사용자 집합에 허용 하거나 제한할 팀 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-114">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="fa6e9-115">팀의 각 정책 패키지는 사용자 역할을 중심으로 설계 되며, 해당 역할에 일반적으로 사용 되는 공동 작업 및 통신 작업을 지 원하는 미리 정의 된 정책 및 정책 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-115">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="fa6e9-116">정책 패키지는 다음 팀 정책 유형을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-116">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="fa6e9-117">메시징 정책</span><span class="sxs-lookup"><span data-stu-id="fa6e9-117">Messaging policy</span></span>
- <span data-ttu-id="fa6e9-118">모임 정책</span><span class="sxs-lookup"><span data-stu-id="fa6e9-118">Meeting policy</span></span>
- <span data-ttu-id="fa6e9-119">앱 설정 정책</span><span class="sxs-lookup"><span data-stu-id="fa6e9-119">App setup policy</span></span>
- <span data-ttu-id="fa6e9-120">통화 정책</span><span class="sxs-lookup"><span data-stu-id="fa6e9-120">Calling policy</span></span>
- <span data-ttu-id="fa6e9-121">라이브 이벤트 정책</span><span class="sxs-lookup"><span data-stu-id="fa6e9-121">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="fa6e9-122">팀에 포함 된 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="fa6e9-122">Policy packages included in Teams</span></span>

<span data-ttu-id="fa6e9-123">현재 팀에는 다음 정책 패키지가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-123">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="fa6e9-124">**패키지 이름**</span><span class="sxs-lookup"><span data-stu-id="fa6e9-124">**Package name**</span></span>  |<span data-ttu-id="fa6e9-125">**설명**</span><span class="sxs-lookup"><span data-stu-id="fa6e9-125">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="fa6e9-126">교육 (고급 교육 학생)</span><span class="sxs-lookup"><span data-stu-id="fa6e9-126">Education (Higher education student)</span></span>    |<span data-ttu-id="fa6e9-127">높은 교육 학생 들에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-127">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="fa6e9-128">교육 (주 학교 학생)</span><span class="sxs-lookup"><span data-stu-id="fa6e9-128">Education (Primary school student)</span></span>   |<span data-ttu-id="fa6e9-129">기본 학생에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-129">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="fa6e9-130">교육 (보조 학교 학생)</span><span class="sxs-lookup"><span data-stu-id="fa6e9-130">Education (Secondary school student)</span></span>    |<span data-ttu-id="fa6e9-131">보조 학생에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-131">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="fa6e9-132">교육 (교사)</span><span class="sxs-lookup"><span data-stu-id="fa6e9-132">Education (Teacher)</span></span>    |<span data-ttu-id="fa6e9-133">교사에 게 적용할 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-133">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="fa6e9-134">교육 (원격 학습을 사용 하 여 기본 학교 교사)</span><span class="sxs-lookup"><span data-stu-id="fa6e9-134">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="fa6e9-135">초등학교 교사에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-135">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="fa6e9-136">교육 (원격 학습을 사용 하는 기본 학교 학생)</span><span class="sxs-lookup"><span data-stu-id="fa6e9-136">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="fa6e9-137">초등학교 학생에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-137">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="fa6e9-138">Firstline manager</span><span class="sxs-lookup"><span data-stu-id="fa6e9-138">Firstline manager</span></span> |<span data-ttu-id="fa6e9-139">조직의 Firstline 관리자에 게 정책 집합을 만들고 해당 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-139">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span> |
|<span data-ttu-id="fa6e9-140">Firstline worker</span><span class="sxs-lookup"><span data-stu-id="fa6e9-140">Firstline worker</span></span> |<span data-ttu-id="fa6e9-141">정책 집합을 만들고 조직의 Firstline Worker에 해당 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-141">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span> |
|<span data-ttu-id="fa6e9-142">의료 임상 근로자</span><span class="sxs-lookup"><span data-stu-id="fa6e9-142">Healthcare clinical worker</span></span>  |<span data-ttu-id="fa6e9-143">등록 된 nurses, 청구 nurses, 의사, 소셜 작업자에 게 채팅, 통화, 교대 관리, 모임에 대 한 전체 액세스 등의 임상 근로자를 제공 하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-143">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="fa6e9-144">의료 정보 근로자</span><span class="sxs-lookup"><span data-stu-id="fa6e9-144">Healthcare information worker</span></span>  |<span data-ttu-id="fa6e9-145">IT 직원, informatics 스태프, 재무 담당자, 규정 준수 관리자, 채팅, 통화, 모임에 대 한 모든 액세스 권한을 제공 하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-145">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="fa6e9-146">의료 환자 실</span><span class="sxs-lookup"><span data-stu-id="fa6e9-146">Healthcare patient room</span></span>  |<span data-ttu-id="fa6e9-147">건강 관리 조직의 환자 방에 해당 하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-147">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="fa6e9-148">중소 기업 사용자 (비즈니스 음성)</span><span class="sxs-lookup"><span data-stu-id="fa6e9-148">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="fa6e9-149">비즈니스 음성 환경에 대 한 앱을 포함 하는 앱 설치 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-149">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="fa6e9-150">중소 규모 비즈니스 사용자 (비즈니스 보이스 필요 없음)</span><span class="sxs-lookup"><span data-stu-id="fa6e9-150">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="fa6e9-151">중소 규모의 비즈니스 팀 사용자 (비 비즈니스 음성 환경)와 관련 된 앱 설치 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-151">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="fa6e9-152">공개 안전 책임자</span><span class="sxs-lookup"><span data-stu-id="fa6e9-152">Public safety officer</span></span>   |<span data-ttu-id="fa6e9-153">조직의 공개 보안 책임자에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-153">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="fa6e9-154">팀의 향후 릴리스에서 정책 패키지를 더 추가 하 게 되므로 최신 정보를 다시 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-154">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="fa6e9-155">정책 패키지에 연결 된 정책을 쉽게 식별할 수 있도록 각 개별 정책에 정책 패키지의 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-155">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="fa6e9-156">예를 들어 학교에 교사 (교육) 정책 패키지를 할당 하는 경우 패키지의 각 정책에 대해 Education_Teacher 이라는 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-156">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![교사 (교육) 정책 패키지 스크린샷](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="fa6e9-158">사용자 지정 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="fa6e9-158">Custom policy packages</span></span>

<span data-ttu-id="fa6e9-159">**이 기능은 비공개 미리 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="fa6e9-159">**This feature is in private preview**</span></span>

<span data-ttu-id="fa6e9-160">사용자 지정 정책 패키지를 사용 하 여 조직에서 비슷한 역할을 갖는 사용자에 대해 자신만의 정책 집합을 번들로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-160">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="fa6e9-161">필요한 정책 유형 및 정책을 추가 하 여 고유한 정책 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-161">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="fa6e9-162">새 사용자 지정 정책 패키지를 만들려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-162">To create a new custom policy package:</span></span>

1. <span data-ttu-id="fa6e9-163">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지**를 선택한 다음 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-163">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="관리 센터의 정책 패키지 페이지에 있는 추가 단추 스크린샷":::
2. <span data-ttu-id="fa6e9-165">패키지의 이름과 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-165">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="새 사용자 지정 정책 패키지 추가 스크린샷":::
3. <span data-ttu-id="fa6e9-167">패키지에 포함할 정책 유형 및 정책 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-167">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="fa6e9-168">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-168">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="fa6e9-169">정책 패키지를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="fa6e9-169">How to use policy packages</span></span>

<span data-ttu-id="fa6e9-170">다음 개요에는 조직에서 정책 패키지를 사용 하는 방법이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-170">The following outlines how to use policy packages in your organization.</span></span>

![정책 패키지 사용 방법 개요](media/manage-policy-packages-overview.png)

- <span data-ttu-id="fa6e9-172">**[보기](#view-the-settings-of-a-policy-in-a-policy-package)**: 정책 패키지의 정책을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-172">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="fa6e9-173">그런 다음 패키지를 할당 하기 전에 패키지의 각 정책에 대 한 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-173">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="fa6e9-174">각 설정을 이해 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-174">Make sure that you understand each setting.</span></span> <span data-ttu-id="fa6e9-175">미리 정의 된 값이 조직에 적합 한지 아니면 조직의 요구 사항에 따라 더 엄격 하 게 또는 lenient 변경 해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-175">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="fa6e9-176">정책이 삭제 된 경우에도 설정을 볼 수 있지만 설정을 변경할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-176">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="fa6e9-177">정책 패키지를 할당할 때 미리 정의 된 설정을 사용 하 여 삭제 된 정책이 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-177">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="fa6e9-178">**[사용자 지정](#customize-policies-in-a-policy-package)**: 조직의 요구에 맞게 정책 패키지의 정책 설정을 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-178">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="fa6e9-179">**[Assign](#assign-a-policy-package)**: 사용자에 게 정책 패키지를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-179">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="fa6e9-180">패키지를 할당 한 후에는 정책 패키지의 정책 설정을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-180">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="fa6e9-181">정책 설정에 대 한 변경 내용은 패키지를 할당 한 사용자에 게 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-181">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="fa6e9-182">Microsoft 팀 관리 센터에서 정책 패키지를 보고 할당 하 고 사용자 지정 하는 방법에 대 한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-182">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="fa6e9-183">정책 패키지의 정책 설정 보기</span><span class="sxs-lookup"><span data-stu-id="fa6e9-183">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="fa6e9-184">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지**를 선택한 다음 패키지 이름 왼쪽을 클릭 하 여 정책 패키지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-184">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="fa6e9-185">보려는 정책을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-185">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="fa6e9-186">정책 패키지의 정책 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="fa6e9-186">Customize policies in a policy package</span></span>

<span data-ttu-id="fa6e9-187">정책 **패키지** 페이지를 통해 또는 Microsoft 팀 관리 센터의 정책 페이지로 직접 이동 하 여 정책의 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-187">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="fa6e9-188">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-188">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="fa6e9-189">**정책 패키지**를 클릭 한 다음 패키지 이름 왼쪽을 클릭 하 여 정책 패키지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-189">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="fa6e9-190">정책 유형을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-190">Click the policy type.</span></span>  <span data-ttu-id="fa6e9-191">예를 들어 **메시지 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-191">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="fa6e9-192">편집 하려는 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-192">Select the policy you want to edit.</span></span> <span data-ttu-id="fa6e9-193">정책 패키지에 연결 된 정책에는 정책 패키지와 동일한 이름이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-193">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="fa6e9-194">원하는 변경 작업을 수행한 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-194">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="fa6e9-195">정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="fa6e9-195">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="fa6e9-196">한 사용자에 게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="fa6e9-196">Assign a policy package to one user</span></span>

1. <span data-ttu-id="fa6e9-197">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-197">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="fa6e9-198">사용자의 페이지에서 **정책을**클릭 한 다음 **정책 패키지**옆에 있는 **편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-198">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="fa6e9-199">**정책 패키지 할당** 창에서 할당할 패키지를 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-199">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="fa6e9-200">여러 사용자에 게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="fa6e9-200">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="fa6e9-201">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **정책 패키지로**이동한 다음 패키지 이름 왼쪽을 클릭 하 여 할당 하려는 정책 패키지를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-201">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="fa6e9-202">**사용자 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-202">Click **Manage users**.</span></span>
3. <span data-ttu-id="fa6e9-203">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-203">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="fa6e9-204">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-204">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="fa6e9-205">사용자 추가를 마쳤으면 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-205">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="fa6e9-206">사용자의 대규모 집합 (일괄 처리)에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="fa6e9-206">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="fa6e9-207">일괄 처리 정책 패키지 할당을 사용 하 여 한 번에 대규모 사용자 집합에 정책 패키지를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-207">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="fa6e9-208">[CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet을 사용 하 여 할당 하려는 사용자 및 정책 패키지의 일괄 처리를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-208">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="fa6e9-209">할당이 백그라운드 작업으로 처리 되 고 각 일괄 처리에 대 한 작업 ID가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-209">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="fa6e9-210">일괄 처리에는 최대 5000 명의 사용자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-210">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="fa6e9-211">개체 Id, UPN, SIP 주소 또는 전자 메일 주소로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-211">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="fa6e9-212">자세한 내용은 [사용자 일괄 처리에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-212">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="fa6e9-213">문제 해결</span><span class="sxs-lookup"><span data-stu-id="fa6e9-213">Troubleshooting</span></span>

<span data-ttu-id="fa6e9-214">**정책 패키지를 할당할 때 오류가 표시 되는 경우**</span><span class="sxs-lookup"><span data-stu-id="fa6e9-214">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="fa6e9-215">패키지에서 하나 이상의 정책이 성공적으로 만들어지거나 적용 되지 않은 경우이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-215">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="fa6e9-216">정책 패키지를 사용자에 게 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-216">Reassign the policy package to your users.</span></span> <span data-ttu-id="fa6e9-217">작업을 다시 시도 하면 일반적으로이 문제가 해결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa6e9-217">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="fa6e9-218">관련 항목</span><span class="sxs-lookup"><span data-stu-id="fa6e9-218">Related topics</span></span>

[<span data-ttu-id="fa6e9-219">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="fa6e9-219">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="fa6e9-220">.EDU 관리자를 위한 팀 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="fa6e9-220">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="fa6e9-221">의료에 대 한 팀 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="fa6e9-221">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="fa6e9-222">정부용 팀 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="fa6e9-222">Teams policy packages for government</span></span>](policy-packages-gov.md)
