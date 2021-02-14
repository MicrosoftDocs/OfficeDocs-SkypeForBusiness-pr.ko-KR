---
title: 학교에서 대규모 사용자 집합에 정책 할당
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: karsmith, angch, cebulnes
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 그룹 구성원 자격에 따라 또는 원격 학교(원격 학교, 원격 학교)에 대한 일괄 처리 할당을 통해 교육 기관의 대규모 사용자 집합에 정책을 할당하는 방법을 배정합니다.
f1keywords: ''
ms.openlocfilehash: afcaba9df0ff745977b84e34683c1bdfcaca0d01
ms.sourcegitcommit: 07afc959fec802db583e7111280d0035fdb6e412
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616942"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="8aec7-103">학교에서 대규모 사용자 집합에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8aec7-103">Assign policies to large sets of users in your school</span></span>

[!INCLUDE [policy-wizard-edu](includes/policy-wizard-edu.md)]

> [!NOTE]
> <span data-ttu-id="8aec7-104">Microsoft Teams에서 정책 할당에 대한 자세한 내용은 Teams에서 사용자에게 정책 [할당을 참조합니다.](assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="8aec7-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="8aec7-105">개요</span><span class="sxs-lookup"><span data-stu-id="8aec7-105">Overview</span></span>

<span data-ttu-id="8aec7-106">학생과 강사에게 Microsoft Teams의 다양한 기능에 대한 액세스 권한을 제공해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="8aec7-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="8aec7-107">라이선스 유형별로 조직의 사용자를 빠르게 식별한 다음 적절한 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="8aec7-108">이 자습서에서는 학교에서 대규모 사용자 집합에 모임 정책을 할당하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="8aec7-109">Microsoft Teams 관리 센터와 PowerShell을 사용하여 정책을 할당할 수 있으며 두 가지 방법을 모두 보여 드리게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="8aec7-110">일괄 처리 정책 할당을 통해 사용자가 구성원인 보안 그룹에 모임 정책을 할당하거나 대규모로 사용자에게 직접 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="8aec7-111">다음 방법을 배워보게 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-111">You'll learn how to:</span></span>

- <span data-ttu-id="8aec7-112">**그룹에 [정책 할당을 사용하여](#assign-a-policy-to-a-group)** 보안 그룹에 모임 정책을 할당합니다(권장).</span><span class="sxs-lookup"><span data-stu-id="8aec7-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="8aec7-113">이 방법을 사용하면 그룹 멤버 자격에 따라 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="8aec7-114">보안 그룹 또는 메일 그룹에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="8aec7-115">구성원이 그룹에 추가되거나 그룹에서 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="8aec7-116">새 사용자에 대한 정책을 관리하는 시간을 줄이거나 사용자의 역할이 변경될 때 이 방법을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="8aec7-117">이 방법은 최대 50,000명까지의 사용자 그룹에 가장 잘 작동하지만 더 큰 그룹에서도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="8aec7-118">**일괄 [처리 정책 할당을](assign-policies.md#assign-a-policy-to-a-batch-of-users)** 사용하여 사용자에게 직접 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="8aec7-119">한 때 최대 5,000명까지 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="8aec7-120">사용자가 5,000명 이상인 경우 여러 일괄 처리를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="8aec7-121">이 방법을 사용하면 새 사용자가 있는 경우 일괄 처리 할당을 다시 실행하여 해당 새 사용자에게 정책을 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="8aec7-122">Teams에서 사용자는 사용자 지정 정책을 만들고 할당하지 않는 한 Teams 정책 유형에 대한 전역(전체 기본) 정책을 자동으로 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="8aec7-123">학생 인구는 종종 가장 큰 사용자 집합이기 때문에 가장 제한적인 설정을 받는 경우가 종종 있기 때문에 다음을 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="8aec7-124">비공개 채팅 및 모임 예정과 같은 핵심 기능을 허용하는 사용자 지정 정책을 만들고 교직원 및 강사에게 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="8aec7-125">교직원 및 강사에게 사용자 지정 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="8aec7-126">전역(전체 기본) 정책을 편집하고 적용하여 학생의 기능을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="8aec7-127">전역 정책은 사용자 지정 정책을 만들고 교직원 및 강사에게 할당할 때까지 학교의 모든 사용자에게 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="8aec7-128">이 자습서에서는 학생에게 전역 모임 정책을 적용하고 강사 및 강사에게 EducatorMeetingPolicy라는 사용자 지정 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="8aec7-129">학생을 위한 모임 설정을 조정하고 교직원 및 [](policy-packages-edu.md) 강사에 대한 모임 환경을 정의하는 사용자 지정 정책을 만들었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![Teams 관리 센터의 모임 정책 페이지의 스크린샷](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="8aec7-131">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8aec7-131">Assign a policy to a group</span></span>

<span data-ttu-id="8aec7-132">다음 단계에 따라 교직원 및 강사에 대한 보안 그룹을 만든 다음, 해당 보안 그룹에 EducatorMeetingPolicy라는 사용자 지정 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="8aec7-133">시작하기 전</span><span class="sxs-lookup"><span data-stu-id="8aec7-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8aec7-134">그룹에 정책을 할당하면 우선 순위 규칙에 따라 정책 할당이 그룹의 구성원에게 전파됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="8aec7-135">예를 들어 사용자에게 개별적으로 또는 일괄 처리 할당을 통해 직접 정책이 할당된 경우 해당 정책이 그룹에서 상속된 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="8aec7-136">즉, 사용자에게 직접 할당된 모임 정책이 있는 경우 보안 그룹에서 모임 정책을 상속하려면 먼저 사용자로부터 해당 모임 정책을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="8aec7-137">시작하기 전에 우선 순위 규칙 및 [](assign-policies.md#precedence-rules) 그룹 할당 순위를 [이해하는 것이 중요합니다.](assign-policies.md#group-assignment-ranking)</span><span class="sxs-lookup"><span data-stu-id="8aec7-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="8aec7-138">그룹에 정책 할당에 대해 알아야 할 개념을 읽고 **[이해해야 합니다.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**</span><span class="sxs-lookup"><span data-stu-id="8aec7-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="8aec7-139">교직원과 강사는 보안 그룹에서 모임 정책을 상속받기 위해 이러한 모든 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="8aec7-140">[보안 그룹을 만들 수 있습니다.](#create-security-groups)</span><span class="sxs-lookup"><span data-stu-id="8aec7-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="8aec7-141">[보안 그룹에 정책을 할당합니다.](#assign-a-policy-to-a-security-group)</span><span class="sxs-lookup"><span data-stu-id="8aec7-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="8aec7-142">[사용자에게 직접 할당된 정책을 제거합니다.](#remove-a-policy-that-was-directly-assigned-to-users)</span><span class="sxs-lookup"><span data-stu-id="8aec7-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="8aec7-143">보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="8aec7-143">Create security groups</span></span>

<span data-ttu-id="8aec7-144">먼저 교직원 및 강사에 대한 보안 그룹을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="8aec7-145">SDS(School [Data Sync)를](https://docs.microsoft.com/SchoolDataSync/) 사용하면 학교에서 보안 그룹 [강사](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) 및 학생을 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-145">With [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="8aec7-146">SDS를 사용하여 학교에 대한 정책을 관리하는 데 필요한 보안 그룹을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="8aec7-147">사용자 환경 내에서 SDS를 배포할 수 없는 경우 이 [PowerShell](scripts/powershell-script-security-groups-edu.md) 스크립트를 사용하여 교직원 라이선스가 할당된 모든 교직원 및 강사와 학생 라이선스가 할당된 모든 학생에 대해 하나씩 두 개의 보안 그룹을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="8aec7-148">그룹을 최신으로 최신으로 유지하려면 이 스크립트를 정기적으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="8aec7-149">보안 그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8aec7-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="8aec7-150">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="8aec7-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="8aec7-151">현재 Microsoft Teams 관리 센터를 사용하는 그룹에 대한 정책 할당은 Teams 통화 정책, Teams 호출 공원 정책, Teams 정책, Teams 라이브 이벤트 정책, Teams 모임 정책 및 Teams 메시징 정책에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="8aec7-152">다른 정책 형식의 경우 PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="8aec7-153">Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 모임 모임  >  **정책으로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="8aec7-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="8aec7-154">그룹 **정책 할당 탭을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="8aec7-155">그룹 **추가를 선택하고** 그룹 창에 정책 할당 **창에서** 다음을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![모임 정책을 보여 주며 설정 편집 창의 스크린샷](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="8aec7-157">그룹 **선택 상자에서** 교직원 및 강사들이 포함된 보안 그룹을 검색하고 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="8aec7-158">순위 **선택 상자에** **1을 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="8aec7-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="8aec7-159">정책 **선택 상자에서** **EducatorMeetingPolicy를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8aec7-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="8aec7-160">적용을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8aec7-160">Select **Apply**.</span></span>

<span data-ttu-id="8aec7-161">그룹 정책 할당을 제거하려면  정책 페이지의 그룹 정책 할당 탭에서 그룹 할당을 선택한 다음 제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="8aec7-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="8aec7-162">그룹 할당의 순위를 변경하려면 먼저 그룹 정책 할당을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="8aec7-163">그런 다음 위의 단계에 따라 그룹에 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="8aec7-164">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8aec7-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="8aec7-165">현재 PowerShell을 사용하는 그룹에 대한 정책 할당은 모든 Teams 정책 유형에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="8aec7-166">지원되는 정책 유형 목록은 [New-CsGroupPolicyAssignment를](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8aec7-166">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="8aec7-167">Microsoft Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="8aec7-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="8aec7-168">다음을 실행하여 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 모듈(아직 설치되지 않은 경우)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="8aec7-169">버전 1.0.5 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="8aec7-170">다음을 실행하여 Teams에 연결하고 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="8aec7-171">메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="8aec7-172">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8aec7-172">Assign a policy to a group</span></span>

<span data-ttu-id="8aec7-173">다음을 실행하여 교직원 및 교육자를 포함하는 보안 그룹에 EducatorMeetingPolicy라는 모임 정책을 할당하고 할당 순위를 1로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="8aec7-174">개체 ID, SIP(세션 시작 프로토콜) 주소 또는 전자 메일 주소를 사용하여 보안 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="8aec7-175">이 예제에서는 전자 메일 주소(staff-faculty@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8aec7-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="8aec7-176">사용자에게 직접 할당된 정책 제거</span><span class="sxs-lookup"><span data-stu-id="8aec7-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="8aec7-177">사용자에게 정책이 직접 할당된 경우(개별적으로 또는 일괄 처리 할당을 통해) 해당 정책이 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="8aec7-178">즉, 사용자에게 직접 할당된 모임 정책이 있는 경우 보안 그룹에서 모임 정책을 상속하려면 먼저 사용자로부터 해당 모임 정책을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="8aec7-179">자세한 내용은 그룹에 정책 할당에 대해 [알아야 할 내용을 참조합니다.](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)</span><span class="sxs-lookup"><span data-stu-id="8aec7-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="8aec7-180">다음 단계에 따라 교직원 및 교육자에 직접 할당된 모임 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="8aec7-181">Microsoft Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="8aec7-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="8aec7-182">다음을 실행하여 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 모듈(아직 설치되지 않은 경우)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="8aec7-183">버전 1.0.5 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="8aec7-184">다음을 실행하여 Teams에 연결하고 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="8aec7-185">메시지가 표시될 때 Azure AD에 연결하는 데 사용한 동일한 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="8aec7-186">사용자에게 직접 할당된 정책 할당을 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="8aec7-187">다음을 실행하여 해당 정책이 직접 할당된 사용자로부터 모임 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="8aec7-188">전자 메일 주소 또는 개체 ID로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="8aec7-189">이 예제에서는 전자 메일 주소로 지정된 사용자에서 모임 정책이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="8aec7-190">이 예제에서는 모임 정책이 사용자 목록에서 사용자 이름의 텍스트 파일에서 user_ids.txt.</span><span class="sxs-lookup"><span data-stu-id="8aec7-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span>

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="8aec7-191">그룹에 대한 정책 할당을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-191">Get policy assignments for a group</span></span>

<span data-ttu-id="8aec7-192">다음을 실행하여 특정 보안 그룹에 할당된 모든 정책을 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="8aec7-193">정책을 할당하는 데 SIP 주소 또는 전자 메일 주소가 사용된 경우에도 그룹은 항상 그룹 ID로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-193">Note that groups are always listed by their group ID even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="8aec7-194">사용자에게 할당된 정책 얻기</span><span class="sxs-lookup"><span data-stu-id="8aec7-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="8aec7-195">다음을 실행하여 특정 사용자에게 할당된 모든 정책을 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="8aec7-196">다음 예제에서는 해당 정책에 할당된 정책을 reda@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8aec7-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="8aec7-197">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8aec7-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="8aec7-198">다음 단계에 따라 교직원 및 강사에게 강사에게 직접 EducatorMeetingPolicy라는 사용자 지정 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8aec7-199">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8aec7-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="8aec7-200">Graph 모듈 및 Teams PowerShell 모듈용 Azure AD PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="8aec7-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="8aec7-201">이 문서의 단계를 수행하기 전에 Azure AD PowerShell for Graph 모듈(할당된 라이선스로 사용자를 식별하기 위해) 및 Microsoft Teams PowerShell 모듈(해당 사용자에게 정책을 할당하기 위해)을 설치하고 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="8aec7-202">Graph 모듈용 Azure AD PowerShell 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="8aec7-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="8aec7-203">관리자 권한 Windows PowerShell 명령 프롬프트를 Windows PowerShell 관리자 권한으로 실행한 다음, 다음을 실행하여 Graph용 Azure Active Directory PowerShell을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="8aec7-204">다음을 실행하여 Azure AD에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="8aec7-205">메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="8aec7-206">자세한 내용은 [Graph 모듈용 Azure Active Directory PowerShell을 사용하여 연결을 참조하세요.](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="8aec7-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="8aec7-207">Microsoft Teams PowerShell 모듈 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="8aec7-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="8aec7-208">다음을 실행하여 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 모듈(아직 설치되지 않은 경우)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="8aec7-209">버전 1.0.5 이상을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="8aec7-210">다음을 실행하여 Teams에 연결하고 세션을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="8aec7-211">메시지가 표시될 때 Azure AD에 연결하는 데 사용한 동일한 관리자 자격 증명을 사용하여 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="8aec7-212">사용자 식별</span><span class="sxs-lookup"><span data-stu-id="8aec7-212">Identify your users</span></span>

<span data-ttu-id="8aec7-213">먼저 다음을 실행하여 라이선스 유형별로 교직원 및 교육자를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="8aec7-214">이렇게 하여 조직에서 사용 중인 SKUS를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="8aec7-215">그런 다음 교직원 SKU가 할당된 교직원 및 강사들을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="8aec7-216">반환되는 사항:</span><span class="sxs-lookup"><span data-stu-id="8aec7-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="8aec7-217">이 예제에서 출력은 교직원 라이선스 SkuId가 "e97c048c-37a4-45fb-ab50-922fbf07a370"입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="8aec7-218">Education SKU 및 SKU의 목록을 표시하는 경우 [Education SKU 참조를 참조하세요.](sku-reference-edu.md)</span><span class="sxs-lookup"><span data-stu-id="8aec7-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="8aec7-219">다음으로, 다음을 실행하여 이 라이선스가 있는 사용자를 식별하고 모두 함께 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="8aec7-220">대량으로 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8aec7-220">Assign a policy in bulk</span></span>

<span data-ttu-id="8aec7-221">이제 사용자에게 적절한 정책을 대량으로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="8aec7-222">정책을 할당하거나 업데이트할 수 있는 최대 사용자 수는 한 때 5,000명입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="8aec7-223">예를 들어 직원과 강사 수가 5,000명을 넘을 경우 여러 일괄 처리를 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="8aec7-224">다음을 실행하여 교직원 및 강사에게 EducatorMeetingPolicy라는 사용자 지정 모임 정책을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="8aec7-225">TeamsMessagingPolicy와 같은 다른 정책 유형을 대량으로 할당하려면 할당하는 정책 및 정책 이름으로 ```PolicyType``` ```PolicyName``` 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="8aec7-226">대량 할당의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="8aec7-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="8aec7-227">각 대량 할당은 정책 할당의 진행률을 추적하거나 발생할 수 있는 모든 실패를 식별하는 데 사용할 수 있는 작업 ID를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="8aec7-228">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="8aec7-229">일괄 처리 작업에서 각 사용자의 할당 상태를 확인하도록 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="8aec7-230">각 사용자의 세부 정보는 속성에 ```UserState``` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="8aec7-231">사용자가 5,000명 이상인 경우 대량으로 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8aec7-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="8aec7-232">먼저 다음을 실행하여 현재 직원 및 강사 수를 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="8aec7-233">전체 사용자 ID 목록을 제공하는 대신 다음을 실행하여 처음 5,000개, 다음 5,000개 등도 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="8aec7-234">전체 사용자 목록에 도달할 때까지 사용자 ID 범위를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="8aec7-235">예를 들어 첫 번째 일괄 처리에 입력하고, 두 번째 일괄 처리에 사용하며, 세 번째 일괄 처리를 입력하는 ```$faculty[0..4999``` ```$faculty[5000..9999``` ```$faculty[10000..14999``` 등입니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="8aec7-236">사용자에게 할당된 정책 얻기</span><span class="sxs-lookup"><span data-stu-id="8aec7-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="8aec7-237">다음을 실행하여 특정 사용자에게 할당된 모든 정책을 봐야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8aec7-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="8aec7-238">다음 예제에서는 해당 정책에 할당된 정책을 hannah@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="8aec7-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="8aec7-239">FAQ</span><span class="sxs-lookup"><span data-stu-id="8aec7-239">FAQ</span></span>

<span data-ttu-id="8aec7-240">**Teams용 PowerShell에 대해 잘 모르는 경우 자세한 내용은 어디에서 볼 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="8aec7-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="8aec7-241">PowerShell을 사용하여 Teams를 관리하는 개요는 [Teams PowerShell 개요를 참조하세요.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="8aec7-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="8aec7-242">이 문서에 사용된 cmdlet에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8aec7-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="8aec7-243">New-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="8aec7-243">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="8aec7-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="8aec7-244">Get-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="8aec7-245">New-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="8aec7-245">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="8aec7-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="8aec7-246">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="8aec7-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="8aec7-247">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="8aec7-248">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8aec7-248">Related topics</span></span>

- [<span data-ttu-id="8aec7-249">사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="8aec7-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="8aec7-250">교육용 Teams 정책 및 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="8aec7-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="8aec7-251">Teams에서 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="8aec7-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
