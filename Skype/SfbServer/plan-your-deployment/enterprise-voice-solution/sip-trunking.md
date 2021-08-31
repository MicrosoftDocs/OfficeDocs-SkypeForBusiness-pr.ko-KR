---
title: SIP 트렁크의 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
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
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: SIP 트렁크에 대한 자세한 비즈니스용 Skype 서버 Enterprise Voice
ms.openlocfilehash: d10f14a8c3f65309c52351a0721aa042faad47b6
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728237"
---
# <a name="sip-trunking-in-skype-for-business-server"></a>SIP 트렁크의 비즈니스용 Skype 서버

SIP 트렁크에 대한 자세한 비즈니스용 Skype 서버 Enterprise Voice

SIP(Session Initiation Protocol)는 기본 전화 서비스 및 인스턴트 메시징, 회의, 현재 상태 감지, 멀티미디어 등의 추가 실시간 통신 서비스에 대한 VoIP(Voice over IP) 통신 세션을 시작 및 관리하는 데 사용됩니다. 이 섹션에서는 로컬 네트워크의 경계를 넘어 확장되는 SIP 연결 유형인 SIP 트렁크를 구현하기 위한 계획 정보를 제공합니다.

## <a name="what-is-sip-trunking"></a>SIP 트렁크란?

SIP 트렁크는 조직과 방화벽 너머의 ITSP(인터넷 전화 통신 서비스 공급자) 간의 SIP 통신 링크를 설정하는 IP 연결입니다. 일반적으로 SIP 트렁크는 조직의 중앙 사이트를 ITSP에 연결하는 데 사용됩니다. 일부의 경우 분기 사이트를 ITSP에 연결하는 데에도 SIP 트렁크를 사용하도록 선택할 수 있습니다.

SIP 트렁크 배포는 조직의 통신을 단순화하고 실시간 통신에 대한 향상된 최신 기능을 준비하는 데 큰 도움이 될 수 있습니다. SIP 트렁크의 주요 이점 중 하나는 조직의 연결을 중앙 사이트의 PSTN(Public Switched Telephone Network)에 통합할 수 있는데, 이는 일반적으로 각 분기 사이트에서 별도의 트렁크가 필요한 선행 TDM(Time Division Multiplexing) 트렁크가 아니라는 것입니다.

### <a name="cost-savings"></a>비용 절감

SIP 트렁크와 관련된 비용 절감은 크게 증가할 수 있습니다.

- 일반적으로 장거리 통화는 SIP 트렁크를 통해 비용이 훨씬 적습니다.

- 관리 가능성 비용을 절감하고 배포 복잡성을 줄일 수 있습니다.

- SIP 트렁크를 ITSP에 직접 연결하는 경우 상당히 낮은 비용으로 SIP 트렁크를 연결할 경우 BRI(기본 요금 인터페이스) 및 PRI(기본 요금 인터페이스) 수수료를 제거할 수 있습니다. TDM 트렁크에서 서비스 공급자는 분당 통화에 대해 요금을 부과합니다. SIP 트렁크의 비용은 대역폭 사용량을 기반으로 할 수 있습니다. 이 경우 더 작고 경제적인 증분으로 구입할 수 있습니다. 실제 비용은 선택한 ITSP의 서비스 모델에 따라 다릅니다.

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a>SIP 트렁크와 PSTN 게이트웨이 또는 IP-PBX 호스팅 비교

SIP 트렁크는 서비스 공급자에 직접 연결하기 때문에 PSTN 게이트웨이와 관리 비용 및 복잡성을 제거할 수 있습니다. SIP 트렁크를 사용하는 경우 유지 관리 및 관리가 줄어들어 비용이 크게 절감될 수 있습니다.

### <a name="expanded-voip-services"></a>확장된 VoIP 서비스

음성 기능은 종종 SIP 트렁크 배포의 주요 동기가 되지만 음성 지원은 첫 번째 단계에 불과합니다. SIP 트렁크를 사용하면 VoIP 기능을 확장하고 더 비즈니스용 Skype 서버 서비스를 제공할 수 있습니다. 예를 들어 다음과 같습니다.

- 휴대폰을 실행하지 않는 비즈니스용 Skype 서버 향상된 현재 상태 검색을 통해 휴대폰과 더 나은 통합을 제공할 수 있으므로 사용자가 휴대폰 통화 중일 때를 볼 수 있습니다.

- E9-1-1 긴급 통화를 통해 911 통화에 응답하는 기관은 자신의 전화 번호에서 발신자 위치를 확인할 수 있습니다.

> [!NOTE]
> ITSP에 문의하여 조직에서 지원하고 사용하도록 설정할 수 있는 서비스 목록을 확인하세요.

### <a name="sip-trunks-vs-direct-sip-connections"></a>SIP 트렁크와 Direct SIP 연결

트렁크 용어는 회로 전환 기술에서 파생됩니다. 전화 전환 장비를 연결하는 전용 실제 선을 지칭합니다. 선행 TDM(시간 분할 다중화) 트렁크와 마찬가지로 SIP 트렁크는 두 개의 별도 SIP 네트워크인 비즈니스용 Skype 서버 엔터프라이즈와 ITSP 간의 연결입니다. 회로 전환 트렁크와 달리 SIP 트렁크는 지원되는 모든 SIP 트렁크 연결 유형에 대해 설정될 수 있는 가상 연결입니다.

반면에 Direct SIP 연결은 로컬 네트워크 경계를 가로지르지 않는 SIP 연결입니다(즉, 내부 네트워크 내에서 PSTN(공중 전화망) 게이트웨이 또는 PBX(Private Branch Exchange)에 연결됨). 사용자와 직접 SIP 연결을 사용하는 방법에 대한 자세한 비즈니스용 Skype 서버 에서 [직접 SIP 연결을 비즈니스용 Skype 서버.](direct-sip.md)

## <a name="how-do-i-implement-sip-trunking"></a>SIP 트렁크를 구현하는 방법

SIP 트렁크를 구현하려면 비즈니스용 Skype 서버 클라이언트와 서비스 공급자 간의 통신 세션에 대한 프록시 역할을 하는 중재 서버를 통해 연결을 라우팅하고 필요한 경우 미디어를 코드 변환해야 합니다.

각 중재 서버에는 내부 네트워크 인터페이스와 외부 네트워크 인터페이스가 있습니다. 내부 인터페이스는 프런트 엔드 서버에 연결됩니다. 외부 인터페이스는 일반적으로 중재 서버를 PSTN(Public Switched Telephone Network) 게이트웨이 또는 IP-PBX에 연결하는 데 사용되었습니다. SIP 트렁크를 구현하기 위해 중재 서버의 외부 인터페이스를 ITSP의 외부 에지 구성 요소에 연결합니다. ITSP의 외부 에지 구성 요소는 SBC(Session Border Controller), 라우터 또는 게이트웨이일 수 있습니다.

중재 서버에 대한 자세한 내용은 의 중재 서버 구성 [요소를 비즈니스용 Skype 서버.](mediation-server.md)

### <a name="centralized-vs-distributed-sip-trunking"></a>중앙 집중식 SIP 트렁크와 분산형 SIP 트렁크

중앙 집중식 SIP 트렁크는 분기 사이트 트래픽을 비롯한 모든 VoIP 트래픽을 중앙 사이트를 통해 라우팅합니다. 중앙 집중식 배포 모델은 단순하고 비용 효과적인 모델로, 일반적으로 중앙 집중식 배포 모델을 사용하여 SIP 트렁크를 구현하는 비즈니스용 Skype 서버.

분산 SIP 트렁크는 하나 이상의 분기 사이트에서 로컬 SIP 트렁크를 구현하는 배포 모델입니다. 그런 다음 VoIP 트래픽은 중앙 사이트를 거치지 않고 분기 사이트에서 서비스 공급자로 직접 라우팅됩니다.

분산형 SIP 트렁크는 다음과 같은 경우에만 필요합니다.

- 분기 사이트에 지속 가능한 전화 연결(예: WAN이 다운된 경우)이 필요한 경우. 이 요구 사항은 각 분기 사이트에 대해 분석해야 합니다. 일부 분기는 중복 및 장애 조치(failover)가 필요할 수 있는 반면 다른 분기는 중복 및 장애 조치(failover)가 필요할 수 있습니다.

- 두 중앙 사이트 간에는 탄력성이 필요합니다. 각 중앙 사이트에서 SIP 트렁크가 종료되는지 확인해야 합니다. 예를 들어 Dublin 및 Tukwila 중앙 사이트가 있으며 둘 다 사이트의 SIP 트렁크를 하나만 사용하는 경우 트렁크가 다운될 경우 다른 사이트의 사용자가 PSTN 호출을 할 수 없습니다.

- 분기 사이트와 중앙 사이트는 서로 다른 국가/지역에 있습니다. 호환성 및 규정 준수를 위해 국가/지역당 하나 이상의 SIP 트렁크가 필요합니다. 예를 들어 유럽 연합에서 통신은 중앙 지점에서 로컬로 종료하지 않고는 국가/지역을 떠날 수 없습니다.

사이트의 지리적 위치와 엔터프라이즈 내에서 예상되는 트래픽의 양에 따라 일부 사용자를 중앙 SIP 트렁크를 통해 라우팅하지 않을 수도, 아니면 분기 사이트의 SIP 트렁크를 통해 일부 사용자를 라우팅할 수도 있습니다. 다음 질문에 대한 대답을 통해 요구 사항을 분석할 수 있습니다.

- 각 사이트(즉, 사이트 사용 가능 사용자 수)의 Enterprise Voice?

- 각 사이트의 DID(Direct Inward Dialing) 번호로 전화를 가장 많이 걸 수 있는 번호는 무엇입니까?

중앙 집중식 SIP 트렁크를 배포할지 또는 분산된 SIP 트렁크를 배포할지 여부를 결정하려면 비용 이익 분석이 필요합니다. 경우에 따라 분산형 배포 모델이 필요하지 않은 경우에도 이 모델이 훨씬 이익인 경우가 있을 수 있습니다. 완전히 중앙화된 배포에서는 모든 분기 사이트 트래픽이 WAN 링크를 통해 라우팅됩니다. WAN 링크에 필요한 대역폭에 대한 비용을 지불하는 대신 분산형 SIP 트렁크를 사용할 수 있습니다. 예를 들어 Standard Edition 사이트에 중앙 사이트에 페더럴이 있는 Standard Edition 서버를 배포하거나 작은 게이트웨이를 통해 Survivable Branch Appliance 또는 Survivable Branch Server를 배포할 수 있습니다.

> [!NOTE]
> 분산된 SIP 트렁크에 대한 자세한 내용은 에서 분기 사이트 [SIP 트렁크를 비즈니스용 Skype 서버.](branch-site.md)

### <a name="supported-sip-trunking-connection-types"></a>지원되는 SIP 트렁크 연결 유형

비즈니스용 Skype 서버 SIP 트렁크에 대해 다음 연결 유형을 지원할 수 있습니다.

- MPLS(Multiprotocol Label Switching)는 하나의 네트워크 노드에서 다음 네트워크 노드로 데이터를 전달하는 개인 네트워크입니다. MPLS 네트워크의 대역폭은 다른 구독자와 공유하며, 각 데이터 패킷에는 구독자의 데이터를 다른 구독자의 데이터와 구분하는 레이블이 할당됩니다. 이 연결 형식에는 VPN(가상 사설망)이 필요하지 않습니다. 그러나 VoIP 트래픽이 우선적으로 적용되지 않는 경우 과도한 IP 트래픽으로 인해 VoIP 작업이 방해를 받을 수 있다는 단점이 있습니다.

- 다른 트래픽이 없는 개인 연결(예: 임대된 광섬유 연결 또는 T1 줄)은 일반적으로 가장 안정적이고 안전한 연결 유형입니다. 이 연결 유형은 통화 수행 용량이 가장 높지만 일반적으로 비용이 가장 많이 드는 연결 유형입니다. VPN은 필요하지 않습니다. 개인 연결은 통화량이 높거나 엄격한 보안 및 가용성 요구 사항이 있는 조직에 적절합니다.

- 인터넷은 비용이 가장 저렴한 연결 유형이지만 안정성도 가장 저렴합니다. 인터넷 연결은 VPN이 비즈니스용 Skype 서버 SIP 트렁크 연결 유형 중 유일한 연결입니다.

#### <a name="selecting-a-connection-type"></a>연결 유형 선택

회사에 가장 적절한 SIP 트렁크 연결 유형은 요구 사항 및 예산에 따라 결정됩니다.

- 중소기업의 경우 일반적으로 MPLS 네트워크가 가장 큰 가치를 제공합니다. MPLS 네트워크는 전문화된 개인 네트워크보다 저렴한 비용으로 필요한 대역폭을 제공할 수 있습니다.

- 대기업은 개인 광섬유, T1, T3 이상 연결(유럽 연합의 경우 E1, E3 이상)이 필요할 수 있습니다.

- 통화량이 적은 소규모 기업 또는 분기 사이트의 경우 인터넷을 통한 SIP 트렁크를 가장 적합한 선택이 될 수 있습니다. 이 연결 유형은 중간 규모 또는 대규모 사이트에는 권장되지 않습니다.

### <a name="bandwidth-requirements"></a>대역폭 요구 사항

구현에 필요한 대역폭의 양은 통화 용량(지원할 수 있어야 하는 동시 통화 수)에 따라 다를 수 있습니다. 지불한 최대 용량을 모두 활용할 수 있도록 대역폭 가용성을 고려해야 합니다. 다음 수식을 사용하여 SIP 트렁크 최대 대역폭 요구 사항을 계산합니다.

SIP 트렁크 최대 대역폭 = 최대 동시 통화 x(64 kbps + 헤더 크기)

> [!NOTE]
> 헤더 크기는 최대 20비트입니다.

### <a name="codec-support"></a>코덱 지원

비즈니스용 Skype 서버 다음 코덱만 지원됩니다.

- G.711 a-law(주로 북미 이외의 다른 지역에서 사용)

- G.711 µ-law(북미에서 사용)

### <a name="internet-telephony-service-provider"></a>인터넷 전화 통신 서비스 공급자

SIP 트렁크 연결의 서비스 공급자 쪽을 구현하는 방법은 ITSP에 따라 다릅니다. 배포 정보에 대해서는 서비스 공급자에 문의하십시오. 인증된 SIP 트렁크 서비스 공급자 목록은 [Microsoft Unified Communications Open Interoperability Program website](../../../SfbPartnerCertification/lync-cert/qualified-ip-pbx-gateway.md)를 참조하십시오.

Microsoft 인증 SIP 트렁크 공급자에 대한 자세한 내용은 Microsoft 담당자에게 문의하십시오.

> [!IMPORTANT]
> Microsoft 인증 서비스 공급자를 사용하여 ITSP가 SIP 트렁크를 트래버스하는 모든 기능(예: 세션 설정 및 관리와 모든 확장된 VoIP 서비스 지원)을 지원하도록 해야 합니다. Microsoft 기술 지원은 인증되지 않은 공급자를 사용하는 구성으로 확장되지 않습니다. 현재 SIP 트렁크에 대해 인증되지 않은 인터넷 서비스 공급자를 사용하는 경우 해당 공급자를 ISP로 계속 사용하고 SIP 트렁크를 위해 Microsoft에서 인증한 공급자를 사용할 수 있습니다.

### <a name="topologies-and-components-for-sip-trunking"></a>SIP 트렁크용 토폴로지 및 구성 요소

다음 그림에서는 2013의 SIP 트렁크 토폴로지가 비즈니스용 Skype 서버.

**SIP 트렁크 토폴로지**

![SIP 트렁크 토폴로지.](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

다이어그램에 나온 것처럼 엔터프라이즈 네트워크 및 PSTN(공중 전화망) 서비스 공급자 간의 연결에 IP VPN(가상 사설망)이 사용됩니다. 이 사설망의 목적은 IP 연결을 제공하고 보안을 향상시키며 선택적으로 QoS(서비스 품질) 보증을 얻는 것입니다. VPN의 특성으로 인해 SIP 신호 트래픽을 위한 TLS(Transport Layer Security)나 미디어 트래픽을 위한 SRTP(실시간 전송 프로토콜)를 사용할 필요가 없습니다. 따라서 엔터프라이즈와 서비스 공급자 간의 연결은 SIP를 위한 일반 TCP 연결 및 IP VPN을 통해 터널링되는 미디어를 위한 UDP를 통한 일반 RTP(실시간 전송 프로토콜)로 구성됩니다. 이때 VPN 라우터 간 모든 방화벽에서는 VPN 라우터가 통신할 수 있도록 포트를 열어 놓아야 하고 VPN 라우터의 외부 에지에 대한 IP 주소는 공개적으로 라우팅 가능한 주소여야 합니다.

> [!IMPORTANT]
> 서비스 공급자에게 문의하여 장애 조치(failover)를 비롯한 고가용성 지원을 제공하는지 여부를 확인하십시오. 이 경우 설정 절차를 결정해야 합니다. 예를 들어 각 중재 서버에서 하나의 IP 주소와 하나의 SIP 트렁크만 구성해야 하는지 아니면 각 중재 서버에서 여러 SIP 트렁크를 구성해야 합니까? > 중앙 사이트가 여러 개 있는 경우 서비스 공급자가 다른 중앙 사이트와의 연결을 사용하도록 설정할 수 있는지도 묻습니다.

> [!NOTE]
> SIP 트렁크의 경우 독립 실행형 중재 서버를 배포하는 것이 좋습니다. 자세한 내용은 배포 설명서의 [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers)를 참조하십시오.

### <a name="securing-the-mediation-server-for-sip-trunking"></a>SIP 트렁크에 대해 중재 서버 보호

보안을 위해 두 VPN 라우터 간의 각 연결에 대해 VLAN(가상 LAN)을 설치해야 합니다. VLAN의 실제 설치 프로세스는 라우터 제조업체별로 다릅니다. 자세한 내용은 라우터 공급업체에 문의하십시오.

다음 지침을 따르는 것이 좋습니다.

- 중재 서버와 경계 네트워크의 VPN 라우터(DMZ, 비무장 영역 및 스크린된 서브넷) 사이에 VLAN(가상 LAN)을 설치합니다.

- 라우터에서 VLAN으로 브로드캐스트나 멀티캐스트 패킷이 전송되는 것을 허용하지 않습니다.

- 라우터에서 중재 서버가 아니라 다른 곳으로 트래픽을 라우팅하는 라우팅 규칙을 차단합니다.

VPN 서버를 사용하는 경우 다음 지침을 따르는 것이 좋습니다.

- VPN 서버와 중재 서버 간에 VLAN을 설정합니다.

- VPN 서버에서 VLAN으로 브로드캐스트나 멀티캐스트 패킷이 전송되는 것을 허용하지 않습니다.

- VPN 서버 트래픽을 중재 서버가 있는 모든 곳으로 라우팅하는 라우팅 규칙을 차단합니다.

- GRE(Generic Routing Encapsulation)를 사용하여 VPN의 데이터를 암호화합니다.

## <a name="see-also"></a>기타 참고 항목

[분기 사이트 SIP 트렁크 비즈니스용 Skype 서버](branch-site.md)