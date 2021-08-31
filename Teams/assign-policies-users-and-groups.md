---
title: 사용자 및 그룹에 정책 할당
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 사용자 및 그룹에 정책을 할당하는 다양한 방법을 Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: a8182e1fe9058a5b7b7e8c88d0fdbac4070d48b7
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58732090"
---
# <a name="assign-policies-to-users-and-groups"></a>사용자 및 그룹에 정책 할당

이 문서에서는 사용자 및 그룹에 정책을 할당하는 다양한 방법을 Microsoft Teams. 읽기 전에 에서 정책 할당을 Teams [을 읽어야 합니다.](policy-assignment-overview.md)

## <a name="assign-a-policy-to-individual-users"></a>개별 사용자에게 정책 할당

다음 단계에 따라 개별 사용자 또는 소수의 사용자에게 정책을 할당합니다.

### <a name="use-the-microsoft-teams-admin-center"></a>관리 Microsoft Teams 사용

사용자에게 정책을 할당하는 경우:

1. 관리 센터의 왼쪽 Microsoft Teams 사용자로 이동한 다음 사용자를 선택합니다.
2. 사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 다음 설정 편집 **을 선택합니다.**
3. 할당할 정책을 선택한 다음 적용을 **선택합니다.**

![관리 센터의 사용자에게 Teams 할당합니다.](media/assign-policy-user.png)

또는 다음을 할 수도 있습니다.

1. 관리 센터의 왼쪽 Microsoft Teams 정책 페이지로 이동합니다.
2. 정책 이름의 왼쪽을 클릭하여 할당할 정책을 선택합니다.
3. **사용자 관리** 를 선택합니다.
4. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요. 추가할 각 사용자에 대해 이 단계를 반복합니다.
5. 사용자 추가가 완료되면 적용 을 **선택합니다.**

![두 번째 방법을 통해 Teams 관리자 센터의 사용자에게 정책을 할당합니다.](media/assign-policy-user2.png)

### <a name="use-powershell"></a>PowerShell 사용

각 정책 유형에는 관리하기 위한 자체 cmdlet 집합이 있습니다. 특정 정책 유형에 ```Grant-``` 대한 cmdlet을 사용하여 정책을 할당합니다. 예를 들어 cmdlet을 사용하여 사용자에게 Teams 모임 정책을 ```Grant-CsTeamsMeetingPolicy``` 할당합니다. 이러한 cmdlet은 Teams PowerShell 모듈에 포함되어 있으며 비즈니스용 Skype [cmdlet 참조에 설명되어 있습니다.](/powershell/skype)

 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) Teams 릴리스를 다운로드하고 설치한 다음 다음을 실행하여 연결합니다.

> [!NOTE]
> 비즈니스용 Skype Online Connector는 현재 최신 Teams PowerShell 모듈의 일부입니다.
>
> 최신 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 Teams 사용하는 경우 온라인 커넥터를 비즈니스용 Skype 필요가 없습니다.

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

이 예제에서는 Reda라는 사용자에게 Teams 모임 정책이라는 모임 정책을 할당합니다.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

자세한 내용은 [PowerShell을 통해 정책 관리 를 읽어보아야 합니다.](teams-powershell-managing-teams.md#manage-policies-via-powershell)

## <a name="assign-a-policy-to-a-group"></a>그룹에 정책 할당

그룹에 정책 할당을 사용하면 보안 그룹 또는 메일 그룹과 같은 사용자 그룹에 정책을 할당할 수 있습니다. 정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다. 그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.

그룹에 대한 정책 할당은 최대 50,000명까지의 그룹에 권장되지만 더 큰 그룹에서도 사용할 수 있습니다.

정책을 할당하면 그룹에 즉시 할당됩니다. 그러나 그룹의 구성원에게 정책 할당의 전파는 백그라운드 작업으로 수행됩니다. 그룹 크기에 따라 다소 시간이 걸릴 수 있습니다. 그룹에서 정책이 부가되지 않은 경우나 구성원이 그룹에 추가되거나 그룹에서 제거될 때도 마찬가지입니다.

그룹 정책 할당은 그룹의 직접 구성원인 사용자에게만 전파됩니다. 할당은 중첩된 그룹의 구성원에게 전파되지 않습니다.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>그룹에 정책 할당에 대해 알아야 할 정보

시작하기 전에 우선 순위 규칙 및 그룹 할당 순위를 이해하는 것이 중요합니다.

#### <a name="precedence-rules"></a>우선 순위 규칙

주어진 정책 형식의 경우 사용자의 유효 정책은 다음에 따라 결정됩니다.

- 사용자에게 직접 할당되는 정책은 그룹에 할당된 동일한 유형의 다른 정책보다 우선합니다. 즉, 사용자가 지정된 형식의 정책을 직접 할당하는 경우 해당 사용자는 그룹에서 동일한 형식의 정책을 상속하지 않습니다. 즉, 사용자에게 직접 할당된 지정된 형식의 정책이 있는 경우 그룹에서 동일한 형식의 정책을 상속하려면 먼저 사용자로부터 해당 정책을 제거해야 합니다.
- 사용자에게 직접 할당된 정책이 없고 두 개 이상의 그룹의 구성원이고 각 그룹에 할당된 동일한 유형의 정책이 있는 경우 사용자는 가장 높은 순위를 가지는 그룹 할당의 정책을 상속합니다.
- 사용자가 정책이 할당된 그룹의 구성원이 아닌 경우 해당 정책 유형에 대한 전역(Org-wide default) 정책이 사용자에게 적용됩니다.

사용자의 유효 정책은 다음 규칙에 따라 업데이트됩니다.

- 사용자가 정책에 할당된 그룹에 추가되거나 제거될 때
- 그룹에서 정책이 부가되지 않습니다.
- 사용자에게 직접 할당된 정책이 제거됩니다.

#### <a name="group-assignment-ranking"></a>그룹 할당 순위

그룹에 정책을 할당할 때 그룹 할당에 대한 순위를 지정합니다. 이 정책은 사용자가 두 개 이상의 그룹의 구성원이고 각 그룹에 동일한 유형의 정책이 할당된 경우 사용자가 효과적인 정책으로 상속해야 하는 정책을 결정하는 데 사용됩니다.

그룹 할당 순위는 동일한 유형의 다른 그룹 할당과 상대적입니다. 예를 들어 두 그룹에 호출 정책을 할당하는 경우 한 할당의 순위를 1로, 다른 할당은 2로, 1은 가장 높은 순위로 설정합니다. 그룹 할당 순위는 상속과 관련하여 다른 그룹 멤버 자격보다 더 중요하거나 관련성이 높은 그룹 멤버 자격을 나타냅니다.

예를 들어 직원 저장소 및 스토어 관리자의 두 그룹이 있습니다. 두 그룹 모두 각각 Teams 호출 정책, Store Employees Calling Policy 및 Store Manager 호출 정책이 할당됩니다. 두 그룹에 있는 저장소 관리자의 경우 관리자 역할은 직원 역할보다 관련성이 높기 때문에 Store Managers 그룹에 할당된 호출 정책은 순위가 높아야 합니다.

|그룹 |Teams 이름 호출  |순위|
|---------|---------|---|
|Store Managers   |스토어 관리자 호출 정책         |1|
|직원 저장    |직원 호출 정책 저장      |2|

순위를 지정하지 않으면 정책 할당에 가장 낮은 순위가 지정됩니다.

### <a name="in-the-teams-admin-center"></a>관리 Teams 센터에서

> [!NOTE]
> 현재 Microsoft Teams 관리 센터를 사용하는 그룹에 대한 정책 할당은 Teams 통화 정책, 통화 Teams 정책, Teams 이벤트 정책, Teams 모임 정책 및 Teams 메시지 Teams 사용할 수 있습니다. 다른 정책 형식의 경우 PowerShell을 사용 합니다.

1. 관리 센터의 왼쪽 Microsoft Teams 정책 유형 페이지로 이동합니다. 예를 들어 모임 모임 정책  >  **으로 이동합니다.**
2. 그룹 정책 **할당 탭을** 선택합니다.
3. 그룹 **추가를 선택한** 다음  그룹화 정책 할당 창에서 다음을 선택합니다.
    1. 정책을 할당할 그룹을 검색하고 추가합니다.
    2. 그룹 할당의 순위를 설정합니다.
    3. 할당할 정책을 선택합니다.
    4. 적용 **을 선택합니다.**
    
![관리 센터의 그룹에 Teams 할당합니다.](media/assign-policy-group.png)

그룹 정책 할당을 제거하려면  정책 페이지의 그룹 정책 할당 탭에서 그룹 할당을 선택한 다음 **제거를 선택합니다.**

그룹 할당의 순위를 변경하려면 먼저 그룹 정책 할당을 제거해야 합니다. 그런 다음 위의 단계를 수행하여 그룹에 정책을 할당합니다.

### <a name="use-the-powershell-option"></a>PowerShell 옵션 사용

> [!NOTE]
> 현재 PowerShell을 사용하는 그룹에 대한 정책 할당은 모든 정책 유형에 Teams 없습니다. 지원되는 정책 유형 목록에 대한 [New-CsGroupPolicyAssignment를](/powershell/module/teams/new-csgrouppolicyassignment) 참조하세요.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>PowerShell 모듈을 Microsoft Teams 연결

단계별 지침은 [PowerShell Teams 참조하세요.](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>사용자 그룹에 정책 할당

[New-CsGroupPolicyAssignment](/powershell/module/teams/new-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 정책을 할당합니다. 개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다.

이 예제에서는 Teams 할당 순위가 1인 그룹에 Retail Managers 모임 정책이라는 모임 정책을 할당합니다.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>그룹에 대한 정책 할당을 얻습니다.

[Get-CsGroupPolicyAssignment](/powershell/module/teams/get-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 할당된 모든 정책을 얻습니다. 그룹은 정책을 할당하는 데 SIP 주소 또는 전자 메일 주소를 사용하는 경우에도 항상 그룹 ID로 나열됩니다.

이 예제에서는 특정 그룹에 할당된 모든 정책을 검색합니다.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

이 예제에서는 모임 정책에 할당된 Teams 반환합니다.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>그룹에서 정책 제거

[Remove-CsGroupPolicyAssignment](/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet을 사용하여 그룹에서 정책을 제거합니다. 그룹에서 정책을 제거하면 해당 그룹에 할당된 동일한 유형의 다른 정책의 우선 순위가 업데이트됩니다. 예를 들어 순위가 2인 정책을 제거하면 순위가 3과 4인 정책이 업데이트되어 새 순위가 반영됩니다. 다음 두 표에는 이 예제가 표시됩니다.

다음은 모임 정책에 대한 정책 할당 및 우선 순위 Teams 있습니다.

|그룹 이름  |정책 이름  |순위|
|---------|---------|---------|
|영업    |판매 정책       | 1        |
|서부 지역     |서부 지역 정책         |2         |
|디비전    |분할 정책         |3         |
|자회사   |자회사 정책        |4         |

서부 지역 그룹에서 서부 지역 정책을 제거하는 경우 정책 할당 및 우선 순위는 다음과 같이 업데이트됩니다.

|그룹 이름  |정책 이름  |순위|
|---------|---------|---------|
|영업    |판매 정책       | 1        |
|디비전    |분할 정책         |2         |
|자회사   |자회사 정책        |3        |

이 예제에서는 그룹에서 Teams 모임 정책을 제거합니다.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>그룹에 대한 정책 할당 변경

> [!NOTE]
> [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 곧 사용할 수 있습니다. 그 동안 그룹 정책 할당을 변경하려면 그룹에서 현재 정책 할당을 제거한 다음 새 정책 할당을 추가할 수 있습니다.

그룹에 정책을 할당한 후 [Set-CsGroupPolicyAssignment](/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 사용하여 해당 그룹의 정책 할당을 다음과 같이 변경할 수 있습니다.

- 순위 변경
- 주어진 정책 형식의 정책 변경
- 주어진 정책 유형 및 순위의 정책 변경

이 예제에서는 그룹의 호출 Teams 콜 파크 정책을 SupportCallPark라는 정책으로 변경하고 할당 순위를 3으로 변경합니다.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>사용자에 대한 유효 정책 변경

정책에 직접 할당된 사용자에 대한 효과적인 정책을 변경하는 방법에 대한 예제는 다음과 같습니다.

먼저 [Get-CsUserPolicyAssignment](/powershell/module/teams/get-csuserpolicyassignment) cmdlet과 매개 변수를 함께 사용하여 사용자와 Teams 모임 브로드캐스트 정책에 대한 세부 정보를 ```PolicySource``` 얻습니다.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

출력은 사용자가 직접 직원 이벤트라는 Teams 모임 브로드캐스트 정책이 할당되어 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트라는 정책보다 우선합니다.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

이제 사용자에서 Employee Events 정책을 제거합니다. 즉, 사용자에게 직접 할당된 Teams 모임 브로드캐스트 정책이 더 이상 없고 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트 정책을 상속합니다.

이 작업을 위해 비즈니스용 Skype PowerShell 모듈에서 다음 cmdlet을 사용합니다.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

다음 cmdlet을 Teams PowerShell 모듈에서 이를 대규모로 수행하면 일괄 처리 정책 할당이 $users 사용자 목록입니다.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>사용자 일괄 처리에 정책 할당

### <a name="use-the-admin-center"></a>관리 센터 사용

사용자에게 정책을 대량으로 할당하는 경우:

1. 관리 센터의 왼쪽 탐색에서 Microsoft Teams 를 **선택합니다.**
2. 정책을 할당할 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
3. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.
4. 설정 **편집을 선택하고** 원하는 내용을 변경한 다음 적용을 **선택합니다.**

정책 할당의 상태를 확인하려면 적용을 선택한 후 사용자 페이지  맨 위에  나타나는 배너에서 활동 **로그를 선택합니다.** 또는 관리 센터의 왼쪽 탐색에서 Microsoft Teams 대시보드로 이동한 다음 활동 로그에서 **세부** 정보 **보기를 선택합니다.** 활동 로그는 지난 30일 동안 관리 센터를 통해 20명 Microsoft Teams 일괄 처리에 대한 정책 할당을 보여줍니다. 자세한 내용은 활동 로그에서 정책 할당 [보기를 참조합니다.](activity-log.md)

### <a name="use-powershell-method"></a>PowerShell 메서드 사용

> [!NOTE]
> 현재 PowerShell을 사용하는 일괄 처리 정책 할당은 모든 정책 유형에 Teams 없습니다. 지원되는 정책 유형 목록은 [New-CsBatchPolicyAssignmentOperation을](/powershell/module/teams/new-csbatchpolicyassignmentoperation) 참조하세요.

일괄 처리 정책 할당을 사용하면 스크립트를 사용하지 않고도 동시에 대규모 사용자 집합에 정책을 할당할 수 있습니다. [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 사용자 일괄 처리 및 할당하려는 정책을 제출합니다. 할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다. 그런 다음 [Get-CsBatchPolicyAssignmentOperation](/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 과제의 진행률 및 상태를 추적할 수 있습니다.

개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정합니다. 사용자의 SIP 주소는 종종 UPN(사용자 주체 이름) 또는 전자 메일 주소와 동일한 값을 지만 필수는 아닙니다. 사용자가 UPN 또는 전자 메일을 사용하여 지정되지만 해당 SIP 주소와 다른 값이 있는 경우 사용자에게 정책 할당이 실패합니다. 일괄 처리에 중복 사용자가 포함된 경우 처리 전에 일괄 처리에서 중복된 사용자가 제거되고 일괄 처리에 남아 있는 고유 사용자에게만 상태가 제공됩니다.

배치에는 최대 5천 명의 사용자가 포함될 수 있습니다. 최상의 결과를 얻기 위해 한 번에 몇 개 이상의 일괄 처리를 제출하지 않습니다. 더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>PowerShell 모듈을 Teams 연결

다음을 실행하여 [powerShell Microsoft Teams 설치합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams) 버전 1.0.5 이상을 설치해야 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행하여 Teams 세션을 시작합니다.

```powershell
Connect-MicrosoftTeams
```

메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Azure AD PowerShell에 설치 및 Graph 모듈(선택 사항)

또한 조직의 사용자 목록을 검색할 수 있도록 Azure [AD PowerShell을](/powershell/azure/active-directory/install-adv2) 다운로드하여 Graph 모듈을 다운로드하고 설치하고 Azure AD에 연결할 수도 있습니다.

다음을 실행하여 Azure AD에 연결합니다.

```powershell
Connect-AzureAD
```

메시지가 표시될 때 로그인하는 데 사용한 관리자 자격 증명과 동일한 관리자 자격 증명을 사용하여 Teams.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>사용자 일괄 처리에 설정 정책 할당

이 예제에서는 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 Users_ids.text 파일에 나열된 사용자 일괄 처리에 HR 앱 설정 정책이라는 앱 설치 정책을 할당합니다.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

이 예제에서는 Azure AD에 연결하여 사용자 컬렉션을 검색한 다음, SIP 주소를 사용하여 지정된 사용자 일괄 처리에 새 고용 메시징 정책이라는 메시징 정책을 할당합니다.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>일괄 처리 할당의 상태 확인

다음을 실행하여 일괄 처리 할당의 상태를 얻습니다. 여기서 OperationId는 주어진 일괄 처리에 대해 cmdlet에서 반환되는 작업 ```New-CsBatchPolicyAssignmentOperation``` ID입니다.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

출력에서 오류가 발생한 것으로 표시되는 경우 다음을 실행하여 속성에 있는 오류에 대한 자세한 정보를 ```UserState``` 얻습니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

자세한 내용은 [Get-CsBatchPolicyAssignmentOperation 을 참조합니다.](/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>관련 항목

- [정책으로 Teams 관리](manage-teams-with-policies.md)
- [Teams PowerShell 개요](teams-powershell-overview.md)
- [Teams 정책 할당 - 시작](policy-assignment-overview.md)
