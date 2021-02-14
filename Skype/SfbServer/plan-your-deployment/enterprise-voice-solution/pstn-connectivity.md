---
title: 비즈니스용 Skype 서버의 PSTN 연결 구성 요소
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
ms.assetid: 6b2a3f7d-760f-4f09-8432-312c98a7e6b7
description: 비즈니스용 Skype 서버에서 SIP 트렁크 Enterprise Voice PSTN 게이트웨이에 대해 자세히 알아보습니다.
ms.openlocfilehash: 6261b95906699777e62c025889d23e03d381f09d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813538"
---
# <a name="pstn-connectivity-components-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 PSTN 연결 구성 요소
 
비즈니스용 Skype 서버에서 SIP 트렁크 Enterprise Voice PSTN 게이트웨이에 대해 자세히 알아보습니다.
  
엔터프라이즈급 VoIP 솔루션은 QoS(서비스 품질)를 떨어트려도 PSTN(공용 전화망)과의 통화를 제공해야 합니다. 또한 사용자가 전화를 걸고 받을 때의 기술에 대해 인식하지 못합니다. 사용자 관점에서 볼 때 Enterprise Voice 인프라와 PSTN 간의 통화는 다른 SIP 세션처럼 보일 것입니다.
  
PSTN 연결의 경우 SIP 트렁크 또는 PSTN 게이트웨이(PBX를 직접 SIP 링크라고도 하는 경우 또는 PBX 없이)를 배포할 수 있습니다.
  
## <a name="sip-trunking"></a>SIP 트렁크

PSTN 게이트웨이를 사용하는 대신 SIP 트렁크를 사용하여 Enterprise Voice 솔루션을 PSTN에 연결할 수 있습니다. SIP 트렁크를 사용하면 다음과 같은 시나리오를 할 수 있습니다.
  
- 회사 방화벽 내부 또는 외부의 엔터프라이즈 사용자는 해당 서비스 공급자의 서비스로 PSTN에서 종료되는 E.164 규격 번호로 지정된 로컬 또는 시외 전화를 걸 수 있습니다.
    
- PSTN 구독자는 해당 엔터프라이즈 사용자와 연결된 DID(Direct Inward Dialing) 번호로 전화를 걸면 회사 방화벽 내부 또는 외부의 엔터프라이즈 사용자에게 연락할 수 있습니다.
    
이 배포 솔루션을 사용하려면 SIP 트렁크 서비스 공급자가 필요합니다. 
  
## <a name="pstn-gateways"></a>PSTN 게이트웨이

PSTN 게이트웨이는 Enterprise Voice 인프라와 PSTN 또는 PBX 간에 신호 및 미디어를 변환하는 타사 장치입니다. PSTN 게이트웨이는 중재 서버와 함께 작동하여 PSTN 또는 PBX 통화를 Enterprise Voice 클라이언트에 제공합니다. 또한 중재 서버는 PSTN 또는 PBX로의 라우팅을 위해 Enterprise Voice 클라이언트에서 PSTN 게이트웨이로의 통화를 제공합니다. 비즈니스용 Skype 서버에서 사용할 수 있는 장치를 제공하기 위해 Microsoft와 협력하는 파트너 목록은 [Microsoft Unified Communications Partners 웹 사이트를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=202836) 
  
## <a name="private-branch-exchanges"></a>Private Branch Exchange

 PBX(Private Branch Exchange)를 사용하는 기존 음성 인프라가 있는 경우 PBX와 함께 사용할 수 Enterprise Voice.
  
지원되는 Enterprise Voice-PBX 통합 시나리오는 다음과 같습니다.
  
- 중재 서버를 통해 미디어 우회를 지원하는 IP-PBX입니다.
    
- 독립 실행형 PSTN 게이트웨이가 필요한 IP-PBX입니다.
    
- 독립 실행형 PSTN 게이트웨이가 있는 TDM(Time Division Multiplexing) PBX
    
> [!NOTE]
> 미디어 바이패스가 모든 PSTN 게이트웨이, IP-PBX 및 SBC에서 작동하지는 않습니다. Microsoft는 인증된 파트너와 함께 PSTN 게이트웨이 및 SBC 집합을 테스트하고 Cisco IP-PBX를 통해 몇 가지 테스트를 수행했습니다. 미디어 우회는 [Unified Communications Open Interoperability Program - Lync Server에](https://go.microsoft.com/fwlink/p/?linkId=214406)나열된 제품 및 버전에서만 지원됩니다. 
  
솔루션 솔루션을 제공하는 파트너에 대한 자세한 Enterprise Voice [Microsoft Unified Communications Partners 웹 사이트를 참조하세요.](https://go.microsoft.com/fwlink/p/?linkId=202836)
  
PSTN 게이트웨이를 포함하여 Enterprise Voice 하드웨어 솔루션을 제공하는 파트너에 대한 자세한 내용은 [Microsoft Unified Communications Partners 웹](https://go.microsoft.com/fwlink/p/?linkId=202836)사이트를 참조하십시오.
  

