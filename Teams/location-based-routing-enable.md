---
title: 직접 라우팅에 위치 기반 라우팅 사용
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 사용자, 네트워크 Location-Based 게이트웨이 구성 및 호출 정책을 사용하도록 설정하는 것을 포함하여 직접 라우팅에 대한 Location-Based 라우팅을 사용하도록 설정하는 방법에 대해 자세히 알아보습니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a53ab4ad866f3d9ad6acb1258247da59b15a27d9
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399492"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>직접 라우팅에 위치 기반 라우팅 사용

이 문서의 단계를 수행하기 전에 직접 라우팅에 대한 계획 Location-Based 라우팅을 [](location-based-routing-plan.md) 읽고 네트워크 설정 구성에서 Location-Based 완료해야 [합니다](location-based-routing-configure-network-settings.md).

이 문서에서는 직접 라우팅에 Location-Based 라우팅을 사용하도록 설정하는 방법을 설명합니다. 직접 전화 시스템 배포하고 네트워크 지역, 사이트 및 서브넷을 설정한 후 라우팅을 사용하도록 Location-Based 있습니다. 이 문서의 단계를 완료하려면 PowerShell cmdlet에 대해 잘 알고 있는 것이 필요합니다. 자세한 내용은 [PowerShell Teams 참조하세요](teams-powershell-overview.md).

 다음에 대해 Location-Based 라우팅을 사용하도록 설정해야 합니다.
- 사용자
- 네트워크 사이트
- 게이트웨이 구성
- 통화 정책

관리 센터 또는 [powerShell](#using-powershell)을 사용하여 Microsoft Teams 라우팅을 사용하도록 Location-Based 수 있습니다.[](#using-the-microsoft-teams-admin-center)

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

### <a name="enable-location-based-routing-for-users"></a>사용자 Location-Based 라우팅 사용

1. 음성 라우팅 정책을 만들고 정책에 PSTN 사용량을 할당합니다. 정책에 PSTN 사용량을 할당할 때 다음 중 하나를 해야 합니다.

    - 사이트에 로컬 PSTN 게이트웨이를 사용하는 음성 경로에 연결된 PSTN 사용량을 사용합니다.
    - 라우팅 제한이 필요하지 않은 지역에 있는 PSTN 게이트웨이를 사용하는 음성 경로에 Location-Based PSTN 사용량을 사용합니다.
2. 라우팅 제한을 적용해야 하는 사용자에게 음성 라우팅 정책을 할당합니다.

음성 라우팅 정책을 만들고 사용자에게 할당하는 방법에 대한 자세한 내용은 음성 라우팅 정책 관리를 [Microsoft Teams.](manage-voice-routing-policies.md)

### <a name="enable-location-based-routing-for-network-sites"></a>네트워크 Location-Based 라우팅 사용

라우팅 Location-Based 적용해야 하는 사이트에 대한 Location-Based 라우팅을 사용하도록 설정합니다. 이렇게하려면 관리 센터의 왼쪽 Microsoft Teams **LocationNetwork** >  토폴로지로 이동하여 네트워크 사이트를 선택하고 편집을 클릭한 다음 위치 기반 라우팅을 **켜면 됩니다**.  

자세한 내용은 네트워크 토폴로 [지 관리를 참조합니다](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>게이트웨이에 Location-Based 라우팅 사용

PSTN Location-Based 호출을 라우팅하는 PSTN 게이트웨이에 대한 호출을 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결하는 게이트웨이에 대한 라우팅을 사용하도록 설정합니다. 

1. 왼쪽 탐색에서 **VoiceDirect** >  라우팅으로 이동한 다음 **SBC 탭을 클릭합니다**.
2. SBC를 선택한 다음 편집을 **클릭합니다**. 
3. 위치 **기반 라우팅** 및 미디어 최적화에서 위치 기반 라우팅 사용하도록 **설정합니다**.
4. 게이트웨이 사이트 ID를 지정한 다음, 우회 모드를 설정합니다.
5. **저장** 을 클릭합니다.

### <a name="enable-location-based-routing-for-calling-policies"></a>호출 정책에 Location-Based 라우팅 사용

특정 Location-Based 라우팅을 적용하기 위해 사용자의 호출 정책을 설정하여 PSTN 통화 우회를 방지합니다. 이렇게 하여 통화 정책에서 호출 우  회 방지 설정을 켜야 합니다.

자세한 내용은 전화 통화 정책을 [Teams](teams-calling-policy.md).

## <a name="using-powershell"></a>PowerShell 사용

### <a name="enable-location-based-routing-for-users"></a>사용자 Location-Based 라우팅 사용

1. [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet을 사용하여 PSTN 사용량을 설정합니다. 여러 사용의 경우 각 사용량을 콤마로 구분합니다.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    예를 들면 다음과 같습니다.
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용하여 음성 라우팅 정책을 만들어 사용자를 적절한 PSTN 사용량과 연결합니다.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    음성 라우팅 정책에 PSTN 사용량을 할당할 때 다음 중 하나를 해야 합니다.
    - 사이트에 로컬 PSTN 게이트웨이를 사용하는 음성 경로에 연결된 PSTN 사용량 사용
    - 라우팅 제한이 필요하지 않은 지역에 있는 PSTN 게이트웨이를 사용하는 음성 경로에 Location-Based PSTN 사용량을 사용합니다.

    이 예제에서는 두 개의 새 음성 라우팅 정책을 만들고 PSTN 사용량을 할당합니다. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    다음 표에서는 이 예제에 정의된 음성 라우팅 정책을 보여줍니다. 
    
    |&nbsp;|음성 라우팅 정책 1|음성 라우팅 정책 2|
    |---------|---------|---------|
    |온라인 음성 정책 ID   |Delhi 온라인 음성 라우팅 정책   |Hyderabad 온라인 음성 라우팅 정책    |
    |온라인 PSTN 사용량  |장거리  |장거리, 로컬, 내부  |

3. [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용하여 라우팅 제한을 적용해야 하는 사용자에게 온라인 음성 라우팅 정책을 연결합니다.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
### <a name="enable-location-based-routing-for-network-sites"></a>네트워크 Location-Based 라우팅 사용

1.  [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet을 사용하여 Location-Based 라우팅을 사용하도록 설정하고 라우팅 제한을 적용해야 하는 네트워크 사이트에 음성 라우팅 정책을 연결합니다.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    이 예제에서는 Delhi Location-Based 및 Hyderabad 사이트에 대한 Location-Based 라우팅을 사용하도록 설정합니다. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    다음 표에서는 이 예제에서 Location-Based 라우팅에 사용하도록 설정된 사이트를 보여줍니다.

    |&nbsp;|Site 1(Delhi)  |Site 2(Hyderabad)  |
    |---------|---------|---------|
    |사이트 이름    |Site 1(Delhi)    |Site 2(Hyderabad)|
    |EnableLocationBasedRouting    |True    |True    |
    |서브넷     |서브넷 1(Delhi)     |서브넷 2(Hyderabad)     |

### <a name="enable-location-based-routing-for-gateways"></a>게이트웨이에 Location-Based 라우팅 사용

1. [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet을 사용하여 각 게이트웨이 또는 네트워크 사이트에 대한 게이트웨이 구성을 만들 수 있습니다. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    여러 게이트웨이가 시스템(예: 게이트웨이 또는 PBX)에 연결되어 있는 경우 라우팅 제한을 사용하도록 각 게이트웨이를 Location-Based 합니다. 

    이 예제에서는 각 게이트웨이에 대해 하나의 게이트웨이 구성을 생성합니다. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    자세한 내용은 직접 라우팅 [구성을 참조하세요](direct-routing-configure.md).
    
2. [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet을 사용하여 라우팅 제한을 적용해야 하는 게이트웨이에 Location-Based 라우팅을 사용할 수 있습니다. 

    PSTN Location-Based 호출을 라우팅하는 PSTN 게이트웨이에 대한 호출을 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결하는 게이트웨이에 대한 라우팅을 사용하도록 설정합니다.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    이 예제에서는 Location-Based 및 Hyderabad 사이트의 PSTN 게이트웨이에 연결된 각 게이트웨이에 대한 라우팅을 사용하도록 설정합니다. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```
    PSTN에 Location-Based 라우팅하지 않는 게이트웨이에 대한 라우팅을 사용하도록 설정하지 않습니다. 그러나 여전히 시스템이 있는 네트워크 사이트에 게이트웨이를 연결해야 합니다. 이 게이트웨이를 통해 Location-Based 엔드포인트에 도달하는 PSTN 호출에 대해 라우팅 제한을 적용해야 하기 때문이다. 이 예제에서는 Location-Based 및 Hyderabad 사이트의 PBX 시스템에 연결된 각 게이트웨이에 대해 라우팅을 사용할 수 없습니다.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>호출 정책에 Location-Based 라우팅 사용

특정 Location-Based 라우팅을 적용하기 위해 사용자의 음성 정책을 설정하여 PTSN의 에지 우회를 방지합니다. 

[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet을 사용하여 PSTN Location-Based 우회를 방지하여 라우팅을 활성화합니다.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
이 예제에서는 User1의 호출 정책에 대한 PSTN 호출 우회를 방지합니다. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>관련 항목

- [클라우드 음성 기능에 대한 네트워크 Teams](cloud-voice-network-settings.md)