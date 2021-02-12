---
title: 비즈니스용 Skype에서 Location-Based 라우팅 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4aa494bd-0d66-4335-b9e8-f758d44a7202
description: 동시 벨 울림 및 위임과의 상호 작용Enterprise Voice 위치 기반 라우팅에 대해 지원되는 시나리오를 포함하여 비즈니스용 Skype 서버의 위치 기반 라우팅 계획
ms.openlocfilehash: 473ed77dce8edaee3b43822adcb8920027795d9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825558"
---
# <a name="plan-for-location-based-routing-in-skype-for-business"></a>비즈니스용 Skype에서 Location-Based 라우팅 계획

동시 벨 울림 및 위임과의 상호 작용Enterprise Voice 위치 기반 라우팅에 대해 지원되는 시나리오를 포함하여 비즈니스용 Skype 서버의 위치 기반 라우팅 계획

Location-Based 라우팅을 사용하면 통화의 당사자 위치에 따라 VoIP 끝점과 PSTN 끝점 간의 통화 라우팅을 제한할 수 있습니다. Location-Based 라우팅은 비즈니스용 Skype 서버에서 통화를 라우팅하는 방법을 제어하는 통화 관리 기능입니다. 통화를 비즈니스용 Skype 발신자 지리적 위치에 따라 PBX 또는 PSTN 끝점으로 라우팅할 수 있는지 여부에 대해 통화 권한 부여 규칙을 적용합니다.

Location-Based 라우팅에는 국내 및 국제 PSTN 통화의 라우팅을 수정하여 전화 우회를 방지하는 새로운 규칙 집합이 도입되었습니다. Location-Based 라우팅은 특정 지역, 특정 게이트웨이 또는 특정 사용자 집합으로 이러한 규칙의 범위를 유연하게 설정할 수 있습니다.

다음 시나리오에서는 라우팅에서 적용할 수 있는 Location-Based 유형의 제한을 설명합니다.

- 발신 전화 - Location-Based 라우팅은 발신자 통화가 PSTN 전화 우회를 방지하는 위치와 동일한 지역에 있는 PSTN 게이트웨이로의 발신 전화를 적용할 수 있습니다. 이 경우 발신자 및 다른 지역에 있는 PSTN 게이트웨이로의 전화가 걸러지지 않습니다.

- 수신 전화 - Location-Based 라우팅은 수신 전화를 라우팅하는 PSTN 게이트웨이가 호출된 비즈니스용 Skype 사용자와 동일한 지역에 있지 않은 경우 수신 PSTN 통화가 비즈니스용 Skype 끝점으로 울리는 것을 방지할 수 있습니다.

- 알 수 없는 지역 - Location-Based 라우팅은 미확인 위치에 있는 사용자(예: 인터넷에서 연결되거나 알 수 없는 지역에 있는 원격 사용자)에게 걸고 받는 PSTN 통화를 제한합니다.

- 국제 지역 - Location-Based 라우팅은 사용자의 위치로 로컬 게이트웨이를 찾을 수 없는 경우 국제 PSTN 게이트웨이를 통해 걸린 통화의 라우팅을 적용합니다.

## <a name="guidance-for-where-to-apply-location-based-routing"></a>라우팅을 적용할 Location-Based 지침

Location-Based 상황에 따라 라우팅을 사용자의 끝점 네트워크 사이트 위치 또는 PSTN 게이트웨이의 네트워크 사이트 위치에 적용할 수 있습니다. 이 항목에서는 라우팅이 적용되는 Location-Based 지침을 제공합니다.

### <a name="applying-location-based-routing-at-the-users-location"></a>사용자 Location-Based 라우팅 적용

Location-Based 라우팅은 E9-1-1, CAC 및 미디어 우회에서 사용하는 비즈니스용 Skype 서버에 정의된 동일한 네트워크 지역, 사이트 및 서브넷을 활용하여 PSTN 전화 우회를 방지하기 위해 통화 라우팅 제한을 적용합니다. 사용자의 위치는 사용자의 비즈니스용 Skype 끝점이 연결된 IP 서브넷에 의해 결정됩니다. 각 IP 서브넷은 관리자가 정의한 네트워크 지역으로 집계되는 네트워크 사이트에 연결됩니다. Location-Based 라우팅은 사용자의 네트워크 사이트에 따라 적용됩니다.

Location-Based 라우팅 규칙은 네트워크 사이트당 적용됩니다. 즉, 동일한 네트워크 사이트에 있는 Location-Based 라우팅에 대해 사용하도록 설정된 모든 끝점에 주어진 규칙 집합이 적용됩니다. 관리자는 필요한 Location-Based 사이트에 대한 라우팅을 적용할 수 있습니다.

음성 라우팅 정책은 네트워크 사이트에 있는 모든 사용자가 PSTN 전화 번호로 전화를 걸 때 사용할 특정 PSTN 게이트웨이를 정의하기 위해 네트워크 사이트당 정의할 수 있습니다. 이러한 음성 라우팅 정책은 사용자가 Location-Based 라우팅을 사용할 수 있는 네트워크 사이트에 있는 경우 사용자의 음성 정책에 정의된 라우팅보다 우선하며 Location-Based 라우팅을 사용하도록 설정된 다른 PSTN 게이트웨이를 통한 통화 라우팅을 방지합니다. 비즈니스용 Skype 사용자가 PSTN 통화를 걸면 사용자의 음성 정책에 따라 사용자에게 통화를 걸 수 있는 권한을 부여할 수 있는지 여부가 결정됩니다. 사용자의 음성 정책에서 사용자가 통화를 걸 수 있도록 허용하는 경우 Location-Based 라우팅에서 통화를 시작해야 하는 PSTN 게이트웨이를 결정할 수 있습니다. Location-Based 라우팅은 사용자의 위치에 따라 결정됩니다.

사용자 위치는 다음과 같은 방식으로 분류할 수 있습니다.

- 사용자가 Location-Based 라우팅을 사용할 수 있는 알려진 네트워크 사이트에 있으며 DID(Direct Inward Dial) 번호는 동일한 네트워크 사이트(예: 사무실)에 있는 PSTN 게이트웨이에서 종료됩니다. 아웃바운드 통화의 라우팅은 사용자가 있는 네트워크 사이트의 음성 라우팅 정책을 통해 진행됩니다. 사용자에 대한 들어오는 PSTN 통화는 PSTN 게이트웨이와 동일한 네트워크 사이트에 있는 끝점으로 라우팅됩니다.

- 사용자는 PSTN 게이트웨이가 있는 네트워크 사이트와 다른 알려진 네트워크 사이트에 있습니다. (예: 사용자가 다른 회사 사무실로 출장했습니다.) 아웃바운드 통화의 라우팅은 사용자가 있는 네트워크 사이트의 음성 라우팅 정책을 사용하게 됩니다. 사용자에 대한 들어오는 PSTN 통화는 PSTN 수신 전화 우회를 방지하기 위해 PSTN 게이트웨이와 다른 사이트에 있는 끝점으로 라우팅되지 않습니다.

- 사용자가 비즈니스용 Skype 서버 배포에 알 수 없는 네트워크 사이트에 있는 경우 아웃바운드 통화 라우팅은 사용자에게 할당된 음성 정책을 기반으로 라우팅 제한에 바인딩되지 않은 PSTN 게이트웨이에 Location-Based 합니다. 들어오는 PSTN 통화는 PSTN 전화 수신자 우회를 방지하기 위해 알 수 없는 네트워크 사이트에 있는 끝점으로 라우팅되지 않습니다.

### <a name="applying-location-based-routing-at-the-pstn-gateways-location"></a>PSTN Location-Based 위치에서 라우팅 적용

PSTN 게이트웨이 및 PBX를 통해 라우팅되는 통화에는 이러한 시스템의 위치에 Location-Based 라우팅 제한이 필요할 수 있습니다. Location-Based 라우팅은 트렁크당 세분성으로 사용하도록 설정될 수 있습니다.

Location-Based 트렁크에서 사용하도록 설정하면 다음과 같은 규칙 집합이 도입됩니다.

- 트렁크 Location-Based 라우팅을 사용하도록 설정하면 규칙은 해당 트렁크를 통해 라우팅되는 통화에만 적용되는 트렁크를 정의합니다.

- PSTN 게이트웨이가 있는 네트워크 사이트와 다른 네트워크 사이트에서 통화가 시작되는 PSTN 전화 우회를 방지하기 위해 Location-Based 라우팅은 네트워크 사이트와 해당 트렁크의 연결에 대해 소개합니다. 이렇게 하면 통화를 특정 트렁크로 라우팅할 수 있는 네트워크 사이트가 정의됩니다.

트렁크는 다음 두 가지 방법으로 Location-Based 라우팅에 대해 사용하도록 설정될 수 있습니다.

- 트렁크는 PSTN으로 전화를 걸고 가는 PSTN 게이트웨이에 대해 정의됩니다. 이 유형의 트렁크가 라우팅하는 수신 전화는 트렁크와 동일한 네트워크 사이트 내에 있는 끝점으로만 라우팅됩니다.

- 트렁크는 PSTN으로의 통화를 전송하지 않는 중재 서버 피어 및 정적 위치(예: PBX 전화)에 레거시 전화가 있는 사용자에 대해 정의됩니다. 이 특정 구성의 경우 이 유형의 트렁크가 라우팅하는 모든 수신 전화는 트렁크와 동일한 네트워크 사이트에서 시작된 것으로 간주됩니다. PBX 사용자의 통화는 트렁크와 동일한 네트워크 사이트에 있는 Location-Based 비즈니스용 Skype 사용자와 동일한 라우팅 적용을 하게 됩니다. 별도의 네트워크 사이트에 있는 두 PBX 시스템이 비즈니스용 Skype 서버를 통해 연결되어 있는 경우 Location-Based 라우팅을 통해 한 네트워크 사이트의 한 PBX 끝점에서 다른 네트워크 사이트의 다른 PBX 끝점으로 라우팅할 수 있습니다. 이 시나리오는 라우팅에 의해 Location-Based 않습니다. 이 시나리오 외에도 동일한 위치에 있는 비즈니스용 Skype 사용자와 유사한 방식으로 이 구성을 통해 중재 서버 피어에 연결된 끝점은 중재 서버 피어가 연결된 네트워크 사이트에 관계없이 PSTN(즉, 다른 PBX에 연결된 끝점)으로 통화를 라우팅하지 않는 다른 중재 서버 피어와 통화를 걸거나 받을 수 있습니다. 모든 인바운드 통화, 아웃바운드 통화, 통화 전송 및 PSTN 끝점과 관련된 통화 전달에는 위치 기반 라우팅이 적용되어 이러한 중재 서버 피어에 대해 로컬로 정의된 PSTN 게이트웨이만 사용할 수 있습니다.

## <a name="scenarios-for-location-based-routing"></a>라우팅에 Location-Based 시나리오

Location-Based 라우팅은 다음 시나리오에서 통화를 라우팅할 때 다음과 같은 일반 규칙을 적용합니다.

### <a name="outgoing-calls"></a>전화를 걸기

Location-Based 라우팅을 사용하도록 설정된 사용자의 아웃바운드 통화 라우팅은 사용자 끝점의 네트워크 위치에 의해 영향을받습니다. 다음 표에서는 Location-Based 라우팅이 발신자 끝점의 위치에 따라 아웃바운드 통화의 라우팅에 어떤 영향을 주는지 보여 주며,

**발신자 PSTN에 아웃바운드 통화**

||**라우팅을 사용하도록 설정된 네트워크 사이트에 있는 Location-Based 끝점**|**알 수 없는 네트워크 사이트에 있는 사용자 끝점 또는 라우팅에 Location-Based 사용되지 않습니다.**|
|:-----|:-----|:-----|
|아웃바운드 통화 권한 부여  <br/> |사용자의 음성 정책에 따라 통화 권한이 부여됩니다.  <br/> |사용자의 음성 정책에 따라 통화 권한이 부여됩니다.  <br/> |
|아웃바운드 통화 라우팅  <br/> |네트워크 사이트의 음성 라우팅 정책에 따라 통화가 라우팅됩니다.  <br/> |통화는 사용자의 음성 정책에 따라 라우팅됩니다. 통화 라우팅에 사용할 수 없는 트렁크만 Location-Based(사용 가능한 경우)  <br/> |

### <a name="incoming-calls"></a>수신 전화

Location-Based 라우팅을 사용하도록 설정된 사용자에 대한 수신 전화 라우팅은 사용자의 끝점 위치에 따라 달라 집니다. 수신 전화 라우팅은 다음과 같은 방식으로 영향을 받을 수 있습니다. Location-Based 라우팅 사용 네트워크 사이트에 있는 끝점에 대한 수신 전화가 있는 경우 끝점이 PSTN 게이트웨이와 동일한 네트워크 사이트에 있는 경우 통화가 라우팅됩니다. Location-Based 라우팅 사용 네트워크 사이트에 있는 끝점에 대한 수신 전화가 있는 경우 끝점이 PSTN 게이트웨이와 다른 네트워크 사이트에 있는 경우 통화가 라우팅되지 않습니다. 사용자에게 수신 전화가 시작되는 PSTN 게이트웨이와 동일한 네트워크 사이트에 끝점이 없는 경우 수신 전화가 사용자의 음성 메일로 직접 라우팅됩니다. 부재 중 전화 알림이 호출된 사용자에게 전송됩니다.

Location-Based 라우팅을 사용하도록 설정된 사용자의 통화 전달 설정은 계속 적용되지만 전달된 통화에는 사용자의 Location-Based 제한이 적용됩니다.

다음 표에서는 Location-Based 라우팅이 발신자 끝점의 위치에 따라 인바운드 통화의 라우팅에 어떤 영향을 주는지 보여 제공합니다. PSTN 게이트웨이의 네트워크 사이트는 Location-Based 라우팅을 사용할 수 있으며 Location-Based 라우팅은 PSTN 통화를 동일한 네트워크 사이트 내의 끝점으로 라우팅하는 것만 허용합니다.

**PSTN에서 인바운드 통화를 수신하는 수신자**

||**PSTN 게이트웨이와 동일한 네트워크 사이트에 있는 발신자 끝점**|**PSTN 게이트웨이와 동일한 네트워크 사이트에 있지 않은 발신자 끝점**|**알 수 없는 네트워크 사이트에 위치하거나 라우팅에 대해 설정되지 않은 Location-Based 끝점**|
|:-----|:-----|:-----|:-----|
|인바운드 PSTN 통화 라우팅  <br/> |수신 전화가 수신자 끝점으로 라우팅됩니다.  <br/> |수신 전화가 수신자 끝점으로 라우팅되지 않습니다.  <br/> |수신 전화가 수신자 끝점으로 라우팅되지 않습니다.  <br/> |

### <a name="call-transfers-and-call-forwarding"></a>통화 전송 및 통화 전달

PSTN 끝점이 관련된 경우 Location-Based 라우팅은 통화를 전송하거나 전달할 끝점(예: 전송/전달 대상)의 위치와 끝점을 분석합니다. Location-Based 라우팅은 두 끝점의 위치에 따라 통화를 전송할지 또는 전달할지 여부를 결정할 수 있습니다.

다음 표에서는 PSTN 끝점과의 통화에서 비즈니스용 Skype 사용자의 시나리오를 보여 주며, 비즈니스용 Skype 사용자는 통화를 다른 비즈니스용 Skype 사용자에게 전송합니다. 전송자 끝점의 네트워크 사이트 위치에 따라 Location-Based 라우팅은 통화 전송 또는 전달의 라우팅에 영향을 미치게 됩니다.

**통화 전송 또는 전달 시작**

|**통화 전송/전달을 시작하는 사용자**|**대상 끝점이 사용자가 통화 전송 또는 전달을 시작하는 네트워크 사이트에 있습니다.**|**사용자가 통화 전송 또는 전달을 시작할 때 대상 끝점이 서로 다른 네트워크 사이트에 있습니다.**|**대상 끝점이 알 수 없는 네트워크 사이트 또는 네트워크 사이트에 있는 경우 라우팅에 사용할 수 Location-Based 없습니다.**|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 사용자  <br/> |전달 또는 전송이 허용됩니다.  <br/> |전달 또는 전송이 허용되지 않습니다.  <br/> |전달 또는 전송이 허용되지 않습니다.  <br/> |

예를 들어 PSTN 끝점이 있는 통화의 비즈니스용 Skype 사용자는 통화를 동일한 네트워크 사이트에 있는 다른 비즈니스용 Skype 사용자에게 전송합니다. 이 경우 통화 전송이 허용됩니다.

다음 표에서는 다른 비즈니스용 Skype 사용자와의 통화에서 비즈니스용 Skype 사용자의 시나리오를 보여 주며 한 사용자가 통화를 PSTN 끝점으로 전송합니다. 통화를 전송하는 사용자의 위치에 따라 이 표에서는 라우팅이 통화에 Location-Based 방법에 대해 자세히 설명합니다.

**통화 전송 또는 PSTN 끝점으로 전달**

|**통화 전송/전달 끝점 대상**|**동일한 네트워크 사이트에 있는 비즈니스용 Skype 사용자**|**서로 다른 네트워크 사이트의 비즈니스용 Skype 사용자**|**알 수 없는 네트워크 사이트 또는 네트워크 사이트의 비즈니스용 Skype 사용자 한 명 또는 Location-Based 라우팅을 사용할 수 없음**|
|:-----|:-----|:-----|:-----|
|PSTN 끝점  <br/> |전송된 사용자의 사이트 음성 라우팅 정책에서 허용된 전달 또는 전송  <br/> |전송된 사용자의 사이트 음성 라우팅 정책에서 허용된 전달 또는 전송  <br/> |전송된 사용자의 음성 정책에서 허용된 통화 전달 또는 전송은 전송 라우팅에 대해 사용하도록 설정되지 않은 트렁크를 통해서만 Location-Based 허용됩니다.  <br/> |

예를 들어 동일한 네트워크 사이트에 있는 다른 비즈니스용 Skype 사용자와 통화하는 비즈니스용 Skype 사용자가 통화를 PSTN 끝점으로 전송하고 통화 전송이 허용됩니다.

### <a name="simultaneous-ringing"></a>동시 벨 울림

발신자에 동시 벨 울림이 설정되면 Location-Based 라우팅은 발신자 위치와 통화 당사자의 끝점을 분석하여 통화를 라우팅할지 여부를 확인합니다.

다음 표에서는 동시 벨 울림으로 구성된 사용자를 보여 주며, 동시 벨 울림 대상은 같은 네트워크 사이트, 다른 네트워크 사이트 또는 알 수 없는 네트워크 사이트에 있는 사용자입니다.

****

|**수신 PSTN 통화**|**발신자와 동일한 네트워크 사이트에 위치**|**다른 네트워크 사이트에 있는 경우**|**알 수 없는 네트워크 사이트에 위치하거나 라우팅에 Location-Based 설정되지 않았습니다.**|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 사용자  <br/> |동시 벨 울림 허용  <br/> |동시 벨 울림이 허용되지 않습니다.  <br/> |동시 벨 울림이 허용되지 않습니다.  <br/> |

다음 표에서는 동일한 네트워크 사이트, 다른 네트워크 사이트 또는 알 수 없는 네트워크 사이트에서 비즈니스용 Skype 사용자(즉, 비즈니스용 Skype 발신자)의 통화를 보여 주며, 발신자에 동시 벨 울림 대상으로 구성된 PSTN 끝점(예: 셀폰)이 있습니다. 이 시나리오에서 Location-Based 라우팅은 통화를 발신자에 대한 동시 벨 울림 대상(즉, 휴대폰)으로 라우팅할지 여부를 결정합니다.

****

|**동시 벨 울림 대상**|**발신자와 동일한 네트워크 사이트에 위치**|**다른 네트워크 사이트에 있는 경우**|**알 수 없는 네트워크 사이트에 위치하거나 라우팅에 Location-Based 설정되지 않았습니다.**|
|:-----|:-----|:-----|:-----|
|PSTN 끝점  <br/> |발신자 사이트 음성 라우팅 정책을 통해 동시 벨 울림 허용  <br/> |발신자 사이트 음성 라우팅 정책을 통해 동시 벨 울림 허용  <br/> |발신자 음성 정책을 통해 동시 벨 울림을 허용하여 발신자 음성 라우팅에 사용할 수 없는 트렁크에 Location-Based 허용  <br/> |

### <a name="skype-for-business-cumulative-update-4"></a>비즈니스용 Skype 누적 업데이트 4

누적 업데이트 4에서는 다음을 볼 수 있습니다.

- Location-Based 라우팅은 비즈니스용 Skype 모바일 클라이언트를 포함하여 음성 정책을 통해 계속 사용하도록 설정됩니다.

- 비즈니스용 Skype 모바일 클라이언트의 통화 동작은 클라이언트가 라우팅을 사용하도록 설정되어 있는지 여부와 통신 클라이언트를 Location-Based 기반합니다. 이는 정적이 되지만 특정 상황에서는 비즈니스용 Skype 모바일 클라이언트를 로컬 PSTN 게이트웨이에 연결하고 에스컬레이터와 같은 특정 동작을 허용하기 위한 노력이 있을 수 있습니다.

- OS에 관계없이 비즈니스용 Skype 모바일 클라이언트의 기능은 동일해야 합니다.

다음 표에서는 누적 업데이트 4 이후 시나리오 중 일부를 설명합니다.

|**위치 기반 라우팅 사용자**|**기타 파티**|**작업**|**결과**|
|:-----|:-----|:-----|:-----|
|비즈니스용 Skype 모바일  <br/> |PSTN  <br/> |비즈니스용 Skype 모바일이 수신하는 PSTN 통화를 수신합니다.  <br/> |통화는 VoIP가 아니라 CvW(직장 전화)를 통해 라우팅됩니다.  <br/> |
|비즈니스용 Skype 모바일  <br/> |PSTN  <br/> |비즈니스용 Skype 모바일에서 발신 PSTN 통화를 합니다.  <br/> |통화는 VoIP가 아니라 CvW를 통해 라우팅됩니다.  <br/> |
|비즈니스용 Skype 모바일  <br/> |PSTN  <br/> |비즈니스용 Skype 모바일이 PSTN 통화 중입니다. 그런 다음 비즈니스용 Skype 모바일에서 통화를 다른 사용자 또는 연락처로 에스컬레이터합니다.  <br/> |사용자 또는 연락처가 PSTN 게이트웨이 레그에 로컬인 경우 통화는 VoIP를 통해 라우팅됩니다.  <br/> 사용자 또는 연락처가 PSTN 게이트웨이 레그에서 원격인 경우 통화는 CvW를 통해 라우팅됩니다.  <br/> PSTN을 통해 대상 사용자에게 연결하지 못하면 통화가 실패합니다.  <br/> 대상 연락처가 CAA(Conference 자동 전화 교환)이면 통화가 차단됩니다.  <br/> |
|비즈니스용 Skype 모바일  <br/> |비즈니스용 Skype 클라이언트 또는 페더리트 사용자  <br/> |A Skype for Business Mobile initiates a voice call to another Skype for Business client or Federated user.  <br/> |VoIP를 통해 통화가 완료됩니다.  <br/> |
|비즈니스용 Skype 모바일  <br/> |비즈니스용 Skype 클라이언트 또는 페더리트 사용자  <br/> | 비즈니스용 Skype 클라이언트 또는 페더러티 사용자가 라우팅 사용자에 대한 음성 통화를 비즈니스용 Skype 모바일 Location-Based 시작됩니다. <br/> |VoIP를 통해 통화가 완료됩니다.  <br/> |
|비즈니스용 Skype 모바일  <br/> |비즈니스용 Skype 클라이언트 또는 페더리트 사용자  <br/> |비즈니스용 Skype 클라이언트 또는 페더타임 사용자가 비즈니스용 Skype 모바일 사용자에 대한 VoIP 통화를 진행 중입니다. 두 사용자 모두 추가 비즈니스용 Skype 또는 페더레이터 사용자로 에스컬레이터합니다.  <br/> |VoIP를 통해 통화가 완료됩니다.  <br/> |
|비즈니스용 Skype 모바일  <br/> |페더레이션 사용자  <br/> |페더링 사용자가 라우팅 사용자와 비즈니스용 Skype 모바일 Location-Based 있습니다. 비즈니스용 Skype 모바일 사용자는 PSTN 사용자에게 에스컬레이터합니다.  <br/> |통화가 차단됩니다.  <br/> |
|비즈니스용 Skype 모바일  <br/> |페더레이션 사용자  <br/> |페더링 사용자가 라우팅 사용자에 대한 VoIP 통화를 비즈니스용 Skype 모바일 Location-Based 있습니다. 어느 한 쪽이 CAA 연락처로 에스컬레이터합니다.  <br/> |적절한 오류 메시지와 함께 에스컬레이터 통화가 차단됩니다.  <br/> |
|비즈니스용 Skype 모바일  <br/> |페더레이션 사용자  <br/> |페더레이터 사용자가 비즈니스용 Skype 모바일 Location-Based 라우팅 사용자에 대한 VoIP 통화를 진행 중이면 페더레이터 사용자가 PSTN 사용자로 에스컬레이터됩니다.  <br/> |페더레이터 사용자의 라우팅에 따라 에스컬레이터가 Location-Based 허용되거나 허용되지 않습니다. 비즈니스용 Skype 모바일 Location-Based 라우팅 사용자의 응용 프로그램은 아무 작업도 수행하지 않습니다.  <br/> |

### <a name="delegation"></a>위임

비즈니스용 Skype의 위임 기능은 다음과 같은 Location-Based 라우팅의 영향을 받을 수 있습니다.

- Location-Based 라우팅에 대해 설정된 대리인이 관리자를 대신하여 전화를 걸면 대리인의 음성 정책이 통화에 권한을 설정하는 데 사용되어 대리인의 사이트 음성 라우팅 정책이 통화를 라우팅하는 데 사용됩니다.

- 관리자에 대한 수신 PSTN 통화의 경우 통화 전달 또는 동시 전화 울림에 적용할 수 있는 동일한 규칙이 통화 전송 및 전달 및 동시 전화 울림 항목에 설명된 바와 같이 적용됩니다.

- 대리인이 PSTN 끝점을 동시 벨 울림 대상으로 설정하면 관리자에 대한 수신 전화에 대해 수신 트렁크에 연결된 사이트의 음성 라우팅 정책이 통화를 대리인의 PSTN 끝점으로 라우팅하는 데 사용됩니다.

- 위임의 경우 관리자와 연결된 대리인은 일반적으로 동일한 네트워크 사이트에 있는 것이 좋습니다.

## <a name="other-planning-considerations"></a>기타 계획 고려 사항

라우팅을 Location-Based 다음과 같은 시나리오에 미치는 영향을 고려해야 합니다.

### <a name="disaster-recovery"></a>재해 복구

기본 풀에서 백업 풀로 장애 조치(failover)를 수행하고 일반 작업을 기본 풀로 복원하는 경우Location-Based 재해 및 복구 절차 중에도 라우팅이 계속 적용됩니다.

### <a name="survivable-branch-appliance"></a>Survivable Branch Appliance

연결 Location-Based 구성하면 Survivable Branch Appliance와 연결된 게이트웨이를 배포하는 위치의 계획에 영향을 미치게 됩니다. SBA에 연결된 게이트웨이는 SBA와 SBA의 SBA(Survivable Branch Appliance)가 같은 네트워크 사이트에 있어야 합니다. 그렇지 않으면 사용자 라우팅이 구성된 경우 Survivable Branch Appliance에 있는 Location-Based 아웃바운드 통화를 걸 수 없습니다. Survivable Branch Appliance와 중앙 사이트 간의 WAN 연결이 다운된 경우 Location-Based 라우팅 제한이 적용됩니다.

## <a name="client-and-server-support-for-location-based-routing"></a>Location-Based 라우팅에 대한 클라이언트 및 서버 지원

Location-Based 라우팅은 비즈니스용 Skype 서버에서 적용됩니다. 비즈니스용 Skype 서버는 사용자가 회사 네트워크 내에서 연결되는 네트워크 사이트를 식별할 수 있습니다. 원격 사용자가 회사 네트워크 외부에 있는 경우 해당 위치는 알 수 없는 것으로 간주됩니다.

### <a name="server-support"></a>서버 지원

Location-Based 라우팅을 사용하려면 비즈니스용 Skype 서버 또는 Lync Server 2013 CU1을 특정 토폴로지의 모든 프런트 엔드 풀 및 Standard Edition 서버에 배포해야 합니다. 이러한 버전의 서버가 설치되어 있지 않은 경우 위치 기반 라우팅 제한을 완전히 적용할 수 없습니다.

다음 표에서는 라우팅에 대해 지원되는 서버 역할과 버전이 Location-Based 식별합니다.

****

|**풀 버전**|**중재 서버 버전**|**지원**|
|:-----|:-----|:-----|
|비즈니스용 Skype 서버 또는 Lync Server 2013 2013년 2월 누적 업데이트  <br/> |비즈니스용 Skype 서버 또는 Lync Server 2013 2013년 2월 누적 업데이트  <br/> |예  <br/> |
|비즈니스용 Skype 서버 또는 Lync Server 2013 2013년 2월 누적 업데이트  <br/> |Lync Server 2013  <br/> |아니요  <br/> |
|비즈니스용 Skype 서버 또는 Lync Server 2013 2013년 2월 누적 업데이트  <br/> |Lync Server 2010  <br/> |아니요  <br/> |
|비즈니스용 Skype 서버 또는 Lync Server 2013 2013년 2월 누적 업데이트  <br/> |Office Communications Server 2007 R2  <br/> |아니요  <br/> |
|Lync Server 2013  <br/> |any  <br/> |아니요  <br/> |
|Lync Server 2010  <br/> |any  <br/> |아니요  <br/> |
|Office Communications Server 2007 R2  <br/> |any  <br/> |아니요  <br/> |

### <a name="client-support"></a>클라이언트 지원

다음 표에서는 라우팅에서 Location-Based 클라이언트를 식별합니다.

****

|**클라이언트 유형**|**지원**|**세부 정보**|
|:-----|:-----|:-----|
|비즈니스용 Skype  <br/> |예  <br/> ||
|Lync 2013  <br/> |예  <br/> ||
|Lync 2010  <br/> |예  <br/> ||
|Office Communicator 2007 R2  <br/> |아니요  <br/> ||
|Lync Phone Edition  <br/> |예  <br/> ||
|Lync Attendant  <br/> |예  <br/> ||
|Lync for Windows 8  <br/> |아니요  <br/> ||
|Lync Mobile 2013  <br/> |아니요  <br/> |라우팅을 사용하는 사용자가 Lync Mobile 2013 클라이언트에 대해 voIP를 Location-Based 수 없습니다.  <br/> |
|Lync Mobile 2010  <br/> |예  <br/> ||

> [!NOTE]
> 비즈니스용 Skype 클라이언트에 대해 VoIP를 사용하지 않도록 설정하고, IP 오디오/비디오 설정을 사용하여 모바일 정책을 할당합니다. IP 오디오/비디오는 라우팅을 사용하도록 설정된 모든 사용자에 대해 Location-Based 합니다. 모바일 정책에 대한 자세한 내용은 [New-CsMobilityPolicy를 참조합니다.](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)

## <a name="capabilities-not-supported-by-location-based-routing"></a>라우팅에서 지원되지 Location-Based 기능

Location-Based 라우팅은 다음 유형의 조작에 적용되지 않습니다. Location-Based 비즈니스용 Skype 끝점이 이러한 기능을 사용하여 PSTN 끝점과 상호 작용할 때 라우팅이 적용되지 않습니다.

- 전화 회의에 대한 PSTN 전화 접속

- 응답 그룹을 통한 수신 및 걸기 PSTN 통화

- 통화 파크를 통한 통화 파크 또는 PSTN 통화 검색

- 알림 서비스에 대한 수신 PSTN 통화

- 그룹 통화 Pickup을 통해 검색된 수신 PSTN 통화

다음 Location-Based 유형의 상호 작용에 대해 라우팅 규칙을 적용하려면 회의에 대해 Location-Based 라우팅을 사용하도록 설정해야 합니다.

- 회의에서 PSTN 전화 접속

- 피어 투 피어 오디오 대화에서 PSTN 끝점과 관련된 회의로의 에스컬링

- PSTN 끝점과 관련된 컨설팅 전송

회의에 Location-Based 라우팅을 사용하도록 설정하려면 회의에 대한 위치 기반 라우팅을 [참조하세요.](https://technet.microsoft.com/library/e1acb1ba-0ed2-4abf-8a7b-1ca3049e95e3.aspx)


