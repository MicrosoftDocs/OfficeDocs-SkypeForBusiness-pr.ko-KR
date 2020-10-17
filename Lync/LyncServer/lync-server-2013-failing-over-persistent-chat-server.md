---
title: 'Lync Server 2013: 영구 채팅 서버 장애 조치 (failover)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over Persistent Chat Server
ms:assetid: 2cd79ffd-fee6-44ce-96cf-b98bf25e2690
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204772(v=OCS.15)
ms:contentKeyID: 48183726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ede95ad504244fc5a97d62a074192a5270fbcdef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530945"
---
# <a name="failing-over-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="84772-102">Lync Server 2013의 영구 채팅 서버 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="84772-102">Failing over Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84772-103">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="84772-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="84772-104">영구 채팅 서버에 대 한 장애 조치 (Failover)는 주로 수동 프로세스를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="84772-104">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>

<span data-ttu-id="84772-105">장애 조치 (failover) 절차는 보조 데이터 센터가 실행 중이 고 기본 영구 채팅 데이터베이스가 있는 영구 채팅 서버 서비스를 사용 하 여 다음을 포함 하는 것을 완전히 사용할 수 없다는 가정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-105">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>

  - <span data-ttu-id="84772-106">영구 채팅 서버 기본 데이터베이스 및 영구 채팅 서버 미러 데이터베이스의 작동이 중지 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="84772-106">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>

  - <span data-ttu-id="84772-107">Lync Server 프런트 엔드 서버가 다운 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="84772-107">Lync Server Front End Server is down.</span></span>

<span data-ttu-id="84772-108">이 절차는 다음과 같은 두 기본 단계를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-108">The procedure is based on two basic steps:</span></span>

  - <span data-ttu-id="84772-109">기본 영구 채팅 데이터베이스 (mgc)를 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-109">Recover the primary Persistent Chat database (mgc).</span></span>

  - <span data-ttu-id="84772-110">새 주 데이터베이스에 대해 미러링을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-110">Establish mirroring for the new primary database.</span></span>

<span data-ttu-id="84772-111">영구 채팅 준수 데이터베이스 (mgccomp)가 장애 조치 (failover) 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="84772-111">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="84772-112">이 데이터베이스의 콘텐츠는 일시적인 항목이며 준수 어댑터가 데이터를 처리하면 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="84772-112">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="84772-113">데이터 손실을 방지 하기 위해 어댑터 출력을 올바르게 관리 하는 것은 영구 채팅 관리자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="84772-113">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>

<div>

## <a name="to-fail-over-persistent-chat-server"></a><span data-ttu-id="84772-114">영구 채팅 서버를 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="84772-114">To fail over Persistent Chat Server</span></span>

1.  <span data-ttu-id="84772-115">영구 채팅 서버 백업 로그 전달 데이터베이스에서 로그 전달을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-115">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
    1.  <span data-ttu-id="84772-116">SQL Server Management Studio를 사용 하 여 영구 채팅 서버 백업 mgc 데이터베이스가 있는 데이터베이스 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-116">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
    2.  <span data-ttu-id="84772-117">마스터 데이터베이스에 대한 쿼리 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="84772-117">Open a query window to the master database.</span></span>
    
    3.  <span data-ttu-id="84772-118">다음 명령을 사용하여 로그 전달을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-118">Use the following command to drop log shipping:</span></span>
        
            exec sp_delete_log_shipping_secondary_database mgc

2.  <span data-ttu-id="84772-119">복사되지 않은 백업 파일을 백업 공유에서 백업 서버의 복사 대상 폴더로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-119">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>

3.  <span data-ttu-id="84772-120">시퀀스에서 적용되지 않은 트랜잭션 로그 백업을 보조 데이터베이스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-120">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="84772-121">자세한 내용은 "How to: Transaction Log Backup (Transact-sql) 적용"을 참조 하십시오 https://go.microsoft.com/fwlink/p/?linkid=247428 .</span><span class="sxs-lookup"><span data-stu-id="84772-121">For details, see "How to: Apply a Transaction Log Backup (Transact-SQL)" at https://go.microsoft.com/fwlink/p/?linkid=247428.</span></span>

4.  <span data-ttu-id="84772-p103">백업 mgc 데이터베이스를 온라인 상태로 설정합니다. 1b단계에서 연 쿼리 창을 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-p103">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
    1.  <span data-ttu-id="84772-124">mgc 데이터베이스에 대한 연결이 있는 경우 모두 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-124">End all connections to the mgc database, if there are any:</span></span>
        
        1.  <span data-ttu-id="84772-125">**exec sp \_ who2** -mgc 데이터베이스에 대 한 연결을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-125">**exec sp\_who2** to identify connections to the mgc database.</span></span>
        
        2.  <span data-ttu-id="84772-126">\*\*kill \<spid\> \*\* 연결을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-126">**kill \<spid\>** to end these connections.</span></span>
    
    2.  <span data-ttu-id="84772-127">데이터베이스를 온라인 상태로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-127">Bring the database online:</span></span>
        
        1.  <span data-ttu-id="84772-128">**recovery를 사용 하 여 데이터베이스 mgc를 복원**합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-128">**restore database mgc with recovery**.</span></span>

5.  <span data-ttu-id="84772-129">Lync Server 관리 셸에서 명령 **집합-set-cspersistentchatstate-Identity "service: atl-001.litwareinc.com" – PoolState FailedOver** 를 사용 하 여 mgc 백업 데이터베이스로 장애 조치 (failover) 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-129">In Lync Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" –PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="84772-130">영구 채팅 풀의 fqdn (정규화 된 도메인 이름)을 atl-cs-001.litwareinc.com로 대체 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-130">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="84772-131">이제 mgc 백업 데이터베이스가 주 데이터베이스로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84772-131">The mgc backup database now serves as the primary database.</span></span>

6.  <span data-ttu-id="84772-132">Lync Server 관리 셸에서 **CsMirrorDatabase** cmdlet을 사용 하 여 이제 기본 데이터베이스로 사용 되는 백업 데이터베이스에 대 한 고가용성 미러를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-132">In Lync Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="84772-133">백업 데이터베이스 인스턴스를 주 데이터베이스로, 백업 미러 데이터베이스 인스턴스를 미러 인스턴스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-133">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="84772-134">이 미러는 설치 중에 주 데이터베이스에 대해 처음 구성한 미러와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="84772-134">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span> <span data-ttu-id="84772-135">자세한 내용은 [Lync server 2013에서 백 엔드 서버 고가용성을 위해 SQL 미러링 배포](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md)의 "Lync Server 관리 셸 cmdlet 사용" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="84772-135">For details, see the section "Using Lync Server Management Shell Cmdlets" in [Deploying SQL mirroring for Back End Server high availability in Lync Server 2013](lync-server-2013-deploying-sql-mirroring-for-back-end-server-high-availability.md).</span></span>

7.  <span data-ttu-id="84772-136">영구 채팅 서버 활성 서버를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-136">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="84772-137">Lync Server 명령 셸에서 **set-cspersistentchatactiveserver** cmdlet을 사용 하 여 활성 서버 목록을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-137">From the Lync Server Command Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="84772-138">모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 배치하거나 데이터베이스에 대한 연결 대기 시간이 낮고 대역폭이 높은 데이터 센터에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84772-138">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span>

    
    </div>
    
    <span data-ttu-id="84772-139">이때 영구 채팅 서버 기본 데이터베이스에서 영구 채팅 서버 백업 데이터베이스로 장애 조치 (failover)가 정상적으로 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="84772-139">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

