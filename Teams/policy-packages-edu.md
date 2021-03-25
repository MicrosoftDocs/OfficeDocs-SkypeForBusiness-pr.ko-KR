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
ms.openlocfilehash: 10b87a804523758df69a68ff9c5812a6ea5b448c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117796"
---
# <a name="teams-policies-and-policy-packages-for-education"></a><span data-ttu-id="c27fc-103">교육용 Teams 정책 및 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="c27fc-103">Teams policies and policy packages for Education</span></span>

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> <span data-ttu-id="c27fc-104">Microsoft Teams의 정책에 대한 자세한 내용은 [Microsoft Teams에서 사용자에게 정책 할당](assign-policies.md)을 검토하세요.</span><span class="sxs-lookup"><span data-stu-id="c27fc-104">For the larger story on policies in Microsoft Teams, please review [Assign policies to your users in Microsoft Teams](assign-policies.md).</span></span>

## <a name="admins-getting-started-with-microsoft-teams-policy-management"></a><span data-ttu-id="c27fc-105">관리자: Microsoft Teams 정책 관리로 시작하기</span><span class="sxs-lookup"><span data-stu-id="c27fc-105">Admins: Getting started with Microsoft Teams policy management</span></span>

<span data-ttu-id="c27fc-106">Microsoft Teams의 핵심은 사용자가 모임 또는 라이브 이벤트로 이동, 채팅, 통화, 앱 사용 등의 작업을 수행할 수 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-106">Microsoft Teams allows users to do things like attend online meetings or live events, chat, make calls, and use apps.</span></span> <span data-ttu-id="c27fc-107">올바른 Microsoft Teams 관리 정책을 설정하는 것은 Teams이 학생에게 안전한 학습 환경인지 확인하는 데 있어 중요한 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-107">Setting the right Microsoft Teams admin policies is a critical step in ensuring that Teams is a safe learning environment for students.</span></span> <span data-ttu-id="c27fc-108">관리자는 정책을 사용하여 교육 기관에서 사용자에게 제공되는 Teams 기능을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-108">As an admin, you can use policies to control the Teams features that are available to users in your educational institute.</span></span> <span data-ttu-id="c27fc-109">대부분의 경우, 환경을 안전하게 유지하기 위해 학생과 교육자 모두에게 정책이 조정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-109">In most cases, policies must be adjusted for both students and educators to keep the environment safe.</span></span>  

<span data-ttu-id="c27fc-110">다음은 Microsoft Teams에서 찾을 수 있는 주요 정책 영역 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-110">Here's a list of the main policy areas you will find in Microsoft Teams.</span></span> <span data-ttu-id="c27fc-111">각 영역의 정책과 해당 정책이 제어하는 기능에 대해 자세히 알아보려면 아래 링크를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-111">To learn more about the policies in each area and the capabilities they control, use the links below:</span></span>

- [<span data-ttu-id="c27fc-112">모임</span><span class="sxs-lookup"><span data-stu-id="c27fc-112">Meetings</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="c27fc-113">라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="c27fc-113">Live events</span></span>](teams-live-events/configure-teams-live-events.md)
- [<span data-ttu-id="c27fc-114">통화</span><span class="sxs-lookup"><span data-stu-id="c27fc-114">Calling</span></span>](teams-calling-policy.md) 
- [<span data-ttu-id="c27fc-115">메시지</span><span class="sxs-lookup"><span data-stu-id="c27fc-115">Messaging</span></span>](messaging-policies-in-teams.md)
- [<span data-ttu-id="c27fc-116">Teams</span><span class="sxs-lookup"><span data-stu-id="c27fc-116">Teams</span></span>](teams-policies.md)
- [<span data-ttu-id="c27fc-117">App 사용 권한</span><span class="sxs-lookup"><span data-stu-id="c27fc-117">App permissions</span></span>](teams-app-permission-policies.md)

:::image type="content" source="media/edu-admin-center-users.png" alt-text="적용된 정책과 함께 사용자 스크린샷":::

<span data-ttu-id="c27fc-119">관리자 자격 증명으로 로그인하여 [Microsoft Teams 관리 센터](https://admin.teams.microsoft.com)에서 모든 Teams 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-119">You can manage all Teams policies in the [Microsoft Teams admin center](https://admin.teams.microsoft.com) by signing in with your admin credentials.</span></span>

### <a name="where-to-find-microsoft-teams-policies"></a><span data-ttu-id="c27fc-120">Microsoft Teams 정책의 위치</span><span class="sxs-lookup"><span data-stu-id="c27fc-120">Where to find Microsoft Teams policies</span></span>

<span data-ttu-id="c27fc-121">Teams 관리 센터에 로그인하면 Teams 관리 센터의 왼쪽 탐색에서 정책 옵션을 클릭하여 관리해야 하는 Teams의 모든 영역에 대한 정책 설정으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-121">Once you've logged into the Teams admin center, you'll be able to go to the policy settings for any area of Teams you need to manage, by clicking on the policy option in the left hand navigation of the Teams admin center.</span></span> <span data-ttu-id="c27fc-122">메시지 정책의 위치 스크린샷이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-122">We've included a screenshot of the location of the messaging policies.</span></span>

:::image type="content" source="media/edu-messaging-policies.png" alt-text="Teams 관리 센터에서 메시지 정책 위치":::

### <a name="how-to-create-and-update-a-policy-definition"></a><span data-ttu-id="c27fc-124">정책 정의의 생성 및 업데이트 방법</span><span class="sxs-lookup"><span data-stu-id="c27fc-124">How to create and update a policy definition</span></span>

<span data-ttu-id="c27fc-125">사용자에게 정책을 할당하기 전에 먼저 Teams에서 각 기능 영역에 대해 정책 정의를 추가하고 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-125">Before you assign policies to your users, you need to first add and create your policy definitions for each capability area with Teams.</span></span>

> [!NOTE]
> <span data-ttu-id="c27fc-126">학생과 교육 담당자를 위한 다른 정책 정의를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-126">We recommend that you set different policy definitions for your students and educators.</span></span>

<span data-ttu-id="c27fc-127">기본적으로 모든 신규 사용자(학생 또는 교육 담당자)에게는 각 기능 영역에 대해 전역(조직 차원에서 기본값) 정책 정의가 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-127">By default, every new user (student or educator) will be assigned the Global (Org-wide default) policy definition for each capability area.</span></span> <span data-ttu-id="c27fc-128">가장 엄격한 정책 정의 집합에 전체(조직 전체 기본값)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-128">We recommend that you use the Global (Org-wide default) for your strictest set of policy definitions.</span></span> <span data-ttu-id="c27fc-129">대부분의 경우, 이 엄격한 정책 세트가 학생들에게 더 적합할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-129">In most cases, this stricter policy set will be more appropriate for students.</span></span> <span data-ttu-id="c27fc-130">이러한 방식으로 전체(조직 전체 기본값) 정책 정의를 사용하면 새 사용자가 테넌트에 추가될 때 가장 엄격한 제한이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-130">Using your Global (Org-wide default) policy definition in this way will ensure that new users will have the tightest restrictions when they are added to your tenant.</span></span> <span data-ttu-id="c27fc-131">이 지침을 준수하려면 다음 단계를 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-131">To adhere to this guidance, we recommend you follow these steps:</span></span>

1. <span data-ttu-id="c27fc-132">교육자의 요구에 맞는 정책 값을 사용하여 각 Teams 역량 영역에 대한 사용자 지정 정책 정의를 작성합니다(이 정의가 없으면 교육자는 전체(조직 전체 기본값) 정책 정의에 정의된 것과 동일한 제한된 액세스를 갖게 됩니다).</span><span class="sxs-lookup"><span data-stu-id="c27fc-132">Create a custom policy definition for each Teams capability area with policy values that are fitting for your educators' needs (without this, educators will have the same restricted access as your students as defined within the Global (Org-wide default) policy definition).</span></span>

1. <span data-ttu-id="c27fc-133">이러한 새로운 사용자 지정 정책 정의를 교육자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-133">Assign these new custom policy definitions to your educators.</span></span>

1. <span data-ttu-id="c27fc-134">각 기능 영역에 대한 전체(조직 전체의 기본값) 정책 정의를 학생에 적합한 값으로 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-134">Edit the Global (Org-wide default) policy definitions for each capability area with values that are appropriate for your students.</span></span>

1. <span data-ttu-id="c27fc-135">전체(조직 전체의 기본값) 정책 정의는 다른 정책 정의가 할당되지 않는 한 학생들에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-135">The Global (Org-wide default) policy definitions will be applied to your students as long as they have no other policy definitions assigned.</span></span>


<span data-ttu-id="c27fc-136">정책 정의를 생성하거나 편집하려면 작업하려는 정책 기능 영역(예: 메시지 정책)으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-136">To create or edit policy definitions, go to the policy capability area you want to work in (for example, Messaging policies).</span></span> <span data-ttu-id="c27fc-137">**추가** 를 선택하여 새 사용자 지정 정책 정의를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-137">Select **Add** to create a new custom policy definition.</span></span> <span data-ttu-id="c27fc-138">기존 정책 정의를 변경하려면 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-138">To change an existing policy definition, select **Edit**.</span></span>

:::image type="content" source="media/edu-messaging-policies-add-closeup.png" alt-text="추가 단추 보기가 있는 메시지 정책 섹션을 닫습니다.":::

<span data-ttu-id="c27fc-140">정책 정의 추가 또는 편집을 선택한 경우 해당 정책 영역과 관련된 모든 정책 옵션이 나열되어 있는 보기로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-140">Whether you choose to add or edit a policy definition, you're brought to a view that lists all the policy options related to this policy area.</span></span> <span data-ttu-id="c27fc-141">해당 목록을 사용하여 정책 정의에 설정하려는 값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-141">Use this list to select what values you want set in your policy definition.</span></span>

![사용자가 선택한 정책 영역과 관련된 정책 옵션이 있는 페이지입니다.](media/edu-global-policy-definition.png)

> [!IMPORTANT]
> <span data-ttu-id="c27fc-143">페이지를 떠날 때 반드시 **저장** 을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-143">Don’t forget to select **Save** before you leave the page.</span></span>

### <a name="assigning-policy-definitions"></a><span data-ttu-id="c27fc-144">정책 정의 할당</span><span class="sxs-lookup"><span data-stu-id="c27fc-144">Assigning policy definitions</span></span> 
<span data-ttu-id="c27fc-145">사용자에게 정책 정의를 할당하는 데 사용할 수 있는 여러 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-145">There are multiple methods you can use to assign policy definitions to your users.</span></span> <span data-ttu-id="c27fc-146">각 방법에는 장점과 단점이 있으며, 이는 기관의 고유한 요구에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-146">Each method has its own advantages and disadvantages, which will differ depending on your institution's unique needs.</span></span>  

<span data-ttu-id="c27fc-147">대부분의 경우 그룹 정책 할당을 사용하여 사용자에게 정책을 할당하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-147">In most cases, we recommend that you use group policy assignment to assign policies to your users.</span></span> <span data-ttu-id="c27fc-148">이 방법을 사용하면 더 빠르고 원활한 정책 적용을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-148">This method allows for faster and more seamless policy application.</span></span>  <span data-ttu-id="c27fc-149">정책 정의가 할당된 그룹에 사용자를 추가하면 새 사용자가 자동으로 그룹의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-149">When a user is added to a group that has a policy definition assigned to it, the new user automatically inherits the policies of the group.</span></span>  <span data-ttu-id="c27fc-150">이를 통해 예를 들어 학기의 시작과 종료와 같이 환경에 많은 수의 사용자가 추가 및 제거될 때 보다 쉽게 정책을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-150">This allows for easier policy management when large numbers of users are added and removed to the environment, for example at the beginning and ending of a school term.</span></span>  

<span data-ttu-id="c27fc-151">대규모 조직의 경우 대규모 사용자에게 정책을 할당해야 하는 경우에 적합한 일괄 정책 할당도 권장합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-151">For large organizations, we also recommend batch policy assignment, which is tailored for cases where you need to assign policies to large sets of users.</span></span> <span data-ttu-id="c27fc-152">이러한 응용 프로그램 방법에 대한 자세한 내용은 [학교의 대규모 사용자에게 정책 할당](batch-group-policy-assignment-edu.md)을 참조하시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-152">To learn more about these application methods, refer to [Assign policies to large sets of users in your school](batch-group-policy-assignment-edu.md).</span></span>

<span data-ttu-id="c27fc-153">소규모 기관이 있거나 개별 학생 또는 교육자의 정책 설정을 업데이트해야 하는 경우 아래 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-153">If you have a smaller institution or have a need to update an individual student or educator's policy settings, follow the instructions below.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="c27fc-154">개별 사용자 수준에서 지정된 정책 할당은 사용자에게 할당된 모든 그룹 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-154">Policy assignments given at the individual user level override any group policies assigned to the user.</span></span> <span data-ttu-id="c27fc-155">그룹 정책 설정을 재정의하려면 개별 정책 할당만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-155">Ensure that you are only using individual policy assignments when you desire to override group policy settings.</span></span> 

#### <a name="how-to-assign-a-policy-definition-to-a-user"></a><span data-ttu-id="c27fc-156">사용자에게 정책 정의를 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="c27fc-156">How to assign a policy definition to a user</span></span>

> [!NOTE]
> <span data-ttu-id="c27fc-157">모든 사용자 및 클라이언트에게 정책 정의를 할당하는 작업에는 시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-157">Assigning a policy definition may take a while to propagate out to all the users and clients.</span></span> <span data-ttu-id="c27fc-158">Azure/M365에 사용자 계정을 처음 생성할 때 및 새 학생이 교육 기관에 참여할 때마다 해당 작업이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-158">You might want to do this when the user accounts are first created in Azure/M365, and whenever a new student joins the educational institute.</span></span>


<span data-ttu-id="c27fc-159">정책 정의를 생성하거나 업데이트한 후에는 정책 페이지에서 **사용자 관리** 를 선택하고 원하는 사용자를 검색한 다음 정책을 적용하여 사용자에게 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-159">Once your policy definition is created or updated, you can assign it to a user by selecting **Manage users** on the policy page, searching for the desired user, then applying the policy.</span></span>

![오른쪽의 메시징 정책 페이지 위에 있는 사용자 패널을 관리합니다.](media/edu-manage-users-pane.png)

<span data-ttu-id="c27fc-161">또한 **사용자** 로 이동하고 정책을 업데이트하려는 사용자를 선택하고 **정책** 을 선택한 후 **편집** 을 선택하여 사용자에게 정책을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-161">You can also assign a policy to a user by navigating to **Users**, selecting the user you wish to update policies for, selecting **Policies**, then **Edit**.</span></span> <span data-ttu-id="c27fc-162">여기에서 각 기능 영역에 대해 사용자에게 할당하려는 정책 정의를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-162">From there, you can select the policy definition you’d like to assign to the user for each capability area.</span></span>

![할당된 정책 페이지의 오른쪽에서 사용자 정책 창을 편집합니다.](media/edu-edit-user-policies-pane.png)

### <a name="policy-packages-in-microsoft-teams"></a><span data-ttu-id="c27fc-164">Microsoft Teams의 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="c27fc-164">Policy packages in Microsoft Teams</span></span>
> [!NOTE]
> <span data-ttu-id="c27fc-165">자세한 내용은 [Microsoft Teams의 정책 패키지 관리](manage-policy-packages.md)를 참조하여 단일 사용자에게 패키지 할당, 최대 5,000명의 사용자에게 패키지 대량 할당, 각 패키지에 연결된 정책 관리 및 업데이트에 대한 단계별 지침을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c27fc-165">For more reading, you can check out [Manage policy packages in Microsoft Teams](manage-policy-packages.md) for step by step guidance on assigning single users a package, assigning packages in bulk to up to 5000 users, and managing and updating the policies linked to each package.</span></span>

<span data-ttu-id="c27fc-166">Teams의 정책 패키지는 위에서 살펴본 사전 정의된 정책 및 정책 설정을 수집하고 수집한 것을 기관에서 유사한 역할을 가진 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-166">A policy package in Teams collects predefined policies and policy settings that you learned about outlined above, and assigns them to users with similar roles in your institution.</span></span> <span data-ttu-id="c27fc-167">정책 패키지는 정책 관리 시 이를 단순화 및 간소화하고 일관성을 제공하도록 돕습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-167">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="c27fc-168">기본 사례에서 정책 패키지를 각 사용자에게 할당하고 해당 사용자 그룹의 요구에 따라 각 패키지의 정책을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-168">In normal practice, you assign each of your users a policy package, and  redefine the policies in each package as needed to suit the needs of that user group.</span></span> <span data-ttu-id="c27fc-169">패키지의 설정을 업데이트하면 해당 패키지에 할당된 모든 사용자는 대량 업데이트로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-169">When you update settings in a package, all users assigned to that package are changed as a bulk update.</span></span>

<span data-ttu-id="c27fc-170">일반적으로 교육 기관에는 학생 나이 및 성숙도에 따라 부분적으로 고유한 요구 사항을 지닌 다양한 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-170">Educational institutions in general have many users with unique needs, depending partly on the age and maturity of the students.</span></span> <span data-ttu-id="c27fc-171">예를 들어 교육 담당자 및 직원에게 Microsoft Teams의 모든 액세스 권한을 부여할 수 있지만 안전하고 집중된 교육 환경을 장려하기 위해 학생용 Microsoft Teams 기능은 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-171">For example, you may want to grant educators and staff full access to Microsoft Teams, but want to limit Microsoft Teams capabilities for students to encourage a safe and focused learning environment.</span></span> <span data-ttu-id="c27fc-172">교육 기관 공동체에서 다양한 코호트 요구 사항에 따라 정책 패키지를 사용하여 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-172">You can use policy packages to tailor settings based on the needs of different cohorts in your educational institute community.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="c27fc-173">기본 권장 사항은 정책 패키지 대신 전체(조직 전체의 기본값) 정책 정의를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-173">Our primary recommendation is that you use the Global (Org-wide default) policy definition for students instead of a policy package.</span></span> <span data-ttu-id="c27fc-174">이렇게 하면 조직의 새 사용자가 항상 학생들에게 가장 엄격한 정책 집합을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-174">This ensures that new users in your organizations always have the strictest set of policies appropriate for students.</span></span> <span data-ttu-id="c27fc-175">이 권장 사항이 해당 기관의 요구를 충족하지 못할 경우 아래의 학생 정책 패키지 중 하나가 좋은 대안이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-175">If this recommendation does not meet the needs of your institution, one of the student policy packages below may be a good alternative.</span></span> 

<span data-ttu-id="c27fc-176">해당 문서의 앞 부분에서 설명한 대로 정책 패키지는 다음 작업에 대해 정책을 사전 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-176">Just like the policy list earlier in this article, policy packages predefine policies for:</span></span>

- <span data-ttu-id="c27fc-177">모임</span><span class="sxs-lookup"><span data-stu-id="c27fc-177">Meetings</span></span>
- <span data-ttu-id="c27fc-178">라이브 이벤트</span><span class="sxs-lookup"><span data-stu-id="c27fc-178">Live events</span></span>
- <span data-ttu-id="c27fc-179">통화</span><span class="sxs-lookup"><span data-stu-id="c27fc-179">Calling</span></span>
- <span data-ttu-id="c27fc-180">메시지</span><span class="sxs-lookup"><span data-stu-id="c27fc-180">Messaging</span></span>
- <span data-ttu-id="c27fc-181">앱 사용 권한</span><span class="sxs-lookup"><span data-stu-id="c27fc-181">App permissions</span></span>

<span data-ttu-id="c27fc-182">Microsoft Teams는 현재 다음 정책 패키지를 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-182">Microsoft Teams currently includes the following policy packages:</span></span>

|<span data-ttu-id="c27fc-183">Microsoft Teams 관리 센터에 나열된 패키지 이름</span><span class="sxs-lookup"><span data-stu-id="c27fc-183">Package name listed in Microsoft Teams Admin center</span></span> |<span data-ttu-id="c27fc-184">최적 용도</span><span class="sxs-lookup"><span data-stu-id="c27fc-184">Best used for</span></span>  |<span data-ttu-id="c27fc-185">설명</span><span class="sxs-lookup"><span data-stu-id="c27fc-185">Description</span></span> |
|:--- |:--- |:--- |
|<span data-ttu-id="c27fc-186">**Education_Teacher**</span><span class="sxs-lookup"><span data-stu-id="c27fc-186">**Education_Teacher**</span></span>| <span data-ttu-id="c27fc-187">교육 담당자 및 직원</span><span class="sxs-lookup"><span data-stu-id="c27fc-187">Educators and staff</span></span>| <span data-ttu-id="c27fc-188">해당 정책의 집합 및 정책 설정을 사용하여 조직 내 교육 담당자 및 직원에게 Microsoft Teams를 통해 채팅, 통화 및 모임에 대한 모든 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-188">Use this set of policies and policy settings to grant educators and staff within your organization full access to chat, calling and meetings through Microsoft Teams.</span></span> |
|<span data-ttu-id="c27fc-189">**Education_PrimaryStudent**</span><span class="sxs-lookup"><span data-stu-id="c27fc-189">**Education_PrimaryStudent**</span></span>| <span data-ttu-id="c27fc-190">초등 연령 이하의 학생</span><span class="sxs-lookup"><span data-stu-id="c27fc-190">Primary school aged students</span></span>  | <span data-ttu-id="c27fc-191">기관 내 초등 연령 이하의 학생에게는 Microsoft Teams 내에서 더 많은 제한이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-191">Younger, primary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="c27fc-192">해당 정책의 집합 및 정책 설정을 사용하여 모임 생성 및 관리, 채팅 관리, 비공개 통화 등의 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-192">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="c27fc-193">**Education_SecondaryStudent**</span><span class="sxs-lookup"><span data-stu-id="c27fc-193">**Education_SecondaryStudent**</span></span>| <span data-ttu-id="c27fc-194">중등 연령의 학생</span><span class="sxs-lookup"><span data-stu-id="c27fc-194">Secondary school aged students</span></span> | <span data-ttu-id="c27fc-195">기관 내 중등 연령의 학생에게는 Microsoft Teams 내에서 더 많은 제한이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-195">Secondary school aged students within your institution may need more limits within Microsoft Teams.</span></span> <span data-ttu-id="c27fc-196">해당 정책의 집합 및 정책 설정을 사용하여 모임 생성 및 관리, 채팅 관리, 비공개 통화 등의 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-196">Use this set of policies and policy settings to limit capabilities like meetings creation and management,  chat management, and private calling.</span></span> |
|<span data-ttu-id="c27fc-197">**Education_HigherEducationStudent**</span><span class="sxs-lookup"><span data-stu-id="c27fc-197">**Education_HigherEducationStudent**</span></span>| <span data-ttu-id="c27fc-198">고등 교육 학생</span><span class="sxs-lookup"><span data-stu-id="c27fc-198">Higher education students</span></span> | <span data-ttu-id="c27fc-199">기관 내 고등 교육 학생에게는 해당 연령 이하의 학생보다 필요한 제한 사항이 더 적을 수 있지만 일부 기능의 제한은 권장될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-199">Higher education students within your intuition may need fewer limits than younger students, but some limitations may be recommended.</span></span> <span data-ttu-id="c27fc-200">해당 정책의 집합 및 정책 설정을 사용하여 조직 내에서 채팅, 통화 및 모임에 대한 액세스 권한을 부여할 수 있지만 외부 참석자와 함께 Microsoft Teams를 사용하는 방법을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-200">You can use this set of policies and policy settings to give access to chat, calling, and meetings within your  organization, but limit how your students use Microsoft Teams with external participants.</span></span> |
|<span data-ttu-id="c27fc-201">**Education_PrimaryTeacher_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="c27fc-201">**Education_PrimaryTeacher_RemoteLearning**</span></span>| <span data-ttu-id="c27fc-202">교육 담당자 및 직원</span><span class="sxs-lookup"><span data-stu-id="c27fc-202">Educators and staff</span></span> | <span data-ttu-id="c27fc-203">초등학교 교사에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-203">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span> |
|<span data-ttu-id="c27fc-204">**Education_PrimaryStudent_RemoteLearning**</span><span class="sxs-lookup"><span data-stu-id="c27fc-204">**Education_PrimaryStudent_RemoteLearning**</span></span>| <span data-ttu-id="c27fc-205">초등 연령 이하의 학생</span><span class="sxs-lookup"><span data-stu-id="c27fc-205">Primary school aged students</span></span>| <span data-ttu-id="c27fc-206">초등학교 학생에게 적용되는 정책 집합을 만들어 원격 학습을 사용할 때 학생의 보안 및 공동 작업을 극대화합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-206">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>
|||

:::image type="content" source="media/edu-policy-packages-list.png" alt-text="선택할 수 있는 정책 패키지 목록을 포함한 정책 패키지 페이지":::

<span data-ttu-id="c27fc-208">정책 패키지에 연결된 정책을 식별할 수 있도록 각 개별 정책에는 정책 패키지의 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-208">Each individual policy is given the name of the policy package so you can identify policies linked to a policy package.</span></span> <span data-ttu-id="c27fc-209">예를 들어 교육 기관의 교육 담당자자에게 Education_Teacher 정책 패키지를 할당하는 경우 패키지의 각 정책에 대해 Education_Teacher 이름의 정책이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-209">For example, when you assign the Education_Teacher policy package to educators in your educational institution, a policy named Education_Teacher is created for each policy in the package.</span></span>

![Education_Teacher 정책 패키지 스크린샷](media/policy-packages-education_teacher.png)

> [!NOTE]
> <span data-ttu-id="c27fc-211">교육 담당자 및 관리 지원 직원에게 다른 정책이 필요하다고 결정한 경우 기존 패키지의 용도를 변경할 수 있습니다. (현재 사용하지 않는 패키지를 식별하고 해당 그룹에 맞게 설정을 변경할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="c27fc-211">If you decide that educators and administrative support staff need different policies, you can repurpose an existing package: identify a package you aren't currently using and change the settings to be appropriate for that group.</span></span> <span data-ttu-id="c27fc-212">어떤 그룹에 어떤 패키지를 지정해야 하는지 직접 메모해야 할 수도 있지만 이는 패키지의 용도를 변경하는 데 있어서 유일한 제한이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-212">You might have to make a note to yourself which group has which package, but that's the only impediment to repurposing a package.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="c27fc-213">정책 패키지 관리</span><span class="sxs-lookup"><span data-stu-id="c27fc-213">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="c27fc-214">보기</span><span class="sxs-lookup"><span data-stu-id="c27fc-214">View</span></span>

<span data-ttu-id="c27fc-215">패키지를 할당하기 전에 정책 패키지에서 각 정책의 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-215">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="c27fc-216">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **정책 패키지** 를 선택하고 패키지 이름을 선택한 다음 정책 이름을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-216">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="c27fc-217">미리 정의된 값이 조직에 적합한지 또는 조직의 요구 사항에 따라 더 엄격하거나 관대하게 사용자 지정해야하는지 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-217">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="c27fc-218">사용자 지정</span><span class="sxs-lookup"><span data-stu-id="c27fc-218">Customize</span></span>

<span data-ttu-id="c27fc-219">필요한 경우, 조직의 요구 사항에 맞게 정책 패키지에서 정책의 설정을 사용자 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-219">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="c27fc-220">정책 설정에 대한 모든 변경 내용은 패키지가 할당된 사용자에게 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-220">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="c27fc-221">정책 패키지에서 정책 설정을 편집하려면 Microsoft Teams 관리 센터에서 정책 패키지를 선택하고 편집하려는 정책 이름을 선택한 다음 **편집** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-221">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="c27fc-222">정책 패키지를 할당한 다음에도 패키지에서 정책 설정을 변경할 수 있다는 점을 잊지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c27fc-222">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="c27fc-223">자세한 내용은 [정책 패키지에서 정책 사용자 지정](manage-policy-packages.md#customize-policies-in-a-policy-package)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c27fc-223">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="c27fc-224">할당</span><span class="sxs-lookup"><span data-stu-id="c27fc-224">Assign</span></span>

<span data-ttu-id="c27fc-225">사용자에게 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-225">Assign the policy package to users.</span></span> <span data-ttu-id="c27fc-226">사용자에게 정책이 할당된 후 나중에 다른 정책을 할당하는 경우 가장 최근의 할당이 우선됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-226">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="c27fc-227">한 명의 사용자나 여러 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="c27fc-227">Assign a policy package to one or several users</span></span>

<span data-ttu-id="c27fc-228">한 명의 사용자나 여러 사용자에게 정책 패키지를 할당하려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 **정책 패키지** 로 이동한 다음 **사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-228">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![관리 센터에서 정책 패키지를 할당하는 방법을 보여 주는 스크린샷](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="c27fc-230">자세한 내용은 [정책 패키지 할당](manage-policy-packages.md#assign-a-policy-package)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c27fc-230">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="c27fc-231">사용자에게 정책이 할당된 후 나중에 다른 정책을 할당하는 경우 가장 최근의 할당이 우선됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-231">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="c27fc-232">그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="c27fc-232">Assign a policy package to a group</span></span>

<span data-ttu-id="c27fc-233">**이 기능은 비공개 리미 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="c27fc-233">**This feature is in private preview**</span></span>

<span data-ttu-id="c27fc-234">그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-234">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="c27fc-235">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-235">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="c27fc-236">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-236">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="c27fc-237">이 방법은 최대 50,000명의 사용자가 있는 그룹에 적합하지만, 더 큰 그룹에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-237">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="c27fc-238">자세한 내용은 [그룹에 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-group)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c27fc-238">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="c27fc-239">대규모 사용자 집합(배치)에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="c27fc-239">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="c27fc-240">한 번에 많은 사용자에게 정책 패키지를 할당하려면 배치 정책 패키지를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-240">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="c27fc-241">[New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet을 사용하여 대규모 사용자와 할당하려는 정책 패키지를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-241">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="c27fc-242">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-242">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="c27fc-243">배치에는 최대 5천 명의 사용자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-243">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="c27fc-244">개체 ID, UPN, SIP 주소 또는 전자 메일 주소로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-244">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="c27fc-245">자세한 내용은 [배치 사용자에게 정책 패키지 할당](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c27fc-245">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="policies-that-should-be-assigned-for-student-safety"></a><span data-ttu-id="c27fc-246">학생 안전을 위해 할당해야 하는 정책</span><span class="sxs-lookup"><span data-stu-id="c27fc-246">Policies that should be assigned for student safety</span></span>

<span data-ttu-id="c27fc-247">사용자 환경에서 학생을 보호하기 위해 수행해야 하는 단계에 대한 자세한 내용은 [원격 학습을 위해 Teams을 사용하는 동안 학생을 안전하게 유지](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8)를 주의 깊게 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c27fc-247">For more information on the steps you need to take to protect students in your environment, carefully review [Keeping students safe while using Teams for distance learning](https://support.office.com/article/keeping-students-safe-while-using-meetings-in-teams-for-distance-learning-f00fa399-0473-4d31-ab72-644c137e11c8).</span></span>