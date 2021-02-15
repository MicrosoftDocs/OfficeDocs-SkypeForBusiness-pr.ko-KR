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
ms.openlocfilehash: 3a788ff2712c065d0273d4dfb6233f03e2272337
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196297"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="785f7-103">Microsoft Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="785f7-104">관리자는 정책을 사용하여 조직의 사용자가 사용할 수 있는 Teams 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="785f7-105">예를 들어 몇 가지 이름을 지정하는 호출 정책, 모임 정책 및 메시징 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="785f7-106">조직에는 고유한 요구 사항을 충족하는 다양한 유형의 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="785f7-107">만들고 할당하는 사용자 지정 정책을 사용하면 이러한 요구에 따라 다양한 사용자 집합에 정책 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="785f7-108">조직에서 정책을 쉽게 관리하기 위해 Teams는 사용자에게 정책을 할당하는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="785f7-109">일괄 처리 할당을 통해 개별적으로 또는 대규모로 또는 사용자가 구성원인 그룹에 직접 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="785f7-110">정책 패키지를 사용하여 비슷한 역할이 있는 조직의 사용자에게 미리 설정한 정책 컬렉션을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="785f7-111">선택하는 옵션은 관리되는 정책의 수와 정책을 할당하는 사용자 수에 따라 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="785f7-112">전역(조직 전체 기본값) 정책은 조직에서 가장 많은 수의 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="785f7-113">특수한 정책이 필요한 사용자에게만 정책을 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="785f7-114">이 문서에서는 사용자에게 정책을 할당할 수 있는 다양한 방법 및 권장되는 시나리오를 사용하는 경우를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="785f7-115">어떤 정책이 우선하나요?</span><span class="sxs-lookup"><span data-stu-id="785f7-115">Which policy takes precedence?</span></span>

<span data-ttu-id="785f7-116">사용자에게는 각 정책 유형에 대한 하나의 유효 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="785f7-117">사용자에게 정책이 직접 할당되어 있으며 동일한 유형의 정책이 할당된 하나 이상의 그룹의 구성원일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="785f7-118">이러한 종류의 시나리오에서 어떤 정책이 우선할까요?</span><span class="sxs-lookup"><span data-stu-id="785f7-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="785f7-119">사용자의 유효 정책은 다음과 같이 우선 순위 규칙에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="785f7-120">사용자에게 정책이 직접 할당된 경우(개별적으로 또는 일괄 처리 할당을 통해) 해당 정책이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="785f7-121">다음 시각적 예제에서 사용자의 효과적인 정책은 사용자에게 직접 할당되는 Lincoln Square 모임 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![직접 할당된 정책이 어떻게 우선하는지 보여주는 다이어그램](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="785f7-123">사용자에게 지정된 유형의 정책이 직접 할당되지 않은 경우 사용자가 구성원인 그룹에 할당된 정책이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="785f7-124">사용자가 여러 그룹의 구성원인 경우 해당 정책 유형에 대해 그룹 할당 순위가 가장 높은 정책이 우선합니다. [](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="785f7-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="785f7-125">이 시각적 예제에서 사용자의 유효 정책은 Exec Teams 및 HD 정책으로, 사용자가 구성원인 다른 그룹에 비해 할당 순위가 가장 높고 동일한 정책 유형의 정책도 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![그룹에서 상속된 정책이 어떻게 우선하는지 보여주는 다이어그램](media/assign-policies-example-group.png)

<span data-ttu-id="785f7-127">사용자에게 정책이 직접 할당되지 않은 경우 또는 정책이 할당된 그룹의 구성원이 아닌 경우 사용자는 해당 정책 유형에 대한 전역(Org 전체 기본값) 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="785f7-128">다음은 시각적 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-128">Here's a visual example.</span></span>

![전역 정책이 어떻게 우선하는지 보여주는 다이어그램](media/assign-policies-example-global.png)

<span data-ttu-id="785f7-130">자세한 내용은 우선 순위 규칙을 [참조합니다.](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="785f7-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="785f7-131">정책을 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="785f7-131">Ways to assign policies</span></span>

<span data-ttu-id="785f7-132">다음은 사용자에게 정책을 할당할 수 있는 방법과 각각에 대한 권장 시나리오에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="785f7-133">자세한 내용은 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-133">Select the links to learn more.</span></span>

<span data-ttu-id="785f7-134">개별 사용자 또는 그룹에 정책을 할당하기 전에 먼저 조직에서 가장 많은 수의 사용자에게 적용될 수 있도록 전역(조직 전체 [기본값)](#set-the-global-policies) 정책을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="785f7-135">전역 정책이 설정되고 나면 특수한 정책이 필요한 사용자에게만 정책을 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="785f7-136">방법</span><span class="sxs-lookup"><span data-stu-id="785f7-136">Do this</span></span>  |<span data-ttu-id="785f7-137">If...</span><span class="sxs-lookup"><span data-stu-id="785f7-137">If...</span></span>  | <span data-ttu-id="785f7-138">사용 중...</span><span class="sxs-lookup"><span data-stu-id="785f7-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="785f7-139">개별 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="785f7-140">Teams를 시작하거나 소수의 사용자에게 정책 하나 또는 몇 개만 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="785f7-141">비즈니스용 Skype Online PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="785f7-141">The Microsoft Teams admin center or PowerShell cmdlets in the Skype for Business Online PowerShell module</span></span>
|[<span data-ttu-id="785f7-142">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="785f7-143">사용자의 그룹 멤버 자격에 따라 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="785f7-144">예를 들어 보안 그룹 또는 메일 그룹의 모든 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="785f7-145">Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="785f7-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="785f7-146">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="785f7-147">대규모 사용자 집합에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="785f7-148">예를 들어 조직에서 수백 또는 수천 명의 사용자에게 한 번만에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="785f7-149">Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="785f7-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="785f7-150">사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="785f7-151">동일하거나 유사한 역할이 있는 조직의 특정 사용자 집합에 여러 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="785f7-152">예를 들어 학교의 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="785f7-153">보조 학생에게 교육(중등 학생) 정책 패키지를 할당하여 개인 통화와 같은 특정 기능을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="785f7-154">Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="785f7-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="785f7-155">[그룹에 정책 패키지 할당(비공개](#assign-a-policy-package-to-a-group) 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="785f7-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="785f7-156">동일하거나 유사한 역할이 있는 조직의 사용자 그룹에 여러 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="785f7-157">예를 들어 보안 그룹 또는 메일 그룹의 모든 사용자에게 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="785f7-158">Teams PowerShell 모듈의 Microsoft Teams 관리 센터(출시 예정) 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="785f7-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="785f7-159">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="785f7-160">동일하거나 유사한 역할이 있는 조직의 사용자 일괄 처리에 여러 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="785f7-161">예를 들어 일괄 처리 할당을 사용하여 학교의 모든 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="785f7-162">개인 통화와 같은 특정 기능을 제한하기 위해 보조 학생 일괄 처리에 교육(중등 학생) 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="785f7-163">Teams PowerShell 모듈의 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="785f7-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="785f7-164">전역 정책 설정</span><span class="sxs-lookup"><span data-stu-id="785f7-164">Set the global policies</span></span>

<span data-ttu-id="785f7-165">다음 단계에 따라 각 정책 유형에 대한 전역(전체 기본) 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="785f7-166">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="785f7-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="785f7-167">Microsoft Teams 관리 센터의 왼쪽 탐색에서 업데이트하려는 정책 유형에 대한 정책 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="785f7-168">예를 들어 **Teams** Teams  >  **정책,** **모임** 모임 정책, 메시징 정책 또는 음성 통화  >      >  **정책이 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="785f7-169">**전역(전체 기본값)** 정책을 선택하여 현재 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="785f7-170">필요한 경우 정책을 업데이트한 다음 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="785f7-171">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="785f7-171">Using PowerShell</span></span>

<span data-ttu-id="785f7-172">PowerShell을 사용하여 전역 정책을 설정하기 위해 전역 식별자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="785f7-173">먼저 현재 전역 정책을 검토하여 변경할 설정을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="785f7-174">다음으로, 필요한 경우 전역 정책을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="785f7-175">변경하려는 설정의 값만 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="785f7-176">개별 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-176">Assign a policy to individual users</span></span>

<span data-ttu-id="785f7-177">다음 단계에 따라 개별 사용자 또는 한에 소수의 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="785f7-178">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="785f7-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="785f7-179">사용자에게 정책을 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="785f7-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="785f7-180">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **사용자로** 이동한 다음 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="785f7-181">사용자 이름 왼쪽을 클릭하여 사용자를 선택한 다음 설정 **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="785f7-182">할당할 정책을 선택한 다음 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="785f7-183">또는 다음을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="785f7-184">Microsoft Teams 관리 센터의 왼쪽 탐색에서 정책 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="785f7-185">정책 이름 왼쪽을 클릭하여 할당할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="785f7-186">**사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="785f7-187">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="785f7-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="785f7-188">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="785f7-189">사용자 추가를 마쳤을 때 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="785f7-190">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="785f7-190">Use PowerShell</span></span>

<span data-ttu-id="785f7-191">각 정책 유형에는 관리하기 위한 자체 cmdlet 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="785f7-192">특정 정책 유형에 ```Grant-``` cmdlet을 사용하여 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="785f7-193">예를 들어 ```Grant-CsTeamsMeetingPolicy``` cmdlet을 사용하여 사용자에게 Teams 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="785f7-194">이러한 cmdlet은 비즈니스용 Skype Online PowerShell 모듈에 포함되어 있으며 비즈니스용 [Skype cmdlet 참조에 설명되어 있습니다.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="785f7-194">These cmdlets are included in the Skype for Business Online PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="785f7-195">비즈니스용 [Skype Online PowerShell](https://www.microsoft.com/download/details.aspx?id=39366) 모듈을 다운로드하여 설치한 다음(아직 설치하지 않은 경우) 다음을 실행하여 비즈니스용 Skype Online에 연결하고 세션을 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="785f7-195">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366) (if you haven't already), and then run the following to connect to Skype for Business Online and start a session.</span></span>

> [!NOTE]
> <span data-ttu-id="785f7-196">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="785f7-197">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

<span data-ttu-id="785f7-198">이 예제에서는 Reda라는 사용자에게 학생 모임 정책이라는 Teams 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="785f7-199">자세한 내용은 [PowerShell을 통해 정책 관리를 읽어보아야 합니다.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="785f7-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="785f7-200">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-200">Assign a policy to a group</span></span>

<span data-ttu-id="785f7-201">그룹에 정책 할당을 사용하면 보안 그룹 또는 메일 그룹과 같은 사용자 그룹에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="785f7-202">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="785f7-203">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="785f7-204">그룹에 대한 정책 할당은 최대 50,000명 사용자 그룹에 권장되지만 더 큰 그룹에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="785f7-205">정책을 할당하면 해당 정책이 그룹에 즉시 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="785f7-206">그러나 그룹의 구성원에게 정책 할당을 전파하는 작업은 백그라운드 작업으로 수행하며 그룹의 크기에 따라 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="785f7-207">그룹에서 정책이 재할당되지 않은 경우 또는 구성원이 그룹에 추가되거나 그룹에서 제거될 때도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="785f7-208">그룹 정책 할당은 그룹의 직접 구성원인 사용자에게만 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="785f7-209">할당은 중첩된 그룹의 멤버에게 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="785f7-210">그룹에 정책 할당에 대해 알아야 할 정보</span><span class="sxs-lookup"><span data-stu-id="785f7-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="785f7-211">시작하기 전에 우선 순위 규칙 및 그룹 할당 순위를 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="785f7-212">우선 순위 규칙</span><span class="sxs-lookup"><span data-stu-id="785f7-212">Precedence rules</span></span>

<span data-ttu-id="785f7-213">주어진 정책 유형에 대해 사용자의 유효 정책은 다음에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="785f7-214">사용자에게 직접 할당된 정책이 그룹에 할당된 동일한 유형의 다른 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="785f7-215">즉, 사용자에게 지정된 형식의 정책이 직접 할당된 경우 해당 사용자는 그룹에서 동일한 형식의 정책을 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="785f7-216">즉, 사용자에게 직접 할당된 지정된 형식의 정책이 있는 경우 그룹에서 동일한 형식의 정책을 상속하려면 먼저 사용자로부터 해당 정책을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="785f7-217">사용자에게 직접 할당된 정책이 없고 둘 이상의 그룹의 구성원이고 각 그룹에 할당된 동일한 유형의 정책이 있는 경우 사용자는 가장 높은 순위를 가지는 그룹 할당의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="785f7-218">사용자가 정책이 할당된 그룹의 구성원이 아닌 경우 해당 정책 유형에 대한 전역(전체 기본값) 정책이 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="785f7-219">사용자의 유효 정책은 다음 규칙에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="785f7-220">사용자가 정책이 할당된 그룹에 추가되거나 제거되는 경우</span><span class="sxs-lookup"><span data-stu-id="785f7-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="785f7-221">그룹에서 정책이 재할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="785f7-222">사용자에게 직접 할당된 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="785f7-223">그룹 할당 순위</span><span class="sxs-lookup"><span data-stu-id="785f7-223">Group assignment ranking</span></span>

<span data-ttu-id="785f7-224">그룹에 정책을 할당할 때 그룹 할당에 대한 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="785f7-225">이 정책은 사용자가 둘 이상의 그룹의 구성원이고 각 그룹에 동일한 유형의 정책이 할당된 경우 사용자가 유효 정책으로 상속해야 하는 정책을 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="785f7-226">그룹 할당 순위는 동일한 유형의 다른 그룹 할당에 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="785f7-227">예를 들어 호출 정책을 두 그룹에 할당하는 경우 한 할당의 순위를 1로 설정하고 다른 할당은 2로 설정하고 1은 가장 높은 순위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="785f7-228">그룹 할당 순위는 상속과 관련하여 다른 그룹 멤버 자격보다 더 중요하거나 관련성이 높은 그룹 멤버 자격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="785f7-229">예를 들어 두 개의 그룹인 Store Employees와 Store Manager가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="785f7-230">두 그룹에는 Teams 통화 정책, 스토어 직원 통화 정책 및 스토어 관리자 통화 정책이 각각 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="785f7-231">두 그룹에 모두 있는 스토어 관리자의 경우 관리자 역할은 직원 역할보다 관련성이 높기 때문에 스토어 관리자 그룹에 할당된 호출 정책의 순위가 더 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="785f7-232">그룹</span><span class="sxs-lookup"><span data-stu-id="785f7-232">Group</span></span> |<span data-ttu-id="785f7-233">정책 이름을 호출하는 팀</span><span class="sxs-lookup"><span data-stu-id="785f7-233">Teams calling policy name</span></span>  |<span data-ttu-id="785f7-234">순위</span><span class="sxs-lookup"><span data-stu-id="785f7-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="785f7-235">스토어 관리자</span><span class="sxs-lookup"><span data-stu-id="785f7-235">Store Managers</span></span>   |<span data-ttu-id="785f7-236">스토어 관리자 호출 정책</span><span class="sxs-lookup"><span data-stu-id="785f7-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="785f7-237">1</span><span class="sxs-lookup"><span data-stu-id="785f7-237">1</span></span>|
|<span data-ttu-id="785f7-238">직원 저장</span><span class="sxs-lookup"><span data-stu-id="785f7-238">Store Employees</span></span>    |<span data-ttu-id="785f7-239">직원 호출 정책 저장</span><span class="sxs-lookup"><span data-stu-id="785f7-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="785f7-240">2</span><span class="sxs-lookup"><span data-stu-id="785f7-240">2</span></span>|

<span data-ttu-id="785f7-241">순위를 지정하지 않으면 정책 할당에 가장 낮은 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="785f7-242">Teams 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="785f7-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="785f7-243">현재 Microsoft Teams 관리 센터를 사용하는 그룹에 대한 정책 할당은 Teams 통화 정책, Teams 호출 공원 정책, Teams 정책, Teams 라이브 이벤트 정책, Teams 모임 정책 및 Teams 메시징 정책에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="785f7-244">다른 정책 형식의 경우 PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="785f7-245">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 정책 유형 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="785f7-246">예를 들어 모임 모임  >  **정책으로 이동**</span><span class="sxs-lookup"><span data-stu-id="785f7-246">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="785f7-247">그룹 **정책 할당 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-247">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="785f7-248">그룹 **추가를 선택하고** 그룹 창에 정책 할당 **창에서** 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="785f7-249">정책을 할당할 그룹을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="785f7-250">그룹 할당의 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="785f7-251">할당하려는 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="785f7-252">적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-252">Select **Apply**.</span></span>

<span data-ttu-id="785f7-253">그룹 정책 할당을 제거하려면  정책 페이지의 그룹 정책 할당 탭에서 그룹 할당을 선택한 다음 제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="785f7-254">그룹 할당의 순위를 변경하려면 먼저 그룹 정책 할당을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="785f7-255">그런 다음 위의 단계에 따라 그룹에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="785f7-256">PowerShell 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="785f7-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="785f7-257">현재 PowerShell을 사용하는 그룹에 대한 정책 할당은 모든 Teams 정책 유형에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="785f7-258">지원되는 정책 유형 목록은 [New-CsGroupPolicyAssignment를](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="785f7-258">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="785f7-259">Microsoft Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="785f7-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="785f7-260">단계별 지침은 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="785f7-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="785f7-261">사용자 그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="785f7-262">[New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-262">Use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="785f7-263">개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="785f7-264">이 예제에서는 할당 순위가 1인 그룹에 Retail Managers 모임 정책이라는 Teams 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="785f7-265">그룹에 대한 정책 할당을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-265">Get policy assignments for a group</span></span>

<span data-ttu-id="785f7-266">[Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 할당된 모든 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-266">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="785f7-267">정책을 할당하는 데 SIP 주소 또는 전자 메일 주소가 사용된 경우에도 그룹은 항상 그룹 ID로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="785f7-268">이 예제에서는 특정 그룹에 할당된 모든 정책을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="785f7-269">이 예제에서는 Teams 모임 정책이 할당된 모든 그룹을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="785f7-270">그룹에서 정책 제거</span><span class="sxs-lookup"><span data-stu-id="785f7-270">Remove a policy from a group</span></span>

<span data-ttu-id="785f7-271">[Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet을 사용하여 그룹에서 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-271">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="785f7-272">그룹에서 정책을 제거하면 해당 그룹에 할당된 동일한 유형의 다른 정책의 우선 순위가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="785f7-273">예를 들어 순위가 2인 정책을 제거하면 순위가 3과 4인 정책이 새 순위를 반영하여 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="785f7-274">다음 두 표에서는 이 예제를 보여 주겠습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-274">The following two tables show this example.</span></span>

<span data-ttu-id="785f7-275">다음은 Teams 모임 정책에 대한 정책 할당 및 우선 순위 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="785f7-276">그룹 이름</span><span class="sxs-lookup"><span data-stu-id="785f7-276">Group name</span></span>  |<span data-ttu-id="785f7-277">정책 이름</span><span class="sxs-lookup"><span data-stu-id="785f7-277">Policy name</span></span>  |<span data-ttu-id="785f7-278">순위</span><span class="sxs-lookup"><span data-stu-id="785f7-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="785f7-279">영업</span><span class="sxs-lookup"><span data-stu-id="785f7-279">Sales</span></span>    |<span data-ttu-id="785f7-280">판매 정책</span><span class="sxs-lookup"><span data-stu-id="785f7-280">Sales policy</span></span>       | <span data-ttu-id="785f7-281">1</span><span class="sxs-lookup"><span data-stu-id="785f7-281">1</span></span>        |
|<span data-ttu-id="785f7-282">서부 지역</span><span class="sxs-lookup"><span data-stu-id="785f7-282">West Region</span></span>     |<span data-ttu-id="785f7-283">서부 지역 정책</span><span class="sxs-lookup"><span data-stu-id="785f7-283">West Region policy</span></span>         |<span data-ttu-id="785f7-284">2</span><span class="sxs-lookup"><span data-stu-id="785f7-284">2</span></span>         |
|<span data-ttu-id="785f7-285">Division</span><span class="sxs-lookup"><span data-stu-id="785f7-285">Division</span></span>    |<span data-ttu-id="785f7-286">부서 정책</span><span class="sxs-lookup"><span data-stu-id="785f7-286">Division policy</span></span>         |<span data-ttu-id="785f7-287">3</span><span class="sxs-lookup"><span data-stu-id="785f7-287">3</span></span>         |
|<span data-ttu-id="785f7-288">자회사</span><span class="sxs-lookup"><span data-stu-id="785f7-288">Subsidiary</span></span>   |<span data-ttu-id="785f7-289">자회사 정책</span><span class="sxs-lookup"><span data-stu-id="785f7-289">Subsidiary policy</span></span>        |<span data-ttu-id="785f7-290">4</span><span class="sxs-lookup"><span data-stu-id="785f7-290">4</span></span>         |

<span data-ttu-id="785f7-291">서부 지역 그룹에서 서부 지역 정책을 제거하면 정책 할당 및 우선 순위가 다음과 같이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="785f7-292">그룹 이름</span><span class="sxs-lookup"><span data-stu-id="785f7-292">Group name</span></span>  |<span data-ttu-id="785f7-293">정책 이름</span><span class="sxs-lookup"><span data-stu-id="785f7-293">Policy name</span></span>  |<span data-ttu-id="785f7-294">순위</span><span class="sxs-lookup"><span data-stu-id="785f7-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="785f7-295">영업</span><span class="sxs-lookup"><span data-stu-id="785f7-295">Sales</span></span>    |<span data-ttu-id="785f7-296">판매 정책</span><span class="sxs-lookup"><span data-stu-id="785f7-296">Sales policy</span></span>       | <span data-ttu-id="785f7-297">1</span><span class="sxs-lookup"><span data-stu-id="785f7-297">1</span></span>        |
|<span data-ttu-id="785f7-298">Division</span><span class="sxs-lookup"><span data-stu-id="785f7-298">Division</span></span>    |<span data-ttu-id="785f7-299">부서 정책</span><span class="sxs-lookup"><span data-stu-id="785f7-299">Division policy</span></span>         |<span data-ttu-id="785f7-300">2</span><span class="sxs-lookup"><span data-stu-id="785f7-300">2</span></span>         |
|<span data-ttu-id="785f7-301">자회사</span><span class="sxs-lookup"><span data-stu-id="785f7-301">Subsidiary</span></span>   |<span data-ttu-id="785f7-302">자회사 정책</span><span class="sxs-lookup"><span data-stu-id="785f7-302">Subsidiary policy</span></span>        |<span data-ttu-id="785f7-303">3</span><span class="sxs-lookup"><span data-stu-id="785f7-303">3</span></span>        |

<span data-ttu-id="785f7-304">이 예제에서는 그룹에서 Teams 모임 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="785f7-305">그룹에 대한 정책 할당 변경</span><span class="sxs-lookup"><span data-stu-id="785f7-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="785f7-306">[Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 곧 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-306">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="785f7-307">그동안 그룹 정책 할당을 변경하려면 그룹에서 현재 정책 할당을 제거한 다음 새 정책 할당을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="785f7-308">그룹에 정책을 할당한 후 [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 사용하여 다음과 같이 해당 그룹의 정책 할당을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="785f7-309">순위 변경</span><span class="sxs-lookup"><span data-stu-id="785f7-309">Change the ranking</span></span>
- <span data-ttu-id="785f7-310">주어진 정책 유형의 정책 변경</span><span class="sxs-lookup"><span data-stu-id="785f7-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="785f7-311">주어진 정책 유형 및 순위의 정책 변경</span><span class="sxs-lookup"><span data-stu-id="785f7-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="785f7-312">이 예제에서는 그룹의 Teams 호출 공원 정책을 SupportCallPark라는 정책으로 변경하고 배정 순위를 3으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="785f7-313">사용자에 대한 유효 정책 변경</span><span class="sxs-lookup"><span data-stu-id="785f7-313">Change the effective policy for a user</span></span>

<span data-ttu-id="785f7-314">정책이 직접 할당된 사용자에 대한 유효 정책을 변경하는 방법의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="785f7-315">먼저 [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet을 매개 변수와 함께 사용하여 사용자와 연결된 Teams 모임 브로드캐스트 정책의 세부 정보를 ```PolicySource``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-315">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="785f7-316">출력은 사용자가 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트라는 정책보다 우선하는 직원 이벤트라는 Teams 모임 브로드캐스트 정책에 직접 할당된 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="785f7-317">이제 사용자에서 직원 이벤트 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="785f7-318">즉, 사용자에게 더 이상 직접 할당된 Teams 모임 브로드캐스트 정책이 없고 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="785f7-319">비즈니스용 Skype PowerShell 모듈에서 다음 cmdlet을 사용하여 이 작업을 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="785f7-320">Teams PowerShell 모듈에서 다음 cmdlet을 사용하여 사용자가 지정한 사용자 목록인 $users 정책 할당을 통해 대규모로 이 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="785f7-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="785f7-321">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="785f7-322">관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="785f7-322">Use the admin center</span></span>

<span data-ttu-id="785f7-323">사용자에게 정책을 일괄 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="785f7-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="785f7-324">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 사용자를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="785f7-325">정책을 할당하려는 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="785f7-326">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="785f7-327">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="785f7-328">설정 **편집을 선택하고** 원하는 내용을 변경한 다음 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="785f7-329">정책 할당의 상태를 확인하려면 [적용]을 선택하여 정책  할당을 제출한  후 사용자 페이지 맨 위에 나타나는 배너에서 활동 **로그를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="785f7-330">또는 Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 대시보드로 이동한 다음 **활동** 로그에서 **세부** 정보 **보기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="785f7-331">활동 로그에는 지난 30일 동안 Microsoft Teams 관리 센터를 통해 20명 이상의 사용자 배치에 대한 정책 할당이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="785f7-332">자세한 내용은 활동 로그에서 정책 할당 [보기를 참조합니다.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="785f7-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="785f7-333">PowerShell 메서드 사용</span><span class="sxs-lookup"><span data-stu-id="785f7-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="785f7-334">현재 PowerShell을 사용한 일괄 처리 정책 할당은 모든 Teams 정책 유형에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="785f7-335">지원되는 정책 유형 목록은 [New-CsBatchPolicyAssignmentOperation을](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="785f7-335">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="785f7-336">일괄 처리 정책 할당을 사용하면 스크립트를 사용하지 않고도 한에 대규모 사용자 집합에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="785f7-337">[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 할당하려는 사용자 및 정책의 일괄 처리를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-337">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="785f7-338">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="785f7-339">그런 다음 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 할당의 진행률 및 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="785f7-340">개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="785f7-341">사용자의 SIP 주소는 UPN(사용자 계정 이름) 또는 전자 메일 주소와 같은 값을 자주 사용하지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="785f7-342">사용자가 UPN 또는 전자 메일을 사용하여 지정했지만 해당 SIP 주소와 다른 값을 사용하는 경우 사용자에 대한 정책 할당이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="785f7-343">일괄 처리에 중복된 사용자가 포함된 경우 처리 전에 중복된 사용자가 일괄 처리에서 제거되고, 상태는 일괄 처리에 남아 있는 고유 사용자에 대해만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="785f7-344">배치에는 최대 5천 명의 사용자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="785f7-345">최상의 결과를 위해 한에 몇 개 이상의 일괄 처리를 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="785f7-346">더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="785f7-347">Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="785f7-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="785f7-348">다음을 실행하여 [Microsoft Teams PowerShell 모듈을 설치합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="785f7-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="785f7-349">버전 1.0.5 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="785f7-350">다음을 실행하여 Teams에 연결하고 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="785f7-351">메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="785f7-352">Graph 모듈용 Azure AD PowerShell 설치 및 연결(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="785f7-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="785f7-353">또한 Azure [AD PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 모듈(아직 없는 경우)을 다운로드하여 설치하고 조직의 사용자 목록을 검색할 수 있도록 Azure AD에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-353">You might also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="785f7-354">다음을 실행하여 Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="785f7-355">메시지가 표시될 때 Teams에 연결하는 데 사용한 동일한 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="785f7-356">사용자 일괄 처리에 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="785f7-357">이 예제에서는 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 Users_ids.text 파일에 나열된 사용자 배치에 HR 앱 설정 정책이라는 앱 설정 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="785f7-358">이 예제에서는 Azure AD에 연결하여 사용자 컬렉션을 검색한 다음, 해당 SIP 주소를 사용하여 지정된 사용자 배치에 New Hire Messaging Policy라는 메시징 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="785f7-359">일괄 처리 할당의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="785f7-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="785f7-360">다음을 실행하여 일괄 처리 할당의 상태를 얻습니다. 여기서 OperationId는 주어진 일괄 처리에 대한 cmdlet에서 반환되는 작업 ```New-CsBatchPolicyAssignmentOperation``` ID입니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="785f7-361">출력에 오류가 발생한 것으로 표시되는 경우 다음을 실행하여 속성에 있는 오류에 대한 자세한 정보를 ```UserState``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="785f7-362">자세한 내용은 [Get-CsBatchPolicyAssignmentOperation을 참조합니다.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="785f7-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="785f7-363">사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-363">Assign a policy package to users</span></span>

<span data-ttu-id="785f7-364">Teams의 정책 패키지는 조직에서 동일하거나 유사한 역할이 있는 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="785f7-365">각 정책 패키지는 사용자 역할을 중심으로 디자인된 것으로, 해당 역할에 대한 일반적인 활동을 지원하는 미리 정의된 정책 및 정책 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="785f7-366">정책 패키지의 몇 가지 예로 Education(교사) 패키지 및 의료(의료 서비스) 패키지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="785f7-367">자세한 내용은 Teams에서 정책 [패키지 관리를 참조합니다.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="785f7-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="785f7-368">한 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="785f7-369">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **사용자로** 이동한 다음 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="785f7-370">사용자의 페이지에서 정책을 선택한 다음 **정책** 패키지 옆에 있는 **편집을** **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="785f7-371">정책 패키지 **할당 창에서** 할당할 패키지를 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="785f7-372">여러 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="785f7-373">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 정책 패키지로 이동한 다음 패키지 이름 왼쪽을 클릭하여 할당하려는 정책 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="785f7-374">**사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-374">Select **Manage users**.</span></span>
3. <span data-ttu-id="785f7-375">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="785f7-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="785f7-376">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-376">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="785f7-377">사용자 추가를 마쳤을 때 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="785f7-378">그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-378">Assign a policy package to a group</span></span>

<span data-ttu-id="785f7-379">**이 기능은 비공개 리미 보기에 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-379">**This feature is in private preview**</span></span>

<span data-ttu-id="785f7-380">그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-380">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="785f7-381">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-381">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="785f7-382">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-382">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="785f7-383">그룹에 대한 정책 패키지 할당은 최대 50,000명 사용자 그룹에 권장되지만 더 큰 그룹에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-383">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="785f7-384">정책 패키지를 할당하면 즉시 그룹에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-384">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="785f7-385">그러나 그룹의 구성원에게 정책 할당을 전파하는 작업은 백그라운드 작업으로 수행하며 그룹의 크기에 따라 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-385">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="785f7-386">그룹에서 정책이 재할당되지 않은 경우 또는 구성원이 그룹에 추가되거나 그룹에서 제거될 때도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-386">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="785f7-387">시작하기 전에 우선 순위 규칙 및 [](#precedence-rules) 그룹 할당 순위를 [이해하는 것이 중요합니다.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="785f7-387">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="785f7-388">이 문서의 앞부분에서 그룹에 정책 할당에 대해 알아야 할 [개념을](#what-you-need-to-know-about-policy-assignment-to-groups) 읽고 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-388">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="785f7-389">관리 센터에서 사용자 그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-389">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="785f7-390">Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-390">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="785f7-391">왼쪽 탐색에서 정책 패키지 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-391">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="785f7-392">그룹 정책 할당 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-392">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="785f7-393">그룹 **추가를 선택하고** 그룹 창에 정책 패키지 할당에서 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-393">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="785f7-394">a.</span><span class="sxs-lookup"><span data-stu-id="785f7-394">a.</span></span> <span data-ttu-id="785f7-395">정책 패키지를 할당하려는 그룹을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-395">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="785f7-396">b.</span><span class="sxs-lookup"><span data-stu-id="785f7-396">b.</span></span> <span data-ttu-id="785f7-397">정책 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-397">Select a policy package.</span></span>

    <span data-ttu-id="785f7-398">c.</span><span class="sxs-lookup"><span data-stu-id="785f7-398">c.</span></span> <span data-ttu-id="785f7-399">각 정책 유형에 대한 순위를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-399">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="785f7-400">d.</span><span class="sxs-lookup"><span data-stu-id="785f7-400">d.</span></span> <span data-ttu-id="785f7-401">적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="785f7-401">Select **Apply**.</span></span>

    ![그룹 정책 할당 표시](media/group-pkg-assignment.png)

5. <span data-ttu-id="785f7-403">특정 정책 유형에 대한 순위를 관리하기 위해 특정 정책 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-403">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="785f7-404">정책 패키지를 그룹에 다시 할당하려면 먼저 그룹 정책 할당을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-404">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="785f7-405">그런 다음 위의 단계에 따라 정책 패키지를 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-405">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="785f7-406">PowerShell 작업</span><span class="sxs-lookup"><span data-stu-id="785f7-406">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="785f7-407">Teams PowerShell 모듈을 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-407">Get the Teams PowerShell module</span></span>

<span data-ttu-id="785f7-408">단계별 지침은 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="785f7-408">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="785f7-409">사용자 그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-409">Assign a policy package to a group of users</span></span>

<span data-ttu-id="785f7-410">[Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet을 사용하여 정책 패키지를 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-410">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="785f7-411">개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-411">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="785f7-412">정책 패키지를 할당할 때 [](#group-assignment-ranking) 정책 패키지의 각 정책 유형에 대한 그룹 할당 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-412">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="785f7-413">이 예제에서는 TeamsAppSetupPolicy 및 TeamsMeetingBroadcastPolicy에 대한 할당 순위가 1인 그룹에 Education_Teacher 정책 패키지를 할당하고 TeamsMeetingPolicy에 대한 순위가 2인 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-413">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="785f7-414">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-414">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="785f7-415">일괄 처리 정책 패키지 할당을 사용하면 스크립트를 사용하지 않고도 한에서 대규모 사용자 집합에 정책 패키지를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-415">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="785f7-416">[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 할당하려는 사용자 및 정책 패키지의 일괄 처리를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-416">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="785f7-417">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-417">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="785f7-418">그런 다음 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 할당의 진행률 및 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-418">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="785f7-419">개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-419">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="785f7-420">사용자의 SIP 주소는 UPN(사용자 계정 이름) 또는 전자 메일 주소와 같은 값을 자주 사용하지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-420">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="785f7-421">사용자가 UPN 또는 전자 메일을 사용하여 지정했지만 해당 SIP 주소와 다른 값을 사용하는 경우 사용자에 대한 정책 할당이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-421">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="785f7-422">일괄 처리에 중복된 사용자가 포함된 경우 처리 전에 중복된 사용자가 일괄 처리에서 제거되고, 상태는 일괄 처리에 남아 있는 고유 사용자에 대해만 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-422">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="785f7-423">일괄 처리에는 최대 5,000명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-423">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="785f7-424">최상의 결과를 위해 한에 몇 개 이상의 일괄 처리를 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-424">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="785f7-425">더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-425">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="785f7-426">Teams PowerShell 모듈 사용</span><span class="sxs-lookup"><span data-stu-id="785f7-426">Use the Teams PowerShell module</span></span>

<span data-ttu-id="785f7-427">다음을 실행하여 [Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 모듈을 설치합니다(아직 설치하지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="785f7-427">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="785f7-428">버전 1.0.5 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-428">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="785f7-429">다음을 실행하여 Teams에 연결하고 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-429">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="785f7-430">메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-430">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="785f7-431">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="785f7-431">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="785f7-432">이 예제에서는 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 Education_PrimaryStudent 정책 패키지를 사용자 일괄 처리에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-432">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="785f7-433">일괄 처리 할당의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="785f7-433">See the status of a batch assignment</span></span>

<span data-ttu-id="785f7-434">다음을 실행하여 일괄 처리 할당의 상태를 얻습니다. 여기서 OperationId는 주어진 일괄 처리에 대한 cmdlet에서 반환되는 작업 ```New-CsBatchPolicyAssignmentOperation``` ID입니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-434">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="785f7-435">출력에 오류가 발생한 것으로 표시되는 경우 다음을 실행하여 속성에 있는 오류에 대한 자세한 정보를 ```UserState``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="785f7-435">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="785f7-436">자세한 내용은 [Get-CsBatchPolicyAssignmentOperation을 참조합니다.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="785f7-436">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="785f7-437">관련 주제</span><span class="sxs-lookup"><span data-stu-id="785f7-437">Related topics</span></span>

[<span data-ttu-id="785f7-438">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="785f7-438">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
