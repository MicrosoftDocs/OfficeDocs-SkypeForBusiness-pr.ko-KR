---
title: 정부용 팀 정책 패키지
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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 정부 조직의 팀 정책 패키지를 사용 하 고 관리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804038"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="df016-103">정부용 팀 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="df016-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="df016-104">현재 Microsoft 365 정부 GCC High 또는 DoD 배포에서는 정책 패키지를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="df016-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="df016-105">개요</span><span class="sxs-lookup"><span data-stu-id="df016-105">Overview</span></span>

<span data-ttu-id="df016-106">Microsoft 팀의 [정책 패키지](manage-policy-packages.md) 는 조직에서 유사한 역할을 갖는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="df016-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="df016-107">정책 패키지는 정책 관리 시 이를 단순화 및 간소화하고 일관성을 제공하도록 돕습니다.</span><span class="sxs-lookup"><span data-stu-id="df016-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="df016-108">사용자의 요구에 맞게 패키지의 정책 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df016-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="df016-109">정책 패키지의 정책 설정을 변경 하면 해당 패키지에 할당 된 모든 사용자가 업데이트 된 설정을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="df016-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="df016-110">Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책 패키지를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df016-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="df016-111">정책 패키지는 패키지에 따라 다음에 대 한 정책을 미리 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="df016-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="df016-112">메시징</span><span class="sxs-lookup"><span data-stu-id="df016-112">Messaging</span></span>
- <span data-ttu-id="df016-113">모임</span><span class="sxs-lookup"><span data-stu-id="df016-113">Meetings</span></span>
- <span data-ttu-id="df016-114">통화</span><span class="sxs-lookup"><span data-stu-id="df016-114">Calling</span></span>
- <span data-ttu-id="df016-115">앱 설정</span><span class="sxs-lookup"><span data-stu-id="df016-115">App setup</span></span>
- <span data-ttu-id="df016-116">라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="df016-116">Live events</span></span>

<span data-ttu-id="df016-117">현재 팀에는 다음과 같은 정부용 정책 패키지가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df016-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="df016-118">Microsoft 팀 관리 센터의 패키지 이름</span><span class="sxs-lookup"><span data-stu-id="df016-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="df016-119">최적 용도</span><span class="sxs-lookup"><span data-stu-id="df016-119">Best used for</span></span>|<span data-ttu-id="df016-120">설명</span><span class="sxs-lookup"><span data-stu-id="df016-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="df016-121">공개 안전 책임자</span><span class="sxs-lookup"><span data-stu-id="df016-121">Public safety officer</span></span>  |<span data-ttu-id="df016-122">정부 조직의 공개 보안 관리 책임자</span><span class="sxs-lookup"><span data-stu-id="df016-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="df016-123">조직의 공개 보안 책임자에 게 적용 되는 정책 및 정책 설정 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="df016-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="df016-124">Firstline manager</span><span class="sxs-lookup"><span data-stu-id="df016-124">Firstline manager</span></span>  |<span data-ttu-id="df016-125">정부 조직의 firstline 관리자</span><span class="sxs-lookup"><span data-stu-id="df016-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="df016-126">조직의 Firstline 관리자에 게 정책 집합을 만들고 해당 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df016-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="df016-127">Firstline worker</span><span class="sxs-lookup"><span data-stu-id="df016-127">Firstline worker</span></span>  |<span data-ttu-id="df016-128">정부 조직의 firstline Worker</span><span class="sxs-lookup"><span data-stu-id="df016-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="df016-129">정책 집합을 만들고 조직의 Firstline Worker에 해당 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="df016-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![건강 보험 정책 패키지 스크린샷](media/policy-packages-gov.png)

<span data-ttu-id="df016-131">정책 패키지에 연결 된 정책을 쉽게 식별할 수 있도록 각 개별 정책에 정책 패키지의 이름이 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df016-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="df016-132">예를 들어 조직의 사용자에 게 공용 보안 책임자 정책 패키지를 할당 하면 패키지의 각 정책에 대 한 PublicSafety_Officer 라는 정책이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="df016-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![의료 임상 작업자 패키지의 정책 스크린샷](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="df016-134">정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="df016-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="df016-135">보기</span><span class="sxs-lookup"><span data-stu-id="df016-135">View</span></span>

<span data-ttu-id="df016-136">패키지를 할당 하기 전에 정책 패키지의 각 정책에 대 한 설정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="df016-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="df016-137">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지**를 선택 하 고 패키지 이름을 선택한 다음 정책 이름을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="df016-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="df016-138">미리 정의 된 값이 조직에 적합 한지 아니면 조직의 요구 사항에 따라 더 엄격 하 게 또는 lenient 사용자 지정 해야 하는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df016-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="df016-139">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="df016-139">Customize</span></span>

<span data-ttu-id="df016-140">필요에 따라 정책 패키지의 정책 설정을 조직의 필요에 맞게 사용자 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="df016-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="df016-141">정책 설정에 대 한 변경 내용은 패키지를 할당 한 사용자에 게 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df016-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="df016-142">정책 패키지의 정책 설정을 편집 하려면 Microsoft 팀 관리 센터에서 정책 패키지를 선택 하 고 편집 하려는 정책의 이름을 선택한 다음 **편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="df016-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="df016-143">정책 패키지를 할당 한 후에는 패키지의 정책 설정을 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df016-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="df016-144">자세히 알아보려면 [정책 패키지의 정책 사용자 지정](manage-policy-packages.md#customize-policies-in-a-policy-package)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df016-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="df016-145">배정할</span><span class="sxs-lookup"><span data-stu-id="df016-145">Assign</span></span>

<span data-ttu-id="df016-146">사용자에 게 정책 패키지를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="df016-146">Assign the policy package to users.</span></span> <span data-ttu-id="df016-147">한 명 또는 여러 명의 사용자에 게 정책 패키지를 할당 하려면 **사용자 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="df016-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="df016-148">[PowerShell을 사용](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) 하 여 대규모 사용자 일괄 처리에 정책 패키지를 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df016-148">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="df016-149">Microsoft 팀 관리 센터 또는 PowerShell을 사용 하 여 정책 패키지를 할당 하는 방법에 대 한 단계는 [정책 패키지 할당](manage-policy-packages.md#assign-a-policy-package)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="df016-149">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![관리 센터에서 정책 패키지를 할당 하는 방법 스크린샷](media/policy-packages-gov-assign.png)

<span data-ttu-id="df016-151">사용자에 게 정책이 할당 된 후 나중에 다른 정책을 할당 하는 경우에는 가장 최근의 할당이 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df016-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="df016-152">관련 항목</span><span class="sxs-lookup"><span data-stu-id="df016-152">Related topics</span></span>

[<span data-ttu-id="df016-153">Teams에서 정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="df016-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="df016-154">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="df016-154">Assign policies to your users in Teams</span></span>](assign-policies.md) 
