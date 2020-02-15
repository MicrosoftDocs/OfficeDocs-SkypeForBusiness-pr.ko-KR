---
title: 'Lync Server 2013: SIP 트렁크 구현 방법은 무엇입니까?'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 062eb44fb79d6ecfa33f449e62341003bbed571b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a>Lync Server 2013에서 SIP 트렁크를 구현 하려면 어떻게 하나요?

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-18_

SIP 트렁크을 구현 하려면 필요에 따라 Lync Server 2013 클라이언트와 서비스 공급자 및 코드 미디어 간의 통신 세션에 대 한 프록시 역할을 하는 중재 서버를 통해 연결을 라우팅해야 합니다.

각 중재 서버에는 내부 네트워크 인터페이스와 외부 네트워크 인터페이스가 있습니다. 내부 인터페이스가 프런트 엔드 서버에 연결 됩니다. 외부 인터페이스는 전통적으로 중재 서버를 PSTN (공중 전화망) 게이트웨이 또는 IP-PBX에 연결 하는 데 사용 되므로 일반적으로 게이트웨이 인터페이스 라고 합니다. SIP 트렁크를 구현 하려면 중재 서버의 외부 인터페이스를 ITSP의 외부에 지 구성 요소에 연결 합니다.

<div>


> [!NOTE]  
> ITSP의 외부에 지 구성 요소는 SBC (세션 경계 컨트롤러), 라우터 또는 gateway 일 수 있습니다.



</div>

중재 서버에 대 한 자세한 내용은 [Lync server 2013의 중재 서버 구성 요소](lync-server-2013-mediation-server-component.md)를 참조 하십시오.

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a>중앙 집중식 SIP 트렁크와 분산형 SIP 트렁크

*중앙 집중식* SIP 트렁크는 분기 사이트 트래픽을 비롯 한 모든 VoIP (Voice over Internet Protocol) 트래픽을 중앙 사이트를 통해 라우팅합니다. 중앙 집중식 배포 모델은 비용 효율이 간단 하며 Lync Server 2013을 사용 하 여 SIP 트렁크을 구현 하는 경우에는 일반적으로 권장 되는 방법입니다.

*분산* 된 SIP 트렁크는 하나 이상의 분기 사이트에서 로컬 SIP 트렁크를 구현 하는 배포 모델입니다. 그러면 VoIP 트래픽은 중앙 사이트를 거치지 않고 분기 사이트에서 서비스 공급자로 직접 라우팅됩니다.

분산형 SIP 트렁크는 다음과 같은 경우에만 필요합니다.

  - 분기 사이트에 지속 가능한 전화 연결(예: WAN이 다운된 경우)이 필요한 경우. 각 분기 사이트에 대해이 요구 사항을 분석 해야 합니다. 일부 분기에는 중복 및 장애 조치 (failover)가 필요할 수 있지만 그렇지 않을 수도 있습니다.

  - 두 중앙 사이트 사이에 복원성이 필요 합니다. 각 중앙 사이트에서 SIP 트렁크가 종료 되는지 확인 해야 합니다. 예를 들어 더블린 및 Tukwila 중앙 사이트가 있고 둘 다 사이트의 SIP 트렁크를 하나만 사용 하는 경우 트렁크가 다운 되 면 다른 사이트의 사용자가 PSTN 전화를 걸 수 없습니다.

  - 분기 사이트와 중앙 사이트가 서로 다른 국가/지역에 있습니다. 호환성 및 규정 준수를 위해 국가/지역당 하나 이상의 SIP 트렁크가 필요합니다. 예를 들어 유럽 연합에서 통신은 중앙 지점에서 로컬로 종료 하지 않고는 국가/지역을 나갈 수 없습니다.

사이트의 지리적 위치 및 회사 내에서 예상 되는 트래픽 크기에 따라 모든 사용자를 중앙 SIP 트렁크를 통해 라우트 하지 않으려는 경우 또는 분기 사이트에서 SIP 트렁크를 통해 일부 사용자의 경로를 지정할 수도 있습니다. 다음 질문에 대한 대답을 통해 요구 사항을 분석할 수 있습니다.

  - 각 사이트의 크기 (Enterprise Voice를 사용할 수 있는 사용자 수)

  - 각 사이트에서 대부분의 전화 통화를 받게 되는 직접 안쪽 전화 걸기 (온) 번호는 무엇입니까?

중앙 집중식 또는 분산 SIP 트렁크 배포 여부에 대 한 결정에는 비용 이점 분석이 필요 합니다. 경우에 따라 분산형 배포 모델이 필요하지 않은 경우에도 이 모델이 훨씬 이익인 경우가 있을 수 있습니다. 완전히 중앙화된 배포에서는 모든 분기 사이트 트래픽이 WAN 링크를 통해 라우팅됩니다. WAN 링크에 필요한 대역폭에 대한 비용을 지불하는 대신 분산형 SIP 트렁크를 사용할 수 있습니다. 예를 들어, 중앙 사이트에 대 한 페더레이션이 있는 분기 사이트에 Standard Edition server를 배포 하거나 소규모 게이트웨이를 사용 하 여 Sba (survivable 분기 어플라이언스 또는 Sba (survivable 분기 서버를 배포할 수 있습니다.

<div>


> [!NOTE]  
> 분산 SIP 트렁크에 대 한 자세한 내용은 <A href="lync-server-2013-branch-site-sip-trunking.md">Branch SITE SIP 트렁크 In Lync Server 2013</A>을 참조 하십시오.



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a>지원되는 SIP 트렁크 연결 유형

Lync Server에서는 SIP 트렁크에 대해 다음 연결 유형을 지원 합니다.

  - MPLS(Multiprotocol Label Switching)는 하나의 네트워크 노드에서 다음 네트워크 노드로 데이터를 전달하는 개인 네트워크입니다. MPLS 네트워크의 대역폭은 다른 구독자와 공유되며, 각 데이터 패킷에는 구독자 간에 데이터를 구별하는 레이블이 할당됩니다. 이 연결 유형에는 VPN (가상 사설망)이 필요 하지 않습니다. 그러나 VoIP 트래픽이 우선적으로 적용되지 않는 경우 과도한 IP 트래픽으로 인해 VoIP 작업이 방해를 받을 수 있다는 단점이 있습니다.

  - 임대 파이버-광 연결 또는 T1 회선과 같은 다른 트래픽이 없는 개인 연결은 대개 가장 안정적이 고 안전한 연결 유형입니다. 이 연결 유형은 통화 운반 용량을 가장 많이 제공 하지만 일반적으로 비용이 가장 높습니다. VPN은 필요 하지 않습니다. 개인 연결은 통화 볼륨이 높고 보안 및 가용성 요구 사항이 엄격한 조직에 적합 합니다.

  - 인터넷은 비용이 저렴 한 연결 형식 이지만 안정성이 가장 낮은 것도 좋습니다. 인터넷 연결은 VPN을 필요로 하는 유일한 Lync Server SIP 트렁크 연결 유형입니다.

<div>

## <a name="selecting-a-connection-type"></a>연결 유형 선택

회사에 가장 적절한 SIP 트렁크 연결 유형은 요구 사항 및 예산에 따라 결정됩니다.

  - 중간 규모 또는 대기업의 경우 일반적으로 MPLS 네트워크가 가장 큰 값을 제공 합니다. MPLS 네트워크는 전문화된 개인 네트워크보다 저렴한 비용으로 필요한 대역폭을 제공할 수 있습니다.

  - 대기업에는 전용 섬유-파이버, T1, T3 또는 더 높은 연결 (유럽 연합의 경우 E1, E3 이상)이 필요할 수 있습니다.

  - 통화 량이 적은 소규모 기업 또는 분기 사이트의 경우 인터넷을 통한 SIP 트렁크이 가장 적합할 수 있습니다. 중간 규모 또는 대규모 사이트에는이 연결 유형을 사용 하지 않는 것이 좋습니다.

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a>대역폭 요구 사항

구현 해야 하는 대역폭의 양은 통화 용량 (지원 해야 하는 동시 호출 수)에 따라 달라 집니다. 지불한 최대 용량을 충분히 활용할 수 있도록 대역폭 가용성을 고려해 야 합니다. 다음 수식을 사용 하 여 SIP 트렁크 최고 대역폭 요구 사항을 계산 합니다.

SIP 트렁크 최대 대역폭 = 최대 동시 통화 x (64 kbps + 헤더 크기)

<div>


> [!NOTE]  
> 헤더 크기는 최대 20 바이트입니다.



</div>

</div>

<div>

## <a name="codec-support"></a>코덱 지원

Lync Server 2013는 다음 코덱과 지원 합니다.

  - G.711 a-law(주로 북미 이외의 다른 지역에서 사용)

  - G.711 µ-law(북미에서 사용)

</div>

<div>

## <a name="internet-telephony-service-provider"></a>인터넷 전화 통신 서비스 공급자

SIP 트렁크 연결의 서비스 공급자 쪽을 구현하는 방법은 ITSP에 따라 다릅니다. 배포 정보에 대해서는 서비스 공급자에 문의하십시오. 인증 된 SIP 트렁크 서비스 공급자 목록은 [Microsoft 통합 커뮤니케이션 오픈 상호 운용성 프로그램 웹 사이트](http://go.microsoft.com/fwlink/?linkid=287029)를 참조 하세요.

Microsoft 인증 SIP 트렁크 공급자에 대한 자세한 내용은 Microsoft 담당자에게 문의하십시오.

<div>


> [!IMPORTANT]  
> Microsoft 인증 서비스 공급자를 사용하여 ITSP가 SIP 트렁크를 트래버스하는 모든 기능(예: 세션 설정 및 관리와 모든 확장된 VoIP 서비스 지원)을 지원하도록 해야 합니다. Microsoft 기술 지원은 인증 되지 않은 공급자를 사용 하는 구성으로 확장 되지 않습니다. 현재 SIP 트렁크에 대해 인증 되지 않은 인터넷 서비스 공급자를 사용 하는 경우 해당 공급자를 ISP로 계속 사용 하도록 선택 하 고 SIP 트렁크에 대해 Microsoft에서 인증 한 공급자를 사용할 수 있습니다.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

