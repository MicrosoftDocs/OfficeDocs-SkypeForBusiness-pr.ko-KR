---
title: 직접 라우팅으로 전달되는 위치 기반 라우팅 계획
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: roykuntz
search.appverid: MET150
description: 직접 라우팅에 Location-Based 라우팅을 계획하는 방법을 배워야 합니다.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: f05049cdc181aef72f9ed018f20cd8d2e3264909
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822928"
---
# <a name="plan-location-based-routing-for-direct-routing"></a>직접 라우팅으로 전달되는 위치 기반 라우팅 계획

## <a name="overview-of-location-based-routing"></a>Location-Based 라우팅 개요

일부 국가 및 지역에서는 PSTN(Public Switched Telephone Network) 공급자를 우회하여 장거리 통화 비용을 절감하는 것이 불법입니다. 이 문서에서는 지리적 위치에 따라 Location-Based 라우팅을 사용하여 Microsoft Teams 사용자에 대한 우회를 제한하는 방법을 설명하고 있습니다. 이 문서는 전화 시스템 직접 라우팅에만 적용됩니다.

여기서는 계획하는 데 도움이 되는 Location-Based 라우팅 및 지침에 대한 개요를 제공합니다. 라우팅을 적용하고 사용하도록 Location-Based 경우 다음을 참조합니다.

- [라우팅에 대한 네트워크 Location-Based 배포](location-based-routing-configure-network-settings.md)
- [직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)

> [!NOTE]
> Location-Based 라우팅은 Microsoft 365 GCC(Government Community Cloud) 높음 또는 DoD 배포에서 사용할 수 없습니다.

Location-Based 라우팅은 인바운드 또는 아웃바운드 PSTN 통화 시 정책 및 사용자의 지리적 위치에 따라 전화 우회를 제한할 수 있는 기능입니다. Location-Based 라우팅은 에지 우회를 방지하는 메커니즘을 제공하기 위한 것입니다. 사용자의 위치에 따라 PSTN 호출을 동적으로 라우팅하거나 의도하지 않은 결과가 발생할 수 있는 메커니즘으로 사용되지 말아야 합니다.

Teams 사용자가 라우팅에 대해 Location-Based 경우 다음이 적용됩니다.

- 아웃바운드 PSTN 호출을 만들 경우 다음 중 하나에 해당해야 합니다.
    - 사용자의 엔드포인트는 Location-Based 라우팅에 사용할 수 있는 네트워크 사이트에 있으며 Location-Based 라우팅에 사용하도록 설정된 해당 게이트웨이를 통해 Location-Based 호출합니다. 
    - 사용자의 엔드포인트는 Location-Based 라우팅에 사용할 수 없는 네트워크 사이트에 있으며, Location-Based 라우팅에 사용할 수 없는 게이트웨이를 통해 Location-Based 호출합니다.

    아웃바운드 호출은 다른 시나리오에서는 허용되지 않습니다.

- 인바운드 PSTN 호출을 수신하려면 사용자의 응답 엔드포인트가 라우팅에 대해 사용하도록 설정된 게이트웨이를 통해 호출이 수신되는 동일한 네트워크 사이트에 Location-Based 합니다. 사용자가 로밍하는 경우와 같은 다른 시나리오에서는 통화가 허용되지 않습니다. 사용자의 통화 전달 설정(일반적으로 음성 메시지)으로 라우팅됩니다.
- 다른 Teams 사용자에게 PSTN 통화를 전송하려면 대상 사용자의 엔드포인트가 전송을 시작하는 사용자와 동일한 네트워크 사이트에 있어야 합니다. 다른 시나리오에서는 전송이 허용되지 않습니다. 
- 다른 Teams 사용자를 PSTN으로 전송하려면 초기 호출자와 동일한 네트워크 사이트에 있는 Location-Based 라우팅 사용 게이트웨이를 통해 통화를 전송해야 합니다. 다른 시나리오에서는 전송이 허용되지 않습니다.

Location-Based 라우팅은 비즈니스용 Skype Server에서 사용하는 동일한 네트워크 지역, 사이트 및 서브넷 정의를 사용합니다. 한 위치에 대해 toll 우회가 제한되는 경우 관리자는 각 IP 서브넷과 해당 위치에 대한 각 PSTN 게이트웨이를 네트워크 사이트에 연결합니다. 사용자의 위치는 사용자의 Teams 엔드포인트가 PSTN 호출 시 연결되는 IP 서브넷에 의해 결정됩니다. 사용자는 서로 다른 사이트에 여러 Teams 클라이언트가 있을 수 있습니다. 이 경우 Location-Based 라우팅은 해당 엔드포인트의 위치에 따라 각 클라이언트의 라우팅을 개별적으로 적용합니다. 

이 문서에 사용된 네트워크 용어 중 일부를 익숙하게 사용하려면 Teams의 클라우드 음성 기능에 대한 네트워크 [설정을 참조하세요.](cloud-voice-network-settings.md)

## <a name="apply-location-based-routing"></a>라우팅 Location-Based 적용

사용자, Location-Based 사이트 및 PSTN 게이트웨이에 라우팅을 적용해야 합니다.  

### <a name="apply-location-based-routing-at-the-user-location"></a>사용자 Location-Based 라우팅 적용

앞에서 설명한 대로 Location-Based 라우팅은 직접 라우팅에 대해 설정된 사용자에게만 적용됩니다. Location-Based 라우팅은 통화 요금제에 대해 설정된 사용자에게는 적용되지 않습니다. 사용자가 PSTN 호출을 걸고 받을 수 있는 조건과 사용할 수 있는 PSTN 게이트웨이를 제어하는 Location-Based 우회 제한을 받는 경우 사용자 라우팅을 사용하도록 설정해야 합니다. Location-Based 라우팅을 사용하도록 설정된 사용자가 Location-Based 라우팅을 사용하도록 설정된 사이트에 있는 경우 사용자는 사이트에 연결된 Location-Based 라우팅 사용 게이트웨이를 통해 전화를 걸 수 있어야 합니다. 

Location-Based 라우팅은 사용자의 Teams 엔드포인트의 IP 주소를 기반으로 사용자의 현재 위치를 결정하여 작동하고 그에 따라 규칙을 적용합니다. Location-Based 라우팅을 사용하도록 설정된 사용자의 위치는 다음과 같은 방법으로 분류할 수 있습니다. 
- **사용자가 DID가 할당된 PSTN 게이트웨이에 Location-Based 라우팅이 설정된 동일한 사이트에 있습니다.**<br>이 시나리오에서 사용자는 Location-Based 라우팅에 사용할 수 있는 알려진 네트워크 사이트에 있으며 사용자의 DID(Direct Inward Dial) 번호는 동일한 네트워크 사이트에 있는 PSTN 게이트웨이에서 종료됩니다. 예를 들어 사용자가 사무실에 있습니다. 
- **사용자가 DID가 할당된 PSTN Location-Based 연결되지 않은 다른 라우팅 사용 사이트에 있습니다.**<br>이 시나리오에서 사용자는 Location-Based 라우팅을 사용하도록 설정된 알려진 네트워크 사이트에 있으며 해당 사이트는 사용자의 DID 번호가 할당된 PSTN 게이트웨이와 연결되지 않습니다. 예를 들어 사용자가 다른 사무실로 출장합니다.  
- **사용자는 사용자 라우팅에 대해 사용하도록 설정되지 않은 내부 Location-Based 있습니다.** <br>이 시나리오에서 사용자는 라우팅에 사용할 수 없는 알려진 내부 네트워크 사이트에 Location-Based 있습니다. 
- **사용자가 알 수 없는 사이트에 있습니다.** 
    - 사용자는 네트워크 사이트로 정의되지 않은 내부 네트워크 내에 있습니다. 
    - 사용자가 내부 네트워크 외부에 있습니다. 예를 들어 사용자는 집이나 커피숍에 있는 인터넷에 있습니다. 

### <a name="apply-location-based-routing-at-the-network-site"></a>네트워크 Location-Based 라우팅 적용 
네트워크 사이트는 로밍할 Location-Based 라우팅이 설정된 사용자를 라우팅할 게이트웨이를 Location-Based 사용하도록 설정해야 합니다. Location-Based 라우팅을 사용하도록 설정된 사용자가 Location-Based 라우팅을 사용하도록 설정된 사이트로 로밍하는 경우 해당 사이트에서 Location-Based 라우팅을 사용하도록 설정된 PSTN 게이트웨이만 아웃바운드 호출에 사용할 수 있습니다. Location-Based 라우팅을 사용하도록 설정된 사용자가 Location-Based 라우팅을 사용할 수 없는 사이트로 로밍하는 경우 Location-Based 라우팅에 사용할 수 없는 게이트웨이를 아웃바운드 호출에 사용할 수 있습니다.  

### <a name="apply-location-based-routing-at-the-pstn-gateway"></a>PSTN Location-Based 라우팅 적용 

게이트웨이는 PSTN 통화를 걸거나 받을 때 Location-Based 라우팅을 사용할 수 있는 사용자를 확인할 수 있는 사이트에 연결됩니다. 게이트웨이는 Location-Based 라우팅에 대해 사용하도록 설정되어 있어야 하여 해당 게이트웨이가 toll 우회 제한을 준수하고 해당 라우팅을 사용하도록 설정되지 않은 사용자가 사용할 수 Location-Based 합니다. 동일한 게이트웨이가 여러 사이트에 연결될 수 있으며 사이트에 따라 Location-Based 라우팅에 대해 사용하도록 구성하거나 Location-Based 라우팅을 사용하도록 구성할 수 있습니다.

## <a name="scenarios-for-location-based-routing"></a>위치 기반 라우팅 시나리오

이 섹션에서는 Location-Based 라우팅을 사용하여 무료 우회를 제한하는 다양한 시나리오를 설명하고 Location-Based 라우팅을 사용하도록 설정되지 않은 사용자와 통화를 라우팅하는 방법을 Location-Based 방법을 비교합니다.

- [Teams 사용자가 PSTN에 아웃바운드 통화를 걸 수 있습니다.](#teams-user-places-an-outbound-call-to-the-pstn)
- [Teams 사용자가 PSTN에서 인바운드 통화를 수신합니다.](#teams-user-receives-an-inbound-call-from-the-pstn)
- [Teams 사용자가 다른 Teams 사용자에게 통화를 전송하거나 전달합니다.](#teams-user-transfers-or-forwards-call-to-another-teams-user)
- [Teams 사용자가 PSTN 엔드포인트로 통화를 전송하거나 전달합니다.](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)
- [동시 연결](#simultaneous-ringing)
- [위임](#delegation)

다음 다이어그램에서는 각 시나리오에서 라우팅을 Location-Based 제한 사항을 보여 줍니다. 사용자, 네트워크 사이트 및 Location-Based 라우팅에 사용할 수 있는 게이트웨이에는 테두리가 있습니다. 다이어그램을 가이드로 사용하여 각 시나리오에서 라우팅이 Location-Based 방법을 이해할 수 있습니다.  

![라우팅에 대한 시나리오를 Location-Based 다이어그램](media/lbr-direct-routing.png "라우팅에 대한 시나리오를 Location-Based 다이어그램")

### <a name="teams-user-places-an-outbound-call-to-the-pstn"></a>Teams 사용자가 PSTN에 아웃바운드 통화를 걸 수 있습니다.

#### <a name="user-not-enabled-for-location-based-routing"></a>사용자 라우팅에 대해 Location-Based 설정되지 않은 경우

Location-Based 라우팅을 사용할 수 없는 사용자는 할당된 음성 라우팅 정책을 통해 Location-Based 모든 사이트에서 게이트웨이를 사용하여 아웃바운드 통화를 걸 수 있습니다. 그러나 게이트웨이가 Location-Based 라우팅을 사용하도록 설정되어 있는 경우 사용자는 음성 라우팅 정책에 할당된 경우에도 게이트웨이를 통해 아웃바운드 호출을 걸 수 없습니다. 사용자가 Location-Based 라우팅을 사용할 수 있는 사이트로 로밍하는 경우 해당 라우팅에 대해 사용하도록 설정되지 않은 일반 라우팅 게이트웨이를 통해서만 호출할 Location-Based 있습니다.
 
#### <a name="user-enabled-for-location-based-routing"></a>사용자 라우팅에 Location-Based 사용하도록 설정
반면, Location-Based 라우팅을 사용하도록 설정된 사용자에 대한 아웃바운드 호출 라우팅은 사용자의 엔드포인트의 네트워크 위치에 영향을 미치게 됩니다. 다음 표에서는 사용자 Location-Based User1의 위치에 따라 사용자1의 아웃바운드 호출 라우팅에 영향을 주는 방법을 보여 주는 표입니다. 

|User1 엔드포인트 위치  |User1에 대한 아웃바운드 호출 라우팅  |
|---------|---------|
|사용자의 DID가 할당된 동일한 사이트, Location-Based 라우팅을 사용하도록 설정된 사이트(Site1)      |사용자의 음성 라우팅 정책에 따라 Site1에서 GW1(Location-Based 라우팅)에 사용하도록 설정된 게이트웨이를 통해 라우팅된 호출         |
|사용자의 DID가 할당된 사이트와 다른 사이트, Location-Based 라우팅(Site2)    |사용자의 음성 라우팅 정책에 따라 roam Site2에서 Location-Based 라우팅(GW2)에 사용하도록 설정된 게이트웨이를 통해 라우팅된 호출        |
|사용자의 DID가 할당된 사이트와 다른 사이트, Location-Based 라우팅(Site3)  |사용자의 음성 라우팅 정책에 따라 Location-Based 라우팅(GW3)에 사용할 수 없는 Location-Based 라우팅에 사용할 수 없는 게이트웨이를 통해 라우팅된 호출       |
|알 수 없는 내부 네트워크(Location4)    |  PSTN 통화가 허용되지 않습니다.       |
|알 수 없는 외부 네트워크(Location5)    | PSTN 통화가 허용되지 않습니다.        |

### <a name="teams-user-receives-an-inbound-call-from-the-pstn"></a>Teams 사용자가 PSTN에서 인바운드 통화를 수신합니다.

#### <a name="user-not-enabled-for-location-based-routing"></a>사용자 라우팅에 대해 Location-Based 설정되지 않은 경우

Location-Based 라우팅을 사용하도록 설정하지 않은 사용자는 할당된 DID 번호 수신을 Location-Based 게이트웨이에서 인바운드 호출을 받을 수 있습니다. 사용자가 Location-Based 라우팅을 사용할 수 없는 사이트로 로밍하는 경우 일반 PSTN 게이트웨이를 통해 호출을 받을 수 있습니다.
  
#### <a name="user-enabled-for-location-based-routing"></a>사용자 라우팅에 Location-Based 사용하도록 설정

이에 비해, Location-Based 라우팅을 사용하도록 설정된 사용자는 동일한 사이트에 있을 때 DID이 할당된 PSTN 게이트웨이에서만 인바운드 호출을 받을 수 있습니다. 다음 표에서는 User1이 다른 네트워크 위치로 이동할 때 User1이 인바운드 호출을 받는 방법을 보여줍니다. 호출이 사용자의 엔드포인트로 라우팅되지 않는 경우 설정이 구성된 경우 사용자의 통화 전달 설정으로 이동합니다. 일반적으로 음성 메시지입니다.  

|User1 엔드포인트 위치  |User1에 대한 인바운드 호출 라우팅  |
|---------|---------|
|사용자의 DID가 할당된 사이트와 동일한 사이트, Location-Based 라우팅(Site1)   | Site1에서 User1의 엔드포인트로 라우팅된 호출        |
|사용자의 DID가 할당된 사이트와 다른 사이트, Location-Based 라우팅(Site2)    | Site2의 엔드포인트로 라우팅되지 않는 호출        |
|사용자의 DID가 할당된 사이트와 다른 사이트, Location-Based 라우팅(Site3)    | Site3의 엔드포인트로 라우팅되지 않는 호출        |
|알 수 없는 내부 네트워크(Location4)   | Location4의 엔드포인트로 라우팅되지 않는 호출        |
|알 수 없는 외부 네트워크(Location5)     | Location5의 엔드포인트로 라우팅되지 않는 호출        |

### <a name="teams-user-transfers-or-forwards-call-to-another-teams-user"></a>Teams 사용자가 다른 Teams 사용자에게 통화를 전송하거나 전달합니다.

PSTN 엔드포인트가 관련된 경우 Location-Based 라우팅은 Location-Based 라우팅에 대해 한 사용자 또는 둘 다를 사용하도록 설정되어 있는지 여부를 분석하고 두 엔드포인트의 위치에 따라 호출을 전송하거나 전달해야 하는지 여부를 확인합니다. 
 
통화 전송을 사용하려면 착신전화 착신을 착신전송할 때 초기 호출에 응답할 필요가 없는 동안 시작 사용자가 통화를 선택해야 합니다. 즉, User1이 인바운드 통화를 받을 위치에 있지 않은 경우에도(Teams 사용자가 [PSTN](#teams-user-receives-an-inbound-call-from-the-pstn) 섹션에서 인바운드 통화를 수신하는 테이블 참조) User1이 인바운드 통화를 받을 수 없는 경우 통화를 전송할 수 없습니다. 

#### <a name="user-not-enabled-for-location-based-routing"></a>사용자 라우팅에 대해 Location-Based 설정되지 않은 경우

Location-Based 라우팅을 사용할 수 없는 사용자는 PSTN 통화를 라우팅에 사용할 수 없는 다른 사용자에게 전송하거나 전달할 Location-Based 있습니다. 일반적으로 Location-Based 라우팅을 사용하도록 설정된 사용자는 PSTN 통화에 대한 Location-Based 라우팅 사용 게이트웨이에서만 공동으로 위치할 수 있기 때문에 사용자는 일반적으로 Location-Based 라우팅을 사용하도록 설정된 사용자에게 PSTN 통화를 전송하거나 전달할 수 없습니다. 예외는 Location-Based 라우팅을 사용하도록 설정되지 않은 사이트로 Location-Based 경우입니다. 이 시나리오에서는 전송된 호출이 허용됩니다.  

마찬가지로, Location-Based 라우팅을 사용할 수 없는 사용자는 다른 사용자로부터 전송 또는 전달된 PSTN 통화만 받을 수 Location-Based 있습니다. 

#### <a name="user-enabled-for-location-based-routing"></a>사용자 라우팅에 Location-Based 사용하도록 설정

일반적으로 Location-Based 라우팅에 사용하도록 설정된 게이트웨이에서 인바운드 PSTN 호출을 전송하고 전달하는 것은 대상 사용자가 Location-Based 라우팅을 사용하도록 설정되어 있으며 동일한 사이트에 있는 경우만 허용됩니다. 그렇지 않으면 통화 전송 및 전달이 허용되지 않습니다. 

다음 표에서는 대상 사용자의 위치에 따라 통화 전달 및 통화 전송이 허용되는지 여부를 보여줍니다. 이 표에서 Site1에 있는 User1은 사용자 라우팅을 사용하도록 설정되어 있으며 다른 위치에 있는 다른 Teams Location-Based 이전 또는 전달을 시작됩니다.  

|대상 사용자 엔드포인트 위치|User1에서 통화 전송 시작 |User1에서 착신전화 시작|
|---------|---------|---------|
|초기자와 동일한 네트워크 사이트(User2)|허용|허용|
|다른 네트워크 사이트, 사용자 라우팅에 Location-Based 사이트(User3)|허용되지 않습니다.|허용되지 않습니다.|
|다른 네트워크 사이트, 사이트가 Location-Based 라우팅(User4)|허용되지 않습니다.|허용되지 않습니다.|
|알 수 없는 내부 네트워크(User5)| 허용되지 않습니다.|허용되지 않습니다.|
|알 수 없는 외부 네트워크(User6)| 허용되지 않습니다.|허용되지 않습니다.|

### <a name="teams-user-transfers-or-forwards-call-to-pstn-endpoint"></a>Teams 사용자가 PSTN 엔드포인트로 통화를 전송하거나 전달합니다.

#### <a name="user-not-enabled-for-location-based-routing"></a>사용자 라우팅에 대해 Location-Based 설정되지 않은 경우

- 다른 PSTN 번호로 PSTN 통화 전송 및 전달이 허용됩니다. 
- 인바운드 VOIP 호출을 PSTN으로 전송하고 전달하는 경우 호출자에 대한 전화 우회 제한을 적용해야 합니다. 
    - Location-Based 라우팅에 대해 호출을 사용하도록 설정하지 않은 경우 해당 라우팅에 대해 사용하도록 설정되지 않은 모든 PSTN 게이트웨이로 Location-Based 수 있습니다.
    - 호출자에서 라우팅을 Location-Based 경우 동일한 네트워크 사이트에 있는 Location-Based 라우팅 사용 게이트웨이로만 전송될 수 있습니다. 

#### <a name="user-enabled-for-location-based-routing"></a>사용자 라우팅에 Location-Based 사용하도록 설정

- 인바운드 호출을 다른 PSTN 번호로 전송하고 전달하려면 인바운드 호출이 도착한 Location-Based 라우팅이 설정된 게이트웨이와 동일하게 라우팅되어야 합니다. 
- 인바운드 VOIP 호출을 PSTN으로 전송하고 전달하는 경우 호출자 및 호출된 사용자의 전화 우회 제한을 모두 적용해야 합니다. 
    - Location-Based 라우팅에 대해 호출을 사용하도록 설정하지 않은 경우 해당 라우팅에 대해 사용하도록 설정되지 않은 모든 PSTN 게이트웨이로 Location-Based 수 있습니다.
    - 호출자 Location-Based 라우팅을 사용하도록 설정한 경우 동일한 네트워크 사이트에 있는 Location-Based 라우팅을 사용하도록 설정된 게이트웨이로만 전송될 수 있습니다.
 
다음 표에서는 사용자 Location-Based 라우팅이 Site1의 User1에서 PSTN 엔드포인트로 통화를 전송하거나 전달하는 다른 위치의 사용자에게 VOIP 호출을 라우팅하는 데 어떤 영향을 주는지 보여줍니다.  

|사용자가 착신전송 또는 전달을 시작하는 경우  |PSTN으로 전송  |PSTN으로 전달  |
|---------|---------|---------|
|동일한 네트워크 사이트, 사용자 라우팅에 Location-Based 사이트(User2)   |통화 전송은 User2의 음성 라우팅 정책에 Location-Based Site1에서 라우팅이 설정된 Gateway1을 통해서만 라우팅할 수 있습니다.         |전달은 User2의 음성 Location-Based 정책에 따라 Site1에서 Location-Based 사용하도록 설정된 Gateway1을 통해서만 라우팅할 수 있습니다.         |
|다른 네트워크 사이트, 사용자 라우팅에 Location-Based 사이트(User3)    |통화 전송은 User3의 음성 라우팅 정책에 Location-Based Site1에서 라우팅을 사용하도록 설정된 Gateway1을 통해서만 라우팅할 수 있습니다.         |사용자 3의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용하도록 설정된 Gateway1을 통해서만 통화 전달을 라우팅할 수 있습니다.         |
|다른 네트워크 사이트, 사이트가 Location-Based 라우팅(User4)    |통화 전송은 User4의 음성 라우팅 정책에 Location-Based Site1에서 라우팅을 사용하도록 설정된 Gateway1을 통해서만 라우팅할 수 있습니다.         |사용자 4의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용하도록 설정된 Gateway1을 통해서만 통화 전달을 라우팅할 수 있습니다.         |
|알 수 없는 내부 네트워크(User5)     |통화 전송은 User5의 음성 라우팅 정책에 Location-Based Site1에서 라우팅을 사용하도록 설정된 Gateway1을 통해서만 라우팅할 수 있습니다.         |사용자5의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용하도록 설정된 Gateway1을 통해서만 통화 전달을 라우팅할 수 있습니다.         |
|알 수 없는 외부 네트워크(User6)   |통화 전송은 User6의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용하도록 설정된 Gateway1을 통해서만 라우팅할 수 있습니다.        |사용자 6의 음성 라우팅 정책에 따라 Site1에서 Location-Based 사용하도록 설정된 Gateway1을 통해서만 통화 전달을 라우팅할 수 있습니다.         |

### <a name="simultaneous-ringing"></a>동시 연결

Location-Based 라우팅을 사용하도록 설정된 사용자가 통화를 수신하고 동시 연결 기능을 사용하도록 설정한 경우 Location-Based 라우팅은 호출 당사자의 위치와 호출 당사자의 엔드포인트를 분석하여 통화를 라우팅해야 하는지 여부를 확인합니다. 동시 벨소리는 통화 Location-Based 전달과 동일한 기본 규칙을 따릅니다. 

#### <a name="simultaneous-ringing-for-another-teams-user"></a>다른 Teams 사용자에 대한 동시 벨소리

다음 표에서는 사용자 Location-Based 사용자 1에 대한 인바운드 PSTN 호출에 대해 서로 다른 사용자에게 동시 벨 울림을 허용하는지 여부를 보여줍니다.

|대상 사용자 엔드포인트 위치|동시 링  |
|---------|---------|
|초기자와 동일한 네트워크 사이트(User2)   |허용         |
|사용자 라우팅(User3)에 대해 Location-Based 로밍된 다른 네트워크 사이트   |허용되지 않습니다.         |
|라우팅에 대해 로밍된 네트워크 Location-Based(User4)   |허용되지 않습니다.        |
|알 수 없는 내부 네트워크(User5)    | 허용되지 않습니다.        |
|알 수 없는 외부 네트워크(User6)    |허용되지 않습니다.        |
|대상 사용자가 PSTN 번호입니다.    |통화는 User1의 음성 Location-Based 정책에 따라 Site1에서 Location-Based 사용하도록 설정된 Gateway1을 통해서만 라우팅할 수 있습니다.      |

#### <a name="simultaneous-ringing-to-a-pstn-endpoint"></a>PSTN 엔드포인트에 동시 벨 울림

다음 표에서는 Location-Based PSTN 번호로 동시 링이 설정된 다른 위치의 사용자로 Site1의 인바운드 VOIP 호출에 대한 라우팅 동작을 보여줍니다. 

|호출된 사용자 엔드포인트 위치  |동시 링 대상은 PSTN 엔드포인트입니다. |
|---------|---------|
|동일한 네트워크 사이트, 사용자 라우팅에 Location-Based 사이트(User2)    |User2의 음성 라우팅 정책에 따라 Site1의 Location-Based 라우팅 Gateway1을 통해서만 통화를 라우팅할 수 있습니다.       |
|사용자 라우팅에 사용할 수 있는 Location-Based 네트워크 사이트(User3)    |통화는 User3의 음성 라우팅 정책에 Location-Based Site1의 라우팅 Gateway1을 통해서만 라우팅할 수 있습니다.        |
|사용자 라우팅에 사용할 수 없는 다른 네트워크 Location-Based(User4)    |통화는 User4의 음성 라우팅 정책에 Location-Based Site1의 라우팅 Gateway1을 통해서만 라우팅할 수 있습니다.         |
|알 수 없는 내부 네트워크(User5)    |통화는 User5의 음성 라우팅 정책에 Location-Based Site1의 라우팅 Gateway1을 통해서만 라우팅할 수 있습니다.         |
|알 수 없는 외부 네트워크(User6)   |User6의 음성 라우팅 정책에 따라 Site1에서 Location-Based 라우팅 Gateway1을 통해서만 통화를 라우팅할 수 있습니다.         |

#### <a name="inbound-calls-through-voice-app-auto-attendant-or-call-queue"></a>음성 앱을 통한 인바운드 통화(자동 전화 교환 또는 통화 큐)

라우팅이 설정된 Location-Based 게이트웨이의 인바운드 PSTN 통화는 자동 전화 접속 또는 통화 큐에 연결할 수 있습니다. Location-Based 라우팅을 사용하도록 설정된 사용자는 인바운드 PSTN 호출이 시작된 동일한 사이트에 있을 때만 이러한 애플리케이션에서 인바운드 호출 전송을 받을 수 있습니다. 
 
음성 앱 전송에 대해 사용자 및 PSTN에 대한 통화 전달 및 동시 벨소리가 허용됩니다. 대상에 대한 호출을 완료하면 앞에서 나열한 동일한 Location-Based 규칙이 따릅니다.  
 
음성메일로 전달도 허용됩니다.  

### <a name="delegation"></a>위임

Teams 사용자는 대신 전화를 걸고 받을 수 있는 대리인을 선택할 수 있습니다. Teams의 위임 기능은 다음과 같은 Location-Based 라우팅의 영향을 받습니다. 
- 위임자를 대신하여 Location-Based 라우팅이 설정된 대리자로부터의 아웃바운드 호출의 경우 동일한 규칙이 적용됩니다. 통화 라우팅은 대리인의 통화 권한 부여 정책, 음성 라우팅 정책 및 위치를 기반으로 합니다. 자세한 내용은 Teams 사용자가 [PSTN에 아웃바운드 호출을 던진 경우를 참조하세요.](#teams-user-places-an-outbound-call-to-the-pstn) 
- 위임자에 대한 인바운드 PSTN 통화의 경우 통화 전달 또는 Location-Based 동시에 울리는 동일한 라우팅 규칙이 대리인에게도 적용됩니다. 자세한 내용은 Teams 사용자 전송 또는 다른 Teams 사용자에게 통화 전달, [Teams](#teams-user-transfers-or-forwards-call-to-another-teams-user)사용자 전송 또는 [PSTN](#teams-user-transfers-or-forwards-call-to-pstn-endpoint)엔드포인트로 통화 전달, 동시 벨 울림을 [참조하세요.](#simultaneous-ringing) 대리인이 PSTN 엔드포인트를 동시 링 대상으로 설정하는 경우 대리인의 음성 라우팅 정책은 PSTN으로 통화를 라우팅하는 데 사용됩니다. 
- 위임의 경우 위임자 및 관련 대리인을 동일한 네트워크 사이트에 두는 것이 좋습니다. 

## <a name="other-planning-considerations"></a>기타 계획 고려 사항

### <a name="changes-from-an-on-premises-location-based-routing-deployment"></a>라우팅 배포에 대한 Location-Based 변경 내용

네트워크 사이트 음성 라우팅 정책은 더 이상 사용 안 됩니다. 대신 사용자의 음성 라우팅 정책을 사용합니다. 즉, 사용자가 다른 사이트로 로밍할 수 있도록 허용하려면 음성 라우팅 정책에 로밍된 사이트의 게이트웨이가 포함되어야 합니다. 

### <a name="technical-considerations-for-location-based-routing"></a>위치 기반 라우팅을 위한 기술적 고려 사항

IPv4 및 IPv6 서브넷이 지원됩니다. 그러나 일치를 확인할 때 IPv6이 우선합니다.

### <a name="client-support-for-location-based-routing"></a>Location-Based 라우팅에 대한 클라이언트 지원

지원되는 Teams 클라이언트는 다음과 같습니다.
- Teams 데스크톱 클라이언트(Windows 및 Mac)
- Teams 모바일 클라이언트(iOS 및 Android)
- Teams IP 전화기

Teams 웹 클라이언트 및 비즈니스용 Skype 클라이언트는 지원되지 않습니다.

### <a name="capabilities-not-supported-by-location-based-routing"></a>위치 기반 라우팅에서 지원하지 않는 기능

Location-Based 라우팅은 다음과 같은 유형의 상호 작용에 적용되지 않습니다. Location-Based 라우팅은 Teams 엔드포인트가 다음 시나리오에서 PSTN 엔드포인트와 상호 작용할 때 적용되지 않습니다. 
- 통화 공원을 통한 PSTN 통화 검색 또는 호출 
- 비즈니스용 Skype 사용자 또는 비즈니스용 Skype Online 사용자가 Teams 사용자로 전화를 걸 수 있습니다.  

### <a name="location-based-routing-for-conferencing"></a>Location-Based 라우팅

PSTN Location-Based 라우팅이 설정된 사용자는 다른 사용자 또는 PSTN 번호로 전화 회의를 시작할 수 없습니다. 자동 전화 회의 또는 통화 큐에 연결할 수 있습니다. 사용자에게 회의 라이선스가 있는 경우 사용자는 관련 사용자와 회의를 시작하고 전화 회의 브리지를 통해 PSTN에 전화를 걸고 전화 회의를 시작해야 합니다.  

### <a name="media-bypass-requirement-for-location-based-routing"></a>라우팅에 대한 미디어 Location-Based 요구 사항

인도에서 라우팅을 Location-Based 경우 미디어 우회도 구성해야 합니다. 자세한 내용은 직접 [](direct-routing-plan-media-bypass.md) 라우팅을 통해 미디어 우회 계획 및 직접 라우팅에 대한 로컬 미디어 최적화를 [참조합니다.](direct-routing-media-optimization.md)

### <a name="direct-voice-over-ip-voip"></a>VoIP(Direct Voice over IP)

VoIP(Direct Voice over IP)는 인도의 전화 통신 장비와 함께 배포할 수 없습니다.

## <a name="next-steps"></a>다음 단계

Location-Based 라우팅에 대한 네트워크 [설정 구성으로 이동합니다.](location-based-routing-configure-network-settings.md)

## <a name="related-topics"></a>관련 항목

- [직접 라우팅에 위치 기반 라우팅 사용](location-based-routing-enable.md)
- [Teams의 클라우드 음성 기능에 대한 네트워크 설정](cloud-voice-network-settings.md)
