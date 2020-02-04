---
title: Lync Server 2013 지원되는 토폴로지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported topologies
ms:assetid: 3475d430-0394-491b-a09b-ba85bd62be70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425833(v=OCS.15)
ms:contentKeyID: 48183832
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f200cde348d1fbdc931daa25abef28aec804a1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Lync Server 2013의 지원되는 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-01-14_

Lync Server 2013는 조직에서 온-프레미스 배포를 지원 하 고 Lync Online 배포를 사용 하 여 하이브리드 배포 라고 하는 on-premises deployment를 통합할 수 있습니다. 하이브리드 배포에서 일부 사용자는 온-프레미스이 고 일부 사용자는 온라인으로 설정 됩니다.

온-프레미스 배포의 경우 Lync Server 2013는 고가용성 및 위치 요구 사항에 맞게 확장할 수 있는 하나 이상의 사이트 배포를 지원 합니다. 이러한 사이트와 해당 구성 요소를 조직에 대 한 액세스 및 탄력성 요구 사항에 맞게 구성할 수 있습니다.

Lync Server 2013 온-프레미스 배포는 다음으로 구성 됩니다.

  - 배포에는 하나 이상의 중앙 사이트 (데이터 센터가 라고도 함)가 포함 되어야 합니다. 각 중앙 사이트에는 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버가 하나 이상 포함 되어 있어야 합니다. 이러한 작업은 다음과 같이 구성 됩니다.
    
      - 하나 이상의 프런트 엔드 서버로 구성 되는 Enterprise Edition 프런트 엔드 풀 (일반적으로 최소 두 개의 프런트 엔드 서버와 확장 가능) 및 별도의 백 엔드 서버입니다. 프런트 엔드 풀에는 최대 12 개의 프런트 엔드 서버가 포함 될 수 있습니다. 여러 프런트 엔드 서버에 대 한 부하 분산이 필요 합니다. SIP 트래픽의 경우 DNS 부하 분산을 권장 하지만 하드웨어 로드 균형 조정도 지원 됩니다. SIP 트래픽에 대 한 DNS 부하 분산을 사용 하는 경우에도 HTTP 트래픽에 대 한 하드웨어 부하 분산 장치가 필요 합니다. 데이터베이스의 고가용성을 위해 SQL Server 미러링을 사용 하는 것이 좋습니다. 백 엔드 데이터베이스에는 별도의 인스턴스가 필요 하지만, 보관 데이터베이스, 모니터링 데이터베이스, 지속적인 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스를 collocate 수 있습니다. Lync Server 2013는 배포의 파일 공유에 대 한 공유 클러스터의 사용을 지원 합니다. 데이터베이스 저장소 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md)참조 하세요. 파일 저장소 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 파일 저장소 지원을](lync-server-2013-file-storage-support.md)참고 하세요.
        
        <div>
        

        > [!IMPORTANT]  
        > Lync Server 데이터베이스를 collocate 경우 가용성 및 성능에 영향을 줄 수 있는 모든 요인을 평가 하는 것이 좋습니다. 장애 조치(failover) 기능을 확인하려면 모든 장애 조치(failover) 시나리오를 테스트하세요.

        
        </div>
    
      - Collocated SQL Server Express 데이터베이스를 포함 하는 Standard Edition 서버입니다.

  - 배포에는 중앙 사이트와 연결 된 지점 사이트가 하나 이상 있을 수도 있습니다.

이 섹션에서는 Lync Server 2013 배포의 사이트 및 구성 요소에 대해 설명 합니다. Lync Server 2013 사이트, 토폴로지 및 구성 요소 계획에 대 한 자세한 내용은 계획 설명서의 lync server 2013에서 Lync server 2013 및 [참조 토폴로지](lync-server-2013-reference-topologies.md) 를 [계획 하기 전에 알아야 할 토폴로지 기본 사항](lync-server-2013-topology-basics-you-must-know-before-planning.md) 을 참조 하세요. 이전 릴리스의 구성 요소 통합에 대 한 자세한 내용은 [Lync Server 2013에서 지원 되는 마이그레이션 경로 및 공존 시나리오](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)를 참조 하세요.

<div>


> [!NOTE]  
> 스트레치 된 풀은 프런트 엔드, Edge, 중재 및 디렉터 서버 역할에 대해 지원 되지 않습니다.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>중앙 사이트 토폴로지 및 구성 요소 (온-프레미스)

중앙 사이트 토폴로지에는 프런트 엔드 풀 또는 표준 버전 서버 하나가 포함 되어야 하지만 각 중앙 사이트에는 다음이 포함 될 수 있습니다.

  - 여러 프런트 엔드 풀 (동일한 도메인 또는 다른 도메인에 있을 수 있음) 그러나 프런트 엔드 풀의 모든 프런트 엔드 서버와 해당 풀의 백 엔드 서버는 동일한 도메인에 있어야 합니다.

  - 여러 스탠더드 버전 서버.

  - Lync Server 2013의 Office 웹 응용 프로그램에서 Microsoft PowerPoint 프레젠테이션 공유 및 렌더링을 처리 하는 데 사용 되는 office Web Apps 서버입니다.

  - 경계 네트워크의 edge 서버 또는 Edge 풀 배포에 페더레이션 파트너, 공용 IM 연결, 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이, 원격 사용자 액세스, 모임에서 익명 사용자 참가 등을 원하는 경우 또는 Exchange UM (통합 메시징). Edge 서버를 사용 하 여 다른 서버 역할을 collocate 수 없습니다. 적절 한 경우 DNS 부하 분산을 유지 하는 것이 좋지만 하드웨어 로드 균형 조정도 지원 됩니다. 내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다. 부하 분산 요구 사항 및 지원에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 및 [lync server 2013의 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md) 설명서를 참조 하세요.

  - 중앙 사이트의 프런트 엔드 풀에서 엔터프라이즈 음성 또는 전화 접속 회의를 지원 하려는 경우 중재 서버 또는 풀입니다. 엔터프라이즈 음성 기능을 배포 하는 방법에 따라 프런트 엔드 풀의 중재 서버를 collocate (기본값) 또는 독립 실행형 중재 서버 또는 풀을 배포할 수 있습니다. DNS, 하드웨어 또는 응용 프로그램 부하 분산 (적절 한 경우)을 사용 하 여 PSTN 게이트웨이, IP-PBX 또는 SIP 트렁크 세션 경계 컨트롤 (SBC)을 포함 하는 중재 서버 풀의 게이트웨이 피어에서 트래픽을 분산할 수 있습니다. 적절 한 중재 서버 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 중재 서버에 대 한 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md) 을 참조 하세요.

  - 사용자가 시간에 따라 유지 되는 단체의 주제 기반 대화에 참여할 수 있게 하려는 경우 영구 채팅 서버. 용량 향상과 안정성이 높은 안정성을 제공 하기 위해 토폴로지에 영구 채팅 서버를 실행 하는 여러 대의 컴퓨터가 포함 될 수 있습니다. 엔터프라이즈 풀의 다른 서버 역할과 영구 채팅 서버를 collocate 수 없습니다. 그러나 Standard Edition 서버에서 영구 채팅 서버를 collocate 수 있습니다. 영구 채팅에는 데이터베이스가 필요 하며 지속적인 채팅 준수 데이터베이스를 구현 하는 경우 데이터베이스를 보관 데이터베이스, 모니터링 데이터베이스 또는 엔터프라이즈 에디션의 백 엔드 서버와 collocated 수 있습니다. 프런트 엔드 풀. 적절 한 영구 채팅 서버 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) 을 참조 하세요.

  - 모니터링-오디오/비디오 품질 (체감 품질) 및 배포에서 A/V 회의에 대 한 데이터 수집을 지원 하려는 경우 필요한 경우 모니터링 CDR 및 체감 품질 데이터를 사용 하 여 통화 안정성 및 미디어 품질의 상태를 표시 하는 가까운 실시간 알림을 생성 하는 Microsoft System Center Operations Manager (이전의 Microsoft Operations Manager)를 설치할 수 있습니다. 모니터링을 배포 하는 경우 프런트 엔드 서버 또는 Standard Edition 서버에서 collocated. 모니터링에는 데이터베이스가 필요 하지만, 데이터베이스는 보관 데이터베이스, 영구 채팅 데이터베이스, 지속적인 채팅 준수 데이터베이스 또는 Enterprise Edition 프런트 엔드 풀의 백 엔드 서버와 collocated 될 수 있습니다.

  - 배포에서 IM 통신 및 모임 콘텐츠 (규정 준수 사유)를 보관 하려는 경우 보관 합니다. 보관 하는 경우 collocated는 프런트 엔드 서버 또는 Standard Edition 서버에서 발생 합니다. 보관 저장소에는 보관 데이터베이스 배포 또는 Exchange 2013 저장소 통합이 필요 합니다. *혼합 모드*라고 하는 둘 다를 사용 하는 경우 exchange 2013 저장소를 사용 하 여 exchange 2013에 속한 사용자의 보관 데이터를 저장 하 고 배포의 다른 모든 사용자에 대 한 데이터를 보관 하는 데 보관 데이터베이스를 사용 합니다. 보관 데이터베이스가 필요한 경우 모니터링 데이터베이스, 영구 채팅 데이터베이스, 지속적인 채팅 준수 데이터베이스 또는 프런트 엔드 풀의 백 엔드 서버에서 데이터베이스를 collocated 수 있습니다. 적절 한 보관 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하세요.

  - 사용자의 홈 풀 (Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버)으로 Lync Server 2013 사용자 요청을 복구 하 고 리디렉션할 수 있도록 하려면 디렉터 또는 디렉터 풀을 선택 합니다. 외부 사용자 액세스를 지 원하는 각 중앙 사이트에서 하나 이상의 프런트 엔드 풀을 배포 하는 각 중앙 사이트에 디렉터 또는 디렉터 풀을 배포 하는 것이 좋습니다. 각 디렉터 풀에는 최대 10 개의 이사회이 포함 될 수 있습니다. 다른 서버 역할을 사용 하 여 디렉터를 collocated 수 없습니다. 적절 한 디렉터 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md) 를 참조 하세요.

  - 역방향 프록시-Lync Server 2013 구성 요소가 아니지만 페더레이션 사용자를 위해 웹 콘텐츠를 공유 하거나 이동성 트래픽을 지원 하려는 경우 필요 합니다. 역방향 프록시 서버에 Lync Server 2013 서버 역할을 collocate 수는 없지만, 다른 사용자에 게 사용 되는 조직의 기존 역방향 프록시 서버에 대 한 지원을 구성 하 여 Lync Server 2013 배포에 대 한 역방향 프록시 지원을 구현할 수 있습니다. 프로그램도. 리버스 프록시 서버에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013에 대 한 리버스 프록시 서버 설정을](lync-server-2013-setting-up-reverse-proxy-servers.md) 참조 하세요.

<div>


> [!NOTE]  
> Lync Server 2013에서 A/V 회의, 모니터링, 보관은 프런트 엔드 서버에서 실행 되며 더 이상 별도의 서버 역할이 아닙니다.



</div>

중앙 사이트에서 배포 하는 모든 프런트 엔드 풀 및 Standard Edition 서버는 중앙 사이트에 대해 배포 하는 다음 중 하나를 공유 합니다.

  - 이사 또는 이사 은행

  - 독립 실행형 중재 서버 또는 풀

  - Office Web Apps 서버

  - Edge 서버 또는 Edge 풀

  - 영구 채팅 서버 또는 풀

  - 모니터링

  - 보관

<div>


> [!NOTE]  
> Exchange 2013 통합 메시징의 통합을 지원 하려는 경우에는 Lync server 2013 배포를 사용 하 여 Exchange UM 서버를 구현할 수 있지만 Lync Server 2013 사이트의 구성 요소가 아닙니다.



</div>

여러 중앙 사이트는 한 중앙 사이트에서 배포 하는 다음 중 하나를 공유할 수도 있습니다.

  - 독립 실행형 중재 서버 또는 풀

  - Edge 서버 또는 Edge 풀

  - 영구 채팅 서버 또는 풀

  - 보관

  - 모니터링

<div>


> [!NOTE]  
> Exchange UM 서버는 Lync Server 2013 배포로 구현 하 고 여러 중앙 사이트에서 공유할 수 있지만 Lync Server 2013 사이트의 구성 요소는 아닙니다.



</div>

Lync Server 2013 서버 역할 및 기능에 대 한 자세한 내용은 계획 설명서의 [Lync server 2013에서 서버 역할](lync-server-2013-server-roles.md) 을 참조 하세요.

Lync Server 2013 서버 collocation 지원에 대 한 요약 정보는 [Lync server 2013에서 지원 되는 서버 위치](lync-server-2013-supported-server-collocation.md)를 참조 하세요.

이 섹션의 앞부분에 설명 된 서버 역할 및 기능 외에도 Lync Server 2013에는 다음과 같은 추가 구성 요소와 옵션이 포함 되어 있습니다.

  - 들

  - PSTN 게이트웨이 (Enterprise Voice를 배포 하는 경우)

  - Exchange UM 서버

  - DNS 부하 분산

  - 하드웨어 부하 분산 장치

  - SQL Server 데이터베이스

  - 파일 공유

모든 Lync Server 2013 기능, 구성 요소 및 옵션에 대 한 자세한 내용은 계획 설명서를 참조 하세요.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>지점 사이트 토폴로지 및 구성 요소 (온-프레미스)

지점 사이트는 중앙 사이트와 연결 되며, 지점 사이트의 각 Survivable Branch 기기는 Enterprise Edition 프런트 엔드 풀 또는 연결 된 중앙 사이트의 스탠더드 버전 서버와 연결 됩니다. 분기 사이트는 대부분의 기능에 종속 되어 있으므로 지점 사이트의 구성 요소에는 다음만 포함 됩니다.

  - PSTN (공개 통신 네트워크) 게이트웨이와 일부 Lync Server 기능을 결합 하는 Survivable Branch 기기입니다. 중재 서버는 Survivable Branch 기기의 레지스트라 인스턴스와 collocated 수 있으며, 독립 실행형 중재 서버 또는 중재 서버 풀을 배포할 수 있습니다.

  - Lync Server 2013 등록자 및 조정 서버 소프트웨어가 설치 된 Windows Server를 실행 하는 서버인 Survivable Branch 서버입니다.

  - 독립 실행형 PSTN 게이트웨이 (Survivable Branch 기기의 일부가 아님) 및 독립 실행형 중재 서버.

Survivable 분기 서버에 대 한 요구 사항은 Lync Server 2013 서버 역할의 요구 사항과 동일 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

