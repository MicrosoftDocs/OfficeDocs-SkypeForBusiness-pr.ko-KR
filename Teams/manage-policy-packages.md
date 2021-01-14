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
description: Microsoft Teams에서 정책 패키지를 사용 및 관리하여 사용자 그룹에 대한 정책을 관리할 때 일관성을 단순화하고, 간소화하고, 일관성을 제공하는 방법을 배워야 합니다.
ms.openlocfilehash: 9718751ea1d34692718b63cbe90ee6e694577c21
ms.sourcegitcommit: c537b1cf03e7ac5d07f2fbf4ba73d73c510f3d96
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2021
ms.locfileid: "49862587"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="12f9b-103">Microsoft Teams에서 정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="12f9b-103">Manage policy packages in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="12f9b-104">이 문서에서 설명하는 기능 중 하나인 사용자 지정 정책 [패키지는](#custom-policy-packages)현재 비공개 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-104">One of the features discussed in this article, [custom policy packages](#custom-policy-packages), is currently in private preview.</span></span>

<span data-ttu-id="12f9b-105">Microsoft Teams의 정책 패키지는 조직에서 비슷한 역할이 있는 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-105">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="12f9b-106">조직 전체의 사용자 그룹에 대한 정책을 관리할 때 일관성을 단순화하고, 간소화하고, 일관성을 제공하는 정책 패키지를 구축했습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-106">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="12f9b-107">Teams에 포함된 [정책 패키지를](#policy-packages-included-in-teams) 사용하거나 사용자 [지정](#custom-policy-packages) 정책 패키지(비공개 미리 보기)를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-107">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages) (in private preview).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="관리 센터의 정책 패키지 페이지의 스크린샷":::

<span data-ttu-id="12f9b-109">정책 패키지의 정책 설정을 사용자의 요구에 맞게 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-109">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="12f9b-110">패키지에서 정책 설정을 변경하면 해당 패키지에 할당된 모든 사용자가 업데이트된 설정을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-110">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="12f9b-111">Microsoft Teams 관리 센터 또는 PowerShell을 사용하여 정책 패키지를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-111">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="12f9b-112">정책 패키지란?</span><span class="sxs-lookup"><span data-stu-id="12f9b-112">What is a policy package?</span></span>

<span data-ttu-id="12f9b-113">정책 패키지를 사용하면 조직 전체의 특정 사용자 집합에 대해 허용하거나 제한하려는 Teams 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-113">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="12f9b-114">Teams의 각 정책 패키지는 사용자 역할을 중심으로 디자인된 것으로, 해당 역할에 일반적인 공동 작업 및 통신 활동을 지원하는 미리 정의된 정책 및 정책 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-114">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="12f9b-115">정책 패키지는 다음 Teams 정책 유형을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-115">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="12f9b-116">메시징 정책</span><span class="sxs-lookup"><span data-stu-id="12f9b-116">Messaging policy</span></span>
- <span data-ttu-id="12f9b-117">모임 정책</span><span class="sxs-lookup"><span data-stu-id="12f9b-117">Meeting policy</span></span>
- <span data-ttu-id="12f9b-118">앱 설정 정책</span><span class="sxs-lookup"><span data-stu-id="12f9b-118">App setup policy</span></span>
- <span data-ttu-id="12f9b-119">통화 정책</span><span class="sxs-lookup"><span data-stu-id="12f9b-119">Calling policy</span></span>
- <span data-ttu-id="12f9b-120">라이브 이벤트 정책</span><span class="sxs-lookup"><span data-stu-id="12f9b-120">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="12f9b-121">Teams에 포함된 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="12f9b-121">Policy packages included in Teams</span></span>

<span data-ttu-id="12f9b-122">Teams에는 현재 다음과 같은 정책 패키지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-122">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="12f9b-123">**패키지 이름**</span><span class="sxs-lookup"><span data-stu-id="12f9b-123">**Package name**</span></span>  |<span data-ttu-id="12f9b-124">**설명**</span><span class="sxs-lookup"><span data-stu-id="12f9b-124">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="12f9b-125">교육(고등 교육 학생)</span><span class="sxs-lookup"><span data-stu-id="12f9b-125">Education (Higher education student)</span></span>    |<span data-ttu-id="12f9b-126">고등학교 학생에게 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-126">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="12f9b-127">교육(초등학교 학생)</span><span class="sxs-lookup"><span data-stu-id="12f9b-127">Education (Primary school student)</span></span>   |<span data-ttu-id="12f9b-128">주 학생에게 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-128">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="12f9b-129">교육(중등 학생)</span><span class="sxs-lookup"><span data-stu-id="12f9b-129">Education (Secondary school student)</span></span>    |<span data-ttu-id="12f9b-130">보조 학생에게 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-130">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="12f9b-131">교육(교사)</span><span class="sxs-lookup"><span data-stu-id="12f9b-131">Education (Teacher)</span></span>    |<span data-ttu-id="12f9b-132">교사에게 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-132">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="12f9b-133">교육(원격 학습을 사용하는 초등학교 교사)</span><span class="sxs-lookup"><span data-stu-id="12f9b-133">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="12f9b-134">초등학교 교사에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-134">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="12f9b-135">교육(원격 학습을 사용하는 초등학교 학생)</span><span class="sxs-lookup"><span data-stu-id="12f9b-135">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="12f9b-136">초등학교 학생에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-136">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="12f9b-137">프런트라인 관리자</span><span class="sxs-lookup"><span data-stu-id="12f9b-137">Frontline manager</span></span> |<span data-ttu-id="12f9b-138">정책 집합을 만들고 조직의 Fronttline 관리자에게 해당 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-138">Creates a set of policies and applies those settings to Fronttline managers in your organization.</span></span> |
|<span data-ttu-id="12f9b-139">Fronttline Worker</span><span class="sxs-lookup"><span data-stu-id="12f9b-139">Fronttline worker</span></span> |<span data-ttu-id="12f9b-140">정책 집합을 만들고 조직의 프런트라인 작업자에게 해당 설정을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-140">Creates a set of policies and applies those settings to Fronttline workers in your organization.</span></span> |
|<span data-ttu-id="12f9b-141">의료 의료 의료진</span><span class="sxs-lookup"><span data-stu-id="12f9b-141">Healthcare clinical worker</span></span>  |<span data-ttu-id="12f9b-142">등록된 간호사, 간호사, 의사, 사회복지사와 같은 의료 근로자가 채팅, 통화, 교대 근무 관리 및 모임에 대한 모든 권한을 부여하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-142">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="12f9b-143">의료 정보 작업자</span><span class="sxs-lookup"><span data-stu-id="12f9b-143">Healthcare information worker</span></span>  |<span data-ttu-id="12f9b-144">IT 직원, 정보 보호 담당자, 재무 담당자 및 규정 준수 담당자와 같은 정보 근로자들에게 채팅, 통화 및 모임에 대한 모든 권한을 부여하는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-144">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="12f9b-145">의료 환자실</span><span class="sxs-lookup"><span data-stu-id="12f9b-145">Healthcare patient room</span></span>  |<span data-ttu-id="12f9b-146">의료 조직의 환자 방에 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-146">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="12f9b-147">중소기업 사용자(Business Voice)</span><span class="sxs-lookup"><span data-stu-id="12f9b-147">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="12f9b-148">비즈니스 음성 환경용 앱을 포함하는 앱 설정 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-148">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="12f9b-149">중소기업 사용자(Business Voice 없이)</span><span class="sxs-lookup"><span data-stu-id="12f9b-149">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="12f9b-150">중소기업 Teams 사용자(비 비즈니스 음성 환경)에 관련된 앱 설정 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-150">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="12f9b-151">공공 안전 책임자</span><span class="sxs-lookup"><span data-stu-id="12f9b-151">Public safety officer</span></span>   |<span data-ttu-id="12f9b-152">조직의 공공 안전 책임자에 적용되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-152">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="12f9b-153">향후 Teams 릴리스에서 정책 패키지를 더 추가할 예정이니, 최신 정보를 다시 확인해 보시겠어요.</span><span class="sxs-lookup"><span data-stu-id="12f9b-153">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="12f9b-154">각 개별 정책에는 정책 패키지의 이름이 지정되어 정책 패키지에 연결된 정책을 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-154">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="12f9b-155">예를 들어 학교의 교사에게 교육(교사) 정책 패키지를 할당하면 패키지의 각 정책에 대해 Education_Teacher 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-155">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![교육(교사) 정책 패키지 스크린샷](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="12f9b-157">사용자 지정 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="12f9b-157">Custom policy packages</span></span>

<span data-ttu-id="12f9b-158">**이 기능은 비공개 리미 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="12f9b-158">**This feature is in private preview**</span></span>

<span data-ttu-id="12f9b-159">사용자 지정 정책 패키지를 사용하면 조직에서 비슷한 역할을 하는 사용자에 대한 자체 정책 집합을 번들로 묶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-159">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="12f9b-160">필요한 정책 유형 및 정책을 추가하여 사용자 자신의 정책 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-160">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="12f9b-161">새 사용자 지정 정책 패키지를 만들 경우:</span><span class="sxs-lookup"><span data-stu-id="12f9b-161">To create a new custom policy package:</span></span>

1. <span data-ttu-id="12f9b-162">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 정책 패키지를 선택한 다음 **추가를** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12f9b-162">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>
    :::image type="content" source="media/policy-packages-add.png" alt-text="관리 센터의 정책 패키지 페이지의 추가 단추 스크린샷":::
2. <span data-ttu-id="12f9b-164">패키지의 이름과 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-164">Enter a name and description for your package.</span></span>
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="새 사용자 지정 정책 패키지를 추가하는 스크린샷":::
3. <span data-ttu-id="12f9b-166">패키지에 포함할 정책 유형 및 정책 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-166">Select the policy types and policy names to include in the package.</span></span>
4. <span data-ttu-id="12f9b-167">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-167">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="12f9b-168">정책 패키지를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="12f9b-168">How to use policy packages</span></span>

<span data-ttu-id="12f9b-169">다음은 조직에서 정책 패키지를 사용하는 방법을 간략하게 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-169">The following outlines how to use policy packages in your organization.</span></span>

![정책 패키지를 사용하는 방법 개요](media/manage-policy-packages-overview.png)

- <span data-ttu-id="12f9b-171">**[보기:](#view-the-settings-of-a-policy-in-a-policy-package)** 정책 패키지에서 정책을 본다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-171">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="12f9b-172">그런 다음 패키지를 할당하기 전에 패키지에서 각 정책의 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-172">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="12f9b-173">각 설정을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-173">Make sure that you understand each setting.</span></span> <span data-ttu-id="12f9b-174">미리 정의한 값이 조직에 적합한지 또는 조직의 요구에 따라 더 제한적이거나 유의적으로 변경해야 하는지 여부를 결정하세요.</span><span class="sxs-lookup"><span data-stu-id="12f9b-174">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="12f9b-175">정책이 삭제된 경우 설정을 볼 수 있지만 설정을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-175">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="12f9b-176">정책 패키지를 할당할 때 미리 정의한 설정으로 삭제된 정책이 다시 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-176">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="12f9b-177">**[사용자](#customize-policies-in-a-policy-package)** 지정: 정책 패키지의 정책 설정을 조직의 요구에 맞게 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-177">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="12f9b-178">**[할당:](#assign-a-policy-package)** 사용자에게 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-178">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="12f9b-179">패키지를 할당한 후 정책 패키지에서 정책 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-179">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="12f9b-180">정책 설정에 대한 모든 변경 내용은 패키지가 할당된 사용자에게 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-180">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="12f9b-181">Microsoft Teams 관리 센터에서 정책 패키지를 보고, 할당하고, 사용자 지정하는 방법에 대한 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-181">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="12f9b-182">정책 패키지에서 정책 설정 보기</span><span class="sxs-lookup"><span data-stu-id="12f9b-182">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="12f9b-183">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 정책 패키지를 선택한 다음 패키지 이름 왼쪽을 클릭하여 정책 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-183">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="12f9b-184">보하려는 정책을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-184">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="12f9b-185">정책 패키지에서 정책 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="12f9b-185">Customize policies in a policy package</span></span>

<span data-ttu-id="12f9b-186">정책 패키지 페이지를 통해 또는  Microsoft Teams 관리 센터의 정책 페이지로 직접 이동하여 정책 설정을 편집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-186">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="12f9b-187">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 다음 중 하나를 합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-187">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="12f9b-188">정책 **패키지를** 클릭한 다음 패키지 이름 왼쪽을 클릭하여 정책 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-188">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="12f9b-189">정책 유형을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-189">Click the policy type.</span></span>  <span data-ttu-id="12f9b-190">예를 들어 메시징 정책을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12f9b-190">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="12f9b-191">편집할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-191">Select the policy you want to edit.</span></span> <span data-ttu-id="12f9b-192">정책 패키지에 연결된 정책의 이름은 정책 패키지와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-192">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="12f9b-193">원하는 내용을 변경한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12f9b-193">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="12f9b-194">정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="12f9b-194">Assign a policy package</span></span> 

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="12f9b-195">한 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="12f9b-195">Assign a policy package to one user</span></span>

1. <span data-ttu-id="12f9b-196">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자** 로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-196">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="12f9b-197">사용자의 페이지에서 정책을 클릭한 다음 정책 패키지 옆에 있는 **편집을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12f9b-197">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="12f9b-198">정책 패키지 **할당 창에서** 할당할 패키지를 선택한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12f9b-198">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="12f9b-199">여러 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="12f9b-199">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="12f9b-200">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 정책 패키지로 이동한 다음 패키지 이름 왼쪽을 클릭하여 할당하려는 정책 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-200">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="12f9b-201">사용자 **관리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12f9b-201">Click **Manage users**.</span></span>
3. <span data-ttu-id="12f9b-202">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-202">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="12f9b-203">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-203">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="12f9b-204">사용자 추가를 마쳤을 때 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12f9b-204">When you're finished adding users, click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="12f9b-205">그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="12f9b-205">Assign a policy package to a group</span></span>

<span data-ttu-id="12f9b-206">**이 기능은 비공개 리미 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="12f9b-206">**This feature is in private preview**</span></span>

<span data-ttu-id="12f9b-207">그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-207">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="12f9b-208">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-208">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="12f9b-209">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-209">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="12f9b-210">이 방법은 최대 50,000명의 사용자가 있는 그룹에 적합하지만, 더 큰 그룹에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-210">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="12f9b-211">자세한 내용은 [그룹에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-group)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12f9b-211">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="12f9b-212">대규모 사용자 집합(배치)에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="12f9b-212">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="12f9b-213">한 번에 많은 사용자에게 정책 패키지를 할당하려면 배치 정책 패키지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-213">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="12f9b-214">[New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet을 사용하여 대규모 사용자와 할당하려는 정책 패키지를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-214">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="12f9b-215">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-215">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="12f9b-216">배치에는 최대 5천 명의 사용자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-216">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="12f9b-217">개체 ID, UPN, SIP 주소 또는 전자 메일 주소로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-217">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="12f9b-218">자세한 내용은 [배치 사용자에게 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12f9b-218">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="12f9b-219">문제 해결</span><span class="sxs-lookup"><span data-stu-id="12f9b-219">Troubleshooting</span></span>

<span data-ttu-id="12f9b-220">**정책 패키지를 할당할 때 오류가 발생합니다.**</span><span class="sxs-lookup"><span data-stu-id="12f9b-220">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="12f9b-221">패키지에서 하나 이상의 정책이 만들어지거나 성공적으로 적용되지 않은 경우 이 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-221">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="12f9b-222">사용자에게 정책 패키지를 다시 재할당합니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-222">Reassign the policy package to your users.</span></span> <span data-ttu-id="12f9b-223">작업을 다시 시도하는 경우 일반적으로 이 문제가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="12f9b-223">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="12f9b-224">관련 항목</span><span class="sxs-lookup"><span data-stu-id="12f9b-224">Related topics</span></span>

[<span data-ttu-id="12f9b-225">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="12f9b-225">Assign policies to your users in Teams</span></span>](assign-policies.md)

[<span data-ttu-id="12f9b-226">EDU 관리자를 위한 Teams 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="12f9b-226">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)

[<span data-ttu-id="12f9b-227">의료를 위한 Teams 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="12f9b-227">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)

[<span data-ttu-id="12f9b-228">정부용 Teams 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="12f9b-228">Teams policy packages for government</span></span>](policy-packages-gov.md)
