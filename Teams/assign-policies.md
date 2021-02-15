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
# <a name="assign-policies-to-your-users-in-microsoft-teams"></a>Microsoft Teams에서 사용자에게 정책 할당

관리자는 정책을 사용하여 조직의 사용자가 사용할 수 있는 Teams 기능을 제어합니다. 예를 들어 몇 가지 이름을 지정하는 호출 정책, 모임 정책 및 메시징 정책이 있습니다.

조직에는 고유한 요구 사항을 충족하는 다양한 유형의 사용자가 있습니다. 만들고 할당하는 사용자 지정 정책을 사용하면 이러한 요구에 따라 다양한 사용자 집합에 정책 설정을 조정할 수 있습니다.

조직에서 정책을 쉽게 관리하기 위해 Teams는 사용자에게 정책을 할당하는 여러 가지 방법을 제공합니다. 일괄 처리 할당을 통해 개별적으로 또는 대규모로 또는 사용자가 구성원인 그룹에 직접 정책을 할당합니다. 정책 패키지를 사용하여 비슷한 역할이 있는 조직의 사용자에게 미리 설정한 정책 컬렉션을 할당할 수도 있습니다. 선택하는 옵션은 관리되는 정책의 수와 정책을 할당하는 사용자 수에 따라 선택됩니다. 전역(조직 전체 기본값) 정책은 조직에서 가장 많은 수의 사용자에게 적용됩니다. 특수한 정책이 필요한 사용자에게만 정책을 할당하면 됩니다.

이 문서에서는 사용자에게 정책을 할당할 수 있는 다양한 방법 및 권장되는 시나리오를 사용하는 경우를 설명합니다.

## <a name="which-policy-takes-precedence"></a>어떤 정책이 우선하나요?

사용자에게는 각 정책 유형에 대한 하나의 유효 정책이 있습니다. 사용자에게 정책이 직접 할당되어 있으며 동일한 유형의 정책이 할당된 하나 이상의 그룹의 구성원일 수도 있습니다. 이러한 종류의 시나리오에서 어떤 정책이 우선할까요? 사용자의 유효 정책은 다음과 같이 우선 순위 규칙에 따라 결정됩니다.

사용자에게 정책이 직접 할당된 경우(개별적으로 또는 일괄 처리 할당을 통해) 해당 정책이 우선합니다. 다음 시각적 예제에서 사용자의 효과적인 정책은 사용자에게 직접 할당되는 Lincoln Square 모임 정책입니다.

![직접 할당된 정책이 어떻게 우선하는지 보여주는 다이어그램](media/assign-policies-example-directly-assigned.png)

사용자에게 지정된 유형의 정책이 직접 할당되지 않은 경우 사용자가 구성원인 그룹에 할당된 정책이 우선합니다. 사용자가 여러 그룹의 구성원인 경우 해당 정책 유형에 대해 그룹 할당 순위가 가장 높은 정책이 우선합니다. [](#group-assignment-ranking)

이 시각적 예제에서 사용자의 유효 정책은 Exec Teams 및 HD 정책으로, 사용자가 구성원인 다른 그룹에 비해 할당 순위가 가장 높고 동일한 정책 유형의 정책도 할당됩니다.  

![그룹에서 상속된 정책이 어떻게 우선하는지 보여주는 다이어그램](media/assign-policies-example-group.png)

사용자에게 정책이 직접 할당되지 않은 경우 또는 정책이 할당된 그룹의 구성원이 아닌 경우 사용자는 해당 정책 유형에 대한 전역(Org 전체 기본값) 정책을 얻습니다. 다음은 시각적 예제입니다.

![전역 정책이 어떻게 우선하는지 보여주는 다이어그램](media/assign-policies-example-global.png)

자세한 내용은 우선 순위 규칙을 [참조합니다.](#precedence-rules)

## <a name="ways-to-assign-policies"></a>정책을 할당하는 방법

다음은 사용자에게 정책을 할당할 수 있는 방법과 각각에 대한 권장 시나리오에 대한 개요입니다. 자세한 내용은 링크를 선택합니다.

개별 사용자 또는 그룹에 정책을 할당하기 전에 먼저 조직에서 가장 많은 수의 사용자에게 적용될 수 있도록 전역(조직 전체 [기본값)](#set-the-global-policies) 정책을 설정해야 합니다.  전역 정책이 설정되고 나면 특수한 정책이 필요한 사용자에게만 정책을 할당하면 됩니다.

|방법  |If...  | 사용 중...
|---------|---------|----|
|[개별 사용자에게 정책 할당](#assign-a-policy-to-individual-users)    | Teams를 시작하거나 소수의 사용자에게 정책 하나 또는 몇 개만 할당하면 됩니다. |비즈니스용 Skype Online PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet
|[그룹에 정책 할당](#assign-a-policy-to-a-group) |사용자의 그룹 멤버 자격에 따라 정책을 할당합니다. 예를 들어 보안 그룹 또는 메일 그룹의 모든 사용자에게 정책을 할당합니다.| Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet|
|[사용자 일괄 처리에 정책 할당](#assign-a-policy-to-a-batch-of-users)   | 대규모 사용자 집합에 정책을 할당합니다. 예를 들어 조직에서 수백 또는 수천 명의 사용자에게 한 번만에 정책을 할당합니다. |Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet|
| [사용자에게 정책 패키지 할당](#assign-a-policy-package-to-users)  |동일하거나 유사한 역할이 있는 조직의 특정 사용자 집합에 여러 정책을 할당합니다. 예를 들어 학교의 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 권한을 부여합니다. 보조 학생에게 교육(중등 학생) 정책 패키지를 할당하여 개인 통화와 같은 특정 기능을 제한합니다.  |Teams PowerShell 모듈의 Microsoft Teams 관리 센터 또는 PowerShell cmdlet|
| [그룹에 정책 패키지 할당(비공개](#assign-a-policy-package-to-a-group) 미리 보기)   |동일하거나 유사한 역할이 있는 조직의 사용자 그룹에 여러 정책을 할당합니다. 예를 들어 보안 그룹 또는 메일 그룹의 모든 사용자에게 정책 패키지를 할당합니다. |Teams PowerShell 모듈의 Microsoft Teams 관리 센터(출시 예정) 또는 PowerShell cmdlet|
| [사용자 일괄 처리에 정책 패키지 할당](#assign-a-policy-package-to-a-batch-of-users)|동일하거나 유사한 역할이 있는 조직의 사용자 일괄 처리에 여러 정책을 할당합니다. 예를 들어 일괄 처리 할당을 사용하여 학교의 모든 교사에게 교육(교사) 정책 패키지를 할당하여 채팅, 통화 및 모임에 대한 모든 권한을 부여합니다. 개인 통화와 같은 특정 기능을 제한하기 위해 보조 학생 일괄 처리에 교육(중등 학생) 정책 패키지를 할당합니다.|Teams PowerShell 모듈의 PowerShell cmdlet|

## <a name="set-the-global-policies"></a>전역 정책 설정

다음 단계에 따라 각 정책 유형에 대한 전역(전체 기본) 정책을 설정합니다.

### <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 업데이트하려는 정책 유형에 대한 정책 페이지로 이동합니다. 예를 들어 **Teams** Teams  >  **정책,** **모임** 모임 정책, 메시징 정책 또는 음성 통화  >      >  **정책이 있습니다.**
2. **전역(전체 기본값)** 정책을 선택하여 현재 설정을 확인합니다.
3. 필요한 경우 정책을 업데이트한 다음 적용을 **선택합니다.**

### <a name="using-powershell"></a>PowerShell 사용

PowerShell을 사용하여 전역 정책을 설정하기 위해 전역 식별자를 사용 합니다.  먼저 현재 전역 정책을 검토하여 변경할 설정을 결정해야 합니다.

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

다음으로, 필요한 경우 전역 정책을 업데이트합니다.  변경하려는 설정의 값만 지정하면 됩니다.

```powershell
Set-CsTeamsMessagingPolicy -Identity Global -AllowUserEditMessage $false
```

## <a name="assign-a-policy-to-individual-users"></a>개별 사용자에게 정책 할당

다음 단계에 따라 개별 사용자 또는 한에 소수의 사용자에게 정책을 할당합니다.

### <a name="use-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

사용자에게 정책을 할당하는 경우:

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **사용자로** 이동한 다음 사용자를 선택합니다.
2. 사용자 이름 왼쪽을 클릭하여 사용자를 선택한 다음 설정 **편집을 선택합니다.**
3. 할당할 정책을 선택한 다음 적용을 **선택합니다.**

또는 다음을 할 수도 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색에서 정책 페이지로 이동합니다.
2. 정책 이름 왼쪽을 클릭하여 할당할 정책을 선택합니다.
3. **사용자 관리** 를 선택합니다.
4. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요. 추가할 각 사용자에 대해 이 단계를 반복합니다.
5. 사용자 추가를 마쳤을 때 적용을 **선택합니다.**

### <a name="use-powershell"></a>PowerShell 사용

각 정책 유형에는 관리하기 위한 자체 cmdlet 집합이 있습니다. 특정 정책 유형에 ```Grant-``` cmdlet을 사용하여 정책을 할당합니다. 예를 들어 ```Grant-CsTeamsMeetingPolicy``` cmdlet을 사용하여 사용자에게 Teams 모임 정책을 할당합니다. 이러한 cmdlet은 비즈니스용 Skype Online PowerShell 모듈에 포함되어 있으며 비즈니스용 [Skype cmdlet 참조에 설명되어 있습니다.](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)

 비즈니스용 [Skype Online PowerShell](https://www.microsoft.com/download/details.aspx?id=39366) 모듈을 다운로드하여 설치한 다음(아직 설치하지 않은 경우) 다음을 실행하여 비즈니스용 Skype Online에 연결하고 세션을 시작하세요.

> [!NOTE]
> 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.
>
> 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.

```powershell
Import-Module -Name MicrosoftTeams
$Cred = Get-Credential
$CSSession = New-CsOnlineSession -Credential $Cred
Import-PSSession -Session $CSSession
```

이 예제에서는 Reda라는 사용자에게 학생 모임 정책이라는 Teams 모임 정책을 할당합니다.

```powershell
Grant-CsTeamsMeetingPolicy -Identity reda@contoso.com -PolicyName "Student Meeting Policy"
```

자세한 내용은 [PowerShell을 통해 정책 관리를 읽어보아야 합니다.](teams-powershell-managing-teams.md#manage-policies-via-powershell)

## <a name="assign-a-policy-to-a-group"></a>그룹에 정책 할당

그룹에 정책 할당을 사용하면 보안 그룹 또는 메일 그룹과 같은 사용자 그룹에 정책을 할당할 수 있습니다. 정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다. 그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.

그룹에 대한 정책 할당은 최대 50,000명 사용자 그룹에 권장되지만 더 큰 그룹에서도 사용할 수 있습니다.

정책을 할당하면 해당 정책이 그룹에 즉시 할당됩니다. 그러나 그룹의 구성원에게 정책 할당을 전파하는 작업은 백그라운드 작업으로 수행하며 그룹의 크기에 따라 다소 시간이 걸릴 수 있습니다. 그룹에서 정책이 재할당되지 않은 경우 또는 구성원이 그룹에 추가되거나 그룹에서 제거될 때도 마찬가지입니다.

그룹 정책 할당은 그룹의 직접 구성원인 사용자에게만 전파됩니다. 할당은 중첩된 그룹의 멤버에게 전파되지 않습니다.

### <a name="what-you-need-to-know-about-policy-assignment-to-groups"></a>그룹에 정책 할당에 대해 알아야 할 정보

시작하기 전에 우선 순위 규칙 및 그룹 할당 순위를 이해하는 것이 중요합니다.

#### <a name="precedence-rules"></a>우선 순위 규칙

주어진 정책 유형에 대해 사용자의 유효 정책은 다음에 따라 결정됩니다.

- 사용자에게 직접 할당된 정책이 그룹에 할당된 동일한 유형의 다른 정책보다 우선합니다. 즉, 사용자에게 지정된 형식의 정책이 직접 할당된 경우 해당 사용자는 그룹에서 동일한 형식의 정책을 상속하지 않습니다. 즉, 사용자에게 직접 할당된 지정된 형식의 정책이 있는 경우 그룹에서 동일한 형식의 정책을 상속하려면 먼저 사용자로부터 해당 정책을 제거해야 합니다.
- 사용자에게 직접 할당된 정책이 없고 둘 이상의 그룹의 구성원이고 각 그룹에 할당된 동일한 유형의 정책이 있는 경우 사용자는 가장 높은 순위를 가지는 그룹 할당의 정책을 상속합니다.
- 사용자가 정책이 할당된 그룹의 구성원이 아닌 경우 해당 정책 유형에 대한 전역(전체 기본값) 정책이 사용자에게 적용됩니다.

사용자의 유효 정책은 다음 규칙에 따라 업데이트됩니다.

- 사용자가 정책이 할당된 그룹에 추가되거나 제거되는 경우
- 그룹에서 정책이 재할당되지 않습니다.
- 사용자에게 직접 할당된 정책이 제거됩니다.

#### <a name="group-assignment-ranking"></a>그룹 할당 순위

그룹에 정책을 할당할 때 그룹 할당에 대한 순위를 지정합니다. 이 정책은 사용자가 둘 이상의 그룹의 구성원이고 각 그룹에 동일한 유형의 정책이 할당된 경우 사용자가 유효 정책으로 상속해야 하는 정책을 결정하는 데 사용됩니다.

그룹 할당 순위는 동일한 유형의 다른 그룹 할당에 상대적입니다. 예를 들어 호출 정책을 두 그룹에 할당하는 경우 한 할당의 순위를 1로 설정하고 다른 할당은 2로 설정하고 1은 가장 높은 순위로 설정합니다. 그룹 할당 순위는 상속과 관련하여 다른 그룹 멤버 자격보다 더 중요하거나 관련성이 높은 그룹 멤버 자격을 나타냅니다.

예를 들어 두 개의 그룹인 Store Employees와 Store Manager가 있습니다. 두 그룹에는 Teams 통화 정책, 스토어 직원 통화 정책 및 스토어 관리자 통화 정책이 각각 할당됩니다. 두 그룹에 모두 있는 스토어 관리자의 경우 관리자 역할은 직원 역할보다 관련성이 높기 때문에 스토어 관리자 그룹에 할당된 호출 정책의 순위가 더 높아야 합니다.

|그룹 |정책 이름을 호출하는 팀  |순위|
|---------|---------|---|
|스토어 관리자   |스토어 관리자 호출 정책         |1|
|직원 저장    |직원 호출 정책 저장      |2|

순위를 지정하지 않으면 정책 할당에 가장 낮은 순위가 지정됩니다.

### <a name="in-the-teams-admin-center"></a>Teams 관리 센터에서

> [!NOTE]
> 현재 Microsoft Teams 관리 센터를 사용하는 그룹에 대한 정책 할당은 Teams 통화 정책, Teams 호출 공원 정책, Teams 정책, Teams 라이브 이벤트 정책, Teams 모임 정책 및 Teams 메시징 정책에만 사용할 수 있습니다. 다른 정책 형식의 경우 PowerShell을 사용 합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 정책 유형 페이지로 이동합니다. 예를 들어 모임 모임  >  **정책으로 이동**
2. 그룹 **정책 할당 탭을** 선택합니다.
3. 그룹 **추가를 선택하고** 그룹 창에 정책 할당 **창에서** 다음을 합니다.
    1. 정책을 할당할 그룹을 검색하고 추가합니다.
    2. 그룹 할당의 순위를 지정합니다.
    3. 할당하려는 정책을 선택합니다.
    4. 적용을 **선택합니다.**

그룹 정책 할당을 제거하려면  정책 페이지의 그룹 정책 할당 탭에서 그룹 할당을 선택한 다음 제거를 **선택합니다.**

그룹 할당의 순위를 변경하려면 먼저 그룹 정책 할당을 제거해야 합니다. 그런 다음 위의 단계에 따라 그룹에 정책을 할당합니다.

### <a name="use-the-powershell-option"></a>PowerShell 옵션 사용

> [!NOTE]
> 현재 PowerShell을 사용하는 그룹에 대한 정책 할당은 모든 Teams 정책 유형에서 사용할 수 없습니다. 지원되는 정책 유형 목록은 [New-CsGroupPolicyAssignment를](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) 참조하세요.

#### <a name="install-and-connect-to-the-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell 모듈 설치 및 연결

단계별 지침은 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)

#### <a name="assign-a-policy-to-a-group-of-users"></a>사용자 그룹에 정책 할당

[New-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/new-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 정책을 할당합니다. 개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다.

이 예제에서는 할당 순위가 1인 그룹에 Retail Managers 모임 정책이라는 Teams 모임 정책을 할당합니다.

```powershell
New-CsGroupPolicyAssignment -GroupId d8ebfa45-0f28-4d2d-9bcc-b158a49e2d17 -PolicyType TeamsMeetingPolicy -PolicyName "Retail Managers Meeting Policy" -Rank 1
```

#### <a name="get-policy-assignments-for-a-group"></a>그룹에 대한 정책 할당을 얻습니다.

[Get-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csgrouppolicyassignment) cmdlet을 사용하여 그룹에 할당된 모든 정책을 얻습니다. 정책을 할당하는 데 SIP 주소 또는 전자 메일 주소가 사용된 경우에도 그룹은 항상 그룹 ID로 나열됩니다.

이 예제에서는 특정 그룹에 할당된 모든 정책을 검색합니다.

```powershell
Get-CsGroupPolicyAssignment -GroupId e050ce51-54bc-45b7-b3e6-c00343d31274
```

이 예제에서는 Teams 모임 정책이 할당된 모든 그룹을 반환합니다.

```powershell
Get-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy
```

#### <a name="remove-a-policy-from-a-group"></a>그룹에서 정책 제거

[Remove-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/remove-csgrouppolicyassignment) cmdlet을 사용하여 그룹에서 정책을 제거합니다. 그룹에서 정책을 제거하면 해당 그룹에 할당된 동일한 유형의 다른 정책의 우선 순위가 업데이트됩니다. 예를 들어 순위가 2인 정책을 제거하면 순위가 3과 4인 정책이 새 순위를 반영하여 업데이트됩니다. 다음 두 표에서는 이 예제를 보여 주겠습니다.

다음은 Teams 모임 정책에 대한 정책 할당 및 우선 순위 목록입니다.

|그룹 이름  |정책 이름  |순위|
|---------|---------|---------|
|영업    |판매 정책       | 1        |
|서부 지역     |서부 지역 정책         |2         |
|Division    |부서 정책         |3         |
|자회사   |자회사 정책        |4         |

서부 지역 그룹에서 서부 지역 정책을 제거하면 정책 할당 및 우선 순위가 다음과 같이 업데이트됩니다.

|그룹 이름  |정책 이름  |순위|
|---------|---------|---------|
|영업    |판매 정책       | 1        |
|Division    |부서 정책         |2         |
|자회사   |자회사 정책        |3        |

이 예제에서는 그룹에서 Teams 모임 정책을 제거합니다.

```powershell
Remove-CsGroupPolicyAssignment -PolicyType TeamsMeetingPolicy -GroupId f985e013-0826-40bb-8c94-e5f367076044
```

#### <a name="change-a-policy-assignment-for-a-group"></a>그룹에 대한 정책 할당 변경

> [!NOTE]
> [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 곧 사용할 수 있습니다. 그동안 그룹 정책 할당을 변경하려면 그룹에서 현재 정책 할당을 제거한 다음 새 정책 할당을 추가할 수 있습니다.

그룹에 정책을 할당한 후 [Set-CsGroupPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/set-csgrouppolicyassignment) cmdlet을 사용하여 다음과 같이 해당 그룹의 정책 할당을 변경할 수 있습니다.

- 순위 변경
- 주어진 정책 유형의 정책 변경
- 주어진 정책 유형 및 순위의 정책 변경

이 예제에서는 그룹의 Teams 호출 공원 정책을 SupportCallPark라는 정책으로 변경하고 배정 순위를 3으로 변경합니다.

```powershell
Set-CsGroupPolicyAssignment -GroupId 566b8d39-5c5c-4aaa-bc07-4f36278a1b38 -PolicyType TeamsMeetingPolicy -PolicyName SupportCallPark -Rank 3
```

#### <a name="change-the-effective-policy-for-a-user"></a>사용자에 대한 유효 정책 변경

정책이 직접 할당된 사용자에 대한 유효 정책을 변경하는 방법의 예는 다음과 같습니다.

먼저 [Get-CsUserPolicyAssignment](https://docs.microsoft.com/powershell/module/teams/get-csuserpolicyassignment) cmdlet을 매개 변수와 함께 사용하여 사용자와 연결된 Teams 모임 브로드캐스트 정책의 세부 정보를 ```PolicySource``` 얻습니다.

```powershell
Get-CsUserPolicyAssignment -Identity daniel@contoso.com -PolicyType TeamsMeetingBroadcastPolicy | select -ExpandProperty PolicySource
```

출력은 사용자가 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트라는 정책보다 우선하는 직원 이벤트라는 Teams 모임 브로드캐스트 정책에 직접 할당된 것으로 표시됩니다.

```console
AssignmentType PolicyName         Reference
-------------- ----------         ---------
Direct         Employee Events
Group          Vendor Live Events 566b8d39-5c5c-4aaa-bc07-4f36278a1b38
```

이제 사용자에서 직원 이벤트 정책을 제거합니다. 즉, 사용자에게 더 이상 직접 할당된 Teams 모임 브로드캐스트 정책이 없고 사용자가 속한 그룹에 할당된 공급업체 라이브 이벤트 정책을 상속합니다.

비즈니스용 Skype PowerShell 모듈에서 다음 cmdlet을 사용하여 이 작업을 합니다.

```powershell
Grant-CsTeamsMeetingBroadcastPolicy -Identity daniel@contoso.com -PolicyName $null
```

Teams PowerShell 모듈에서 다음 cmdlet을 사용하여 사용자가 지정한 사용자 목록인 $users 정책 할당을 통해 대규모로 이 작업을 수행하세요.

```powershell
New-CsBatchPolicyAssignmentOperation -OperationName "Assigning null at bulk" -PolicyType TeamsMeetingBroadcastPolicy -PolicyName $null -Identity $users  
```

## <a name="assign-a-policy-to-a-batch-of-users"></a>사용자 일괄 처리에 정책 할당

### <a name="use-the-admin-center"></a>관리 센터 사용

사용자에게 정책을 일괄 할당하는 경우:

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 사용자를 **선택합니다.**
2. 정책을 할당하려는 사용자를 검색하거나 보기를 필터링하여 원하는 사용자를 표시합니다.
3. **&#x2713;**(확인 표시) 열에서 사용자를 선택합니다. 모든 사용자를 선택하려면 표 맨 위에서 &#x2713;(확인 표시)를 클릭합니다.
4. 설정 **편집을 선택하고** 원하는 내용을 변경한 다음 적용을 **선택합니다.**

정책 할당의 상태를 확인하려면 [적용]을 선택하여 정책  할당을 제출한  후 사용자 페이지 맨 위에 나타나는 배너에서 활동 **로그를 선택합니다.** 또는 Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 대시보드로 이동한 다음 **활동** 로그에서 **세부** 정보 **보기를 선택합니다.** 활동 로그에는 지난 30일 동안 Microsoft Teams 관리 센터를 통해 20명 이상의 사용자 배치에 대한 정책 할당이 표시됩니다. 자세한 내용은 활동 로그에서 정책 할당 [보기를 참조합니다.](activity-log.md)

### <a name="use-powershell-method"></a>PowerShell 메서드 사용

> [!NOTE]
> 현재 PowerShell을 사용한 일괄 처리 정책 할당은 모든 Teams 정책 유형에서 사용할 수 없습니다. 지원되는 정책 유형 목록은 [New-CsBatchPolicyAssignmentOperation을](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) 참조하세요.

일괄 처리 정책 할당을 사용하면 스크립트를 사용하지 않고도 한에 대규모 사용자 집합에 정책을 할당할 수 있습니다. [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 할당하려는 사용자 및 정책의 일괄 처리를 제출합니다. 할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다. 그런 다음 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 할당의 진행률 및 상태를 추적할 수 있습니다.

개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정합니다. 사용자의 SIP 주소는 UPN(사용자 계정 이름) 또는 전자 메일 주소와 같은 값을 자주 사용하지만 필수는 아닙니다. 사용자가 UPN 또는 전자 메일을 사용하여 지정했지만 해당 SIP 주소와 다른 값을 사용하는 경우 사용자에 대한 정책 할당이 실패합니다. 일괄 처리에 중복된 사용자가 포함된 경우 처리 전에 중복된 사용자가 일괄 처리에서 제거되고, 상태는 일괄 처리에 남아 있는 고유 사용자에 대해만 제공됩니다.

배치에는 최대 5천 명의 사용자가 포함될 수 있습니다. 최상의 결과를 위해 한에 몇 개 이상의 일괄 처리를 제출하지 않습니다. 더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.

#### <a name="install-and-connect-to-the-teams-powershell-module"></a>Teams PowerShell 모듈 설치 및 연결

다음을 실행하여 [Microsoft Teams PowerShell 모듈을 설치합니다.](https://www.powershellgallery.com/packages/MicrosoftTeams) 버전 1.0.5 이상을 설치해야 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행하여 Teams에 연결하고 세션을 시작합니다.

```powershell
Connect-MicrosoftTeams
```

메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.

#### <a name="install-and-connect-to-the-azure-ad-powershell-for-graph-module-optional"></a>Graph 모듈용 Azure AD PowerShell 설치 및 연결(선택 사항)

또한 Azure [AD PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) 모듈(아직 없는 경우)을 다운로드하여 설치하고 조직의 사용자 목록을 검색할 수 있도록 Azure AD에 연결할 수도 있습니다.

다음을 실행하여 Azure AD에 연결합니다.

```powershell
Connect-AzureAD
```

메시지가 표시될 때 Teams에 연결하는 데 사용한 동일한 관리자 자격 증명을 사용하여 로그인합니다.

#### <a name="assign-a-setup-policy-to-a-batch-of-users"></a>사용자 일괄 처리에 설정 정책 할당

이 예제에서는 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 Users_ids.text 파일에 나열된 사용자 배치에 HR 앱 설정 정책이라는 앱 설정 정책을 할당합니다.

```powershell
$user_ids = Get-Content .\users_ids.txt
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $users_ids -OperationName "Example 1 batch"
```

이 예제에서는 Azure AD에 연결하여 사용자 컬렉션을 검색한 다음, 해당 SIP 주소를 사용하여 지정된 사용자 배치에 New Hire Messaging Policy라는 메시징 정책을 할당합니다.

```powershell
Connect-AzureAD
$users = Get-AzureADUser
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMessagingPolicy -PolicyName "New Hire Messaging Policy" -Identity $users.SipProxyAddress -OperationName "Example 2 batch"
```

#### <a name="get-the-status-of-a-batch-assignment"></a>일괄 처리 할당의 상태 확인

다음을 실행하여 일괄 처리 할당의 상태를 얻습니다. 여기서 OperationId는 주어진 일괄 처리에 대한 cmdlet에서 반환되는 작업 ```New-CsBatchPolicyAssignmentOperation``` ID입니다.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

출력에 오류가 발생한 것으로 표시되는 경우 다음을 실행하여 속성에 있는 오류에 대한 자세한 정보를 ```UserState``` 얻습니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

자세한 내용은 [Get-CsBatchPolicyAssignmentOperation을 참조합니다.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="assign-a-policy-package-to-users"></a>사용자에게 정책 패키지 할당

Teams의 정책 패키지는 조직에서 동일하거나 유사한 역할이 있는 사용자에게 할당할 수 있는 미리 정의된 정책 및 정책 설정의 컬렉션입니다. 각 정책 패키지는 사용자 역할을 중심으로 디자인된 것으로, 해당 역할에 대한 일반적인 활동을 지원하는 미리 정의된 정책 및 정책 설정을 포함합니다. 정책 패키지의 몇 가지 예로 Education(교사) 패키지 및 의료(의료 서비스) 패키지가 있습니다. 자세한 내용은 Teams에서 정책 [패키지 관리를 참조합니다.](manage-policy-packages.md)

### <a name="assign-a-policy-package-to-one-user"></a>한 사용자에게 정책 패키지 할당

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **사용자로** 이동한 다음 사용자를 선택합니다.
2. 사용자의 페이지에서 정책을 선택한 다음 **정책** 패키지 옆에 있는 **편집을** **선택합니다.**
3. 정책 패키지 **할당 창에서** 할당할 패키지를 선택한 다음 저장을 **선택합니다.**

### <a name="assign-a-policy-package-to-multiple-users"></a>여러 사용자에게 정책 패키지 할당

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 정책 패키지로 이동한 다음 패키지 이름 왼쪽을 클릭하여 할당하려는 정책 패키지를 선택합니다.
2. **사용자 관리** 를 선택합니다.
3. **사용자 관리** 창에서 표시 이름 또는 사용자 이름으로 사용자를 검색하고 이름을 선택한 다음, **추가** 를 선택하세요. 추가할 각 사용자에 대해 이 단계를 반복합니다.
4. 사용자 추가를 마쳤을 때 저장을 **선택합니다.**

## <a name="assign-a-policy-package-to-a-group"></a>그룹에 정책 패키지 할당

**이 기능은 비공개 리미 보기에 있습니다.**

그룹에 정책 패키지 할당을 사용하면 보안 그룹이나 배포 목록과 같은 사용자 그룹에 여러 정책을 할당할 수 있습니다. 정책 할당은 선행 규칙에 따라 그룹의 구성원에게 전파됩니다. 그룹에서 구성원이 추가되거나 제거되면 상속된 정책 할당이 그에 따라 업데이트됩니다.

그룹에 대한 정책 패키지 할당은 최대 50,000명 사용자 그룹에 권장되지만 더 큰 그룹에서도 사용할 수 있습니다.

정책 패키지를 할당하면 즉시 그룹에 할당됩니다. 그러나 그룹의 구성원에게 정책 할당을 전파하는 작업은 백그라운드 작업으로 수행하며 그룹의 크기에 따라 다소 시간이 걸릴 수 있습니다. 그룹에서 정책이 재할당되지 않은 경우 또는 구성원이 그룹에 추가되거나 그룹에서 제거될 때도 마찬가지입니다.

> [!IMPORTANT]
> 시작하기 전에 우선 순위 규칙 및 [](#precedence-rules) 그룹 할당 순위를 [이해하는 것이 중요합니다.](#group-assignment-ranking) 이 문서의 앞부분에서 그룹에 정책 할당에 대해 알아야 할 [개념을](#what-you-need-to-know-about-policy-assignment-to-groups) 읽고 이해해야 합니다.

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a>관리 센터에서 사용자 그룹에 정책 패키지 할당

1. Teams 관리 센터에 로그인합니다.
2. 왼쪽 탐색에서 정책 패키지 페이지로 이동합니다.
3. 그룹 정책 할당 탭을 선택합니다.
4. 그룹 **추가를 선택하고** 그룹 창에 정책 패키지 할당에서 다음을 합니다.

    a. 정책 패키지를 할당하려는 그룹을 검색하고 추가합니다.

    b. 정책 패키지를 선택합니다.

    c. 각 정책 유형에 대한 순위를 설정합니다.

    d. 적용을 **선택합니다.**

    ![그룹 정책 할당 표시](media/group-pkg-assignment.png)

5. 특정 정책 유형에 대한 순위를 관리하기 위해 특정 정책 페이지로 이동합니다.
6. 정책 패키지를 그룹에 다시 할당하려면 먼저 그룹 정책 할당을 제거합니다. 그런 다음 위의 단계에 따라 정책 패키지를 그룹에 할당합니다.

### <a name="work-with-powershell"></a>PowerShell 작업

#### <a name="get-the-teams-powershell-module"></a>Teams PowerShell 모듈을 얻게 됩니다.

단계별 지침은 [Teams PowerShell 설치를 참조하세요.](teams-powershell-install.md)

#### <a name="assign-a-policy-package-to-a-group-of-users"></a>사용자 그룹에 정책 패키지 할당

[Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet을 사용하여 정책 패키지를 그룹에 할당합니다. 개체 ID, SIP 주소 또는 전자 메일 주소를 사용하여 그룹을 지정할 수 있습니다. 정책 패키지를 할당할 때 [](#group-assignment-ranking) 정책 패키지의 각 정책 유형에 대한 그룹 할당 순위를 지정합니다.

이 예제에서는 TeamsAppSetupPolicy 및 TeamsMeetingBroadcastPolicy에 대한 할당 순위가 1인 그룹에 Education_Teacher 정책 패키지를 할당하고 TeamsMeetingPolicy에 대한 순위가 2인 그룹에 할당합니다.

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a>사용자 일괄 처리에 정책 패키지 할당

일괄 처리 정책 패키지 할당을 사용하면 스크립트를 사용하지 않고도 한에서 대규모 사용자 집합에 정책 패키지를 할당할 수 있습니다. [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 할당하려는 사용자 및 정책 패키지의 일괄 처리를 제출합니다. 할당은 백그라운드 작업으로 처리되고 각 배치에 작업 ID가 생성됩니다. 그런 다음 [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet을 사용하여 일괄 처리에서 할당의 진행률 및 상태를 추적할 수 있습니다.

개체 ID 또는 SIP(세션 시작 프로토콜) 주소로 사용자를 지정합니다. 사용자의 SIP 주소는 UPN(사용자 계정 이름) 또는 전자 메일 주소와 같은 값을 자주 사용하지만 필수는 아닙니다. 사용자가 UPN 또는 전자 메일을 사용하여 지정했지만 해당 SIP 주소와 다른 값을 사용하는 경우 사용자에 대한 정책 할당이 실패합니다. 일괄 처리에 중복된 사용자가 포함된 경우 처리 전에 중복된 사용자가 일괄 처리에서 제거되고, 상태는 일괄 처리에 남아 있는 고유 사용자에 대해만 제공됩니다.

일괄 처리에는 최대 5,000명이 포함되어 있습니다. 최상의 결과를 위해 한에 몇 개 이상의 일괄 처리를 제출하지 않습니다. 더 많은 일괄 처리를 제출하기 전에 일괄 처리가 완료될 수 있도록 허용합니다.

### <a name="use-the-teams-powershell-module"></a>Teams PowerShell 모듈 사용

다음을 실행하여 [Microsoft Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 모듈을 설치합니다(아직 설치하지 않은 경우). 버전 1.0.5 이상을 설치해야 합니다.

```powershell
Install-Module -Name MicrosoftTeams
```

다음을 실행하여 Teams에 연결하고 세션을 시작합니다.

```powershell
Connect-MicrosoftTeams
```

메시지가 표시될 때 관리자 자격 증명을 사용하여 로그인합니다.

### <a name="assign-policy-packages-to-a-batch-of-users"></a>사용자 일괄 처리에 정책 패키지 할당

이 예제에서는 [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet을 사용하여 Education_PrimaryStudent 정책 패키지를 사용자 일괄 처리에 할당합니다.

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a>일괄 처리 할당의 상태 확인

다음을 실행하여 일괄 처리 할당의 상태를 얻습니다. 여기서 OperationId는 주어진 일괄 처리에 대한 cmdlet에서 반환되는 작업 ```New-CsBatchPolicyAssignmentOperation``` ID입니다.

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

출력에 오류가 발생한 것으로 표시되는 경우 다음을 실행하여 속성에 있는 오류에 대한 자세한 정보를 ```UserState``` 얻습니다.

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

자세한 내용은 [Get-CsBatchPolicyAssignmentOperation을 참조합니다.](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation)

## <a name="related-topics"></a>관련 주제

[Teams PowerShell 개요](teams-powershell-overview.md)
