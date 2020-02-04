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
ms.openlocfilehash: d4c39a51f742266c12f618f687c23c645977ffdb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728568"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a>Lync Server 2013의 데이터베이스 소프트웨어 지원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-12-01_

Lync Server 2013는 다음 데이터베이스 관리 시스템을 지원 합니다.

  - **프런트 엔드 풀의 백 엔드 데이터베이스, 보관 데이터베이스, 모니터링 데이터베이스, 영구 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스 **
    
      - Microsoft SQL Server 2008 R2 Enterprise 데이터베이스 소프트웨어(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.
    
      - Microsoft SQL Server 2008 R2 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.
    
      - Microsoft SQL Server 2012 Enterprise(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.
    
      - Microsoft SQL Server 2012 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.

  - **Standard Edition server 데이터베이스 및 프런트 엔드 서버 데이터베이스**
    
      - Microsoft SQL Server 2012 Express(64비트 버전). 또한 최신 서비스 팩을 실행하는 것이 좋습니다.
        
        프런트 엔드 서버와 Standard Edition 서버에서 Microsoft SQL Server의 패치 및 업그레이드를 지원 합니다. 그러나 프런트 엔드 서버에서 모든 종류의 업그레이드 또는 패치를 수행 하는 경우에는 쿼럼 요구 사항을 고려해 야 합니다. 자세한 내용은 [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) 및 [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)를 참조하세요.
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2012 Express (64 비트 버전)는 각 Standard Edition server 및 각 프런트 엔드 서버 서버의 Lync Server 2013에 의해 자동으로 설치 됩니다.

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Lync Server 2013는 SQL Server의 32 비트 버전을 지원 하지 않습니다. 64 비트 버전을 사용 해야 합니다.</P>
> <LI>
> <P>SQL Server Web edition 및 SQL Server Workgroup edition은 지원 되지 않습니다. Lync Server 2013에서는 사용할 수 없습니다.</P>
> <LI>
> <P>Lync Server 2013는 네이티브 데이터베이스 미러링을 지원 합니다.</P>
> <LI>
> <P>모니터링 서버 역할을 사용 하려면 SQL Server Reporting Services를 설치 해야 합니다.</P></LI></UL>



</div>

프런트 엔드 풀에서 백 엔드 데이터베이스는 단일 SQL Server 컴퓨터 일 수 있습니다.

<div>


> [!IMPORTANT]  
> 다른 데이터베이스를 사용 하 여 Lync Server 데이터베이스를 collocate 경우 사용 가능성 및 성능에 영향을 줄 수 있는 모든 요소를 평가 하 고, 한 노드에 장애가 발생 하는 경우 나머지 노드가 로드를 처리할 수 있도록 하는 것이 좋습니다. 장애 조치(failover) 기능을 확인하려면 모든 장애 조치(failover) 시나리오를 테스트하세요.



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a>SQL 미러링 및 SQL 클러스터링 사용

Lync Server 2013에서는 각 Lync Server 데이터베이스에 대해 SQL 미러링 또는 SQL 클러스터링 사용을 지원 합니다. Lync Server 2013의 토폴로지 작성기 도구를 사용 하 여 SQL 미러링을 쉽게 설정할 수 있습니다. SQL 장애 조치(failover) 클러스터링의 경우 설정을 위해 SQL Server를 사용해야 합니다.

Lync Server 2013는 이전 버전의 Lync Server에서 업그레이드 한 greenfield 배포 및 조직을 비롯 하 여 모든 배포에 대해 SQL 미러링 및 SQL 클러스터링 토폴로지를 모두 지원 합니다.

SQL 클러스터링 지원은 능동/수동 구성을 위한 것으로, 성능을 위해 수동 노드는 다른 SQL 인스턴스와 공유하지 말아야 합니다.

다음과 같은 지원이 포함됩니다.

  - 다음을 위한 2개 노드 장애 조치(failover) 클러스터링:
    
      - Microsoft SQL Server 2012 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.
    
      - Microsoft SQL Server 2008 R2 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.

  - 다음을 위한 최대 16개 노드 장애 조치(failover) 클러스터링:
    
      - Microsoft SQL Server 2012 Enterprise(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.
    
      - Microsoft SQL Server 2008 R2 Enterprise 데이터베이스 소프트웨어(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.

SQL 미러링에 대 한 자세한 내용은 [Lync server 2013에서 백 엔드 서버의](lync-server-2013-back-end-server-high-availability.md)고가용성을 참조 하세요. SQL 클러스터링을 배포 하는 방법에 대 한 자세한 내용은 [Lync server 2013에 대 한 Sql Server 클러스터링 구성을](lync-server-2013-configure-sql-server-clustering.md)참조 하세요.

SQL Server 2012의 장애 조치 (failover) 클러스터링에 대 한 자세한 내용 <http://technet.microsoft.com/en-us/library/hh231721.aspx>및 모범 사례를 보려면을 참조 하세요. SQL Server 2008의 장애 조치 (failover) <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>클러스터링에 대 한 자세한 내용은을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

