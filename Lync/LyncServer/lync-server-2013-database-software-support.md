---
title: Lync Server 2013 데이터베이스 소프트웨어 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bc8daef764ce5b15fd8c8b7e29f7031ebcfbafc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="9cc1d-102">Lync Server 2013의 데이터베이스 소프트웨어 지원</span><span class="sxs-lookup"><span data-stu-id="9cc1d-102">Database software support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9cc1d-103">_**마지막으로 수정한 주제:** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="9cc1d-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="9cc1d-104">Lync Server 2013는 다음 데이터베이스 관리 시스템을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="9cc1d-105">\*\*프런트 엔드 풀의 백 엔드 데이터베이스, 보관 데이터베이스, 모니터링 데이터베이스, 영구 채팅 데이터베이스 및 영구 채팅 준수 데이터베이스 \*\*</span><span class="sxs-lookup"><span data-stu-id="9cc1d-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="9cc1d-p101">Microsoft SQL Server 2008 R2 Enterprise 데이터베이스 소프트웨어(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="9cc1d-108">Microsoft SQL Server 2008 R2 Standard(64비트 버전).</span><span class="sxs-lookup"><span data-stu-id="9cc1d-108">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="9cc1d-109">최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-109">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="9cc1d-p103">Microsoft SQL Server 2012 Enterprise(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="9cc1d-p104">Microsoft SQL Server 2012 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="9cc1d-114">**Standard Edition server 데이터베이스 및 프런트 엔드 서버 데이터베이스**</span><span class="sxs-lookup"><span data-stu-id="9cc1d-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="9cc1d-115">Microsoft SQL Server 2012 Express(64비트 버전).</span><span class="sxs-lookup"><span data-stu-id="9cc1d-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="9cc1d-116">또한 최신 서비스 팩을 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="9cc1d-117">프런트 엔드 서버와 Standard Edition 서버에서 Microsoft SQL Server의 패치 및 업그레이드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="9cc1d-118">그러나 프런트 엔드 서버에서 모든 종류의 업그레이드 또는 패치를 수행 하는 경우에는 쿼럼 요구 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="9cc1d-119">자세한 내용은 [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) 및 [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9cc1d-120">Microsoft SQL Server 2012 Express (64 비트 버전)는 각 Standard Edition server 및 각 프런트 엔드 서버 서버의 Lync Server 2013에 의해 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="9cc1d-121">Lync Server 2013는 SQL Server의 32 비트 버전을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="9cc1d-122">64 비트 버전을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="9cc1d-123">SQL Server Web edition 및 SQL Server Workgroup edition은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="9cc1d-124">Lync Server 2013에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="9cc1d-125">Lync Server 2013는 네이티브 데이터베이스 미러링을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="9cc1d-126">모니터링 서버 역할을 사용 하려면 SQL Server Reporting Services를 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="9cc1d-127">프런트 엔드 풀에서 백 엔드 데이터베이스는 단일 SQL Server 컴퓨터 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9cc1d-128">다른 데이터베이스를 사용 하 여 Lync Server 데이터베이스를 collocate 경우 사용 가능성 및 성능에 영향을 줄 수 있는 모든 요소를 평가 하 고, 한 노드에 장애가 발생 하는 경우 나머지 노드가 로드를 처리할 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="9cc1d-129">장애 조치(failover) 기능을 확인하려면 모든 장애 조치(failover) 시나리오를 테스트하세요.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="9cc1d-130">SQL 미러링 및 SQL 클러스터링 사용</span><span class="sxs-lookup"><span data-stu-id="9cc1d-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="9cc1d-131">Lync Server 2013에서는 각 Lync Server 데이터베이스에 대해 SQL 미러링 또는 SQL 클러스터링 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="9cc1d-132">Lync Server 2013의 토폴로지 작성기 도구를 사용 하 여 SQL 미러링을 쉽게 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="9cc1d-133">SQL 장애 조치(failover) 클러스터링의 경우 설정을 위해 SQL Server를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="9cc1d-134">Lync Server 2013는 이전 버전의 Lync Server에서 업그레이드 한 greenfield 배포 및 조직을 비롯 하 여 모든 배포에 대해 SQL 미러링 및 SQL 클러스터링 토폴로지를 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="9cc1d-p111">SQL 클러스터링 지원은 능동/수동 구성을 위한 것으로, 성능을 위해 수동 노드는 다른 SQL 인스턴스와 공유하지 말아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-p111">SQL Clustering support is for an active/passive configuration. For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="9cc1d-137">다음과 같은 지원이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-137">The following support is included:</span></span>

  - <span data-ttu-id="9cc1d-138">다음을 위한 2개 노드 장애 조치(failover) 클러스터링:</span><span class="sxs-lookup"><span data-stu-id="9cc1d-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="9cc1d-p112">Microsoft SQL Server 2012 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-p112">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="9cc1d-p113">Microsoft SQL Server 2008 R2 Standard(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-p113">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="9cc1d-143">다음을 위한 최대 16개 노드 장애 조치(failover) 클러스터링:</span><span class="sxs-lookup"><span data-stu-id="9cc1d-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="9cc1d-p114">Microsoft SQL Server 2012 Enterprise(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-p114">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="9cc1d-p115">Microsoft SQL Server 2008 R2 Enterprise 데이터베이스 소프트웨어(64비트 버전). 최신 서비스 팩을 추가로 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-p115">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="9cc1d-148">SQL 미러링에 대 한 자세한 내용은 [Lync server 2013에서 백 엔드 서버의](lync-server-2013-back-end-server-high-availability.md)고가용성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="9cc1d-149">SQL 클러스터링을 배포 하는 방법에 대 한 자세한 내용은 [Lync server 2013에 대 한 Sql Server 클러스터링 구성을](lync-server-2013-configure-sql-server-clustering.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="9cc1d-150">SQL Server 2012의 장애 조치 (failover) 클러스터링에 대 한 자세한 내용 <http://technet.microsoft.com/en-us/library/hh231721.aspx>및 모범 사례를 보려면을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-150">For more information and best practices for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="9cc1d-151">SQL Server 2008의 장애 조치 (failover) <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>클러스터링에 대 한 자세한 내용은을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9cc1d-151">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

