---
title: 네트워크 로밍 정책
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
description: Teams 네트워크 로밍 정책에 대한 설정을 관리하는 방법을 알아보세요.
ms.openlocfilehash: f8b1d78754c5f608aa76d9261b2164abc4de9194
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2022
ms.locfileid: "68585063"
---
# <a name="manage-video-and-media-settings-with-the-network-roaming-policy"></a>네트워크 로밍 정책으로 비디오 및 미디어 설정 관리

모임 정책으로 비디오 및 미디어 설정을 관리하는 것 외에도 이제 TeamsNetworkRoamingPolicy를 사용하여 Microsoft Teams 클라이언트에서 사용하는 다음 특성의 사용을 동적으로 제어할 수 있습니다. 

- IP 비디오
- 미디어 비트 전송률

이 정책을 사용하면 네트워크 사이트에 설정을 할당할 수 있습니다. Teams 클라이언트는 연결하는 네트워크 사이트에 따라 설정을 동적으로 선택합니다. Teams 클라이언트가 로밍 정책이 할당된 네트워크 사이트에서 로그인하면 해당 정책이 사용됩니다. 할당된 정책이 없으면 모임 정책에 설정된 값이 사용됩니다. 모임 정책 오디오 및 비디오 설정에 대한 자세한 내용은 [오디오 및 비디오에 대한 모임 정책 설정](meeting-policies-audio-and-video.md)을 참조하세요.

## <a name="configure-the-teamsnetworkroamingpolicy"></a>TeamsNetworkRoamingPolicy 구성

TeamsNetworkRoamingPolicy를 구성하려면 다음 PowerShell cmdlet을 사용합니다.

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)

TeamsNetworkRoamingPolicy에는 다음 매개변수가 포함됩니다.

- AllowIPVideo - 이 설정은 사용자가 호스트하는 일대일 모임과 사용자가 시작한 그룹 통화에서 비디오를 설정할 수 있는지 여부를 제어합니다.

- MediaBitRateKb - 이 설정은 사용자 통화 및 모임 내 오디오, 비디오 및 비디오 기반 앱 공유 전송의 합계 평균 미디어 비트 전송률을 결정합니다.

정책을 구성한 후 다음과 같이 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) cmdlet을 사용하여 하나 이상의 네트워크 사이트에 할당합니다.

```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
 ``` 
 
 네트워크 사이트에서 정책을 제거하려면 다음 cmdlet을 사용합니다.
 
 ```PowerShell
 Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy $null
 ```

To enable the network roaming policy for users who are not enterprise voice enabled, you must also enable the AllowNetworkConfigurationSettingsLookup setting in TeamsMeetingPolicy. This setting is off by default.

네트워크 사이트 만들기에 대한 자세한 내용은 [클라우드 음성 기능에 대한 네트워크 설정](cloud-voice-network-settings.md)을 참조하세요. 

## <a name="examples"></a>예제

```PowerShell
New-CsTeamsNetworkRoamingPolicy -Identity LowBandwidthSite -AllowIPVideo $false -MediaBitRateKb 1000
```

```PowerShell
Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

## <a name="supported-clients"></a>지원되는 클라이언트

- Windows 
- MacOS 데스크톱

## <a name="known-issues"></a>알려진 문제

Teams Online PowerShell v 2.0.0에서 New- 및 Get-CsTeamsNetworkRoamingPolicy를 지정하면 추가 데이터가 표시되는 것을 볼 수 있습니다.


## <a name="related-topics"></a>관련 항목

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)
- [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)
