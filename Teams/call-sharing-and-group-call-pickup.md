---
title: 통화 공유 및 그룹 전화 받기
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 02/19/2019
ms.reviewer: jenstr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.users.voice.groupcallpickup.tooltip
- ms.teamsadmincenter.users.voice.callorderanddelay.tooltip
- Phone System
- seo-marvel-mar2020
description: Microsoft Teams에서 통화 공유 및 그룹 통화 픽업을 사용하면 사용자가 전화를 받을 수 없을 때 통화를 캡처할 수 있도록 동료와 수신 전화를 공유할 수 있습니다.
ms.openlocfilehash: 420378ce6d75523bf51b18c17e733d13a76ad877
ms.sourcegitcommit: f0e2a5928e9b959daf45202b9f256f65c2087195
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2022
ms.locfileid: "68613850"
---
# <a name="call-sharing-and-group-call-pickup"></a>통화 공유 및 그룹 전화 받기

Microsoft Teams의 통화 공유 및 그룹 통화 픽업 기능을 사용하면 사용자가 수신 전화를 동료와 공유할 수 있으므로 동료가 사용자를 사용할 수 없는 동안 발생하는 통화에 응답할 수 있습니다.

그룹 통화 픽업은 다른 형태의 통화 공유보다 받는 사람에게 덜 방해가 됩니다. 사용자가 들어오는 공유 통화에 대한 알림을 받는 방법을 구성할 수 있고 응답 여부를 결정할 수 있기 때문입니다. 호출 그룹의 멤버가 들어오는 호출에 대해 알림을 받는 순서는 동시 또는 순서(5명 이하의 멤버 포함)로 지정할 수 있습니다.

> [!IMPORTANT]
> 사용자, 통화 그룹 소유자 및 통화 그룹의 구성원은 Teams 전용 배포 모드에 있어야 합니다. Teams 배포 모드에 대한 자세한 내용은 [Microsoft Teams 이해 및 비즈니스용 Skype 공존 및 상호 운용성을](teams-and-skypeforbusiness-coexistence-and-interoperability.md) 참조하세요.

## <a name="license-required"></a>라이선스 필요

통화 공유 및 그룹 통화 픽업을 설정하고 사용하려면 사용자에게 Microsoft Teams 전화 시스템 라이선스가 할당되어야 합니다. 라이선스 모델에 대한 자세한 내용은 [전화 시스템을 사용하여 얻을 수 있는 항목을 참조](/MicrosoftTeams/here-s-what-you-get-with-phone-system)하세요.

## <a name="limitations"></a>제한 사항

사용자는 하나의 호출 그룹의 소유자만 될 수 있습니다. 구성된 각 통화 그룹은 최대 25명의 사용자 또는 32,768자를 가질 수 있습니다. 사용자는 최대 25개의 호출 그룹의 구성원일 수 있습니다.

모바일 장치는 배너 및 벨소리로 설정된 경우에만 알림을 받습니다.

## <a name="enable-the-use-of-group-call-pickup"></a>그룹 통화 픽업 사용 사용

사용자에 대한 **TeamsCallingPolicy AllowCallGroups** 설정을 구성하여 통화 그룹을 사용하도록 설정합니다. Teams 관리 센터 또는 PowerShell을 사용할 수 있습니다. 사용하도록 설정하면 사용자는 Teams 클라이언트에서 통화 그룹을 구성할 수 있습니다. 

중요: 사용자에 대한 통화 그룹을 해제하는 경우 잘못된 통화 라우팅을 방지하려면 Teams 관리 센터의 사용자에 대한 통화 그룹 관계를 정리해야 합니다. 

## <a name="use-teams-admin-center"></a>Teams 관리 센터 사용

Teams 관리 센터를 사용하여 사용자에 대한 그룹 통화 픽업을 구성하려면 [사용자에 대한 통화 설정 구성을 참조하세요](/MicrosoftTeams/user-call-settings).

## <a name="use-powershell"></a>PowerShell 사용

사용자에 대한 통화 그룹을 구성하려면 다음 Teams PowerShell 모듈 cmdlet을 사용합니다.

- [Set-CsUserCallingSettings](/powershell/module/teams/set-csusercallingsettings)

- [Get-CsUserCallingSettings](/powershell/module/teams/get-csusercallingsettings)

### <a name="examples"></a>예제

다음 예제에서는 멤버 user2@contoso.com 및 user3@contoso.com 사용하여 user1@contoso.com 대한 호출 그룹을 만들고 user1@contoso.com 대한 호출 그룹에 대한 즉시 호출 전달을 설정합니다.

```powershell
$cgm = @("sip:user2@contoso.com","sip:user3@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder InOrder -CallGroupTargets $cgm
Set-CsUserCallingSettings -Identity user1@contoso.com -IsForwardingEnabled $true -ForwardingType Immediate -ForwardingTargetType Group
```

다음 예제에서는 user1@contoso.com 호출 그룹을 업데이트하여 user5@contoso.com 추가하고 user6@contoso.com 제거하는 방법을 보여줍니다.

```powershell
$ucs = Get-CsUserCallingSettings -Identity user1@contoso.com
$cgt = {$ucs.CallGroupTargets}.Invoke()
$cgt.Add("sip:user5@contoso.com")
$cgt.Remove("sip:user6@contoso.com")
Set-CsUserCallingSettings -Identity user1@contoso.com -CallGroupOrder $ucs.CallGroupOrder -CallGroupTargets $cgt
```

## <a name="more-information"></a>추가 정보

[Teams에서 착신 전환 및 동시 연결](https://support.office.com/article/call-forwarding-and-simultaneous-ring-in-teams-a88da9e8-1343-4d3c-9bda-4b9615e4183e)

[Teams 통화 정책](/MicrosoftTeams/teams-calling-policy)

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)
