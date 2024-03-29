---
title: 사용자에 대한 통화 설정 구성
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
audience: Admin
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
description: 통화 전달 및 위임에 대한 사용자 설정을 구성하는 방법을 알아봅니다.
ms.openlocfilehash: 7d1ab3252461d57a99956c90a011a43620c76bea
ms.sourcegitcommit: 18e66d54a9e349d4516253addc85cc12892c69a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2022
ms.locfileid: "68851849"
---
# <a name="configure-call-settings-for-your-users"></a>사용자에 대한 통화 설정 구성

이 문서에서는 관리자가 사용자의 통화 전달 및 위임 설정을 변경하는 방법을 설명합니다. 다음과 같은 경우 이러한 설정을 변경할 수 있습니다.

- 사용자가 병가를 내고 있으며, 사용자에게 들어오는 전화가 동료에게 전달되도록 해야 합니다.
- 부서의 모든 사용자에 대한 착신 전환 설정을 검사하고 적절하게 수정해야 합니다.
- 새 도우미가 고용되었으며 직원 그룹의 대리인으로 도우미를 추가해야 합니다.

Teams 관리 센터 또는 Teams PowerShell cmdlet을 사용하여 사용자의 통화 설정을 보고 변경할 수 있습니다.

사용자에 대한 통화 설정을 설정하려면 사용자에게 할당된 Microsoft 전화 시스템 라이선스가 있어야 합니다.

## <a name="use-the-teams-admin-center"></a>Teams 관리 센터 사용

Teams 관리 센터를 사용하여 통화 전달 및 응답되지 않은 설정을 구성하고, 통화 픽업을 그룹화하고, 사용자를 위한 통화 위임을 구성할 수 있습니다.

즉시 통화 전달 설정을 구성하려면 다음을 수행합니다.

1. Teams 관리 센터에서 **사용자 관리 사용자**  >  로 이동하여 사용자를 선택합니다.

2. 사용자 세부 정보 페이지에서 **음성** 탭으로 이동합니다.

3. **통화 응답 규칙** 에서 **즉시 전달을** 선택하고 적절한 전달 유형 및 대상을 선택합니다.

동시 벨소리를 구성하려면 동일한 페이지에서 **사용자의 디바이스 연결을** 선택합니다. **또한 허용** 드롭다운에서 적절한 동시 벨소리 설정을 선택합니다.

응답되지 않은 설정을 구성하려면 같은 페이지에서 **응답이 없는 경우** 드롭다운에서 적절한 설정을 선택합니다. 드롭다운을 **리디렉션하기 전에 이 여러 초 동안 링** 에서 대기할 시간(초)을 지정합니다.

통화 위임 및 그룹 통화 픽업의 구성은 적절한 유형을 선택하여 통화 전달 및 응답되지 않은 설정에 통합됩니다. 예를 들어 호출이 사용자의 대리자를 울리도록 구성하려면 동일한 페이지에서 **또한 허용** 에서 **통화 위임** 을 선택합니다. 그런 다음 **, 사용자 추가** 를 선택하고 **저장** 을 클릭하여 적절한 대리자를 추가합니다.

이 비디오에서는 사용자의 음성 설정을 보고 편집하는 단계를 보여줍니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE546F7?autoplay=false]

## <a name="use-powershell"></a>PowerShell 사용

PowerShell을 사용하여 사용자에 대한 통화 전달 및 위임 설정을 구성할 수 있습니다.  Teams PowerShell 모듈 버전 4.0 이상에서 사용할 수 있는 다음 cmdlet을 사용합니다.

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings) - 사용자에 대한 착신 전환 설정, 대리자 및 위임자 정보를 표시합니다.
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings) - 사용자에 대한 착신 전환 설정을 설정합니다.
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate) - 사용자에 대한 권한이 있는 새 대리자를 추가합니다.
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate) - 기존 대리자에 대한 권한을 변경합니다.
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate) - 사용자로부터 대리자를 제거합니다.

### <a name="display-call-forward-and-delegation-settings-for-a-user"></a>사용자에 대한 전화 전달 및 위임 설정 표시

사용자의 현재 호출 전달 및 위임 설정을 표시하려면 다음 예제와 같이 Get-CsUserCallingSettings cmdlet을 사용합니다.

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
Delegates                 : Id:sip:user2@contoso.com
Delegators                :
CallGroupOrder            : InOrder
CallGroupTargets          : {}
GroupMembershipDetails    :
GroupNotificationOverride : Ring

(Get-CsUserCallingSettings -Identity user1@contoso.com).Delegates

Id             : sip:user2@contoso.com
MakeCalls      : True
ManageSettings : True
ReceiveCalls   : True
```

출력은 user1이 구성된 대리자를 동시에 울리는 것을 보여 줍니다. 응답되지 않은 통화는 20초 후에 음성 메일로 전송됩니다. User2는 모든 대리자 권한이 있는 대리자로 정의됩니다.

### <a name="set-call-forward-settings-for-a-user"></a>사용자에 대한 통화 전달 설정 설정

user1에 대한 모든 호출을 user2로 전달하려면 다음 예제와 같이 Set-CsUserCallingSettings cmdlet을 사용합니다.

```PowerShell
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType SingleTarget -ForwardingTarget user2@contoso.com
```

user3에 대한 모든 대리자를 동시에 울리려면 다음 예제와 같이 Set-CsUserCallingSettings cmdlet을 사용합니다.

```PowerShell
Set-CsUserCallingSettings -Identity user3@contoso.com -IsForwardingEnabled $true -ForwardingType Simultaneous -ForwardingTargetType MyDelegates
```

다음 예제에서는 Set-CsUserCallingSettings cmdlet을 사용하여 user5 및 user6을 멤버로 사용하는 user4에 대한 호출 그룹을 구성합니다. 그룹의 멤버에 대한 모든 호출은 정의된 순서대로 전달됩니다.

```PowerShell
$cgm = @("user5@contoso.com","user6@contoso.com")

Set-CsUserCallingSettings -Identity user4@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm

Set-CsUserCallingSettings -Identity user4@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

자세한 예제는 [Set-CsUserCallingSettings를 참조하세요](/powershell/module/teams/get-csusercallingsettings).

### <a name="add-a-calling-delegate-for-a-user"></a>사용자에 대한 호출 대리자 추가

모든 권한이 허용되는 user1의 대리자로 user2를 추가하려면 다음 예제와 같이 New-CsUserCallingDelegate cmdlet을 사용합니다.

```PowerShell
New-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $true -ReceiveCalls $true -ManageSettings $true
```

### <a name="change-calling-delegate-permissions"></a>호출 대리자 권한 변경

대리자 권한을 변경하려면(예: user2가 user1을 호출할 수 없도록 허용) 다음 예제와 같이 Set-CsUserCallingDelegate cmdlet을 사용합니다.

```PowerShell
Set-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com -MakeCalls $false
```

### <a name="remove-a-calling-delegate-for-a-user"></a>사용자에 대한 호출 대리자 제거

user2를 user1의 대리자로 제거하려면 다음 예제와 같이 Remove-CsUserCallingDelegate cmdlet을 사용합니다.

```PowerShell
Remove-CsUserCallingDelegate -Identity user1@contoso.com -Delegate user2@contoso.com
```

## <a name="additional-notes"></a>추가 참고 사항

- 사용자 또는 테넌트 관리자가 통화 응답 규칙을 수정한 적이 없는 사용자의 기본 동작은 응답되지 않은 통화가 30초 후에 음성 메일로 전달된다는 것입니다. 팀 관리 센터 또는 Teams PowerShell에서 사용자에 대해 표시되는 설정은 응답되지 않은 대상을 없음으로 표시하고 20초의 지연 시간을 표시합니다.

## <a name="related-topics"></a>관련 주제

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)
- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)
- [New-CsUserCallingDelegate](/powershell/module/teams/new-csusercallingdelegate)
- [Set-CsUserCallingDelegate](/powershell/module/teams/set-csusercallingdelegate)
- [Remove-CsUserCallingDelegate](/powershell/module/teams/remove-csusercallingdelegate)
