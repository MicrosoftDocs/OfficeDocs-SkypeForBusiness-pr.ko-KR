---
title: 직접 라우팅에 위치 기반 라우팅 사용
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.topic: article
ms.reviewer: roykuntz
ms.service: msteams
audience: admin
search.appverid: MET150
description: 사용자, 네트워크 사이트, 게이트웨이 구성 및 통화 정책에 사용하도록 설정하는 등 직접 라우팅에 Location-Based 라우팅을 사용하도록 설정하는 방법을 알아봅니다.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4039105fe27df6fa8acb3f14c0db076e56910403
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999323"
---
# <a name="enable-location-based-routing-for-direct-routing"></a>직접 라우팅에 위치 기반 라우팅 사용

이 문서에서는 직접 라우팅에 Location-Based 라우팅을 사용하도록 설정하는 방법을 설명합니다. 이 문서의 단계를 따르기 전에 [직접 라우팅에 대한 계획 Location-Based 라우팅을 읽고 Location-Based](location-based-routing-plan.md) 라우팅에 [대한 네트워크 설정 구성](location-based-routing-configure-network-settings.md)의 단계를 완료했는지 확인합니다.

 직접 라우팅을 배포하고 네트워크 지역, 사이트 및 서브넷을 설정한 후에는 Location-Based 라우팅을 사용하도록 설정할 준비가 된 것입니다. 이 문서의 단계를 완료하려면 PowerShell cmdlet에 대해 잘 알고 있어야 합니다. 자세한 내용은 [Teams PowerShell 개요](teams-powershell-overview.md)를 참조하세요.

 다음에 대해 Location-Based 라우팅을 사용하도록 설정해야 합니다.

- 사용자
- 네트워크 사이트
- 게이트웨이 구성
- 통화 정책

[Teams 관리 센터](#using-the-microsoft-teams-admin-center) 또는 [PowerShell](#using-powershell)을 사용하여 Location-Based 라우팅을 사용하도록 설정할 수 있습니다.

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

### <a name="enable-location-based-routing-for-users"></a>사용자에 대한 Location-Based 라우팅 사용

1. 음성 라우팅 정책을 만들고 PSTN 사용량을 정책에 할당합니다. 정책에 PSTN 사용량을 할당하는 경우 다음 중 하나를 수행해야 합니다.

    - 사이트에 로컬로 PSTN 게이트웨이를 사용하는 음성 경로에 연결된 PSTN 사용량을 사용합니다.

    - Location-Based 라우팅 제한이 필요하지 않은 지역에 있는 PSTN 게이트웨이를 사용하는 음성 경로와 연결된 PSTN 사용량을 사용합니다.

2. 라우팅 제한을 적용해야 하는 사용자에게 음성 라우팅 정책을 할당합니다.

음성 라우팅 정책을 만들고 사용자에게 할당하는 방법에 대한 자세한 내용은 [Microsoft Teams에서 음성 라우팅 정책 관리를 참조하세요](manage-voice-routing-policies.md).

### <a name="enable-location-based-routing-for-network-sites"></a>네트워크 사이트에 Location-Based 라우팅 사용

라우팅 제한을 적용해야 하는 사이트에 대해 Location-Based 라우팅을 사용하도록 설정합니다. 이렇게 하려면 Microsoft Teams 관리 센터의 왼쪽 탐색에서 **위치** > **네트워크 토폴로지** 로 이동하여 네트워크 사이트를 선택하고 **편집** 을 클릭한 다음 **위치 기반 라우팅을** 켭니다.  

자세한 내용은 [네트워크 토폴로지 관리를 참조하세요](manage-your-network-topology.md).

### <a name="enable-location-based-routing-for-gateways"></a>게이트웨이에 Location-Based 라우팅 사용

호출을 PSTN으로 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결하는 PSTN 게이트웨이에 대한 호출을 라우팅하는 게이트웨이에 대한 Location-Based 라우팅을 사용하도록 설정합니다. 

1. 왼쪽 탐색 영역에서 **음성** > **직접 라우팅** 으로 이동한 다음 **SCC** 탭을 클릭합니다.

2. SBC를 선택한 다음 **편집** 을 클릭합니다. 

3. **위치 기반 라우팅 및 미디어 최적화** 에서 **위치 기반 라우팅을 사용하도록 설정합니다**.

4. 게이트웨이 사이트 ID를 지정한 다음 바이패스 모드를 설정합니다.

5. **저장** 을 클릭합니다.

### <a name="enable-location-based-routing-for-calling-policies"></a>통화 정책에 Location-Based 라우팅 사용

특정 사용자에 대해 Location-Based 라우팅을 적용하려면 PSTN 수신자 우회를 방지하기 위해 사용자의 통화 정책을 설정합니다. 이렇게 하려면 호출 정책에서 **수신자 무시 방지** 설정을 켭니다.

자세한 내용은 [Teams의 통화 정책을 참조하세요](teams-calling-policy.md).

## <a name="using-powershell"></a>PowerShell 사용

### <a name="enable-location-based-routing-for-users"></a>사용자에 대한 Location-Based 라우팅 사용

1. PSTN 사용을 설정하려면 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps) cmdlet을 사용합니다. 여러 사용법의 경우 각 사용량을 쉼표로 구분합니다.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage <usages> 
    ```

    예를 들면 다음과 같습니다.

    ```PowerShell
    Set-CsOnlinePstnUsage -Usage "Long Distance", "Local", "Internal" 
    ```

2. 사용자를 적절한 PSTN 사용과 연결하는 음성 라우팅 정책을 만들려면 [New-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/new-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용합니다.

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity <voice routing policy ID> -Description <voice routing policy name> -OnlinePstnUsages <usages> 
    ```
    
    음성 라우팅 정책에 PSTN 사용량을 할당하는 경우 다음 중 하나를 수행해야 합니다.

    - 사이트에 로컬로 PSTN 게이트웨이를 사용하는 음성 경로에 연결된 PSTN 사용량을 사용합니다.

    - Location-Based 라우팅 제한이 필요하지 않은 지역에 있는 PSTN 게이트웨이를 사용하는 음성 경로와 연결된 PSTN 사용량을 사용합니다.

    다음 예제에서는 두 개의 새 음성 라우팅 정책을 만들고 PSTN 사용을 할당합니다. 

    ```PowerShell
    New-CsOnlineVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Description "Delhi voice routing policy" -OnlinePstnUsages "Long Distance" 
    New-CsOnlineVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Description " Hyderabad voice routing policy" -OnlinePstnUsages "Long Distance", "Local", "Internal" 
    ``` 

    다음 표에서는 이 예제에 정의된 음성 라우팅 정책을 보여줍니다. 
    
    |&nbsp;|음성 라우팅 정책 1|음성 라우팅 정책 2|
    |---------|---------|---------|
    |온라인 음성 정책 ID   |델리 온라인 음성 라우팅 정책   |하이데라바드 온라인 음성 라우팅 정책    |
    |온라인 PSTN 사용량  |장거리  |장거리, 로컬, 내부  |

3. 라우팅 제한을 적용해야 하는 사용자에게 온라인 음성 라우팅 정책을 연결하려면 [Grant-CsOnlineVoiceRoutingPolicy](/powershell/module/skype/grant-csonlinevoiceroutingpolicy?view=skype-ps) cmdlet을 사용합니다.

    ```PowerShell
    Grant-CsOnlineVoiceRoutingPolicy -Identity <User> -Tenant <TenantId>
    ```

### <a name="enable-location-based-routing-for-network-sites"></a>네트워크 사이트에 Location-Based 라우팅 사용

1. Location-Based 라우팅을 사용하도록 설정하고 라우팅 제한을 적용해야 하는 네트워크 사이트에 음성 라우팅 정책을 연결하려면 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite?view=skype-ps) cmdlet을 사용합니다.

    ```PowerShell
    Set-CsTenantNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false>  
    ```

    이 예제에서는 델리 사이트와 하이데라바드 사이트에 대한 Location-Based 라우팅을 사용하도록 설정합니다. 

    ```PowerShell
    Set-CsTenantNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true  
    Set-CsTenantNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true 
    ```
    다음 표에서는 이 예제에서 Location-Based 라우팅에 사용하도록 설정된 사이트를 보여 줍니다.

    |&nbsp;|사이트 1(델리)  |사이트 2(하이데라바드)  |
    |---------|---------|---------|
    |사이트 이름    |사이트 1(델리)    |사이트 2(하이데라바드)|
    |EnableLocationBasedRouting    |사실    |사실    |
    |서브넷     |서브넷 1(델리)     |서브넷 2(하이데라바드)     |


### <a name="enable-location-based-routing-for-gateways"></a>게이트웨이에 Location-Based 라우팅 사용

1. 각 게이트웨이 또는 네트워크 사이트에 대한 게이트웨이 구성을 만들려면 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway?view=skype-ps) cmdlet을 사용합니다. 

    ```PowerShell
    New-CSOnlinePSTNGateway -Fqdn <FDQN registered for the SBC> -Identity <gateway configuration ID> -SipSignalingPort <listening port used> -Enabled $true 
    ```

    여러 게이트웨이가 시스템과 연결된 경우(예: 게이트웨이 또는 PBX) 각 게이트웨이를 수정하여 Location-Based 라우팅 제한을 사용하도록 설정합니다. 

    다음 예제에서는 각 게이트웨이에 대해 하나의 게이트웨이 구성을 만듭니다. 

    ```PowerShell
    New-CsOnlinePSTNGateway -Fqdn sbc.contoso.com -Enabled $true -SipSignalingPort 5067 
    ```
    자세한 내용은 [직접 라우팅 구성을 참조하세요](direct-routing-configure.md).
    
2. 라우팅 제한을 적용해야 하는 게이트웨이에 Location-Based 라우팅을 사용하도록 설정하려면 [Set-CSOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway?view=skype-ps) cmdlet을 사용합니다. 

    호출을 PSTN으로 라우팅하고 게이트웨이가 있는 네트워크 사이트를 연결하는 PSTN 게이트웨이에 대한 호출을 라우팅하는 게이트웨이에 대한 Location-Based 라우팅을 사용하도록 설정합니다.

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity <gateway configuration ID> -GatewaySiteLbrEnabled $true -GatewaySiteID <site ID> 
    ```

   다음 예제에서는 델리 및 하이데라바드 사이트의 PSTN 게이트웨이에 연결된 각 게이트웨이에 대해 Location-Based 라우팅을 사용하도록 설정합니다. 

    ```PowerShell
    Set-CSOnlinePSTNGateway -Identity sbc.contoso.com  -GatewaySiteLbrEnabled $true –GatewaySiteID "Delhi"
    Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com  -GatewaySiteLbrEnabled $true -GatewaySiteID "Hyderabad" 
    ```

    PSTN에 대한 호출을 라우팅하지 않는 게이트웨이에 대해 Location-Based 라우팅을 사용하도록 설정하지 마세요. 그러나 여전히 게이트웨이를 시스템이 있는 네트워크 사이트에 연결해야 합니다. 이 게이트웨이를 통해 연결된 엔드포인트에 도달하는 PSTN 호출에 대해 Location-Based 라우팅 제한을 적용해야 하기 때문입니다. 이 예제에서 Location-Based 라우팅은 델리 및 하이데라바드 사이트의 PBX 시스템에 연결된 각 게이트웨이에 대해 활성화되지 않습니다.

    ```PowerShell
    Get-CSONlinePSTNGateway -Identity sbc.contoso.com 
 
    Identity: sbc.contoso.com 
    GatewaySiteLbrEnabled: $false 
 
    Get-CSONlinePSTNGateway -Identity sbc2.contoso.com 
 
    Identity: sbc2.contoso.com 
    GatewaySiteLbrEnabled: $false 
    ```

### <a name="enable-location-based-routing-for-calling-policies"></a>통화 정책에 Location-Based 라우팅 사용

특정 사용자에 대해 Location-Based 라우팅을 적용하려면 PTSN 수신자 우회를 방지하기 위해 사용자의 음성 정책을 설정합니다. 

PSTN 통행료 우회를 방지하여 Location-Based 라우팅을 사용하도록 설정하려면 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy?view=skype-ps) cmdlet을 사용합니다.


```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName <policy name> -id <user id> 
```

이 예제에서는 PSTN 통행료가 User1의 호출 정책에 우회되지 않도록 합니다. 

```PowerShell
Grant-CsTeamsCallingPolicy –PolicyName "AllowCallingPreventTollBypass" -id "User1" 
```

## <a name="related-topics"></a>관련 주제

- [Teams의 클라우드 음성 기능에 대한 네트워크 설정](cloud-voice-network-settings.md)