---
title: 직접 라우팅으로 전달되는 위치 기반 라우팅 계획
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: 직접 라우팅에 Location-Based 라우팅을 계획하는 방법에 대해 자세히 알아보습니다.
ms.localizationpriority: medium
f1.keywords:
  - NOCSH
ms.collection:
  - M365-voice
appliesto:
  - Microsoft Teams
---

# <a name="plan-location-based-routing-for-direct-routing"></a>직접 라우팅으로 전달되는 위치 기반 라우팅 계획

## <a name="overview-of-location-based-routing"></a>라우팅 Location-Based 개요

일부 국가 및 지역에서는 PSTN(공용 전환 전화 네트워크) 공급자를 우회하여 장거리 통화 비용을 절감하는 것이 불법입니다. 이 문서에서는 해당 지리적 위치에 Location-Based 사용자에 대한 Microsoft Teams 라우팅을 사용하는 방법을 설명합니다. 이 문서는 직접 라우팅에 전화 시스템 적용됩니다.

여기서는 계획하는 데 도움이 되는 Location-Based 라우팅 및 지침에 대한 개요를 제공합니다. 라우팅을 적용하고 사용하도록 설정할 준비가 Location-Based 경우 다음을 참조합니다.

- [라우팅에 Location-Based 네트워크 설정 배포](location-based-routing-configure-network-settings.md)
- [직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)

> [!NOTE]
> Location-Based(Microsoft 365 정부 커뮤니티 클라우드) 높거나 DoD 배포에서 Microsoft 365 정부 커뮤니티 클라우드(GCC) 사용할 수 없습니다.

Location-Based 라우팅은 인바운드 또는 아웃바운드 PSTN 호출 시 정책 및 사용자의 지리적 위치에 따라 통화 우회를 제한할 수 있는 기능입니다. Location-Based 라우팅은 세로 우회를 방지하는 메커니즘을 제공하기 위한 것입니다. 사용자의 위치에 따라 PSTN 호출을 동적으로 라우팅하거나 의도하지 않은 결과가 발생할 수 있는 메커니즘으로는 사용할 수 없습니다.

사용자 Teams 라우팅에 Location-Based 경우 다음이 적용됩니다.

- 아웃바운드 PSTN 호출을 만들 경우 다음 중 하나는 true가 되어야 합니다.
    - 사용자의 엔드포인트는 네트워크 사이트에 위치하여 라우팅을 Location-Based 라우팅에 사용할 수 있는 해당 게이트웨이를 통해 Location-Based 호출합니다. 
    - 사용자의 엔드포인트는 라우팅을 사용할 수 없는 네트워크 사이트에 Location-Based 라우팅에 사용할 수 없는 게이트웨이를 통해 Location-Based 호출합니다.

    아웃바운드 호출은 다른 시나리오에서는 허용되지 않습니다.

- 인바운드 PST Location-Based N 호출을 수신하려면 사용자의 응답 엔드포인트가 동일한 네트워크 사이트에 있어야 합니다. 여기서 호출이 라우팅에 사용하도록 설정된 게이트웨이를 통해 수신됩니다. 사용자가 로밍하는 경우와 같은 다른 시나리오에서는 호출이 허용되지 않습니다. 사용자의 통화 전달 설정(일반적으로 음성 메시지)으로 라우팅됩니다.
- PSTN 호출을 다른 사용자로 Teams 경우 대상 사용자의 엔드포인트는 전송을 시작하는 사용자와 동일한 네트워크 사이트에 있어야 합니다. 다른 시나리오에서는 전송이 허용되지 않습니다. 
- 다른 Teams PSTN으로 전송하려면 초기 호출자와 동일한 네트워크 사이트에 Location-Based 라우팅이 설정된 게이트웨이를 통해 호출을 전송해야 합니다. 다른 시나리오에서는 전송이 허용되지 않습니다.

Location-Based 라우팅은 동일한 네트워크 지역, 사이트 및 서브넷 정의를 비즈니스용 Skype 서버 사용합니다. 위치에 대해 통화 우회가 제한되는 경우 관리자는 각 IP 서브넷 및 해당 위치에 대한 각 PSTN 게이트웨이를 네트워크 사이트에 연결합니다. 사용자의 위치는 PSTN 호출 시 사용자의 Teams 엔드포인트가 연결되는 IP 서브넷에 의해 결정됩니다. 사용자가 서로 다른 사이트에 Teams 여러 개의 클라이언트가 있을 수 있습니다. 이 경우 Location-Based 라우팅은 해당 엔드포인트의 위치에 따라 각 클라이언트의 라우팅을 개별적으로 적용합니다. 

이 문서에서 사용되는 네트워크 용어 중 일부를 익숙하게 사용하려면 이 문서의 클라우드 [음성 기능에 대한 네트워크 설정을 Teams](cloud-voice-network-settings.md).

## <a name="apply-location-based-routing"></a>라우팅 Location-Based 적용

사용자, Location-Based 사이트 및 PSTN 게이트웨이에 라우팅을 적용해야 합니다.  

### <a name="apply-location-based-routing-at-the-user-location"></a>사용자 Location-Based 라우팅 적용

앞에서 설명한 Location-Based 라우팅은 직접 라우팅을 설정한 사용자에게만 적용됩니다. Location-Based 계획에 대해 설정한 사용자에게는 라우팅이 적용되지 않습니다. 사용자는 수신자 Location-Based 우회 제한을 받는 경우 라우팅을 사용하도록 설정해야 합니다. 이는 PSTN 호출을 걸고 받을 수 있는 조건과 사용할 수 있는 PSTN 게이트웨이를 제어합니다. 라우팅을 사용하도록 Location-Based 사용자가 라우팅에 사용하도록 설정된 사이트에 Location-Based 사이트에 있는 경우 사용자는 사이트에 연결된 Location-Based 사용 게이트웨이를 통해 호출해야 합니다. 

Location-Based 엔드포인트의 IP 주소를 기반으로 사용자의 현재 위치를 결정하고 Teams 규칙을 적용합니다. 라우팅에 사용하도록 설정된 사용자의 Location-Based 다음과 같은 방법으로 분류할 수 있습니다. 
- **사용자는 자신의 DID가 할당된 PSTN 게이트웨이에 Location-Based 라우팅이 설정된 사이트와 동일한 위치입니다.**<br>이 시나리오에서 사용자는 라우팅을 사용하도록 Location-Based 알려진 네트워크 사이트에 있으며, 사용자의 직접 내진 다이얼(DID) 번호는 동일한 네트워크 사이트에 있는 PSTN 게이트웨이에서 종료됩니다. 예를 들어 사용자가 자신의 사무실에 있습니다. 
- **사용자는 DID가 할당된 PSTN 게이트웨이에 Location-Based 라우팅이 설정된 다른 사이트에 있습니다.**<br>이 시나리오에서는 사용자가 알려진 네트워크 사이트에 위치하여 라우팅을 Location-Based 해당 사이트는 사용자의 DID 번호가 할당된 PSTN 게이트웨이와 연결되지 않습니다. 예를 들어 사용자는 다른 사무실로 이동합니다.  
- **사용자는 라우팅에 사용할 수 없는 내부 사이트에 Location-Based 있습니다.** <br>이 시나리오에서는 사용자가 알려진 내부 네트워크 사이트에 위치하여 라우팅을 사용할 수 Location-Based 없습니다. 
- **사용자가 알 수 없는 사이트에 있습니다.** 
    - 사용자는 네트워크 사이트로 정의되지 않은 내부 네트워크 내에 있습니다. 
    - 사용자는 내부 네트워크 외부에 있습니다. 예를 들어 사용자는 가정이나 커피숍에서 인터넷에 있습니다. 

### <a name="apply-location-based-routing-at-the-network-site"></a>네트워크 Location-Based 라우팅 적용 
네트워크 사이트는 로밍할 Location-Based 라우팅이 설정된 사용자를 라우팅할 게이트웨이를 Location-Based 사용하도록 설정해야 합니다. 라우팅을 사용하도록 Location-Based 라우팅을 사용하도록 Location-Based 사이트로 로밍하는 경우 해당 사이트에서 라우팅을 사용하도록 Location-Based PSTN 게이트웨이만 아웃바운드 호출에 사용할 수 있습니다. 라우팅을 사용할 수 Location-Based 라우팅을 사용하도록 설정되어 있는 사용자가 Location-Based 라우팅을 사용하도록 설정하지 않은 Location-Based 아웃바운드 호출에 사용할 수 있습니다.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>PSTN Location-Based 라우팅 적용 

게이트웨이는 사이트에 연결되어 PSTN 호출을 만들거나 받을 때 Location-Based 라우팅을 사용할 수 있는 사용자를 확인할 수 있습니다. 게이트웨이를 Location-Based 라우팅에 대해 사용하도록 설정되어 있어야 하여 라우팅을 우회 제한을 적용하고 라우팅을 사용하도록 설정하지 않은 사용자가 사용할 수 Location-Based 합니다. 동일한 게이트웨이는 여러 사이트에 연결될 수 있으며 사이트에 따라 Location-Based 라우팅을 사용하도록 설정하거나 Location-Based 사용하도록 구성할 수 있습니다.

## <a name="scenarios-for-location-based-routing"></a>위치 기반 라우팅 시나리오

이 섹션에서는 Location-Based 라우팅을 사용하여 전화 우회를 제한하는 다양한 시나리오를 설명하고 Location-Based 라우팅을 사용하도록 설정된 사용자와 통화가 라우팅되는 방법을 Location-Based 비교합니다.

- [Teams PSTN에 아웃바운드 호출을 추가합니다.](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams 사용자가 PSTN에서 인바운드 호출을 수신합니다.](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams 다른 사용자에 대한 사용자 전송 또는 Teams 전송](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams PSTN 엔드포인트로 사용자 전송 또는 전달 호출을 전송할 수 있습니다.](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [동시 연결](#simultaneous-ringing)
- [위임](#delegation)

다음 다이어그램은 각 시나리오에서 라우팅을 Location-Based 사용하도록 설정된 제한을 보여 줍니다. 라우팅에 사용하도록 설정된 사용자, 네트워크 사이트 및 Location-Based 경계가 있습니다. 다이어그램을 가이드로 사용하여 각 시나리오에서 라우팅이 Location-Based 방법을 이해하는 데 도움이 됩니다.  

![라우팅에 대한 시나리오를 Location-Based 다이어그램입니다.](media/lbr-direct-routing.png "라우팅에 대한 시나리오를 Location-Based 다이어그램")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams PSTN에 아웃바운드 호출을 추가합니다.

#### <a name="user-not-enabled-for-location-based-routing"></a>사용자 라우팅에 Location-Based 설정되지 않습니다.

라우팅을 사용할 수 Location-Based 할당된 음성 라우팅 정책을 통해 라우팅을 사용할 수 Location-Based 모든 사이트에서 게이트웨이를 사용하여 아웃바운드 호출을 할 수 있습니다. 그러나 게이트웨이가 라우팅에 Location-Based 경우 사용자는 해당 음성 라우팅 정책에 할당된 경우에도 게이트웨이를 통해 아웃바운드 호출을 할 수 없습니다. 사용자가 라우팅을 사용하도록 설정된 사이트로 Location-Based 라우팅에 대해 사용하도록 설정되지 않은 일반 라우팅 게이트웨이를 통해서만 호출할 수 Location-Based 있습니다.
 
#### <a name="user-enabled-for-location-based-routing"></a>라우팅에 Location-Based 사용
반면, 아웃바운드 호출의 라우팅은 Location-Based 엔드포인트의 네트워크 위치의 영향을 받는다. 다음 표에서는 사용자1의 Location-Based 라우팅이 User1의 아웃바운드 호출 라우팅에 미치는 영향을 보여줍니다. 

|User1 엔드포인트 위치  |User1에 대한 아웃바운드 호출 라우팅  |
|---------|---------|
|사용자의 DID가 할당된 동일한 사이트, 라우팅에 Location-Based 사이트(Site1)      |사용자의 음성 라우팅 정책에 따라 Site1에서 GW1(Location-Based 라우팅)에 사용하도록 설정된 게이트웨이를 통해 라우팅된 호출         |
|사용자의 DID가 할당된 사이트와 다른 사이트, 사이트 라우팅에 Location-Based 사이트(Site2)    |사용자의 음성 라우팅 정책에 따라 roam Site2에서 GW2(Location-Based 라우팅)에 사용하도록 설정된 게이트웨이를 통해 라우팅된 통화        |
|사용자의 DID가 할당된 사이트와 다른 사이트, 사이트 라우팅에 Location-Based(Site3)  |사용자의 음성 라우팅 정책에 따라 Location-Based 라우팅(GW3)에 사용할 수 Location-Based 없는 게이트웨이를 통해 라우팅된 호출       |
|알 수 없는 내부 네트워크(Location4)    |  PSTN 호출이 허용되지 않습니다.       |
|알 수 없는 외부 네트워크(Location5)    | PSTN 호출이 허용되지 않습니다.        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams 사용자가 PSTN에서 인바운드 호출을 수신합니다.

#### <a name="user-not-enabled-for-location-based-routing"></a>사용자 라우팅에 Location-Based 설정되지 않습니다.

라우팅을 사용할 수 Location-Based 할당된 DID 번호가 수신되는 라우팅에 대해 Location-Based 게이트웨이에서 인바운드 호출을 받을 수 있습니다. 사용자가 라우팅을 사용할 수 없는 사이트로 로밍하는 경우 Location-Based PSTN 게이트웨이를 통해 계속 호출을 받을 수 있습니다.
  
#### <a name="user-enabled-for-location-based-routing"></a>라우팅에 Location-Based 사용

이와 비교하여 라우팅에 Location-Based 사용자가 동일한 사이트에 있는 경우 해당 DID가 할당된 PSTN 게이트웨이에서 인바운드 호출을 받을 수 있습니다. 다음 표에서는 User1이 다른 네트워크 위치로 이동할 때 User1에서 인바운드 호출을 받는 방법을 보여 주었다. 호출이 사용자의 엔드포인트로 라우팅되지 않은 경우 설정이 구성된 경우 사용자의 통화 전달 설정으로 이동합니다. 일반적으로 음성 메시지입니다.  

|User1 엔드포인트 위치  |User1에 대한 인바운드 호출 라우팅  |
|---------|---------|
|사용자의 DID가 할당된 사이트와 동일한 사이트, 라우팅에 Location-Based 사이트(Site1)   | Site1의 User1 엔드포인트로 라우팅된 호출        |
|사용자의 DID가 할당된 사이트와 다른 사이트, 사이트 라우팅에 Location-Based 사이트(Site2)    | Site2의 엔드포인트로 라우팅되지 않은 호출        |
|사용자의 DID가 할당된 사이트와 다른 사이트, 사이트 라우팅에 Location-Based(Site3)    | Site3의 엔드포인트로 라우팅되지 않은 호출        |
|알 수 없는 내부 네트워크(Location4)   | Location4의 엔드포인트로 라우팅되지 않은 호출        |
|알 수 없는 외부 네트워크(Location5)     | Location5의 엔드포인트로 라우팅되지 않은 호출        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams 다른 사용자에 대한 사용자 전송 또는 Teams 전송

PSTN 엔드포인트가 관련되어 있는 경우 Location-Based 라우팅은 둘 다 라우팅에 대해 Location-Based 여부를 분석하고 두 엔드포인트의 위치에 따라 호출을 전송하거나 전달해야 하는지 여부를 확인합니다. 
 
통화 전송은 시작 사용자가 통화를 선택해야 하는 반면 착신전은 초기 호출에 응답할 필요가 없습니다. 즉, 사용자1이 인바운드 호출을 받을 위치에 있지 않은 경우에도 호출을 전달할 수 있습니다([PSTN](#teams-user-receives-an-inbound-call-from-the-pstn) 섹션에서 인바운드 호출을 수신하는 Teams 테이블 참조) User1이 인바운드 호출을 받을 수 없는 경우 호출을 전송할 수 없습니다. 

#### <a name="user-not-enabled-for-location-based-routing"></a>사용자 라우팅에 Location-Based 설정되지 않습니다.

라우팅을 사용하도록 설정하지 않은 Location-Based 라우팅을 사용하도록 설정하지 않은 다른 사용자에게 PSTN 호출을 전송하거나 전달할 Location-Based 있습니다. 일반적으로 사용자는 PSTN 호출에 대한 라우팅 사용 게이트웨이에서만 Location-Based Location-Based 라우팅을 사용하도록 Location-Based 사용자에 PSTN 호출을 전송하거나 전달할 수 없습니다. 예외는 Location-Based 라우팅을 사용하도록 설정되지 않은 사이트로 Location-Based 경우입니다. 이 시나리오에서는 전송된 호출이 허용됩니다.  

마찬가지로 라우팅을 사용하도록 설정하지 않은 사용자는 Location-Based 라우팅을 사용하도록 설정하지 않은 다른 사용자로부터 전송 또는 전달된 PSTN Location-Based 수 있습니다. 

#### <a name="user-enabled-for-location-based-routing"></a>라우팅에 Location-Based 사용

일반적으로 라우팅에 사용하도록 설정된 게이트웨이에서 인바운드 PSTN Location-Based 라우팅을 사용하도록 설정되어 있으며 동일한 사이트에 있는 Location-Based만 허용됩니다. 그렇지 않은 경우 통화 전송 및 전달은 허용되지 않습니다. 

다음 표에서는 대상 사용자의 위치에 따라 통화 전달 및 통화 전송이 허용되는지 여부를 보여줍니다. 이 표에서 Site1에 있는 User1은 라우팅을 사용하도록 Teams 다른 위치에 있는 다른 사용자에게 Location-Based 전달을 시작합니다.  

|대상 사용자 엔드포인트 위치|User1 호출 전송 시작 |User1 시작 호출 전달|
|---------|---------|---------|
|초기자와 동일한 네트워크 사이트(User2)|허용|허용|
|다른 네트워크 사이트, 사이트 사용 Location-Based 라우팅(User3)|허용되지 않습니다.|허용되지 않습니다.|
|다른 네트워크 사이트, 사이트가 라우팅에 Location-Based(User4)|허용되지 않습니다.|허용되지 않습니다.|
|알 수 없는 내부 네트워크(User5)| 허용되지 않습니다.|허용되지 않습니다.|
|알 수 없는 외부 네트워크(User6)| 허용되지 않습니다.|허용되지 않습니다.|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams PSTN 엔드포인트로 사용자 전송 또는 전달 호출을 전송할 수 있습니다.

#### <a name="user-not-enabled-for-location-based-routing"></a>사용자 라우팅에 Location-Based 설정되지 않습니다.

- PSTN 호출을 다른 PSTN 번호로 전송하고 전달할 수 있습니다. 
- 인바운드 VOIP 호출을 PSTN으로 전송하고 전달하는 경우 호출자의 통화 우회 제한을 존중해야 합니다. 
    - 호출자에서 라우팅을 사용하도록 Location-Based 경우 해당 호출은 라우팅에 사용할 수 없는 모든 PSTN 게이트웨이로 Location-Based 수 있습니다.
    - 호출자에서 라우팅을 Location-Based 경우 동일한 네트워크 사이트에 있는 Location-Based 활성화된 게이트웨이로만 전송할 수 있습니다. 

#### <a name="user-enabled-for-location-based-routing"></a>라우팅에 Location-Based 사용

- 인바운드 호출을 다른 PSTN 번호로 PSTN 호출을 전송하고 전달하려면 인바운드 호출이 도착한 Location-Based 라우팅이 설정된 게이트웨이와 동일한 라우팅을 라우팅해야 합니다. 
- 인바운드 VOIP 호출을 PSTN에 전송하고 전달하는 경우 호출자 및 호출된 사용자의 통화 우회 제한을 모두 존중해야 합니다. 
    - 호출자에서 라우팅을 사용하도록 Location-Based 경우 해당 호출은 라우팅에 사용할 수 없는 모든 PSTN 게이트웨이로 Location-Based 수 있습니다.
    - 호출자에서 라우팅을 Location-Based 경우 동일한 네트워크 사이트에 있는 Location-Based 활성화된 게이트웨이로만 전송할 수 있습니다.
 
다음 표에서는 라우팅이 PSTN 엔드포인트로 Location-Based 다른 위치의 사용자에게 Site1의 User1에서 VOIP 호출 라우팅에 미치는 영향을 보여 주는 것입니다.  

|통화 전송 또는 전달 시작 사용자  |PSTN으로 전송  |PSTN으로 전달  |
|---------|---------|---------|
|동일한 네트워크 사이트, 라우팅에 Location-Based 사이트(User2)   |통화 전송은 User2의 음성 라우팅 정책에 Location-Based Site1에서 라우팅이 설정된 Gateway1을 통해만 라우팅할 수 있습니다.         |호출 전달은 User2의 음성 라우팅 정책에 Location-Based Site1에서 라우팅이 설정된 Gateway1을 통해만 라우팅할 수 있습니다.         |
|다른 네트워크 사이트, 사이트 사용 Location-Based 라우팅(User3)    |통화 전송은 User3의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용할 수 있는 게이트웨이1을 통해만 라우팅할 수 있습니다.         |호출 전달은 User3의 음성 라우팅 정책에 Location-Based Site1에서 라우팅이 설정된 Gateway1을 통해만 라우팅할 수 있습니다.         |
|다른 네트워크 사이트, 사이트가 라우팅에 Location-Based(User4)    |User4의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용할 수 있는 Gateway1을 통해만 통화 전송을 라우팅할 수 있습니다.         |호출 전달은 User4의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용할 수 있는 게이트웨이1을 통해만 라우팅할 수 있습니다.         |
|알 수 없는 내부 네트워크(User5)     |사용자5의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용할 수 있는 Gateway1을 통해만 통화 전송을 라우팅할 수 있습니다.         |호출 전달은 User5의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용할 수 있는 게이트웨이1을 통해만 라우팅할 수 있습니다.         |
|알 수 없는 외부 네트워크(User6)   |사용자6의 음성 라우팅 정책에 따라 Site1에서 라우팅이 Location-Based Gateway1을 통해만 통화 전송을 라우팅할 수 있습니다.        |호출 전달은 User6의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용할 수 있는 게이트웨이1을 통해만 라우팅할 수 있습니다.         |

### <a name="simultaneous-ringing"></a>동시 연결

라우팅을 사용하도록 Location-Based 사용자가 통화를 수신하고 동시 벨소리를 사용하도록 설정한 경우 Location-Based 라우팅은 호출 당사자의 위치와 호출 당사자의 엔드포인트를 분석하여 호출을 라우팅할지 여부를 확인합니다. 동시 벨소리는 통화 Location-Based 전달과 동일한 규칙에 따릅니다. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>다른 사용자에 대한 동시 Teams 울림

다음 표에서는 사용자 Location-Based 인바운드 PSTN 호출에 대해 다른 사용자에게 동시 울림을 허용하는지 여부를 보여줍니다.

|대상 사용자 엔드포인트 위치|동시 링  |
|---------|---------|
|초기자와 동일한 네트워크 사이트(User2)   |허용         |
|라우팅에 대해 사용하도록 Location-Based 다른 로밍된 네트워크 사이트(User3)   |허용되지 않습니다.         |
|로밍된 네트워크 사이트가 라우팅에 Location-Based(User4)   |허용되지 않습니다.        |
|알 수 없는 내부 네트워크(User5)    | 허용되지 않습니다.        |
|알 수 없는 외부 네트워크(User6)    |허용되지 않습니다.        |
|대상 사용자는 PSTN 번호입니다.    |User1의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용할 수 있는 Gateway1을 통해만 호출을 라우팅할 수 있습니다.      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>PSTN 엔드포인트에 대한 동시 벨소리

다음 표에서는 site1에 Location-Based 사용자에서 PSTN 번호로 동시 링이 설정된 다른 위치에 있는 사용자에 대한 인바운드 VOIP 호출에 대한 라우팅 동작이 표시됩니다. 

|사용자 엔드포인트 위치라고 합니다.  |동시 링 대상은 PSTN 엔드포인트입니다. |
|---------|---------|
|동일한 네트워크 사이트, 라우팅에 Location-Based 사이트(User2)    |User2의 음성 라우팅 정책에 따라 Site1의 Location-Based 라우팅 Gateway1을 통해만 호출할 수 있습니다.       |
|라우팅에 Location-Based 다른 네트워크 사이트(User3)    |User3의 음성 라우팅 정책에 따라 Site1의 Location-Based 게이트웨이1을 통해만 호출을 라우팅할 수 있습니다.        |
|다른 네트워크 사이트가 라우팅에 Location-Based(User4)    |User4의 음성 라우팅 정책에 Location-Based Site1의 라우팅 게이트웨이1을 통해만 호출할 수 있습니다.         |
|알 수 없는 내부 네트워크(User5)    |User5의 음성 라우팅 정책에 따라 Site1의 Location-Based 라우팅 Gateway1을 통해만 호출할 수 있습니다.         |
|알 수 없는 외부 네트워크(User6)   |User6의 음성 라우팅 정책에 따라 Site1의 Location-Based 게이트웨이1을 통해만 호출을 라우팅할 수 있습니다.         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>음성 앱을 통한 인바운드 호출(자동 전화 교환 큐 호출)

라우팅이 설정된 Location-Based 게이트웨이의 인바운드 PSTN 호출은 자동 참석자 또는 호출 큐에 연결할 수 있습니다. 라우팅에 Location-Based 활성화된 사용자는 인바운드 PSTN 호출이 시작된 동일한 사이트에 있는 경우 이러한 애플리케이션에서 인바운드 호출 전송을 받을 수 있습니다. 
 
사용자에게 통화 전달 및 동시 벨소리는 음성 앱 전송에 대해 PSTN이 허용됩니다. 대상에 대한 호출을 완료하면 앞에서 나열한 Location-Based 규칙이 적용됩니다.  
 
음성사서로 전달도 허용됩니다.  

### <a name="delegation"></a>위임

사용자 Teams 대신 전화를 걸고 받을 수 있는 대리인을 선택할 수 있습니다. Teams 위임 기능은 다음과 같이 Location-Based 라우팅의 영향을 받는다. 
- 위임자를 대신하여 Location-Based 라우팅이 설정된 대리인의 아웃바운드 호출의 경우 동일한 규칙이 적용됩니다. 통화 라우팅은 대리인의 호출 권한 부여 정책, 음성 라우팅 정책 및 위치를 기반으로 합니다. 자세한 내용은 [PSTN에 Teams](#teams-user-places-an-outbound-call-to-the-pstn) 아웃바운드 호출을 두는 사용자를 참조하세요. 
- 위임자에 대한 인바운드 PSTN 호출의 경우 통화 전달 또는 Location-Based 동시에 울리는 동일한 라우팅 규칙이 대리인에게도 적용됩니다. 자세한 [내용은 다른 Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user) 사용자 전송 또는 전달 Teams, [PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint) 엔드포인트에 대한 사용자 Teams 전달 및 동시 벨소리를 참조[하세요](#simultaneous-ringing). 대리인이 PSTN 엔드포인트를 동시 링 대상으로 설정하면 대리인의 음성 라우팅 정책이 PSTN에 대한 호출을 라우팅하는 데 사용됩니다. 
- 위임의 경우 위임자 및 관련 대리인이 동일한 네트워크 사이트에 있는 것이 좋습니다. 

## <a name="other-planning-considerations"></a>기타 계획 고려 사항

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>라우팅 배포의 Location-Based 변경 내용

네트워크 사이트 음성 라우팅 정책이 더 이상 사용 안 됩니다. 대신 사용자의 음성 라우팅 정책을 사용합니다. 즉, 사용자가 다른 사이트로 로밍할 수 있도록 허용하려면 음성 라우팅 정책에 로밍된 사이트의 게이트웨이가 포함되어야 합니다. 

### <a name="technical-considerations-for-location-based-routing"></a>위치 기반 라우팅을 위한 기술적 고려 사항

IPv4 및 IPv6 서브넷이 지원되는 반면, 일치를 확인할 때 IPv6이 우선합니다.

### <a name="client-support-for-location-based-routing"></a>라우팅에 Location-Based 클라이언트 지원

다음 Teams 클라이언트가 지원됩니다.
- Teams 데스크톱 클라이언트(Windows 및 Mac)
- Teams 클라이언트(iOS 및 Android)
- Teams IP 휴대폰

Teams 클라이언트 및 비즈니스용 Skype 클라이언트는 지원되지 않습니다.

### <a name="capabilities-not-supported-by-location-based-routing"></a>위치 기반 라우팅에서 지원하지 않는 기능

Location-Based 라우팅은 다음 유형의 상호 작용에는 적용되지 않습니다. Location-Based 엔드포인트가 PSTN 엔드포인트와 상호 작용하는 경우 Teams 라우팅이 적용되지 않습니다. 
- 통화 공원을 통한 PSTN 호출 검색 또는 호출 공원 
- 온라인 사용자 또는 비즈니스용 Skype 사용자 또는 비즈니스용 Skype 사용자가 Teams 호출합니다.  

### <a name="location-based-routing-for-conferencing"></a>Location-Based 라우팅

PSTN Location-Based 라우팅이 설정된 사용자는 다른 사용자 또는 PSTN 번호로 회의를 시작할 수 없습니다. 자동 참석자 또는 통화 큐에 연결할 수 있습니다. 사용자에게 회의 라이선스가 있는 경우 사용자는 관련 사용자와의 회의를 시작하고 회의 브리지를 통해 PSTN을 호출하여 전화 회의를 시작해야 합니다.

회의 라이선스가 없는 사용자가 시작한 전화 회의에서 PSTN 참가자를 추가하는 것은 회의 통화에서 라우팅을 사용하도록 설정된 사용자가 Location-Based 있는 경우 허용되지 않습니다. 라우팅을 사용하도록 설정된 모든 참가자가 통화에 참가하기 전에 하나 이상의 PST Location-Based N 참가자가 전화 회의에 참가하거나 일부인 경우 이러한 참가자를 호출에 추가할 수 없습니다.

### <a name="media-bypass-requirement-for-location-based-routing"></a>라우팅에 대한 미디어 Location-Based 요구 사항

인도에서 라우팅을 Location-Based 경우 미디어 우회를 구성해야 합니다. 자세한 [내용은 직접 라우팅](direct-routing-plan-media-bypass.md) 을 통해 미디어 우회 계획 및 직접 라우팅에 대한 [로컬 미디어 최적화를 참조합니다](direct-routing-media-optimization.md).

### <a name="direct-voice-over-ip-voip"></a>IP를 통해 직접 음성(VoIP)

VoIP(직접 음성 IP)는 인도의 전화 통신 장비와 함께 배포할 수 없습니다.

## <a name="next-steps"></a>다음 단계

라우팅에 대한 네트워크 [Location-Based 이동합니다](location-based-routing-configure-network-settings.md).

## <a name="related-topics"></a>관련 항목

- [직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)
- [클라우드 음성 기능에 대한 네트워크 Teams](cloud-voice-network-settings.md)
