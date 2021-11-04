---
title: PSTN 연결 구성 요소의 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: Enterprise Voice SIP 트렁크 및 PSTN 게이트웨이에 대해 비즈니스용 Skype 서버.
ms.openlocfilehash: d0650f4948837fdb169c1c4a3672e25dccb8012f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746734"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>PSTN 연결 구성 요소의 비즈니스용 Skype 서버
 
Enterprise Voice SIP 트렁크 및 PSTN 게이트웨이에 대해 비즈니스용 Skype 서버.
  
엔터프라이즈급 VoIP 솔루션은 QoS(서비스 품질)를 떨어트려도 PSTN(공용 전화망)과의 통화를 제공해야 합니다. 또한 사용자가 전화를 걸고 받을 때의 기술에 대해 인식하지 못해야 합니다. 사용자 관점에서 볼 때 Enterprise Voice 인프라와 PSTN 간의 통화는 다른 SIP 세션처럼 보일 것입니다.
  
PSTN 연결의 경우 SIP 트렁크 또는 PSTN 게이트웨이(직접 SIP 링크라고도 하는 PBX 또는 PBX 없이)를 배포할 수 있습니다.
  
## <a name="sip-trunking"></a>SIP 트렁크

PSTN 게이트웨이를 사용하는 대신 SIP 트렁크를 사용하여 Enterprise Voice 솔루션을 PSTN에 연결할 수 있습니다. SIP 트렁크를 사용하면 다음과 같은 시나리오를 할 수 있습니다.
  
- 회사 방화벽 내부 또는 외부의 엔터프라이즈 사용자는 PSTN에서 해당 서비스 공급자의 서비스로 종료되는 E.164 규격 번호로 지정된 로컬 또는 시외 전화를 걸 수 있습니다.
    
- 모든 PSTN 구독자는 해당 엔터프라이즈 사용자와 연결된 DID(Direct Inward Dialing) 번호로 전화를 걸면 회사 방화벽 내부 또는 외부의 엔터프라이즈 사용자에게 연락할 수 있습니다.
    
이 배포 솔루션을 사용하려면 SIP 트렁크 서비스 공급자가 필요합니다. 
  
## <a name="pstn-gateways"></a>PSTN 게이트웨이

PSTN 게이트웨이는 Enterprise Voice 인프라와 PSTN 또는 PBX 간에 신호 및 미디어를 변환하는 타사 장치입니다. PSTN 게이트웨이는 중재 서버와 함께 작동하여 PSTN 또는 PBX 통화를 Enterprise Voice 클라이언트에 제공합니다. 또한 중재 서버는 Enterprise Voice PSTN 또는 PBX로 라우팅하기 위한 PSTN 게이트웨이로의 통화도 제공합니다. Microsoft와 협력하여 사용자와 함께 작업하는 장치를 제공하는 파트너 비즈니스용 Skype 서버 [Microsoft Unified Communications Partners 웹 사이트를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=202836) 
  
## <a name="private-branch-exchanges"></a>Private Branch Exchange

 PBX(Private Branch Exchange)를 사용하는 기존 음성 인프라가 있는 경우 PBX를 PBX와 함께 사용할 수 Enterprise Voice.
  
지원되는 Enterprise Voice-PBX 통합 시나리오는 다음과 같습니다.
  
- 중재 서버를 통해 미디어 우회를 지원하는 IP-PBX입니다.
    
- 독립 실행형 PSTN 게이트웨이가 필요한 IP-PBX
    
- 독립 실행형 PSTN 게이트웨이가 있는 TDM(Time Division Multiplexing) PBX
    
> [!NOTE]
> 미디어 바이패스가 모든 PSTN 게이트웨이, IP-PBX 및 SBC에서 작동하지는 않습니다. Microsoft는 인증된 파트너와 함께 PSTN 게이트웨이 및 SBC 집합을 테스트하고 Cisco IP-PBX에 대한 몇 가지 테스트를 수행했습니다. 미디어 우회는 [Unified Communications Open Interoperability Program - Lync Server에](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)나열된 제품 및 버전에서만 지원됩니다. 
  
Enterprise Voice 파트너에 대한 자세한 내용은 [Microsoft Unified Communications Partners 웹](https://go.microsoft.com/fwlink/p/?linkId=202836)사이트를 참조하십시오.
  
PSTN 게이트웨이를 포함하여 Enterprise Voice 하드웨어 솔루션을 제공하는 파트너에 대한 자세한 내용은 [Microsoft Unified Communications Partners 웹](https://go.microsoft.com/fwlink/p/?linkId=202836)사이트를 참조하십시오.
