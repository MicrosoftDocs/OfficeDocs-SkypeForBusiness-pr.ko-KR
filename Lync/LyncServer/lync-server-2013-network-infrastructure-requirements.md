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
ms.openlocfilehash: fcded907075b6587eb62ea8b6b76566c4f29ac87
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013의 네트워크 인프라 요구 사항

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

Lync Server 2013 토폴로지에서 각 서버의 네트워크 어댑터 카드는 최소 1 기가 비트/초 (Gbps)를 지원 해야 합니다. 일반적으로 낮은 대기 시간 및 높은 대역폭 LAN (local area network)을 사용 하 여 Lync Server 토폴로지 내에 모든 서버 역할을 연결 해야 합니다. LAN의 크기는 토폴로지 크기에 따라 달라 집니다.

  - 스탠더드 버전 토폴로지에서는 서버가 1Gbps 이더넷을 지 원하는 네트워크에 있어야 합니다.

  - 프런트 엔드 풀 토폴로지에서는 대부분의 서버가 최대 1Gbps, 특히 오디오/비디오 (A/V) 회의 및 응용 프로그램 공유를 지 원하는 네트워크에 있어야 합니다.

PSTN (공개 교환 전화 네트워크) 통합의 경우 T1/E1 회선 또는 SIP 트렁크를 사용 하 여 통합할 수 있습니다.

<div>

## <a name="audiovideo-network-requirements"></a>오디오/비디오 네트워크 요구 사항

Lync Server 배포의 오디오/비디오 (A/V)에 대 한 네트워크 요구 사항은 다음과 같습니다.

  - DNS 부하 분산을 사용 하 여 단일 Edge 서버 또는 Edge 풀을 배포 하는 경우에는 외부 방화벽을 NAT로 구성할 수 있습니다. 내부 방화벽을 NAT로 구성할 수 없습니다. 이러한 요구 사항에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013의 외부 A/V 방화벽 및 포트 요구 사항 결정](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) 을 참조 하세요.
    
    <div>
    

    > [!IMPORTANT]  
    > Edge 풀이 있고 하드웨어 부하 분산 장치를 사용 하는 경우 각 Edge 서버에서 공용 IP 주소를 사용 해야 하며 nat 디바이스 (예: NAT 또는 ou의 다른 인프라 장치) 또는 서버에 대 한 NAT를 사용할 수 없습니다. nd 또는 아웃 바운드 트래픽). 자세한 내용은 포트 요약-외부 사용자 액세스 설명서 계획의 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013에서 하드웨어 부하 분산 장치를 사용 하 여 통합 된 경계 크기를 조정</A> 합니다.

    
    </div>

  - 조직에서 QoS (서비스 품질) 인프라를 사용 하는 경우 미디어 하위 시스템은이 기존 인프라 내에서 작동 하도록 설계 되었습니다.

  - IPsec (인터넷 프로토콜 보안)을 사용 하는 경우 A/V 트래픽에 사용 되는 포트 범위를 통해 IPsec을 사용 하지 않도록 설정 하는 것이 좋습니다. 자세한 내용은 계획 설명서의 [Lync Server 2013의 IPsec 예외](lync-server-2013-ipsec-exceptions.md) 를 참조 하세요.

최적의 미디어 품질을 보장 하려면 다음을 수행 합니다.

  - 네트워크 링크는 최대 사용 기간 동안 오디오 스트림과 초당 65 킬로 비트/비디오 스트림의 500 Kbps (사용 가능한 경우)의 속도를 지원 하도록 준비 합니다. 양방향 오디오 또는 비디오 세션은 두 개의 스트림으로 구성 됩니다.

  - 이 수준 위의 트래픽에 대 한 예기치 않은 스파이크를 처리 하 고 시간 경과에 따른 사용량을 늘리면, Lync Server media 끝점은 다양 한 네트워크 조건에 적응할 수 있고, 계속 해 서 오디오 및 비디오에 대 한 처리량 (이전 단락 참조)의 3 배 부하를 지원 합니다. 허용 되는 품질을 유지 합니다. 그러나이 적응성이 프로비저닝된 네트워크를 지원 한다고 가정해 서는 안 됩니다. 프로비저닝된 네트워크에서 Lync Server media 끝점을 사용 하 여 다양 한 네트워크 상태 (예: 임시 대용량 패킷 손실)를 동적으로 처리할 수 있는 기능이 줄어들었습니다.

  - 구축 하는 데 비용이 매우 많이 들고 어려운 네트워크 링크의 경우 적은 소통량을 위해 프로비저닝을 고려해 야 할 수 있습니다. 이 시나리오에서, Lync Server 미디어 끝점의 elasticity는 트래픽 볼륨과 최고 트래픽 수준 간의 차이를 흡수 하 여 음성 음질을 줄이는 비용을 사용 합니다. 또한 사용량을 감소 시킬 수 있으며, 이렇게 하지 않으면 소통량의 갑작스런 피크를 흡수 하 게 됩니다.

  - 단기에 올바르게 프로 비전 할 수 없는 링크 (예: WAN 연결이 잘못 된 사이트)의 경우 특정 사용자에 대해 비디오를 사용 하지 않도록 설정 하는 것이 좋습니다.

  - 최고 부하에서 최대 150 밀리초 (밀리초)의 종단 간 지연 (대기 시간)을 보장 하도록 네트워크를 프로 비전 합니다. 대기 시간은 Lync Server 미디어 구성 요소가 줄일 수 없는 한 가지 네트워크 장애가 며 취약 한 점을 찾아 제거 하는 것이 중요 합니다.

  - 바이러스 백신 소프트웨어를 실행 하는 서버의 경우 예외 목록에서 Lync Server를 실행 하는 모든 서버를 포함 하 여 최적의 성능과 오디오 품질을 제공 합니다.

</div>

<div>

## <a name="conferencing-network-requirements"></a>회의 네트워크 요구 사항

IIS (인터넷 정보 서비스) 서버에서 회의 콘텐츠를 다운로드 하는 데 사용 되는 대역폭은 업로드 되는 콘텐츠의 크기에 따라 달라 집니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

