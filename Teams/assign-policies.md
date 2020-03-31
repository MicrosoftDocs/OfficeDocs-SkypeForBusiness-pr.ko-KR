---
title: Microsoft 팀에서 사용자에 게 정책 할당
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: tomkau, saragava, ritikag
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
description: Microsoft 팀에서 사용자에 게 정책을 할당 하는 다양 한 방법에 대해 알아봅니다.
f1keywords: ''
ms.openlocfilehash: 0ad4794d0813eec97ea723d86ae6b3c60e0c9129
ms.sourcegitcommit: 996ae0d36ae1bcb3978c865bb296d8eccf48598e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2020
ms.locfileid: "43068500"
---
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Microsoft 팀에서 사용자에 게 정책 할당

> [!NOTE]
> **이 [문서에서 설명 하는](#assign-a-policy-to-a-group)Microsoft 팀의 기능 중 하나는 현재 비공개 미리 보기 에서만 사용할 수 있습니다. 이 기능에 대 한 Powershell cmdlet은 시험판 팀 PowerShell 모듈에 있습니다.** 이 기능의 릴리스 상태를 유지 하려면 [Microsoft 365 로드맵을](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=61185)확인 하세요.

관리자는 정책을 사용 하 여 조직의 사용자가 사용할 수 있는 팀 기능을 제어 합니다. 예를 들어, 전화 정책, 모임 정책, 메시지 정책이 몇 가지 이름으로 사용할 수 있습니다.

조직에는 고유한 요구 사항이 있는 다양 한 유형의 사용자와 사용자 지정 정책을 만들어 할당 하 여 해당 요구에 따라 다른 사용자 집합에 맞게 정책 설정을 조정할 수 있습니다.

조직의 정책을 더욱 쉽게 관리할 수 있도록 하기 위해 팀에서는 여러 가지 방법으로 사용자에 게 정책을 할당할 수 있습니다. 정책을 사용자에 게 직접 또는 일괄 처리 할당을 통해 또는 사용자가 구성원으로 속해 있는 그룹에 할당할 수 있습니다. 정책 패키지를 사용 하 여 조직에서 유사한 역할이 있는 사용자에 게 미리 설정 된 정책 모음을 할당할 수도 있습니다. 선택 하는 옵션은 관리 하는 정책의 수와 할당 하려는 사용자 수에 따라 달라 집니다.

이 문서에서는 사용자에 게 정책을 할당할 수 있는 다양 한 방법과이를 사용 하는 경우에 권장 되는 시나리오에 대해 설명 합니다.

## <a name="which-policy-takes-precedence"></a>어떤 정책이 우선적으로 적용 되나요?

사용자에 게 각 정책 유형에 대 한 하나의 유효 정책이 있습니다. 사용자에 게 정책을 직접 할당 했을 가능성이 있거나 같은 유형의 정책이 할당 된 하나 이상의 그룹의 구성원 이기도 한 경우도 있습니다. 이러한 유형의 시나리오에서는 어떤 정책이 우선적으로 적용 되나요?  사용자의 유효 정책은 다음과 같이 우선 순위 규칙에 따라 결정 됩니다.

사용자에 게 정책 (개별적으로 또는 일괄 할당을 통해)을 직접 할당 한 경우 해당 정책이 우선권을 갖습니다. 다음 예제에서 사용자의 유효한 정책은 사용자에 게 직접 할당 되는 Lincoln 제곱근 모임 정책입니다.

![직접 할당 된 정책이 우선 하는 방법을 보여 주는 다이어그램](media/assign-policies-example-directly-assigned.png)

사용자가 지정 된 형식의 정책을 직접 할당 하지 않은 경우 사용자가 구성원으로 속해 있는 그룹에 할당 된 정책이 우선권을 갖습니다. 사용자가 여러 그룹의 구성원 인 경우 지정 된 정책 형식에 대 한 [그룹 할당 순위가](#group-assignment-ranking) 가장 높은 정책이 우선 합니다.

이 예제에서 사용자의 유효 정책은 사용자가 구성원으로 속해 있고 동일한 정책 유형의 정책만 할당 하는 다른 그룹을 기준으로 할당 순위가 가장 높은 Exec 팀 및 HD 정책입니다.  

![그룹에서 상속 된 정책이 우선 하는 방법을 보여 주는 다이어그램](media/assign-policies-example-group.png)

사용자에 게 정책이 직접 할당 되지 않았거나 정책이 할당 된 그룹의 구성원이 아닌 경우 사용자는 해당 정책 형식에 대 한 전역 (조직 차원의 기본) 정책을 가져옵니다. 예제는 다음과 같습니다.

![글로벌 정책이 우선 하는 방법을 보여 주는 다이어그램](media/assign-policies-example-global.png)

자세히 알아보려면 [우선 순위 규칙](#precedence-rules)을 참조 하세요.

## <a name="ways-to-assign-policies"></a>정책을 할당 하는 방법

다음은 사용자에 게 정책을 할당할 수 있는 방법과 각각에 대해 권장 되는 시나리오에 대 한 개요입니다. 링크를 클릭 하 여 자세한 내용을 알아보세요.

|방법  |If ...  | 사용 하 고 있습니다 ...
|---------|---------|----|
|[개인 사용자에 게 정책 할당](#assign-a-policy-to-individual-users)    | 팀을 처음 사용할 때 시작 하는 것이 든, 소수의 사용자에 게 하나 또는 두 가지 정책만 할당 하면 됩니다. |비즈니스용 Skype Online PowerShell 모듈의 Microsoft 팀 관리 센터 또는 PowerShell cmdlet
| [정책 패키지 할당](#assign-a-policy-package)   | 조직에서 역할이 같거나 비슷한 특정 사용자 집합에 여러 정책을 할당 해야 합니다. 예를 들어 학교에서 교사에 게 교육 (교사) 정책 패키지를 할당 하 여 채팅, 통화, 모임, 교육 (보조 학생) 정책 패키지에 대 한 모든 액세스 권한을 보조 학생이 비공개 통화와 같은 특정 기능을 제한할 수 있습니다.  |팀 PowerShell 모듈의 Microsoft 팀 관리 센터 또는 PowerShell cmdlet|
|[사용자 일괄 처리에 정책 할당](#assign-a-policy-to-a-batch-of-users)   | 대규모 사용자 집합에 정책을 할당 해야 합니다. 예를 들어 조직에서 한 번에 수백 명 또는 수천 명의 사용자에 게 정책을 할당 하려고 합니다.  |팀 PowerShell 모듈의 PowerShell cmdlet|
|[그룹에 정책 할당](#assign-a-policy-to-a-group) (미리 보기)   |사용자의 그룹 구성원 자격을 기준으로 정책을 할당 해야 합니다. 예를 들어 보안 그룹 또는 조직 구성 단위의 모든 사용자에 게 정책을 할당 하려고 합니다.| 팀 PowerShell 모듈의 PowerShell cmdlet|
| 사용자 일괄 처리에 정책 패키지 할당 (예정 대로) |||
| 그룹에 정책 패키지 할당 (예정 대로)   | ||

## <a name="assign-a-policy-to-individual-users"></a>개인 사용자에 게 정책 할당

개별 사용자 또는 한 번에 적은 수의 사용자에 게 정책을 할당 하려면 다음 단계를 따르세요.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터 사용

사용자에 게 정책을 할당 하려면 다음을 수행 합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 창에서 **사용자**로 이동한 후 해당 사용자를 클릭합니다.
2. 사용자 이름의 왼쪽을 클릭하여 사용자를 선택한 후 **설정 편집**을 클릭합니다.
3. 할당 하려는 정책을 선택한 다음 **적용**을 클릭 합니다.

한 번에 최대 20 명의 사용자에 게 정책을 할당 하려면 [팀 사용자 설정을 일괄적으로 편집](edit-user-settings-in-bulk.md)을 참조 하세요.

또는 다음을 수행할 수도 있습니다.

1. Microsoft 팀 관리 센터의 왼쪽 탐색 모음에서 정책 페이지로 이동 합니다.
2. 정책 이름 왼쪽을 클릭 하 여 할당 하려는 정책을 선택 합니다.
3. **사용자 관리**를 선택합니다.
4. **사용자 관리** 창에서 표시 이름 또는 사용자 이름을 사용 하 여 사용자를 검색 하 고 이름을 선택한 다음 **추가**를 선택 합니다. 추가할 각 사용자에 대해 이 단계를 반복합니다.
5. 사용자 추가를 마쳤으면 **저장**을 선택 합니다.

### <a name="using-powershell"></a>PowerShell 사용

각 정책 형식에는 관리를 위한 고유한 cmdlet 집합이 있습니다. 지정 된 ```Grant-``` 정책 형식에 대 한 cmdlet을 사용 하 여 정책을 할당 합니다. 예를 들어 ```Grant-CsTeamsMeetingPolicy``` cmdlet을 사용 하 여 팀 모임 정책을 사용자에 게 할당 합니다. 이러한 cmdlet은 비즈니스용 Skype Online PowerShell 모듈에 포함 되어 있으며 [비즈니스용 skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)에 설명 되어 있습니다.

 [비즈니스용 Skype Online PowerShell 모듈](https://www.microsoft.com/en-us/download/details.aspx?id=39366) 을 다운로드 하 여 설치한 후 (아직 없는 경우) 다음을 실행 하 여 비즈니스용 skype online에 연결 하 고 세션을 시작 합니다.

```powershell
Import-Module SkypeOnlineConnector
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

이 예제에서는 학생 모임 정책 이라는 팀 모임 정책을 Reda 이라는 사용자에 게 할당 합니다.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

자세히 알아보려면 [PowerShell을 통한 정책 관리](teams-powershell-overview.md#managing-policies-via-powershell)를 참조 하세요.

## <a name="assign-a-policy-package"></a>정책 패키지 할당

팀의 정책 패키지는 조직에서 동일 하거나 비슷한 역할을 하는 사용자에 게 할당할 수 있는 미리 정의 된 정책 및 정책 설정의 모음입니다. 각 정책 패키지는 사용자 역할을 중심으로 설계 되며, 해당 역할에 대 한 일반적인 활동을 지 원하는 미리 정의 된 정책 및 정책 설정이 포함 되어 있습니다. 일부 정책 패키지의 예로는 교육 (교사) 패키지 및 의료 (임상 worker) 패키지가 있습니다.

정책 패키지를 사용자에 게 할당 하면 패키지의 정책이 만들어지고 사용자의 요구에 맞게 패키지의 각 정책 설정을 사용자 지정할 수 있습니다.

정책 패키지를 할당 하 고 관리 하는 방법에 대 한 단계별 지침은 [팀에서 정책 패키지 관리](manage-policy-packages.md)를 참조 하세요.

## <a name="assign-a-policy-to-a-batch-of-users"></a>사용자 일괄 처리에 정책 할당
 
일괄 처리 정책 할당을 사용 하면 대규모 사용자 집합에 스크립트를 사용할 필요 없이 한 번에 정책을 할당할 수 있습니다. ```New-CsBatchPolicyAssignmentOperationd``` Cmdlet을 사용 하 여 할당 하려는 사용자의 일괄 처리 및 정책을 제출할 수 있습니다. 할당이 백그라운드 작업으로 처리 되 고 각 일괄 처리에 대 한 작업 ID가 생성 됩니다. 그런 다음 ```Get-CsBatchPolicyAssignmentOperation``` cmdlet을 사용 하 여 일괄 처리에서 배정의 진행률과 상태를 추적할 수 있습니다.

일괄 처리에는 최대 2만 명의 사용자를 포함할 수 있습니다. 개체 Id, UPN (사용자 계정 이름), SIP (세션 초기화 프로토콜) 주소 또는 전자 메일 주소를 사용 하 여 사용자를 지정할 수 있습니다.

> [!IMPORTANT]
> 현재는 5000 사용자를 한 번에 일괄적으로 할당 하는 것을 제안 하 고 있습니다. 이러한 시간을 연장 하는 동안에는 처리 시간이 지연 될 수 있습니다. 이 늘어난 처리 시간에 대 한 영향을 최소화 하기 위해 최대 5000 사용자에 대 한 작은 일괄 처리 크기를 제출 하 고 이전 작업을 완료 한 후에 각 일괄 처리를 제출 하는 것이 좋습니다. 업무 시간 외에 일괄 처리를 제출 하는 것도 도움이 될 수 있습니다.

> [!NOTE]
> 현재 일부 팀 정책 유형에는 일괄 처리 정책 할당을 사용할 수 없습니다. 지원 되는 정책 유형 목록에 대 한 [CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 을 참조 하세요.

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.

다음을 실행 하 여 [Microsoft 팀 PowerShell 모듈](https://www.powershellgallery.com/packages/MicrosoftTeams)을 설치 합니다. 버전 1.0.5 이상이 설치 되어 있는지 확인 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.

```powershell
Connect-MicrosoftTeams
```

메시지가 표시 되 면 관리자 자격 증명을 사용 하 여 로그인 합니다.

### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Azure AD PowerShell for Graph 모듈을 설치 하 고 연결 (선택 사항)

또한 [Graph 모듈에 대 한 AZURE Ad PowerShell을 다운로드 하 여 설치](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 하 고 (아직 없는 경우) azure ad에 연결 하 여 조직에서 사용자 목록을 검색할 수 있도록 할 수 있습니다.

Azure AD에 연결 하려면 다음을 실행 합니다.

```powershell
Connect-AzureAD
```

메시지가 표시 되 면 팀에 연결 하는 데 사용한 것과 동일한 관리자 자격 증명을 사용 하 여 로그인 합니다.

### <a name="assign-a-policy-to-a-batch-of-users"></a>사용자 일괄 처리에 정책 할당

이 예제에서는 ```New-CsBatchPolicyAssignmentOperation``` cmdlet을 사용 하 여 HR 앱 설치 정책 이라는 앱 설정 정책을 Users_ids에 나열 된 사용자 일괄 처리에 할당 합니다.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

이 예제에서는 Azure AD에 연결 하 여 사용자 컬렉션을 검색 한 다음 해당 Upn을 사용 하 여 지정 된 일괄 처리 사용자에 게 새 고용 메시징 정책 이라는 메시징 정책을 할당 합니다.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.UserPrincipalName -OperationName "Example 2 batch"
```

자세한 내용은 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)를 참조 하세요.

### <a name="get-the-status-of-a-batch-assignment"></a>일괄 처리의 상태 가져오기

일괄 처리 할당의 상태를 가져오려면 다음을 실행 합니다. 여기서 OperationId는 지정 된 일괄 처리에 대해 ```New-CsBatchPolicyAssignmentOperation``` cmdlet에서 반환 되는 작업 ID입니다.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

출력에 오류가 발생 했음을 표시 하는 경우 다음을 실행 하 여 ```UserState``` 속성에 있는 오류에 대 한 자세한 정보를 얻을 수 있습니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

자세한 내용은 [get-help를 CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).

## <a name="assign-a-policy-to-a-group"></a>그룹에 정책 할당

**그룹에 대 한 정책 할당은 현재 비공개 미리 보기 에서만 사용할 수 있습니다. 이 기능에 대 한 cmdlet은 시험판 팀 PowerShell 모듈에 있습니다.**

그룹에 정책 할당을 통해 보안 그룹 또는 조직 구성 단위와 같은 사용자 그룹에 정책을 할당할 수 있습니다. 정책 할당은 선행 규칙에 따라 그룹의 구성원에 게 전파 됩니다. 그룹에서 구성원이 추가 되거나 제거 되 면 그에 따라 상속 된 정책 할당이 업데이트 됩니다.

```New-CsGroupPolicyAssignment``` Cmdlet을 사용 하 여 그룹에 정책을 할당 합니다. 개체 Id, SIP 주소 또는 전자 메일 주소를 사용 하 여 그룹을 지정할 수 있습니다.

정책을 할당 하면 그룹에 즉시 할당 됩니다. 그러나 그룹 구성원에 게 정책 할당의 전파는 백그라운드 작업으로 수행 되며 그룹 크기에 따라 시간이 걸릴 수 있습니다. 그룹에서 정책이 할당 되지 않거나 구성원이 그룹에서 추가 되거나 제거 되는 경우에도 마찬가지입니다.

> [!NOTE]
> 현재, 그룹에 대 한 정책 할당은 모든 팀 정책 유형에 사용할 수 없습니다. 지원 되는 정책 유형 목록에 대 한 [새 CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 을 참조 하세요.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>그룹에 정책 할당에 대해 알아야 할 사항

시작 하기 전에 우선 순위 규칙 및 그룹 배정 순위를 이해 하는 것이 중요 합니다.

#### <a name="precedence-rules"></a>우선 순위 규칙

지정 된 정책 유형의 경우 사용자의 유효한 정책은 다음에 따라 결정 됩니다.

- 사용자에 게 직접 할당 되는 정책은 그룹에 할당 된 같은 유형의 다른 정책 보다 우선 합니다. 즉, 사용자에 게 지정 된 형식의 정책을 직접 할당 한 경우 해당 사용자는 그룹에서 같은 유형의 정책을 상속 하지 않습니다. 또한 사용자에 게 직접 할당 된 지정 된 형식의 정책이 있는 경우 해당 정책을 사용자가 제거 해야 그룹에서 같은 유형의 정책을 상속할 수 있습니다.,
- 사용자에 게 직접 할당 된 정책이 없고 두 개 이상의 그룹의 구성원 인 경우 각 그룹에 동일한 유형의 정책이 있는 경우 사용자는 우선 순위가 가장 높은 그룹 할당의 정책을 상속 합니다.
- 사용자가 정책이 할당 된 그룹의 구성원이 아니면 해당 정책 유형에 대 한 전역 (조직 차원의 기본) 정책이 사용자에 게 적용 됩니다.

사용자의 유효 정책은 정책이 할당 된 그룹에서 사용자가 추가 또는 제거 되거나 그룹에서 정책이 할당 되지 않거나 사용자에 게 직접 할당 된 정책이 제거 되는 경우 이러한 규칙에 따라 업데이트 됩니다.

#### <a name="group-assignment-ranking"></a>그룹 할당 순위
 
그룹에 정책을 할당 하는 경우 그룹 할당에 대 한 순위를 지정 합니다. 이는 사용자가 두 개 이상의 그룹의 구성원 인 경우 각 그룹에 같은 유형의 정책이 할당 되는 경우 사용자가 유효한 정책으로 상속 해야 하는 정책을 결정 하는 데 사용 됩니다.

그룹 할당 순위는 같은 종류의 다른 그룹 배정에 대해 상대적입니다. 예를 들어, 호출 정책을 두 그룹에 배정 하는 경우 1 개의 배정에 대 한 순위를 1로 설정 하 고, 나머지 하나는 가장 높은 순위를 사용 합니다. 그룹 할당 순위는 상속과 관련 하 여 다른 그룹 구성원 자격 보다 더 중요 하거나 관련성이 높은 그룹 구성원을 나타냅니다.
 
예를 들어 두 개의 그룹이 있고 직원을 저장 하 고 저장소 관리자를 사용 하 고 있다고 가정 합니다. 두 그룹 모두 팀 호출 정책을 할당 하 고 직원을 호출 하 고 정책 및 저장소 관리자 호출 정책을 각각 저장 합니다. 두 그룹에 모두 포함 된 저장소 관리자의 경우 관리자 역할은 직원 역할 보다 관련성이 있으므로 스토어 관리자 그룹에 할당 되는 호출 정책은 우선 순위가 높아야 합니다.

|그룹과 |팀 호출 정책 이름  |순위|
|---------|---------|---|
|스토어 관리자   |스토어 관리자 호출 정책         |1|
|직원 저장    |직원에 게 통화 정책 저장      |2|

순위를 지정 하지 않으면 정책 할당에 순위가 가장 낮은 것으로 지정 됩니다.

### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft 팀 PowerShell 모듈을 설치 하 고 연결 합니다.

> [!NOTE]
> Cmdlet은 팀 PowerShell 모듈의 시험판 버전에 있습니다. 일반적으로 사용 가능한 팀 PowerShell 모듈 (설치 되어 있는 경우)을 제거 하 고 PowerShell 테스트 갤러리에서 해당 모듈의 최신 시험판 버전을 설치 하려면 다음 단계를 따릅니다.

아직 하지 않은 경우 다음을 실행 하 여 PowerShell 테스트 갤러리를 신뢰할 수 있는 원본으로 등록 합니다.

```powershell
Register-PSRepository -SourceLocation https://www.poshtestgallery.com/api/v2 -Name PsTestGallery -InstallationPolicy Trusted
```

일반적으로 사용 가능한 팀 PowerShell 모듈 버전이 설치 되어 있는 경우 다음을 실행 하 여 제거 합니다.

```powershell
Uninstall-Module MicrosoftTeams -AllVersions
```

다음을 실행 하 여 PowerShell 테스트 갤러리에서 최신 Microsoft 팀 PowerShell 모듈을 설치 합니다.

```powershell
Install-Module MicrosoftTeams -Repository PSTestGallery
```

다음을 실행 하 여 팀에 연결 하 고 세션을 시작 합니다.

```powershell
Connect-MicrosoftTeams
```

메시지가 표시 되 면 관리자 자격 증명을 사용 하 여 로그인 합니다.

### <a name="assign-a-policy-to-a-group"></a>그룹에 정책 할당

이 예제에서는 ```New-CsGroupPolicyAssignment``` cmdlet을 사용 하 여 정품 관리자 모임 정책 이라는 팀 구성원 정책을 할당 순위가 1 인 그룹에 할당 합니다.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

자세한 내용은 [새 CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment)을 참조 하세요.

### <a name="get-policy-assignments-for-a-group"></a>그룹에 대 한 정책 할당 가져오기

```Get-CsGroupPolicyAssignment``` Cmdlet을 사용 하 여 그룹에 할당 된 모든 정책을 가져옵니다. 그룹은 해당 SIP 주소 또는 전자 메일 주소가 정책을 할당 하는 데 사용 된 경우에도 그룹 Id에 의해 항상 나열 됨을 참고 하세요.

이 예제에서는 특정 그룹에 할당 된 모든 정책을 검색 합니다.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

이 예제에서는 팀 모임 정책이 할당 된 모든 그룹을 반환 합니다.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

자세한 내용은 [Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment)을 참조 하세요.

### <a name="remove-a-policy-from-a-group"></a>그룹에서 정책 제거

```Remove-CsGroupPolicyAssignment``` Cmdlet을 사용 하 여 그룹에서 정책을 제거 합니다. 그룹에서 정책을 제거 하면 해당 그룹에 할당 된 같은 유형의 다른 정책에 대 한 우선 순위와 순위가 낮게 업데이트 됩니다. 예를 들어 순위가 2 인 정책을 제거 하는 경우 3 및 4 순위의 등급이 업데이트 되어 새 순위를 반영 합니다. 다음 두 테이블은이 예제를 보여 줍니다.

팀 모임 정책에 대 한 정책 과제 및 우선 순위 목록은 다음과 같습니다.

|그룹 이름  |정책 이름  |순위|
|---------|---------|---------|
|영업    |판매 정책       | 1        |
|서쪽 지역     |서쪽 지역 정책         |2         |
|나눠    |디비전 정책         |3         |
|대리점   |자회사 정책        |4(tcp/ipv4)         |

서쪽 지역 그룹에서 서쪽 지역 정책을 제거 하는 경우 정책 할당 및 우선 순위는 다음과 같이 업데이트 됩니다.

|그룹 이름  |정책 이름  |순위|
|---------|---------|---------|
|영업    |판매 정책       | 1        |
|나눠    |디비전 정책         |2         |
|대리점   |자회사 정책        |3        |

이 예제에서는 그룹에서 팀 모임 정책을 제거 합니다.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

자세한 내용은 [-CsGroupPolicyAssignment 제거](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment)를 참조 하세요.

### <a name="change-a-policy-assignment-for-a-group"></a>그룹에 대 한 정책 할당 변경

그룹에 정책을 할당 한 후 ```Set-CsGroupPolicyAssignmentd``` cmdlet을 사용 하 여 다음과 같이 해당 그룹의 정책 할당을 변경할 수 있습니다.

- 순위 변경
- 지정 된 정책 유형의 정책 변경
- 지정 된 정책 유형 및 순위에 대 한 정책 변경

이 예제에서는 그룹의 팀 통화 대기 정책을 SupportCallPark 정책으로 변경 하 고 3으로 할당 순위를 지정 합니다.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

자세한 내용은 [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment)을 참조 하세요.

### <a name="change-the-effective-policy-for-a-user"></a>사용자에 대 한 유효 정책 변경

다음은 정책을 직접 할당 받은 사용자의 유효 정책을 변경 하는 방법의 예입니다.

먼저, cmdlet을 ```Get-CsUserPolicyAssignment``` ```PolicySource``` 매개 변수와 함께 사용 하 여 사용자와 연결 된 팀 모임 브로드캐스트 정책의 세부 정보를 가져옵니다. 자세한 내용은 [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment)을 참조 하세요.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

출력은 사용자가 사용자가 속한 그룹에 할당 된 공급 업체 라이브 이벤트 정책 보다 우선 하는 직원 이벤트 라는 팀에 게 직접 할당 된 모임 브로드캐스트 정책에 대 한 작업을 수행 하는 것을 보여 줍니다.

```
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

이제 사용자의 직원 이벤트 정책을 제거 합니다. 즉, 사용자에 게는 더 이상 팀 모임 브로드캐스트 정책이 직접 할당 되어 있지 않으며 사용자가 속한 그룹에 할당 된 공급 업체 Live 이벤트 정책이 상속 됩니다. 

비즈니스용 Skype PowerShell 모듈에서 다음 cmdlet을 사용 하 여이 작업을 수행 합니다.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

팀 Powershell 모듈에서 다음 cmdlet을 사용 하 여 일괄 처리 정책 할당 인 경우에는이 작업을 수행할 수 있으며, 여기서 $users는 사용자가 지정 하는 사용자의 목록입니다.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="related-topics"></a>관련 항목

- [팀 PowerShell 개요](teams-powershell-overview.md)