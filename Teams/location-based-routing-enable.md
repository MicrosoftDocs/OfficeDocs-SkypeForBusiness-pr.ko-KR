---
title: 직접 라우팅에 위치 기반 라우팅 사용
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 직접 라우팅에 대해 위치 기반 라우팅을 사용 하는 방법에 대해 알아봅니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 734a2354e81dc88430e8f880c46b0f97862158b5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836558"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>직접 라우팅에 위치 기반 라우팅 사용

> [!INCLUDE [Preview customer token](includes/preview-feature.md)]

이 문서에 나와 있는 단계를 수행 하기 전에 위치 [기반 라우팅에 대 한 네트워크 설정 구성](location-based-routing-configure-network-settings.md)단계를 [직접 라우팅과 완료 하기 위한 계획 위치 기반 라우팅을](location-based-routing-plan.md) 읽어 주십시오.

이 문서에서는 직접 라우팅에 위치 기반 라우팅을 사용 하는 방법에 대해 설명 합니다. 전화 시스템 직접 라우팅을 배포 하 고 네트워크 지역, 사이트 및 서브넷을 설정한 후에는 위치 기반 라우팅을 사용할 준비가 된 것입니다. 이 문서의 단계를 완료 하려면 PowerShell cmdlet에 대해 잘 알고 있어야 합니다. 자세히 알아보려면 [팀 PowerShell 개요](teams-powershell-overview.md)를 참조 하세요.

 위치 기반 회람을 사용 해야 하는 경우는 다음과 같습니다.
- 사용자
- 네트워크 사이트
- 게이트웨이 구성
- 통화 정책

## <a name="enable-location-based-routing-for-users"></a>사용자의 위치 기반 라우팅 사용

1. [CsOnlinePstnUsage](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet을 사용 하 여 PSTN 사용량을 설정 합니다. 여러 용도를 위해 각 용도를 쉼표로 구분 합니다.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```
    예를 들면 다음과 같습니다.
    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```
2. [CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용 하 여 사용자를 적절 한 PSTN 용도에 연결 하는 음성 라우팅 정책을 만듭니다.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    음성 라우팅 정책에 PSTN 용도를 할당 하는 경우 다음 중 하나를 수행 해야 합니다.
    - 사이트에 로컬 PSTN 게이트웨이를 사용 하는 음성 경로에 연결 된 PSTN 용도 사용
    - 위치 기반 라우팅 제한이 필요 하지 않은 지역에 있는 PSTN 게이트웨이를 사용 하는 음성 경로에 연결 된 PSTN 사용량을 사용 합니다.

    이 예제에서는 두 개의 새로운 음성 라우팅 정책을 만들고 PSTN 용도를 할당 합니다. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ```
    다음 표에는이 예제에 정의 된 음성 라우팅 정책이 나와 있습니다. 
    
    ||음성 라우팅 정책 1|음성 라우팅 정책 2|
    |---------|---------|---------|
    |온라인 음성 정책 ID   |이 (가) 뉴델리 온라인 음성 라우팅 정책   |Hyderabad 온라인 음성 라우팅 정책    |
    |온라인 PSTN 용도  |시외  |장거리, 지역, 내부  |

3. [CsOnlineVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용 하 여 라우팅 제한을 적용 해야 하는 사용자에 게 온라인 음성 라우팅 정책을 연결 합니다.
    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```
## <a name="enable-location-based-routing-for-network-sites"></a>네트워크 사이트용 위치 기반 라우팅 사용
1.  [Set-Csten앤틸리스 site](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet을 사용 하 여 위치 기반 라우팅을 사용 하도록 설정 하 고 라우팅 제한을 적용 해야 하는 네트워크 사이트에 음성 라우팅 정책을 연결 합니다.
    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    이 예제에서는 뉴델리 사이트 및 Hyderabad 사이트에 대 한 위치 기반 라우팅을 사용 하도록 설정 합니다. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    다음 표에는이 예제에서 위치 기반 라우팅에 사용할 수 있는 사이트가 나와 있습니다.

    ||사이트 1(뉴델리)  |Site 2 (Hyderabad)  |
    |---------|---------|---------|
|사이트 이름    |사이트 1(뉴델리)    |Site 2 (Hyderabad)   
    |EnableLocationBasedRouting    |False    |False    |
    |네트     |서브넷 1 (뉴델리)     |서브넷 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-gateways"></a>게이트웨이에 대 한 위치 기반 라우팅 사용
1. [새 CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet을 사용 하 여 각 게이트웨이 또는 네트워크 사이트에 대 한 게이트웨이 구성을 만듭니다. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```
    여러 게이트웨이가 시스템 (예: 게이트웨이 또는 PBX)과 연결 되어 있는 경우 위치 기반 라우팅 제한을 사용 하도록 각 게이트웨이를 수정 합니다. 

    이 예제에서는 각 게이트웨이에 대해 하나의 게이트웨이 구성을 만듭니다. 
    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.
    
2. [CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet을 사용 하 여 라우팅 제한을 적용 해야 하는 게이트웨이에 대 한 위치 기반 라우팅을 사용 하도록 설정 합니다. 

    PSTN으로 호출을 라우팅하는 PSTN 게이트웨이로 통화를 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결 하는 게이트웨이에 대 한 위치 기반 라우팅을 사용 하도록 설정 합니다.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

    이 예제에서는 뉴델리 및 Hyderabad 사이트의 PSTN 게이트웨이와 연결 된 각 게이트웨이에 대해 위치 기반 라우팅을 사용 하도록 설정 합니다. 
    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID “Delhi”
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID “Hyderabad” 
    ```
    PSTN으로 호출을 라우팅되지 않는 게이트웨이에 대해 위치 기반 라우팅을 사용 하지 마세요. 그러나이 경우에도 시스템이 있는 네트워크 사이트에 게이트웨이를 연결 해야 합니다. 이 게이트웨이를 통해 연결 된 끝점에 도달 하는 PSTN 호출에 대해 위치 기반 라우팅 제한을 적용 해야 하기 때문입니다. 이 예제에서는 Hyderabad 사이트에서 PBX 시스템과 연결 된 각 게이트웨이에 대해 위치 기반 라우팅이 사용 되지 않습니다.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

    PSTN으로 호출을 라우팅 하지 않는 시스템 (예: PBX)에 연결 된 끝점은 위치 기반 라우팅에 대해 사용 하도록 설정한 팀 사용자의 끝점과 유사 하 게 제한 됩니다. 즉, 이러한 사용자는 사용자 위치에 관계 없이 팀 사용자에 게 전화를 걸거나 받을 수 있습니다. 또한 시스템을 연결 하는 네트워크 사이트에 관계 없이 PSTN 네트워크 (예: 다른 PBX에 연결 된 끝점과 같은)에 대 한 통화를 라우팅 하지 않는 다른 시스템에서 전화를 걸거나 받을 수 있습니다. PSTN 끝점을 포함 하는 모든 인바운드 통화, 아웃 바운드 통화, 통화 전송 및 착신 전환에는 위치 기반 라우팅 enforcements 적용 됩니다. 이러한 통화는 해당 시스템에 로컬으로 정의 된 PSTN 게이트웨이만 사용 해야 합니다. 

    다음 표에서는 PSTN 게이트웨이와 연결 된 두 개의 다른 네트워크 사이트와 PBX 시스템에 연결 된 두 개의 게이트웨이 구성을 보여 줍니다. 

    ||게이트웨이 사용   |NetworkSiteID  |
    |---------|---------|---------|
    |PstnGateway: Gateway 1 DEL-GW    |    False     |   사이트 1(뉴델리)      |
    |PstnGateway: Gateway 2 HYD-GW     |   False      |      Site 2 (Hyderabad)   |
    |PstnGateway: 게이트웨이 3 DEL-PBX    |    해제     |     사이트 1(뉴델리)    |
    |PstnGateway: Gateway 4 HYD-PBX    |    해제     |    Site 2 (Hyderabad)     |

## <a name="enable-location-based-routing-for-calling-policies"></a>호출 정책에 대해 위치 기반 라우팅 사용

특정 사용자에 대해 위치 기반 라우팅을 적용 하려면, 사용자의 음성 정책을 설정 하 여 PTSN을 무시할 수 있습니다. 

[CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet을 사용 하 여 PSTN 유료 바이패스를 방지 하 여 위치 기반 라우팅을 사용 하도록 설정 합니다.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```
이 예제에서는 PSTN 유료 바이패스를 User1's 호출 정책을 방지 합니다. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName “AllowCallingPreventTollBypass” -id “User1” 
```

## <a name="related-topics"></a>관련 항목

- [팀의 클라우드 음성 기능에 대 한 네트워크 설정](cloud-voice-network-settings.md)
