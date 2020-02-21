---
title: Lync Server 2013 지원 되는 토폴로지
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
ms.openlocfilehash: 732b9a70ee61ce4ecdf19b3f668ba09a3416cca9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-topologies-in-lync-server-2013"></a>Lync Server 2013에서 지원 되는 토폴로지

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-01-14_

Lync Server 2013에서는 온-프레미스에 사이트를 배포할 수 있도록 지원 하 고 하이브리드 배포 라고도 하는 Lync Online 배포와의 통합을 기반으로 합니다. 하이브리드 배포에서는 온-프레미스와 온라인에 각각 사용자가 있습니다.

온-프레미스 배포의 경우 Lync Server 2013은 고가용성 및 위치 요구 사항을 충족 하기 위해 확장할 수 있는 하나 이상의 사이트 배포를 지원 합니다. 이러한 사이트와 해당 구성 요소를 조직의 액세스 및 복구 요구 사항을 충족하도록 구성할 수 있습니다.

Lync Server 2013 온-프레미스 배포는 다음으로 구성 됩니다.

  - 배포에 중앙 사이트(데이터 센터라고도 함)가 하나 이상 포함되어야 합니다. 각 중앙 사이트는 하나 이상의 Enterprise Edition 프런트 엔드 풀 또는 하나의 Standard Edition 서버를 포함해야 합니다. 이러한 풀 또는 서버는 다음으로 구성됩니다.
    
      - Enterprise Edition 프런트 엔드 풀은 하나 이상의 프런트 엔드 서버와 별도의 백 엔드 서버로 구성되며, 일반적으로 확장성을 위해 둘 이상의 프런트 엔드 서버를 포함합니다. 프런트 엔드 풀은 최대 12 개의 프런트 엔드 서버를 포함할 수 있습니다. 프런트 엔드 서버가 여러 개인 경우 부하 분산이 필요합니다. SIP 트래픽의 경우 DNS 부하 분산이 권장되지만 하드웨어 부하 분산도 지원됩니다. SIP 트래픽에 DNS 부하 분산을 사용하는 경우에도 HTTP 트래픽에 대한 하드웨어 부하 분산 장치가 필요합니다. 데이터베이스의 고가용성을 위해 SQL Server 미러링을 사용 하는 것이 좋습니다. 백 엔드 데이터베이스에는 별도의 인스턴스가 필요하지만 보관 데이터베이스, 미러링 데이터베이스, 영구 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스를 함께 배치할 수 있습니다. Lync Server 2013에서는 배포의 파일 공유에 대 한 공유 클러스터 사용을 지원 합니다. 데이터베이스 저장소 요구 사항에 대 한 자세한 내용은 [Lync Server 2013에서 데이터베이스 소프트웨어 지원을](lync-server-2013-database-software-support.md)참조 하십시오. 파일 저장소 요구 사항에 대 한 자세한 내용은 [Lync Server 2013의 파일 저장소 지원을](lync-server-2013-file-storage-support.md)참조 하십시오.
        
        <div>
        

        > [!IMPORTANT]  
        > Lync Server 데이터베이스를 함께 배치할 경우 가용성 및 성능에 영향을 줄 수 있는 모든 요소를 평가 하는 것이 좋습니다. 장애 조치(failover) 기능을 확인하려면 모든 장애 조치(failover) 시나리오를 테스트하는 것이 좋습니다.

        
        </div>
    
      - Standard Edition 서버는 함께 배치된 SQL Server Express 데이터베이스를 포함합니다.

  - 배포에 중앙 사이트와 연결된 하나 이상의 분기 사이트를 포함할 수도 있습니다.

이 섹션에서는 Lync Server 2013 배포의 사이트 및 구성 요소에 대해 설명 합니다. Lync Server 2013 사이트, 토폴로지 및 구성 요소 계획에 대 한 자세한 내용은 계획 설명서에서 lync server 2013 및 [참조 2013 토폴로지](lync-server-2013-reference-topologies.md) 를 [계획 하기 전에 알아야 할 토폴로지 기본 사항을](lync-server-2013-topology-basics-you-must-know-before-planning.md) 참조 하세요. 이전 릴리스의 구성 요소를 통합 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 지원 되는 마이그레이션 경로 및 동시 사용 시나리오](lync-server-2013-supported-migration-paths-and-coexistence-scenarios.md)를 참조 하세요.

<div>


> [!NOTE]  
> 스트레치 된 풀은 프런트 엔드, Edge, 중재 및 디렉터 서버 역할에 대해 지원 되지 않습니다.



</div>

<div>

## <a name="central-site-topologies-and-components-on-premises"></a>중앙 사이트 토폴로지 및 구성 요소(온-프레미스)

중앙 사이트 토폴로지는 하나의 프런트 엔드 풀 또는 하나의 Standard Edition 서버를 포함해야 하지만 각 중앙 사이트는 다음을 포함할 수도 있습니다.

  - 같은 도메인 또는 다른 도메인에 있을 수 있는 여러 프런트 엔드 풀. 그러나 프런트 엔드 풀의 모든 프런트 엔드 서버와 해당 풀에 대한 백 엔드 서버는 같은 도메인에 있어야 합니다.

  - 여러 Standard Edition 서버

  - Lync Server 2013의 Office 웹 응용 프로그램에서 사용 하는 office Web Apps 서버는 Microsoft PowerPoint 프레젠테이션의 공유 및 렌더링을 처리 합니다.

  - 경계 네트워크의에 지 서버 또는에 지 풀 배포에서 페더레이션 파트너, 공용 IM 연결, 확장 가능한 메시징 및 현재 상태 프로토콜 (XMPP) 게이트웨이, 원격 사용자 액세스, 모임에 대 한 익명 사용자의 참여를 지원 하려면 또는 Exchange UM (통합 메시징)이 있습니다. 다른 서버 역할을 에지 서버와 함께 배치할 수 없습니다. 해당되는 경우 DNS 부하 분산이 권장되지만 하드웨어 부하 분산도 지원됩니다. 내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다. 즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다. 부하 분산 요구 사항 및 지원에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 외부 사용자 액세스 계획](lync-server-2013-planning-for-external-user-access.md) 및 [lync Server 2013의](lync-server-2013-deploying-external-user-access.md) 배포 설명서에서 external user access 배포를 참조 하세요.

  - 중재 서버 또는 풀 (중앙 사이트의 프런트 엔드 풀에서 Enterprise Voice 또는 전화 접속 회의를 지원 하려는 경우) Enterprise Voice support를 배포 하는 방법에 따라 프런트 엔드 풀에 중재 서버를 함께 배치할 (기본값) 아니면 독립 실행형 중재 서버 또는 풀을 배포할 수 있습니다. DNS, 하드웨어 또는 응용 프로그램 부하 분산 (해당 하는 경우)을 사용 하 여 PSTN 게이트웨이, IP-PBX 또는 SIP 트렁크 세션 테두리 조절 (SBC)을 포함 하 여 중재 서버 풀의 게이트웨이 피어에서 트래픽을 분산할 수 있습니다. 적절 한 중재 서버 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 중재 서버에 대 한 배포 지침](lync-server-2013-deployment-guidelines-for-mediation-server.md) 을 참조 하십시오.

  - 영구 채팅 서버 (사용자가 시간에 따라 지속 되는 단체의 항목 기반 대화에 참가할 수 있도록 하려는 경우) 더 많은 용량과 안정성을 제공 하기 위해 토폴로지에 영구 채팅 서버를 실행 하는 여러 컴퓨터를 포함할 수 있습니다. 엔터프라이즈 풀의 다른 서버 역할과 영구 채팅 서버를 함께 배치할 수는 없습니다. 그러나 Standard Edition 서버에서 영구 채팅 서버를 함께 배치할 수 있습니다. 영구 채팅에는 데이터베이스가 필요하며, 영구 채팅 준수를 구현하는 경우에는 영구 채팅 준수 데이터베이스도 필요하지만 이러한 데이터베이스는 보관 데이터베이스/모니터링 데이터베이스와 함께 배치하거나 Enterprise Edition 프런트 엔드 풀의 백 엔드 서버에 배치할 수 있습니다. 적절 한 영구 채팅 서버 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서에서 " [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) "을 참조 하십시오.

  - 모니터링(배포에 포함된 Enterprise Voice 및 A/V 회의의 CDR(통화 정보 기록) 및 오디오/비디오 QoE(체감 품질)에 대한 데이터 수집을 지원하려는 경우). 필요에 따라 모니터링 CDR 및 QoE 데이터를 사용 하 여 통화 안정성 및 미디어 품질의 상태를 표시 하는 거의 실시간 경고를 생성 하는 Microsoft System Center Operations Manager (이전 Microsoft Operations Manager)를 설치할 수 있습니다. 모니터링은 배포하는 경우 프런트 엔드 서버 또는 Standard Edition 서버에 배치됩니다. 모니터링에는 데이터베이스가 필요하지만 해당 데이터베이스는 보관 데이터베이스/영구 채팅 데이터베이스/영구 채팅 준수 데이터베이스와 함께 배치하거나 Enterprise Edition 프런트 엔드 풀의 백 엔드 서버에 배치할 수 있습니다.

  - 보관(준수용으로 배포의 IM 통신 및 모임 콘텐츠를 보관하려는 경우). 보관은 배포하는 경우 프런트 엔드 서버 또는 Standard Edition 서버에 배치됩니다. 보관 저장소를 사용 하려면 보관 데이터베이스를 배포 하거나 Exchange 2013 저장소와 통합 해야 합니다. *혼합 모드*라고 하는 둘 다 사용 하는 경우 exchange 2013 저장소는 exchange 2013에 있는 사용자에 대 한 보관 데이터를 저장 하는 데 사용 되며, 배포의 다른 모든 사용자에 대 한 데이터를 보관 하는 데 보관 데이터베이스를 사용 합니다. 보관 데이터베이스가 필요한 경우 해당 데이터베이스는 모니터링 데이터베이스/영구 채팅 데이터베이스/영구 채팅 준수 데이터베이스와 함께 배치하거나 프런트 엔드 풀의 백 엔드 서버에 배치할 수 있습니다. 적절 한 보관 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 보관 계획](lync-server-2013-planning-for-archiving.md) 을 참조 하십시오.

  - 디렉터 또는 디렉터 풀-사용자의 홈 풀에 대 한 Lync Server 2013 사용자 요청을 복구 및 리디렉션하는 것을 용이 하 게 하려면 (Enterprise Edition 프런트 엔드 풀 또는 Standard Edition Server 일 수 있음) 외부 사용자 액세스를 지원하는 각 중앙 사이트 및 하나 이상의 프런트 엔드 풀을 배포한 각 중앙 사이트에 디렉터 또는 디렉터 풀을 배포하는 것이 좋습니다. 각 디렉터 풀은 최대 10개의 디렉터를 포함할 수 있습니다. 디렉터를 다른 서버 역할과 함께 배치할 수는 없습니다. 적절 한 디렉터 토폴로지를 계획 하는 방법에 대 한 자세한 내용은 계획 설명서의 [Lync Server 2013에서 디렉터에 대 한 시나리오](lync-server-2013-scenarios-for-the-director.md) 를 참조 하십시오.

  - 역방향 프록시-Lync Server 2013 구성 요소가 아니지만, 페더레이션 사용자에 대해 웹 콘텐츠를 공유 하거나 모바일 트래픽을 지원 하려는 경우에 필요 합니다. 역방향 프록시 서버를 Lync Server 2013 서버 역할을 사용 하 여 함께 배치할 수는 없지만 다른 사용자에 게 사용 되는 조직의 기존 역방향 프록시 서버에 대 한 지원을 구성 하 여 Lync Server 2013 배포에 대 한 역방향 프록시 지원을 구현할 수 있습니다. 프로그램만. 역방향 프록시 서버에 대 한 자세한 내용은 배포 설명서에서 [Lync Server 2013에 대 한 역방향 프록시 서버 설정을](lync-server-2013-setting-up-reverse-proxy-servers.md) 참조 하십시오.

<div>


> [!NOTE]  
> Lync Server 2013에서는 A/V 회의, 모니터링 및 보관이 프런트 엔드 서버에서 실행 되며 더 이상 별도의 서버 역할이 아닙니다.



</div>

중앙 사이트에 배포한 모든 프런트 엔드 풀 및 Standard Edition 서버는 중앙 사이트용으로 배포한 다음 항목을 공유합니다.

  - 디렉터 또는 디렉터 풀

  - 독립 실행형 중재 서버 또는 풀

  - Office Web Apps 서버

  - 에지 서버 또는 에지 풀

  - 영구 채팅 서버 또는 풀

  - 모니터링

  - 보관할

<div>


> [!NOTE]  
> Exchange 2013 통합 메시징의 통합을 지원 하려고 하지만 Lync Server 2013 사이트의 구성 요소가 아닌 경우 Lync Server 2013 배포를 사용 하 여 Exchange UM 서버를 구현할 수 있습니다.



</div>

또한 하나의 중앙 사이트에 배포한 다음 항목을 여러 중앙 사이트에서 공유할 수 있습니다.

  - 독립 실행형 중재 서버 또는 풀

  - 에지 서버 또는 에지 풀

  - 영구 채팅 서버 또는 풀

  - 보관할

  - 모니터링

<div>


> [!NOTE]  
> Exchange UM 서버는 Lync Server 2013 배포를 사용 하 여 구현 하 고 여러 중앙 사이트에서 공유할 수 있지만 Lync Server 2013 사이트의 구성 요소는 아닙니다.



</div>

Lync Server 2013 서버 역할 및 기능에 대 한 자세한 내용은 계획 설명서에서 [Lync server 2013의 서버 역할](lync-server-2013-server-roles.md) 을 참조 하십시오.

Lync Server 2013 서버 위치 지원에 대 한 요약은 [Lync server 2013에서 지원 되는 서버 위치](lync-server-2013-supported-server-collocation.md)를 참조 하세요.

이 섹션의 앞 부분에서 설명한 서버 역할 및 기능 외에도 Lync Server 2013에는 다음과 같은 추가 구성 요소와 옵션이 포함 되어 있으며,이는 다음 중 일부 또는 모두를 포함할 수 있습니다.

  - 방화벽

  - PSTN 게이트웨이(Enterprise Voice를 배포하는 경우)

  - Exchange UM 서버

  - DNS 부하 분산

  - 하드웨어 부하 분산 장치

  - SQL Server 데이터베이스

  - 파일 공유

모든 Lync Server 2013 기능, 구성 요소 및 옵션에 대 한 자세한 내용은 계획 설명서를 참조 하십시오.

</div>

<div>

## <a name="branch-site-topologies-and-components-on-premises"></a>분기 사이트 토폴로지 및 구성 요소(온-프레미스)

분기 사이트는 중앙 사이트와 연결되며, 분기 사이트의 각 SBA(Survivable Branch Appliance)는 연결된 중앙 사이트의 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버와 연결됩니다. 분기 사이트는 대부분의 기능을 중앙 사이트에 의존하므로 다음 구성 요소만 포함합니다.

  - 공중 전화망 (PSTN) 게이트웨이와 일부 Lync Server 기능을 결합 하는 Sba (survivable Branch 기기입니다. 중재 서버는 Sba (survivable 분기 기기의 등록자 인스턴스와 함께 배치 된 수 있으며 독립 실행형 중재 서버 또는 중재 서버 풀을 배포할 수 있습니다.

  - Lync Server 2013 등록자 및 중재 서버 소프트웨어가 설치 된 Windows Server를 실행 하는 서버에 해당 하는 Sba (survivable 분기 서버

  - 독립 실행형 PSTN 게이트웨이(SBA(Survivable Branch Appliance)의 일부가 아님) 및 독립 실행형 중재 서버

Sba (survivable 분기 서버에 대 한 요구 사항은 Lync Server 2013 서버 역할에 대 한 요구 사항과 동일 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

