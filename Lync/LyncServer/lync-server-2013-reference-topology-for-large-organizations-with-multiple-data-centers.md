---
title: Lync Server 2013 데이터 센터가 여러 개인 대규모 조직에 대한 참조 토폴로지
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
ms.openlocfilehash: 56d9edde5ab097f3244919d6dd2c572b4a1dc112
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-large-organizations-with-multiple-data-centers"></a>데이터 센터가 여러 개인 대규모 조직에서 Lync Server 2013에 대한 참조 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-22_

여러 데이터 센터가 지원 되는 대규모 조직의 경우에는 두 개 이상의 중앙 사이트를 사용 하는 모든 조직의 규모에 대 한 참조 토폴로지가 있습니다. 다음 다이어그램의 정확한 토폴로지는 중앙 사이트 A 2만, 중앙 사이트 B의 2만 사용자, 중앙 사이트 C 및 지사 사이트의 총 1만를 사용 하 여 5만 사용자의 조직에 대 한 것입니다. 이 다이어그램에 표시 되는 토폴로지 유형은 사용자 수에 관계 없이 조직을 수용할 수 있습니다.

프런트 엔드 서버의 풀에서 제공 하는 고가용성 외에도이 토폴로지가 재해 복구 지원을 추가 합니다. 중앙 사이트 A와 B의 프런트 엔드 풀은 서로 쌍을 이룹니다. 이러한 풀 중 하나가 다운 되 면 관리자가 영향을 받는 사용자에 대 한 서비스를 영향을 받지 않은 사이트의 페어링 된 풀로 전환할 수 있습니다.

이 토폴로지는 여러 다이어그램으로 표시 되며 먼저 개요와 중앙 사이트의 자세히 보기를 사용 합니다.

**여러 데이터 센터가 있는 대규모 조직의 참조 토폴로지 개요**

![여러 데이터 센터용 참조 토폴로지](images/Gg398797.471e1ce9-be11-44b9-9f4a-59e0551b7b30(OCS.15).jpg "여러 데이터 센터용 참조 토폴로지")

**대규모 조직의 참조 토폴로지: 중앙 사이트 A의 자세히 보기**

![dab33f19-e77b-42da-9047-858fb9851264](images/Gg398797.dab33f19-e77b-42da-9047-858fb9851264(OCS.15).jpg "dab33f19-e77b-42da-9047-858fb9851264")

**대규모 조직의 참조 토폴로지: 중앙 사이트 B의 자세히 보기**

![5ccaf1d4-bd53-4cb7-96fe-723147334e7f](images/Gg398797.5ccaf1d4-bd53-4cb7-96fe-723147334e7f(OCS.15).jpg "5ccaf1d4-bd53-4cb7-96fe-723147334e7f")

**대규모 조직의 참조 토폴로지: 중앙 사이트 C의 자세히 보기**

![7238ca40-340c-491f-b497-ddc2665dadb6](images/Gg398797.7238ca40-340c-491f-b497-ddc2665dadb6(OCS.15).jpg "7238ca40-340c-491f-b497-ddc2665dadb6")

  - **프론트 엔드 풀은 재해 복구를 사용 하는 데 쌍을 이룹니다.**    사이트 A와 사이트 B의 프런트 엔드 풀은 재해 복구 지원을 제공 하기 위해 서로 쌍을 이룹니다. 한 사이트의 풀에 장애가 발생 하는 경우 관리자는 해당 사이트의 사용자를 다른 사이트의 페어링 된 프런트 엔드 풀로 장애 조치할 수 있으며, 사용자에 게 최소 서비스 중단이 있습니다. 이러한 두 프런트 엔드 풀 각각에는 6 대의 서버가 있으며,이는 장애 조치 시 두 풀의 모든 4만 사용자에 대해 충분 합니다. 자세한 내용은 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)을 참조 하세요.

  - **백 엔드 서버**   는 기본 사용자 기능에 대 한 높은 가용성을 제공 하기 위해 미러링 되며, 조직은 각 프런트 엔드 풀에 대 한 미러 쌍의 백 엔드 서버를 배포 했습니다. 이는 선택적 토폴로지가 며 대신 단일 백 엔드 서버를 배포 하도록 선택할 수 있습니다.

  - **지점 사이트에서 Standard Edition server를 사용 합니다.**    이 조직은 600 직원만 있기 때문에 사이트 C를 지점 사이트로 간주 합니다. 그러나 사용자에 게는 서로 다 수의 A/V 회의가 있습니다. Lync Server를 지점 사이트로 배포 하는 경우 이러한 회의에 대 한 미디어는 프런트 엔드 서버가 배포 된 중앙 사이트 간에 WAN (광역 네트워크)을 통해 실행 됩니다. 이러한 잠재적인 대역폭 로드를 방지 하기 위해이 사이트에서 이러한 회의를 호스트 하는 표준 버전 서버 쌍을 설치 했습니다. 또한 Standard Edition 서버는이 위치에 설치 되어 있기 때문에 Lync Server는 중앙 사이트를 정의 하는 것으로 간주 하 고 토폴로지 작성기 및 계획 도구 에서처럼 처리 됩니다.
    
    단 하나의 표준 버전 서버를 사용 하는 것 만으로도 충분 하지만, 조직은 두 개를 배포 하 고 연결 하 여 한 서버가 다운 되는 경우 고가용성을 제공 합니다.
    
    사이트 C는 중앙 사이트로 간주 되지만 여기에 Edge 서버를 배포할 필요는 없습니다. 이 예제에서 사이트 C는 사이트 A에 배포 된에 지 서버를 사용 합니다.

  - **** 이 조직의 모니터링과 아카이빙은 모니터링과 아카이빙 모두 배포 되었습니다.    모니터링 또는 보관을 배포 하면 모든 프런트 엔드 서버에서 실행 됩니다. 이러한 기능에 대 한 데이터베이스는 백 엔드 데이터베이스를 사용 하 여 collocated 하거나 별도의 서버에 배치할 수 있습니다. 이 조직은 중앙 사이트 B에서 백 엔드 서버와 별도의 서버에 이러한 데이터베이스를 찾았습니다. 여기에 나와 있는 데이터베이스는 모든 사이트의 프런트 엔드 서버에서 데이터 모니터링 및 보관을 받습니다.

  - **지점 사이트 배포 옵션**    이 조직에는 실제로 50 분기 사이트가 있지만, 그 중 세 개는 세부 다이어그램에 표시 됩니다. 지점 사이트 1 및 3에는 중앙 사이트에 대 한 탄성 WAN 링크가 없기 때문에 중앙 사이트에 대 한 WAN 링크가 다운 되는 경우 전화 서비스를 제공 하도록 Survivable Branch 기기가 배포 되었습니다. 그러나 지점 사이트 2에는 회복성 있는 WAN 링크가 있으므로, PSTN (공개 통신 네트워크) 게이트웨이만 있으면 됩니다. PSTN 게이트웨이가 미디어 바이패스를 지원 하기 때문에 지점 사이트 B에는 중재 서버가 필요 하지 않습니다. 지점 사이트에서 설치할 항목을 결정 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 엔터프라이즈 음성 복원 계획](lync-server-2013-planning-for-enterprise-voice-resiliency.md) 을 참조 하세요.

  - **SIP 트렁크 및 중재 서버.**    중앙 사이트 B에서 중재 서버는 프런트 엔드 서버와 collocated 되지 않는다는 점에 유의 하세요. 이는 SIP 트렁크를 사용 하는 사이트에 대 한 독립 실행형 중재 서버가 권장 되기 때문입니다. 대부분의 다른 경우에는 프런트 엔드 서버를 사용 하는 중재 서버를 collocate 하는 것이 좋습니다. 중재 서버 토폴로지에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 중재 서버용 구성 요소 및 토폴로지](lync-server-2013-components-and-topologies-for-mediation-server.md) 를 참조 하세요.

  - **영구 채팅이 배포 되었습니다.**    이 조직은 영구 채팅을 사용 하도록 설정 하는 데 필요한 서버를 배포 했습니다. 풀의 사용자 수에 대 한 로드를 처리 하 고 고가용성을 제공 하기 위해 여러 영구 채팅 프런트 엔드 서버를 배포 했습니다. 또한 영구 채팅에 대 한 준수를 배포 하 고 별도의 서버에 영구 채팅 저장소와 영구 채팅 준수 저장소를 배치 했습니다. 이러한 저장소는 collocated 수 있으며 백 엔드 서버와도 collocated 수 있지만,이 조직은이를 구분 하 여 더 나은 성능을 제공 하도록 선택 했습니다.

  - **DNS 로드 균형 조정.**    프런트 엔드 풀 및 Edge 서버 풀. 이렇게 하면 Edge 서버의 내부 인터페이스에 대 한 하드웨어 부하 분산 장치가 필요 하지 않으며 하드웨어 로드 시 다른 풀의 하드웨어 로드 균형 조정기 설정 및 유지 관리에 소요 되는 시간을 크게 줄일 수 있습니다. 분산 장치는 HTTP 트래픽에만 필요 합니다. DNS 부하 분산에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 dns 부하 분산](lync-server-2013-dns-load-balancing.md) 을 참조 하세요.

  - **Exchange UM 배포**   Lync Server는 exchange Um (통합 메시징) 및 *호스트* 된 exchange UM의 *온-프레미스* 배포 모두에서 작동 합니다. 중앙 사이트 A에는 Lync Server가 아닌 Microsoft Exchange Server를 실행 하는 UM (Exchange 통합 메시징) 서버가 포함 됩니다. Lync Server의 Exchange UM 기능은 프런트 엔드 풀에서 실행 됩니다.
    
    중앙 사이트 B는 호스트 된 Exchange를 사용 하므로 Exchange UM 서버 기능 또한 호스팅됩니다.
    
    Exchange UM에 대 한 자세한 내용은 계획 설명서의 lync server 2013에서 lync Server 2013 및 [호스트 된 Exchange 통합 메시징 통합](lync-server-2013-hosted-exchange-unified-messaging-integration.md) 의 [exchange 통합 메시징 통합 계획](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) 을 참조 하세요.

  - **Office Web Apps 서버.**   웹 회의를 사용 하는 모든 조직에서 Office Web Apps 서버 또는 Office Web Apps 서버 팜을 배포 하는 것이 좋습니다. 하나의 사이트에서 모든 사이트의 트래픽을 처리 하거나 각 사이트에 배포 하는 단일 Office Web Apps 서버 팜을 배포할 수 있습니다. Office Web Apps Server를 통해 Powerpoint 슬라이드를 웹 회의에 표시할 수 있습니다. 자세한 내용은 [Office Web Apps 서버 및 Lync server 2013의 통합 구성을](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)참조 하세요.

  - **감독을 추가할 수 있습니다.**   이 조직이 서비스 거부 공격에 대 한 보안을 강화 하고자 하는 경우에도 디렉터 풀을 배포할 수 있습니다. 디렉터는 사용자 계정이 가정용이 아니거나 현재 상태 또는 회의 서비스를 제공 하는 Lync Server의 개별 선택적 서버 역할입니다. 이 서비스는 Edge 서버가 내부 서버를 대상으로 하는 인바운드 SIP 트래픽을 라우팅하는 내부 다음 홉 서버로 작동 합니다. 디렉터는 인바운드 요청을 사전 인증 하 고 사용자의 홈 풀이나 서버로 리디렉션합니다. 디렉터에서 사전 인증을 통해 배포에 알려지지 않은 사용자 계정의 요청을 삭제할 수 있습니다. 디렉터는 DoS (서비스 거부) 공격과 같은 악의적인 트래픽에 대 한 프런트 엔드 서버를 방지 하는 데 도움이 됩니다. 이러한 공격에서 유효 하지 않은 외부 트래픽으로 네트워크에 장애가 발생 하는 경우에는 해당 트래픽이 디렉터에서 끝납니다.

  - **System Center Operations Manager가 배포 되었습니다.**   최종 사용자에 대 한 서비스 가용성을 보장 하기 위해 Lync Server 배포의 상태를 모니터링 하는 것이 좋습니다. Microsoft에서 무료로 다운로드할 수 있는 Lync 용 System Center Operations Manager 관리 팩을 사용 하 여 Lync를 모니터링할 수 있습니다. Lync 관리 팩을 사용 하면 문제가 발생할 경우 실시간 알림을 받을 수 있으며, 종합 트랜잭션을 실행 하 여 엔드 투 엔드 Lync 기능을 테스트 하 고, 서비스 가용성을 위한 보고서를 얻을 수도 있습니다. 이렇게 하면 최종 사용자가 작업을 수행 하기 전에 배포 문제에 대 한 사전 대처를 경험할 수 있습니다.
    
    이 조직은 각 중앙 사이트에 System Center Operations Manager 서버를 배포 했습니다.

</div>

<span> </span>

</div>

</div>

</div>

