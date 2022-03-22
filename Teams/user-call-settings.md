---
title: 사용자에 대한 호출 설정 구성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: 통화 전달 및 위임에 대한 사용자 설정을 구성하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 5443ad958d23753b1d67d42782ddab41d9d6d080
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2022
ms.locfileid: "63689120"
---
# <a name="configure-call-settings-for-your-users"></a>사용자에 대한 호출 설정 구성

이 문서에서는 관리자인 사용자가 사용자에 대한 통화 전달 및 위임 설정을 변경할 수 있는 방법을 설명합니다. 다음과 같은 경우 이러한 설정을 변경할 수 있습니다.

- 사용자가 병가를 떠날 때 사용자에 대한 들어오는 호출이 동료에게 전달되도록 해야 합니다.

- 부서의 모든 사용자에 대한 통화 전달 설정을 검사하고 적절하게 수정해야 합니다.

- 새 도우미가 고용되고 직원 그룹에 대한 대리인으로 도우미를 추가해야 합니다.

PowerShell cmdlet을 Teams Teams 또는 PowerShell cmdlet을 사용하여 사용자에 대한 통화 설정을 보고 변경할 수 있습니다.

사용자에 대한 호출 설정을 설정하려면 사용자에게 할당된 시스템 Microsoft 전화 있어야 합니다.

## <a name="use-the-teams-admin-center"></a>관리 Teams 사용

관리자 센터를 사용하여 Teams 그룹 호출 픽업을 구성하고 사용자에 대한 위임을 호출할 수 있습니다. 

> [!NOTE]
> 통화 전달 설정을 구성하는 옵션은 현재 관리 센터에서 사용할 Teams 없습니다.

그룹 호출 픽업을 구성하는 경우:

1. 관리 Teams **사용자** > 로 이동하여 사용자를 선택합니다.

2. 사용자 세부 정보 페이지에서 음성 **탭으로 이동합니다** .

3. 그룹 **호출 픽업에서** 사람 **추가를 선택합니다**. 

4. 통화 지연 및 **주문에 대한 설정을 지정합니다**.

위임 구성을 구성하려면 동일한 페이지에서 위임 호출로 이동 **하고 사용자 추가****를 선택합니다**.

## <a name="use-powershell"></a>PowerShell 사용

PowerShell을 사용하여 사용자에 대한 통화 전달 및 위임 설정을 구성할 수 있습니다.  PowerShell 모듈 버전 4.0 이상에서 사용할 수 있는 Teams cmdlet을 사용합니다.

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) - 사용자에 대한 통화 전달 설정, 대리인 및 위임자 정보를 보여줍니다.

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) - 사용자에 대한 통화 전달 설정을 설정합니다.

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) - 사용자에 대한 사용 권한이 있는 새 대리인을 추가합니다.

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) - 기존 대리인에 대한 사용 권한을 변경합니다.

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) - 사용자에서 대리인을 제거합니다.


### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>사용자에 대한 통화 전달 및 위임 설정 표시

사용자에 대한 현재 호출 전달 및 위임 설정을 표시하려면 다음 예제와 Get-CsUserCallingSettings cmdlet을 사용합니다.

```PowerShell
Get-CsUserCallingSettings -Identity user1@contoso.com
SipUri                    : sip:opr1@contoso.com
IsForwardingEnabled       : True
ForwardingType            : Simultaneous
ForwardingTarget          :
ForwardingTargetType      : MyDelegates
IsUnansweredEnabled       : True
UnansweredTarget          :
UnansweredTargetType      : Voicemail
UnansweredDelay           : 00:00:20
Delegates                 : Id:user2@contoso.com
Delegators                : 
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

출력은 user1이 구성된 대리인에게 동시 벨소리가 있는 경우를 보여줍니다. 20초 후에 음성 메일로 전송됩니다. User2는 모든 대리인 권한이 있는 대리인으로 정의됩니다.


### <a name="set-call-forward-settings-for-a-user"></a>사용자에 대한 통화 전달 설정 설정

user1에 대한 모든 호출을 user2로 전달하기 위해 다음 예제와 Set-CsUserCallingSettings cmdlet을 사용 합니다. 

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

user3에 대한 모든 대리자를 동시에 링하기 위해 다음 예제와 Set-CsUserCallingSettings cmdlet을 사용 합니다. 

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

다음 예제에서는 Set-CsUserCallingSettings cmdlet을 사용하여 user5 및 user6를 구성원으로 사용하여 user4에 대한 호출 그룹을 구성합니다. 그룹의 구성원에 대한 모든 호출은 정의된 순서대로 전달됩니다. 

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

자세한 예제는 [Set-CsUserCallingSettings를 참조합니다](/powershell/module/teams/get-csusercallingsettings?view=teams-ps).

### <a name="add-a-calling-delegate-for-a-user"></a>사용자에 대한 호출 대리인 추가

모든 사용 권한이 허용된 user1의 대리인으로 user2를 추가하려면 다음 예제와 New-CsUserCallingDelegate cmdlet을 사용 합니다. 

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>대리자 권한 호출 변경

대리자 권한을 변경하려면- 예를 들어 user2가 user1에 대한 호출을 허용하지 못하도록 합니다. 다음 예제와 같이 Set-CsUserCallingDelegate cmdlet을 사용 

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>사용자에 대한 호출 대리인 제거

user1의 대리인으로 user2를 제거하려면 다음 예제와 Remove-CsUserCallingDelegate cmdlet을 사용 합니다. 

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```


## <a name="related-topics"></a>관련 주제

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings?view=teams-ps) 

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings?view=teams-ps) 

- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate?view=teams-ps) 

-   [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate?view=teams-ps) 

-   [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate?view=teams-ps) 
