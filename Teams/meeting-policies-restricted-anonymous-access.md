---
title: 사용자에서 RestrictedAnonymousAccess Teams 모임 정책 제거
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: 조직의 사용자에서 RestrictedAnonymousAccess Teams 모임 정책을 제거하는 방법을 배워야 합니다.
ms.openlocfilehash: 55385cdd47f6b6c9882f8d4e8dcadc848f13755d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806258"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="a0d8e-103">사용자에서 RestrictedAnonymousAccess Teams 모임 정책 제거</span><span class="sxs-lookup"><span data-stu-id="a0d8e-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="a0d8e-104">Microsoft [Teams의](meeting-policies-in-teams.md) 모임 정책은 조직의 사용자가 예약한 모임에 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="a0d8e-105">Teams에는 익명 사용자의 모임 시작을 제한하는 미리 정의된 설정이 포함된 RestrictedAnonymousAccess라는 기본 제공 정책이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="a0d8e-106">(익명 사용자는 인증되지 않은 사용자입니다.) 모임 정책에서 미리 정의한 설정은 관리자가 편집하거나 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="a0d8e-107">이 문서에서는 PowerShell을 사용하여 이 정책이 할당된 사용자에서 RestrictedAnonymousAccess 모임 정책을 제거하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="a0d8e-108">PowerShell을 사용하여 Teams를 관리하는 방법에 대한 자세한 내용은 [Teams PowerShell 개요를 참조하세요.](teams-powershell-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a0d8e-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="a0d8e-109">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="a0d8e-109">Before you start</span></span>

<span data-ttu-id="a0d8e-110">비즈니스용 Skype [PowerShell 모듈을 설치하고 연결합니다.](https://www.microsoft.com/download/details.aspx?id=39366)</span><span class="sxs-lookup"><span data-stu-id="a0d8e-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="a0d8e-111">단계별 지침은 [Microsoft Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="a0d8e-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="a0d8e-112">조직의 Teams 모임 정책 할당을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="a0d8e-113">다음을 실행하여 조직의 Teams 모임 정책 할당을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="a0d8e-114">이 예제에서는 두 사용자에게 RestrictedAnonymousAccess 모임 정책이 할당된 다음 출력이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="a0d8e-115">사용자로부터 RestrictedAnonymous 모임 정책의 재할당을 확정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="a0d8e-116">사용자로부터 RestrictedAnonymous 모임 정책을 제거하려면 적은 수의 사용자(예: 100명 미만)가 있는 경우 [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="a0d8e-117">많은 수의 사용자(예: 100명 이상의 사용자)가 있는 경우  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet을 사용하여 일괄 처리 작업을 제출하는 것이 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="a0d8e-118">Grant-CsTeamsMeeting Policy cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="a0d8e-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="a0d8e-119">다음을 실행하여 사용자로부터 RestrictedAnonymous 모임 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="a0d8e-120">New-CsBatchPolicyAssignmentOperation cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="a0d8e-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="a0d8e-121">일괄 처리 [정책 할당을](assign-policies.md#assign-a-policy-to-a-batch-of-users)사용하면 정책을 제거하거나 업데이트할 수 있는 최대 사용자 수는 한 때 5,000명입니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="a0d8e-122">예를 들어 사용자가 5,000명 이상인 경우 여러 일괄 처리를 제출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="a0d8e-123">최상의 결과를 위해 한 번에 여러 일괄 처리를 제출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="a0d8e-124">더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="a0d8e-125">[New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet은 Teams PowerShell 모듈에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="a0d8e-126">다음 단계를 수행하기 전에 Teams [PowerShell 모듈을 설치하고 연결합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams)</span><span class="sxs-lookup"><span data-stu-id="a0d8e-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="a0d8e-127">단계별 지침은 [Microsoft Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="a0d8e-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="a0d8e-128">다음 명령을 실행하여 사용자 일괄 처리에서 RestrictedAnonymousAccess 모임 정책을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="a0d8e-129">일괄 처리 할당의 상태 확인</span><span class="sxs-lookup"><span data-stu-id="a0d8e-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="a0d8e-130">각 일괄 처리 할당은 작업 ID를 반환합니다. 이 ID는 할당의 진행률 및 상태를 추적하고 발생할 수 있는 모든 실패를 식별하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="a0d8e-131">예를 들어 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a0d8e-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="a0d8e-132">**ErrorCount가** **0이고** **OverallStatus가** **완료된지 확인**</span><span class="sxs-lookup"><span data-stu-id="a0d8e-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a0d8e-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a0d8e-133">Related topics</span></span>

- [<span data-ttu-id="a0d8e-134">Teams에서 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="a0d8e-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="a0d8e-135">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="a0d8e-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="a0d8e-136">Teams에서 사용자에게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="a0d8e-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
