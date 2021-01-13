---
title: Microsoft Teams에서 사용자에게 정책 할당
author: cichur
ms.author: v-cichur
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
description: Microsoft Teams에서 사용자에게 정책을 할당하는 다양한 방법을 배워야 합니다.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 5d213c53de22994d46e7d7faf54a8dfd687806d7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821308"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="26eb4-103">Microsoft Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="26eb4-104">관리자는 정책을 사용하여 조직의 사용자가 사용할 수 있는 Teams 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="26eb4-105">예를 들어 몇 가지 이름을 지정하기 위해 호출 정책, 모임 정책 및 메시징 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="26eb4-106">조직에는 고유한 요구 사항을 가지고 있는 다양한 유형의 사용자와 사용자가 만들고 할당하는 사용자 지정 정책을 통해 이러한 요구에 따라 다양한 사용자 집합에 정책 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-106">Organizations have different types of users with unique needs and custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="26eb4-107">조직에서 정책을 보다 쉽게 관리할 수 있도록 Teams는 사용자에게 정책을 할당하는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-107">To make it easier to manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="26eb4-108">개별적으로 또는 대규모로 일괄 처리 할당을 통해 또는 사용자가 구성원인 그룹에 직접 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-108">You can assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="26eb4-109">정책 패키지를 사용하여 비슷한 역할이 있는 조직의 사용자에게 미리 설정한 정책 컬렉션을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-109">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="26eb4-110">선택하는 옵션은 관리되는 정책의 수와 할당하는 사용자 수에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-110">The option that you choose depends on the number of policies that you're managing and the number of users that you're assigning to.</span></span> <span data-ttu-id="26eb4-111">조직에서 가장 많은 수의 사용자에게 적용될 수 있도록 전역(조직 전체 기본값) 정책을 설정하면 특수한 정책이 필요한 사용자에게만 정책을 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-111">By setting the global (Org-wide default) policies so that they apply to the largest number of users in your organization, you only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="26eb4-112">이 문서에서는 사용자에게 정책을 할당할 수 있는 다양한 방법 및 권장되는 시나리오를 사용하는 경우를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-112">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="26eb4-113">어떤 정책이 우선하나요?</span><span class="sxs-lookup"><span data-stu-id="26eb4-113">Which policy takes precedence?</span></span>

<span data-ttu-id="26eb4-114">사용자에게는 각 정책 유형에 대한 하나의 유효 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-114">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="26eb4-115">사용자에게 정책이 직접 할당되거나 동일한 유형의 정책이 할당된 하나 이상의 그룹의 구성원일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-115">It's possible or even likely that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="26eb4-116">이러한 종류의 시나리오에서 어떤 정책이 우선할까요?</span><span class="sxs-lookup"><span data-stu-id="26eb4-116">In these kinds of scenarios, which policy takes precedence?</span></span>  <span data-ttu-id="26eb4-117">사용자의 유효 정책은 다음과 같이 우선 순위 규칙에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-117">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="26eb4-118">사용자에게 정책이 직접 할당된 경우(개별적으로 또는 일괄 처리 할당을 통해) 해당 정책이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-118">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="26eb4-119">다음 예제에서 사용자의 유효 정책은 사용자에게 직접 할당되는 Lincoln Square 모임 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-119">In the following example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![직접 할당된 정책이 우선하는 방법을 보여주는 다이어그램](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="26eb4-121">사용자에게 지정된 유형의 정책이 직접 할당되지 않은 경우 사용자가 구성원인 그룹에 할당된 정책이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-121">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="26eb4-122">사용자가 여러 그룹의 구성원인 경우 지정한 정책 [](#group-assignment-ranking) 유형에 대해 그룹 할당 순위가 가장 높은 정책이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-122">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="26eb4-123">이 예제에서 사용자의 유효 정책은 Exec Teams 및 HD 정책으로, 사용자가 구성원인 다른 그룹에 비해 할당 순위가 가장 높고 동일한 정책 유형의 정책도 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-123">In this example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![그룹에서 상속된 정책이 어떻게 우선하는지 보여주는 다이어그램](media/assign-policies-example-group.png)

<span data-ttu-id="26eb4-125">사용자에게 정책이 직접 할당되지 않은 경우 또는 정책이 할당된 그룹의 구성원이 아닌 경우 사용자는 해당 정책 유형에 대한 전역(Org 전체 기본값) 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-125">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="26eb4-126">예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-126">Here's an example.</span></span>

![전역 정책이 어떻게 우선하는지 보여주는 다이어그램](media/assign-policies-example-global.png)

<span data-ttu-id="26eb4-128">자세한 내용은 우선 순위 규칙을 [참조합니다.](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="26eb4-128">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="26eb4-129">정책을 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="26eb4-129">Ways to assign policies</span></span>

<span data-ttu-id="26eb4-130">다음은 사용자에게 정책을 할당할 수 있는 방법과 각각에 대한 권장 시나리오에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-130">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="26eb4-131">자세한 내용을 보려면 링크를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="26eb4-131">Click the links to learn more.</span></span>

<span data-ttu-id="26eb4-132">개별 사용자 또는 그룹에 정책을 할당하기 전에 먼저 조직에서 가장 많은 수의 사용자에게 적용될 수 있도록 전역(조직 전체 [기본값)](#set-the-global-policies) 정책을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-132">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="26eb4-133">전역 정책이 설정되고 나면 특수한 정책이 필요한 사용자에게만 정책을 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-133">Once the global policies are set, you will only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="26eb4-134">방법</span><span class="sxs-lookup"><span data-stu-id="26eb4-134">Do this</span></span>  |<span data-ttu-id="26eb4-135">If...</span><span class="sxs-lookup"><span data-stu-id="26eb4-135">If...</span></span>  | <span data-ttu-id="26eb4-136">사용 중...</span><span class="sxs-lookup"><span data-stu-id="26eb4-136">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="26eb4-137">개별 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-137">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="26eb4-138">Teams를 시작하거나 소수의 사용자에게 정책 하나 또는 몇 개만 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-138">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="26eb4-139">비즈니스용 Skype Online PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="26eb4-139">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="26eb4-140">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-140">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="26eb4-141">사용자의 그룹 멤버 자격에 따라 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-141">You need to assign policies based on a user's group membership.</span></span> <span data-ttu-id="26eb4-142">예를 들어 보안 그룹 또는 메일 그룹의 모든 사용자에게 정책을 할당하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-142">For example, you want to assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="26eb4-143">Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="26eb4-143">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="26eb4-144">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-144">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="26eb4-145">대규모 사용자 집합에 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-145">You need to assign policies to large sets of users.</span></span> <span data-ttu-id="26eb4-146">예를 들어 조직에서 수백 또는 수천 명의 사용자에게 정책을 한에 할당하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-146">For example, you want to assign a policy to hundreds or thousands of users in your organization at a time.</span></span>  |<span data-ttu-id="26eb4-147">Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="26eb4-147">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="26eb4-148">사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-148">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  | <span data-ttu-id="26eb4-149">동일하거나 유사한 역할이 있는 조직의 특정 사용자 집합에 여러 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-149">You need to assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="26eb4-150">예를 들어 학교의 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 권한을 학생에게 부여하고, 보조 학생에게 교육(중등 학생) 정책 패키지를 할당하여 비공개 통화와 같은 특정 기능을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-150">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings and the Education (Secondary school student) policy package to secondary students to limit certain capabilities like private calling.</span></span>  |<span data-ttu-id="26eb4-151">Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="26eb4-151">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="26eb4-152">[그룹에 정책 패키지 할당(비공개](#assign-a-policy-package-to-a-group) 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="26eb4-152">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="26eb4-153">동일한 역할 또는 유사한 역할이 있는 조직의 사용자 그룹에 여러 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-153">You need to assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="26eb4-154">예를 들어 보안 그룹 또는 메일 그룹의 모든 사용자에게 정책 패키지를 할당하려는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-154">For example, you want to assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="26eb4-155">Teams PowerShell 모듈의 Microsoft Teams 관리 센터(출시 예정) 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="26eb4-155">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="26eb4-156">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-156">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="26eb4-157">동일하거나 유사한 역할이 있는 조직의 사용자 일괄 처리에 여러 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-157">You need to assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="26eb4-158">예를 들어 일괄 처리 할당을 사용하여 학교의 모든 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 권한을 부여하고, 개인 통화와 같은 특정 기능을 제한하기 위해 보조 학생 일괄 처리에 교육(중등 학생) 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-158">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings and assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities like private calling.</span></span>|<span data-ttu-id="26eb4-159">Teams PowerShell 모듈의 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="26eb4-159">PowerShell cmdlets in the Teams PowerShell module</span></span>|


## <a name="set-the-global-policies"></a><span data-ttu-id="26eb4-160">전역 정책 설정</span><span class="sxs-lookup"><span data-stu-id="26eb4-160">Set the global policies</span></span>

<span data-ttu-id="26eb4-161">다음 단계에 따라 각 정책 유형에 대한 전역(전체 기본) 정책을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="26eb4-161">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="26eb4-162">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="26eb4-162">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="26eb4-163">Microsoft Teams 관리 센터의 왼쪽 탐색에서 업데이트하려는 정책 유형에 대한 정책 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-163">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="26eb4-164">예를 들어 **Teams** Teams  >  **정책,** **모임** 모임 정책, 메시징 정책 또는 음성 통화  >      >  **정책이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-164">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="26eb4-165">**전역(전체 기본값)** 정책을 선택하여 현재 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-165">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="26eb4-166">필요한 경우 정책을 업데이트한 다음 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-166">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="26eb4-167">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="26eb4-167">Using PowerShell</span></span>

<span data-ttu-id="26eb4-168">PowerShell을 사용하여 전역 정책을 설정하기 위해 전역 식별자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-168">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="26eb4-169">먼저 현재 전역 정책을 검토하여 변경할 설정을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-169">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="26eb4-170">다음으로, 필요한 경우 전역 정책을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-170">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="26eb4-171">변경하려는 설정의 값만 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-171">You only need to specify values for the settings that you want to change.</span></span> 
 
```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="26eb4-172">개별 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-172">Assign a policy to individual users</span></span>

<span data-ttu-id="26eb4-173">다음 단계에 따라 개별 사용자 또는 적은 수의 사용자에게 한도에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-173">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="26eb4-174">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="26eb4-174">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="26eb4-175">사용자에게 정책을 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="26eb4-175">To assign a policy to a user:</span></span>

1. <span data-ttu-id="26eb4-176">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자** 로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-176">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="26eb4-177">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-177">Select the user by clicking to the left of the user name, and then click **Edit settings**.</span></span>
3. <span data-ttu-id="26eb4-178">할당할 정책을 선택한 다음 적용을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-178">Select the policy you want to assign, and then click **Apply**.</span></span>

<span data-ttu-id="26eb4-179">또는 다음을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-179">Or, you can also do the following:</span></span>

1. <span data-ttu-id="26eb4-180">Microsoft Teams 관리 센터의 왼쪽 탐색에서 정책 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-180">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="26eb4-181">정책 이름 왼쪽을 클릭하여 할당할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-181">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="26eb4-182">**사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-182">Select **Manage users**.</span></span>
4. <span data-ttu-id="26eb4-183">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="26eb4-183">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="26eb4-184">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-184">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="26eb4-185">사용자 추가를 마쳤을 때 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-185">When you're finished adding users, select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="26eb4-186">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="26eb4-186">Using PowerShell</span></span>

<span data-ttu-id="26eb4-187">각 정책 유형에는 관리하기 위한 자체 cmdlet 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-187">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="26eb4-188">특정 정책 유형에 ```Grant-``` cmdlet을 사용하여 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-188">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="26eb4-189">예를 들어 ```Grant-CsTeamsMeetingPolicy``` cmdlet을 사용하여 사용자에게 Teams 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-189">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="26eb4-190">이러한 cmdlet은 비즈니스용 Skype Online PowerShell 모듈에 포함되어 있으며 비즈니스용 [Skype cmdlet 참조에 설명되어 있습니다.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="26eb4-190">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="26eb4-191">비즈니스용 [Skype Online PowerShell](https://www.microsoft.com/download/details.aspx?id=39366) 모듈을 다운로드하여 설치한 다음(아직 설치하지 않은 경우) 다음을 실행하여 비즈니스용 Skype Online에 연결하고 세션을 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="26eb4-191">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="26eb4-192">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-192">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="26eb4-193">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-193">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="26eb4-194">이 예제에서는 Reda라는 사용자에게 학생 모임 정책이라는 Teams 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-194">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="26eb4-195">자세한 내용은 [PowerShell을 통해 정책 관리를 읽어보아야 합니다.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="26eb4-195">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="26eb4-196">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-196">Assign a policy to a group</span></span>

<span data-ttu-id="26eb4-197">그룹에 정책 할당을 사용하면 보안 그룹 또는 메일 그룹과 같은 사용자 그룹에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-197">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="26eb4-198">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-198">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="26eb4-199">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-199">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="26eb4-200">그룹에 대한 정책 할당은 최대 50,000명 사용자 그룹에 권장되지만 더 큰 그룹에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-200">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="26eb4-201">정책을 할당하면 해당 정책이 그룹에 즉시 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-201">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="26eb4-202">그러나 그룹의 구성원에게 정책 할당을 전파하는 작업은 백그라운드 작업으로 수행하며 그룹의 크기에 따라 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-202">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="26eb4-203">그룹에서 정책의 부가가치가 없는 경우 또는 구성원이 그룹에 추가되거나 그룹에서 제거될 때도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-203">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="26eb4-204">그룹 정책 할당은 그룹의 직접 구성원인 사용자에게만 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-204">Group policy assignments are only propagated to users that are direct members of the group.</span></span> <span data-ttu-id="26eb4-205">할당은 중첩된 그룹의 멤버에게 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-205">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="26eb4-206">그룹에 정책 할당에 대해 알아야 할 정보</span><span class="sxs-lookup"><span data-stu-id="26eb4-206">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="26eb4-207">시작하기 전에 우선 순위 규칙 및 그룹 할당 순위를 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-207">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="26eb4-208">우선 순위 규칙</span><span class="sxs-lookup"><span data-stu-id="26eb4-208">Precedence rules</span></span>

<span data-ttu-id="26eb4-209">주어진 정책 유형에 대해 사용자의 유효 정책은 다음에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-209">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="26eb4-210">사용자에게 직접 할당된 정책이 그룹에 할당된 동일한 유형의 다른 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-210">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="26eb4-211">즉, 사용자에게 지정된 형식의 정책이 직접 할당된 경우 해당 사용자는 그룹에서 동일한 형식의 정책을 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-211">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="26eb4-212">즉, 사용자에게 직접 할당된 지정된 형식의 정책이 있는 경우 그룹에서 동일한 형식의 정책을 상속하려면 먼저 사용자로부터 해당 정책을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-212">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="26eb4-213">사용자에게 직접 할당된 정책이 없고 둘 이상의 그룹의 구성원이고 각 그룹에 할당된 동일한 유형의 정책이 있는 경우 사용자는 가장 높은 순위를 가지는 그룹 할당의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-213">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="26eb4-214">사용자가 정책이 할당된 그룹의 구성원이 아닌 경우 해당 정책 유형에 대한 전역(전체 기본값) 정책이 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-214">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="26eb4-215">사용자의 유효 정책은 사용자가 정책이 할당된 그룹에 추가되거나 제거되거나, 그룹에서 정책이 할당되지 않은 경우 또는 사용자에게 직접 할당된 정책이 제거될 때 이러한 규칙에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-215">A user's effective policy is updated according to these rules when a user is added to or removed from a group that's assigned a policy, a policy is unassigned from a group, or a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="26eb4-216">그룹 할당 순위</span><span class="sxs-lookup"><span data-stu-id="26eb4-216">Group assignment ranking</span></span>
 
<span data-ttu-id="26eb4-217">그룹에 정책을 할당할 때 그룹 할당에 대한 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-217">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="26eb4-218">이 정책은 사용자가 둘 이상의 그룹의 구성원이고 각 그룹에 동일한 유형의 정책이 할당된 경우 사용자가 유효 정책으로 상속해야 하는 정책을 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-218">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="26eb4-219">그룹 할당 순위는 동일한 유형의 다른 그룹 할당에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-219">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="26eb4-220">예를 들어 호출 정책을 두 그룹에 할당하는 경우 한 할당의 순위를 1로 설정하고 다른 할당은 2로 설정하고 1은 가장 높은 순위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-220">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="26eb4-221">그룹 할당 순위는 상속과 관련하여 다른 그룹 멤버 자격보다 더 중요하거나 관련성이 높은 그룹 멤버 자격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-221">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>
 
<span data-ttu-id="26eb4-222">예를 들어 두 개의 그룹인 Store Employees와 Store Manager가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-222">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="26eb4-223">두 그룹에는 Teams 통화 정책, 스토어 직원 통화 정책 및 스토어 관리자 통화 정책이 각각 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-223">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="26eb4-224">두 그룹에 모두 있는 스토어 관리자의 경우 관리자 역할은 직원 역할보다 관련성이 높기 때문에 스토어 관리자 그룹에 할당된 호출 정책의 순위가 더 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-224">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="26eb4-225">그룹</span><span class="sxs-lookup"><span data-stu-id="26eb4-225">Group</span></span> |<span data-ttu-id="26eb4-226">정책 이름을 호출하는 팀</span><span class="sxs-lookup"><span data-stu-id="26eb4-226">Teams calling policy name</span></span>  |<span data-ttu-id="26eb4-227">순위</span><span class="sxs-lookup"><span data-stu-id="26eb4-227">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="26eb4-228">스토어 관리자</span><span class="sxs-lookup"><span data-stu-id="26eb4-228">Store Managers</span></span>   |<span data-ttu-id="26eb4-229">스토어 관리자 호출 정책</span><span class="sxs-lookup"><span data-stu-id="26eb4-229">Store Managers Calling Policy</span></span>         |<span data-ttu-id="26eb4-230">1</span><span class="sxs-lookup"><span data-stu-id="26eb4-230">1</span></span>|
|<span data-ttu-id="26eb4-231">직원 저장</span><span class="sxs-lookup"><span data-stu-id="26eb4-231">Store Employees</span></span>    |<span data-ttu-id="26eb4-232">직원 호출 정책 저장</span><span class="sxs-lookup"><span data-stu-id="26eb4-232">Store Employees Calling Policy</span></span>      |<span data-ttu-id="26eb4-233">2</span><span class="sxs-lookup"><span data-stu-id="26eb4-233">2</span></span>|

<span data-ttu-id="26eb4-234">순위를 지정하지 않으면 정책 할당에 가장 낮은 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-234">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span> 

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="26eb4-235">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="26eb4-235">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="26eb4-236">현재 Microsoft Teams 관리 센터를 사용하는 그룹에 대한 정책 할당은 Teams 통화 정책, Teams 호출 공원 정책, Teams 정책, Teams 라이브 이벤트 정책, Teams 모임 정책 및 Teams 메시징 정책에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-236">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="26eb4-237">다른 정책 형식의 경우 PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-237">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="26eb4-238">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 정책 유형 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-238">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="26eb4-239">예를 들어 모임 모임  >  **정책으로 이동**</span><span class="sxs-lookup"><span data-stu-id="26eb4-239">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="26eb4-240">그룹 정책 **할당 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-240">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="26eb4-241">그룹 **추가를 선택하고** 그룹 창에 정책 할당 **창에서** 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-241">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="26eb4-242">정책을 할당할 그룹을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-242">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="26eb4-243">그룹 할당의 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-243">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="26eb4-244">할당하려는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-244">Select the policy that you want to assign.</span></span> 
    4. <span data-ttu-id="26eb4-245">적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-245">Select **Apply**.</span></span>

<span data-ttu-id="26eb4-246">그룹 정책 할당을 제거하려면  정책 페이지의 그룹 정책 할당 탭에서 그룹 할당을 선택한 다음 제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-246">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="26eb4-247">그룹 할당의 순위를 변경하려면 먼저 그룹 정책 할당을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-247">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="26eb4-248">그런 다음 위의 단계에 따라 그룹에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-248">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="26eb4-249">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="26eb4-249">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="26eb4-250">현재 PowerShell을 사용하는 그룹에 대한 정책 할당은 모든 Teams 정책 유형에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-250">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="26eb4-251">지원되는 정책 유형 목록은 [New-CsGroupPolicyAssignment를](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26eb4-251">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="26eb4-252">Microsoft Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="26eb4-252">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="26eb4-253">단계별 지침은 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="26eb4-253">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="26eb4-254">사용자 그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-254">Assign a policy to a group of users</span></span>

<span data-ttu-id="26eb4-255">[New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-255">You use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="26eb4-256">개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-256">You can specify a group by using the object Id, SIP address, or email address.</span></span>

<span data-ttu-id="26eb4-257">이 예제에서는 할당 순위가 1인 그룹에 Retail Managers 모임 정책이라는 Teams 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-257">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="26eb4-258">그룹에 대한 정책 할당을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-258">Get policy assignments for a group</span></span>

<span data-ttu-id="26eb4-259">[Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 할당된 모든 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-259">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="26eb4-260">정책을 할당하는 데 SIP 주소 또는 전자 메일 주소가 사용된 경우에도 그룹은 항상 그룹 ID에 의해 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-260">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="26eb4-261">이 예제에서는 특정 그룹에 할당된 모든 정책을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-261">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="26eb4-262">이 예제에서는 Teams 모임 정책이 할당된 모든 그룹을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-262">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="26eb4-263">그룹에서 정책 제거</span><span class="sxs-lookup"><span data-stu-id="26eb4-263">Remove a policy from a group</span></span>

<span data-ttu-id="26eb4-264">[Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet을 사용하여 그룹에서 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-264">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="26eb4-265">그룹에서 정책을 제거하면 해당 그룹에 할당된 동일한 유형의 다른 정책의 우선 순위가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-265">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group and that have a lower ranking are updated.</span></span> <span data-ttu-id="26eb4-266">예를 들어 순위가 2인 정책을 제거하면 순위가 3과 4인 정책이 새 순위를 반영하여 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-266">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="26eb4-267">다음 두 표에서는 이 예제를 보여 주겠습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-267">The following two tables show this example.</span></span>

<span data-ttu-id="26eb4-268">다음은 Teams 모임 정책에 대한 정책 할당 및 우선 순위 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-268">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="26eb4-269">그룹 이름</span><span class="sxs-lookup"><span data-stu-id="26eb4-269">Group name</span></span>  |<span data-ttu-id="26eb4-270">정책 이름</span><span class="sxs-lookup"><span data-stu-id="26eb4-270">Policy name</span></span>  |<span data-ttu-id="26eb4-271">순위</span><span class="sxs-lookup"><span data-stu-id="26eb4-271">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="26eb4-272">영업</span><span class="sxs-lookup"><span data-stu-id="26eb4-272">Sales</span></span>    |<span data-ttu-id="26eb4-273">판매 정책</span><span class="sxs-lookup"><span data-stu-id="26eb4-273">Sales policy</span></span>       | <span data-ttu-id="26eb4-274">1</span><span class="sxs-lookup"><span data-stu-id="26eb4-274">1</span></span>        |
|<span data-ttu-id="26eb4-275">서부 지역</span><span class="sxs-lookup"><span data-stu-id="26eb4-275">West Region</span></span>     |<span data-ttu-id="26eb4-276">서부 지역 정책</span><span class="sxs-lookup"><span data-stu-id="26eb4-276">West Region policy</span></span>         |<span data-ttu-id="26eb4-277">2</span><span class="sxs-lookup"><span data-stu-id="26eb4-277">2</span></span>         |
|<span data-ttu-id="26eb4-278">Division</span><span class="sxs-lookup"><span data-stu-id="26eb4-278">Division</span></span>    |<span data-ttu-id="26eb4-279">부서 정책</span><span class="sxs-lookup"><span data-stu-id="26eb4-279">Division policy</span></span>         |<span data-ttu-id="26eb4-280">3</span><span class="sxs-lookup"><span data-stu-id="26eb4-280">3</span></span>         |
|<span data-ttu-id="26eb4-281">자회사</span><span class="sxs-lookup"><span data-stu-id="26eb4-281">Subsidiary</span></span>   |<span data-ttu-id="26eb4-282">자회사 정책</span><span class="sxs-lookup"><span data-stu-id="26eb4-282">Subsidiary policy</span></span>        |<span data-ttu-id="26eb4-283">4</span><span class="sxs-lookup"><span data-stu-id="26eb4-283">4</span></span>         |

<span data-ttu-id="26eb4-284">서부 지역 그룹에서 서부 지역 정책을 제거하면 정책 할당 및 우선 순위가 다음과 같이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-284">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="26eb4-285">그룹 이름</span><span class="sxs-lookup"><span data-stu-id="26eb4-285">Group name</span></span>  |<span data-ttu-id="26eb4-286">정책 이름</span><span class="sxs-lookup"><span data-stu-id="26eb4-286">Policy name</span></span>  |<span data-ttu-id="26eb4-287">순위</span><span class="sxs-lookup"><span data-stu-id="26eb4-287">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="26eb4-288">영업</span><span class="sxs-lookup"><span data-stu-id="26eb4-288">Sales</span></span>    |<span data-ttu-id="26eb4-289">판매 정책</span><span class="sxs-lookup"><span data-stu-id="26eb4-289">Sales policy</span></span>       | <span data-ttu-id="26eb4-290">1</span><span class="sxs-lookup"><span data-stu-id="26eb4-290">1</span></span>        |
|<span data-ttu-id="26eb4-291">Division</span><span class="sxs-lookup"><span data-stu-id="26eb4-291">Division</span></span>    |<span data-ttu-id="26eb4-292">부서 정책</span><span class="sxs-lookup"><span data-stu-id="26eb4-292">Division policy</span></span>         |<span data-ttu-id="26eb4-293">2</span><span class="sxs-lookup"><span data-stu-id="26eb4-293">2</span></span>         |
|<span data-ttu-id="26eb4-294">자회사</span><span class="sxs-lookup"><span data-stu-id="26eb4-294">Subsidiary</span></span>   |<span data-ttu-id="26eb4-295">자회사 정책</span><span class="sxs-lookup"><span data-stu-id="26eb4-295">Subsidiary policy</span></span>        |<span data-ttu-id="26eb4-296">3</span><span class="sxs-lookup"><span data-stu-id="26eb4-296">3</span></span>        |

<span data-ttu-id="26eb4-297">이 예제에서는 그룹에서 Teams 모임 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-297">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="26eb4-298">그룹에 대한 정책 할당 변경</span><span class="sxs-lookup"><span data-stu-id="26eb4-298">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="26eb4-299">[Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 곧 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-299">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="26eb4-300">그동안 그룹 정책 할당을 변경하려면 그룹에서 현재 정책 할당을 제거한 다음 새 정책 할당을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-300">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="26eb4-301">그룹에 정책을 할당한 후 [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 사용하여 다음과 같이 해당 그룹의 정책 할당을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-301">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="26eb4-302">순위 변경</span><span class="sxs-lookup"><span data-stu-id="26eb4-302">Change the ranking</span></span>
- <span data-ttu-id="26eb4-303">주어진 정책 유형의 정책 변경</span><span class="sxs-lookup"><span data-stu-id="26eb4-303">Change the policy of a given policy type</span></span>
- <span data-ttu-id="26eb4-304">주어진 정책 유형 및 순위의 정책 변경</span><span class="sxs-lookup"><span data-stu-id="26eb4-304">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="26eb4-305">이 예제에서는 그룹의 Teams 호출 공원 정책을 SupportCallPark라는 정책으로 변경하고 배정 순위를 3으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-305">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="26eb4-306">사용자에 대한 유효 정책 변경</span><span class="sxs-lookup"><span data-stu-id="26eb4-306">Change the effective policy for a user</span></span>

<span data-ttu-id="26eb4-307">정책이 직접 할당된 사용자에 대한 유효 정책을 변경하는 방법의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-307">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="26eb4-308">먼저 [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet을 매개 변수와 함께 사용하여 사용자와 연결된 Teams 모임 브로드캐스트 정책의 세부 정보를 ```PolicySource``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-308">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span> 

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="26eb4-309">출력은 사용자가 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트라는 정책보다 우선하는 직원 이벤트라는 Teams 모임 브로드캐스트 정책에 직접 할당된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-309">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="26eb4-310">이제 사용자에서 직원 이벤트 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-310">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="26eb4-311">즉, 사용자에게 더 이상 직접 할당된 Teams 모임 브로드캐스트 정책이 없고 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-311">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span> 

<span data-ttu-id="26eb4-312">비즈니스용 Skype PowerShell 모듈에서 다음 cmdlet을 사용하여 이 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-312">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="26eb4-313">Teams PowerShell 모듈에서 다음 cmdlet을 사용하여 사용자가 지정한 사용자 목록인 배치 정책 할당을 $users 대규모로 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-313">You can use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="26eb4-314">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-314">Assign a policy to a batch of users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="26eb4-315">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="26eb4-315">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="26eb4-316">사용자에게 정책을 일괄 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="26eb4-316">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="26eb4-317">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 사용자를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-317">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="26eb4-318">정책을 할당할 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-318">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="26eb4-319">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-319">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="26eb4-320">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-320">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="26eb4-321">**설정 편집** 을 클릭하고 원하는 대로 변경한 다음, **적용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-321">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>

<span data-ttu-id="26eb4-322">정책 할당의 상태를 보려면 [적용]을 클릭하여 정책 할당을 제출한  후 사용자 페이지 맨 위에 나타나는 배너에서 활동 **로그를 클릭합니다.** </span><span class="sxs-lookup"><span data-stu-id="26eb4-322">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you click **Apply** to submit your policy assignment, click **Activity log**.</span></span> <span data-ttu-id="26eb4-323">또는 Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 대시보드로 이동한 다음 활동 로그에서 **세부** 정보 **보기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-323">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, click **View details**.</span></span> <span data-ttu-id="26eb4-324">활동 로그에는 지난 30일 동안 Microsoft Teams 관리 센터를 통해 20명 이상의 사용자 배치에 대한 정책 할당이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-324">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="26eb4-325">자세한 내용은 활동 로그에서 정책 할당 [보기를 참조합니다.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="26eb4-325">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="26eb4-326">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="26eb4-326">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="26eb4-327">현재 PowerShell을 사용한 일괄 처리 정책 할당은 모든 Teams 정책 유형에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-327">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="26eb4-328">지원되는 정책 유형 목록은 [New-CsBatchPolicyAssignmentOperation을](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26eb4-328">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>
 
<span data-ttu-id="26eb4-329">일괄 처리 정책 할당을 사용하면 스크립트를 사용하지 않고도 한에 대규모 사용자 집합에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-329">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="26eb4-330">[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 할당하려는 사용자 및 정책의 일괄 처리를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-330">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="26eb4-331">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-331">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="26eb4-332">그런 다음 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 할당의 진행률 및 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-332">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="26eb4-333">해당 개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-333">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="26eb4-334">사용자의 SIP 주소는 UPN(사용자 계정 이름) 또는 전자 메일 주소와 같은 값을 자주 사용하지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-334">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="26eb4-335">사용자가 UPN 또는 전자 메일을 사용하여 지정했지만 해당 SIP 주소와 다른 값을 사용하는 경우 사용자에 대한 정책 할당이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-335">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="26eb4-336">일괄 처리에 중복된 사용자가 포함된 경우 처리 전에 중복된 사용자가 일괄 처리에서 제거되고, 상태는 일괄 처리에 남아 있는 고유 사용자에 대해만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-336">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="26eb4-337">배치에는 최대 5천 명의 사용자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-337">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="26eb4-338">최상의 결과를 위해 한에 몇 개 이상의 일괄 처리를 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-338">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="26eb4-339">더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-339">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="26eb4-340">Microsoft Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="26eb4-340">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="26eb4-341">다음을 실행하여 [Microsoft Teams PowerShell 모듈을 설치합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="26eb4-341">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="26eb4-342">버전 1.0.5 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-342">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="26eb4-343">다음을 실행하여 Teams에 연결하고 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-343">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="26eb4-344">메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-344">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="26eb4-345">Graph 모듈용 Azure AD PowerShell 설치 및 연결(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="26eb4-345">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="26eb4-346">또한 Azure [AD PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 모듈(아직 없는 경우)을 다운로드하여 설치하고 조직의 사용자 목록을 검색할 수 있도록 Azure AD에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-346">You may also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="26eb4-347">다음을 실행하여 Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-347">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="26eb4-348">메시지가 표시될 때 Teams에 연결하는 데 사용한 동일한 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-348">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="26eb4-349">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-349">Assign a policy to a batch of users</span></span>

<span data-ttu-id="26eb4-350">이 예제에서는 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 Users_ids.text 파일에 나열된 사용자 배치에 HR 앱 설정 정책이라는 앱 설정 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-350">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="26eb4-351">이 예제에서는 Azure AD에 연결하여 사용자 컬렉션을 검색한 다음, 해당 SIP 주소를 사용하여 지정된 사용자 배치에 New Hire Messaging Policy라는 메시징 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-351">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="26eb4-352">일괄 처리 할당의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="26eb4-352">Get the status of a batch assignment</span></span>

<span data-ttu-id="26eb4-353">다음을 실행하여 일괄 처리 할당의 상태를 얻습니다. 여기서 OperationId는 주어진 일괄 처리에 대한 cmdlet에서 반환되는 작업 ```New-CsBatchPolicyAssignmentOperation``` ID입니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-353">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="26eb4-354">출력에 오류가 발생한 것으로 표시되는 경우 다음을 실행하여 속성에 있는 오류에 대한 자세한 정보를 ```UserState``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-354">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="26eb4-355">자세한 내용은 [Get-CsBatchPolicyAssignmentOperation을 참조합니다.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="26eb4-355">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="26eb4-356">사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-356">Assign a policy package to users</span></span>

<span data-ttu-id="26eb4-357">Teams의 정책 패키지는 조직에서 동일하거나 유사한 역할이 있는 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-357">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="26eb4-358">각 정책 패키지는 사용자 역할을 중심으로 디자인된 것으로, 해당 역할에 대한 일반적인 활동을 지원하는 미리 정의된 정책 및 정책 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-358">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="26eb4-359">정책 패키지의 몇 가지 예로 Education(교사) 패키지 및 의료(의료 서비스) 패키지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-359">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="26eb4-360">자세한 내용은 Teams에서 정책 [패키지 관리를 참조합니다.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="26eb4-360">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="26eb4-361">한 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-361">Assign a policy package to one user</span></span>

1. <span data-ttu-id="26eb4-362">Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자** 로 이동한 후 해당 사용자를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-362">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="26eb4-363">사용자의 페이지에서 정책을 클릭한 다음 정책 패키지 옆에 있는 **편집을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-363">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="26eb4-364">정책 패키지 **할당 창에서** 할당할 패키지를 선택한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-364">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="26eb4-365">여러 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-365">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="26eb4-366">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 정책 패키지로 이동한 다음 패키지 이름 왼쪽을 클릭하여 할당하려는 정책 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-366">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="26eb4-367">사용자 **관리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-367">Click **Manage users**.</span></span>
3. <span data-ttu-id="26eb4-368">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 후 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-368">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="26eb4-369">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-369">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="26eb4-370">사용자 추가가 완료되면 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-370">When you're finished adding users, click **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="26eb4-371">그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-371">Assign a policy package to a group</span></span>

<span data-ttu-id="26eb4-372">**이 기능은 비공개 리미 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="26eb4-372">**This feature is in private preview**</span></span>

<span data-ttu-id="26eb4-373">그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-373">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="26eb4-374">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-374">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="26eb4-375">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-375">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="26eb4-376">그룹에 대한 정책 패키지 할당은 최대 50,000명 사용자 그룹에 권장되지만 더 큰 그룹에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-376">Policy package assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span> 

<span data-ttu-id="26eb4-377">정책 패키지를 할당하면 즉시 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-377">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="26eb4-378">그러나 그룹의 구성원에게 정책 할당을 전파하는 작업은 백그라운드 작업으로 수행하며 그룹의 크기에 따라 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-378">However, note that the propagation of the policy assignment to members of the group is performed as a background operation and may take some time, depending on the size of the group.</span></span> <span data-ttu-id="26eb4-379">그룹에서 정책의 부가가치가 없는 경우 또는 구성원이 그룹에 추가되거나 그룹에서 제거될 때도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-379">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26eb4-380">시작하기 전에 우선 순위 규칙 및 [](#precedence-rules) 그룹 할당 순위를 [이해하는 것이 중요합니다.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="26eb4-380">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="26eb4-381">이 문서의 앞부분에서 그룹에 정책 할당에 대해 알아야 할 [개념을](#what-you-need-to-know-about-policy-assignment-to-groups) 읽고 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-381">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="using-the-microsoft-teams-admin-center-coming-soon"></a><span data-ttu-id="26eb4-382">Microsoft Teams 관리 센터 사용(출시 예정)</span><span class="sxs-lookup"><span data-stu-id="26eb4-382">Using the Microsoft Teams admin center (coming soon)</span></span>

<span data-ttu-id="26eb4-383">Microsoft Teams 관리 센터의 그룹에 대한 정책 패키지 할당은 곧 제공될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-383">Policy package assignment to groups in the Microsoft Teams admin center is coming soon.</span></span> <span data-ttu-id="26eb4-384">최신 업데이트는 여기를 다시 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-384">Check back here for the latest updates.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="26eb4-385">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="26eb4-385">Using PowerShell</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="26eb4-386">Microsoft Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="26eb4-386">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="26eb4-387">단계별 지침은 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="26eb4-387">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="26eb4-388">사용자 그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-388">Assign a policy package to a group of users</span></span>

<span data-ttu-id="26eb4-389">[Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet을 사용하여 정책 패키지를 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-389">You use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="26eb4-390">개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-390">You can specify a group by using the object Id, SIP address, or email address.</span></span> <span data-ttu-id="26eb4-391">정책 패키지를 할당할 때 [](#group-assignment-ranking) 정책 패키지의 각 정책 유형에 대한 그룹 할당 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-391">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span> 

<span data-ttu-id="26eb4-392">이 예제에서는 TeamsAppSetupPolicy 및 TeamsMeetingBroadcastPolicy에 대한 할당 순위가 1인 그룹에 Education_Teacher 정책 패키지를 할당하고 TeamsMeetingPolicy에 대한 순위가 2인 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-392">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="26eb4-393">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-393">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="26eb4-394">일괄 처리 정책 패키지 할당을 사용하면 스크립트를 사용하지 않고도 한에서 대규모 사용자 집합에 정책 패키지를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-394">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="26eb4-395">[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 할당하려는 사용자 및 정책 패키지의 일괄 처리를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-395">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="26eb4-396">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-396">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="26eb4-397">그런 다음 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 할당의 진행률 및 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-397">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="26eb4-398">해당 개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-398">You can specify users by their object Id or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="26eb4-399">사용자의 SIP 주소는 UPN(사용자 계정 이름) 또는 전자 메일 주소와 같은 값을 자주 사용하지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-399">Note that a user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="26eb4-400">사용자가 UPN 또는 전자 메일을 사용하여 지정했지만 해당 SIP 주소와 다른 값을 사용하는 경우 사용자에 대한 정책 할당이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-400">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="26eb4-401">일괄 처리에 중복된 사용자가 포함된 경우 처리 전에 중복된 사용자가 일괄 처리에서 제거되고, 상태는 일괄 처리에 남아 있는 고유 사용자에 대해만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-401">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span> 

<span data-ttu-id="26eb4-402">배치에는 최대 5천 명의 사용자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-402">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="26eb4-403">최상의 결과를 위해 한에 몇 개 이상의 일괄 처리를 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-403">For best results, do not submit more than a few batches at a time.</span></span> <span data-ttu-id="26eb4-404">더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-404">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="26eb4-405">Microsoft Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="26eb4-405">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="26eb4-406">다음을 실행하여 [Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 모듈을 설치합니다(아직 설치하지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="26eb4-406">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="26eb4-407">버전 1.0.5 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-407">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="26eb4-408">다음을 실행하여 Teams에 연결하고 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-408">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="26eb4-409">메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-409">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="26eb4-410">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="26eb4-410">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="26eb4-411">이 예제에서는 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 Education_PrimaryStudent 정책 패키지를 사용자 일괄 처리에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-411">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="26eb4-412">일괄 처리 할당의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="26eb4-412">Get the status of a batch assignment</span></span>

<span data-ttu-id="26eb4-413">다음을 실행하여 일괄 처리 할당의 상태를 얻습니다. 여기서 OperationId는 주어진 일괄 처리에 대한 cmdlet에서 반환되는 작업 ```New-CsBatchPolicyAssignmentOperation``` ID입니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-413">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="26eb4-414">출력에 오류가 발생한 것으로 표시되는 경우 다음을 실행하여 속성에 있는 오류에 대한 자세한 정보를 ```UserState``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="26eb4-414">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="26eb4-415">자세한 내용은 [Get-CsBatchPolicyAssignmentOperation을 참조합니다.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="26eb4-415">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span> 

## <a name="related-topics"></a><span data-ttu-id="26eb4-416">관련 항목</span><span class="sxs-lookup"><span data-stu-id="26eb4-416">Related topics</span></span>

[<span data-ttu-id="26eb4-417">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="26eb4-417">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
