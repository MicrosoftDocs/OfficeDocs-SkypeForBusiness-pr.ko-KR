---
title: 사용자의 RestrictedAnonymousAccess 팀 모임 정책 제거
author: LanaChin
ms.author: v-lanac
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
description: 조직의 사용자가 RestrictedAnonymousAccess 팀 모임 정책을 제거 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640995"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a><span data-ttu-id="32f11-103">사용자의 RestrictedAnonymousAccess 팀 모임 정책 제거</span><span class="sxs-lookup"><span data-stu-id="32f11-103">Remove the RestrictedAnonymousAccess Teams meeting policy from users</span></span>

<span data-ttu-id="32f11-104">Microsoft 팀의 [모임 정책은](meeting-policies-in-teams.md) 조직의 사용자가 예약한 모임의 모임 참가자가 사용할 수 있는 기능을 제어 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-104">[Meeting policies](meeting-policies-in-teams.md) in Microsoft Teams are used to control the features that are available to meeting participants for meetings that are scheduled by users in your organization.</span></span> 

<span data-ttu-id="32f11-105">팀에는 익명 사용자가 모임을 시작 하지 못하도록 제한 하는 미리 정의 된 설정이 포함 된 기본 제공 정책 RestrictedAnonymousAccess이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-105">Teams includes a built-in policy named RestrictedAnonymousAccess, which contains pre-defined settings that include restricting anonymous users from starting a meeting.</span></span> <span data-ttu-id="32f11-106">(익명 사용자는 인증 되지 않은 사용자입니다.) 모임 정책의 미리 정의 된 설정은 관리자가 편집 하거나 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-106">(Anonymous users are users who haven't been authenticated.) The predefined settings in the meeting policy can't be edited or changed by admins.</span></span>

<span data-ttu-id="32f11-107">이 문서에서는 PowerShell을 사용 하 여이 정책을 할당 한 사용자의 RestrictedAnonymousAccess 모임 정책을 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-107">This article shows you how to use PowerShell to remove the RestrictedAnonymousAccess meeting policy from users who are assigned this policy.</span></span> <span data-ttu-id="32f11-108">PowerShell을 사용 하 여 팀을 관리 하는 방법에 대해 자세히 알아보려면 [팀 powershell 개요](teams-powershell-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32f11-108">To learn more about how to manage Teams using PowerShell, see [Teams PowerShell overview](teams-powershell-overview.md).</span></span>

## <a name="before-you-start"></a><span data-ttu-id="32f11-109">시작 하기 전에</span><span class="sxs-lookup"><span data-stu-id="32f11-109">Before you start</span></span>

<span data-ttu-id="32f11-110">[비즈니스용 Skype PowerShell 모듈](https://www.microsoft.com/download/details.aspx?id=39366)을 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-110">Install and connect to the [Skype for Business PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="32f11-111">단계별 지침은 [Microsoft 팀 PowerShell 설치](teams-powershell-install.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32f11-111">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a><span data-ttu-id="32f11-112">조직의 팀 모임 정책 과제를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-112">Get the Teams meeting policy assignments for your organization</span></span>

<span data-ttu-id="32f11-113">조직의 팀 모임 정책 과제를 가져오려면 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-113">Run the following to get the Teams meeting policy assignments for your organization.</span></span>

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

<span data-ttu-id="32f11-114">이 예제에서는 두 사용자에 게 RestrictedAnonymousAccess 모임 정책이 할당 되었음을 보여 주는 다음 출력이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-114">In this example, the following output is returned, which shows that two users are assigned the RestrictedAnonymousAccess meeting policy.</span></span>

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a><span data-ttu-id="32f11-115">사용자의 RestrictedAnonymous 모임 정책 할당 취소</span><span class="sxs-lookup"><span data-stu-id="32f11-115">Unassign the RestrictedAnonymous meeting policy from users</span></span>

<span data-ttu-id="32f11-116">사용자의 RestrictedAnonymous 모임 정책을 제거 하려면 사용자 수가 적은 경우 [CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet을 사용할 수 있습니다 (예: 100 사용자 미만).</span><span class="sxs-lookup"><span data-stu-id="32f11-116">To remove the the RestrictedAnonymous meeting policy from users, you can use the [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet if you have a small number of users (for example, less than 100 users).</span></span> <span data-ttu-id="32f11-117">사용자가 많은 경우 (예: 100 사용자가 더 많은 경우) [새 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet을 사용 하 여 일괄 작업을 제출 하는 것이 더 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-117">If you have a large number of users (for example, more than 100 users), it's more efficient to use the  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet to submit a batch operation.</span></span>

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a><span data-ttu-id="32f11-118">권한 부여-CsTeamsMeeting 정책 cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="32f11-118">Use the Grant-CsTeamsMeeting Policy cmdlet</span></span>

<span data-ttu-id="32f11-119">다음을 실행 하 여 사용자의 RestrictedAnonymous 모임 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-119">Run the following to remove the RestrictedAnonymous meeting policy from users.</span></span>

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a><span data-ttu-id="32f11-120">New-CsBatchPolicyAssignmentOperation cmdlet 사용</span><span class="sxs-lookup"><span data-stu-id="32f11-120">Use the New-CsBatchPolicyAssignmentOperation cmdlet</span></span>

<span data-ttu-id="32f11-121">[일괄 처리 정책 할당](assign-policies.md#assign-a-policy-to-a-batch-of-users)을 사용 하면 정책을 제거 하거나 업데이트 하는 최대 사용자 수를 한 번에 5000 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-121">With [batch policy assignment](assign-policies.md#assign-a-policy-to-a-batch-of-users), the maximum number of users for which you can remove or update policies is 5,000 at a time.</span></span> <span data-ttu-id="32f11-122">예를 들어 5000 명 이상의 사용자가 있는 경우 여러 일괄 처리를 제출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-122">For example, if you have more than 5,000 users, you'll need to submit multiple batches.</span></span> <span data-ttu-id="32f11-123">최상의 결과를 위해서는 한 번에 여러 일괄 처리를 제출 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="32f11-123">For best results, do not submit multiple batches at a time.</span></span> <span data-ttu-id="32f11-124">일괄 처리를 완료 하는 데 더 많은 일괄 처리가 가능 하도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-124">Allow batches to complete processing before submitting more batches.</span></span>

> [!NOTE]
> <span data-ttu-id="32f11-125">[새 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) Cmdlet은 팀 PowerShell 모듈에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-125">The [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet is in the Teams PowerShell module.</span></span> <span data-ttu-id="32f11-126">이 단계를 수행 하기 전에 [팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams)을 설치 하 고 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-126">Before you follow these steps, install and connect to the [Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams).</span></span> <span data-ttu-id="32f11-127">단계별 지침은 [Microsoft 팀 PowerShell 설치](teams-powershell-install.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32f11-127">For step-by-step guidance, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

<span data-ttu-id="32f11-128">다음 명령을 실행 하 여 사용자 일괄 처리에서 RestrictedAnonymousAccess 모임 정책을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-128">Run the following commands to remove the RestrictedAnonymousAccess meeting policy from a batch of users.</span></span>

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a><span data-ttu-id="32f11-129">일괄 처리의 상태를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-129">Get the status of the batch assignment</span></span>

<span data-ttu-id="32f11-130">각 일괄 처리 과제는 과제의 진행률과 상태를 추적 하 고 발생할 수 있는 오류를 식별 하는 데 사용할 수 있는 작업 ID를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-130">Each batch assignment returns an operation ID, which you can use to track the progress and status of the assignments and identify any failures that might occur.</span></span> <span data-ttu-id="32f11-131">예를 들어 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-131">For example, run the following:</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

<span data-ttu-id="32f11-132">**ErrorCount** 가 **0** 이 고 **OverallStatus** 가 **완료**되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="32f11-132">Make sure the **ErrorCount** is **0** (zero) and **OverallStatus** is **Completed**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="32f11-133">관련 항목</span><span class="sxs-lookup"><span data-stu-id="32f11-133">Related topics</span></span>

- [<span data-ttu-id="32f11-134">팀에서 모임 정책 관리</span><span class="sxs-lookup"><span data-stu-id="32f11-134">Manage meeting policies in Teams</span></span>](meeting-policies-in-teams.md)
- [<span data-ttu-id="32f11-135">Teams PowerShell 개요</span><span class="sxs-lookup"><span data-stu-id="32f11-135">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="32f11-136">팀에서 사용자에 게 정책 할당</span><span class="sxs-lookup"><span data-stu-id="32f11-136">Assign policies to your users in Teams</span></span>](assign-policies.md)
