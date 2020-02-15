---
title: Lync Server 2013 SIP 트렁크 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fd2bd6d66b8b4f040e654f2412f86027071f9ac
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42039048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Lync Server 2013의 SIP 트렁크 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

SIP 트렁크에 Enterprise Voice를 사용 하려는 경우 중재 서버를 배포 하 고 다른 인프라 및 구성 요소가 배포 모델에 적합 한 지원 요구 사항을 충족 하는지 확인 해야 합니다. SIP 트렁크를 구현할지 여부를 결정 하는 방법에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 sip 트렁크 개요](lync-server-2013-overview-of-sip-trunking.md) 를 참조 하세요.

Microsoft 통합 통신 오픈 상호 운용성 프로그램을 사용 하 여 엔터프라이즈 전화 통신 인프라에 대 한 정규화 된 공공 전화망 (PSTN) 게이트웨이, IP-Pbx 및 SIP 트렁크 서비스 (자격 부여 된 IP 전화 통신 포함)를 찾을 수 있습니다. 서비스 공급자 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램 웹 사이트를 참조 하세요.

<div>

## <a name="mediation-server-support"></a>중재 서버 지원

SIP 트렁크을 구현 하려면 Lync Server 2013 클라이언트와 서비스 공급자 간의 통신 세션에 대 한 프록시 역할을 하는 중재 서버를 통해 연결을 라우팅해야 합니다. 중재 서버는 클라이언트와 서버의 미디어 트래픽을 디코딩하여 서비스 공급자로 보내기 전에 다시 인코딩합니다. SIP 트렁크은 방화벽 통과에 대 한 얼음 (실시간 오디오) 또는 ICE (대화형 연결 설정) 프로토콜 협상과 같은 사용 되는 일부 코덱을 지원 하지 않으므로 재 인코딩이 필요 합니다.

각 중재 서버에는 내부 네트워크 인터페이스와 외부 네트워크 인터페이스를 제공하는 두 개의 네트워크 어댑터가 있을 수 있습니다. 일반적으로 외부 인터페이스는 PSTN 게이트웨이 또는 IP-PBX에 연결 하는 데 사용 되기 때문에 게이트웨이 인터페이스 라고 합니다. SIP 트렁크를 구현하려면 외부 인터페이스를 서비스 공급자의 SBC(Session Border Controller)에 연결합니다.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>중앙 집중식 SIP 트렁크와 분산형 SIP 트렁크

*중앙 집중식* SIP 트렁크는 분기 사이트 트래픽을 비롯 한 모든 VoIP (Voice over Internet Protocol) 트래픽을 데이터 센터를 통해 라우팅합니다. 중앙 집중식 배포 모델은 비용 효율이 간단 하며 Lync Server 2013을 사용 하 여 SIP 트렁크을 구현 하는 기본 방법입니다.

엔터프라이즈 내에서의 사용 패턴에 따라 일부 사용자를 중앙 집중식 SIP 트렁크를 통해 라우팅하지 않을 수 있습니다. 다음 질문에 대한 대답을 통해 요구 사항을 분석할 수 있습니다.

  - 각 사이트의 규모는 어느 정도입니까? 사용자가 몇 명입니까?

  - 각 사이트에서 대부분의 전화 통화가 이루어지는 DID(Direct Inward Dialing) 번호는 몇 번입니까?

*분산형* SIP 트렁크는 하나 이상의 분기 사이트에 로컬 SIP 트렁크를 구현하는 배포 모델입니다. 이 경우 VoIP 트래픽은 데이터 센터를 통과하지 않고 분기 사이트에서 해당 서비스 공급자로 직접 라우팅됩니다.

분산형 SIP 트렁크는 다음과 같은 경우에만 필요합니다.

  - 분기 사이트에 지속 가능한 전화 연결(예: WAN이 다운된 경우)이 필요한 경우. 분기에 중복 및 장애 조치가 필요한 경우에는 서비스 공급자가 추가 비용을 청구하며 구성 시간이 더 오래 걸립니다. 따라서 이 요구 사항은 각 분기 사이트에 대해 분석해야 합니다. 일부 분기에는 중복 및 장애 조치 (failover)가 필요 하지만 다른 일부는 그렇지 않을 수 있습니다.

  - 분기 사이트와 데이터 센터가 서로 다른 국가/지역에 있는 경우. 호환성 및 규정 준수를 위해 국가/지역당 하나 이상의 SIP 트렁크가 필요합니다.

중앙 집중식 또는 분산 된 SIP 트렁크를 배포할지 여부를 결정 하면 비용 혜택 분석이 필요 합니다. 경우에 따라서는 필요 하지 않은 경우에도 분산 배포 모드를 선택 하는 것이 유용할 수 있습니다. 완전히 중앙화된 배포에서는 모든 분기 사이트 트래픽이 WAN 링크를 통해 라우팅됩니다. WAN 링크에 필요한 대역폭에 대한 비용을 지불하는 대신 분산형 SIP 트렁크를 사용할 수 있습니다.

<div>


> [!NOTE]  
> 분산 SIP 트렁크를 사용 하는 이유 및 방법에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-branch-site-sip-trunking.md">Branch SITE SIP 트렁크 In Lync Server 2013</A> 을 참조 하십시오.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>지원되는 SIP 트렁크 연결 유형

Lync Server 2013에서는 SIP 트렁크에 대해 다음 연결 유형을 지원 합니다.

  - MPLS(Multiprotocol Label Switching)는 하나의 네트워크 노드에서 다음 네트워크 노드로 데이터를 전달하는 개인 네트워크입니다. MPLS 네트워크의 대역폭은 다른 구독자와 공유되며, 각 데이터 패킷에는 구독자 간에 데이터를 구별하는 레이블이 할당됩니다. 이 연결 유형에는 VPN이 필요하지 않습니다. 그러나 VoIP 트래픽이 우선적으로 적용되지 않는 경우 과도한 IP 트래픽으로 인해 VoIP 작업이 방해를 받을 수 있다는 단점이 있습니다.

  - 다른 트래픽(예: 임대된 광 케이블 연결 또는 T1 회선)이 없는 개인 연결은 일반적으로 가장 안정적이고 안전한 연결 유형입니다. 이 연결 유형은 최고의 통화 전달 용량을 제공하지만 일반적으로 가장 비싸며, VPN이 필요하지 않습니다. 개인 연결은 통화량이 많거나 보안 및 사용 가능성 요구 사항이 엄격한 조직에 적합합니다.

  - 인터넷은 비용이 가장 저렴한 연결 유형이지만 통화 전달 용량이 가장 적기 때문에 안정성도 가장 낮습니다. ITSP (인터넷 전화 통신 서비스 공급자)는 TLS (전송 계층 보안) 및 SRTP (실시간 전송 프로토콜)를 지원 하 여 신호 및 미디어 트래픽을 암호화할 때이 SIP 트렁크 연결 형식을 보호 하는 데 도움이 됩니다. 인터넷을 통해 TLS 및 SRTP를 사용하도록 SIP 트렁크 연결을 구성할 수 없는 경우, VPN 터널을 사용하여 원격 보안 연결을 제공하는 것이 좋습니다. TLS 및 SRTP 사용에 대한 지원 여부를 해당 ITSP에 확인하십시오.

<div>

## <a name="selecting-a-connection-type"></a>연결 유형 선택

회사에 가장 적절한 SIP 트렁크 연결 유형은 요구 사항 및 예산에 따라 결정됩니다.

  - 중간 규모 또는 대기업의 경우 일반적으로 MPLS 네트워크에서 대부분의 값을 제공 합니다. MPLS 네트워크는 전문화된 개인 네트워크보다 저렴한 비용으로 필요한 대역폭을 제공할 수 있습니다.

  - 대기업에는 전용 광 케이블 또는 T1 연결이 필요할 수 있습니다.

  - 통화 량이 적은 소규모 기업 또는 분기 사이트의 경우 인터넷을 통한 SIP 트렁크이 가장 적합할 수 있습니다. 그러나 중간 규모 또는 대규모 사이트에는이 연결 유형을 사용 하지 않는 것이 좋습니다.

</div>

</div>

<div>

## <a name="codec-support"></a>코덱 지원

서비스 공급자 프록시는 다음 코덱을 지원해야 합니다.

  - G.711 a-law(주로 북미 이외의 다른 지역에서 사용)

  - G.711 µ-law(북미에서 사용)

</div>

</div>

<span> </span>

</div>

</div>

</div>

