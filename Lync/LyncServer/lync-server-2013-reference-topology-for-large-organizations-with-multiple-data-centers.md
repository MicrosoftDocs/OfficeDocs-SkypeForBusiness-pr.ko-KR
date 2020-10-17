---
title: 여러 데이터 센터가 있는 대규모 조직에 대 한 Lync Server 2013 참조 토폴로지
description: 여러 데이터 센터가 있는 대규모 조직에 대 한 Lync Server 2013 참조 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for large organizations with multiple data centers
ms:assetid: 9a6aeae6-629b-49e6-9804-7ef369d7c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398797(v=OCS.15)
ms:contentKeyID: 48184887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfb88bd59e4bc27aefbdc94fdf53f094a09998f4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567604"
---
# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>여러 데이터 센터가 있는 대규모 조직의 Lync Server 2013에 대 한 참조 토폴로지

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-22_

여러 데이터 센터를 지원하는 대규모 조직용 참조 토폴로지는 둘 이상의 중앙 사이트가 있는 모든 규모의 조직에 적합합니다. 다음 다이어그램은 사용자 수가 50,000명(중앙 사이트 A에 20,000명, 중앙 사이트 B에 20,000명, 중앙 사이트 C와 분기 사이트에 총 10,000명)인 조직의 토폴로지입니다. 이 다이어그램에 표시된 유형의 토폴로지는 사용자 수에 관계없이 모든 규모의 조직에 적용될 수 있습니다.

프런트 엔드 서버 풀에서 제공 하는 고가용성 외에도이 토폴로지는 재해 복구 지원을 추가 합니다. 중앙 사이트 A와 B의 프런트 엔드 풀은 서로 쌍을 이룹니다. 이러한 풀 중 하나가 다운될 경우 관리자는 영향을 받지 않은 사이트의 쌍으로 구성된 풀로 영향을 받은 사용자에 대한 서비스를 이동할 수 있습니다.

이 토폴로지는 여러 다이어그램으로 표시되어 있는데, 먼저 개요를 보여 준 다음 중앙 사이트에 대한 상세 보기를 제공합니다.

**여러 데이터 센터가 있는 대규모 조직용 참조 토폴로지의 개요**

![여러 데이터 센터에 대 한 참조 토폴로지](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "여러 데이터 센터에 대 한 참조 토폴로지")

**대규모 조직용 참조 토폴로지: 중앙 사이트 A의 상세 보기**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**대규모 조직용 참조 토폴로지: 중앙 사이트 B의 상세 보기**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**대규모 조직용 참조 토폴로지: 중앙 사이트 C의 상세 보기**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **프런트 엔드 풀은 재해 복구를 사용 하기 위해 쌍을 이룹니다.**     재해 복구 지원을 제공 하기 위해 사이트 A와 사이트 B의 프런트 엔드 풀은 서로 쌍을 이룹니다. 한 사이트의 풀에 오류가 발생 하는 경우 관리자는 해당 사이트의 사용자를 다른 사이트의 연결 된 프런트 엔드 풀로 장애 조치 (failover) 하 여 사용자에 대 한 서비스 중단을 최소화할 수 있습니다. 이러한 두 프런트 엔드 풀에는 각각 6개의 서버가 있어 장애 조치(failover) 시 두 풀에 있는 40,000명의 사용자 모두를 충분히 지원할 수 있습니다. 자세한 내용은 [Lync Server 2013에서 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.

  - **백 엔드 서버가 미러링 됨**     기본 사용자 기능에 대 한 고가용성을 제공 하기 위해 조직은 각 프런트 엔드 풀에 대해 미러링된 백 엔드 서버 쌍을 배포 했습니다. 이는 선택적 토폴로지 이며 대신 단일 백 엔드 서버를 배포 하도록 선택할 수 있습니다.

  - **분기 사이트에서 Standard Edition server를 사용 합니다.**     이 조직은 사이트 C에 게 600 명의 직원만 있으므로 분기 사이트로 간주 합니다. 그러나 사용자에 게는 서로 다 수의 A/V 회의가 있습니다. Lync Server에서 분기 사이트로 배포한 경우 이러한 회의에 대 한 미디어는 프런트 엔드 서버를 배포 하는 중앙 사이트와의 WAN (wide area network)을 통해 실행 됩니다. 이러한 잠재적인 대역폭 부하를 방지 하기 위해 이러한 회의를 호스트 하는이 사이트에 Standard Edition 서버 쌍을 설치 했습니다. 또한 Standard Edition 서버는 설치 되어 있기 때문에 Lync Server는 정의에 따라 중앙 사이트로 간주 되며 토폴로지 작성기 및 계획 도구에서와 같은 방식으로 처리 됩니다.
    
    Standard Edition 서버 하나만 있으면 충분 하지만, 조직에서는 두 개를 배포 하 고 함께 사용 하 여 한 서버가 다운 될 경우 고가용성을 제공 합니다.
    
    사이트 C가 중앙 사이트로 간주되지만 여기에 에지 서버를 배포할 필요는 없습니다. 이 예에서는 사이트 C에서 사이트 A에 배포된 에지 서버를 사용합니다.

  - **모니터링 및 보관**     이 조직은 모니터링 및 보관을 모두 배포 했습니다. 모니터링 또는 보관을 배포할 때는 모든 프런트 엔드 서버에서 실행 됩니다. 이러한 기능에 대 한 데이터베이스는 백 엔드 데이터베이스와 배치 된 또는 별도의 서버에 위치할 수 있습니다. 이 조직은 중앙 사이트 B의 백 엔드 서버와는 별도의 서버에 이러한 데이터베이스를 배치 했습니다. 여기에 나와 있는 데이터베이스는 모든 사이트의 프런트 엔드 서버에서 모니터링 및 보관 데이터를 수신 합니다.

  - **분기 사이트 배포 옵션입니다.**     이 조직은 실제로 50 분기 사이트를 초과 하며,이 중 3 개는 자세한 다이어그램에 표시 됩니다. 분기 사이트 1 및 3에는 중앙 사이트에 대 한 복구 가능한 WAN 링크가 없기 때문에 중앙 사이트에 대 한 WAN 링크가 다운 될 경우 전화 서비스를 제공 하도록 Sba (survivable 분기 기기가 배포 되었습니다. 그러나 분기 사이트 2에는 탄력적 WAN 링크가 있으므로 공중 전화망 (PSTN) 게이트웨이만 있으면 됩니다. 여기에 배포 된 PSTN 게이트웨이는 미디어 바이패스를 지원 하므로 분기 사이트 B에서는 중재 서버가 필요 하지 않습니다. 분기 사이트에서 설치할 항목을 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 Enterprise Voice 복구 계획](lync-server-2013-planning-for-enterprise-voice-resiliency.md) 을 참조 하십시오.

  - **SIP 트렁크 및 중재 서버**     중앙 사이트 B에서는 중재 서버가 프런트 엔드 서버와 배치 된 되지 않습니다. 이는 SIP 트렁크를 사용하는 사이트에는 독립 실행형 중재 서버가 권장되기 때문입니다. 그 밖의 경우에는 대부분 중재 서버를 프런트 엔드 서버와 함께 배치하는 것이 좋습니다. 중재 서버 토폴로지에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 중재 서버에 대 한 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-mediation-server.md) 를 참조 하십시오.

  - **영구 채팅을 배포 합니다.**     이 조직은 영구 채팅을 사용 하도록 설정 하는 데 필요한 서버를 배포 했습니다. 풀의 사용자 수에 대 한 부하를 처리 하 고 고가용성을 제공 하기 위해 여러 영구 채팅 프런트 엔드 서버를 배포 했습니다. 또한 영구 채팅에 대 한 준수를 배포 했으며 영구 채팅 저장소 및 영구 채팅 준수 저장소를 별도의 서버에 배치 했습니다. 이러한 저장소는 배치 된 일 수 있으며 백 엔드 서버를 사용 하 여 배치 된 수도 있지만이 조직은이를 구분 하 여 더 나은 성능을 제공 하도록 선택 했습니다.

  - **DNS 부하 분산**     프런트 엔드 풀 및에 지 서버 풀 이를 통해에 지 서버의 내부 인터페이스에 대 한 하드웨어 부하 분산 장치를 사용할 필요가 없으며, 하드웨어 부하 분산 장치는 HTTP 트래픽에만 필요 하므로 다른 풀에 대 한 하드웨어 부하 분산 장치를 설정 하 고 유지 관리 하는 데 소요 되는 시간을 크게 줄일 수 있습니다. DNS 부하 분산에 대 한 자세한 내용은 계획 설명서에서 [Lync Server 2013의 dns 부하 분산](lync-server-2013-dns-load-balancing.md) 을 참조 하십시오.

  - **EXCHANGE UM 배포**    Lync Server는 Exchange UM (통합 메시징) 및 *호스팅된* exchange UM의 *온-프레미스 배포에서* 모두 작동 합니다. 중앙 사이트 A에는 Lync Server가 아닌 Microsoft Exchange Server를 실행 하는 Exchange UM (통합 메시징) 서버가 포함 되어 있습니다. Lync Server에 대 한 Exchange UM 기능은 프런트 엔드 풀에서 실행 됩니다.
    
    중앙 사이트 B에서는 호스팅된 Exchange를 사용하므로 Exchange UM 서버 기능도 호스팅됩니다.
    
    Exchange UM에 대 한 자세한 내용은 계획 설명서의 lync server 2013에서 Lync server 2013 및 [Hosted Exchange 통합 메시징 통합](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 의 [exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 을 참조 하세요.

  - **Office Web Apps 서버.**   웹 회의를 사용하는 모든 조직에서 Office Web Apps Server 또는 Office Web Apps Server 팜을 배포하는 것이 좋습니다. 단일 Office Web Apps Server 팜을 한 사이트에 배포하여 모든 사이트의 트래픽을 처리할 수도 있고 각 사이트에 배포할 수도 있습니다. Office Web Apps 서버를 사용하면 웹 회의에서 Powerpoint 슬라이드를 제시할 수 있습니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

  - **디렉터를 추가할 수 있습니다.**    이 조직이 서비스 거부 공격에 대 한 보안을 강화 하려는 경우 디렉터 풀도 배포할 수 있습니다. 디렉터는 홈 사용자 계정이 아닌 Lync Server의 별도의 선택적 서버 역할 이거나, 현재 상태 또는 회의 서비스를 제공 합니다. 또한에 지 서버가 내부 서버로 향하는 인바운드 SIP 트래픽을 라우팅하는 내부 다음 홉 서버 역할을 합니다. 디렉터는 인바운드 요청을 미리 인증 하 고 사용자의 홈 풀이나 서버로 리디렉션합니다. 디렉터에서의 사전 인증을 통해 배포에 알려지지 않은 사용자 계정에서 오는 요청을 끊을 수 있습니다. 디렉터는 DoS (서비스 거부) 공격과 같은 악의적인 트래픽에 대 한 프런트 엔드 서버를 제거할 수 있도록 지원 합니다. 이러한 공격에 잘못 된 외부 트래픽이 발생 하는 네트워크의 경우에는 디렉터에서 트래픽이 종료 됩니다.

  - **System Center Operations Manager가 배포 되었습니다.**    최종 사용자에 대 한 서비스 가용성을 보장 하려면 Lync Server 배포의 상태를 모니터링 하는 것이 좋습니다. Microsoft에서 무료로 다운로드할 수 있는 Lync 용 System Center Operations Manager 관리 팩을 사용 하 여 Lync를 모니터링할 수 있습니다. Lync 관리 팩을 사용하면 문제가 발생할 때 실시간 알림을 받아 대처하고, 가상 트랜잭션을 실행하여 전체 Lync 기능을 테스트하고, 서비스 가용성에 대한 보고서를 받는 등 다양한 이점을 얻을 수 있습니다. 이를 통해 최종 사용자가 문제를 경험하기 전에 배포에 대한 문제를 미리 해결할 수 있습니다.
    
    이 조직은 각 중앙 사이트에 System Center Operations Manager 서버를 배포 했습니다.

</div>

<span> </span>

</div>

</div>

</div>

