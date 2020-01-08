---
title: 'Lync Server 2013: 영구 채팅 서버 장애 조치(failover)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 021b34cafd91397cc36da1dbc22f91b8665aea96
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="5e96d-102">Lync Server 2013에서 영구 채팅 서버 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="5e96d-102">Failing over Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e96d-103">_**마지막으로 수정한 주제:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="5e96d-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="5e96d-104">영구 채팅 서버에 대 한 장애 조치는 주로 수동 프로세스를 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-104">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="5e96d-105">장애 조치 절차는 보조 데이터 센터가 실행 중이 고, 기본 영구 채팅 데이터베이스가 있는 영구 채팅 서버 서비스를 다음을 포함 하 여 완전히 사용할 수 없다는 가정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-105">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="5e96d-106">영구 채팅 서버 기본 데이터베이스와 영구 채팅 서버 미러 데이터베이스는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-106">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="5e96d-107">Lync Server 프런트 엔드 서버가 작동 중지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-107">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="5e96d-108">절차는 두 가지 기본 단계를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-108">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="5e96d-109">Mgc (기본 영구 채팅 데이터베이스)를 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-109">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="5e96d-110">새 기본 데이터베이스에 대 한 미러링을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-110">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="5e96d-111">영구 채팅 준수 데이터베이스 (mgccomp)는 장애 조치 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-111">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="5e96d-112">이 데이터베이스의 콘텐츠는 임시 이며 준수 어댑터가 데이터를 처리 하므로 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-112">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="5e96d-113">데이터 손실을 방지 하기 위해 어댑터 출력을 올바르게 관리 하는 것은 관리자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-113">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="5e96d-114">영구 채팅 서버를 장애 조치할 때</span><span class="sxs-lookup"><span data-stu-id="5e96d-114">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="5e96d-115">영구 채팅 서버 백업 로그 전달 데이터베이스에서 로그 전달을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-115">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="5e96d-116">SQL Server Management Studio를 사용 하 여 영구 채팅 서버 백업 mgc 데이터베이스가 있는 데이터베이스 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-116">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="5e96d-117">쿼리 창을 마스터 데이터베이스에 엽니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-117">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="5e96d-118">다음 명령을 사용 하 여 로그 전달을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-118">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="5e96d-119">백업 공유의 uncopied 백업 파일을 백업 서버의 복사 대상 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-119">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="5e96d-120">적용 되지 않은 트랜잭션 로그 백업을 보조 데이터베이스에 차례로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-120">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="5e96d-121">자세한 내용은에서 http://go.microsoft.com/fwlink/p/?linkid=247428"방법: 트랜잭션 로그 백업 (Transact-sql) 적용"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e96d-121">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at http://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="5e96d-122">백업 mgc 데이터베이스를 온라인 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-122">Bring the backup mgc database online.</span></span> <span data-ttu-id="5e96d-123">1b 단계에서 열리는 쿼리 창을 사용 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-123">Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="5e96d-124">Mgc 데이터베이스에 대 한 모든 연결 (있는 경우)을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-124">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="5e96d-125">mgc 데이터베이스에 대 한 연결을 식별 하는 **exec sp\_who2** .</span><span class="sxs-lookup"><span data-stu-id="5e96d-125">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="5e96d-126">\*\* \<spid\> 를 중단\*\* 하 여 이러한 연결을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-126">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="5e96d-127">데이터베이스를 온라인 상태로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-127">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="5e96d-128">**복구로 데이터베이스 mgc를 복원**합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-128">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="5e96d-129">Lync Server 관리 셸에서는 명령 **집합-CsPersistentChatState-id "서비스: atl-cs-001.litwareinc.com" – PoolState FailedOver** 를 사용 하 여 mgc 백업 데이터베이스로 장애 조치 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e96d-129">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="5e96d-130">Atl-cs-001.litwareinc.com에 대 한 영구 채팅 풀의 정규화 된 도메인 이름을 대체 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e96d-130">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="5e96d-131">Mgc 백업 데이터베이스는 이제 기본 데이터베이스로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-131">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="5e96d-132">Lync Server 관리 셸에서 **CsMirrorDatabase** cmdlet을 사용 하 여 이제 기본 데이터베이스로 작동 하는 백업 데이터베이스에 대해 고가용성 미러를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-132">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="5e96d-133">백업 데이터베이스 인스턴스를 기본 데이터베이스로 사용 하 고, 미러 인스턴스로 백업 미러 데이터베이스 인스턴스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-133">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="5e96d-134">이는 처음에 설치 하는 동안 기본 데이터베이스에 대해 구성 된 것과는 다른 미러와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-134">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="5e96d-135">자세한 내용은 [lync server 2013에서 백 엔드 서버의 SQL 미러링 배포](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)에서 "Lync Server Management Shell cmdlet 사용" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5e96d-135">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="5e96d-136">영구 채팅 서버 활성 서버를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-136">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="5e96d-137">Lync Server 명령 셸에서 **set-CsPersistentChatActiveServer** cmdlet을 사용 하 여 활성 서버 목록을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-137">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="5e96d-138">모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 있거나 데이터베이스에 대 한 대기/고속 대역폭 연결이 낮은 데이터 센터에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-138">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="5e96d-139">이 시점에서 영구 채팅 서버 기본 데이터베이스에서 영구 채팅 서버 백업 데이터베이스로 장애 조치 (failover)가 성공적으로 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e96d-139">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

