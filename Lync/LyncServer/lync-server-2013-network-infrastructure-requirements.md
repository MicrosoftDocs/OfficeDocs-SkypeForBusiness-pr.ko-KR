---
title: Lync Server 2013 네트워크 인프라 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network infrastructure requirements
ms:assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425841(v=OCS.15)
ms:contentKeyID: 48183804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3571dba317998af4fe19f7d2dfd1677d3691f278
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217114"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013의 네트워크 인프라 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-18_

Lync Server 2013 토폴로지에서 각 서버의 네트워크 어댑터 카드는 초당 1 기가 비트 (Gbps)를 지원 해야 합니다. 일반적으로는 낮은 대기 시간 및 높은 대역폭 LAN (local area network)을 사용 하 여 Lync Server 토폴로지 내의 모든 서버 역할을 연결 해야 합니다. LAN의 크기는 토폴로지 크기에 따라 달라집니다.

  - Standard Edition 토폴로지에서 서버는 1Gbps 이더넷 또는 동급를 지 원하는 네트워크에 있어야 합니다.

  - 프런트 엔드 풀 토폴로지에서는 특히, A/V (오디오/비디오) 회의 및 응용 프로그램 공유를 지 원하는 경우 대부분의 서버가 1Gbps를 지 원하는 네트워크에 있어야 합니다.

공중 전화망(PSTN) 통합의 경우에는 T1/E1 회선 또는 SIP 트렁크를 사용하여 통합할 수 있습니다.

<div>

## <a name="audiovideo-network-requirements"></a>오디오/비디오 네트워크 요구 사항

Lync Server 배포에서 A/V (오디오/비디오)에 대 한 네트워크 요구 사항은 다음과 같습니다.

  - DNS 부하 분산을 사용 하 여 단일에 지 서버 또는에 지 풀을 배포 하는 경우에는 외부 방화벽을 NAT로 구성할 수 있습니다. 내부 방화벽은 NAT로 구성할 수 없습니다. 이러한 요구 사항에 대 한 자세한 내용은 계획 설명서에서 [External A/V 방화벽 및 Lync Server 2013에 대 한 포트 요구 사항 결정](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) 을 참조 하십시오.
    
    <div>
    

    > [!IMPORTANT]  
    > 에 지 풀이 있고 하드웨어 부하 분산 장치를 사용 하는 경우에는 각에 지 서버에 대해 공용 IP 주소를 사용 해야 하며 nat 장치 (예: 방화벽 또는 NAT inbou에서 사용 되는 다른 인프라 장치)의 풀 또는 서버에 대해 NAT를 사용할 수 없습니다. nd 또는 아웃 바운드 트래픽) 자세한 내용은 외부 사용자 액세스 설명서 계획에서 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">포트 요약-확장 된 통합에 지 Lync Server 2013의 하드웨어 부하 분산 장치</A> 를 참조 하십시오.

    
    </div>

  - 조직에서 QoS(서비스 품질) 인프라를 사용하는 경우 미디어 하위 시스템은 이러한 기존 인프라 내에서 작동하도록 설계됩니다.

  - IPsec(인터넷 프로토콜 보안)를 사용하는 경우 A/V 트래픽에 사용되는 포트 범위에서 IPSec를 사용하지 않도록 설정하는 것이 좋습니다. 자세한 내용은 계획 설명서에서 [Lync Server 2013의 IPsec 예외](lync-server-2013-ipsec-exceptions.md) 를 참조 하십시오.

최적의 미디어 품질을 유지하려면 다음을 수행합니다.

  - 최대 사용 기간 동안 오디오 스트림당 65Kbps 및 비디오 스트림(사용 가능한 경우)당 500Kbps의 처리량을 지원하도록 네트워크 링크를 프로비전합니다. 양방향 오디오 또는 비디오 세션은 두 개의 스트림으로 이루어집니다.

  - 이 수준 보다 높은 트래픽에 대 한 예기치 않은 스파이크를 처리 하 고 시간 경과에 따른 사용량을 증대 시키려면 Lync Server media endpoints는 다양 한 네트워크 조건에 적응할 수 있고 3 배의 처리량 (이전 단락 참조)의 부하를 지원 하 여 오디오 및 비디오를 계속 사용 적절 한 품질을 유지 합니다. 하지만 이러한 적응 가능성 때문에 네트워크를 충분하지 않게 프로비전해도 되는 것으로 간주하면 안 됩니다. 프로 비전 된 네트워크에서 Lync Server 미디어 끝점이 동적으로 다양 한 네트워크 조건 (예: 일시적인 높은 패킷 손실)을 처리 하는 기능을 줄였습니다.

  - 프로비전이 상당히 어렵고 비용이 많이 드는 네트워크 링크의 경우 낮은 트래픽 볼륨에 대해 프로비전하는 것을 고려할 수 있습니다. 이 시나리오에서는 Lync Server 미디어 끝점의 회복 력가 트래픽 볼륨과 최고 트래픽 수준 간의 차이를 흡수 하 여 음성 품질이 약간 저하 되는 것을 허용 합니다. 이 경우, 트래픽의 급격한 증가를 수용하는 데 사용할 수 있는 헤드 공간도 감소합니다.

  - 매우 불량한 WAN 링크가 포함된 사이트 등과 같이 단기간에 올바로 프로비전할 수 없는 링크의 경우 특정 사용자에 대해 비디오를 비활성화하는 것을 고려합니다.

  - 최대 종단 간 지연(대기 시간)이 최대 부하에서 150ms가 되도록 네트워크를 프로비전합니다. 시간 지연은 Lync Server 미디어 구성 요소에서 줄일 수 없는 단일 네트워크 장애가 며 취약 한 지점을 찾아서 제거 하는 것이 중요 합니다.

  - 바이러스 백신 소프트웨어를 실행 하는 서버의 경우 예외 목록에 Lync Server를 실행 하는 모든 서버를 포함 하 여 최적의 성능 및 오디오 품질을 제공 합니다.

</div>

<div>

## <a name="conferencing-network-requirements"></a>회의 네트워크 요구 사항

IIS (인터넷 정보 서비스) 서버에서 전화 회의 콘텐츠를 다운로드 하는 데 사용 되는 대역폭은 업로드 되는 콘텐츠의 크기에 따라 달라 집니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

