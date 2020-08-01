---
title: 학교에서 대규모 사용자 집합에 정책 할당
author: lanachin
ms.author: v-lanac
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
description: 그룹 구성원 자격을 기준으로 또는 원격 school (teleschool, tele) 용도의 일괄 처리를 통해 직접 교육 기관에 정책을 할당 하는 방법에 대해 알아봅니다.
f1keywords: ''
ms.openlocfilehash: 0b4fd804b51fef9537d30230aed400bb0cb7e0aa
ms.sourcegitcommit: dc3e8ae454c42981f037f4de2e48005428b6078e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46534132"
---
# <a name="assign-policies-to-large-sets-of-users-in-your-school"></a><span data-ttu-id="4190d-103">학교에서 대규모 사용자 집합에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4190d-103">Assign policies to large sets of users in your school</span></span>

> [!NOTE]
> <span data-ttu-id="4190d-104">Microsoft 팀의 정책 할당에 대 한 자세한 내용은 [팀에서 사용자에 게 정책 할당](assign-policies.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-104">For the larger story on assigning policies in Microsoft Teams, see [Assign policies to your users in Teams](assign-policies.md).</span></span>

## <a name="overview"></a><span data-ttu-id="4190d-105">개요</span><span class="sxs-lookup"><span data-stu-id="4190d-105">Overview</span></span>

<span data-ttu-id="4190d-106">학생 및 교사에 게 Microsoft 팀의 다양 한 기능에 대 한 액세스 권한이 필요 한가요?</span><span class="sxs-lookup"><span data-stu-id="4190d-106">Do you need to give your students and educators access to different features in Microsoft Teams?</span></span> <span data-ttu-id="4190d-107">라이선스 유형을 기준으로 조직의 사용자를 빠르게 식별 한 다음 적절 한 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-107">You can quickly identify the users in your organization by license type and then assign them the appropriate policy.</span></span> <span data-ttu-id="4190d-108">이 자습서에서는 학교에서 대규모 사용자 집합에 모임 정책을 할당 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-108">This tutorial shows you how to assign a meeting policy to large sets of users in your school.</span></span> <span data-ttu-id="4190d-109">Microsoft 팀 관리 센터 및 PowerShell을 사용 하 여 정책을 할당할 수 있으며, 두 가지 방법 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-109">You can assign policies using the Microsoft Teams admin center and PowerShell and we'll show you both ways.</span></span>

<span data-ttu-id="4190d-110">사용자가 구성원 인 보안 그룹 또는 일괄 처리 정책 할당을 통해 확장할 때 사용자에 게 직접 모임 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-110">You can assign a meeting policy to a security group that the users are members of or directly to users at scale through a batch policy assignment.</span></span> <span data-ttu-id="4190d-111">다음을 수행 하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-111">You'll learn how to:</span></span>

- <span data-ttu-id="4190d-112">\*\* [그룹에 정책 할당](#assign-a-policy-to-a-group) 을 사용 하 여 보안 그룹에 모임 정책을 할당 합니다 (권장)\*\*.</span><span class="sxs-lookup"><span data-stu-id="4190d-112">**Use [policy assignment to groups](#assign-a-policy-to-a-group) to assign a meeting policy to a security group (recommended)**.</span></span> <span data-ttu-id="4190d-113">이 방법을 사용 하면 그룹 구성원을 기준으로 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-113">This method lets you assign a policy based on group membership.</span></span> <span data-ttu-id="4190d-114">보안 그룹 또는 배포 목록에 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-114">You can assign a policy to a security group or distribution list.</span></span> <span data-ttu-id="4190d-115">그룹에서 구성원이 추가 되거나 제거 되 면 그에 따라 상속 된 정책 할당이 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-115">As members are added to or removed from the group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="4190d-116">이 방법은 새 사용자에 대 한 정책을 관리 하는 시간을 단축 하거나 사용자의 역할이 변경 되는 경우를 위해 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-116">We recommend you use this method because it reduces the time to manage policies for new users or when users' roles change.</span></span> <span data-ttu-id="4190d-117">이 방법은 최대 5만 사용자를 대상으로 하는 그룹에 가장 적합 하지만 대형 그룹과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-117">This method works best for groups of up to 50,000 users but will also work with larger groups.</span></span>

- <span data-ttu-id="4190d-118">\*\* [일괄 처리 정책 할당](assign-policies.md#assign-a-policy-to-a-batch-of-users) 을 사용 하 여 모임 정책을 사용자에 게 직접 대량으로 할당\*\*합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-118">**Use [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users) to assign a meeting policy directly to users in bulk**.</span></span> <span data-ttu-id="4190d-119">한 번에 최대 5000 명의 사용자에 대 한 정책을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-119">You can assign a policy for up to 5,000 users at a time.</span></span> <span data-ttu-id="4190d-120">5000 명 이상의 사용자가 있는 경우 여러 일괄 처리를 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-120">If you have more than 5,000 users, you can submit multiple batches.</span></span> <span data-ttu-id="4190d-121">이 방법을 사용 하면 새 사용자가 있는 경우 일괄 처리 할당을 다시 실행 하 여 정책을 해당 새 사용자에 게 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-121">With this method, when you have new users, you'll need to re-run the batch assignment to assign the policy to those new users.</span></span>

<span data-ttu-id="4190d-122">사용자 지정 정책을 만들고 할당 하지 않는 한 팀에서 팀 정책 유형의 전역 (조직 차원의 기본) 정책을 자동으로 얻을 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-122">Remember that in Teams, users automatically get the Global (Org-wide default) policy for a Teams policy type unless you create and assign a custom policy.</span></span> <span data-ttu-id="4190d-123">학생 집단은 일반적으로 가장 큰 사용자 집합 이므로 가장 제한적인 설정을 받을 수 있으므로 다음을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-123">Because the student population is often the largest set of users and they often receive the most restrictive settings, we recommend that you do the following:</span></span>

- <span data-ttu-id="4190d-124">개인 채팅 및 모임 예약과 같은 핵심 기능을 허용 하는 사용자 지정 정책을 만들어 교직원 및 교육자에 게 정책을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-124">Create a custom policy that allows core capabilities such as private chat and meeting scheduling and assign the policy to your staff and educators.</span></span>
- <span data-ttu-id="4190d-125">사용자 지정 정책을 직원과 교육자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-125">Assign the custom policy to your staff and educators.</span></span>
- <span data-ttu-id="4190d-126">전역 (조직 전체 기본값) 정책을 편집 하 고 적용 하 여 학생에 대 한 접근 권한 제한</span><span class="sxs-lookup"><span data-stu-id="4190d-126">Edit and apply the Global (Org-wide default) policy to restrict capabilities for students.</span></span>

<span data-ttu-id="4190d-127">사용자 지정 정책을 만들어 교직원과 교육자에 게 배정할 때까지 해당 학교의 모든 사용자에 게 전역 정책이 적용 된다는 점을 기억 하세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-127">Keep in mind that the Global policy will apply to all users in your school until you create a custom policy and assign it to your staff and educators.</span></span>

<span data-ttu-id="4190d-128">이 자습서에서 학생 들은 전역 모임 정책을 받게 되며 EducatorMeetingPolicy 이라는 사용자 지정 모임 정책을 교직원 및 교육자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-128">In this tutorial, students will get the Global meeting policy and we'll assign a custom meeting policy named EducatorMeetingPolicy to staff and educators.</span></span> <span data-ttu-id="4190d-129">학생에 대 한 모임 설정을 조정 하 고 교직원 및 교사를 위한 모임 환경을 정의 하는 [사용자 지정 정책을 만드는](policy-packages-edu.md) 전역 정책을 편집 했다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-129">We assume that you've edited the Global policy to tailor meeting settings for students and [created a custom policy](policy-packages-edu.md) that defines the meeting experience for staff and educators.</span></span>

![팀 관리 센터의 모임 정책 페이지 스크린샷](media/batch-group-policy-assignment-edu-meeting-policies.png)

## <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="4190d-131">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4190d-131">Assign a policy to a group</span></span>

<span data-ttu-id="4190d-132">다음 단계에 따라 직원과 교육자에 대 한 보안 그룹을 만든 다음 EducatorMeetingPolicy 이라는 사용자 지정 모임 정책을 해당 보안 그룹에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-132">Follow these steps to create a security group for your staff and educators, and then assign a custom meeting policy named EducatorMeetingPolicy to that security group.</span></span>

### <a name="before-you-get-started"></a><span data-ttu-id="4190d-133">시작하기 전</span><span class="sxs-lookup"><span data-stu-id="4190d-133">Before you get started</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4190d-134">그룹에 정책을 할당 하면 우선 순위 규칙에 따라 정책 할당이 그룹의 구성원에 게 전파 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-134">When you assign a policy to a group, the policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="4190d-135">예를 들어 사용자에 게 정책 (개별적으로 또는 일괄 할당을 통해)을 직접 할당 한 경우 해당 정책은 그룹에서 상속 된 정책 보다 우선적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-135">For example, if a user is directly assigned a policy (either individually or through a batch assignment), that policy takes precedence over a policy that's inherited from a group.</span></span> <span data-ttu-id="4190d-136">또한 사용자에 게 직접 할당 된 모임 정책이 있는 경우 사용자가 해당 모임 정책을 제거 해야 보안 그룹에서 모임 정책을 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-136">This also means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="4190d-137">시작 하기 전에 [우선 순위 규칙](assign-policies.md#precedence-rules) 및 [그룹 배정 순위](assign-policies.md#group-assignment-ranking)를 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-137">Before you get started, it's important to understand [precedence rules](assign-policies.md#precedence-rules) and [group assignment ranking](assign-policies.md#group-assignment-ranking).</span></span> <span data-ttu-id="4190d-138">\*\* [그룹에 대 한 정책 할당에 대해 알아야 할](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)개념을 읽고 이해\*\*해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-138">**Make sure that you read and understand the concepts in [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)**.</span></span>

<span data-ttu-id="4190d-139">교직원과 교육자는 보안 그룹에서 모임 정책을 상속 받도록 모든 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-139">You'll need to complete all these steps for your staff and educators to inherit a meeting policy from a security group.</span></span>

1. <span data-ttu-id="4190d-140">[보안 그룹을 만듭니다](#create-security-groups).</span><span class="sxs-lookup"><span data-stu-id="4190d-140">[Create security groups](#create-security-groups).</span></span>
2. <span data-ttu-id="4190d-141">[보안 그룹에 정책을 할당](#assign-a-policy-to-a-security-group)합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-141">[Assign a policy to a security group](#assign-a-policy-to-a-security-group).</span></span>
3. <span data-ttu-id="4190d-142">[사용자에 게 직접 할당 된 정책을 제거](#remove-a-policy-that-was-directly-assigned-to-users)합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-142">[Remove a policy that was directly assigned to users](#remove-a-policy-that-was-directly-assigned-to-users).</span></span>

### <a name="create-security-groups"></a><span data-ttu-id="4190d-143">보안 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="4190d-143">Create security groups</span></span>

<span data-ttu-id="4190d-144">먼저 직원과 교육자를 위한 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-144">First, create a security group for your staff and educators.</span></span>

<span data-ttu-id="4190d-145">SDS ( [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) )를 사용 하 여 학교에서 [보안 그룹 교육자 및 학생을 쉽게 만들](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-145">With [School Data Sync](https://docs.microsoft.com/SchoolDataSync/) (SDS), you can [easily create security groups educators and students](https://docs.microsoft.com/SchoolDataSync/edu-security-groups) in your school.</span></span> <span data-ttu-id="4190d-146">SDS를 사용 하 여 정책을 관리 하는 데 필요한 보안 그룹을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-146">We recommend that you use SDS to create the security groups you need to manage policies for your school.</span></span>

<span data-ttu-id="4190d-147">환경 내에 SDS를 배포할 수 없는 경우 [이 PowerShell 스크립트](scripts/powershell-script-security-groups-edu.md) 를 사용 하 여 두 개의 보안 그룹을 만들고, 교직원 라이선스를 할당 받은 모든 직원과 강사와 학생 라이선스가 할당 된 모든 학생에 게 각각에 대해 하나씩을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-147">If you're unable to deploy SDS within your environment, use [this PowerShell script](scripts/powershell-script-security-groups-edu.md) to create two security groups, one for all staff and educators who have a Faculty license assigned and another for all students who have a Student license assigned.</span></span> <span data-ttu-id="4190d-148">그룹을 최신 상태로 유지 하려면이 스크립트를 정기적으로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-148">You'll need to run this script routinely to keep the groups fresh and up to date.</span></span>

### <a name="assign-a-policy-to-a-security-group"></a><span data-ttu-id="4190d-149">보안 그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4190d-149">Assign a policy to a security group</span></span>

#### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="4190d-150">Microsoft Teams 관리 센터 사용</span><span class="sxs-lookup"><span data-stu-id="4190d-150">Using the Microsoft Teams admin center</span></span>

> [!NOTE]
> <span data-ttu-id="4190d-151">현재 Microsoft 팀 관리 센터를 사용 하는 그룹에 대 한 정책 할당은 팀 호출 정책, 팀 통화 대기 정책, 팀 정책, 팀 live 이벤트 정책, 팀 모임 정책, 팀 메시징 정책에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-151">Currently, policy assignment to groups using the Microsoft Teams admin center is only available for Teams calling policy, Teams call park policy, Teams policy, Teams live events policy, Teams meeting policy, and Teams messaging policy.</span></span> <span data-ttu-id="4190d-152">다른 정책 유형의 경우 PowerShell을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-152">For other policy types, use PowerShell.</span></span>

1. <span data-ttu-id="4190d-153">Microsoft 팀 관리 센터의 왼쪽 탐색 창에서 **모임**  >  **모임 정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-153">In the left navigation of the Microsoft Teams admin center, go to **Meetings** > **Meeting policies**.</span></span>
2. <span data-ttu-id="4190d-154">**그룹 정책 할당** 탭을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-154">Select the **Group policy assignment** tab.</span></span>
3. <span data-ttu-id="4190d-155">**그룹 추가**를 선택 하 고 **그룹에 정책 할당** 창에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-155">Select **Add group**, and then in the **Assign policy to group** pane, do the following:</span></span>

    ![모임 정책이 표시 된 설정 편집 창의 스크린샷](media/batch-group-policy-assignment-edu-group.png)
    1. <span data-ttu-id="4190d-157">**그룹 선택** 상자에서 직원과 교사를 포함 하는 보안 그룹을 검색 하 여 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-157">In the **Select a group** box, search for and add the security group that contains your staff and educators.</span></span>
    2. <span data-ttu-id="4190d-158">**순위 선택** 상자에 **1**을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-158">In the **Select rank** box, enter **1**.</span></span>
    3. <span data-ttu-id="4190d-159">**정책 선택** 상자에서 **EducatorMeetingPolicy**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-159">In the **Select a policy** box, select **EducatorMeetingPolicy**.</span></span>
    4. <span data-ttu-id="4190d-160">**적용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-160">Select **Apply**.</span></span>

<span data-ttu-id="4190d-161">그룹 정책 할당을 제거 하려면 정책 페이지의 **그룹 정책 할당** 탭에서 그룹 할당을 선택한 다음 **제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-161">To remove a group policy assignment, on the **Group policy assignment** tab of the policy page, select the group assignment, and then select **Remove**.</span></span>

<span data-ttu-id="4190d-162">그룹 할당 순위를 변경 하려면 먼저 그룹 정책 할당을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-162">To change the ranking of a group assignment, you have to first remove the group policy assignment.</span></span> <span data-ttu-id="4190d-163">그런 다음 위의 단계에 따라 정책을 그룹에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-163">Then, follow the steps above to assign the policy to a group.</span></span>

#### <a name="using-powershell"></a><span data-ttu-id="4190d-164">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="4190d-164">Using PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="4190d-165">현재 모든 팀 정책 유형에는 PowerShell을 사용 하는 그룹에 대 한 정책 할당을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-165">Currently, policy assignment to groups using PowerShell isn't available for all Teams policy types.</span></span> <span data-ttu-id="4190d-166">지원 되는 정책 유형 목록에 대 한 [새 CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-166">See [New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) for the list of supported policy types.</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="4190d-167">Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-167">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="4190d-168">다음을 실행 하 여 [팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams) 을 설치 합니다 (아직 설치 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="4190d-168">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="4190d-169">버전 1.0.5 이상이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-169">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="4190d-170">다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-170">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="4190d-171">메시지가 표시 되 면 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-171">When you're prompted, sign in using your admin credentials.</span></span>

##### <a name="assign-a-policy-to-a-group"></a><span data-ttu-id="4190d-172">그룹에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4190d-172">Assign a policy to a group</span></span>

<span data-ttu-id="4190d-173">다음을 실행 하 여 EducatorMeetingPolicy 라는 모임 정책을 교직원 및 교육자가 포함 된 보안 그룹에 할당 하 고 과제 순위를 1로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-173">Run the following to assign the meeting policy named EducatorMeetingPolicy to the security group that contains your staff and educators and set the assignment ranking to 1.</span></span> <span data-ttu-id="4190d-174">개체 Id, SIP (세션 시작 프로토콜) 주소 또는 전자 메일 주소를 사용 하 여 보안 그룹을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-174">You can specify a security group by using the object Id, Session Initiation Protocol (SIP) address, or email address.</span></span> <span data-ttu-id="4190d-175">이 예제에서는 전자 메일 주소 (staff-faculty@contoso.com)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-175">In this example, we use an email address (staff-faculty@contoso.com).</span></span>

```powershell
New-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com -PolicyType TeamsMeetingPolicy -PolicyName "EducatorMeetingPolicy" -Rank 1
```

### <a name="remove-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="4190d-176">사용자에 게 직접 할당 된 정책 제거</span><span class="sxs-lookup"><span data-stu-id="4190d-176">Remove a policy that was directly assigned to users</span></span>

<span data-ttu-id="4190d-177">사용자가 정책을 직접 할당 하는 경우 (개별적으로 또는 일괄 할당을 통해) 해당 정책이 우선 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-177">Remember that if a user was directly assigned a policy (either individually or through a batch assignment), that policy takes precedence.</span></span> <span data-ttu-id="4190d-178">즉, 사용자에 게 직접 할당 된 모임 정책이 있는 경우 사용자가 해당 모임 정책을 제거 해야 보안 그룹에서 모임 정책을 상속할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-178">This means that if a user has a meeting policy that was directly assigned to them, you'll have to remove that meeting policy from the user before they can inherit a meeting policy from a security group.</span></span>

<span data-ttu-id="4190d-179">자세히 알아보려면 [그룹에 정책 할당에 대해 알아야 할 사항](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-179">To learn more, see [What you need to know about policy assignment to groups](assign-policies.md#what-you-need-to-know-about-policy-assignment-to-groups).</span></span>

<span data-ttu-id="4190d-180">다음 단계에 따라 직원과 교육자에 직접 할당 된 모임 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-180">Follow these steps to remove the meeting policy that was directly assigned to your staff and educators.</span></span>

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="4190d-181">Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-181">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="4190d-182">다음을 실행 하 여 [팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams) 을 설치 합니다 (아직 설치 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="4190d-182">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="4190d-183">버전 1.0.5 이상이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-183">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="4190d-184">다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-184">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="4190d-185">메시지가 표시 되 면 Azure AD에 연결 하는 데 사용한 것과 동일한 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-185">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="unassign-a-policy-that-was-directly-assigned-to-users"></a><span data-ttu-id="4190d-186">사용자에 게 직접 할당 된 정책 할당 취소</span><span class="sxs-lookup"><span data-stu-id="4190d-186">Unassign a policy that was directly assigned to users</span></span>

<span data-ttu-id="4190d-187">다음을 실행 하 여 해당 정책을 직접 할당 한 사용자에 게 서 모임 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-187">Run the following to remove a meeting policy from users who were directly assigned that policy.</span></span> <span data-ttu-id="4190d-188">전자 메일 주소 또는 개체 ID를 기준으로 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-188">You can specify users by email address or object ID.</span></span>

<span data-ttu-id="4190d-189">이 예제에서 모임 정책은 전자 메일 주소로 지정 된 사용자에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-189">In this example, the meeting policy is removed from users specified by their email address.</span></span>

```powershell
$users_ids = @("reda@contoso.com", "nikica@contoso.com", "jamie@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

<span data-ttu-id="4190d-190">이 예제에서 모임 정책은 user_ids.txt 라는 텍스트 파일의 사용자 목록에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-190">In this example, the meeting policy is removed from the list of users in a text file named user_ids.txt.</span></span> 

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $users_ids -OperationName "Unassign meeting policy"
```

##### <a name="get-policy-assignments-for-a-group"></a><span data-ttu-id="4190d-191">그룹에 대 한 정책 할당 가져오기</span><span class="sxs-lookup"><span data-stu-id="4190d-191">Get policy assignments for a group</span></span>

<span data-ttu-id="4190d-192">특정 보안 그룹에 지정 된 모든 정책을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-192">Run the following to see all the policies assigned to a specific security group.</span></span> <span data-ttu-id="4190d-193">그룹은 해당 SIP 주소 또는 전자 메일 주소가 정책을 할당 하는 데 사용 된 경우에도 그룹 Id에 의해 항상 나열 됨을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-193">Note that groups are always listed by their group Id even if its SIP address or email address was used to assign the policy.</span></span>

```powershell
Get-CsGroupPolicyAssignment -GroupId staff-faculty@contoso.com

```

##### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="4190d-194">사용자에 게 할당 된 정책 가져오기</span><span class="sxs-lookup"><span data-stu-id="4190d-194">Get the policies assigned to a user</span></span>

<span data-ttu-id="4190d-195">특정 사용자에 게 할당 된 모든 정책을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-195">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="4190d-196">다음 예에서는 reda@contoso.com에 할당 된 정책을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-196">The following example shows you how to get the policies that are assigned to reda@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity reda@contoso.com
```

## <a name="assign-a-policy-to-a-batch-of-users"></a><span data-ttu-id="4190d-197">사용자 일괄 처리에 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4190d-197">Assign a policy to a batch of users</span></span>

<span data-ttu-id="4190d-198">다음 단계에 따라 EducatorMeetingPolicy 이라는 사용자 지정 모임 정책을 교직원에 게 직접 할당 하 고 교사에 게 대량으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-198">Follow these steps to assign a custom meeting policy named EducatorMeetingPolicy directly to your staff and educators in bulk.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="4190d-199">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="4190d-199">Using PowerShell</span></span>

#### <a name="connect-to-the-azure-ad-powershell-for-graph-module-and-the-teams-powershell-module"></a><span data-ttu-id="4190d-200">Graph 모듈 및 팀 PowerShell 모듈에 대 한 Azure AD PowerShell에 연결</span><span class="sxs-lookup"><span data-stu-id="4190d-200">Connect to the Azure AD PowerShell for Graph module and the Teams PowerShell module</span></span>

<span data-ttu-id="4190d-201">이 문서의 단계를 수행 하기 전에 Graph 모듈에 대 한 Azure AD PowerShell을 설치 하 고 연결 (사용자에 게 할당 된 라이선스를 식별 하기 위해) 하 고 Microsoft 팀 PowerShell 모듈 (해당 사용자에 게 정책을 할당 해야 함) 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-201">Before you perform the steps in this article, you'll need to install and connect to the Azure AD PowerShell for Graph module (to identify users by their assigned licenses) and the Microsoft Teams PowerShell module (to assign the policies to those users).</span></span>

##### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module"></a><span data-ttu-id="4190d-202">Graph 모듈에 대 한 Azure AD PowerShell 설치 및 연결</span><span class="sxs-lookup"><span data-stu-id="4190d-202">Install and connect to the Azure AD PowerShell for Graph module</span></span>

<span data-ttu-id="4190d-203">관리자 권한으로 windows PowerShell 명령 프롬프트를 열고 (관리자로 Windows PowerShell 실행) 다음을 실행 하 여 Graph 모듈에 대 한 Azure Active Directory PowerShell을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-203">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator), and then run the following to install the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Install-Module -Name AzureAD
```

<span data-ttu-id="4190d-204">Azure AD에 연결 하려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-204">Run the following to connect to Azure AD.</span></span>

```powershell
Connect-AzureAD
```

<span data-ttu-id="4190d-205">메시지가 표시 되 면 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-205">When you're prompted, sign in using your admin credentials.</span></span>

<span data-ttu-id="4190d-206">자세한 내용은 [Graph 용 Azure Active Directory PowerShell 모듈을 사용 하 여 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-206">To learn more, see [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

##### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a><span data-ttu-id="4190d-207">Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-207">Install and connect to the Microsoft Teams PowerShell module</span></span>

<span data-ttu-id="4190d-208">다음을 실행 하 여 [팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams) 을 설치 합니다 (아직 설치 되지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="4190d-208">Run the following to install the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if it's not already installed).</span></span> <span data-ttu-id="4190d-209">버전 1.0.5 이상이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-209">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="4190d-210">다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-210">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```
<span data-ttu-id="4190d-211">메시지가 표시 되 면 Azure AD에 연결 하는 데 사용한 것과 동일한 관리자 자격 증명을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-211">When you're prompted, sign in using the same admin credentials you used to connect to Azure AD.</span></span>

#### <a name="identify-your-users"></a><span data-ttu-id="4190d-212">사용자 식별</span><span class="sxs-lookup"><span data-stu-id="4190d-212">Identify your users</span></span>

<span data-ttu-id="4190d-213">먼저 다음을 실행 하 여 라이선스 유형별로 교직원 및 교사를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-213">First, run the following to identify your staff and educators by license type.</span></span> <span data-ttu-id="4190d-214">조직에서 사용 중인 Sku를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-214">This tells you what SKUs are in use in your organization.</span></span> <span data-ttu-id="4190d-215">그런 다음 교직원 SKU가 지정 된 교직원 및 교사를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-215">You can then identify staff and educators that have a Faculty SKU assigned.</span></span>

```powershell
Get-AzureAdSubscribedSku | Select-Object -Property SkuPartNumber,SkuId
```

<span data-ttu-id="4190d-216">반환 되는 결과:</span><span class="sxs-lookup"><span data-stu-id="4190d-216">Which returns:</span></span>

```
SkuPartNumber      SkuId
-------------      -----
M365EDU_A5_FACULTY e97c048c-37a4-45fb-ab50-922fbf07a370
M365EDU_A5_STUDENT 46c119d4-0379-4a9d-85e4-97c66d3f909e
```

<span data-ttu-id="4190d-217">이 예제에서는 교직원 라이선스 SkuId "e97c048c-37a4-45fb-ab50-922fbf07a370" 라는 것을 출력에 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-217">In this example, the output shows that the Faculty license SkuId is "e97c048c-37a4-45fb-ab50-922fbf07a370".</span></span>

> [!NOTE]
> <span data-ttu-id="4190d-218">교육 Sku 및 SKU Id 목록을 보려면 [교육 sku 참조](sku-reference-edu.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-218">To see a list of Education SKUs and SKU IDs, see [Education SKU reference](sku-reference-edu.md).</span></span>

<span data-ttu-id="4190d-219">다음으로, 다음을 실행 하 여이 라이선스가 있는 사용자를 식별 하 고 함께 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-219">Next, we run the following to identify the users that have this license and collect them all together.</span></span>

```powershell
$faculty = Get-AzureADUser -All $true | Where-Object {($_.assignedLicenses).SkuId -contains "e97c048c-37a4-45fb-ab50-922fbf07a370"}
```

#### <a name="assign-a-policy-in-bulk"></a><span data-ttu-id="4190d-220">대량으로 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4190d-220">Assign a policy in bulk</span></span>

<span data-ttu-id="4190d-221">이제 사용자에 게 적절 한 정책을 대량으로 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-221">Now, we assign the appropriate policies to users in bulk.</span></span> <span data-ttu-id="4190d-222">정책을 할당 하거나 업데이트 하는 데 사용할 수 있는 최대 사용자 수는 한 번에 5000입니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-222">The maximum number of users for which you can assign or update policies is 5,000 at a time.</span></span> <span data-ttu-id="4190d-223">예를 들어 5000 개 이상의 직원과 교육자가 있는 경우 여러 일괄 처리를 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-223">For example, if you have more than 5,000 staff and educators, you'll need to submit multiple batches.</span></span>

<span data-ttu-id="4190d-224">다음을 실행 하 여 EducatorMeetingPolicy 이라는 사용자 지정 모임 정책을 교직원 및 교육자에 게 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-224">Run the following to assign a custom meeting policy named EducatorMeetingPolicy to your staff and educators.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty.ObjectId
```

> [!NOTE]
> <span data-ttu-id="4190d-225">TeamsMessagingPolicy와 같이 대량으로 다른 정책 유형을 할당 하려면 ```PolicyType``` 할당할 정책 및 ```PolicyName``` 정책 이름으로 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-225">To assign a different policy type in bulk, like TeamsMessagingPolicy, you'll need to change ```PolicyType``` to the policy that you're assigning and ```PolicyName``` to the policy name.</span></span>

#### <a name="get-the-status-of-a-bulk-assignment"></a><span data-ttu-id="4190d-226">대량 배정 상태 가져오기</span><span class="sxs-lookup"><span data-stu-id="4190d-226">Get the status of a bulk assignment</span></span>

<span data-ttu-id="4190d-227">각 대량 과제는 정책 할당의 진행률을 추적 하거나 발생할 수 있는 오류를 식별 하는 데 사용할 수 있는 작업 ID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-227">Each bulk assignment returns an operation ID, which you can use to track the progress of the policy assignments or identify any failures that might occur.</span></span> <span data-ttu-id="4190d-228">예를 들어 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-228">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | fl
```

<span data-ttu-id="4190d-229">일괄 작업에서 각 사용자의 할당 상태를 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-229">To view the assignment status of each user in the batch operation, run the following.</span></span> <span data-ttu-id="4190d-230">각 사용자에 대 한 세부 정보는 속성에 있습니다 ```UserState``` .</span><span class="sxs-lookup"><span data-stu-id="4190d-230">Details of each user are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 3964004e-caa8-4eb4-b0d2-7dd2c8173c8c | Select -ExpandProperty UserState
```

#### <a name="assign-a-policy-in-bulk-if-you-have-more-than-5000-users"></a><span data-ttu-id="4190d-231">5000 명 이상의 사용자가 있는 경우 대량으로 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4190d-231">Assign a policy in bulk if you have more than 5,000 users</span></span>

<span data-ttu-id="4190d-232">먼저 다음을 실행 하 여 보유 하 고 있는 교직원 및 강사 수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-232">First, run the following to see how many staff and educators you have:</span></span>

```powershell
$faculty.count
```

<span data-ttu-id="4190d-233">사용자 Id의 전체 목록을 제공 하는 대신 다음을 실행 하 여 첫 번째 5000을 지정 하 고 다음 5000 등</span><span class="sxs-lookup"><span data-stu-id="4190d-233">Instead of providing the whole list of user IDs, run the following to specify the first 5,000, and then the next 5,000, and so on.</span></span>

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName EducatorMeetingPolicy -Identity $faculty[0..19999].ObjectId
```

<span data-ttu-id="4190d-234">전체 사용자 목록에 도달할 때까지 사용자 Id의 범위를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-234">You can change the range of user IDs until you reach the full list of users.</span></span> <span data-ttu-id="4190d-235">예를 들어 첫 번째 일괄 처리를 입력 하 고 두 번째 일괄 처리에 대해 ```$faculty[0..4999``` ```$faculty[5000..9999``` , ```$faculty[10000..14999``` 세 번째 일괄 처리에 대해 enter 키를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-235">For example, enter ```$faculty[0..4999``` for the first batch, use ```$faculty[5000..9999``` for the second batch, enter ```$faculty[10000..14999``` for the third batch, and so on.</span></span>

#### <a name="get-the-policies-assigned-to-a-user"></a><span data-ttu-id="4190d-236">사용자에 게 할당 된 정책 가져오기</span><span class="sxs-lookup"><span data-stu-id="4190d-236">Get the policies assigned to a user</span></span>

<span data-ttu-id="4190d-237">특정 사용자에 게 할당 된 모든 정책을 보려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-237">Run the following to see all the policies that are assigned to a specific user.</span></span> <span data-ttu-id="4190d-238">다음 예에서는 hannah@contoso.com에 할당 된 정책을 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4190d-238">The following example shows you how to get the policies that are assigned to hannah@contoso.com.</span></span>

```powershell
Get-CsUserPolicyAssignment -Identity hannah@contoso.com
```

## <a name="faq"></a><span data-ttu-id="4190d-239">FAQ</span><span class="sxs-lookup"><span data-stu-id="4190d-239">FAQ</span></span>

<span data-ttu-id="4190d-240">**팀에 대 한 PowerShell에 익숙하지 않습니다. 자세한 내용은 어디에서 확인할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="4190d-240">**I'm not familiar with PowerShell for Teams. Where can I learn more?**</span></span>

<span data-ttu-id="4190d-241">PowerShell을 사용 하 여 팀을 관리 하는 방법에 대 한 개요는 [팀 powershell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-241">For an overview of using PowerShell to manage Teams, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span> <span data-ttu-id="4190d-242">이 문서에서 사용 되는 cmdlet에 대 한 자세한 내용은 다음을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4190d-242">For more information about the cmdlets used in this article, see:</span></span>

- [<span data-ttu-id="4190d-243">새-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="4190d-243">New-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)
- [<span data-ttu-id="4190d-244">Get-CsGroupPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="4190d-244">Get-CsGroupPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)
- [<span data-ttu-id="4190d-245">새로운 CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="4190d-245">New-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="4190d-246">Get-CsBatchPolicyAssignmentOperation</span><span class="sxs-lookup"><span data-stu-id="4190d-246">Get-CsBatchPolicyAssignmentOperation</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)
- [<span data-ttu-id="4190d-247">Get-CsUserPolicyAssignment</span><span class="sxs-lookup"><span data-stu-id="4190d-247">Get-CsUserPolicyAssignment</span></span>](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)

## <a name="related-topics"></a><span data-ttu-id="4190d-248">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4190d-248">Related topics</span></span>

- [<span data-ttu-id="4190d-249">사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="4190d-249">Assign policies to your users</span></span>](assign-policies.md)
- [<span data-ttu-id="4190d-250">교육용 팀 정책 및 정책 패키지</span><span class="sxs-lookup"><span data-stu-id="4190d-250">Teams policies and policy packages for Education</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="4190d-251">팀에서 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="4190d-251">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
