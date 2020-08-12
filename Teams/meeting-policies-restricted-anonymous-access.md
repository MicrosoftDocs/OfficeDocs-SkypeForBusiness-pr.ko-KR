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
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>사용자의 RestrictedAnonymousAccess 팀 모임 정책 제거

Microsoft 팀의 [모임 정책은](meeting-policies-in-teams.md) 조직의 사용자가 예약한 모임의 모임 참가자가 사용할 수 있는 기능을 제어 하는 데 사용 됩니다. 

팀에는 익명 사용자가 모임을 시작 하지 못하도록 제한 하는 미리 정의 된 설정이 포함 된 기본 제공 정책 RestrictedAnonymousAccess이 포함 되어 있습니다. (익명 사용자는 인증 되지 않은 사용자입니다.) 모임 정책의 미리 정의 된 설정은 관리자가 편집 하거나 변경할 수 없습니다.

이 문서에서는 PowerShell을 사용 하 여이 정책을 할당 한 사용자의 RestrictedAnonymousAccess 모임 정책을 제거 하는 방법을 보여 줍니다. PowerShell을 사용 하 여 팀을 관리 하는 방법에 대해 자세히 알아보려면 [팀 powershell 개요](teams-powershell-overview.md)를 참조 하세요.

## <a name="before-you-start"></a>시작 하기 전에

[비즈니스용 Skype PowerShell 모듈](https://www.microsoft.com/download/details.aspx?id=39366)을 설치 하 고 연결 합니다. 단계별 지침은 [Microsoft 팀 PowerShell 설치](teams-powershell-install.md)를 참조 하세요.

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>조직의 팀 모임 정책 과제를 가져옵니다.

조직의 팀 모임 정책 과제를 가져오려면 다음을 실행 합니다.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

이 예제에서는 두 사용자에 게 RestrictedAnonymousAccess 모임 정책이 할당 되었음을 보여 주는 다음 출력이 반환 됩니다.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>사용자의 RestrictedAnonymous 모임 정책 할당 취소

사용자의 RestrictedAnonymous 모임 정책을 제거 하려면 사용자 수가 적은 경우 [CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet을 사용할 수 있습니다 (예: 100 사용자 미만). 사용자가 많은 경우 (예: 100 사용자가 더 많은 경우) [새 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) cmdlet을 사용 하 여 일괄 작업을 제출 하는 것이 더 효율적일 수 있습니다.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>권한 부여-CsTeamsMeeting 정책 cmdlet 사용

다음을 실행 하 여 사용자의 RestrictedAnonymous 모임 정책을 제거 합니다.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>New-CsBatchPolicyAssignmentOperation cmdlet 사용

[일괄 처리 정책 할당](assign-policies.md#assign-a-policy-to-a-batch-of-users)을 사용 하면 정책을 제거 하거나 업데이트 하는 최대 사용자 수를 한 번에 5000 수 있습니다. 예를 들어 5000 명 이상의 사용자가 있는 경우 여러 일괄 처리를 제출 해야 합니다. 최상의 결과를 위해서는 한 번에 여러 일괄 처리를 제출 하지 마세요. 일괄 처리를 완료 하는 데 더 많은 일괄 처리가 가능 하도록 허용 합니다.

> [!NOTE]
> [새 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) Cmdlet은 팀 PowerShell 모듈에 있습니다. 이 단계를 수행 하기 전에 [팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams)을 설치 하 고 연결 합니다. 단계별 지침은 [Microsoft 팀 PowerShell 설치](teams-powershell-install.md)를 참조 하세요.

다음 명령을 실행 하 여 사용자 일괄 처리에서 RestrictedAnonymousAccess 모임 정책을 제거 합니다.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>일괄 처리의 상태를 가져옵니다.

각 일괄 처리 과제는 과제의 진행률과 상태를 추적 하 고 발생할 수 있는 오류를 식별 하는 데 사용할 수 있는 작업 ID를 반환 합니다. 예를 들어 다음을 실행 합니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

**ErrorCount** 가 **0** 이 고 **OverallStatus** 가 **완료**되었는지 확인 합니다.

## <a name="related-topics"></a>관련 항목

- [팀에서 모임 정책 관리](meeting-policies-in-teams.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
- [팀에서 사용자에 게 정책 할당](assign-policies.md)
