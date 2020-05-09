---
title: EDU 관리자용 Microsoft Teams 정책 및 정책 패키지
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Priority
search.appverid: MET150
description: 교육 또는 EDU 설정의 정책과 Microsoft Teams에서 정책 패키지를 사용하고 관리하는 방법에 대해 자세히 알아봅니다.
ms.openlocfilehash: 7aab40ce5cd3e82d884faffea29c0a1f47be6d26
ms.sourcegitcommit: c3f44fccdbd9178d30b52bb0db6f6d31a6dd174b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139231"
---
# <a name="teams-policies-and-policy-packages-for-education"></a><span data-ttu-id="9ba93-103">교육용 Teams 정책 및 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="9ba93-103">Teams Policies and Policy Packages for Education</span></span>

> [!NOTE]
> <span data-ttu-id="9ba93-104">Microsoft Teams의 정책에 대한 자세한 내용은 [Microsoft Teams에서 사용자에게 정책 할당](assign-policies.md)을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="9ba93-104">For the larger story on policies in Microsoft Teams, please review [Assign policies to your users in Microsoft Teams](assign-policies.md).</span></span>

<span data-ttu-id="9ba93-105">이 문서는 Teams에서 사용자에게 정책을 할당하는 여러 방법에 대해 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-105">It's important to note this article will cover multiple ways to assign policies to users in Teams.</span></span>

- <span data-ttu-id="9ba93-106">개별 사용자에게 수동으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-106">Manual assign to individual users.</span></span>
- <span data-ttu-id="9ba93-107">PowerShell을 통해 여러 사용자에게 일괄적으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-107">Bulk assigning via PowerShell to multiple users.</span></span>
- <span data-ttu-id="9ba93-108">개별 또는 여러 사용자에게 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-108">Assigning policy packages to individual or multiple users.</span></span>

<span data-ttu-id="9ba93-109">해당 접근 방식의 장점 및 단점은 교육 기관의 개별 요구 사항으로 설명됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-109">The advantages and disadvantages of these approaches come down to the institution's individual needs.</span></span>

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a><span data-ttu-id="9ba93-110">관리자: Microsoft Teams 정책 관리로 시작하기</span><span class="sxs-lookup"><span data-stu-id="9ba93-110">Admins: Getting started with Microsoft Teams policy management</span></span>

<span data-ttu-id="9ba93-111">Microsoft Teams의 핵심은 사용자가 모임 또는 라이브 이벤트로 이동, 채팅, 통화, 앱 사용 등의 작업을 수행할 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-111">Microsoft Teams, at its core, is about users being able to do things like go to meetings or live events, chat, make calls, and use apps.</span></span> <span data-ttu-id="9ba93-112">Teams 내에서 학생을 위한 안전한 교육 환경을 만드는 데에는 적절한 Microsoft Teams 관리 정책을 설정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-112">And setting the right Microsoft Teams admin policies is a critical step in creating a safe learning environment for students within Teams.</span></span> <span data-ttu-id="9ba93-113">관리자는 정책을 사용하여 교육 기관에서 사용자에게 제공되는 Teams 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-113">As an admin, you can use policies to control the Teams features that are available to users in your educational institute.</span></span>

<span data-ttu-id="9ba93-114">Microsoft Teams에서 확인할 수 있는 정책 영역 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-114">Here's a list of the policy areas you will find in Microsoft Teams:</span></span>

- <span data-ttu-id="9ba93-115">모임</span><span class="sxs-lookup"><span data-stu-id="9ba93-115">Meetings</span></span>
- <span data-ttu-id="9ba93-116">라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="9ba93-116">Live events</span></span>
- <span data-ttu-id="9ba93-117">통화</span><span class="sxs-lookup"><span data-stu-id="9ba93-117">Calling</span></span>
- <span data-ttu-id="9ba93-118">메시지</span><span class="sxs-lookup"><span data-stu-id="9ba93-118">Messaging</span></span>
- <span data-ttu-id="9ba93-119">Teams</span><span class="sxs-lookup"><span data-stu-id="9ba93-119">Teams</span></span>
- <span data-ttu-id="9ba93-120">앱 사용 권한</span><span class="sxs-lookup"><span data-stu-id="9ba93-120">App permissions</span></span>

:::image type="content" source="media/edu-admin-center-users.png" alt-text="적용된 정책과 함께 사용자 스크린샷":::

<span data-ttu-id="9ba93-122">관리자 자격 증명으로 로그인하여 [Microsoft Teams 관리자 센터](https://admin.teams.microsoft.com)에서 모든 Teams 정책을 손쉽게 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-122">You can easily manage all Teams policies in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) by signing in with your admin credentials.</span></span>

### <a name="where-to-find-microsoft-teams-policies"></a><span data-ttu-id="9ba93-123">Microsoft Teams 정책의 위치</span><span class="sxs-lookup"><span data-stu-id="9ba93-123">Where to find Microsoft Teams policies</span></span>

<span data-ttu-id="9ba93-124">Teams 관리 센터에 로그인하면 Teams 관리 센터의 왼쪽 탐색에서 정책 옵션을 클릭하여 관리해야 하는 Teams의 모든 영역에 대한 정책 설정으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-124">Once you've logged into the Teams admin center, you'll be able to go to the policy settings for any area of Teams you need to manage, by clicking on the policy option in the left hand navigation of the Teams admin center.</span></span> <span data-ttu-id="9ba93-125">메시지 정책의 위치 스크린샷이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-125">We've included a screenshot of the location of the messaging policies.</span></span>

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Teams 관리 센터에서 메시지 정책 위치":::

### <a name="how-to-create-and-update-a-policy-definition"></a><span data-ttu-id="9ba93-127">정책 정의의 생성 및 업데이트 방법</span><span class="sxs-lookup"><span data-stu-id="9ba93-127">How to create and update a policy definition</span></span>

<span data-ttu-id="9ba93-128">사용자에게 정책을 할당하기 전에 먼저 Teams에서 각 기능 영역에 대해 정책 정의를 추가하고 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-128">Before you assign policies to your users, you need to first add and create your policy definitions for each capability area with Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="9ba93-129">학생과 교육 담당자를 위한 다른 정책 정의를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-129">We recommend that you set different policy definitions for your students and educators.</span></span>

<span data-ttu-id="9ba93-130">기본적으로 모든 신규 사용자(학생 또는 교육 담당자)에게는 각 기능 영역에 대해 전역(조직 차원에서 기본값) 정책 정의가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-130">By default, every new user (student or educator) will be assigned the Global (Org-wide default) policy definition for each capability area.</span></span> <span data-ttu-id="9ba93-131">다음 단계를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-131">We recommend you follow these steps:</span></span>

1. <span data-ttu-id="9ba93-132">교육 담당자에게 할당할 수 있는 Teams의 각 기능 영역에 대해 사용자 지정 정책 정의를 생성합니다. (해당 단계를 수행하지 않으면 전역 정책에 대한 모든 변경 사항은 교육 담당자를 위한 정책을 생성하기 전까지 교육 담당자에게 제한됩니다.)</span><span class="sxs-lookup"><span data-stu-id="9ba93-132">Create a custom policy definition for each Teams capability area that can then be assigned to your educators (without this, any changes you make to the Global policy will restrict educators until they have their own policy).</span></span>
1. <span data-ttu-id="9ba93-133">해당 새 정책 정의를 교육 담당자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-133">Assign your educators to this new policy definition.</span></span>
1. <span data-ttu-id="9ba93-134">전역(조직 차원에서 기본값) 정책 정의를 업데이트한 후 학생에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-134">Update the Global (Org-wide default) policy definition, then assign it to your students.</span></span>

<span data-ttu-id="9ba93-135">정책 정의를 생성하거나 편집하려면 작업하려는 정책 기능 영역(예: 메시지 정책)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-135">To create or edit policy definitions, go to the policy capability area you want to work in (for example, Messaging policies).</span></span> <span data-ttu-id="9ba93-136">새 사용자 지정 정책 정의 (교육 담당자용으로 생성한 사용자 지정 정책 정의)를 생성하려면 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-136">Select **Add** if you want to create a new custom policy definition (which you'll do for the custom policy definition you create for educators).</span></span> <span data-ttu-id="9ba93-137">그렇지 않고 기존 정책 정의를 변경하려면 **편집**(학생을 위한 전역 정책 업데이트를 선택한 경우 수행해야 하는 작업)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-137">Otherwise, to change an existing policy definition, then select **Edit** (which will be what you do if you choose to update the Global policy for students).</span></span>

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="추가 단추 보기가 있는 메시지 정책 섹션을 닫습니다.":::

<span data-ttu-id="9ba93-139">정책 정의 추가 또는 편집을 선택한 경우 해당 정책 영역과 관련된 모든 정책 옵션이 나열되어 있는 보기로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-139">Whether you choose to add or edit a policy definition, you're brought to a view that lists all the policy options related to this policy area.</span></span> <span data-ttu-id="9ba93-140">해당 목록을 사용하여 정책 정의에 설정하려는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-140">Use this list to select what values you want set in your policy definition.</span></span>

![사용자가 선택한 정책 영역과 관련된 정책 옵션이 있는 페이지입니다.](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> <span data-ttu-id="9ba93-142">페이지를 떠날 때 반드시 **저장**을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-142">Don’t forget to select **Save** before you leave the page.</span></span>

### <a name="how-to-assign-a-policy-definition-to-a-user"></a><span data-ttu-id="9ba93-143">사용자에게 정책 정의를 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="9ba93-143">How to assign a policy definition to a user</span></span>

> [!NOTE]
> <span data-ttu-id="9ba93-144">모든 사용자 및 클라이언트에게 정책 정의를 할당하는 작업에는 시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-144">Assigning a policy definition may take a while to propagate out to all the users and clients.</span></span> <span data-ttu-id="9ba93-145">Azure/M365에 사용자 계정을 처음 생성할 때 및 새 학생이 교육 기관에 참여할 때마다 해당 작업이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-145">You might want to do this when the user accounts are first created in Azure/M365, and whenever a new student joins the educational institute.</span></span>

<span data-ttu-id="9ba93-146">정책 정의를 생성하거나 업데이트하면 정책 페이지에서 **사용자 관리**를 선택하고 원하는 사용자를 검색한 후 정책을 적용하여 사용자에게 해당 정책 정의를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-146">Once your policy definition is created or updated, you can assign it to a user by selecting **Manage users** in policy page, searching for the desired user then applying the policy.</span></span>

![사용자 관리 패널은 메시지 정책 페이지 상단에서 오른쪽에 있습니다.](media/edu-manage-users-pane.png)

<span data-ttu-id="9ba93-148">또한 사용자로 이동하고 정책을 업데이트하려는 사용자를 선택하고 정책을 선택한 후 편집을 선택하여 사용자에게 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-148">You can also assign a policy to a user by navigating to Users, selecting the user you wish to update policies for, selecting Policies, then Edit.</span></span> <span data-ttu-id="9ba93-149">여기에서 각 기능 영역에 대해 사용자에게 할당하고 사용하려는 정책 정의를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-149">From there, you can select the policy definition you’d like to use assign to the user for each capability area.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9ba93-150">사용자가 대규모 교육 기관에 소속되어 있는 경우 Microsoft Teams 관리 포털 환경을 사용하여 각 사용자에 대해 정책을 설정하는 작업이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-150">If you're part of a large educational institute, using the Microsoft Teams admin portal experience to set policies for each user may be difficult.</span></span> <span data-ttu-id="9ba93-151">PowerShell을 통해 일괄적으로 정책을 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-151">It'll be better for you to assign policies in batches via PowerShell.</span></span> <span data-ttu-id="9ba93-152">사용자에게 필요한 경우 [교육 기관에서 대규모 사용자 집합에 정책을 할당](batch-policy-assignment-edu.md)하는 방법에 대해 몇 가지 EDU 관련 정보를 제공하며 대규모 사용자 그룹에 대한 정책 및 설정을 관리하는 또 다른 유용한 방법인 정책 패키지에서 아래 섹션을 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-152">We have some EDU-specific information on how to [Assign policies to large sets of users in your educational institute](batch-policy-assignment-edu.md) if you need it, and you can also check out the section below on policy packages, which are another great way to manage policies and settings for large groups of users.</span></span>

![할당된 정책 페이지의 오른쪽에서 사용자 정책 창을 편집합니다.](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a><span data-ttu-id="9ba93-154">Microsoft Teams의 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="9ba93-154">Policy packages in Microsoft Teams</span></span>

<span data-ttu-id="9ba93-155">Teams의 정책 패키지는 위에서 살펴본 사전 정의된 정책 및 정책 설정을 수집하고 수집한 것을 기관에서 유사한 역할을 가진 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-155">A policy package in Teams collects predefined policies and policy settings that you learned about outlined above, and assigns them to users with similar roles in your institution.</span></span> <span data-ttu-id="9ba93-156">정책 패키지는 정책 관리 시 이를 단순화 및 간소화하고 일관성을 제공하도록 돕습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-156">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="9ba93-157">기본 사례에서 정책 패키지를 각 사용자에게 할당하고 해당 사용자 그룹의 요구에 따라 각 패키지의 정책을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-157">In normal practice, you assign each of your users a policy package, and  redefine the policies in each package as needed to suit the needs of that user group.</span></span> <span data-ttu-id="9ba93-158">패키지의 설정을 업데이트하면 해당 패키지에 할당된 모든 사용자는 대량 업데이트로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-158">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="9ba93-159">일반적으로 교육 기관에는 학생 나이 및 성숙도에 따라 부분적으로 고유한 요구 사항을 지닌 다양한 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-159">Educational institutions in general have many users with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="9ba93-160">예를 들어 교육 담당자 및 직원에게 Microsoft Teams의 모든 액세스 권한을 부여할 수 있지만 안전하고 집중된 교육 환경을 장려하기 위해 학생용 Microsoft Teams 기능은 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-160">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="9ba93-161">교육 기관 공동체에서 다양한 코호트 요구 사항에 따라 정책 패키지를 사용하여 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-161">You can use policy packages to tailor settings based on the needs of different cohorts in your educational institute community.</span></span>

> [!NOTE]
> <span data-ttu-id="9ba93-162">자세한 내용은 [Microsoft Teams의 정책 패키지 관리](manage-policy-packages.md)를 참조하여 단일 사용자에게 패키지 할당, 최대 5,000명의 사용자에게 패키지 대량 할당, 각 패키지에 연결된 정책 관리 및 업데이트에 대한 단계별 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="9ba93-162">For more reading, you can check out [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 5000 users, and managing and updating the policies linked to each package.</span></span>

<span data-ttu-id="9ba93-163">해당 문서의 앞 부분에서 설명한 대로 정책 패키지는 다음 작업에 대해 정책을 사전 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-163">Just like the policy list earlier in this article, policy packages predefine policies for:</span></span>

- <span data-ttu-id="9ba93-164">모임</span><span class="sxs-lookup"><span data-stu-id="9ba93-164">Meetings</span></span>
- <span data-ttu-id="9ba93-165">라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="9ba93-165">Live events</span></span>
- <span data-ttu-id="9ba93-166">통화</span><span class="sxs-lookup"><span data-stu-id="9ba93-166">Calling</span></span>
- <span data-ttu-id="9ba93-167">메시지</span><span class="sxs-lookup"><span data-stu-id="9ba93-167">Messaging</span></span>
- <span data-ttu-id="9ba93-168">Teams</span><span class="sxs-lookup"><span data-stu-id="9ba93-168">Teams</span></span>
- <span data-ttu-id="9ba93-169">앱 사용 권한</span><span class="sxs-lookup"><span data-stu-id="9ba93-169">App permissions</span></span>

<span data-ttu-id="9ba93-170">Microsoft Teams는 현재 다음 정책 패키지를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-170">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="9ba93-171">Microsoft Teams 관리 센터에 나열된 패키지 이름</span><span class="sxs-lookup"><span data-stu-id="9ba93-171">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="9ba93-172">최적 용도</span><span class="sxs-lookup"><span data-stu-id="9ba93-172">Best used for</span></span>  |<span data-ttu-id="9ba93-173">설명</span><span class="sxs-lookup"><span data-stu-id="9ba93-173">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="9ba93-174">**Education_Teacher**</span><span class="sxs-lookup"><span data-stu-id="9ba93-174">**Education_Teacher**</span></span>| <span data-ttu-id="9ba93-175">교육 담당자 및 직원</span><span class="sxs-lookup"><span data-stu-id="9ba93-175">Educators and staff</span></span>| <span data-ttu-id="9ba93-176">해당 정책의 집합 및 정책 설정을 사용하여 조직 내 교육 담당자 및 직원에게 Microsoft Teams를 통해 채팅, 통화 및 모임에 대한 모든 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-176">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="9ba93-177">**Education_PrimaryStudent**</span><span class="sxs-lookup"><span data-stu-id="9ba93-177">**Education_PrimaryStudent**</span></span>| <span data-ttu-id="9ba93-178">초등 연령 이하의 학생</span><span class="sxs-lookup"><span data-stu-id="9ba93-178">Primary school aged students</span></span>  | <span data-ttu-id="9ba93-179">기관 내 초등 연령 이하의 학생에게는 Microsoft Teams 내에서 더 많은 제한이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-179">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="9ba93-180">해당 정책의 집합 및 정책 설정을 사용하여 모임 생성 및 관리, 채팅 관리, 비공개 통화 등의 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-180">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="9ba93-181">**Education_SecondaryStudent**</span><span class="sxs-lookup"><span data-stu-id="9ba93-181">**Education_SecondaryStudent**</span></span>| <span data-ttu-id="9ba93-182">중등 연령의 학생</span><span class="sxs-lookup"><span data-stu-id="9ba93-182">Secondary school aged students</span></span> | <span data-ttu-id="9ba93-183">기관 내 중등 연령의 학생에게는 Microsoft Teams 내에서 더 많은 제한이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-183">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="9ba93-184">해당 정책의 집합 및 정책 설정을 사용하여 모임 생성 및 관리, 채팅 관리, 비공개 통화 등의 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-184">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="9ba93-185">**Education_HigherEducationStudent**</span><span class="sxs-lookup"><span data-stu-id="9ba93-185">**Education_HigherEducationStudent**</span></span>| <span data-ttu-id="9ba93-186">고등 교육 학생</span><span class="sxs-lookup"><span data-stu-id="9ba93-186">Higher education students</span></span> | <span data-ttu-id="9ba93-187">기관 내 고등 교육 학생에게는 해당 연령 이하의 학생보다 필요한 제한 사항이 더 적을 수 있지만 일부 기능의 제한은 권장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-187">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="9ba93-188">해당 정책의 집합 및 정책 설정을 사용하여 조직 내에서 채팅, 통화 및 모임에 대한 액세스 권한을 부여할 수 있지만 외부 참석자와 함께 Microsoft Teams를 사용하는 방법을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-188">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="선택할 수 있는 정책 패키지 목록을 포함한 정책 패키지 페이지":::

<span data-ttu-id="9ba93-190">각 개별 정책은 정책 패키지의 이름이 지정되며 정책 패키지에 연결된 정책을 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-190">Each individual policy is given the name of the policy package so you can easily identify policies linked to a policy package.</span></span> <span data-ttu-id="9ba93-191">예를 들어 교육 기관의 교육 담당자자에게 Education_Teacher 정책 패키지를 할당하는 경우 패키지의 각 정책에 대해 Education_Teacher 이름의 정책이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-191">For example, when you assign the Education_Teacher policy package to educators in your educational institution, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher 정책 패키지 스크린샷](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="9ba93-193">교육 담당자 및 관리 지원 직원에게 다른 정책이 필요하다고 결정한 경우 기존 패키지의 용도를 변경할 수 있습니다. (현재 사용하지 않는 패키지를 식별하고 해당 그룹에 맞게 설정을 변경할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="9ba93-193">If you decide that educators and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="9ba93-194">어떤 그룹에 어떤 패키지를 지정해야 하는지 직접 메모해야 할 수도 있지만 이는 패키지의 용도를 변경하는 데 있어서 유일한 제한이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-194">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="policies-that-should-be-assigned-for-student-safety"></a><span data-ttu-id="9ba93-195">학생 안전을 위해 할당해야 하는 정책</span><span class="sxs-lookup"><span data-stu-id="9ba93-195">Policies that should be assigned for student safety</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="9ba93-196">모임 정책</span><span class="sxs-lookup"><span data-stu-id="9ba93-196">Meeting policies</span></span>

#### <a name="turn-off-the-ability-to-create-and-start-meetings"></a><span data-ttu-id="9ba93-197">모임 생성 및 시작 기능 해제</span><span class="sxs-lookup"><span data-stu-id="9ba93-197">Turn off the ability to create and start meetings</span></span>

<span data-ttu-id="9ba93-198">학생이 무인 통신을 위해 모임을 예약할 수 없도록 하려면 모임 정책에서 해당 일반 설정을 통해 모임 생성 기능을 **해제**로 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="9ba93-198">To ensure that students can’t schedule a meeting to communicate unattended, in meeting policies set to **Off** meeting creation capabilities through these General settings:</span></span>

- <span data-ttu-id="9ba93-199">**채널에서 모임 시작 허용**: 해제</span><span class="sxs-lookup"><span data-stu-id="9ba93-199">**Allow Meet now in channels**: Off</span></span>
- <span data-ttu-id="9ba93-200">**Outlook 추가 기능 허용**: 해제</span><span class="sxs-lookup"><span data-stu-id="9ba93-200">**Allow the Outlook add-in**: Off</span></span>
- <span data-ttu-id="9ba93-201">**채널 모임 예약 허용**: 해제</span><span class="sxs-lookup"><span data-stu-id="9ba93-201">**Allow channel meeting scheduling**: Off</span></span>
- <span data-ttu-id="9ba93-202">**비공개 모임 예약 허용**: 해제</span><span class="sxs-lookup"><span data-stu-id="9ba93-202">**Allow scheduling private meetings**: Off</span></span>

![원격 학습 페이지의 학생 교육, 일반 섹션 표시, 해당 모든 옵션 해제](media/edu-policy-list-a.png)

- <span data-ttu-id="9ba93-204">동일한 페이지에서 모임의 참석자 및 게스트 섹션: **비공개 모임에서 모임 시작 허용**: 해제</span><span class="sxs-lookup"><span data-stu-id="9ba93-204">And on the same page, in the Participants and Guests in meeting section: **Allow Meet now in private meetings**: Off</span></span>

![참석자 및 게스트 섹션은 비공개 모임에서 모임 시작 허용 옵션과 함께 해제됩니다.](media/edu-participants-and-guests.png)

#### <a name="control-whether-or-not-students-can-share-their-videos-during-calls-and-meetings"></a><span data-ttu-id="9ba93-206">학생이 통화 및 모임 중에 비디오를 공유할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-206">Control whether or not students can share their videos during calls and meetings</span></span>

<span data-ttu-id="9ba93-207">모임 정책 섹션에서 학생에 대해 설정하는 오디오 및 시각적 값이 교육 기관의 지침 및 학생, 교육 담당자, 학부모 및 보호자의 요청에 부합하는지 확인합니다. (**해제**하는 것이 좋은 **클라우드 녹음/녹화 허용**은 제외)</span><span class="sxs-lookup"><span data-stu-id="9ba93-207">In the meeting policies section, ensure that the Audio and visual values you set for your students aligns to your educational institution’s guidelines, as well as the desires of students, educators, and parents and guardians (With the exception of **Allow cloud recording**, which we recommend be set to **Off**).</span></span>

<span data-ttu-id="9ba93-208">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-208">The options here:</span></span>

- <span data-ttu-id="9ba93-209">**기록 허용**: 해제/설정</span><span class="sxs-lookup"><span data-stu-id="9ba93-209">**Allow transcription**: Off/On</span></span>
- <span data-ttu-id="9ba93-210">**클라우드 녹음/녹화 허용**: **해제**</span><span class="sxs-lookup"><span data-stu-id="9ba93-210">**Allow cloud recording**: **Off**</span></span>
- <span data-ttu-id="9ba93-211">**IP 비디오 허용**: 해제/설정</span><span class="sxs-lookup"><span data-stu-id="9ba93-211">**Allow IP Video**: Off/On</span></span>

:::image type="content" source="media/edu-policy-list-b.png" alt-text="원격 학습 페이지의 학생 교육, 비디오 옵션 표시":::

### <a name="live-events-policies"></a><span data-ttu-id="9ba93-213">라이브 이벤트 정책</span><span class="sxs-lookup"><span data-stu-id="9ba93-213">Live events policies</span></span>

#### <a name="turn-off-the-ability-to-create-and-start-live-events"></a><span data-ttu-id="9ba93-214">라이브 이벤트 생성 및 시작 기능 해제</span><span class="sxs-lookup"><span data-stu-id="9ba93-214">Turn off the ability to create and start live events</span></span>

<span data-ttu-id="9ba93-215">학생이 무인 통신을 위해 라이브 이벤트를 예약할 수 없도록 하려면 학생에 대해 **예약 허용** 정책을 **해제**로 설정하여 사용하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-215">To ensure that students can’t schedule a live events to communicate unattended, disable the **Allow scheduling** policy for students by setting it to **Off**.</span></span>

:::image type="content" source="media/edu-allow-scheduling-off.png" alt-text="원격 학습 페이지의 학생 교육, 예약 허용 옵션 해제":::

### <a name="calling-policies"></a><span data-ttu-id="9ba93-217">통화 정책</span><span class="sxs-lookup"><span data-stu-id="9ba93-217">Calling policies</span></span>

#### <a name="turn-off-the-ability-to-make-private-calls"></a><span data-ttu-id="9ba93-218">비공개 통화를 설정하는 기능을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-218">Turn off the ability to make private calls</span></span>

<span data-ttu-id="9ba93-219">학생이 다른 학생 또는 교육 담당자와 비공개 통화를 생성할 수 없도록 하려면 학생에 대해 **비공개 통화 생성** 정책을 **해제**로 설정하여 사용하지 못하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-219">To ensure that students can’t make private calls with other students or educators, disable the **Make private calls** policy for students by setting it to **Off**.</span></span>

:::image type="content" source="media/edu-private-calls-off.png" alt-text="원격 학습 페이지의 학생 교육, 비공개 통화 생성 해제":::

### <a name="messaging-policies"></a><span data-ttu-id="9ba93-221">메시지 정책</span><span class="sxs-lookup"><span data-stu-id="9ba93-221">Messaging policies</span></span>

#### <a name="turn-off-the-ability-to-delete-or-edit-sent-messages"></a><span data-ttu-id="9ba93-222">보낸 메시지 삭제 또는 편집 기능 해제</span><span class="sxs-lookup"><span data-stu-id="9ba93-222">Turn off the ability to delete or edit sent messages</span></span>

- <span data-ttu-id="9ba93-223">학생용: 학생이 보낸 메시지를 삭제 또는 변경하지 않도록 하려면 학생은 해당 설정을 **해제**해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-223">For students: To make sure the messages that students send aren’t deleted or altered, students should have these settings turned **Off**:</span></span>
  - <span data-ttu-id="9ba93-224">**보낸 메시지 삭제**</span><span class="sxs-lookup"><span data-stu-id="9ba93-224">**Delete sent messages**</span></span>
  - <span data-ttu-id="9ba93-225">**보낸 메시지 편집**</span><span class="sxs-lookup"><span data-stu-id="9ba93-225">**Edit sent messages**</span></span>
- <span data-ttu-id="9ba93-226">교육 담당자용: 교육 담당자가 학생이 보낸 부적절한 메시지를 조정 또는 삭제할 수 있도록 하려면 교육 담당자는 해당 설정을 **설정**해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-226">For educators: To make sure that educators can moderate or delete inappropriate messages students sent, educators should have these settings turned **On**:</span></span>
  - <span data-ttu-id="9ba93-227">**소유자는 보낸 메시지를 삭제할 수 있습니다.** (해당 설정을 사용하면 교육 담당자는 학생이 보낸 부적절한 메시지를 삭제할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="9ba93-227">**Owners can delete sent messages** (This setting allows educators to delete inappropriate student messages)</span></span>
  - <span data-ttu-id="9ba93-228">**보낸 메시지 삭제**</span><span class="sxs-lookup"><span data-stu-id="9ba93-228">**Delete sent messages**</span></span>
  - <span data-ttu-id="9ba93-229">**보낸 메시지 편집**</span><span class="sxs-lookup"><span data-stu-id="9ba93-229">**Edit sent messages**</span></span>

![원격 학습 페이지의 학생 교육, 학생 및 교육 담당자를 위한 보낸 메시지 설정.](media/edu-delete-edit-sent.png)

> [!NOTE]
> <span data-ttu-id="9ba93-231">해당 항목에 대한 자세한 내용은 [수업 팀에서 학생 의견 차단](https://support.office.com/article/Mute-student-comments-in-a-class-team-a378de16-ffc0-420c-b08d-e17ec08e7c17)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ba93-231">For more information on this topic, check out [Mute student comments in a class team.](https://support.office.com/article/Mute-student-comments-in-a-class-team-a378de16-ffc0-420c-b08d-e17ec08e7c17).</span></span>

#### <a name="control-whether-students-can-chat-privately"></a><span data-ttu-id="9ba93-232">학생이 비공개로 채팅을 할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-232">Control whether students can chat privately</span></span>

<span data-ttu-id="9ba93-233">학생에 대해 설정된 **채팅 설정/해제** 값이 교육 기관의 지침 및 학생, 교육 담당자의 요구에 부합하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-233">Ensure that the **Chat On/Off** value you set for students aligns to your educational institution’s guidelines as well as the desires of students and educators.</span></span> <span data-ttu-id="9ba93-234">해당 제어는 Teams에서 사용자가 1:1 채팅 또는 그룹 채팅에서 비공개로 통신하는 기능을 설정 또는 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-234">This control turns on or off the ability for a user to communicate privately in 1:1 chat or group chat in Teams.</span></span>

![원격 학습 페이지의 학생 교육, 채팅 옵션 해제](media/edu-chat-private.png)

#### <a name="control-whether-students-can-personalize-their-messages"></a><span data-ttu-id="9ba93-236">학생이 자신의 메시지를 개인 설정할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-236">Control whether students can personalize their messages</span></span>

<span data-ttu-id="9ba93-237">학생에 대해 설정된 값이 교육 기관의 지침 및 학생, 교육 담당자, 학부모 및 보호자의 요구에 부합하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-237">Ensure that the value you set for students aligns to your educational institution’s guidelines as well as the desires of students, educators, parents, and guardians.</span></span> <span data-ttu-id="9ba93-238">**학생에 대해 Giphy**를 **해제**로 설정하고 **밈 및 스티커**를 계속 **설정**한 상태로 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-238">Our recommendation is to set **Giphy for students** to **Off**, and keep **Memes and Stickers** turned **On**.</span></span>

![원격 학습 페이지의 학생 교육, Giphy 옵션 및 밈과 스티커 옵션](media/edu-personalize-messages.png)

#### <a name="control-whether-students-can-send-voice-messages"></a><span data-ttu-id="9ba93-240">학생이 음성 메시지를 전송할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-240">Control whether students can send voice messages</span></span>

<span data-ttu-id="9ba93-241">학생을 위한 **음성 메시지 생성**에 대해 설정된 값이 교육 기관의 지침 및 학생, 교육 담당자의 요구에 부합하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-241">Ensure that the value you set for **Create voice messages** for students aligns to your educational institution’s guidelines as well as the desires of students and educators.</span></span>

![원격 학습 페이지의 학생 교육, 음성 메시지 생성 옵션](media/edu-create-send-voice-mess.png)

#### <a name="turn-off-the-ability-to-remove-users-from-chat-for-students"></a><span data-ttu-id="9ba93-243">학생용 채팅에서 사용자를 제거하는 기능을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-243">Turn off the ability to remove users from chat for students</span></span>

<span data-ttu-id="9ba93-244">학생은 자신이 포함된 채팅에서 다른 사용자를 제거할 수 있는 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-244">Students should not have the ability to remove other users from any chats they're included in.</span></span> <span data-ttu-id="9ba93-245">**그룹 채팅에서 사용자 제거**는 **해제**로 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-245">The setting for **Remove users from group chats** should be set to **Off**.</span></span>

![원격 학습 페이지의 학생 교육, 그룹 채팅에서 사용자 제거 옵션 해제](media/edu-remove-users-from-chat-for-students.png)

### <a name="teams-policies"></a><span data-ttu-id="9ba93-247">Teams 정책</span><span class="sxs-lookup"><span data-stu-id="9ba93-247">Teams policies</span></span>

#### <a name="turn-off-the-ability-to-discover-and-create-private-channels"></a><span data-ttu-id="9ba93-248">비공개 채널 검색 및 생성 기능 해제</span><span class="sxs-lookup"><span data-stu-id="9ba93-248">Turn off the ability to discover and create private channels</span></span>

<span data-ttu-id="9ba93-249">학생이 보호자의 지도 없이 통신하기 위한 개인 공간으로 개인 채널을 만들 수 없도록 하려면 학생에 대한 **개인 채널 생성** 정책을 **해제**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-249">To ensure that students can’t create a private channel as personal space to communicate without supervision, set the **Create private channels** policy for students to **Off**.</span></span>

![페이지의 오른쪽에서 오버레이된 새 팀 정책 패널을 포함하는 Teams 정책 페이지, 해당 패널에서 비공개 채널 생성 설정 해제](media/edu-private-channels.png)

> [!IMPORTANT]
> <span data-ttu-id="9ba93-251">또한 Microsoft Teams에서 학생이 새 팀을 생성하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-251">Likely you will also want to ensure students don't have the ability to create new teams in Microsoft Teams.</span></span> <span data-ttu-id="9ba93-252">이는 실제로 M365 그룹 설정이며 자세한 내용은 [여기](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ba93-252">This is actually an M365 groups setting, and you can read more about it [here](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups).</span></span>

### <a name="app-permission-policies"></a><span data-ttu-id="9ba93-253">앱 사용 권한 정책</span><span class="sxs-lookup"><span data-stu-id="9ba93-253">App permission policies</span></span>

#### <a name="control-whether-students-can-add-apps-within-teams"></a><span data-ttu-id="9ba93-254">학생이 Teams 내에서 앱을 추가할 수 있는지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-254">Control whether students can add apps within Teams</span></span>

<span data-ttu-id="9ba93-255">학생에 대해 설정된 값이 교육 기관의 지침에 부합하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-255">Ensure the values you set for students align to your educational institution’s guidelines.</span></span> <span data-ttu-id="9ba93-256">예를 들어 승인하는 앱에 학생이 노출되게 하려면 다음을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-256">For example, if you’d like the students to be exposed to the apps you approve, you can select:</span></span>

- <span data-ttu-id="9ba93-257">**Microsoft 앱**: **모든 앱 허용**</span><span class="sxs-lookup"><span data-stu-id="9ba93-257">**Microsoft apps**: **Allow all apps**</span></span>
- <span data-ttu-id="9ba93-258">**타사 앱의 경우**: **특정 앱을 허용하고 다른 모든 앱 차단**</span><span class="sxs-lookup"><span data-stu-id="9ba93-258">**For Third-party apps**: **Allow specific apps and block all others**</span></span>
- <span data-ttu-id="9ba93-259">**테넌트 앱의 경우**: **특정 앱을 허용하고 다른 모든 앱 차단**</span><span class="sxs-lookup"><span data-stu-id="9ba93-259">**For Tenant apps**: **Allow specific apps and block all others**</span></span>

:::image type="content" source="media/edu-policies-apps.png" alt-text="원격 학습 페이지의 학생 교육, 앱 정책 옵션 설정":::

> [!NOTE]
> <span data-ttu-id="9ba93-261">위에 언급된 대로 이는 예시이며 교육 기관의 지침에 따라 해당 정책을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-261">This is an example, and as stated above, you should set these policies in accordance to your educational institution's guidelines.</span></span>

## <a name="policies-that-should-be-assigned-for-educators"></a><span data-ttu-id="9ba93-262">교육 담당자에 대해 할당해야 하는 정책</span><span class="sxs-lookup"><span data-stu-id="9ba93-262">Policies that should be assigned for educators</span></span>

<span data-ttu-id="9ba93-263">이는 교육 담당자가 학생에게 안전한 수업 환경을 제공할 수 있도록 교육 담당자에 대해 적용하는 관리자용 권장 정책 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-263">These are recommended policy settings for admins to apply for educators, so they can have a safe class experience for their students.</span></span>

> [!NOTE]
> <span data-ttu-id="9ba93-264">핵상에 대한 정책 권장 사항은 아래에서 확인할 수 있는 교육 담당자의 섹션보다 더 많은 정보를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-264">The policy recommendations for students contains more information than the educators' sections you'll see below.</span></span> <span data-ttu-id="9ba93-265">교육 기관의 자체 정책 및 절차를 사용하여 정책 설정을 즉시 설정할 수 있는 반면, 여기에서 제공하는 권장 사항은 학생의 안전 및 보안과 엄격히 관련되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-265">While you may set policy settings in-line with your educational institute's own policies and procedures, the recommendations provided here are strictly relevant when it comes to the safety and security of students.</span></span>

### <a name="meeting-policies"></a><span data-ttu-id="9ba93-266">모임 정책</span><span class="sxs-lookup"><span data-stu-id="9ba93-266">Meeting policies</span></span>

<span data-ttu-id="9ba93-267">해당 설정을 사용하여 교육 담당자는 자신의 모임에 대한 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-267">These settings will allow educators to control access to their meetings.</span></span>

- <span data-ttu-id="9ba93-268">**익명 사용자의 모임 시작 허용**: **해제**</span><span class="sxs-lookup"><span data-stu-id="9ba93-268">**Let anonymous people start a meeting**: **Off**</span></span>
- <span data-ttu-id="9ba93-269">**자동으로 사용자 허용**: **조직의 모든 사용자**</span><span class="sxs-lookup"><span data-stu-id="9ba93-269">**Automatically admit people**: **Everyone in your organization**</span></span>
- <span data-ttu-id="9ba93-270">**전화 접속 사용자의 로비 우회 허용**: **해제**</span><span class="sxs-lookup"><span data-stu-id="9ba93-270">**Allow dial-in users to bypass the lobby**: **Off**</span></span>

### <a name="message-policies"></a><span data-ttu-id="9ba93-271">메시지 정책</span><span class="sxs-lookup"><span data-stu-id="9ba93-271">Message policies</span></span>

<span data-ttu-id="9ba93-272">**소유자는 보낸 메시지 삭제 가능**을 **설정**으로 설정하면 교육 담당자는 채널 모임에서 채팅 세션을 모니터링하고 부적절한 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-272">Setting **Owners can delete sent messages** to **On** will allow educators to monitor chat sessions and remove inappropriate messages in channel meetings.</span></span>

> [!NOTE]
> <span data-ttu-id="9ba93-273">교육 담당자는 채널 내에 모임 생성 시 수업 채팅에 부적절한 메시지를 삭제하거나 채널 자체 내에서 메시지를 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-273">This allows educators to remove inappropriate messages in class chats when the meeting is created within the channel, or to remove messages within the channel itself.</span></span>

## <a name="what-educators-can-do-to-protect-students"></a><span data-ttu-id="9ba93-274">교육 담당자가 학생을 보호하기 위해 수행할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="9ba93-274">What educators can do to protect students</span></span>

<span data-ttu-id="9ba93-275">물론, 정책을 설정하는 것은 관리자가 Teams 설정에서 학생을 사전에 보호하는 유익한 방법입니다. 교육 담당자는 정기적으로 학생과 상호 작용하는 사용자이며 학생의 안전 유지에 중요한 역할을 담당하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-275">Of course, while setting policies is a great way for Admins to proactively protect students in a Teams setting, educators are the people who are interacting with the students on a regular basis, and they also have a vital role to play to keep students safe.</span></span> <span data-ttu-id="9ba93-276">관리자는 함께 작업 중인 교육 담당자와 다음의 정보를 논의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-276">Admins may want to discuss the following information with the educators they work with.</span></span>

### <a name="set-meeting-roles-through-your-meeting-options"></a><span data-ttu-id="9ba93-277">모임 옵션을 통해 모임 역할 설정</span><span class="sxs-lookup"><span data-stu-id="9ba93-277">Set meeting roles through your Meeting options</span></span>

<span data-ttu-id="9ba93-278">모임 옵션을 사용하여 모임 참석자가 모임을 참가자 또는 발표자로 참가하는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-278">Meeting options allow you to control if meeting participants join your meetings as attendees or presenters.</span></span> <span data-ttu-id="9ba93-279">옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-279">Your options are:</span></span>

- <span data-ttu-id="9ba93-280">**일정**으로 이동하여 업데이트하려는 모임으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-280">Go to your **Calendar**  and navigate to the meeting you'd like to update.</span></span> <span data-ttu-id="9ba93-281">모임 참가 링크 옆의 **모임 옵션**을 클릭하거나 탭하여 **모임 옵션**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-281">Click or tap **Meeting options** near the meeting join link to open your **Meeting options**.</span></span>

![Microsoft Teams 모임 초대에 참여합니다. 모임 옵션은 초대 링크 바로 아래에 있습니다.](media/edu-join-meeting-options.png)

- <span data-ttu-id="9ba93-283">**대기실 우회가 가능한 사용자** 선택 영역에서 모임을 직접 입력할 수 있는 사용자를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-283">Control who can enter the meeting directly with the **Who can bypass the lobby** selection.</span></span> <span data-ttu-id="9ba93-284">**조직 내 사용자**로 설정하여 외부 사용자가 입력할 옵션을 사용하지 않도록 하고 **호출자가 대기실을 항상 우회하도록 허용**을 **해제**로 전환하여 참석자가 모임에 즉시 참가하는 대신 대기하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-284">Set it to **People in my organization** to keep external users from having the option to enter, and turn **Always let callers bypass the lobby** to **Off** to have participants wait to be admitted to the meeting instead of joining immediately.</span></span> <span data-ttu-id="9ba93-285">또한 **호출자가 참가하거나 떠나는 경우 알림** 옵션도 있습니다. 해당 옵션은 모임에 참여하는 사용자를 항상 알 수 있도록 **설정**되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-285">You also have the option to **Announce when callers join or leave**, and this should be set to **On** so you're always aware of who's in the meeting.</span></span>
- <span data-ttu-id="9ba93-286">발표자 또는 참가자로 모임에 참가하는 사용자를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-286">Control who joins the meeting as a presenter or attendee.</span></span> <span data-ttu-id="9ba93-287">**자신만**을 선택하여 다른 모든 참석자를 참가자로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-287">You can select **Only Me** to designate all other participants as attendees.</span></span> <span data-ttu-id="9ba93-288">교실 설정에서 생성하는 모임에 대한 가장 안전한 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-288">This is the safest set-up for meetings held in a classroom setting.</span></span>
  - <span data-ttu-id="9ba93-289">모임에 한 명 이상의 발표자가 있을 것으로 예상되면 **특정 사용자**를 선택하고 발표자로 참가해야 하는 다른 참석자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-289">If you expect to have more than one presenter in your meeting, select **Specific people** and pick the other participants who should join as presenters.</span></span> <span data-ttu-id="9ba93-290">모든 참석자가 모임에 발표자로 참여하게 하려면 **모든 참석자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-290">Select **Everyone** if you want all participants to join the meeting as a presenter.</span></span>

:::image type="content" source="media/edu-meeting-options.png" alt-text="조직에서 선택한 사용자와 함께 대기실 드롭다운을 우회할 수 있는 사용자 및 내가 선택한 사용자와 함께 드롭다운을 표시할 수 있는 사용자":::

### <a name="roles-in-an-online-meeting"></a><span data-ttu-id="9ba93-292">온라인 모임에서의 역할</span><span class="sxs-lookup"><span data-stu-id="9ba93-292">Roles in an online meeting</span></span>

<span data-ttu-id="9ba93-293">모임의 모든 참석자를 발표자 또는 참가자로 역할을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-293">Every participant in a meeting is assigned a role as a presenter or attendee.</span></span> <span data-ttu-id="9ba93-294">참석자의 역할은 모임에서 수행할 수 있는 작업을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-294">A participant's role controls what they can do in a meeting.</span></span> <span data-ttu-id="9ba93-295">아래 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9ba93-295">Please see the table below.</span></span>

|<span data-ttu-id="9ba93-296">기능</span><span class="sxs-lookup"><span data-stu-id="9ba93-296">Capabilities</span></span>  |<span data-ttu-id="9ba93-297">주최자/발표자</span><span class="sxs-lookup"><span data-stu-id="9ba93-297">Organizer/Presenter</span></span>  |<span data-ttu-id="9ba93-298">참가자</span><span class="sxs-lookup"><span data-stu-id="9ba93-298">Attendee</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="9ba93-299">발언 및 비디오 공유</span><span class="sxs-lookup"><span data-stu-id="9ba93-299">Speak and share video</span></span>     |     <span data-ttu-id="9ba93-300">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-300">Y</span></span>     |     <span data-ttu-id="9ba93-301">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-301">Y</span></span>     |
|<span data-ttu-id="9ba93-302">모임 채팅 참여</span><span class="sxs-lookup"><span data-stu-id="9ba93-302">Participate in meeting chat</span></span>     |     <span data-ttu-id="9ba93-303">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-303">Y</span></span>     |     <span data-ttu-id="9ba93-304">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-304">Y</span></span>     |
|<span data-ttu-id="9ba93-305">다른 사용자가 공유하는 PowerPoint 파일 비공개로 보기</span><span class="sxs-lookup"><span data-stu-id="9ba93-305">Privately view a PowerPoint file shared by someone else</span></span>     |     <span data-ttu-id="9ba93-306">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-306">Y</span></span>     |     <span data-ttu-id="9ba93-307">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-307">Y</span></span>     |
|<span data-ttu-id="9ba93-308">콘텐츠 공유</span><span class="sxs-lookup"><span data-stu-id="9ba93-308">Share content</span></span>     |     <span data-ttu-id="9ba93-309">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-309">Y</span></span>     |     <span data-ttu-id="9ba93-310">N</span><span class="sxs-lookup"><span data-stu-id="9ba93-310">N</span></span>     |
|<span data-ttu-id="9ba93-311">다른 참가자 음소거</span><span class="sxs-lookup"><span data-stu-id="9ba93-311">Mute other participants</span></span>|     <span data-ttu-id="9ba93-312">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-312">Y</span></span>     |     <span data-ttu-id="9ba93-313">N</span><span class="sxs-lookup"><span data-stu-id="9ba93-313">N</span></span>     |
|<span data-ttu-id="9ba93-314">참석자 제거</span><span class="sxs-lookup"><span data-stu-id="9ba93-314">Remove participants</span></span>      |     <span data-ttu-id="9ba93-315">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-315">Y</span></span>     |     <span data-ttu-id="9ba93-316">N</span><span class="sxs-lookup"><span data-stu-id="9ba93-316">N</span></span>     |
|<span data-ttu-id="9ba93-317">대기실에서 참석자 허용</span><span class="sxs-lookup"><span data-stu-id="9ba93-317">Admit participants from the lobby</span></span>|     <span data-ttu-id="9ba93-318">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-318">Y</span></span>     |     <span data-ttu-id="9ba93-319">N</span><span class="sxs-lookup"><span data-stu-id="9ba93-319">N</span></span>     |
|<span data-ttu-id="9ba93-320">다른 참석자의 역할 변경</span><span class="sxs-lookup"><span data-stu-id="9ba93-320">Change the roles of other participants</span></span>     |     <span data-ttu-id="9ba93-321">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-321">Y</span></span>     |     <span data-ttu-id="9ba93-322">N</span><span class="sxs-lookup"><span data-stu-id="9ba93-322">N</span></span>     |
|<span data-ttu-id="9ba93-323">녹화 시작 또는 중지</span><span class="sxs-lookup"><span data-stu-id="9ba93-323">Start or stop recording</span></span>     |     <span data-ttu-id="9ba93-324">Y</span><span class="sxs-lookup"><span data-stu-id="9ba93-324">Y</span></span>     |     <span data-ttu-id="9ba93-325">N</span><span class="sxs-lookup"><span data-stu-id="9ba93-325">N</span></span>     |

### <a name="change-roles-during-a-meeting"></a><span data-ttu-id="9ba93-326">모임 중 역할 변경</span><span class="sxs-lookup"><span data-stu-id="9ba93-326">Change roles during a meeting</span></span>

<span data-ttu-id="9ba93-327">모임의 모든 참석자를 발표자 또는 참가자로 역할을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-327">Every participant in a meeting is assigned a role as presenter or attendee.</span></span> <span data-ttu-id="9ba93-328">참석자의 역할은 모임에서 수행할 수 있는 작업을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-328">A participant's role controls what they can do while in a meeting.</span></span>

- <span data-ttu-id="9ba93-329">참석자의 역할을 변경하려면 통화 컨트롤에서 **참석자 표시**를 클릭하거나 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-329">To change a participant's role, click or tap to **Show participants** in your call controls.</span></span> <span data-ttu-id="9ba93-330">변경해야 하는 역할의 참석자를 마우스 오른쪽 단추로 클릭한 다음 **참가자 지정** 또는 **발표자 지정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-330">Right-click on the participant whose role needs to be changed, and then select **Make an attendee** or **Make a presenter**.</span></span>

![메뉴 옵션을 표시하는 사용자 모음 메뉴에서 네 번째 옵션인 참가자 지정을 선택합니다.](media/edu-make-attendee-menu.png)

- <span data-ttu-id="9ba93-332">모임 옵션에 신속하게 액세스하고 현재 참석자 및 추후 모임에 참여하는 모든 사용자에 대해 모임 역할 설정을 변경하려면 통화 제어에서 **추가 작업**을 클릭하거나 탭한 다음 **모임 세부 정보 표시**를 클릭하거나 탭합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-332">To quickly access your Meeting options and change the meeting role settings for both current participants and anyone joining your meeting in the future, click or tap **More actions** in your call controls, and then **Show meeting details**.</span></span> <span data-ttu-id="9ba93-333">모임에 대한 참가 링크 옆에 **모임 옵션**에 대한 링크를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-333">You can find the link to your **Meeting options** near the join link for the meeting.</span></span>

:::image type="content" source="media/edu-meeting-details.png" alt-text="오른쪽에 모임 세부 정보 창이 있는 모임 창":::

### <a name="mute-student-comments"></a><span data-ttu-id="9ba93-335">학생 의견 차단</span><span class="sxs-lookup"><span data-stu-id="9ba93-335">Mute student comments</span></span>

<span data-ttu-id="9ba93-336">모임 후 채널 모임을 예약하면 학생 의견을 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-336">After the meeting, you can block students from commenting further if you scheduled a channel meeting.</span></span>

#### <a name="for-a-specific-meeting"></a><span data-ttu-id="9ba93-337">특정 모임용</span><span class="sxs-lookup"><span data-stu-id="9ba93-337">For a specific meeting</span></span>

<span data-ttu-id="9ba93-338">채널에서 모임 예약 시 모임 자체가 채널 게시물이며 모임 채팅은 게시물의 복제본입니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-338">When you schedule a meeting in a channel, the meeting itself is a channel post, and the meeting chats are replicas of the post.</span></span> <span data-ttu-id="9ba93-339">팀 소유자는 해당 게시물에 대한 **추가 작업**을 클릭하거나 탭할 수 있고 **편집**을 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-339">As the team owner, you can click or tap **More actions** for that post, click **Edit**.</span></span>

:::image type="content" source="media/edu-meeting-edit.png" alt-text="채널 게시물에서 추가 옵션을 선택하고 팝업 메뉴의 두 번째 옵션으로 편집 메뉴 옵션을 확인합니다.":::

<span data-ttu-id="9ba93-341">편집 창에서 드롭다운 옵션을 **사용자 및 진행자 회신 가능**으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-341">On the edit pane, you have a dropdown option, where you can set that option to be **You and moderators can reply**.</span></span>

![편집 메뉴에서 모든 사용자가 회신 가능 옵션을 표시하고 사용자 및 진행자 회신 가능 옵션 옆에 확인 표시합니다.](media/edu-you-and-mods-reply.png)

### <a name="for-all-meetings-and-posts-of-a-team"></a><span data-ttu-id="9ba93-343">팀의 모든 모임 및 게시물용</span><span class="sxs-lookup"><span data-stu-id="9ba93-343">For all meetings and posts of a team</span></span>

<span data-ttu-id="9ba93-344">학생이 수업 팀 및 모임 채팅에서 게시하고 회신할 수 있는 시기를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-344">You can control when students can post and reply in the class team and meeting chats.</span></span> <span data-ttu-id="9ba93-345">팀의 **추가 작업**을 클릭하거나 탭하고 **팀 관리**를 클릭하고 **구성원**으로 이동한 다음 음소거할 개별 사용자 선택 또는 **모든 학생 음소거**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="9ba93-345">Click or tap **More actions** of the team, click **Manage Team**, go to **Members**, and either select individuals to mute or **Mute all students**.</span></span>

![목록 맨 위에서 학생을 개별적으로 또는 모든 학생을 음소거하는 옵션을 표시하는 참가자의 모임 목록](media/edu-student-mute.png)

## <a name="further-reading"></a><span data-ttu-id="9ba93-347">추가 자료</span><span class="sxs-lookup"><span data-stu-id="9ba93-347">Further reading</span></span>

<span data-ttu-id="9ba93-348">학생 보호에 대한 자세한 내용은 [Teams에서 원격 학습을 위한 모임을 사용하는 동안 학생 안전 유지](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)를 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="9ba93-348">Please review the [Keeping students safe while using meetings in Teams for distance learning](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8) for more information on protecting students.</span></span>
