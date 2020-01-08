---
title: Lync Server 2013 SIP 트렁크 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2bdcf814a62bed4954c77be76bef32e1b6807ba
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979277"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a>Lync Server 2013의 SIP 트렁크 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

SIP 트렁크에서 엔터프라이즈 음성을 사용 하려는 경우 중재 서버를 배포 하 고 다른 인프라 및 구성 요소가 배포 모델에 적합 한 지원 요구 사항을 충족 하는지 확인 해야 합니다. SIP 트렁크을 구현할지 여부를 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 sip 트렁크 개요](lync-server-2013-overview-of-sip-trunking.md) 를 참조 하세요.

엔터프라이즈 전화 통신 인프라에 대 한 Microsoft 통합 커뮤니케이션 열기 상호 운용성 프로그램을 사용 하 여 적격 IP 전화 통신을 비롯 한 다양 한 PSTN (공개 교환 전화 네트워크) 게이트웨이, IP-Pbx 및 SIP 트렁크 서비스를 찾을 수 있습니다. 서비스 공급자. 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?LinkId=203309](http://go.microsoft.com/fwlink/p/?linkid=203309)Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램 웹 사이트를 참조 하세요.

<div>

## <a name="mediation-server-support"></a>중재 서버 지원

SIP 트렁크을 구현 하려면 Lync Server 2013 클라이언트와 서비스 공급자 간의 통신 세션에 대 한 프록시 역할을 하는 중재 서버를 통해 연결을 라우팅 해야 합니다. 중재 서버는 클라이언트 및 서버에서 미디어 트래픽을 디코딩하고 서비스 공급자에 게 보내기 전에 다시 인코딩합니다. SIP trunks는 실시간 오디오 (RTA) 또는 방화벽 통과를 위한 ICE (대화형 연결 설정) 프로토콜 협상과 같은 일부 코덱을 지원 하지 않기 때문에 재 인코딩이 필요 합니다.

각 중재 서버는 내부 및 외부 네트워크 인터페이스를 제공 하는 두 개의 네트워크 어댑터를 가질 수 있습니다. 외부 인터페이스는 일반적으로 PSTN 게이트웨이 또는 ip-pbx에 연결 하는 데 사용 되기 때문에 게이트웨이 인터페이스 라고 합니다. SIP 트렁크를 구현 하려면 외부 인터페이스를 서비스 공급자의 SBC (세션 경계 컨트롤러)에 연결 합니다.

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>중앙 집중화 및 분산 SIP 트렁크

*중앙 집중화* SIP 트렁크는 지점 사이트 소통량을 포함 하 여 데이터 센터를 통해 모든 Voice over 인터넷 프로토콜 (VoIP) 트래픽을 라우팅합니다. 중앙 집중화 된 배포 모델은 간단 하 고 비용 효율적 이며, 일반적으로 Lync Server 2013에서 SIP trunks을 구현 하는 데 주로 사용 됩니다.

엔터프라이즈의 사용 패턴에 따라 중앙 SIP 트렁크를 통해 모든 사용자를 라우팅 하는 것이 원하지 않을 수 있습니다. 필요 사항을 분석 하려면 다음 질문에 대답 하세요.

  - 각 사이트의 크기 명의 사용자 수

  - 각 사이트에서 바로 안쪽으로 거는 전화 접속 (a) 번호를 통해 가장 많은 전화를 받을 수 있나요?

*분산* SIP 트렁크 하나 이상의 지점 사이트에서 로컬 SIP 트렁크를 구현 하는 배포 모델입니다. 그런 다음 데이터 센터를 거치지 않고 지사 사이트에서 해당 서비스 공급자로 직접 VoIP 트래픽을 라우팅합니다.

분산 SIP 트렁크는 다음과 같은 경우에만 필요 합니다.

  - 지점 사이트에는 survivable 전화 연결이 필요 합니다 (예: WAN이 작동 하지 않는 경우). 지점에 중복성 및 장애 조치가 필요한 경우 서비스 공급자가 더 많은 비용을 청구 하 고 구성에 더 오랜 시간이 소요 됩니다. 각 지점 사이트에 대해이를 분석 해야 합니다. 일부 분기에는 중복 및 장애 조치가 필요할 수 있지만 다른 경우에는 그렇지 않습니다.

  - 분기 사이트와 데이터 센터는 서로 다른 국가/지역에 있습니다. 호환성과 법적 고 지는 국가/지역에 따라 적어도 하나 이상의 SIP 트렁크가 필요 합니다.

중앙 집중화 또는 분산 SIP 트렁크를 배포할지 결정 하려면 비용 이점 분석이 필요 합니다. 필요 하지 않은 경우에도 분산 배포 모드를 선택 하는 것이 유용할 수 있는 경우도 있습니다. 완전히 중앙 집중화 된 배포에서는 모든 지점 사이트 트래픽이 WAN 링크를 통해 라우팅됩니다. WAN 연결에 필요한 대역폭을 지불 하는 대신 분산 SIP 트렁크를 사용 하는 것이 좋습니다.

<div>


> [!NOTE]  
> 분산 SIP 트렁크를 사용 하는 이유와 방법에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013에서 분기 사이트 SIP 트렁크</A> 을 참조 하세요.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>지원 되는 SIP 트렁크 연결 유형

Lync Server 2013는 SIP 트렁크에 대해 다음 연결 유형을 지원 합니다.

  - MPLS (멀티 프로토콜 레이블 전환)는 하나의 네트워크 노드에서 다음으로 데이터를 전송 하 고 전달 하는 개인 네트워크입니다. MPLS 네트워크의 대역폭은 다른 구독자와 공유 되며 각 데이터 패킷에는 다른 구독자의 데이터를 구분 하는 레이블이 지정 됩니다. 이 연결 형식에는 VPN이 필요 하지 않습니다. 잠재적인 단점은 VoIP 트래픽이 우선 순위로 지정 되지 않는 이상 과도 한 IP 트래픽이 VoIP 작업을 방해할 수 있다는 것입니다.

  - 다른 트래픽이 없는 개인 연결은 일반적으로 가장 안정적이 고 안전한 연결 형식 (예: 임대한 광섬유 연결 또는 T1 회선)입니다. 이 연결 유형은 가장 높은 통화 운반 용량을 제공 하지만 일반적으로 가장 비쌉니다. VPN이 필요 하지 않습니다. 개인 연결은 높은 통화 볼륨이 나 엄격한 보안 및 가용성 요구 사항이 있는 조직에 적합 합니다.

  - 공개 인터넷은 가장 저렴 한 연결 형식으로, 최소한의 신뢰를가지고 있으며 통화 운반 용량이 가장 낮은 것입니다. 인터넷 전화 통신 서비스 공급자 (ITSP)는 신호 및 미디어 트래픽을 암호화 하는 TLS (전송 계층 보안) 및 보안 실시간 전송 프로토콜 (SRTP)을 지 원하는 경우이 SIP 트렁크 연결 형식을 보호 하는 데 도움이 될 수 있습니다. TLS 및 SRTP을 사용 하도록 인터넷을 통해 SIP 트렁크 연결을 구성할 수 없는 경우 VPN 터널을 사용 하 여 더 안전한 연결을 제공 하는 것이 좋습니다. SRTP를 사용 하 여 TLS에 대 한 지원이 제공 되는지 확인 하려면 ITSP에 문의 하세요.

<div>

## <a name="selecting-a-connection-type"></a>연결 형식 선택

기업의 가장 적합 한 SIP 트렁크 연결 유형은 사용자의 요구와 예산에 따라 달라 집니다.

  - 중간 규모 또는 대규모 엔터프라이즈의 경우 일반적으로 MPLS 네트워크에서 대부분의 값을 제공 합니다. 특별 한 사설 네트워크 보다 저렴 한 요금으로 필요한 대역폭을 제공할 수 있습니다.

  - 대기업에는 사설 광섬유 또는 T1 연결이 필요할 수 있습니다.

  - 낮은 규모의 중소기업 또는 저렴 한 통화를 사용 하는 지사 사이트의 경우 인터넷을 통해 SIP를 트렁크 하는 것이 가장 좋은 선택 일 수 있습니다. 그러나 중간 규모 또는 대규모 사이트에는이 연결 유형을 사용할 수 없습니다.

</div>

</div>

<div>

## <a name="codec-support"></a>코덱 지원

서비스 공급자 프록시는 다음 코덱을 지원 해야 합니다.

  - 711 a-법률 (주로 북미 지역 외에 사용)

  - 711 μ-사법 기관 (북미 지역에서 사용)

</div>

</div>

<span> </span>

</div>

</div>

</div>

