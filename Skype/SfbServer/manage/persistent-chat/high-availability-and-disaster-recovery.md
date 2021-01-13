---
title: 영구 채팅 서버의 고가용성 및 재해 복구 관리
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4346e70b-ac48-4ab9-853e-3cdd6dcfe678
description: '요약: 비즈니스용 Skype 서버 2015에서 영구 채팅 서버 고가용성 및 재해 복구를 관리하는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 7ec7182d8fe2866499f731b43df712a69c44bc42
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815048"
---
# <a name="manage-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="eb543-103">영구 채팅 서버의 고가용성 및 재해 복구 관리</span><span class="sxs-lookup"><span data-stu-id="eb543-103">Manage high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="eb543-104">**요약:** 영구 채팅 서버 고가용성 및 재해 복구를 관리하는 방법을 비즈니스용 Skype 서버 2015에서 자세히 알아보고,</span><span class="sxs-lookup"><span data-stu-id="eb543-104">**Summary:** Learn how to manage Persistent Chat Server high availability and disaster recovery in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="eb543-105">이 항목에서는 영구 채팅 서버를 장애 조치(fail back) 및 장애 조치(fail back)하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-105">This topic describes how to fail over and fail back Persistent Chat Server.</span></span> <span data-ttu-id="eb543-106">이 항목을 읽기 전에 비즈니스용 Skype 서버 [2015에서](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) 영구 채팅 서버에 대한 고가용성 및 재해 복구 계획을 읽고 비즈니스용 Skype 서버 [2015에서](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-106">Before reading this topic, be sure to read [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md) and [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span>

> [!NOTE]
> <span data-ttu-id="eb543-107">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="eb543-108">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="eb543-109">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="eb543-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="eb543-110">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="fail-over-persistent-chat-server"></a><span data-ttu-id="eb543-111">영구 채팅 서버 장애 조치(fail over)</span><span class="sxs-lookup"><span data-stu-id="eb543-111">Fail over Persistent Chat Server</span></span>

<span data-ttu-id="eb543-112">영구 채팅 서버에 대한 장애 조치(failover)는 주로 수동 프로세스로 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-112">Failover for Persistent Chat Server is designed to be mainly a manual process.</span></span>
  
<span data-ttu-id="eb543-113">장애 조치(failover) 절차는 보조 데이터 센터가 실행 중이지만 다음을 포함하여 기본 영구 채팅 데이터베이스가 있는 영구 채팅 서버 서비스를 완전히 사용할 수 없다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-113">The failover procedure is based on the assumption that the secondary data center is up and running, but the Persistent Chat Server services where the primary Persistent Chat database is located are completely unavailable, including the following:</span></span>
  
- <span data-ttu-id="eb543-114">영구 채팅 서버 기본 데이터베이스 및 영구 채팅 서버 미러 데이터베이스가 다운되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-114">Persistent Chat Server primary database and Persistent Chat Server mirror database are down.</span></span>
    
- <span data-ttu-id="eb543-115">비즈니스용 Skype 서버 프런트 엔드 서버가 다운됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-115">Skype for Business Server Front End Server is down.</span></span>
    
<span data-ttu-id="eb543-116">이 절차는 다음과 같은 두 기본 단계를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-116">The procedure is based on two basic steps:</span></span>
  
- <span data-ttu-id="eb543-117">기본 영구 채팅 데이터베이스(mgc)를 복구합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-117">Recover the primary Persistent Chat database (mgc).</span></span>
    
- <span data-ttu-id="eb543-118">새 주 데이터베이스에 대해 미러링을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-118">Establish mirroring for the new primary database.</span></span>
    
<span data-ttu-id="eb543-119">영구 채팅 준수 데이터베이스(mgccomp)는 실패하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-119">The Persistent Chat compliance database (mgccomp) is not failed over.</span></span> <span data-ttu-id="eb543-120">이 데이터베이스의 콘텐츠는 일시적인 항목이며 준수 어댑터가 데이터를 처리하면 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-120">The contents of this database are transient and are purged as the compliance adapter processes the data.</span></span> <span data-ttu-id="eb543-121">데이터 손실을 방지하기 위해 어댑터 출력을 올바르게 관리하는 것은 영구 채팅 관리자로서의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-121">It is your responsibility, as Persistent Chat Administrator, to correctly manage the adapter output to avoid data loss.</span></span>
  
<span data-ttu-id="eb543-122">영구 채팅 서버를 장애 조치(fail over)를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-122">To fail over Persistent Chat Server:</span></span>
  
1. <span data-ttu-id="eb543-123">영구 채팅 서버 백업 로그 전달 데이터베이스에서 로그 전달을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-123">Remove log shipping from the Persistent Chat Server Backup Log Shipping database.</span></span>
    
   - <span data-ttu-id="eb543-124">이 SQL Server Management Studio 영구 채팅 서버 백업 mgc 데이터베이스가 있는 데이터베이스 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-124">Using SQL Server Management Studio, connect to the database instance where the Persistent Chat Server backup mgc database is located.</span></span>
    
   - <span data-ttu-id="eb543-125">마스터 데이터베이스에 대한 쿼리 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-125">Open a query window to the master database.</span></span>
    
   - <span data-ttu-id="eb543-126">다음 명령을 사용하여 로그 전달을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-126">Use the following command to drop log shipping:</span></span>
    
   ```SQL
   exec sp_delete_log_shipping_secondary_database mgc
   ```

2. <span data-ttu-id="eb543-127">복사되지 않은 백업 파일을 백업 공유에서 백업 서버의 복사 대상 폴더로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-127">Copy any uncopied backup files from the backup share to the copy destination folder of the backup server.</span></span>
    
3. <span data-ttu-id="eb543-128">시퀀스에서 적용되지 않은 트랜잭션 로그 백업을 보조 데이터베이스에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-128">Apply any unapplied transaction log backups in sequence to the secondary database.</span></span> <span data-ttu-id="eb543-129">자세한 내용은 [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span><span class="sxs-lookup"><span data-stu-id="eb543-129">For details, see [How to: Apply a Transaction Log Backup (Transact-SQL)](https://go.microsoft.com/fwlink/p/?linkid=247428).</span></span>
    
4. <span data-ttu-id="eb543-p105">백업 mgc 데이터베이스를 온라인 상태로 설정합니다. 1b단계에서 연 쿼리 창을 사용하여 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-p105">Bring the backup mgc database online. Using the query window that opens in step 1b, do the following:</span></span>
    
   - <span data-ttu-id="eb543-132">mgc 데이터베이스에 대한 연결이 있는 경우 모두 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-132">End all connections to the mgc database, if there are any:</span></span>
    
   - <span data-ttu-id="eb543-133">**exec sp_who2** mgc 데이터베이스에 대한 연결을 식별하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-133">**exec sp_who2** to identify connections to the mgc database.</span></span>
    
   - <span data-ttu-id="eb543-134">**kill \<spid\>** 을 사용하여 이러한 연결을 끝내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-134">**kill \<spid\>** to end these connections.</span></span>
    
   - <span data-ttu-id="eb543-135">데이터베이스를 온라인 상태로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-135">Bring the database online:</span></span>
    
   - <span data-ttu-id="eb543-136">**복구를 통해 데이터베이스 mgc를 복원합니다.**</span><span class="sxs-lookup"><span data-stu-id="eb543-136">**restore database mgc with recovery**.</span></span>
    
5. <span data-ttu-id="eb543-137">비즈니스용 Skype 서버 관리 셸에서 **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** 명령을 사용하여 mgc 백업 데이터베이스로 장애 조치(failover)합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-137">In Skype for Business Server Management Shell, use the command **Set-CsPersistentChatState -Identity "service:atl-cs-001.litwareinc.com" -PoolState FailedOver** to fail over to the mgc backup database.</span></span> <span data-ttu-id="eb543-138">영구 채팅 풀의 정식 도메인 이름을 영구 채팅 풀로 대체해야 atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="eb543-138">Be sure to substitute the fully qualified domain name of your Persistent Chat pool for atl-cs-001.litwareinc.com.</span></span>
    
    <span data-ttu-id="eb543-139">이제 mgc 백업 데이터베이스가 주 데이터베이스로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-139">The mgc backup database now serves as the primary database.</span></span>
    
6. <span data-ttu-id="eb543-140">비즈니스용 Skype 서버 관리 셸에서 **Install-CsMirrorDatabase** cmdlet을 사용하여 현재 기본 데이터베이스 역할을 하는 백업 데이터베이스에 대한 고가용성 미러를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-140">In Skype for Business Server Management Shell, use the **Install-CsMirrorDatabase** cmdlet to establish a high availability mirror for the backup database that now serves as the primary database.</span></span> <span data-ttu-id="eb543-141">백업 데이터베이스 인스턴스를 주 데이터베이스로, 백업 미러 데이터베이스 인스턴스를 미러 인스턴스로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-141">Use the backup database instance as the primary database and the backup mirror database instance as the mirror instance.</span></span> <span data-ttu-id="eb543-142">이 미러는 설치 중에 주 데이터베이스에 대해 처음 구성한 미러와는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-142">This is not the same mirror as the one that was initially configured for the primary database during setup.</span></span>
    
7. <span data-ttu-id="eb543-143">영구 채팅 서버 활성 서버를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="eb543-143">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="eb543-144">비즈니스용 Skype 서버 관리 셸에서 **Set-CsPersistentChatActiveServer** cmdlet을 사용하여 활성 서버 목록을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-144">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="eb543-145">모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 배치하거나 데이터베이스에 대한 연결 대기 시간이 낮고 대역폭이 높은 데이터 센터에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-145">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
    <span data-ttu-id="eb543-146">이때 영구 채팅 서버 기본 데이터베이스에서 영구 채팅 서버 백업 데이터베이스로의 장애 조치(failover)가 성공적으로 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-146">At this point, the failover from the Persistent Chat Server primary database to the Persistent Chat Server backup database completes successfully.</span></span>
    
## <a name="fail-back-persistent-chat-server"></a><span data-ttu-id="eb543-147">영구 채팅 서버 장애 조치(fail back)</span><span class="sxs-lookup"><span data-stu-id="eb543-147">Fail back Persistent Chat Server</span></span>

<span data-ttu-id="eb543-148">이 절차에서는 영구 채팅 서버 오류로부터 복구하고 기본 데이터 센터에서 작업을 다시 설정하는 데 필요한 단계를 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-148">This procedure outlines the steps necessary to recover from a Persistent Chat Server failure, and to reestablish operations from the primary data center.</span></span>
  
<span data-ttu-id="eb543-149">영구 채팅 서버 오류가 발생하면 기본 데이터 센터에서 전체 중단이 발생하고 기본 및 미러 데이터베이스를 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-149">During Persistent Chat Server failure, the primary data center suffers complete outage, and the primary and mirror databases become unavailable.</span></span> <span data-ttu-id="eb543-150">기본 데이터 센터는 백업 서버로 장애 조치(failover)됩니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-150">The primary data center fails over to the backup server.</span></span>
  
<span data-ttu-id="eb543-151">다음 절차에서는 기본 데이터 센터가 백업되고 서버를 다시 구축한 후에 일반 작업을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-151">The following procedure restores normal operation after the primary data center is back up, and the servers have been rebuilt.</span></span> <span data-ttu-id="eb543-152">이 절차에서는 기본 데이터 센터가 총 정전으로부터 복구되고, 토폴로지 작성기에서 mgc 데이터베이스와 mgccomp 데이터베이스를 다시 구축하고 다시 설치했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-152">The procedure assumes that the primary data center has been recovered from total outage, and that the mgc database and the mgccomp database have been rebuilt and reinstalled by using Topology Builder.</span></span>
  
<span data-ttu-id="eb543-153">또한 이 절차에서는 장애 조치 기간 동안 새 미러 및 백업 서버가 배포되지 않은 것으로 가정하고 이전에 영구 채팅 서버 장애 조치(Failover)에 정의된 백업 서버와 해당 미러 서버만 배포된 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-153">The procedure also assumes that no new mirror and backup servers were deployed during the failover period, and that the only server deployed is the backup server and its mirror server, as defined in Fail over Persistent Chat Server previously.</span></span>
  
<span data-ttu-id="eb543-154">이러한 단계는 구성을 재해 이전의 상태로 복구하여 기본 서버를 백업 서버로 장애 조치(failover)하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-154">These steps are designed to recover configuration as it existed prior to the disaster, resulting in failover from the primary server to the backup server.</span></span>
  
1. <span data-ttu-id="eb543-155">비즈니스용 Skype 서버 관리 셸에서 **Set-CsPersistentChatActiveServer** cmdlet을 사용하여 영구 채팅 서버 Active Server 목록에서 모든 서버를 지우는 방법을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-155">Clear all servers from the Persistent Chat Server Active Server list by using the **Set-CsPersistentChatActiveServer** cmdlet from the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="eb543-156">이렇게 하여 장애 조치(failback) 중에 모든 영구 채팅 서버가 mgc 데이터베이스 및 mgccomp 데이터베이스에 연결할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-156">This stops all Persistent Chat Servers from connecting to the mgc database and the mgccomp database during failback.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="eb543-157">보조 SQL Server 채팅 서버 백 엔드 서버의 사용자 에이전트는 권한 있는 계정으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-157">The SQL Server agent on the secondary Persistent Chat Server Back End Server should be running under a privileged account.</span></span> <span data-ttu-id="eb543-158">특히 이 계정은 다음과 같은 권한을 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-158">Specifically, the account must include:</span></span> 
  
   - <span data-ttu-id="eb543-159">백업을 배치 중인 네트워크 공유에 대한 읽기 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="eb543-159">Read access to the network share that backups are being placed in.</span></span>
    
   - <span data-ttu-id="eb543-160">백업을 복사 중인 특정 로컬 디렉터리에 대한 쓰기 액세스 권한</span><span class="sxs-lookup"><span data-stu-id="eb543-160">Write access to the specific local directory that the backups are being copied to.</span></span>
    
2. <span data-ttu-id="eb543-161">백업 mgc 데이터베이스에서 미러링 해제:</span><span class="sxs-lookup"><span data-stu-id="eb543-161">Disable mirroring on the backup mgc database:</span></span>
    
   - <span data-ttu-id="eb543-162">SQL Server Management Studio 사용하여 백업 mgc 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-162">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="eb543-163">mgc 데이터베이스를 마우스 오른쪽 단추로 클릭하고 **작업** 을 가리킨 후 **미러** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-163">Right-click the mgc database, point to **Tasks**, and then click **Mirror**.</span></span>
    
   - <span data-ttu-id="eb543-164">**미러링 제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-164">Click **Remove Mirroring**.</span></span>
    
   - <span data-ttu-id="eb543-165">**확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-165">Click **OK**.</span></span>
    
   - <span data-ttu-id="eb543-166">mgccomp 데이터베이스에서도 같은 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-166">Perform the same steps with the mgccomp database.</span></span>
    
3. <span data-ttu-id="eb543-167">새 기본 데이터베이스로 복원할 수 있도록 mgc 데이터베이스를 백업합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-167">Back up the mgc database so that it can be restored to the new primary database:</span></span>
    
   - <span data-ttu-id="eb543-168">SQL Server Management Studio 사용하여 백업 mgc 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-168">Using SQL Server Management Studio, connect to the backup mgc instance.</span></span>
    
   - <span data-ttu-id="eb543-p113">mgc 데이터베이스를 마우스 오른쪽 단추로 클릭하고 **작업** 을 가리킨 후 **백업** 을 클릭합니다. **데이터베이스 백업** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-p113">Right-click the mgc database, point to **Tasks**, and then click **Back Up**. The **Back Up Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="eb543-171">**백업 유형** 에서 **전체** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-171">In **Backup type**, select **Full**.</span></span>
    
   - <span data-ttu-id="eb543-172">**백업 구성 요소** 에 대해 **데이터베이스** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-172">For **Backup component**, click **Database**.</span></span>
    
   - <span data-ttu-id="eb543-173">**이름** 에 제안된 기본 백업 집합 이름을 사용하거나 백업 집합에 대해 다른 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-173">Either accept the default backup set name suggested in **Name**, or enter a different name for the backup set.</span></span>
    
   -  <span data-ttu-id="eb543-174">*\<Optional\>\*\*\*설명에서*\* 백업 세트에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-174">*\<Optional\>*  In **Description**, enter a description of the backup set.</span></span>
    
   - <span data-ttu-id="eb543-175">대상 목록에서 기본 백업 위치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-175">Remove the default backup location from the destination list.</span></span>
    
   - <span data-ttu-id="eb543-p114">로그 전달을 위해 설정한 공유 위치에 대한 경로를 사용해서 목록에 파일을 추가합니다. 이 경로는 기본 데이터베이스 및 백업 데이터베이스 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-p114">Add a file to the list by using the path to the share location that you established for log shipping. This path is available to the primary database and to the backup database.</span></span>
    
   - <span data-ttu-id="eb543-178">**확인** 을 클릭하여 대화 상자를 닫고 백업 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-178">Click **OK** to close the dialog box and begin the backup process.</span></span>
    
4. <span data-ttu-id="eb543-179">이전 단계에서 만든 백업 데이터베이스를 사용하여 기본 데이터베이스를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-179">Restore the primary database by using the backup database created in the previous step.</span></span>
    
   - <span data-ttu-id="eb543-180">이 SQL Server Management Studio 기본 mgc 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-180">Using SQL Server Management Studio, connect to the primary mgc instance.</span></span>
    
   - <span data-ttu-id="eb543-p115">mgc 데이터베이스를 마우스 오른쪽 단추로 클릭하고 **작업**, **복원** 을 차례로 클릭한 후 **데이터베이스** 를 클릭합니다. **데이터베이스 복원** 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-p115">Right-click the mgc database, point to **Tasks**, point to **Restore**, and then click **Database**. The **Restore Database** dialog box appears.</span></span>
    
   - <span data-ttu-id="eb543-183">**장치에서** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-183">Select **From Device**.</span></span>
    
   - <span data-ttu-id="eb543-p116">찾아보기 단추를 클릭하여 **백업 지정** 대화 상자를 엽니다. **백업 미디어** 에서 **파일** 을 선택합니다. **추가** 를 클릭하고 3단계에서 만든 백업 파일을 선택한 후 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-p116">Click the browse button, which opens the **Specify Backup** dialog box. In **Backup media**, select **File**. Click **Add**, select the backup file that you created in step 3, and then click **OK**.</span></span>
    
   - <span data-ttu-id="eb543-187">**복원할 백업 집합 선택** 에서 백업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-187">In **Select the backup sets to restore**, select the backup.</span></span>
    
   - <span data-ttu-id="eb543-188">**페이지 선택** 창에서 **옵션** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-188">Click **Options** in the **Select a page** pane.</span></span>
    
   - <span data-ttu-id="eb543-189">**복원 옵션** 에서 **기존 데이터베이스 덮어쓰기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-189">In **Restore options**, select **Overwrite the existing database**.</span></span>
    
   - <span data-ttu-id="eb543-190">**복구 상태** 에서 **데이터베이스를 사용할 수 있는 상태로 유지합니다.** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-190">In **Recovery State**, select **Leave the database ready to use**.</span></span>
    
   - <span data-ttu-id="eb543-191">**확인** 을 클릭하여 복원 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-191">Click **OK** to begin the restoration process.</span></span>
    
5. <span data-ttu-id="eb543-192">기본 SQL Server 로그 전달을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-192">Configure SQL Server Log Shipping for the primary database.</span></span> <span data-ttu-id="eb543-193">비즈니스용 Skype 서버 [2015에서](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) 영구 채팅 서버에 대해 고가용성 및 재해 복구 구성의 절차에 따라 기본 mgc 데이터베이스에 대한 로그 전달을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-193">Follow the procedures in [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md) to establish log shipping for the primary mgc database.</span></span>
    
6. <span data-ttu-id="eb543-194">영구 채팅 서버 활성 서버를 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="eb543-194">Set the Persistent Chat Server active servers.</span></span> <span data-ttu-id="eb543-195">비즈니스용 Skype 서버 관리 셸에서 **Set-CsPersistentChatActiveServer** cmdlet을 사용하여 활성 서버 목록을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-195">From the Skype for Business Server Management Shell, use the **Set-CsPersistentChatActiveServer** cmdlet to set the list of active servers.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="eb543-196">모든 활성 서버는 새 기본 데이터베이스와 동일한 데이터 센터 내에 배치하거나 데이터베이스에 대한 연결 대기 시간이 낮고 대역폭이 높은 데이터 센터에 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-196">All the active servers must be located within the same data center as the new primary database, or in a data center that has a low latency/high bandwidth connection to the database.</span></span> 
  
<span data-ttu-id="eb543-197">풀을 정상 상태로 복원하기 위해 다음 Windows PowerShell 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eb543-197">To restore the pool to its normal state run the following Windows PowerShell command:</span></span>
  
```PowerShell
Set-CsPersistentChatState -Identity "service: lyncpc.dci.discovery.com" -PoolState Normal
```

<span data-ttu-id="eb543-198">자세한 내용은 [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="eb543-198">For more information, see the help topic for the [Set-CsPersistentChatState](https://docs.microsoft.com/powershell/module/skype/set-cspersistentchatstate?view=skype-ps) cmdlet.</span></span>
  

