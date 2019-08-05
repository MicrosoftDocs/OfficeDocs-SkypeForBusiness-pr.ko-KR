---
title: 영구 채팅 서버를 위한 고가용성 및 재해 복구 관리
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버의 고가용성 및 재해 복구를 관리 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: ff30bcdd99a4c92bd8fbd8f0a5c4bcedd8aa63b0
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "36197957"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="0bbfb-103">영구 채팅 서버를 위한 고가용성 및 재해 복구 관리</span><span class="sxs-lookup"><span data-stu-id="0bbfb-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0bbfb-104">**요약:** 비즈니스용 Skype 서버 2015에서 영구 채팅 서버의 고가용성 및 재해 복구를 관리 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0bbfb-105">이 항목에서는 영구 채팅 서버 장애 조치 및 실패 복구 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="0bbfb-106">이 항목을 읽기 전에 비즈니스용 [Skype server 2015의 영구 채팅 서버에 대 한 고가용성 및 재해 복구 계획](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) 을 읽고 [Skype의 영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성 해야 합니다. 비즈니스 서버 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)</span><span class="sxs-lookup"><span data-stu-id="0bbfb-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="0bbfb-107">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0bbfb-108">팀 에서도 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="0bbfb-109">자세한 내용은 [Microsoft 팀 업그레이드 시작](/microsoftteams/upgrade-start-here)을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="0bbfb-110">영구 채팅을 사용 해야 하는 경우에는이 기능이 필요한 사용자를 팀에 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용 하는 것이 선택 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="0bbfb-111">영구 채팅 서버 장애 조치</span><span class="sxs-lookup"><span data-stu-id="0bbfb-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="0bbfb-112">영구 채팅 서버에 대 한 장애 조치는 주로 수동 프로세스를 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="0bbfb-113">장애 조치 절차는 보조 데이터 센터가 실행 중이 고, 기본 영구 채팅 데이터베이스가 있는 영구 채팅 서버 서비스를 다음을 포함 하 여 완전히 사용할 수 없다는 가정을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="0bbfb-114">영구 채팅 서버 기본 데이터베이스와 영구 채팅 서버 미러 데이터베이스는 작동 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="0bbfb-115">비즈니스용 Skype Server 프런트 엔드 서버가 중단 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="0bbfb-116">절차는 두 가지 기본 단계를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="0bbfb-117">Mgc (기본 영구 채팅 데이터베이스)를 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="0bbfb-118">새 기본 데이터베이스에 대 한 미러링을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="0bbfb-119">영구 채팅 준수 데이터베이스 (mgccomp)는 장애 조치 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="0bbfb-120">이 데이터베이스의 콘텐츠는 임시 이며 준수 어댑터가 데이터를 처리 하므로 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="0bbfb-121">데이터 손실을 방지 하기 위해 어댑터 출력을 올바르게 관리 하는 것은 관리자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="0bbfb-122">영구 채팅 서버를 장애 조치할 때:</span><span class="sxs-lookup"><span data-stu-id="0bbfb-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="0bbfb-123">영구 채팅 서버 백업 로그 전달 데이터베이스에서 로그 전달을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="0bbfb-124">SQL Server Management Studio를 사용 하 여 영구 채팅 서버 백업 mgc 데이터베이스가 있는 데이터베이스 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="0bbfb-125">쿼리 창을 마스터 데이터베이스에 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="0bbfb-126">다음 명령을 사용 하 여 로그 전달을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-126">Use the following command to drop log shipping:</span></span>
    
   ```
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="0bbfb-127">백업 공유의 uncopied 백업 파일을 백업 서버의 복사 대상 폴더에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="0bbfb-128">적용 되지 않은 트랜잭션 로그 백업을 보조 데이터베이스에 차례로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="0bbfb-129">자세한 내용은 [방법: 트랜잭션 로그 백업 적용 (transact-sql)](https://go.microsoft.com/fwlink/p/?linkid=247428)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="0bbfb-130">백업 mgc 데이터베이스를 온라인 상태로 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-130">Bring the backup mgc database online.</span></span> <span data-ttu-id="0bbfb-131">1b 단계에서 열리는 쿼리 창을 사용 하 여 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-131">Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="0bbfb-132">Mgc 데이터베이스에 대 한 모든 연결 (있는 경우)을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="0bbfb-133">mgc 데이터베이스에 대 한 연결을 식별 하는 **exec sp_who2** .</span><span class="sxs-lookup"><span data-stu-id="0bbfb-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="0bbfb-134">\*\* \<spid\> 를 중단\*\* 하 여 이러한 연결을 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="0bbfb-135">데이터베이스를 온라인 상태로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="0bbfb-136">**복구로 데이터베이스 mgc를 복원**합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="0bbfb-137">비즈니스용 Skype Server Management Shell에서 명령 **집합-CsPersistentChatState "서비스: atl-cs-001.litwareinc.com"-PoolState FailedOver** 를 사용 하 여 mgc 백업 데이터베이스로 장애 조치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="0bbfb-138">Atl-cs-001.litwareinc.com에 대 한 영구 채팅 풀의 정규화 된 도메인 이름을 대체 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="0bbfb-139">Mgc 백업 데이터베이스는 이제 기본 데이터베이스로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="0bbfb-140">비즈니스용 Skype Server Management Shell에서 **CsMirrorDatabase** cmdlet을 사용 하 여 이제 기본 데이터베이스로 작동 하는 백업 데이터베이스에 대 한 고가용성 미러를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="0bbfb-141">백업 데이터베이스 인스턴스를 기본 데이터베이스로 사용 하 고, 미러 인스턴스로 백업 미러 데이터베이스 인스턴스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="0bbfb-142">이는 처음에 설치 하는 동안 기본 데이터베이스에 대해 구성 된 것과는 다른 미러와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="0bbfb-143">영구 채팅 서버 활성 서버를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="0bbfb-144">비즈니스용 Skype 서버 관리 셸에서 **CsPersistentChatActiveServer** cmdlet을 사용 하 여 활성 서버 목록을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0bbfb-145">모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 있거나 데이터베이스에 대 한 대기/고속 대역폭 연결이 낮은 데이터 센터에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="0bbfb-146">이 시점에서 영구 채팅 서버 기본 데이터베이스에서 영구 채팅 서버 백업 데이터베이스로 장애 조치 (failover)가 성공적으로 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="0bbfb-147">영구 채팅 서버 장애 복구</span><span class="sxs-lookup"><span data-stu-id="0bbfb-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="0bbfb-148">이 절차에서는 영구 채팅 서버 오류에서 복구 하 고 기본 데이터 센터에서 작업을 다시 설정 하는 데 필요한 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="0bbfb-149">영구 채팅 서버 장애가 발생 한 경우 기본 데이터 센터에서 중단 되 고 기본 및 미러 데이터베이스를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="0bbfb-150">주 데이터 센터가 백업 서버로 장애 조치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="0bbfb-151">다음 절차는 기본 데이터 센터를 백업한 후에 정상 작업을 복원 하 고 서버를 다시 작성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="0bbfb-152">이 절차에서는 기본 데이터 센터가 총 중단 으로부터 복구 되었고, mgc 데이터베이스와 mgccomp 데이터베이스가 토폴로지 작성기를 사용 하 여 다시 작성 되 고 다시 설치 되었다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="0bbfb-153">또한이 절차에서는 장애 조치 기간 동안 새 미러 및 백업 서버가 배포 되지 않은 것으로 가정 하 고 이전에는 영구 채팅 서버에서 장애 조치에 정의 된 것 처럼 백업 서버와 미러 서버만 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="0bbfb-154">이러한 단계는 재해가 발생 하기 이전에 구성을 복구 하도록 설계 되었으며, 결과적으로 주 서버에서 백업 서버로 장애 조치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="0bbfb-155">비즈니스용 Skype 서버 관리 셸에서 **CsPersistentChatActiveServer** cmdlet을 사용 하 여 영구 채팅 서버 활성 서버 목록에서 모든 서버를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="0bbfb-156">이렇게 하면 장애 복구 하는 동안 mgc 데이터베이스 및 mgccomp 데이터베이스에 연결 하는 모든 영구 채팅 서버가 중지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0bbfb-157">보조 영구 채팅 서버 백 엔드 서버의 SQL Server 에이전트는 특권 계정으로 실행 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="0bbfb-158">특히, 계정에는 다음이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="0bbfb-159">백업이 저장 되는 네트워크 공유에 대 한 읽기 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="0bbfb-160">백업을 복사할 특정 로컬 디렉터리에 대 한 쓰기 액세스입니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="0bbfb-161">Backup mgc 데이터베이스에서 미러링을 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="0bbfb-162">SQL Server Management Studio를 사용 하 여 backup mgc 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="0bbfb-163">Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**을 가리킨 다음 **미러**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="0bbfb-164">**미러링 제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="0bbfb-165">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="0bbfb-166">Mgccomp 데이터베이스에 대해 동일한 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="0bbfb-167">새 기본 데이터베이스로 복원할 수 있도록 mgc 데이터베이스를 백업 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="0bbfb-168">SQL Server Management Studio를 사용 하 여 backup mgc 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="0bbfb-169">Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**을 가리킨 다음 **백업을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-169">Right-click the mgc database, point to **Tasks**, and then click **Back Up**.</span></span> <span data-ttu-id="0bbfb-170">**데이터베이스 백업** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-170">The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="0bbfb-171">**백업 유형에**서 Full ( **전체**)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="0bbfb-172">**백업 구성 요소**를 보려면 **데이터베이스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="0bbfb-173">**이름**에 제시 된 기본 백업 집합 이름을 그대로 사용 하거나 백업 집합에 다른 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="0bbfb-174">\* \<선택\> 사항\*  **설명**에 백업 집합에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="0bbfb-175">대상 목록에서 기본 백업 위치를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="0bbfb-176">로그 전달을 위해 설정한 공유 위치의 경로를 사용 하 여 목록에 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-176">Add a file to the list by using the path to the share location that you established for log shipping.</span></span> <span data-ttu-id="0bbfb-177">이 경로는 기본 데이터베이스와 백업 데이터베이스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-177">This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="0bbfb-178">**확인** 을 클릭 하 여 대화 상자를 닫고 백업 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="0bbfb-179">이전 단계에서 만든 백업 데이터베이스를 사용 하 여 기본 데이터베이스를 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="0bbfb-180">SQL Server Management Studio를 사용 하 여 기본 mgc 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="0bbfb-181">Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 하 고 **작업**, **복원을**차례로 가리킨 다음 **데이터베이스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-181">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**.</span></span> <span data-ttu-id="0bbfb-182">**데이터베이스 복원** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-182">The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="0bbfb-183">**장치에서를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="0bbfb-184">찾아보기 단추를 클릭 하 여 **백업 지정** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-184">Click the browse button, which opens the **Specify Backup** dialog box.</span></span> <span data-ttu-id="0bbfb-185">**백업 미디어**에서 **파일**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-185">In **Backup media**, select **File**.</span></span> <span data-ttu-id="0bbfb-186">**추가**를 클릭 하 고 3 단계에서 만든 백업 파일을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-186">Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="0bbfb-187">**복원할 백업 세트 선택**에서 백업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="0bbfb-188">**페이지 선택** 창에서 **옵션** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="0bbfb-189">**복원 옵션**에서 **기존 데이터베이스 덮어쓰기를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="0bbfb-190">**복구 상태**에서 **데이터베이스를 사용할 준비가 된 상태로 둡니다**.를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="0bbfb-191">**확인** 을 클릭 하 여 복원 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="0bbfb-192">기본 데이터베이스에 대 한 SQL Server 로그 전달을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="0bbfb-193">[비즈니스용 Skype server 2015의 영구 채팅 서버에 대해 고가용성 및 재해 복구 구성](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) 절차를 따라 기본 mgc 데이터베이스에 대 한 로그 전달을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="0bbfb-194">영구 채팅 서버 활성 서버를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="0bbfb-195">비즈니스용 Skype 서버 관리 셸에서 **CsPersistentChatActiveServer** cmdlet을 사용 하 여 활성 서버 목록을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0bbfb-196">모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 있거나 데이터베이스에 대 한 대기/고속 대역폭 연결이 낮은 데이터 센터에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="0bbfb-197">풀을 정상 상태로 복원 하려면 다음 Windows PowerShell 명령을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="0bbfb-198">자세한 내용은 [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet에 대 한 도움말 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bbfb-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

