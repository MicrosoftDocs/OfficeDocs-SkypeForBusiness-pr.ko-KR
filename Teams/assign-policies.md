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
description: Microsoft Teams의 사용자에게 정책을 할당하는 다양한 방법을 알아보습니다.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 50d0ddf3da73addde36cb045a3d61eb9a5618e8c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50568994"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a><span data-ttu-id="6afcc-103">Microsoft Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-103">Assign policies to your users in Microsoft Teams</span></span>

<span data-ttu-id="6afcc-104">관리자는 정책을 사용하여 조직의 사용자가 사용할 수 있는 Teams 기능을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-104">As an admin, you use policies to control the Teams features that are available to users in your organization.</span></span> <span data-ttu-id="6afcc-105">예를 들어 몇 가지 이름을 지정하는 호출 정책, 모임 정책 및 메시징 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-105">For example, there are calling policies, meeting policies, and messaging policies, to name just a few.</span></span>

<span data-ttu-id="6afcc-106">조직에는 고유한 요구 사항을 가지는 다양한 유형의 사용자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-106">Organizations have different types of users with unique needs.</span></span> <span data-ttu-id="6afcc-107">만들고 할당하는 사용자 지정 정책을 사용하면 이러한 요구에 따라 다양한 사용자 집합에 정책 설정을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-107">Custom policies that you create and assign let you tailor policy settings to different sets of users based on those needs.</span></span>

<span data-ttu-id="6afcc-108">조직의 정책을 쉽게 관리하기 위해 Teams는 사용자에게 정책을 할당하는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-108">To easily manage policies in your organization, Teams offers several ways to assign policies to users.</span></span> <span data-ttu-id="6afcc-109">일괄 처리 할당을 통해 개별적으로 또는 규모에 따라 사용자에게 직접 정책을 할당하거나 사용자가 구성원인 그룹에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-109">Assign a policy directly to users, either individually or at scale through a batch assignment, or to a group that the users are members of.</span></span> <span data-ttu-id="6afcc-110">정책 패키지를 사용하여 유사한 역할이 있는 조직의 사용자에게 미리 설정한 정책 컬렉션을 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-110">You can also use policy packages to assign a preset collection of policies to users in your organization who have similar roles.</span></span> <span data-ttu-id="6afcc-111">선택하는 옵션은 관리하는 정책의 수와 정책을 할당하는 사용자 수에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-111">The option that you choose depends on the number of policies that you're managing and the number of users you're assigning policies to.</span></span> <span data-ttu-id="6afcc-112">전역(조직 전체 기본값) 정책은 조직의 가장 많은 사용자 수에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-112">Global (Org-wide default) policies apply to the largest number of users in your organization.</span></span> <span data-ttu-id="6afcc-113">특수한 정책이 필요한 사용자에게만 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-113">You only have to assign policies to those users that require specialized policies.</span></span>

<span data-ttu-id="6afcc-114">이 문서에서는 사용자에게 정책을 할당할 수 있는 다양한 방법과 이를 사용할 때 권장되는 시나리오에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-114">This article describes the different ways that you can assign policies to users and the recommended scenarios for when to use what.</span></span>

## <a name="which-policy-takes-precedence"></a><span data-ttu-id="6afcc-115">우선 순위는 어떤 정책인가요?</span><span class="sxs-lookup"><span data-stu-id="6afcc-115">Which policy takes precedence?</span></span>

<span data-ttu-id="6afcc-116">사용자에게는 각 정책 유형에 대해 하나의 효과적인 정책이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-116">A user has one effective policy for each policy type.</span></span> <span data-ttu-id="6afcc-117">사용자가 정책을 직접 할당하고 동일한 유형의 정책을 할당한 하나 이상의 그룹의 구성원일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-117">It's possible, or even likely, that a user is directly assigned a policy and is also a member of one or more groups that's assigned a policy of the same type.</span></span> <span data-ttu-id="6afcc-118">이러한 종류의 시나리오에서 어떤 정책이 우선인가요?</span><span class="sxs-lookup"><span data-stu-id="6afcc-118">In these kinds of scenarios, which policy takes precedence?</span></span> <span data-ttu-id="6afcc-119">사용자의 유효 정책은 다음과 같이 우선 순위 규칙에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-119">A user's effective policy is determined according to rules of precedence, as follows.</span></span>

<span data-ttu-id="6afcc-120">사용자가 정책(개별적으로 또는 일괄 처리 할당을 통해)을 직접 할당하는 경우 해당 정책이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-120">If a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="6afcc-121">다음 시각적 예제에서 사용자의 효과적인 정책은 사용자에게 직접 할당되는 Lincoln Square 모임 정책입니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-121">In the following visual example, the user's effective policy is the Lincoln Square meeting policy, which is directly assigned to the user.</span></span>

![직접 할당된 정책이 우선하는 방법을 보여주는 다이어그램](media/assign-policies-example-directly-assigned.png)

<span data-ttu-id="6afcc-123">사용자가 지정된 유형의 정책을 직접 할당하지 않은 경우 사용자가 구성원인 그룹에 할당된 정책이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-123">If a user isn't directly assigned a policy of a given type, the policy assigned to a group that the user is a member of takes precedence.</span></span> <span data-ttu-id="6afcc-124">사용자가 여러 그룹의 구성원인 경우 해당 정책 유형에 대해 그룹 할당 순위가 가장 높은 정책이 우선합니다. [](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="6afcc-124">If a user is a member of multiple groups, the policy that has the highest [group assignment ranking](#group-assignment-ranking) for the given policy type takes precedence.</span></span>

<span data-ttu-id="6afcc-125">이 시각적 예제에서 사용자의 효과적인 정책은 Exec Teams 및 HD 정책으로, 이 정책은 사용자가 구성원으로 있는 다른 그룹에 비해 가장 높은 할당 순위를 가지며 동일한 정책 유형의 정책도 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-125">In this visual example, the user's effective policy is the Exec Teams and HD policy, which has the highest assignment ranking relative to other groups that the user is a member of and that are also assigned a policy of the same policy type.</span></span>  

![그룹에서 상속된 정책이 우선하는 방법을 보여주는 다이어그램](media/assign-policies-example-group.png)

<span data-ttu-id="6afcc-127">사용자가 정책을 직접 할당하지 않은 경우 또는 정책이 할당된 그룹의 구성원이 아닌 경우 사용자는 해당 정책 유형에 대한 전역(Org-wide default) 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-127">If a user isn't directly assigned a policy or isn't a member of any groups that are assigned a policy, the user gets the global (Org-wide default) policy for that policy type.</span></span> <span data-ttu-id="6afcc-128">다음은 시각적 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-128">Here's a visual example.</span></span>

![전역 정책의 우선 순위를 보여주는 다이어그램](media/assign-policies-example-global.png)

<span data-ttu-id="6afcc-130">자세한 내용은 우선 순위 [규칙을 참조합니다.](#precedence-rules)</span><span class="sxs-lookup"><span data-stu-id="6afcc-130">To learn more, see [Precedence rules](#precedence-rules).</span></span>

## <a name="ways-to-assign-policies"></a><span data-ttu-id="6afcc-131">정책을 할당하는 방법</span><span class="sxs-lookup"><span data-stu-id="6afcc-131">Ways to assign policies</span></span>

<span data-ttu-id="6afcc-132">사용자에게 정책을 할당할 수 있는 방법과 각 시나리오에 대해 권장되는 시나리오에 대한 개요는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-132">Here's an overview of the ways that you can assign policies to users and the recommended scenarios for each.</span></span> <span data-ttu-id="6afcc-133">자세한 내용은 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-133">Select the links to learn more.</span></span>

<span data-ttu-id="6afcc-134">개별 사용자 또는 그룹에 정책을 할당하기 전에 먼저 조직에서 가장 많은 사용자 수에 적용할 수 있도록 전역(조직 전체 [기본값)](#set-the-global-policies) 정책을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-134">Before assigning policies to individual users or groups, start by [setting the global (Org-wide default) policies](#set-the-global-policies) so that they apply to the largest number of users in your organization.</span></span>  <span data-ttu-id="6afcc-135">전역 정책을 설정하면 특수한 정책이 필요한 사용자에게만 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-135">Once the global policies are set, you'll only need to assign policies to those users that require specialized policies.</span></span>

|<span data-ttu-id="6afcc-136">방법</span><span class="sxs-lookup"><span data-stu-id="6afcc-136">Do this</span></span>  |<span data-ttu-id="6afcc-137">경우...</span><span class="sxs-lookup"><span data-stu-id="6afcc-137">If...</span></span>  | <span data-ttu-id="6afcc-138">사용 중...</span><span class="sxs-lookup"><span data-stu-id="6afcc-138">Using...</span></span>
|---------|---------|----|
|[<span data-ttu-id="6afcc-139">개별 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-139">Assign a policy to individual users</span></span>](#assign-a-policy-to-individual-users)    | <span data-ttu-id="6afcc-140">Teams를 새로 시작하거나 소수의 사용자에게 정책 하나 또는 몇 개만 할당하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-140">You're new to Teams and just getting started or you only need to assign one or a couple of policies to a small number of users.</span></span> |<span data-ttu-id="6afcc-141">Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="6afcc-141">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>
|[<span data-ttu-id="6afcc-142">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-142">Assign a policy to a group</span></span>](#assign-a-policy-to-a-group) |<span data-ttu-id="6afcc-143">사용자의 그룹 구성원 자격에 따라 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-143">Assign policies based on a user's group membership.</span></span> <span data-ttu-id="6afcc-144">예를 들어 보안 그룹 또는 메일 그룹의 모든 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-144">For example, assign a policy to all users in a security group or distribution list.</span></span>| <span data-ttu-id="6afcc-145">Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="6afcc-145">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
|[<span data-ttu-id="6afcc-146">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-146">Assign a policy to a batch of users</span></span>](#assign-a-policy-to-a-batch-of-users)   | <span data-ttu-id="6afcc-147">대규모 사용자 집합에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-147">Assign policies to large sets of users.</span></span> <span data-ttu-id="6afcc-148">예를 들어 조직에서 수백 또는 수천 명의 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-148">For example, assign a policy to hundreds or thousands of users in your organization at a time.</span></span> |<span data-ttu-id="6afcc-149">Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="6afcc-149">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="6afcc-150">사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-150">Assign a policy package to users</span></span>](#assign-a-policy-package-to-users)  |<span data-ttu-id="6afcc-151">동일한 역할 또는 유사한 역할이 있는 조직의 특정 사용자 집합에 여러 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-151">Assign multiple policies to specific sets of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="6afcc-152">예를 들어 학교의 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-152">For example, assign the Education (Teacher) policy package to teachers in your school to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="6afcc-153">중등 학생에게 교육(중등 학생) 정책 패키지를 할당하여 개인 통화와 같은 특정 기능을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-153">Assign the Education (Secondary school student) policy package to secondary students to limit certain capabilities such as private calling.</span></span>  |<span data-ttu-id="6afcc-154">Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="6afcc-154">The Microsoft Teams admin center or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| <span data-ttu-id="6afcc-155">[그룹에 정책 패키지](#assign-a-policy-package-to-a-group) 할당(비공개 미리 보기에서)</span><span class="sxs-lookup"><span data-stu-id="6afcc-155">[Assign a policy package to a group](#assign-a-policy-package-to-a-group) (in private preview)</span></span>   |<span data-ttu-id="6afcc-156">동일한 역할 또는 유사한 역할이 있는 조직의 사용자 그룹에 여러 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-156">Assign multiple policies to a group of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="6afcc-157">예를 들어 보안 그룹 또는 메일 그룹의 모든 사용자에게 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-157">For example, assign a policy package to all users in a security group or distribution list.</span></span> |<span data-ttu-id="6afcc-158">Teams PowerShell 모듈의 Microsoft Teams 관리 센터(곧) 또는 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="6afcc-158">The Microsoft Teams admin center (coming soon) or PowerShell cmdlets in the Teams PowerShell module</span></span>|
| [<span data-ttu-id="6afcc-159">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-159">Assign a policy package to a batch of users</span></span>](#assign-a-policy-package-to-a-batch-of-users)|<span data-ttu-id="6afcc-160">동일한 역할 또는 유사한 역할이 있는 조직의 사용자 일괄 처리에 여러 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-160">Assign multiple policies to a batch of users in your organization who have the same or similar roles.</span></span> <span data-ttu-id="6afcc-161">예를 들어 일괄 처리 과제를 사용하여 학교의 모든 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 액세스 권한을 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-161">For example, assign the Education (Teacher) policy package to all teachers in your school using batch assignment to give them full access to chats, calling, and meetings.</span></span> <span data-ttu-id="6afcc-162">사설 통화와 같은 특정 기능을 제한하기 위해 중등 학생 일괄 처리에 교육(중등 학생) 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-162">Assign the Education (Secondary school student) policy package to a batch of secondary students to limit certain capabilities such as private calling.</span></span>|<span data-ttu-id="6afcc-163">Teams PowerShell 모듈의 PowerShell cmdlet</span><span class="sxs-lookup"><span data-stu-id="6afcc-163">PowerShell cmdlets in the Teams PowerShell module</span></span>|

## <a name="set-the-global-policies"></a><span data-ttu-id="6afcc-164">전역 정책 설정</span><span class="sxs-lookup"><span data-stu-id="6afcc-164">Set the global policies</span></span>

<span data-ttu-id="6afcc-165">다음 단계를 수행하여 각 정책 유형에 대해 전역(Org-wide default) 정책을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-165">Follow these steps to set the global (Org-wide default) policies for each policy type.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="6afcc-166">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="6afcc-166">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="6afcc-167">Microsoft Teams 관리 센터의 왼쪽 탐색에서 업데이트할 정책 유형에 대한 정책 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-167">In the left navigation of the Microsoft Teams admin center, go to the policy page for the policy type you want to update.</span></span> <span data-ttu-id="6afcc-168">예를 들어 **Teams**  >  **Teams 정책,** **모임** 모임  >  정책, 메시징 **정책** 또는 **음성** 통화 정책이  >  **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-168">For example, **Teams** > **Teams policies**, **Meetings** > **Meetings policies**, **Messaging policies**, or **Voice** > **Calling policies**.</span></span>
2. <span data-ttu-id="6afcc-169">**전역(Org-wide 기본값)** 정책을 선택하여 현재 설정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-169">Select the **Global (Org-wide default)** policy to view the current settings.</span></span>
3. <span data-ttu-id="6afcc-170">필요한 경우 정책을 업데이트한 다음 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-170">Update the policy as needed, and then select **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="6afcc-171">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="6afcc-171">Using PowerShell</span></span>

<span data-ttu-id="6afcc-172">PowerShell을 사용하여 전역 정책을 설정하기 위해 전역 식별자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-172">To set the global policies using PowerShell, use the Global identifier.</span></span>  <span data-ttu-id="6afcc-173">먼저 현재 전역 정책을 검토하여 변경할 설정을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-173">Start by reviewing the current Global policy to determine which setting you want to change.</span></span>

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

<span data-ttu-id="6afcc-174">다음으로, 필요한 경우 전역 정책을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-174">Next, update the Global policy as needed.</span></span>  <span data-ttu-id="6afcc-175">변경할 설정의 값만 지정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-175">You only need to specify values for the settings that you want to change.</span></span>

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a><span data-ttu-id="6afcc-176">개별 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-176">Assign a policy to individual users</span></span>

<span data-ttu-id="6afcc-177">다음 단계에 따라 개별 사용자 또는 소수의 사용자에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-177">Follow these steps to assign a policy to an individual user or to a small number of users at a time.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="6afcc-178">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="6afcc-178">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="6afcc-179">사용자에게 정책을 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="6afcc-179">To assign a policy to a user:</span></span>

1. <span data-ttu-id="6afcc-180">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자로** 이동한 다음 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-180">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="6afcc-181">사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 다음 설정 편집 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-181">Select the user by clicking to the left of the user name, and then select **Edit settings**.</span></span>
3. <span data-ttu-id="6afcc-182">할당할 정책을 선택한 다음 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-182">Select the policy you want to assign, and then select **Apply**.</span></span>

<span data-ttu-id="6afcc-183">또는 다음을 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-183">Or, you can also do the following:</span></span>

1. <span data-ttu-id="6afcc-184">Microsoft Teams 관리 센터의 왼쪽 탐색에서 정책 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-184">In the left navigation of the Microsoft Teams admin center, go to the policy page.</span></span>
2. <span data-ttu-id="6afcc-185">정책 이름의 왼쪽을 클릭하여 할당할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-185">Select the policy you want to assign by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="6afcc-186">**사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-186">Select **Manage users**.</span></span>
4. <span data-ttu-id="6afcc-187">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="6afcc-187">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="6afcc-188">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-188">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="6afcc-189">사용자 추가가 완료되면 적용 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-189">When you're finished adding users, select **Apply**.</span></span>

### <a name="use-powershell"></a><span data-ttu-id="6afcc-190">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="6afcc-190">Use PowerShell</span></span>

<span data-ttu-id="6afcc-191">각 정책 유형에는 관리하기 위한 자체 cmdlet 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-191">Each policy type has its own set of cmdlets for managing it.</span></span> <span data-ttu-id="6afcc-192">특정 정책 유형에 ```Grant-``` 대한 cmdlet을 사용하여 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-192">Use the ```Grant-``` cmdlet for a given policy type to assign the policy.</span></span> <span data-ttu-id="6afcc-193">예를 들어 cmdlet을 사용하여 사용자에게 Teams 모임 정책을 ```Grant-CsTeamsMeetingPolicy``` 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-193">For example, use the ```Grant-CsTeamsMeetingPolicy``` cmdlet to assign a Teams meeting policy to users.</span></span> <span data-ttu-id="6afcc-194">이러한 cmdlet은 Teams PowerShell 모듈에 포함되어 있으며 [비즈니스용 Skype cmdlet](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)참조에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-194">These cmdlets are included in the Teams PowerShell module and are documented in the [Skype for Business cmdlet reference](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps).</span></span>

 <span data-ttu-id="6afcc-195">[Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 공개 릴리스(아직 없는 경우)를 다운로드하여 설치한 다음 다음을 실행하여 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-195">Download and install the [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) (if you haven't already), and then run the following to connect.</span></span>

> [!NOTE]
> <span data-ttu-id="6afcc-196">비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-196">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="6afcc-197">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-197">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

<span data-ttu-id="6afcc-198">이 예제에서는 학생 모임 정책이라는 Teams 모임 정책을 Reda라는 사용자에게 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-198">In this example, we assign a Teams meeting policy named Student Meeting Policy to a user named Reda.</span></span>

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

<span data-ttu-id="6afcc-199">자세한 내용은 [PowerShell을 통해 정책 관리 를 읽어보아야 합니다.](teams-powershell-managing-teams.md#manage-policies-via-powershell)</span><span class="sxs-lookup"><span data-stu-id="6afcc-199">To learn more, read [Manage policies via PowerShell](teams-powershell-managing-teams.md#manage-policies-via-powershell).</span></span>

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="6afcc-200">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-200">Assign a policy to a group</span></span>

<span data-ttu-id="6afcc-201">그룹에 정책 할당을 사용하면 보안 그룹 또는 메일 그룹과 같은 사용자 그룹에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-201">Policy assignment to groups lets you assign a policy to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="6afcc-202">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-202">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="6afcc-203">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-203">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="6afcc-204">그룹에 대한 정책 할당은 최대 50,000명까지의 그룹에 권장되지만 더 큰 그룹에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-204">Policy assignment to groups is recommended for groups of up to 50,000 users but it will also work with larger groups.</span></span>

<span data-ttu-id="6afcc-205">정책을 할당하면 그룹에 즉시 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-205">When you assign the policy, it's immediately assigned to the group.</span></span> <span data-ttu-id="6afcc-206">그러나 그룹의 구성원에게 정책 할당의 전파는 백그라운드 작업으로 수행됩니다. 그룹 크기에 따라 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-206">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="6afcc-207">그룹에서 정책이 부가되지 않은 경우나 구성원이 그룹에 추가되거나 그룹에서 제거될 때도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-207">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

<span data-ttu-id="6afcc-208">그룹 정책 할당은 그룹의 직접 구성원인 사용자에게만 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-208">Group policy assignments are only propagated to users who are direct members of the group.</span></span> <span data-ttu-id="6afcc-209">할당은 중첩된 그룹의 구성원에게 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-209">The assignments aren't propagated to members of nested groups.</span></span>

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a><span data-ttu-id="6afcc-210">그룹에 정책 할당에 대해 알아야 할 정보</span><span class="sxs-lookup"><span data-stu-id="6afcc-210">What you need to know about policy assignment to groups</span></span>

<span data-ttu-id="6afcc-211">시작하기 전에 우선 순위 규칙 및 그룹 할당 순위를 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-211">Before you get started, it's important to understand precedence rules and group assignment ranking.</span></span>

#### <a name="precedence-rules"></a><span data-ttu-id="6afcc-212">우선 순위 규칙</span><span class="sxs-lookup"><span data-stu-id="6afcc-212">Precedence rules</span></span>

<span data-ttu-id="6afcc-213">주어진 정책 형식의 경우 사용자의 유효 정책은 다음에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-213">For a given policy type, a user's effective policy is determined according to the following:</span></span>

- <span data-ttu-id="6afcc-214">사용자에게 직접 할당되는 정책은 그룹에 할당된 동일한 유형의 다른 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-214">A policy that's directly assigned to a user takes precedence over any other policy of the same type that's assigned to a group.</span></span> <span data-ttu-id="6afcc-215">즉, 사용자가 지정된 형식의 정책을 직접 할당하는 경우 해당 사용자는 그룹에서 동일한 형식의 정책을 상속하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-215">In other words, if a user is directly assigned a policy of a given type, that user won't inherit a policy of the same type from a group.</span></span> <span data-ttu-id="6afcc-216">즉, 사용자에게 직접 할당된 지정된 형식의 정책이 있는 경우 그룹에서 동일한 형식의 정책을 상속하려면 먼저 사용자로부터 해당 정책을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-216">This also means that if a user has a policy of a given type that was directly assigned to them, you have to remove that policy from the user before they can inherit a policy of the same type from a group.</span></span>
- <span data-ttu-id="6afcc-217">사용자에게 직접 할당된 정책이 없고 두 개 이상의 그룹의 구성원이고 각 그룹에 할당된 동일한 유형의 정책이 있는 경우 사용자는 가장 높은 순위를 가지는 그룹 할당의 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-217">If a user doesn't have a policy directly assigned to them and is a member of two or more groups and each group has a policy of the same type assigned to it, the user inherits the policy of the group assignment that has the highest ranking.</span></span>
- <span data-ttu-id="6afcc-218">사용자가 정책이 할당된 그룹의 구성원이 아닌 경우 해당 정책 유형에 대한 전역(Org-wide default) 정책이 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-218">If a user isn't a member of any groups that are assigned a policy, the global (Org-wide default) policy for that policy type applies to the user.</span></span>

<span data-ttu-id="6afcc-219">사용자의 유효 정책은 다음 규칙에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-219">A user's effective policy is updated according to these rules:</span></span>

- <span data-ttu-id="6afcc-220">사용자가 정책에 할당된 그룹에 추가되거나 제거될 때</span><span class="sxs-lookup"><span data-stu-id="6afcc-220">when a user is added to or removed from a group that's assigned a policy.</span></span>
- <span data-ttu-id="6afcc-221">그룹에서 정책이 부가되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-221">a policy is unassigned from a group.</span></span>
- <span data-ttu-id="6afcc-222">사용자에게 직접 할당된 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-222">a policy that's directly assigned to the user is removed.</span></span>

#### <a name="group-assignment-ranking"></a><span data-ttu-id="6afcc-223">그룹 할당 순위</span><span class="sxs-lookup"><span data-stu-id="6afcc-223">Group assignment ranking</span></span>

<span data-ttu-id="6afcc-224">그룹에 정책을 할당할 때 그룹 할당에 대한 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-224">When you assign a policy to a group, you specify a ranking for the group assignment.</span></span> <span data-ttu-id="6afcc-225">이 정책은 사용자가 두 개 이상의 그룹의 구성원이고 각 그룹에 동일한 유형의 정책이 할당된 경우 사용자가 효과적인 정책으로 상속해야 하는 정책을 결정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-225">This is used to determine which policy a user should inherit as their effective policy if the user is a member of two or more groups and each group is assigned a policy of the same type.</span></span>

<span data-ttu-id="6afcc-226">그룹 할당 순위는 동일한 유형의 다른 그룹 할당과 상대적입니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-226">The group assignment ranking is relative to other group assignments of the same type.</span></span> <span data-ttu-id="6afcc-227">예를 들어 두 그룹에 호출 정책을 할당하는 경우 한 할당의 순위를 1로, 다른 할당은 2로, 1은 가장 높은 순위로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-227">For example, if you're assigning a calling policy to two groups, set the ranking of one assignment to 1 and the other to 2, with 1 being the highest ranking.</span></span> <span data-ttu-id="6afcc-228">그룹 할당 순위는 상속과 관련하여 다른 그룹 멤버 자격보다 더 중요하거나 관련성이 높은 그룹 멤버 자격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-228">The group assignment ranking indicates which group membership is more important or more relevant than other group memberships with regards to inheritance.</span></span>

<span data-ttu-id="6afcc-229">예를 들어 직원 저장소 및 스토어 관리자의 두 그룹이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-229">Say, for example, you have two groups, Store Employees and Store Managers.</span></span> <span data-ttu-id="6afcc-230">두 그룹에는 각각 Teams 호출 정책, 스토어 직원 호출 정책 및 저장소 관리자 호출 정책이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-230">Both groups are assigned a Teams calling policy, Store Employees Calling Policy and Store Managers Calling Policy, respectively.</span></span> <span data-ttu-id="6afcc-231">두 그룹에 있는 저장소 관리자의 경우 관리자 역할은 직원 역할보다 관련성이 높기 때문에 Store Managers 그룹에 할당된 호출 정책은 순위가 높아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-231">For a store manager who is in both groups, their role as a manager is more relevant than their role as an employee, so the calling policy that's assigned to the Store Managers group should have a higher ranking.</span></span>

|<span data-ttu-id="6afcc-232">그룹</span><span class="sxs-lookup"><span data-stu-id="6afcc-232">Group</span></span> |<span data-ttu-id="6afcc-233">정책 이름을 호출하는 팀</span><span class="sxs-lookup"><span data-stu-id="6afcc-233">Teams calling policy name</span></span>  |<span data-ttu-id="6afcc-234">순위</span><span class="sxs-lookup"><span data-stu-id="6afcc-234">Rank</span></span>|
|---------|---------|---|
|<span data-ttu-id="6afcc-235">Store Managers</span><span class="sxs-lookup"><span data-stu-id="6afcc-235">Store Managers</span></span>   |<span data-ttu-id="6afcc-236">스토어 관리자 호출 정책</span><span class="sxs-lookup"><span data-stu-id="6afcc-236">Store Managers Calling Policy</span></span>         |<span data-ttu-id="6afcc-237">1</span><span class="sxs-lookup"><span data-stu-id="6afcc-237">1</span></span>|
|<span data-ttu-id="6afcc-238">직원 저장</span><span class="sxs-lookup"><span data-stu-id="6afcc-238">Store Employees</span></span>    |<span data-ttu-id="6afcc-239">직원 호출 정책 저장</span><span class="sxs-lookup"><span data-stu-id="6afcc-239">Store Employees Calling Policy</span></span>      |<span data-ttu-id="6afcc-240">2</span><span class="sxs-lookup"><span data-stu-id="6afcc-240">2</span></span>|

<span data-ttu-id="6afcc-241">순위를 지정하지 않으면 정책 할당에 가장 낮은 순위가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-241">If you don't specify a ranking, the policy assignment is given the lowest ranking.</span></span>

### <a name="in-the-teams-admin-center"></a><span data-ttu-id="6afcc-242">Teams 관리 센터에서</span><span class="sxs-lookup"><span data-stu-id="6afcc-242">In the Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="6afcc-243">현재 Microsoft Teams 관리 센터를 사용하는 그룹에 대한 정책 할당은 Teams 호출 정책, Teams 호출 공원 정책, Teams 정책, Teams 라이브 이벤트 정책, Teams 모임 정책 및 Teams 메시징 정책에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-243">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="6afcc-244">다른 정책 형식의 경우 PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-244">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="6afcc-245">Microsoft Teams 관리 센터의 왼쪽 탐색에서 정책 유형 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-245">In the left navigation of the Microsoft Teams admin center, go to the policy type page.</span></span> <span data-ttu-id="6afcc-246">예를 들어 모임 모임 정책  >  **으로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-246">For example, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="6afcc-247">그룹 정책 **할당 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-247">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="6afcc-248">그룹 **추가를 선택한** 다음  그룹화 정책 할당 창에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-248">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>
    1. <span data-ttu-id="6afcc-249">정책을 할당할 그룹을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-249">Search for and add the group you want to assign the policy to.</span></span>
    2. <span data-ttu-id="6afcc-250">그룹 할당의 순위를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-250">Set the ranking for the group assignment.</span></span>
    3. <span data-ttu-id="6afcc-251">할당할 정책을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-251">Select the policy that you want to assign.</span></span>
    4. <span data-ttu-id="6afcc-252">적용 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-252">Select **Apply**.</span></span>

<span data-ttu-id="6afcc-253">그룹 정책 할당을 제거하려면  정책 페이지의 그룹 정책 할당 탭에서 그룹 할당을 선택한 다음 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-253">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="6afcc-254">그룹 할당의 순위를 변경하려면 먼저 그룹 정책 할당을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-254">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="6afcc-255">그런 다음 위의 단계를 수행하여 그룹에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-255">Then, follow the steps above to assign the policy to a group.</span></span>

### <a name="use-the-powershell-option"></a><span data-ttu-id="6afcc-256">PowerShell 옵션 사용</span><span class="sxs-lookup"><span data-stu-id="6afcc-256">Use the PowerShell option</span></span>

> [!NOTE]
> <span data-ttu-id="6afcc-257">현재 PowerShell을 사용하는 그룹에 대한 정책 할당은 모든 Teams 정책 유형에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-257">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="6afcc-258">지원되는 정책 유형 목록에 대한 [New-CsGroupPolicyAssignment를](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6afcc-258">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="6afcc-259">Microsoft Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="6afcc-259">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="6afcc-260">단계별 지침은 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="6afcc-260">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-to-a-group-of-users"></a><span data-ttu-id="6afcc-261">사용자 그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-261">Assign a policy to a group of users</span></span>

<span data-ttu-id="6afcc-262">[New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-262">Use the [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet to assign a policy to a group.</span></span> <span data-ttu-id="6afcc-263">개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-263">You can specify a group by using the object ID, SIP address, or email address.</span></span>

<span data-ttu-id="6afcc-264">이 예제에서는 할당 순위가 1인 그룹에 Retail Managers 모임 정책이라는 Teams 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-264">In this example, we assign a Teams meeting policy named Retail Managers Meeting Policy to a group with an assignment ranking of 1.</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="6afcc-265">그룹에 대한 정책 할당을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-265">Get policy assignments for a group</span></span>

<span data-ttu-id="6afcc-266">[Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 할당된 모든 정책을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-266">Use the [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet to get all policies assigned to a group.</span></span> <span data-ttu-id="6afcc-267">그룹은 정책을 할당하는 데 SIP 주소 또는 전자 메일 주소를 사용하는 경우에도 항상 그룹 ID로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-267">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

<span data-ttu-id="6afcc-268">이 예제에서는 특정 그룹에 할당된 모든 정책을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-268">In this example, we retrieve all policies assigned to a specific group.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

<span data-ttu-id="6afcc-269">이 예제에서는 Teams 모임 정책이 할당된 모든 그룹을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-269">In this example, we return all groups that are assigned a Teams meeting policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a><span data-ttu-id="6afcc-270">그룹에서 정책 제거</span><span class="sxs-lookup"><span data-stu-id="6afcc-270">Remove a policy from a group</span></span>

<span data-ttu-id="6afcc-271">[Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet을 사용하여 그룹에서 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-271">Use the [Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet to remove a policy from a group.</span></span> <span data-ttu-id="6afcc-272">그룹에서 정책을 제거하면 해당 그룹에 할당된 동일한 유형의 다른 정책의 우선 순위가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-272">When you remove a policy from a group, the priorities of other policies of the same type assigned to that group, and that have a lower ranking, are updated.</span></span> <span data-ttu-id="6afcc-273">예를 들어 순위가 2인 정책을 제거하면 순위가 3과 4인 정책이 업데이트되어 새 순위가 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-273">For example, if you remove a policy that has a ranking of 2, policies that have a ranking of 3 and 4 are updated to reflect their new ranking.</span></span> <span data-ttu-id="6afcc-274">다음 두 표에는 이 예제가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-274">The following two tables show this example.</span></span>

<span data-ttu-id="6afcc-275">다음은 Teams 모임 정책에 대한 정책 할당 및 우선 순위 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-275">Here's a list of the policy assignments and priorities for a Teams meeting policy.</span></span>

|<span data-ttu-id="6afcc-276">그룹 이름</span><span class="sxs-lookup"><span data-stu-id="6afcc-276">Group name</span></span>  |<span data-ttu-id="6afcc-277">정책 이름</span><span class="sxs-lookup"><span data-stu-id="6afcc-277">Policy name</span></span>  |<span data-ttu-id="6afcc-278">순위</span><span class="sxs-lookup"><span data-stu-id="6afcc-278">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="6afcc-279">영업</span><span class="sxs-lookup"><span data-stu-id="6afcc-279">Sales</span></span>    |<span data-ttu-id="6afcc-280">판매 정책</span><span class="sxs-lookup"><span data-stu-id="6afcc-280">Sales policy</span></span>       | <span data-ttu-id="6afcc-281">1</span><span class="sxs-lookup"><span data-stu-id="6afcc-281">1</span></span>        |
|<span data-ttu-id="6afcc-282">서부 지역</span><span class="sxs-lookup"><span data-stu-id="6afcc-282">West Region</span></span>     |<span data-ttu-id="6afcc-283">서부 지역 정책</span><span class="sxs-lookup"><span data-stu-id="6afcc-283">West Region policy</span></span>         |<span data-ttu-id="6afcc-284">2</span><span class="sxs-lookup"><span data-stu-id="6afcc-284">2</span></span>         |
|<span data-ttu-id="6afcc-285">디비전</span><span class="sxs-lookup"><span data-stu-id="6afcc-285">Division</span></span>    |<span data-ttu-id="6afcc-286">분할 정책</span><span class="sxs-lookup"><span data-stu-id="6afcc-286">Division policy</span></span>         |<span data-ttu-id="6afcc-287">3</span><span class="sxs-lookup"><span data-stu-id="6afcc-287">3</span></span>         |
|<span data-ttu-id="6afcc-288">자회사</span><span class="sxs-lookup"><span data-stu-id="6afcc-288">Subsidiary</span></span>   |<span data-ttu-id="6afcc-289">자회사 정책</span><span class="sxs-lookup"><span data-stu-id="6afcc-289">Subsidiary policy</span></span>        |<span data-ttu-id="6afcc-290">4</span><span class="sxs-lookup"><span data-stu-id="6afcc-290">4</span></span>         |

<span data-ttu-id="6afcc-291">서부 지역 그룹에서 서부 지역 정책을 제거하는 경우 정책 할당 및 우선 순위는 다음과 같이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-291">If we remove the West Region policy from the West Region group, the policy assignments and priorities are updated as follows.</span></span>

|<span data-ttu-id="6afcc-292">그룹 이름</span><span class="sxs-lookup"><span data-stu-id="6afcc-292">Group name</span></span>  |<span data-ttu-id="6afcc-293">정책 이름</span><span class="sxs-lookup"><span data-stu-id="6afcc-293">Policy name</span></span>  |<span data-ttu-id="6afcc-294">순위</span><span class="sxs-lookup"><span data-stu-id="6afcc-294">Rank</span></span>|
|---------|---------|---------|
|<span data-ttu-id="6afcc-295">영업</span><span class="sxs-lookup"><span data-stu-id="6afcc-295">Sales</span></span>    |<span data-ttu-id="6afcc-296">판매 정책</span><span class="sxs-lookup"><span data-stu-id="6afcc-296">Sales policy</span></span>       | <span data-ttu-id="6afcc-297">1</span><span class="sxs-lookup"><span data-stu-id="6afcc-297">1</span></span>        |
|<span data-ttu-id="6afcc-298">디비전</span><span class="sxs-lookup"><span data-stu-id="6afcc-298">Division</span></span>    |<span data-ttu-id="6afcc-299">분할 정책</span><span class="sxs-lookup"><span data-stu-id="6afcc-299">Division policy</span></span>         |<span data-ttu-id="6afcc-300">2</span><span class="sxs-lookup"><span data-stu-id="6afcc-300">2</span></span>         |
|<span data-ttu-id="6afcc-301">자회사</span><span class="sxs-lookup"><span data-stu-id="6afcc-301">Subsidiary</span></span>   |<span data-ttu-id="6afcc-302">자회사 정책</span><span class="sxs-lookup"><span data-stu-id="6afcc-302">Subsidiary policy</span></span>        |<span data-ttu-id="6afcc-303">3</span><span class="sxs-lookup"><span data-stu-id="6afcc-303">3</span></span>        |

<span data-ttu-id="6afcc-304">이 예제에서는 그룹에서 Teams 모임 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-304">In this example, we remove the Teams meeting policy from a group.</span></span>

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a><span data-ttu-id="6afcc-305">그룹에 대한 정책 할당 변경</span><span class="sxs-lookup"><span data-stu-id="6afcc-305">Change a policy assignment for a group</span></span>

> [!NOTE]
> <span data-ttu-id="6afcc-306">[Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 곧 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-306">The [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet will be available soon.</span></span> <span data-ttu-id="6afcc-307">그 동안 그룹 정책 할당을 변경하려면 그룹에서 현재 정책 할당을 제거한 다음 새 정책 할당을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-307">In the meantime, to change a group policy assignment, you can remove the current policy assignment from the group, and then add a new policy assignment.</span></span>

<span data-ttu-id="6afcc-308">그룹에 정책을 할당한 후 [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 사용하여 해당 그룹의 정책 할당을 다음과 같이 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-308">After you assign a policy to a group, you can use the [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet to change that group's policy assignment as follows:</span></span>

- <span data-ttu-id="6afcc-309">순위 변경</span><span class="sxs-lookup"><span data-stu-id="6afcc-309">Change the ranking</span></span>
- <span data-ttu-id="6afcc-310">주어진 정책 형식의 정책 변경</span><span class="sxs-lookup"><span data-stu-id="6afcc-310">Change the policy of a given policy type</span></span>
- <span data-ttu-id="6afcc-311">주어진 정책 유형 및 순위의 정책 변경</span><span class="sxs-lookup"><span data-stu-id="6afcc-311">Change the policy of a given policy type and the ranking</span></span>

<span data-ttu-id="6afcc-312">이 예제에서는 그룹의 Teams 호출 공원 정책을 SupportCallPark라는 정책으로 변경하고 할당 순위를 3으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-312">In this example, we change a group's Teams call park policy to a policy named SupportCallPark and the assignment ranking to 3.</span></span>

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a><span data-ttu-id="6afcc-313">사용자에 대한 유효 정책 변경</span><span class="sxs-lookup"><span data-stu-id="6afcc-313">Change the effective policy for a user</span></span>

<span data-ttu-id="6afcc-314">정책에 직접 할당된 사용자에 대한 효과적인 정책을 변경하는 방법에 대한 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-314">Here's an example of how to change the effective policy for a user who is directly assigned a policy.</span></span>

<span data-ttu-id="6afcc-315">먼저 [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet과 매개 변수를 함께 사용하여 사용자와 연결된 Teams 모임 브로드캐스트 정책에 대한 세부 정보를 ```PolicySource``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-315">First, we use the [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet together with the ```PolicySource``` parameter to get details of the Teams meeting broadcast policies associated with the user.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

<span data-ttu-id="6afcc-316">출력은 사용자가 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트라는 정책보다 우선하는 Employee Events라는 Teams 모임 브로드캐스트 정책을 직접 할당했다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-316">The output shows that the user was directly assigned a Teams meeting broadcast policy named Employee Events, which takes precedence over the policy named Vendor Live Events that's assigned to a group the user belongs to.</span></span>

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

<span data-ttu-id="6afcc-317">이제 사용자에서 Employee Events 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-317">Now, we remove the Employee Events policy from the user.</span></span> <span data-ttu-id="6afcc-318">즉, 사용자에게 더 이상 Teams 모임 브로드캐스트 정책이 직접 할당되지 않고 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트 정책을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-318">This means that the user no longer has a Teams meeting broadcast policy directly assigned to them and will inherit the Vendor Live Events policy that's assigned to the group the user belongs to.</span></span>

<span data-ttu-id="6afcc-319">이 작업을 위해 비즈니스용 Skype PowerShell 모듈에서 다음 cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-319">Use the following cmdlet in the Skype for Business PowerShell module to do this.</span></span>

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

<span data-ttu-id="6afcc-320">Teams PowerShell 모듈에서 다음 cmdlet을 사용하여 일괄 처리 정책 할당이 $users 사용자 목록인 대규모로 이 작업을 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="6afcc-320">Use following cmdlet in the Teams PowerShell module to do this at scale though a batch policy assignment, where $users is a list of users that you specify.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="6afcc-321">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-321">Assign a policy to a batch of users</span></span>

### <a name="use-the-admin-center"></a><span data-ttu-id="6afcc-322">관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="6afcc-322">Use the admin center</span></span>

<span data-ttu-id="6afcc-323">사용자에게 정책을 대량으로 할당하는 경우:</span><span class="sxs-lookup"><span data-stu-id="6afcc-323">To assign a policy to users in bulk:</span></span>

1. <span data-ttu-id="6afcc-324">Microsoft Teams 관리 센터의 왼쪽 탐색에서 사용자를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-324">In the left navigation of the Microsoft Teams admin center, select **Users**.</span></span>
2. <span data-ttu-id="6afcc-325">정책을 할당할 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-325">Search for the users you want to assign the policy to or filter the view to show the users you want.</span></span>
3. <span data-ttu-id="6afcc-326">**&#x2713;**(확인 표시) 열에서 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-326">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="6afcc-327">모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-327">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
4. <span data-ttu-id="6afcc-328">설정 **편집을 선택하고** 원하는 내용을 변경한 다음 적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-328">Select **Edit settings**, make the changes that you want, and then select **Apply**.</span></span>

<span data-ttu-id="6afcc-329">정책 할당의 상태를 확인하려면 적용을 선택한 후 사용자 페이지  맨 위에  나타나는 배너에서 활동 **로그를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-329">To view the status of your policy assignment, in the banner that appears at the top of the **Users** page after you select **Apply** to submit your policy assignment, select **Activity log**.</span></span> <span data-ttu-id="6afcc-330">또는 Microsoft Teams 관리 센터의 왼쪽 탐색에서 대시보드로 이동한 다음 활동 로그에서 **세부** 정보 **보기를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-330">Or, in the left navigation of the Microsoft Teams admin center, go to **Dashboard**, and then under **Activity log**, select **View details**.</span></span> <span data-ttu-id="6afcc-331">활동 로그는 지난 30일 동안 Microsoft Teams 관리 센터를 통해 20명 이상의 사용자 일괄 처리에 대한 정책 할당을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-331">The Activity log shows policy assignments to batches of more than 20 users through the Microsoft Teams admin center from the last 30 days.</span></span> <span data-ttu-id="6afcc-332">자세한 내용은 활동 로그에서 정책 할당 [보기를 참조합니다.](activity-log.md)</span><span class="sxs-lookup"><span data-stu-id="6afcc-332">To learn more, see [View your policy assignments in the Activity log](activity-log.md).</span></span>

### <a name="use-powershell-method"></a><span data-ttu-id="6afcc-333">PowerShell 메서드 사용</span><span class="sxs-lookup"><span data-stu-id="6afcc-333">Use PowerShell method</span></span>

> [!NOTE]
> <span data-ttu-id="6afcc-334">현재 PowerShell을 사용하는 일괄 처리 정책 할당은 모든 Teams 정책 유형에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-334">Currently, batch policy assignment using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="6afcc-335">지원되는 정책 유형 목록은 [New-CsBatchPolicyAssignmentOperation을](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6afcc-335">See [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) for the list of supported policy types.</span></span>

<span data-ttu-id="6afcc-336">일괄 처리 정책 할당을 사용하면 스크립트를 사용하지 않고도 동시에 대규모 사용자 집합에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-336">With batch policy assignment, you can assign a policy to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="6afcc-337">[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 사용자 일괄 처리 및 할당하려는 정책을 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-337">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy that you want to assign.</span></span> <span data-ttu-id="6afcc-338">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-338">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="6afcc-339">그런 다음 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 과제의 진행률 및 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-339">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="6afcc-340">개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-340">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="6afcc-341">사용자의 SIP 주소는 종종 UPN(사용자 주체 이름) 또는 전자 메일 주소와 동일한 값을 지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-341">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this is not required.</span></span> <span data-ttu-id="6afcc-342">사용자가 UPN 또는 전자 메일을 사용하여 지정되지만 해당 SIP 주소와 다른 값이 있는 경우 사용자에게 정책 할당이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-342">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="6afcc-343">일괄 처리에 중복 사용자가 포함된 경우 처리 전에 일괄 처리에서 중복된 사용자가 제거되고 일괄 처리에 남아 있는 고유 사용자에게만 상태가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-343">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="6afcc-344">배치에는 최대 5천 명의 사용자가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-344">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="6afcc-345">최상의 결과를 얻기 위해 한 번에 몇 개 이상의 일괄 처리를 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-345">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="6afcc-346">더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-346">Allow batches to complete processing before submitting more batches.</span></span>

#### <a name="install-and-connect-to-the-teams-powershell-module"></a><span data-ttu-id="6afcc-347">Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="6afcc-347">Install and connect to the Teams PowerShell module</span></span>

<span data-ttu-id="6afcc-348">다음을 실행하여 [Microsoft Teams PowerShell 모듈을 설치합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="6afcc-348">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="6afcc-349">버전 1.0.5 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-349">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6afcc-350">다음을 실행하여 Teams에 연결하고 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-350">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="6afcc-351">메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-351">When you're prompted, sign in using your admin credentials.</span></span>

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a><span data-ttu-id="6afcc-352">Azure AD PowerShell for Graph 모듈 설치 및 연결(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="6afcc-352">Install and connect to the Azure AD PowerShell for Graph module (optional)</span></span>

<span data-ttu-id="6afcc-353">또한 Azure [AD PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 모듈(아직 없는 경우)을 다운로드하여 설치하고 조직의 사용자 목록을 검색할 수 있도록 Azure AD에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-353">You might also want to [download and install the Azure AD PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (if you haven't already) and connect to Azure AD so that you can retrieve a list of users in your organization.</span></span>

<span data-ttu-id="6afcc-354">다음을 실행하여 Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-354">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="6afcc-355">메시지가 표시될 때 Teams에 연결하는 데 사용한 동일한 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-355">When you're prompted, sign in using the same admin credentials that you used to connect to Teams.</span></span>

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a><span data-ttu-id="6afcc-356">사용자 일괄 처리에 설정 정책 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-356">Assign a setup policy to a batch of users</span></span>

<span data-ttu-id="6afcc-357">이 예제에서는 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 Users_ids.text 파일에 나열된 사용자 일괄 처리에 HR 앱 설정 정책이라는 앱 설치 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-357">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign an app setup policy named HR App Setup Policy to a batch of users listed in the Users_ids.text file.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

<span data-ttu-id="6afcc-358">이 예제에서는 Azure AD에 연결하여 사용자 컬렉션을 검색한 다음, SIP 주소를 사용하여 지정된 사용자 일괄 처리에 새 고용 메시징 정책이라는 메시징 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-358">In this example, we connect to Azure AD to retrieve a collection of users and then assign a messaging policy named New Hire Messaging Policy to a batch of users specified by using their SIP address.</span></span>

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a><span data-ttu-id="6afcc-359">일괄 처리 할당의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="6afcc-359">Get the status of a batch assignment</span></span>

<span data-ttu-id="6afcc-360">다음을 실행하여 일괄 처리 할당의 상태를 얻습니다. 여기서 OperationId는 주어진 일괄 처리에 대해 cmdlet에서 반환되는 작업 ```New-CsBatchPolicyAssignmentOperation``` ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-360">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="6afcc-361">출력에서 오류가 발생한 것으로 표시되는 경우 다음을 실행하여 속성에 있는 오류에 대한 자세한 정보를 ```UserState``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-361">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="6afcc-362">자세한 내용은 [Get-CsBatchPolicyAssignmentOperation 을 참조합니다.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="6afcc-362">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="6afcc-363">사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-363">Assign a policy package to users</span></span>

<span data-ttu-id="6afcc-364">Teams의 정책 패키지는 조직의 역할이 동일하거나 유사한 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-364">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="6afcc-365">각 정책 패키지는 사용자 역할을 중심으로 설계하며 해당 역할에 대한 일반적인 활동을 지원하는 미리 정의된 정책 및 정책 설정을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-365">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="6afcc-366">정책 패키지의 몇 가지 예로는 교육(교사) 패키지 및 Healthcare(임상 작업자) 패키지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-366">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="6afcc-367">자세한 내용은 Teams에서 정책 [패키지 관리를 참조합니다.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="6afcc-367">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="6afcc-368">한 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-368">Assign a policy package to one user</span></span>

1. <span data-ttu-id="6afcc-369">Microsoft Teams 관리 센터의 왼쪽 탐색에서 **사용자로** 이동한 다음 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-369">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="6afcc-370">사용자의 페이지에서 정책 **을** 선택한 다음 정책 패키지 옆에 **있는** **편집을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-370">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="6afcc-371">정책 **패키지** 할당 창에서 할당할 패키지를 선택한 다음 저장을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-371">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="6afcc-372">여러 사용자에게 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-372">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="6afcc-373">Microsoft Teams 관리 센터의 왼쪽 탐색에서 정책 패키지로 이동한 다음, 패키지 이름의 왼쪽을 클릭하여 할당할 정책 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-373">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="6afcc-374">**사용자 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-374">Select **Manage users**.</span></span>
3. <span data-ttu-id="6afcc-375">**사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="6afcc-375">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="6afcc-376">추가할 각 사용자에 대해 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-376">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="6afcc-377">사용자 추가가 완료되면 저장 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-377">When you're finished adding users, select **Save**.</span></span>

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="6afcc-378">그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-378">Assign a policy package to a group</span></span>

<span data-ttu-id="6afcc-379">그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-379">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="6afcc-380">정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-380">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="6afcc-381">그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-381">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="6afcc-382">최대 50,000명까지의 그룹에 대해 그룹에 정책 패키지 할당을 할당하는 것이 좋습니다. 하지만 더 큰 그룹에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-382">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="6afcc-383">정책 패키지를 할당하면 그룹에 즉시 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-383">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="6afcc-384">그러나 그룹의 구성원에게 정책 할당의 전파는 백그라운드 작업으로 수행됩니다. 그룹 크기에 따라 다소 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-384">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="6afcc-385">그룹에서 정책이 부가되지 않은 경우나 구성원이 그룹에 추가되거나 그룹에서 제거될 때도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-385">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6afcc-386">시작하기 전에 우선 순위 규칙 및 [](#precedence-rules) 그룹 할당 순위를 [이해하는 것이 중요합니다.](#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="6afcc-386">Before you get started, it's important to understand [precedence rules](#precedence-rules) and [group assignment ranking](#group-assignment-ranking).</span></span> <span data-ttu-id="6afcc-387">이 문서의 앞부분에 있는 그룹에 정책 할당에 대해 알아야 할 개념을 [읽고](#what-you-need-to-know-about-policy-assignment-to-groups) 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-387">Make sure you read and understand the concepts in [What you need to know about policy assignment to groups](#what-you-need-to-know-about-policy-assignment-to-groups) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="6afcc-388">관리 센터의 사용자 그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-388">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="6afcc-389">Teams 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-389">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="6afcc-390">왼쪽 탐색에서 정책 패키지 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-390">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="6afcc-391">그룹 정책 할당 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-391">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="6afcc-392">그룹 **추가를 선택한** 다음 정책 패키지 할당에서 그룹 창을 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-392">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="6afcc-393">a.</span><span class="sxs-lookup"><span data-stu-id="6afcc-393">a.</span></span> <span data-ttu-id="6afcc-394">정책 패키지를 할당할 그룹을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-394">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="6afcc-395">b.</span><span class="sxs-lookup"><span data-stu-id="6afcc-395">b.</span></span> <span data-ttu-id="6afcc-396">정책 패키지를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-396">Select a policy package.</span></span>

    <span data-ttu-id="6afcc-397">c.</span><span class="sxs-lookup"><span data-stu-id="6afcc-397">c.</span></span> <span data-ttu-id="6afcc-398">각 정책 유형에 대한 순위를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-398">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="6afcc-399">d.</span><span class="sxs-lookup"><span data-stu-id="6afcc-399">d.</span></span> <span data-ttu-id="6afcc-400">적용 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="6afcc-400">Select **Apply**.</span></span>

    ![그룹 정책 할당을 보여줍니다.](media/group-pkg-assignment.png)

5. <span data-ttu-id="6afcc-402">특정 정책 유형에 대한 순위를 관리하기 위해 특정 정책 페이지로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-402">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="6afcc-403">정책 패키지를 그룹에 다시 할당하려면 먼저 그룹 정책 할당을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-403">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="6afcc-404">그런 다음 위의 단계를 수행하여 그룹에 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-404">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="6afcc-405">PowerShell 작업</span><span class="sxs-lookup"><span data-stu-id="6afcc-405">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="6afcc-406">Teams PowerShell 모듈 사용</span><span class="sxs-lookup"><span data-stu-id="6afcc-406">Get the Teams PowerShell module</span></span>

<span data-ttu-id="6afcc-407">단계별 지침은 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="6afcc-407">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="6afcc-408">사용자 그룹에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-408">Assign a policy package to a group of users</span></span>

<span data-ttu-id="6afcc-409">[Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet을 사용하여 그룹에 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-409">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="6afcc-410">개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-410">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="6afcc-411">정책 패키지를 할당할 때 [](#group-assignment-ranking) 정책 패키지의 각 정책 유형에 대한 그룹 할당 순위를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-411">When you assign the policy package, specify a [group assignment ranking](#group-assignment-ranking) for each policy type in the policy package.</span></span>

<span data-ttu-id="6afcc-412">이 예제에서는 TeamsAppSetupPolicy 및 TeamsMeetingBroadcastPolicy에 대한 할당 순위가 1이고 TeamsMeetingPolicy에 대한 2 순위가 있는 그룹에 Education_Teacher 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-412">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="6afcc-413">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-413">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="6afcc-414">일괄 처리 정책 패키지 할당을 사용하면 스크립트를 사용하지 않고도 동시에 대규모 사용자 집합에 정책 패키지를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-414">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="6afcc-415">[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 사용자 일괄 처리 및 할당하려는 정책 패키지를 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-415">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="6afcc-416">할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-416">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="6afcc-417">그런 다음 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 과제의 진행률 및 상태를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-417">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="6afcc-418">개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-418">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="6afcc-419">사용자의 SIP 주소는 종종 UPN(사용자 주체 이름) 또는 전자 메일 주소와 동일한 값을 지만 필수는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-419">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="6afcc-420">사용자가 UPN 또는 전자 메일을 사용하여 지정되지만 해당 SIP 주소와 다른 값이 있는 경우 사용자에게 정책 할당이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-420">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="6afcc-421">일괄 처리에 중복 사용자가 포함된 경우 처리 전에 일괄 처리에서 중복된 사용자가 제거되고 일괄 처리에 남아 있는 고유 사용자에게만 상태가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-421">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="6afcc-422">일괄 처리에는 최대 5,000명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-422">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="6afcc-423">최상의 결과를 얻기 위해 한 번에 몇 개 이상의 일괄 처리를 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-423">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="6afcc-424">더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-424">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="6afcc-425">Teams PowerShell 모듈 사용</span><span class="sxs-lookup"><span data-stu-id="6afcc-425">Use the Teams PowerShell module</span></span>

<span data-ttu-id="6afcc-426">다음을 실행하여 [Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 모듈을 설치합니다(아직 없는 경우).</span><span class="sxs-lookup"><span data-stu-id="6afcc-426">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="6afcc-427">버전 1.0.5 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-427">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="6afcc-428">다음을 실행하여 Teams에 연결하고 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-428">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="6afcc-429">메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-429">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="6afcc-430">사용자 일괄 처리에 정책 패키지 할당</span><span class="sxs-lookup"><span data-stu-id="6afcc-430">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="6afcc-431">이 예제에서는 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 사용자 일괄 처리에 Education_PrimaryStudent 정책 패키지를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-431">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="6afcc-432">일괄 처리 할당의 상태 보기</span><span class="sxs-lookup"><span data-stu-id="6afcc-432">See the status of a batch assignment</span></span>

<span data-ttu-id="6afcc-433">다음을 실행하여 일괄 처리 할당의 상태를 얻습니다. 여기서 OperationId는 주어진 일괄 처리에 대해 cmdlet에서 반환되는 작업 ```New-CsBatchPolicyAssignmentOperation``` ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-433">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="6afcc-434">출력에서 오류가 발생한 것으로 표시되는 경우 다음을 실행하여 속성에 있는 오류에 대한 자세한 정보를 ```UserState``` 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6afcc-434">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="6afcc-435">자세한 내용은 [Get-CsBatchPolicyAssignmentOperation 을 참조합니다.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)</span><span class="sxs-lookup"><span data-stu-id="6afcc-435">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="6afcc-436">관련 항목</span><span class="sxs-lookup"><span data-stu-id="6afcc-436">Related topics</span></span>

[<span data-ttu-id="6afcc-437">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="6afcc-437">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
