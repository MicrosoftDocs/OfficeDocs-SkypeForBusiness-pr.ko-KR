---
title: Microsoft Teams에서 정책 패키지 관리
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams에서 정책 패키지를 사용 및 관리하여 사용자 그룹에 대한 정책을 관리할 때 일관성을 단순화하고 간소화하고, 일관성을 제공하는 방법을 알아보고 있습니다.
ms.openlocfilehash: 1173f5a626d6ea559dadd75149a0517f515d821b
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51699337"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="4b67e-103">Microsoft Teams에서 정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="4b67e-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="4b67e-104">Microsoft Teams의 정책 패키지는 조직에서 유사한 역할을 가진 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="4b67e-105">조직 전체의 사용자 그룹에 대한 정책을 관리할 때 일관성을 제공, 간소화 및 지원하기 위한 정책 패키지를 구축했습니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="4b67e-106">[Teams에 포함된](#policy-packages-included-in-teams) 정책 패키지를 사용하거나 사용자 지정 정책 패키지를 만들 [수 있습니다.](#custom-policy-packages)</span><span class="sxs-lookup"><span data-stu-id="4b67e-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="관리 센터의 정책 패키지 페이지의 스크린샷":::

<span data-ttu-id="4b67e-108">사용자의 요구에 맞게 정책 패키지에서 정책 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="4b67e-109">패키지의 정책 설정을 변경하면 해당 패키지에 할당된 모든 사용자가 업데이트된 설정을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="4b67e-110">Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 정책 패키지를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="4b67e-111">정책 패키지란?</span><span class="sxs-lookup"><span data-stu-id="4b67e-111">What is a policy package?</span></span>

<span data-ttu-id="4b67e-112">정책 패키지를 사용하면 조직 전체의 특정 사용자 집합을 허용하거나 제한하려는 Teams 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-112">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="4b67e-113">Teams의 각 정책 패키지는 사용자 역할을 중심으로 설계하고 해당 역할에 대한 일반적인 공동 작업 및 통신 활동을 지원하는 미리 정의된 정책 및 정책 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-113">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="4b67e-114">정책 패키지는 다음 Teams 정책 유형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-114">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="4b67e-115">메시징 정책</span><span class="sxs-lookup"><span data-stu-id="4b67e-115">Messaging policy</span></span>
- <span data-ttu-id="4b67e-116">모임 정책</span><span class="sxs-lookup"><span data-stu-id="4b67e-116">Meeting policy</span></span>
- <span data-ttu-id="4b67e-117">앱 설정 정책</span><span class="sxs-lookup"><span data-stu-id="4b67e-117">App setup policy</span></span>
- <span data-ttu-id="4b67e-118">통화 정책</span><span class="sxs-lookup"><span data-stu-id="4b67e-118">Calling policy</span></span>
- <span data-ttu-id="4b67e-119">라이브 이벤트 정책</span><span class="sxs-lookup"><span data-stu-id="4b67e-119">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="4b67e-120">Teams에 포함된 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="4b67e-120">Policy packages included in Teams</span></span>

<span data-ttu-id="4b67e-121">현재 팀은 다음과 같은 정책 패키지를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-121">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="4b67e-122">패키지 이름</span><span class="sxs-lookup"><span data-stu-id="4b67e-122">Package name</span></span> | <span data-ttu-id="4b67e-123">설명</span><span class="sxs-lookup"><span data-stu-id="4b67e-123">Description</span></span> |
|---------|---------|
|<span data-ttu-id="4b67e-124">교육(고등 교육 학생)</span><span class="sxs-lookup"><span data-stu-id="4b67e-124">Education (Higher education student)</span></span>    |<span data-ttu-id="4b67e-125">고등 교육 학생들에게 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-125">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="4b67e-126">교육(초등학생)</span><span class="sxs-lookup"><span data-stu-id="4b67e-126">Education (Primary school student)</span></span>   |<span data-ttu-id="4b67e-127">기본 학생에 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-127">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="4b67e-128">교육(중등학생)</span><span class="sxs-lookup"><span data-stu-id="4b67e-128">Education (Secondary school student)</span></span>    |<span data-ttu-id="4b67e-129">중등 학생에게 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-129">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="4b67e-130">교육(교사)</span><span class="sxs-lookup"><span data-stu-id="4b67e-130">Education (Teacher)</span></span>    |<span data-ttu-id="4b67e-131">교사에게 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-131">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="4b67e-132">교육(원격 학습을 사용하는 초등학교 교사)</span><span class="sxs-lookup"><span data-stu-id="4b67e-132">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="4b67e-133">초등학교 교사에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-133">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="4b67e-134">교육(원격 학습을 사용하는 초등학생)</span><span class="sxs-lookup"><span data-stu-id="4b67e-134">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="4b67e-135">초등학교 학생에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-135">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="4b67e-136">프런트라인 관리자</span><span class="sxs-lookup"><span data-stu-id="4b67e-136">Frontline manager</span></span> |<span data-ttu-id="4b67e-137">정책 집합을 만들고 해당 설정을 조직의 Frontline 관리자에게 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-137">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="4b67e-138">프런트라인 작업자</span><span class="sxs-lookup"><span data-stu-id="4b67e-138">Frontline worker</span></span> |<span data-ttu-id="4b67e-139">정책 집합을 만들고 조직의 Frontline 작업자에게 해당 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-139">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="4b67e-140">의료 임상 연구원</span><span class="sxs-lookup"><span data-stu-id="4b67e-140">Healthcare clinical worker</span></span>  |<span data-ttu-id="4b67e-141">등록된 간호사, 유료 간호사, 의사 및 사회복지사와 같은 의료진에게 채팅, 통화, 이동 관리 및 회의에 대한 완전한 액세스를 제공하는 정책 및 정책 설정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-141">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="4b67e-142">의료 정보 직원</span><span class="sxs-lookup"><span data-stu-id="4b67e-142">Healthcare information worker</span></span>  |<span data-ttu-id="4b67e-143">IT 직원, 정보 전문가, 재무 담당자 및 규정 준수 담당자와 같은 정보 직원에게 채팅, 통화 및 모임에 대한 전체 액세스 권한을 부여하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-143">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="4b67e-144">의료 환자실</span><span class="sxs-lookup"><span data-stu-id="4b67e-144">Healthcare patient room</span></span>  |<span data-ttu-id="4b67e-145">의료 조직의 환자실에 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-145">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="4b67e-146">중소기업 사용자(비즈니스 음성)</span><span class="sxs-lookup"><span data-stu-id="4b67e-146">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="4b67e-147">비즈니스 음성 환경용 앱을 포함하는 앱 설정 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-147">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="4b67e-148">중소기업 사용자(비즈니스 음성이 없는 경우)</span><span class="sxs-lookup"><span data-stu-id="4b67e-148">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="4b67e-149">중소기업 Teams 사용자(비기업 음성 환경)에 관련된 앱 설정 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-149">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="4b67e-150">공공 안전 책임자</span><span class="sxs-lookup"><span data-stu-id="4b67e-150">Public safety officer</span></span>   |<span data-ttu-id="4b67e-151">조직의 공공 안전 책임자에 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-151">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="4b67e-152">Teams의 향후 릴리스에서 더 많은 정책 패키지가 추가될 예정이니 최신 정보를 다시 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4b67e-152">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="4b67e-153">각 개별 정책은 정책 패키지의 이름이 지정되며 정책 패키지에 연결된 정책을 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-153">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="4b67e-154">예를 들어 학교의 교사에게 교육(교사) 정책 패키지를 할당하면 패키지의 각 정책에 대해 Education_Teacher 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-154">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![교육(교사) 정책 패키지 스크린샷](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="4b67e-156">사용자 지정 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="4b67e-156">Custom policy packages</span></span>

<span data-ttu-id="4b67e-157">**사용자 지정 정책 패키지는 GCC(Government Community Cloud)에 대해 아직 사용할 수 없습니다.**</span><span class="sxs-lookup"><span data-stu-id="4b67e-157">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="4b67e-158">사용자 지정 정책 패키지를 사용하면 조직에서 비슷한 역할을 하는 사용자에 대한 자체 정책 집합을 번들로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-158">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="4b67e-159">필요한 정책 유형 및 정책을 추가하여 사용자만의 정책 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-159">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="4b67e-160">새 사용자 지정 정책 패키지를 만들 경우:</span><span class="sxs-lookup"><span data-stu-id="4b67e-160">To create a new custom policy package:</span></span>

1. <span data-ttu-id="4b67e-161">Microsoft Teams 관리 센터의 왼쪽 탐색에서 정책 패키지를 **선택한** 다음 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4b67e-161">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="관리 센터의 정책 패키지 페이지의 추가 단추 스크린샷":::

2. <span data-ttu-id="4b67e-163">패키지에 대한 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-163">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="새 사용자 지정 정책 패키지 추가 스크린샷":::

3. <span data-ttu-id="4b67e-165">패키지에 포함할 정책 형식 및 정책 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-165">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="4b67e-166">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-166">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="4b67e-167">정책 패키지를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="4b67e-167">How to use policy packages</span></span>

<span data-ttu-id="4b67e-168">다음에서는 조직에서 정책 패키지를 사용하는 방법을 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-168">The following outlines how to use policy packages in your organization.</span></span>

![정책 패키지를 사용하는 방법 개요](media/manage-policy-packages-overview.png)

- <span data-ttu-id="4b67e-170">**[보기](#view-the-settings-of-a-policy-in-a-policy-package)**: 정책 패키지에서 정책을 본다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-170">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="4b67e-171">그런 다음 패키지를 할당하기 전에 패키지의 각 정책 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-171">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="4b67e-172">각 설정을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-172">Make sure that you understand each setting.</span></span> <span data-ttu-id="4b67e-173">미리 정의된 값이 조직에 적합한지 또는 조직의 요구에 따라 더 제한적이거나 부적격으로 변경해야 하는지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-173">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="4b67e-174">정책이 삭제된 경우 설정을 계속 볼 수 있지만 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-174">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="4b67e-175">정책 패키지를 할당할 때 미리 정의된 설정으로 삭제된 정책이 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-175">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="4b67e-176">**[사용자 지정](#customize-policies-in-a-policy-package)**: 조직의 요구에 맞게 정책 패키지의 정책 설정을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-176">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="4b67e-177">**[할당](#assign-a-policy-package)**: 사용자에게 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-177">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="4b67e-178">패키지를 할당한 후 정책 패키지에서 정책 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-178">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="4b67e-179">정책 설정에 대한 모든 변경 내용은 패키지가 할당된 사용자에게 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-179">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="4b67e-180">다음은 Microsoft Teams 관리 센터에서 정책 패키지를 보고, 할당하고, 사용자 지정하는 방법에 대한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-180">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="4b67e-181">정책 패키지에서 정책 설정 보기</span><span class="sxs-lookup"><span data-stu-id="4b67e-181">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="4b67e-182">Microsoft Teams 관리 센터의 왼쪽 탐색에서 정책 패키지를 선택한 다음, 패키지 이름의 왼쪽을 클릭하여 정책 패키지를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="4b67e-182">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="4b67e-183">볼 정책을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-183">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="4b67e-184">정책 패키지에서 정책 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="4b67e-184">Customize policies in a policy package</span></span>

<span data-ttu-id="4b67e-185">정책 패키지 페이지를 통해 또는  Microsoft Teams 관리 센터의 정책 페이지로 직접 이동하여 정책 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-185">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="4b67e-186">Microsoft Teams 관리 센터의 왼쪽 탐색에서 다음 중 하나를 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-186">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="4b67e-187">정책 **패키지를** 클릭한 다음 패키지 이름의 왼쪽을 클릭하여 정책 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-187">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="4b67e-188">정책 유형을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-188">Click the policy type.</span></span>  <span data-ttu-id="4b67e-189">예를 들어 메시징 정책을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4b67e-189">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="4b67e-190">편집할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-190">Select the policy you want to edit.</span></span> <span data-ttu-id="4b67e-191">정책 패키지에 연결된 정책의 이름은 정책 패키지와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-191">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="4b67e-192">원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4b67e-192">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="4b67e-193">정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="4b67e-193">Assign a policy package</span></span>

<span data-ttu-id="4b67e-194">개별 사용자, 그룹 또는 사용자 일괄 처리에 정책 패키지를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b67e-194">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="4b67e-195">정책 패키지를 할당하는 방법에 대한 자세한 내용은 사용자 및 그룹에 정책 패키지 [할당을 참조하세요.](assign-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="4b67e-195">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="4b67e-196">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4b67e-196">Related topics</span></span>

- [<span data-ttu-id="4b67e-197">정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="4b67e-197">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="4b67e-198">EDU 관리자에 대한 Teams 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="4b67e-198">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="4b67e-199">의료용 Teams 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="4b67e-199">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="4b67e-200">정부용 Teams 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="4b67e-200">Teams policy packages for government</span></span>](policy-packages-gov.md)
