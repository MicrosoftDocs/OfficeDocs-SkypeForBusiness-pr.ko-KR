---
title: 영구 채팅 서버를 위한 고가용성 및 재해 복구 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: '요약: 비즈니스용 Skype Server 2015에서 영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성 하는 방법을 알아보려면이 항목을 참조 하세요.'
ms.openlocfilehash: a771479eccc88c6ff30864a44649fe3d309a7ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196974"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="b438f-103">영구 채팅 서버를 위한 고가용성 및 재해 복구 구성</span><span class="sxs-lookup"><span data-stu-id="b438f-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b438f-104">**요약:** 이 항목에서는 비즈니스용 Skype 서버 2015에서 영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b438f-105">비즈니스용 Skype 서버는 데이터베이스 미러링을 포함 하 여 백 엔드 서버에 대 한 여러 가지 고가용성 모드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="b438f-106">자세한 내용은 비즈니스용 [Skype 서버 2015의 고가용성 및 재해 복구 계획](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b438f-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b438f-107">AlwaysOn 가용성 그룹은 영구 채팅 서버에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 
  
<span data-ttu-id="b438f-108">고가용성 및 장애 복구를 위해 영구 채팅 배포를 구성 하기 전에 비즈니스용 [Skype 서버 2015에서 영구 채팅 서버용으로 고가용성 및 재해 복구 계획](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)의 개념을 잘 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-108">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="b438f-109">이 항목에서 설명 하는 영구 채팅 서버의 재해 복구 솔루션은 늘어난 영구 채팅 서버 풀에서 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-109">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="b438f-110">계획 콘텐츠는 고가용성 및 SQL Server 로그 전달을 위해 SQL Server 미러링을 사용 하는 것을 포함 하 여 영구 채팅 서버에 대 한 고가용성 및 장애 복구를 가능 하 게 하는 스트레치 된 풀 토폴로지 및 리소스 요구 사항을 설명 합니다. 재난 복구.</span><span class="sxs-lookup"><span data-stu-id="b438f-110">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="b438f-111">토폴로지 작성기를 사용 하 여 고가용성 및 재해 복구 구성</span><span class="sxs-lookup"><span data-stu-id="b438f-111">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="b438f-112">토폴로지 작성기 내에서 영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성 하려면 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-112">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="b438f-113">미러 데이터베이스와 로그 전달 보조 데이터베이스 SQL Server 저장소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-113">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="b438f-114">영구 채팅 서버 서비스 속성을 다음으로 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-114">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="b438f-115">에서.</span><span class="sxs-lookup"><span data-stu-id="b438f-115">a.</span></span> <span data-ttu-id="b438f-116">기본 데이터베이스에 대해 미러링을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-116">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="b438f-117">b.</span><span class="sxs-lookup"><span data-stu-id="b438f-117">b.</span></span> <span data-ttu-id="b438f-118">기본 미러 SQL Server 저장소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-118">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="b438f-119">c.</span><span class="sxs-lookup"><span data-stu-id="b438f-119">c.</span></span> <span data-ttu-id="b438f-120">SQL Server 로그 전달 데이터베이스를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-120">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="b438f-121">a.</span><span class="sxs-lookup"><span data-stu-id="b438f-121">d.</span></span> <span data-ttu-id="b438f-122">SQL Server 로그 전달 보조 SQL Server 저장소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-122">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="b438f-123">z.e.n.works.</span><span class="sxs-lookup"><span data-stu-id="b438f-123">e.</span></span> <span data-ttu-id="b438f-124">보조 데이터베이스에 대 한 SQL Server 저장소 미러를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-124">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="b438f-125">f.</span><span class="sxs-lookup"><span data-stu-id="b438f-125">f.</span></span> <span data-ttu-id="b438f-126">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-126">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="b438f-127">영구 채팅 서버 기본 데이터베이스에 대 한 SQL Server 로그 전달을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-127">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="b438f-128">SQL Server Management Studio를 사용 하 여 영구 채팅 서버 보조 로그 전달 데이터베이스 인스턴스에 연결 하 고 SQL Server 에이전트가 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-128">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="b438f-129">그런 다음 영구 채팅 기본 데이터베이스 인스턴스에 연결 하 고 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-129">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="b438f-130">Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-130">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="b438f-131">**페이지 선택**에서 **트랜잭션 로그 전달을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-131">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="b438f-132">**로그 전달 구성의 기본 데이터베이스로 사용할 수 있도록이** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-132">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="b438f-133">**트랜잭션 로그 백업**에서 **백업 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-133">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="b438f-134">**백업 폴더에 대 한 네트워크 경로** 상자에 트랜잭션 로그 백업 폴더에 대해 만든 공유의 네트워크 경로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-134">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="b438f-135">백업 폴더가 주 서버에 있는 경우 백업 폴더의 백업 폴더에 대 한 로컬 경로를 **주 서버에 입력 하 고 폴더 (예: c:\backup) 상자에 대 한 로컬 경로를 입력** 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-135">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box.</span></span> <span data-ttu-id="b438f-136">(백업 폴더가 주 서버에 없는 경우에는이 상자를 비워 둘 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b438f-136">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b438f-137">주 서버의 SQL Server 서비스 계정이 로컬 시스템 계정에서 실행 되는 경우 주 서버에서 백업 폴더를 만들고 해당 폴더에 대 한 로컬 경로를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-137">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="b438f-138">**보다 오래 된 파일 삭제** 및 매개 변수 **내에서 백업이 수행 되지 않는 경우 경고** 를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-138">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="b438f-139">**백업 작업**아래의 **일정** 상자에 나열 된 백업 일정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-139">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b438f-140">설치 일정을 사용자 지정 하려면 **일정**을 클릭 하 고 필요에 따라 SQL Server 에이전트 일정을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-140">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="b438f-141">**압축**에서 **기본 서버 설정 사용**을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-141">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="b438f-142">**보조 서버 인스턴스 및 데이터베이스**에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-142">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="b438f-143">**연결** 을 클릭 하 고 보조 서버로 구성한 SQL Server 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-143">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="b438f-144">**보조 데이터베이스** 상자에서 목록에 있는 **mgc** 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-144">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="b438f-145">**보조 데이터베이스 초기화** 탭에서 **예, 기본 데이터베이스의 전체 백업을 생성 하 고 보조 데이터베이스에 복원 합니다 (없는 경우 보조 데이터베이스 만들기)**.</span><span class="sxs-lookup"><span data-stu-id="b438f-145">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="b438f-146">**파일 복사** 탭의 **복사 된 파일의 대상 폴더** 상자에 트랜잭션 로그 백업을 복사 해야 하는 폴더의 경로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-146">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied.</span></span> <span data-ttu-id="b438f-147">이 폴더는 주로 보조 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-147">This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="b438f-148">**작업 복사**아래에 있는 **일정** 상자에 나열 된 복사 일정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-148">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="b438f-149">설치 일정을 사용자 지정 하려면 **일정**을 클릭 하 고 필요에 따라 SQL Server 에이전트 일정을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-149">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="b438f-150">이 일정은 거의 백업 일정과 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-150">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="b438f-151">**복원** 탭의 **데이터베이스 상태에서 백업을 복원할 때** **복구 안 됨 모드** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-151">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="b438f-152">**최소 백업 복구 지연**에서 **0 분**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-152">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="b438f-153">**내에 복원이 발생 하지 않는 경우 알림**아래에서 경고 임계값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-153">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="b438f-154">**복원 작업**아래에 있는 **일정** 상자에 나열 된 복원 일정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-154">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="b438f-155">설치 일정을 사용자 지정 하려면 **일정**을 클릭 하 고 필요에 따라 SQL Server 에이전트 일정을 조정 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-155">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="b438f-156">이 일정은 거의 백업 일정과 동일 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-156">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="b438f-157">**데이터베이스 속성** 대화 상자에서 **확인** 을 클릭 하 여 구성 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-157">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="b438f-158">기본 미러 서버와 보조 데이터베이스 간의 SQL Server 로그 전달을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-158">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="b438f-159">기본 영구 채팅 데이터베이스가 미러 데이터베이스로 장애 조치 되는 경우 계속 하려면 로그 전달을 위해 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-159">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="b438f-160">기본 영구 채팅 데이터베이스를 미러에서 수동으로 장애 조치 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-160">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="b438f-161">이 작업은 비즈니스용 Skype 서버 관리 셸 및 **Csdatabasedatabase장애 조치** cmdlet을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-161">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="b438f-162">SQL Server Management Studio를 사용 하 여 기본 영구 채팅 서버 미러 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-162">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="b438f-163">SQL Server 에이전트가 실행 중인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-163">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="b438f-164">Mgc 데이터베이스를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-164">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="b438f-165">**페이지 선택**에서 **트랜잭션 로그 전달을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-165">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="b438f-166">**로그 전달 구성의 기본 데이터베이스로 사용할 수 있도록이** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-166">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="b438f-167">**트랜잭션 로그 백업**에서 **백업 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-167">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="b438f-168">**백업 폴더에 대 한 네트워크 경로** 상자에 트랜잭션 로그 백업 폴더에 대해 만든 공유의 네트워크 경로를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-168">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="b438f-169">백업 폴더가 주 서버에 있는 경우 백업 폴더의 백업 폴더에 대 한 로컬 경로를 **주 서버에 입력 하 고 폴더 상자에 대 한 로컬 경로를 입력** 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-169">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box.</span></span> <span data-ttu-id="b438f-170">(백업 폴더가 주 서버에 없는 경우에는이 상자를 비워 둘 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="b438f-170">(If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b438f-171">주 서버의 SQL Server 서비스 계정이 로컬 시스템 계정에서 실행 되는 경우 주 서버에서 백업 폴더를 만들고 해당 폴더에 대 한 로컬 경로를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-171">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="b438f-172">**보다 오래 된 파일 삭제** 및 매개 변수 **내에서 백업이 수행 되지 않는 경우 경고** 를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-172">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="b438f-173">**백업 작업**아래의 **일정** 상자에 나열 된 백업 일정을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-173">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="b438f-174">설치 일정을 사용자 지정 하려면 **예약**을 클릭 하 고 필요에 따라 SQL Server 에이전트 일정을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-174">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b438f-175">기본 데이터베이스에 사용 했던 것과 동일한 설정을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-175">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="b438f-176">**압축**에서 **기본 서버 설정 사용**을 선택 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-176">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="b438f-177">**보조 서버 인스턴스 및 데이터베이스**에서 **추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-177">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="b438f-178">**연결**을 클릭 하 고 보조 서버로 구성한 SQL Server 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-178">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="b438f-179">**보조 데이터베이스** 상자에서 목록에 있는 **mgc** 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-179">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="b438f-180">**보조 데이터베이스 초기화** 탭에서 아니요 옵션을 선택 합니다. **보조 데이터베이스가 초기화**됩니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-180">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="b438f-181">**파일 복사** 탭에서 **복사 된 파일의 대상 폴더**에 트랜잭션 로그 백업을 복사 해야 하는 폴더의 경로를 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-181">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**.</span></span> <span data-ttu-id="b438f-182">이 폴더는 주로 보조 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-182">This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="b438f-183">**스크립트 구성** 드롭다운 목록을 열고 **구성 스크립트를 새 쿼리 창으로**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-183">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="b438f-184">새 쿼리 창의 **데이터베이스 속성**에서 **확인** 을 클릭 하 여 구성 프로세스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-184">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="b438f-185">쿼리의 첫 번째 절반 (18 단계 참조)을 선택 하 \* \* \* \* \* \* 고 실행 합니다 (--끝: 기본 \* \* \* \* \* \*에서 실행할 스크립트:).</span><span class="sxs-lookup"><span data-stu-id="b438f-185">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="b438f-186">Sql server Management Studio는 SQL Server 로그 전달 구성에서 여러 개의 기본 데이터베이스를 지원 하지 않으므로이 스크립트를 수동으로 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-186">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="b438f-187">' **취소** '를 선택 하 여 로그 파일 전달 구성 패널을 닫고, 장애 조치 (failover)의 경우 기본 데이터베이스와 미러된 데이터베이스 모두에 대 한 로그 파일 전달을 올바르게 구현 하는 작동 설정을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-187">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="b438f-188">기본 영구 채팅 데이터베이스를 기본으로 다시 장애 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-188">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="b438f-189">이 작업은 비즈니스용 Skype 서버 관리 셸을 사용 하 여 수행 하 고, **CsDatabaseFailover** Cmdlet을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b438f-189">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

