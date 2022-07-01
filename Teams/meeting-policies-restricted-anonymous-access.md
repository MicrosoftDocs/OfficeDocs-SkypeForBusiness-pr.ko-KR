---
title: 사용자의 RestrictedAnonymousAccess Teams 모임 정책 삭제
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: 조직의 사용자로부터 RestrictedAnonymousAccess Teams 모임 정책을 제거하는 방법을 알아봅니다.
ms.openlocfilehash: e5ea203e52ca1b81ed7ce37f31c9f8cb5900c131
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564106"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>사용자의 RestrictedAnonymousAccess Teams 모임 정책 삭제

Microsoft Teams의 [모임 정책은](meeting-policies-overview.md) 조직의 사용자가 예약한 모임 참가자가 사용할 수 있는 기능을 제어하는 데 사용됩니다. 

Teams에는 익명 사용자가 모임을 시작하지 못하도록 제한하는 미리 정의된 설정이 포함된 RestrictedAnonymousAccess라는 기본 제공 정책이 포함되어 있습니다. (익명 사용자는 인증되지 않은 사용자입니다.) 모임 정책의 미리 정의된 설정은 관리자가 편집하거나 변경할 수 없습니다.

이 문서에서는 PowerShell을 사용하여 이 정책이 할당된 사용자로부터 RestrictedAnonymousAccess 모임 정책을 제거하는 방법을 보여 줍니다. PowerShell을 사용하여 Teams를 관리하는 방법에 대한 자세한 내용은 [Teams PowerShell 개요](teams-powershell-overview.md)를 참조하세요.

## <a name="before-you-start"></a>시작하기 전에

[비즈니스용 Skype PowerShell 모듈](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell)을 설치하고 연결합니다. 단계별 지침은 [Microsoft Teams PowerShell 설치](teams-powershell-install.md)를 참조하세요.

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>조직에 대한 Teams 모임 정책 할당 가져오기

다음을 실행하여 조직에 대한 Teams 모임 정책 할당을 가져옵니다.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

이 예제에서는 두 사용자에게 RestrictedAnonymousAccess 모임 정책이 할당되었음을 보여 주는 다음 출력이 반환됩니다.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>사용자의 RestrictedAnonymous 모임 정책 할당 취소

사용자로부터 RestrictedAnonymous 모임 정책을 제거하려면 적은 수의 사용자(예: 100명 미만)가 있는 경우 [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) cmdlet을 사용할 수 있습니다. 사용자가 많은 경우(예: 100명 이상의 사용자)  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리 작업을 제출하는 것이 더 효율적입니다.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Grant-CsTeamsMeeting Policy cmdlet 사용

다음을 실행하여 사용자로부터 RestrictedAnonymous 모임 정책을 제거합니다.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>New-CsBatchPolicyAssignmentOperation cmdlet 사용

[일괄 처리 정책 할당](assign-policies-users-and-groups.md#assign-a-policy-to-a-batch-of-users)을 사용하면 정책을 제거하거나 업데이트할 수 있는 최대 사용자 수는 한 번에 5,000명입니다. 예를 들어 사용자가 5,000명 이상인 경우 여러 일괄 처리를 제출해야 합니다. 최상의 결과를 얻으려면 한 번에 여러 일괄 처리를 제출하지 마세요. 더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료되도록 허용합니다.

> [!NOTE]
> [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet은 Teams PowerShell 모듈에 있습니다. 이러한 단계를 따르기 전에 [Teams PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams)을 설치하고 연결합니다. 단계별 지침은 [Microsoft Teams PowerShell 설치](teams-powershell-install.md)를 참조하세요.

다음 명령을 실행하여 사용자 일괄 처리에서 RestrictedAnonymousAccess 모임 정책을 제거합니다.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>일괄 처리 할당의 상태 가져오기

각 일괄 처리 할당은 작업의 진행률 및 상태를 추적하고 발생할 수 있는 오류를 식별하는 데 사용할 수 있는 작업 ID를 반환합니다. 예를 들어 다음을 실행합니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

**ErrorCount** 가 **0** 이고 **OverallStatus** 가 **완료** 되었는지 확인합니다.

## <a name="related-topics"></a>관련 항목

- [Teams에서의 모임 정책 관리](meeting-policies-overview.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)