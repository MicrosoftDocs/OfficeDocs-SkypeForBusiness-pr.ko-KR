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
# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="93340-102">Lync Server 2013의 데이터베이스 소프트웨어 지원</span><span class="sxs-lookup"><span data-stu-id="93340-102">Database software support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93340-103">_**마지막으로 수정 된 항목:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="93340-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="93340-104">Lync Server 2013에서는 다음과 같은 데이터베이스 관리 시스템을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="93340-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="93340-105">**프런트 엔드 풀의 백 엔드 데이터베이스, 보관 데이터베이스, 모니터링 데이터베이스, 영구 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스**</span><span class="sxs-lookup"><span data-stu-id="93340-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="93340-p101">Microsoft SQL Server 2008 R2 Enterprise 데이터베이스 소프트웨어(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="93340-p102">Microsoft SQL Server 2008 R2 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-p102">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="93340-p103">Microsoft SQL Server 2012 Enterprise(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="93340-p104">Microsoft SQL Server 2012 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="93340-114">**Standard Edition 서버 데이터베이스 및 프런트 엔드 서버 데이터베이스**</span><span class="sxs-lookup"><span data-stu-id="93340-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="93340-115">Microsoft SQL Server 2012 Express (64 비트 버전).</span><span class="sxs-lookup"><span data-stu-id="93340-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="93340-116">최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="93340-117">Microsoft는 프런트 엔드 서버 및 Standard Edition 서버에서의 SQL Server 패치 및 업그레이드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="93340-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="93340-118">그러나 프런트 엔드 서버에서 모든 유형의 업그레이드 또는 패치를 수행 하는 경우에는 쿼럼 요구 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93340-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="93340-119">자세한 내용은 프런트 엔드 서버 [, 인스턴트 메시징 및 현재 상태를 Lync server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)에 제공 하는 lync server 2013 및 토폴로지 및 구성 요소에 대 한 [프런트 엔드 서버 업그레이드 또는 업데이트](lync-server-2013-upgrade-or-update-front-end-servers.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="93340-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="93340-120">Microsoft SQL Server 2012 Express (64 비트 버전)는 각 Standard Edition Server 및 각 프런트 엔드 서버 서버에서 Lync Server 2013에 의해 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93340-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="93340-121">Lync Server 2013는 32 비트 버전의 SQL Server를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="93340-122">64 비트 버전을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93340-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="93340-123">SQL Server Web edition 및 SQL Server Workgroup edition은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="93340-124">Lync Server 2013에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="93340-125">Lync Server 2013에서는 네이티브 데이터베이스 미러링을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="93340-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="93340-126">모니터링 서버 역할을 사용 하려면 SQL Server Reporting Services를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93340-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="93340-127">프런트 엔드 풀에서는 백 엔드 데이터베이스를 단일 SQL Server 컴퓨터로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="93340-128">Lync Server 데이터베이스를 다른 데이터베이스와 함께 배치할 경우 가용성 및 성능에 영향을 줄 수 있는 모든 요소를 평가 하 고, 노드 하나가 실패할 경우 나머지 노드가 부하를 처리할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="93340-129">장애 조치(failover) 기능을 확인하려면 모든 장애 조치(failover) 시나리오를 테스트하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="93340-130">SQL 미러링 및 SQL 클러스터링 사용</span><span class="sxs-lookup"><span data-stu-id="93340-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="93340-131">Lync Server 2013에서는 각 Lync Server 데이터베이스에 대해 SQL 미러링 또는 SQL 클러스터링을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="93340-132">Lync Server 2013의 토폴로지 작성기 도구를 사용 하 여 SQL 미러링을 쉽게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="93340-133">SQL 장애 조치 (failover) 클러스터링의 경우 설치 프로그램에 SQL Server를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93340-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="93340-134">Lync Server 2013는 이전 버전의 Lync Server에서 업그레이드 한 greenfield 배포 및 조직을 비롯 하 여 모든 배포에 대해 SQL 미러링 및 SQL 클러스터링 토폴로지를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="93340-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="93340-135">SQL 클러스터링 지원은 액티브/패시브 구성을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="93340-135">SQL Clustering support is for an active/passive configuration.</span></span> <span data-ttu-id="93340-136">성능상의 이유로 수동 노드를 다른 SQL 인스턴스에서 공유 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93340-136">For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="93340-137">다음과 같은 지원이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93340-137">The following support is included:</span></span>

  - <span data-ttu-id="93340-138">다음에 대 한 2 개 노드 장애 조치 (failover) 클러스터링:</span><span class="sxs-lookup"><span data-stu-id="93340-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="93340-139">Microsoft SQL Server 2012 Standard(64비트 버전).</span><span class="sxs-lookup"><span data-stu-id="93340-139">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="93340-140">최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-140">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="93340-141">Microsoft SQL Server 2008 R2 Standard(64비트 버전).</span><span class="sxs-lookup"><span data-stu-id="93340-141">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="93340-142">최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-142">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="93340-143">다음에 대 한 최대 16 개 노드 장애 조치 (failover) 클러스터링:</span><span class="sxs-lookup"><span data-stu-id="93340-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="93340-144">Microsoft SQL Server 2012 Enterprise(64비트 버전).</span><span class="sxs-lookup"><span data-stu-id="93340-144">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="93340-145">최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-145">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="93340-146">Microsoft SQL Server 2008 R2 Enterprise 데이터베이스 소프트웨어(64비트 버전).</span><span class="sxs-lookup"><span data-stu-id="93340-146">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="93340-147">최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="93340-147">Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="93340-148">SQL 미러링에 대 한 자세한 내용은 [Lync server 2013에서 백 엔드 서버 고가용성](lync-server-2013-back-end-server-high-availability.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="93340-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="93340-149">SQL 클러스터링을 배포 하는 방법에 대 한 자세한 내용은 [CONFIGURE SQL Server 클러스터링 For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="93340-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="93340-150">SQL Server 2012의 장애 조치 (failover) 클러스터링에 대 한 자세한 내용 및 모범 사례는을 참조 하십시오 <https://technet.microsoft.com/library/hh231721.aspx> .</span><span class="sxs-lookup"><span data-stu-id="93340-150">For more information and best practices for failover clustering in SQL Server 2012, see <https://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="93340-151">SQL Server 2008의 장애 조치 (failover) 클러스터링의 경우를 참조 하세요 <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx> .</span><span class="sxs-lookup"><span data-stu-id="93340-151">For failover clustering in SQL Server 2008, see <https://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

