---
title: Microsoft Teams에서 사용자에게 정책 할당
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag, jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 사용자에 게 정책을 할당 하는 다양 한 방법에 대해 알아봅니다.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 0978ed0413c372b8bacbb936af6e125294e9d35f
ms.sourcegitcommit: 95ccfce5016dfda1a59812df446824be21f3f23e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45143849"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="b11ac-103">Microsoft Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-103">Assign policies to your users in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="b11ac-104">이 문서에서 설명 하는 기능 중에는 [Microsoft 팀 관리 센터를 사용 하는 그룹에 대 한 정책 할당이](#using-the-microsoft-teams-admin-center-3)아직 해제 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-104">One of the features discussed in this article, [policy assignment to groups using the Microsoft Teams admin center](#using-the-microsoft-teams-admin-center-3), hasn't yet been released.</span></span> <span data-ttu-id="b11ac-105">발표 되었으며 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-105">It's been announced, and it's coming soon.</span></span>
> <span data-ttu-id="b11ac-106">이 기능의 릴리스 상태를 유지 하려면 [Microsoft 365 로드맵을](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185)확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-106">To stay on top of the release status of this feature, check out the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185).</span></span>

<span data-ttu-id="b11ac-107">관리자는 정책을 사용 하 여 조직의 사용자가 사용할 수 있는 팀 기능을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-107">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="b11ac-108">예를 들어, 전화 정책, 모임 정책, 메시지 정책이 몇 가지 이름으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-108">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="b11ac-109">조직에는 고유한 요구 사항이 있는 다양 한 유형의 사용자와 사용자 지정 정책을 만들어 할당 하 여 해당 요구에 따라 다른 사용자 집합에 맞게 정책 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-109">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="b11ac-110">조직의 정책을 더욱 쉽게 관리할 수 있도록 하기 위해 팀에서는 여러 가지 방법으로 사용자에 게 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-110">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="b11ac-111">개별적으로 또는 일괄 처리 할당을 통해 또는 사용자가 구성원으로 속한 그룹에 게 정책을 직접 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-111">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="b11ac-112">정책 패키지를 사용 하 여 조직에서 유사한 역할이 있는 사용자에 게 미리 설정 된 정책 모음을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-112">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="b11ac-113">선택 하는 옵션은 관리 하는 정책의 수와 할당 하려는 사용자 수에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-113">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="b11ac-114">조직의 최대 사용자 수에 적용 되도록 전역 (조직 차원의 기본값) 정책을 설정 하 여 특별 한 정책이 필요한 사용자에 게 정책을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-114">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="b11ac-115">이 문서에서는 사용자에 게 정책을 할당할 수 있는 다양 한 방법과이를 사용 하는 경우에 권장 되는 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-115">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="b11ac-116">어떤 정책이 우선적으로 적용 되나요?</span><span class="sxs-lookup"><span data-stu-id="b11ac-116">Which policy takes precedence?</span></span>

<span data-ttu-id="b11ac-117">사용자에 게 각 정책 유형에 대 한 하나의 유효 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-117">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="b11ac-118">사용자에 게 정책을 직접 할당 했을 가능성이 있거나 같은 유형의 정책이 할당 된 하나 이상의 그룹의 구성원 이기도 한 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-118">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="b11ac-119">이러한 유형의 시나리오에서는 어떤 정책이 우선적으로 적용 되나요?</span><span class="sxs-lookup"><span data-stu-id="b11ac-119">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="b11ac-120">사용자의 유효 정책은 다음과 같이 우선 순위 규칙에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-120">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="b11ac-121">사용자에 게 정책 (개별적으로 또는 일괄 할당을 통해)을 직접 할당 한 경우 해당 정책이 우선권을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-121">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="b11ac-122">다음 예제에서 사용자의 유효한 정책은 사용자에 게 직접 할당 되는 Lincoln 제곱근 모임 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-122">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![직접 할당 된 정책이 우선 하는 방법을 보여 주는 다이어그램](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="b11ac-124">사용자가 지정 된 형식의 정책을 직접 할당 하지 않은 경우 사용자가 구성원으로 속해 있는 그룹에 할당 된 정책이 우선권을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-124">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="b11ac-125">사용자가 여러 그룹의 구성원 인 경우 지정 된 정책 형식에 대 한 [그룹 할당 순위가](#group-assignment-ranking) 가장 높은 정책이 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-125">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="b11ac-126">이 예제에서 사용자의 유효 정책은 사용자가 구성원으로 속해 있고 동일한 정책 유형의 정책만 할당 하는 다른 그룹을 기준으로 할당 순위가 가장 높은 Exec 팀 및 HD 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-126">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![그룹에서 상속 된 정책이 우선 하는 방법을 보여 주는 다이어그램](media/assign-policies-example-group.png)

<span data-ttu-id="b11ac-128">사용자에 게 정책이 직접 할당 되지 않았거나 정책이 할당 된 그룹의 구성원이 아닌 경우 사용자는 해당 정책 형식에 대 한 전역 (조직 차원의 기본) 정책을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-128">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="b11ac-129">예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-129">Here's an example.</span></span>

![글로벌 정책이 우선 하는 방법을 보여 주는 다이어그램](media/assign-policies-example-global.png)

<span data-ttu-id="b11ac-131">자세히 알아보려면 [우선 순위 규칙](#precedence-rules)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-131">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="b11ac-132">정책을 할당 하는 방법</span><span class="sxs-lookup"><span data-stu-id="b11ac-132">Ways to assign policies</span></span>

<span data-ttu-id="b11ac-133">다음은 사용자에 게 정책을 할당할 수 있는 방법과 각각에 대해 권장 되는 시나리오에 대 한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-133">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="b11ac-134">링크를 클릭 하 여 자세한 내용을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-134">Click the links to learn more.</span></span>

<span data-ttu-id="b11ac-135">개별 사용자 또는 그룹에 정책을 할당 하기 전에 조직의 최대 사용자 수에 적용 되도록 [전역 (조직 차원의 기본) 정책을 설정](#set-the-global-policies) 하 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-135">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="b11ac-136">전역 정책을 설정한 후에는 특수화 된 정책이 필요한 사용자에 게 정책만 할당 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-136">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="b11ac-137">방법</span><span class="sxs-lookup"><span data-stu-id="b11ac-137">Do this</span></span>  |<span data-ttu-id="b11ac-138">If ...</span><span class="sxs-lookup"><span data-stu-id="b11ac-138">If...</span></span>  | <span data-ttu-id="b11ac-139">사용 하 고 있습니다 ...</span><span class="sxs-lookup"><span data-stu-id="b11ac-139">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="b11ac-140">개인 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-140">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="b11ac-141">팀을 처음 사용할 때 시작 하는 것이 든, 소수의 사용자에 게 하나 또는 두 가지 정책만 할당 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-141">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="b11ac-142">비즈니스용 Skype Online PowerShell 모듈의 Microsoft 팀 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="b11ac-142">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
| [<span data-ttu-id="b11ac-143">정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-143">Assign a policy package</span></span>](#assign-a-policy-package)   | <span data-ttu-id="b11ac-144">조직에서 역할이 같거나 비슷한 특정 사용자 집합에 여러 정책을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-144">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="b11ac-145">예를 들어 학교에서 교사에 게 교육 (교사) 정책 패키지를 할당 하 여 채팅, 통화, 모임, 교육 (보조 학생) 정책 패키지에 대 한 모든 액세스 권한을 보조 학생이 비공개 통화와 같은 특정 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-145">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="b11ac-146">팀 PowerShell 모듈의 Microsoft 팀 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="b11ac-146">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="b11ac-147">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-147">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="b11ac-148">대규모 사용자 집합에 정책을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-148">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="b11ac-149">예를 들어 조직에서 한 번에 수백 명 또는 수천 명의 사용자에 게 정책을 할당 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-149">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="b11ac-150">팀 PowerShell 모듈의 Microsoft 팀 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="b11ac-150">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="b11ac-151">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-151">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="b11ac-152">사용자의 그룹 구성원 자격을 기준으로 정책을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-152">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="b11ac-153">예를 들어 보안 그룹 또는 조직 구성 단위의 모든 사용자에 게 정책을 할당 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-153">For example, you want to assign a policy to all users in a security group or organizational unit.</span></span>| <span data-ttu-id="b11ac-154">팀 PowerShell 모듈의 Microsoft 팀 관리 센터 (곧 출시 예정) 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="b11ac-154">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="b11ac-155">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-155">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="b11ac-156">조직이 동일 하거나 비슷한 역할을 하는 조직의 사용자 일괄 처리에 여러 정책을 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-156">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="b11ac-157">예를 들어, 교육 (교사) 정책 패키지를 일괄 처리를 사용 하 여 모든 교사에 게 배정 하 고, 채팅, 통화, 모임에 대 한 전체 액세스 권한을 부여 하 고, 교육 (보조 학생) 정책 패키지를 보조 학생의 일괄 처리에 할당 하 여 비공개 통화와 같은 특정 기능을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-157">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="b11ac-158">팀 PowerShell 모듈의 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="b11ac-158">PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="b11ac-159">그룹에 정책 패키지 할당 (예정 대로)</span><span class="sxs-lookup"><span data-stu-id="b11ac-159">Assign a policy package to a group (coming soon)</span></span>   | ||

## <a name="set-the-global-policies"></a><span data-ttu-id="b11ac-160">전역 정책 설정</span><span class="sxs-lookup"><span data-stu-id="b11ac-160">Set the global policies</span></span>

<span data-ttu-id="b11ac-161">각 정책 유형의 전역 (조직 전체 기본값) 정책을 설정 하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b11ac-162">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="b11ac-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="b11ac-163">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 업데이트 하려는 정책 유형의 정책 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="b11ac-164">예를 들어 **팀**  >  **팀 정책**, **모임**  >  **모임 정책**, **메시징 정책**또는 **음성**  >  **통화 정책이**있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-164">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="b11ac-165">현재 설정을 보려면 **전역 (조직 전체 기본값)** 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="b11ac-166">필요에 따라 정책을 업데이트 한 다음 **적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b11ac-167">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="b11ac-167">Using PowerShell</span></span>

<span data-ttu-id="b11ac-168">PowerShell을 사용 하 여 전역 정책을 설정 하려면 전역 식별자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="b11ac-169">먼저 현재 전역 정책을 검토 하 여 변경 하려는 설정을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

```powershell
Get-CsTeamsMessagingPolicy -Identity Global
 
Identity                      : Global
Description                   :
AllowUrlPreviews              : True
AllowOwnerDeleteMessage       : False
AllowUserEditMessage          : True
AllowUserDeleteMessage        : True
AllowUserChat                 : True
AllowRemoveUser               : True
AllowGiphy                    : True
GiphyRatingType               : Moderate
AllowMemes                    : True
AllowImmersiveReader          : True
AllowStickers                 : True
AllowUserTranslation          : False
ReadReceiptsEnabledType       : UserPreference
AllowPriorityMessages         : True
ChannelsInChatListEnabledType : DisabledUserOverride
AudioMessageEnabledType       : ChatsAndChannels
Expand (20 lines) Collapse 
```

<span data-ttu-id="b11ac-170">그런 다음 필요에 따라 전역 정책을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="b11ac-171">변경 하려는 설정에 대 한 값만 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="b11ac-172">개인 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-172">Assign a policy to individual users</span></span>

<span data-ttu-id="b11ac-173">개별 사용자 또는 한 번에 적은 수의 사용자에 게 정책을 할당 하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b11ac-174">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="b11ac-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b11ac-175">사용자에 게 정책을 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="b11ac-176">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-176">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="b11ac-177">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="b11ac-178">할당 하려는 정책을 선택한 다음 **적용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="b11ac-179">또는 다음을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="b11ac-180">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 정책 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="b11ac-181">정책 이름 왼쪽을 클릭 하 여 할당 하려는 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="b11ac-182">**사용자 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="b11ac-183">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가**를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="b11ac-184">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="b11ac-185">사용자 추가를 마쳤으면 **적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b11ac-186">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="b11ac-186">Using PowerShell</span></span>

<span data-ttu-id="b11ac-187">각 정책 형식에는 관리를 위한 고유한 cmdlet 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="b11ac-188">지정 된 ```Grant-``` 정책 형식에 대 한 cmdlet을 사용 하 여 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="b11ac-189">예를 들어 cmdlet을 사용 ```Grant-CsTeamsMeetingPolicy``` 하 여 팀 모임 정책을 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="b11ac-190">이러한 cmdlet은 비즈니스용 Skype Online PowerShell 모듈에 포함 되어 있으며 [비즈니스용 skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="b11ac-191">[비즈니스용 Skype Online PowerShell 모듈](https://www.microsoft.com/en-us/download/details.aspx?id=39366) 을 다운로드 하 여 설치한 후 (아직 없는 경우) 다음을 실행 하 여 비즈니스용 skype online에 연결 하 고 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/en-us/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="b11ac-192">이 예제에서는 학생 모임 정책 이라는 팀 모임 정책을 Reda 이라는 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-192">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="b11ac-193">자세히 알아보려면 [PowerShell을 통한 정책 관리](teams-powershell-managing-teams.md#manage-policies-via-powershell)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-193">To learn more, read [Managing policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-package"></a><span data-ttu-id="b11ac-194">정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-194">Assign a policy package</span></span>

<span data-ttu-id="b11ac-195">팀의 정책 패키지는 조직에서 동일 하거나 비슷한 역할을 하는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정의 모음입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-195">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="b11ac-196">각 정책 패키지는 사용자 역할을 중심으로 설계 되며, 해당 역할에 대 한 일반적인 활동을 지 원하는 미리 정의 된 정책 및 정책 설정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-196">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="b11ac-197">일부 정책 패키지의 예로는 교육 (교사) 패키지 및 의료 (임상 worker) 패키지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-197">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span>

<span data-ttu-id="b11ac-198">정책 패키지를 사용자에 게 할당 하면 패키지의 정책이 만들어지고 사용자의 요구에 맞게 패키지의 각 정책 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-198">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of each policy in the package to meet users' needs.</span></span>

<span data-ttu-id="b11ac-199">정책 패키지를 할당 하 고 관리 하는 방법에 대 한 단계별 지침은 [팀에서 정책 패키지 관리](manage-policy-packages.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-199">To learn more about policy packages, including step-by-step guidance on how to assign and manage them, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="b11ac-200">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-200">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b11ac-201">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="b11ac-201">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b11ac-202">사용자에 게 정책을 대량으로 할당 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-202">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="b11ac-203">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 **사용자**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-203">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="b11ac-204">정책을 할당 하려는 사용자를 검색 하거나 보기를 필터링 하 여 원하는 사용자를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-204">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="b11ac-205">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-205">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="b11ac-206">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-206">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="b11ac-207">**설정 편집**을 클릭하고 원하는 대로 변경한 다음, **적용**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-207">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="b11ac-208">정책 할당의 상태를 확인 하려면 **적용** 을 클릭 하 여 정책 할당을 제출 하 고 **사용자** 페이지 위쪽에 표시 되는 배너에서 **활동 로그**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-208">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="b11ac-209">또는 Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **대시보드로**이동한 다음 **활동 로그**에서 **세부 정보 보기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-209">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="b11ac-210">활동 로그에는 지난 30 일간 Microsoft 팀 관리 센터를 통해 20 명 이상의 사용자 일괄 처리에 대 한 정책 할당이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-210">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="b11ac-211">자세한 내용은 [활동 로그에서 정책 할당 보기](activity-log.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-211">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b11ac-212">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="b11ac-212">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="b11ac-213">현재 일부 팀 정책 유형에는 PowerShell을 사용 하 여 일괄 정책 배정을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-213">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="b11ac-214">지원 되는 정책 유형 목록에 대 한 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-214">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="b11ac-215">일괄 처리 정책 할당을 사용 하면 대규모 사용자 집합에 스크립트를 사용할 필요 없이 한 번에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-215">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="b11ac-216">Cmdlet을 사용 하 여 ```New-CsBatchPolicyAssignmentOperation``` 할당 하려는 사용자의 일괄 처리 및 정책을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-216">You use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="b11ac-217">할당이 백그라운드 작업으로 처리 되 고 각 일괄 처리에 대 한 작업 ID가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-217">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="b11ac-218">그런 다음 cmdlet을 사용 ```Get-CsBatchPolicyAssignmentOperation``` 하 여 일괄 처리에서 배정의 진행률과 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-218">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="b11ac-219">개체 Id 또는 SIP (세션 시작 프로토콜) 주소로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-219">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="b11ac-220">사용자의 SIP 주소는 UPN (사용자 계정 이름) 또는 전자 메일 주소와 같은 값을 갖는 경우가 많지만,이는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-220">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="b11ac-221">사용자가 UPN 또는 전자 메일을 사용 하 여 지정 되었지만 해당 SIP 주소와 다른 값을 가지 면 사용자에 대 한 정책 할당이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-221">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="b11ac-222">일괄 처리에 중복 사용자가 포함 된 경우에는 일괄 처리를 위해 남아 있는 고유 사용자에 대해서만 상태가 제공 되기 전에 중복이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-222">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="b11ac-223">일괄 처리에는 최대 5000 명의 사용자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-223">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="b11ac-224">최상의 결과를 위해서는 한 번에 몇 개의 일괄 처리를 제출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-224">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="b11ac-225">일괄 처리를 완료 하는 데 더 많은 일괄 처리가 가능 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-225">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b11ac-226">Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-226">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b11ac-227">다음을 실행 하 여 [Microsoft 팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams)을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-227">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="b11ac-228">버전 1.0.5 이상이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-228">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b11ac-229">다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-229">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="b11ac-230">메시지가 표시 되 면 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-230">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="b11ac-231">Azure AD PowerShell for Graph 모듈을 설치 하 고 연결 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b11ac-231">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="b11ac-232">또한 [Graph 모듈에 대 한 AZURE Ad PowerShell을 다운로드 하 여 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 하 고 (아직 없는 경우) azure ad에 연결 하 여 조직에서 사용자 목록을 검색할 수 있도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-232">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="b11ac-233">Azure AD에 연결 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-233">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="b11ac-234">메시지가 표시 되 면 팀에 연결 하는 데 사용한 것과 동일한 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-234">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="b11ac-235">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-235">Assign a policy to a batch of users</span></span>

<span data-ttu-id="b11ac-236">이 예제에서는 cmdlet을 사용 ```New-CsBatchPolicyAssignmentOperation``` 하 여 HR 앱 설치 정책 이라는 앱 설정 정책을 Users_ids에 나열 된 사용자 일괄 처리에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-236">In this example, we use the ```New-CsBatchPolicyAssignmentOperation``` cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="b11ac-237">이 예제에서는 Azure AD에 연결 하 여 사용자 컬렉션을 검색 한 다음 해당 SIP 주소를 사용 하 여 지정 된 사용자 일괄 처리에 새 고용 메시징 정책 이라는 메시징 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-237">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

<span data-ttu-id="b11ac-238">자세한 내용은 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-238">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="b11ac-239">일괄 처리의 상태 가져오기</span><span class="sxs-lookup"><span data-stu-id="b11ac-239">Get the status of a batch assignment</span></span>

<span data-ttu-id="b11ac-240">일괄 처리 할당의 상태를 가져오려면 다음을 실행 합니다. 여기서 OperationId는 ```New-CsBatchPolicyAssignmentOperation``` 지정 된 일괄 처리에 대해 cmdlet에서 반환 되는 작업 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-240">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="b11ac-241">출력에 오류가 발생 했음을 표시 하는 경우 다음을 실행 하 여 속성에 있는 오류에 대 한 자세한 정보를 얻을 수 ```UserState``` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-241">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="b11ac-242">자세한 내용은 [get-help를 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="b11ac-242">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="b11ac-243">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-243">Assign a policy to a group</span></span>

<span data-ttu-id="b11ac-244">그룹에 정책 할당을 통해 보안 그룹 또는 조직 구성 단위와 같은 사용자 그룹에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-244">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or organizational unit.</span></span> <span data-ttu-id="b11ac-245">정책 할당은 선행 규칙에 따라 그룹의 구성원에 게 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-245">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="b11ac-246">그룹에서 구성원이 추가 되거나 제거 되 면 그에 따라 상속 된 정책 할당이 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-246">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="b11ac-247">그룹에 대 한 정책 할당은 최대 5만 사용자 그룹에 게 권장 되지만 대규모 그룹 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-247">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="b11ac-248">정책을 할당 하면 그룹에 즉시 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-248">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="b11ac-249">그러나 그룹 구성원에 게 정책 할당의 전파는 백그라운드 작업으로 수행 되며 그룹 크기에 따라 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-249">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="b11ac-250">그룹에서 정책이 할당 되지 않거나 구성원이 그룹에서 추가 되거나 제거 되는 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-250">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="b11ac-251">그룹에 정책 할당에 대해 알아야 할 사항</span><span class="sxs-lookup"><span data-stu-id="b11ac-251">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="b11ac-252">시작 하기 전에 우선 순위 규칙 및 그룹 배정 순위를 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-252">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="b11ac-253">우선 순위 규칙</span><span class="sxs-lookup"><span data-stu-id="b11ac-253">Precedence rules</span></span>

<span data-ttu-id="b11ac-254">지정 된 정책 유형의 경우 사용자의 유효한 정책은 다음에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-254">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="b11ac-255">사용자에 게 직접 할당 되는 정책은 그룹에 할당 된 같은 유형의 다른 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-255">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="b11ac-256">즉, 사용자에 게 지정 된 형식의 정책을 직접 할당 한 경우 해당 사용자는 그룹에서 같은 유형의 정책을 상속 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-256">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="b11ac-257">또한 사용자에 게 직접 할당 된 지정 된 형식의 정책이 있는 경우 해당 정책을 사용자가 제거 해야 그룹에서 같은 유형의 정책을 상속할 수 있습니다.,</span><span class="sxs-lookup"><span data-stu-id="b11ac-257">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="b11ac-258">사용자에 게 직접 할당 된 정책이 없고 두 개 이상의 그룹의 구성원 인 경우 각 그룹에 동일한 유형의 정책이 있는 경우 사용자는 우선 순위가 가장 높은 그룹 할당의 정책을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-258">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="b11ac-259">사용자가 정책이 할당 된 그룹의 구성원이 아니면 해당 정책 유형에 대 한 전역 (조직 차원의 기본) 정책이 사용자에 게 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-259">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="b11ac-260">사용자의 유효 정책은 정책이 할당 된 그룹에서 사용자가 추가 또는 제거 되거나 그룹에서 정책이 할당 되지 않거나 사용자에 게 직접 할당 된 정책이 제거 되는 경우 이러한 규칙에 따라 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-260">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="b11ac-261">그룹 할당 순위</span><span class="sxs-lookup"><span data-stu-id="b11ac-261">Group assignment ranking</span></span>
 
<span data-ttu-id="b11ac-262">그룹에 정책을 할당 하는 경우 그룹 할당에 대 한 순위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-262">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="b11ac-263">이는 사용자가 두 개 이상의 그룹의 구성원 인 경우 각 그룹에 같은 유형의 정책이 할당 되는 경우 사용자가 유효한 정책으로 상속 해야 하는 정책을 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-263">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="b11ac-264">그룹 할당 순위는 같은 종류의 다른 그룹 배정에 대해 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-264">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="b11ac-265">예를 들어, 호출 정책을 두 그룹에 배정 하는 경우 1 개의 배정에 대 한 순위를 1로 설정 하 고, 나머지 하나는 가장 높은 순위를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-265">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="b11ac-266">그룹 할당 순위는 상속과 관련 하 여 다른 그룹 구성원 자격 보다 더 중요 하거나 관련성이 높은 그룹 구성원을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-266">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="b11ac-267">예를 들어 두 개의 그룹이 있고 직원을 저장 하 고 저장소 관리자를 사용 하 고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-267">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="b11ac-268">두 그룹 모두 팀 호출 정책을 할당 하 고 직원을 호출 하 고 정책 및 저장소 관리자 호출 정책을 각각 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-268">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="b11ac-269">두 그룹에 모두 포함 된 저장소 관리자의 경우 관리자 역할은 직원 역할 보다 관련성이 있으므로 스토어 관리자 그룹에 할당 되는 호출 정책은 우선 순위가 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-269">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="b11ac-270">그룹과</span><span class="sxs-lookup"><span data-stu-id="b11ac-270">Group</span></span> |<span data-ttu-id="b11ac-271">팀 호출 정책 이름</span><span class="sxs-lookup"><span data-stu-id="b11ac-271">Teams calling policy name</span></span>  |<span data-ttu-id="b11ac-272">순위</span><span class="sxs-lookup"><span data-stu-id="b11ac-272">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="b11ac-273">스토어 관리자</span><span class="sxs-lookup"><span data-stu-id="b11ac-273">Store Managers</span></span>   |<span data-ttu-id="b11ac-274">스토어 관리자 호출 정책</span><span class="sxs-lookup"><span data-stu-id="b11ac-274">Store Managers Calling Policy</span></span>         |<span data-ttu-id="b11ac-275">1</span><span class="sxs-lookup"><span data-stu-id="b11ac-275">1</span></span>|
|<span data-ttu-id="b11ac-276">직원 저장</span><span class="sxs-lookup"><span data-stu-id="b11ac-276">Store Employees</span></span>    |<span data-ttu-id="b11ac-277">직원에 게 통화 정책 저장</span><span class="sxs-lookup"><span data-stu-id="b11ac-277">Store Employees Calling Policy</span></span>      |<span data-ttu-id="b11ac-278">2</span><span class="sxs-lookup"><span data-stu-id="b11ac-278">2</span></span>|

<span data-ttu-id="b11ac-279">순위를 지정 하지 않으면 정책 할당에 순위가 가장 낮은 것으로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-279">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b11ac-280">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="b11ac-280">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b11ac-281">**이 기능은 아직 출시 되지 않았습니다. 발표 되었으며 곧 제공 될 예정입니다.**</span><span class="sxs-lookup"><span data-stu-id="b11ac-281">**This feature hasn't yet been released. It's been announced, and it's coming soon.**</span></span>

> [!NOTE]
> <span data-ttu-id="b11ac-282">현재 Microsoft 팀 관리 센터를 사용 하는 그룹에 대 한 정책 할당은 팀 호출 정책, 팀 통화 대기 정책, 팀 정책, 팀 live 이벤트 정책, 팀 모임 정책, 팀 메시징 정책에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-282">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="b11ac-283">다른 정책 유형의 경우 PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-283">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="b11ac-284">Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 정책 유형 페이지로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-284">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="b11ac-285">예를 들어 **모임**  >  **모임 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-285">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="b11ac-286">**그룹 정책 할당** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-286">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="b11ac-287">**그룹 추가**를 선택 하 고 **그룹에 정책 할당** 창에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-287">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="b11ac-288">정책을 검색 하 고 할당 하려는 그룹을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-288">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="b11ac-289">그룹 할당에 대 한 순위를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-289">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="b11ac-290">할당 하려는 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-290">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="b11ac-291">**적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-291">Select **Apply**.</span></span>

<span data-ttu-id="b11ac-292">그룹 정책 할당을 제거 하려면 정책 페이지의 **그룹 정책 할당** 탭에서 그룹 할당을 선택한 다음 **제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-292">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="b11ac-293">그룹 할당 순위를 변경 하려면 먼저 그룹 정책 할당을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-293">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="b11ac-294">그런 다음 위의 단계에 따라 정책을 그룹에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-294">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="b11ac-295">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="b11ac-295">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="b11ac-296">현재 모든 팀 정책 유형에는 PowerShell을 사용 하는 그룹에 대 한 정책 할당을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-296">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="b11ac-297">지원 되는 정책 유형 목록에 대 한 [새 CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-297">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b11ac-298">Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-298">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b11ac-299">단계별 지침은 [팀 PowerShell 설치](teams-powershell-install.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-299">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="b11ac-300">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-300">Assign a policy to a group</span></span>

<span data-ttu-id="b11ac-301">Cmdlet을 사용 하 여 ```New-CsGroupPolicyAssignment``` 그룹에 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-301">You use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="b11ac-302">개체 Id, SIP 주소 또는 전자 메일 주소를 사용 하 여 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-302">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="b11ac-303">이 예제에서는 cmdlet을 사용 ```New-CsGroupPolicyAssignment``` 하 여 정품 관리자 모임 정책 이라는 팀 구성원 정책을 할당 순위가 1 인 그룹에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-303">In this example, we use the ```New-CsGroupPolicyAssignment``` cmdlet to assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

<span data-ttu-id="b11ac-304">자세한 내용은 [새 CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-304">To learn more, see [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment).</span></span>

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="b11ac-305">그룹에 대 한 정책 할당 가져오기</span><span class="sxs-lookup"><span data-stu-id="b11ac-305">Get policy assignments for a group</span></span>

<span data-ttu-id="b11ac-306">Cmdlet을 사용 ```Get-CsGroupPolicyAssignment``` 하 여 그룹에 할당 된 모든 정책을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-306">Use the ```Get-CsGroupPolicyAssignment``` cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="b11ac-307">그룹은 해당 SIP 주소 또는 전자 메일 주소가 정책을 할당 하는 데 사용 된 경우에도 그룹 Id에 의해 항상 나열 됨을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-307">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="b11ac-308">이 예제에서는 특정 그룹에 할당 된 모든 정책을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-308">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="b11ac-309">이 예제에서는 팀 모임 정책이 할당 된 모든 그룹을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-309">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

<span data-ttu-id="b11ac-310">자세한 내용은 [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-310">To learn more, see [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment).</span></span>

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="b11ac-311">그룹에서 정책 제거</span><span class="sxs-lookup"><span data-stu-id="b11ac-311">Remove a policy from a group</span></span>

<span data-ttu-id="b11ac-312">Cmdlet을 사용 ```Remove-CsGroupPolicyAssignment``` 하 여 그룹에서 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-312">Use the ```Remove-CsGroupPolicyAssignment``` cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="b11ac-313">그룹에서 정책을 제거 하면 해당 그룹에 할당 된 같은 유형의 다른 정책에 대 한 우선 순위와 순위가 낮게 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-313">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="b11ac-314">예를 들어 순위가 2 인 정책을 제거 하는 경우 3 및 4 순위의 등급이 업데이트 되어 새 순위를 반영 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-314">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="b11ac-315">다음 두 테이블은이 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-315">The following two tables show this example.</span></span>

<span data-ttu-id="b11ac-316">팀 모임 정책에 대 한 정책 과제 및 우선 순위 목록은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-316">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="b11ac-317">그룹 이름</span><span class="sxs-lookup"><span data-stu-id="b11ac-317">Group name</span></span>  |<span data-ttu-id="b11ac-318">정책 이름</span><span class="sxs-lookup"><span data-stu-id="b11ac-318">Policy name</span></span>  |<span data-ttu-id="b11ac-319">순위</span><span class="sxs-lookup"><span data-stu-id="b11ac-319">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b11ac-320">영업</span><span class="sxs-lookup"><span data-stu-id="b11ac-320">Sales</span></span>    |<span data-ttu-id="b11ac-321">판매 정책</span><span class="sxs-lookup"><span data-stu-id="b11ac-321">Sales policy</span></span>       | <span data-ttu-id="b11ac-322">1</span><span class="sxs-lookup"><span data-stu-id="b11ac-322">1</span></span>        |
|<span data-ttu-id="b11ac-323">서쪽 지역</span><span class="sxs-lookup"><span data-stu-id="b11ac-323">West Region</span></span>     |<span data-ttu-id="b11ac-324">서쪽 지역 정책</span><span class="sxs-lookup"><span data-stu-id="b11ac-324">West Region policy</span></span>         |<span data-ttu-id="b11ac-325">2</span><span class="sxs-lookup"><span data-stu-id="b11ac-325">2</span></span>         |
|<span data-ttu-id="b11ac-326">나눠</span><span class="sxs-lookup"><span data-stu-id="b11ac-326">Division</span></span>    |<span data-ttu-id="b11ac-327">디비전 정책</span><span class="sxs-lookup"><span data-stu-id="b11ac-327">Division policy</span></span>         |<span data-ttu-id="b11ac-328">3</span><span class="sxs-lookup"><span data-stu-id="b11ac-328">3</span></span>         |
|<span data-ttu-id="b11ac-329">대리점</span><span class="sxs-lookup"><span data-stu-id="b11ac-329">Subsidiary</span></span>   |<span data-ttu-id="b11ac-330">자회사 정책</span><span class="sxs-lookup"><span data-stu-id="b11ac-330">Subsidiary policy</span></span>        |<span data-ttu-id="b11ac-331">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="b11ac-331">4</span></span>         |

<span data-ttu-id="b11ac-332">서쪽 지역 그룹에서 서쪽 지역 정책을 제거 하는 경우 정책 할당 및 우선 순위는 다음과 같이 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-332">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="b11ac-333">그룹 이름</span><span class="sxs-lookup"><span data-stu-id="b11ac-333">Group name</span></span>  |<span data-ttu-id="b11ac-334">정책 이름</span><span class="sxs-lookup"><span data-stu-id="b11ac-334">Policy name</span></span>  |<span data-ttu-id="b11ac-335">순위</span><span class="sxs-lookup"><span data-stu-id="b11ac-335">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="b11ac-336">영업</span><span class="sxs-lookup"><span data-stu-id="b11ac-336">Sales</span></span>    |<span data-ttu-id="b11ac-337">판매 정책</span><span class="sxs-lookup"><span data-stu-id="b11ac-337">Sales policy</span></span>       | <span data-ttu-id="b11ac-338">1</span><span class="sxs-lookup"><span data-stu-id="b11ac-338">1</span></span>        |
|<span data-ttu-id="b11ac-339">나눠</span><span class="sxs-lookup"><span data-stu-id="b11ac-339">Division</span></span>    |<span data-ttu-id="b11ac-340">디비전 정책</span><span class="sxs-lookup"><span data-stu-id="b11ac-340">Division policy</span></span>         |<span data-ttu-id="b11ac-341">2</span><span class="sxs-lookup"><span data-stu-id="b11ac-341">2</span></span>         |
|<span data-ttu-id="b11ac-342">대리점</span><span class="sxs-lookup"><span data-stu-id="b11ac-342">Subsidiary</span></span>   |<span data-ttu-id="b11ac-343">자회사 정책</span><span class="sxs-lookup"><span data-stu-id="b11ac-343">Subsidiary policy</span></span>        |<span data-ttu-id="b11ac-344">3</span><span class="sxs-lookup"><span data-stu-id="b11ac-344">3</span></span>        |

<span data-ttu-id="b11ac-345">이 예제에서는 그룹에서 팀 모임 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-345">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

<span data-ttu-id="b11ac-346">자세한 내용은 [-CsGroupPolicyAssignment 제거](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-346">To learn more, see [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment).</span></span>

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="b11ac-347">그룹에 대 한 정책 할당 변경</span><span class="sxs-lookup"><span data-stu-id="b11ac-347">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="b11ac-348">```Set-CsGroupPolicyAssignment```Cmdlet은 곧 제공 될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-348">The ```Set-CsGroupPolicyAssignment``` cmdlet will be available soon.</span></span> <span data-ttu-id="b11ac-349">그 동안 그룹 정책 할당을 변경 하려면 그룹에서 현재 정책 할당을 제거한 다음 새 정책 할당을 추가 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-349">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="b11ac-350">그룹에 정책을 할당 한 후 cmdlet을 사용 ```Set-CsGroupPolicyAssignment``` 하 여 다음과 같이 해당 그룹의 정책 할당을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-350">After you assign a policy to a group, you can use the ```Set-CsGroupPolicyAssignment``` cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="b11ac-351">순위 변경</span><span class="sxs-lookup"><span data-stu-id="b11ac-351">Change the ranking</span></span>
- <span data-ttu-id="b11ac-352">지정 된 정책 유형의 정책 변경</span><span class="sxs-lookup"><span data-stu-id="b11ac-352">Change the policy of a given policy type</span></span>
- <span data-ttu-id="b11ac-353">지정 된 정책 유형 및 순위에 대 한 정책 변경</span><span class="sxs-lookup"><span data-stu-id="b11ac-353">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="b11ac-354">이 예제에서는 그룹의 팀 통화 대기 정책을 SupportCallPark 정책으로 변경 하 고 3으로 할당 순위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-354">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

<span data-ttu-id="b11ac-355">자세한 내용은 [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-355">To learn more, see [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment).</span></span>



#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="b11ac-356">사용자에 대 한 유효 정책 변경</span><span class="sxs-lookup"><span data-stu-id="b11ac-356">Change the effective policy for a user</span></span>

<span data-ttu-id="b11ac-357">다음은 정책을 직접 할당 받은 사용자의 유효 정책을 변경 하는 방법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-357">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="b11ac-358">먼저, ```Get-CsUserPolicyAssignment``` cmdlet을 매개 변수와 함께 사용 하 여 ```PolicySource``` 사용자와 연결 된 팀 모임 브로드캐스트 정책의 세부 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-358">First, we use the ```Get-CsUserPolicyAssignment``` cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> <span data-ttu-id="b11ac-359">자세한 내용은 [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-359">To learn more, see [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment).</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="b11ac-360">출력은 사용자가 사용자가 속한 그룹에 할당 된 공급 업체 라이브 이벤트 정책 보다 우선 하는 직원 이벤트 라는 팀에 게 직접 할당 된 모임 브로드캐스트 정책에 대 한 작업을 수행 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-360">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="b11ac-361">이제 사용자의 직원 이벤트 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-361">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="b11ac-362">즉, 사용자에 게는 더 이상 팀 모임 브로드캐스트 정책이 직접 할당 되어 있지 않으며 사용자가 속한 그룹에 할당 된 공급 업체 Live 이벤트 정책이 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-362">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="b11ac-363">비즈니스용 Skype PowerShell 모듈에서 다음 cmdlet을 사용 하 여이 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-363">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="b11ac-364">팀 Powershell 모듈에서 다음 cmdlet을 사용 하 여 일괄 처리 정책 할당 인 경우에는이 작업을 수행할 수 있으며, 여기서 $users는 사용자가 지정 하는 사용자의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-364">You can use following cmdlet in the Teams Powershell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="b11ac-365">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-365">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="b11ac-366">일괄 처리 정책 패키지를 사용 하는 경우 스크립트를 사용할 필요 없이 한 번에 대규모 사용자 집합에 정책 패키지를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-366">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="b11ac-367">Cmdlet을 사용 하 여 ```New-CsBatchPolicyPackageAssignmentOperation``` 할당 하려는 사용자 일괄 처리 및 정책 패키지를 제출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-367">You use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="b11ac-368">할당이 백그라운드 작업으로 처리 되 고 각 일괄 처리에 대 한 작업 ID가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-368">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="b11ac-369">그런 다음 cmdlet을 사용 ```Get-CsBatchPolicyAssignmentOperation``` 하 여 일괄 처리에서 배정의 진행률과 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-369">You can then use the ```Get-CsBatchPolicyAssignmentOperation``` cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="b11ac-370">개체 Id 또는 SIP (세션 시작 프로토콜) 주소로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-370">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="b11ac-371">사용자의 SIP 주소는 UPN (사용자 계정 이름) 또는 전자 메일 주소와 같은 값을 갖는 경우가 많지만,이는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-371">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="b11ac-372">사용자가 UPN 또는 전자 메일을 사용 하 여 지정 되었지만 해당 SIP 주소와 다른 값을 가지 면 사용자에 대 한 정책 할당이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-372">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="b11ac-373">일괄 처리에 중복 사용자가 포함 된 경우에는 일괄 처리를 위해 남아 있는 고유 사용자에 대해서만 상태가 제공 되기 전에 중복이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-373">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="b11ac-374">일괄 처리에는 최대 5000 명의 사용자를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-374">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="b11ac-375">최상의 결과를 위해서는 한 번에 몇 개의 일괄 처리를 제출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-375">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="b11ac-376">일괄 처리를 완료 하는 데 더 많은 일괄 처리가 가능 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-376">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="b11ac-377">Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-377">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="b11ac-378">다음을 실행 하 여 [Microsoft 팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams) 을 설치 합니다 (아직 없는 경우).</span><span class="sxs-lookup"><span data-stu-id="b11ac-378">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="b11ac-379">버전 1.0.5 이상이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-379">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="b11ac-380">다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-380">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="b11ac-381">메시지가 표시 되 면 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-381">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="b11ac-382">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="b11ac-382">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="b11ac-383">이 예제에서는 cmdlet을 사용 ```New-CsBatchPolicyPackageAssignmentOperation``` 하 여 Education_PrimaryStudent 정책 패키지를 일괄 사용자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-383">In this example, we use the ```New-CsBatchPolicyPackageAssignmentOperation``` cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

<span data-ttu-id="b11ac-384">자세한 내용은 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b11ac-384">To learn more, see [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation).</span></span>

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="b11ac-385">일괄 처리의 상태 가져오기</span><span class="sxs-lookup"><span data-stu-id="b11ac-385">Get the status of a batch assignment</span></span>

<span data-ttu-id="b11ac-386">일괄 처리 할당의 상태를 가져오려면 다음을 실행 합니다. 여기서 OperationId는 ```New-CsBatchPolicyAssignmentOperation``` 지정 된 일괄 처리에 대해 cmdlet에서 반환 되는 작업 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-386">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="b11ac-387">출력에 오류가 발생 했음을 표시 하는 경우 다음을 실행 하 여 속성에 있는 오류에 대 한 자세한 정보를 얻을 수 ```UserState``` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b11ac-387">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="b11ac-388">자세한 내용은 [get-help를 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="b11ac-388">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="b11ac-389">관련 항목</span><span class="sxs-lookup"><span data-stu-id="b11ac-389">Related topics</span></span>

[<span data-ttu-id="b11ac-390">팀 PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="b11ac-390">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
