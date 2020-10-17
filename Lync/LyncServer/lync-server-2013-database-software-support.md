---
title: Lync Server 2013 데이터베이스 소프트웨어 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f7290a6d4e80c522d29c886b49723cca51d19e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516505"
---
# <a name="database-software-support-in-lync-server-2013"></a>Lync Server 2013의 데이터베이스 소프트웨어 지원

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-12-01_

Lync Server 2013에서는 다음과 같은 데이터베이스 관리 시스템을 지원 합니다.

  - **프런트 엔드 풀의 백 엔드 데이터베이스, 보관 데이터베이스, 모니터링 데이터베이스, 영구 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스**
    
      - Microsoft SQL Server 2008 R2 Enterprise 데이터베이스 소프트웨어(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.
    
      - Microsoft SQL Server 2008 R2 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.
    
      - Microsoft SQL Server 2012 Enterprise(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.
    
      - Microsoft SQL Server 2012 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.

  - **Standard Edition 서버 데이터베이스 및 프런트 엔드 서버 데이터베이스**
    
      - Microsoft SQL Server 2012 Express (64 비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.
        
        Microsoft는 프런트 엔드 서버 및 Standard Edition 서버에서의 SQL Server 패치 및 업그레이드를 지원 합니다. 그러나 프런트 엔드 서버에서 모든 유형의 업그레이드 또는 패치를 수행 하는 경우에는 쿼럼 요구 사항을 고려해 야 합니다. 자세한 내용은 프런트 엔드 서버 [, 인스턴트 메시징 및 현재 상태를 Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)에 제공 하는 lync server 2013 및 토폴로지 및 구성 요소에 대 한 [프런트 엔드 서버 업그레이드 또는 업데이트](lync-server-2013-upgrade-or-update-front-end-servers.md) 를 참조 하세요.
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64 비트 버전)는 각 Standard Edition Server 및 각 프런트 엔드 서버 서버에서 Lync Server 2013에 의해 자동으로 설치 됩니다.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013는 32 비트 버전의 SQL Server를 지원 하지 않습니다. 64 비트 버전을 사용 해야 합니다.</P>
> <LI>
> <P>SQL Server Web edition 및 SQL Server Workgroup edition은 지원 되지 않습니다. Lync Server 2013에는 사용할 수 없습니다.</P>
> <LI>
> <P>Lync Server 2013에서는 네이티브 데이터베이스 미러링을 지원 합니다.</P>
> <LI>
> <P>모니터링 서버 역할을 사용 하려면 SQL Server Reporting Services를 설치 해야 합니다.</P></LI></UL>



</div>

프런트 엔드 풀에서는 백 엔드 데이터베이스를 단일 SQL Server 컴퓨터로 사용할 수 있습니다.

<div>


> [!IMPORTANT]  
> Lync Server 데이터베이스를 다른 데이터베이스와 함께 배치할 경우 가용성 및 성능에 영향을 줄 수 있는 모든 요소를 평가 하 고, 노드 하나가 실패할 경우 나머지 노드가 부하를 처리할 수 있도록 하는 것이 좋습니다. 장애 조치(failover) 기능을 확인하려면 모든 장애 조치(failover) 시나리오를 테스트하는 것이 좋습니다.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>SQL 미러링 및 SQL 클러스터링 사용

Lync Server 2013에서는 각 Lync Server 데이터베이스에 대해 SQL 미러링 또는 SQL 클러스터링을 사용할 수도 있습니다. Lync Server 2013의 토폴로지 작성기 도구를 사용 하 여 SQL 미러링을 쉽게 설정할 수 있습니다. SQL 장애 조치 (failover) 클러스터링의 경우 설치 프로그램에 SQL Server를 사용 해야 합니다.

Lync Server 2013는 이전 버전의 Lync Server에서 업그레이드 한 greenfield 배포 및 조직을 비롯 하 여 모든 배포에 대해 SQL 미러링 및 SQL 클러스터링 토폴로지를 모두 지원 합니다.

SQL 클러스터링 지원은 액티브/패시브 구성을 위한 것입니다. 성능상의 이유로 수동 노드를 다른 SQL 인스턴스에서 공유 해서는 안 됩니다.

다음과 같은 지원이 포함 됩니다.

  - 다음에 대 한 2 개 노드 장애 조치 (failover) 클러스터링:
    
      - Microsoft SQL Server 2012 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.
    
      - Microsoft SQL Server 2008 R2 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.

  - 다음에 대 한 최대 16 개 노드 장애 조치 (failover) 클러스터링:
    
      - Microsoft SQL Server 2012 Enterprise(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.
    
      - Microsoft SQL Server 2008 R2 Enterprise 데이터베이스 소프트웨어(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.

SQL 미러링에 대 한 자세한 내용은 [Lync server 2013에서 백 엔드 서버 고가용성](lync-server-2013-back-end-server-high-availability.md)을 참조 하십시오. SQL 클러스터링을 배포 하는 방법에 대 한 자세한 내용은 [CONFIGURE SQL Server 클러스터링 For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)을 참조 하십시오.

SQL Server 2012의 장애 조치 (failover) 클러스터링에 대 한 자세한 내용 및 모범 사례는을 참조 하십시오 <https://technet.microsoft.com/library/hh231721.aspx> . SQL Server 2008의 장애 조치 (failover) 클러스터링의 경우를 참조 하세요 <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .

</div>

</div>

<span> </span>

</div>

</div>

</div>

