---
title: 영구 채팅 서버의 고가용성 및 재해 복구 구성
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5fb5b189-56c1-49cf-92c8-e4fd6e2fdd5c
description: '요약: 이 항목을 통해 비즈니스용 Skype 서버 2015에서 영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성하는 방법을 배울 수 있습니다.'
ms.openlocfilehash: 10d9e2eb76873cedc82daea817a732b8feb379da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802138"
---
# <a name="configure-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="e2142-103">영구 채팅 서버의 고가용성 및 재해 복구 구성</span><span class="sxs-lookup"><span data-stu-id="e2142-103">Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e2142-104">**요약:** 이 항목을 통해 비즈니스용 Skype 서버 2015에서 영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성하는 방법을 알아보도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-104">**Summary:** Read this topic to learn how to configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e2142-105">비즈니스용 Skype 서버는 데이터베이스 미러링을 포함하여 백 엔드 서버에 대해 여러 가지 고가용성 모드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-105">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="e2142-106">자세한 내용은 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)고가용성 및 재해 복구 계획을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2142-106">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e2142-107">AlwaysOn 가용성 그룹은 영구 채팅 서버에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-107">AlwaysOn Availability Groups are not supported with Persistent Chat Servers.</span></span> 

> [!NOTE] 
> <span data-ttu-id="e2142-108">영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e2142-109">Teams에서 동일한 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="e2142-110">자세한 내용은 Microsoft Teams 업그레이드 시작을 [참조하세요.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="e2142-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="e2142-111">영구 채팅을 사용하려면 이 기능이 필요한 사용자를 Teams로 마이그레이션하거나 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="e2142-112">고가용성 및 재해 복구를 위해 영구 채팅 배포를 구성하기 전에 비즈니스용 Skype 서버 [2015의](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md)영구 채팅 서버에 대한 고가용성 및 재해 복구 계획의 개념을 잘 알고 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="e2142-112">Before you configure your Persistent Chat deployment for high availability and disaster recovery, be sure you are familiar with the concepts in [Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="e2142-113">이러한 항목에 설명된 영구 채팅 서버용 재해 복구 솔루션은 확장된 영구 채팅 서버 풀을 토대화합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-113">The disaster recovery solution for Persistent Chat Server described in these topics is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="e2142-114">계획 콘텐츠에서는 리소스 요구 사항 및 영구 채팅 서버에 대해 고가용성 및 재해 복구를 사용할 수 있는 확장된 풀 토폴로지(고가용성을 위한 SQL Server 미러링 사용 및 재해 복구를 위한 로그 SQL Server 토폴로지)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-114">The planning content describes resource requirements, and the stretched pool topology that enables high availability and disaster recovery for Persistent Chat Server, including using SQL Server mirroring for high availability and SQL Server log shipping for disaster recovery.</span></span>
  
## <a name="use-topology-builder-to-configure-high-availability-and-disaster-recovery"></a><span data-ttu-id="e2142-115">토폴로지 작성기에서 고가용성 및 재해 복구 구성</span><span class="sxs-lookup"><span data-stu-id="e2142-115">Use Topology Builder to configure high availability and disaster recovery</span></span>

<span data-ttu-id="e2142-116">토폴로지 작성기 내에서 다음 단계를 수행하여 영구 채팅 서버에 대해 고가용성 및 재해 복구를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-116">Within Topology Builder, perform the following steps to configure high availability and disaster recovery for Persistent Chat Server.</span></span>
  
1. <span data-ttu-id="e2142-117">저장소에 미러 데이터베이스 및 로그 전달 보조 SQL Server 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-117">Add the mirror databases and the log shipping secondary database SQL Server stores.</span></span>
    
2. <span data-ttu-id="e2142-118">영구 채팅 서버 서비스 속성을 다음으로 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-118">Edit the Persistent Chat Server service properties to:</span></span>
    
    <span data-ttu-id="e2142-119">a.</span><span class="sxs-lookup"><span data-stu-id="e2142-119">a.</span></span> <span data-ttu-id="e2142-120">주 데이터베이스에 대한 미러링을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-120">Enable mirroring for the primary database.</span></span>
    
    <span data-ttu-id="e2142-121">b.</span><span class="sxs-lookup"><span data-stu-id="e2142-121">b.</span></span> <span data-ttu-id="e2142-122">기본 미러 SQL Server 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-122">Add the primary mirror SQL Server store.</span></span>
    
    <span data-ttu-id="e2142-123">c.</span><span class="sxs-lookup"><span data-stu-id="e2142-123">c.</span></span> <span data-ttu-id="e2142-124">로그 SQL Server 데이터베이스를 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="e2142-124">Enable the SQL Server Log Shipping database.</span></span>
    
    <span data-ttu-id="e2142-125">d.</span><span class="sxs-lookup"><span data-stu-id="e2142-125">d.</span></span> <span data-ttu-id="e2142-126">로그 SQL Server 전달 보조 SQL Server 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-126">Add the SQL Server Log Shipping secondary SQL Server store.</span></span>
    
    <span data-ttu-id="e2142-127">e.</span><span class="sxs-lookup"><span data-stu-id="e2142-127">e.</span></span> <span data-ttu-id="e2142-128">보조 SQL Server 대한 저장소 미러를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-128">Add the SQL Server store mirror for the secondary database.</span></span>
    
    <span data-ttu-id="e2142-129">f.</span><span class="sxs-lookup"><span data-stu-id="e2142-129">f.</span></span> <span data-ttu-id="e2142-130">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-130">Publish the topology.</span></span>
    
## <a name="set-up-sql-server-log-shipping-for-the-persistent-chat-server-primary-database"></a><span data-ttu-id="e2142-131">영구 채팅 SQL Server 데이터베이스에 대한 로그 전달 설정</span><span class="sxs-lookup"><span data-stu-id="e2142-131">Set up SQL Server log shipping for the Persistent Chat Server primary database</span></span>

<span data-ttu-id="e2142-132">이 SQL Server Management Studio 영구 채팅 서버 보조 로그 전달 데이터베이스 인스턴스에 연결하고 SQL Server 에이전트가 실행되고 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="e2142-132">Using SQL Server Management Studio, connect to the Persistent Chat Server secondary Log Shipping database instance, and be sure that SQL Server Agent is running.</span></span> <span data-ttu-id="e2142-133">그런 다음 영구 채팅 기본 데이터베이스 인스턴스에 연결하고 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-133">Then connect to the Persistent Chat primary database instance and perform the following steps:</span></span>
  
1. <span data-ttu-id="e2142-134">mgc 데이터베이스를 마우스 오른쪽 단추로 클릭한 후 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-134">Right-click the mgc database, and then click **Properties**.</span></span>
    
2. <span data-ttu-id="e2142-135">**페이지 선택** 아래에서 **트랜잭션 로그 전달** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-135">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
3. <span data-ttu-id="e2142-136">**이 데이터베이스를 로그 전달 구성의 기본 데이터베이스로 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-136">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
4. <span data-ttu-id="e2142-137">**트랜잭션 로그 백업** 에서 **백업 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-137">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
5. <span data-ttu-id="e2142-138">**백업 폴더의 네트워크 경로** 상자에 트랜잭션 로그 백업 폴더에 대해 만든 공유의 네트워크 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-138">In the **Network path to the backup folder** box, type the network path to the share that you created for the transaction log backup folder.</span></span>
    
6. <span data-ttu-id="e2142-p111">백업 폴더가 주 서버에 있는 경우 **백업 폴더가 주 서버에 있는 경우 폴더의 로컬 경로(예: c:\backup)를 입력하십시오.** 상자에 백업 폴더의 로컬 경로를 입력합니다. 백업 폴더가 주 서버에 있지 않으면 이 상자를 비워 두면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-p111">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder (example: c:\backup)** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e2142-141">기본 SQL Server 서비스 계정이 로컬 시스템 계정으로 실행되는 경우 기본 서버에 백업 폴더를 만들고 해당 폴더에 대한 로컬 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-141">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
7. <span data-ttu-id="e2142-142">**다음보다 오래된 파일 삭제** 및 **다음 기간 내에 백업이 발생하지 않으면 경고** 매개 변수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-142">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
8. <span data-ttu-id="e2142-143">**백업 작업** 아래의 **예약** 상자에 나열된 백업 일정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-143">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="e2142-144">설치 일정을 사용자 지정하려면 일정을 클릭하고 필요에 따라 SQL Server 에이전트 일정을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-144">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span>
    
9. <span data-ttu-id="e2142-145">**압축** 에서 **기본 서버 설정 사용** 을 선택하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-145">Under **Compression**, select **Use the default server setting**, and then click **OK**.</span></span>
    
10. <span data-ttu-id="e2142-146">**보조 서버 인스턴스 및 데이터베이스** 에서 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-146">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
11. <span data-ttu-id="e2142-147">**Connect를** 클릭하고 보조 SQL Server 구성한 서버의 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-147">Click **Connect** and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
12. <span data-ttu-id="e2142-148">**보조 데이터베이스** 상자의 목록에서 **mgc** 데이터베이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-148">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
13. <span data-ttu-id="e2142-149">보조  데이터베이스 초기화 탭에서 예 옵션을 선택하고 기본 데이터베이스의 전체 백업을 생성한 다음 보조 데이터베이스로 복원합니다(존재하지 않는 경우 보조 데이터베이스 **만들기).**</span><span class="sxs-lookup"><span data-stu-id="e2142-149">On the **Initialize Secondary database** tab, choose the option **Yes, generate a full backup of the primary database and restore it into the secondary database (and create the secondary database if it doesn't exist)**.</span></span>
    
14. <span data-ttu-id="e2142-p113">**파일 복사** 탭의 **복사한 파일의 대상 폴더: (이 폴더는 일반적으로 보조 서버에 있습니다.)** 상자에 트랜잭션 로그 백업을 복사할 폴더의 경로를 입력합니다. 이 폴더는 대개 보조 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-p113">On the **Copy Files** tab, in the **Destination folder for copied files** box, type the path of the folder into which the transaction logs backups should be copied. This folder is often located on the secondary server.</span></span>
    
15. <span data-ttu-id="e2142-152">**복사 작업** 아래 **일정** 상자에 나열된 복사 일정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-152">Note the copy schedule listed in the **Schedule** box under **Copy job**.</span></span> <span data-ttu-id="e2142-153">설치 일정을 사용자 지정하려면 일정을 클릭하고 필요에 따라 SQL Server 에이전트 일정을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-153">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule as required.</span></span> <span data-ttu-id="e2142-154">이 일정은 백업 일정과 대략적으로 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-154">This schedule should be approximately the same as the backup schedule.</span></span>
    
16. <span data-ttu-id="e2142-155">**복원** 탭의 **백업 복원 시 데이터베이스 상태** 에서 **복구 안 함 모드** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-155">On the **Restore** tab, under **Database state when restoring backups**, choose the **No recovery mode** option.</span></span>
    
17. <span data-ttu-id="e2142-156">**최소 다음 기간 동안 백업 복원 지연:** 에서 **0분** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-156">Under **Delay restoring backups at least:**, select **0 minutes**.</span></span>
    
18. <span data-ttu-id="e2142-157">**다음 기간 내에 복원이 발생하지 않으면 경고** 에서 경고 임계값을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-157">Choose an alert threshold under **Alert if no restore occurs within**.</span></span>
    
19. <span data-ttu-id="e2142-158">**복원 작업** 아래 **일정** 상자에 나열된 복원 일정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-158">Look at the restore schedule listed in the **Schedule** box under **Restore job**.</span></span> <span data-ttu-id="e2142-159">설치 일정을 사용자 지정하려면 일정을 클릭하고 **SQL Server** 에이전트 일정을 조정한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="e2142-159">To customize the schedule for your installation, click **Schedule**, adjust the SQL Server Agent schedule as required, and click **OK**.</span></span> <span data-ttu-id="e2142-160">이 일정은 백업 일정과 대략적으로 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-160">This schedule should be approximately the same as the backup schedule.</span></span>
    
20. <span data-ttu-id="e2142-161">**데이터베이스 속성** 대화 상자에서 **확인** 을 클릭하여 구성 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-161">On the **Database Properties** dialog box, click **OK** to begin the configuration process.</span></span>
    
## <a name="set-up-sql-server-log-shipping-between-the-primary-mirror-and-the-secondary-database"></a><span data-ttu-id="e2142-162">기본 SQL Server 데이터베이스 간에 로그 전달 설정</span><span class="sxs-lookup"><span data-stu-id="e2142-162">Set up SQL Server log shipping between the primary mirror and the secondary database</span></span>

<span data-ttu-id="e2142-163">기본 영구 채팅 데이터베이스가 미러 데이터베이스로 실패한 경우 로그 전달을 계속하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-163">Perform the following steps for log shipping to continue if the primary Persistent Chat database is failed over to its mirror database.</span></span>
  
1. <span data-ttu-id="e2142-164">주 영구 채팅 데이터베이스를 미러로 수동으로 장애 조치(fail over)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-164">Manually fail over the primary Persistent Chat database to the mirror.</span></span> <span data-ttu-id="e2142-165">이 수행은 비즈니스용 Skype 서버 관리 셸 및 **Invoke-CsDatabaseFailover** cmdlet을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-165">This is done by using the Skype for Business Server Management Shell and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    
2. <span data-ttu-id="e2142-166">이 SQL Server Management Studio 기본 영구 채팅 서버 미러 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-166">Using the SQL Server Management Studio, connect to the primary Persistent Chat Server mirror instance.</span></span>
    
3. <span data-ttu-id="e2142-167">에이전트가 SQL Server 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="e2142-167">Be sure that the SQL Server Agent is running.</span></span>
    
4. <span data-ttu-id="e2142-168">mgc 데이터베이스를 마우스 오른쪽 단추로 클릭한 후 **속성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-168">Right-click the mgc database, and then click **Properties**.</span></span>
    
5. <span data-ttu-id="e2142-169">**페이지 선택** 아래에서 **트랜잭션 로그 전달** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-169">Under **Select a page**, click **Transaction Log Shipping**.</span></span>
    
6. <span data-ttu-id="e2142-170">**이 데이터베이스를 로그 전달 구성의 기본 데이터베이스로 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-170">Select the **Enable this as a primary database in a log shipping configuration** check box.</span></span>
    
7. <span data-ttu-id="e2142-171">**트랜잭션 로그 백업** 아래에서 **백업 설정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-171">Under **Transaction log backups**, click **Backup Settings**.</span></span>
    
8. <span data-ttu-id="e2142-172">**백업 폴더의 네트워크 경로** 상자에 트랜잭션 로그 백업 폴더에 대해 만든 공유의 네트워크 경로를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-172">In the **Network path to the backup folder** box, type the network path to the share you created for the transaction log backup folder.</span></span>
    
9. <span data-ttu-id="e2142-p117">백업 폴더가 기본 서버에 있는 경우 **백업 폴더가 주 서버에 있는 경우 폴더의 로컬 경로(예: c:\backup)를 입력하십시오.** 상자에 백업 폴더에 대한 로컬 경로를 입력합니다. 백업 폴더가 주 서버에 없으면 이 상자를 비워 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-p117">If the backup folder is located on the primary server, type the local path to the backup folder in the **If the backup folder is located on the primary server, type a local path to the folder** box. (If the backup folder is not on the primary server, you can leave this box empty.)</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e2142-175">기본 SQL Server 서비스 계정이 로컬 시스템 계정으로 실행되는 경우 기본 서버에 백업 폴더를 만들고 해당 폴더에 대한 로컬 경로를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-175">If the SQL Server service account on your primary server runs under the local system account, you must create your backup folder on the primary server and specify a local path to that folder.</span></span> 
  
10. <span data-ttu-id="e2142-176">**다음보다 오래된 파일 삭제** 및 **다음 기간 내에 백업이 발생하지 않으면 경고** 매개 변수를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-176">Configure the **Delete files older than** and **Alert if no backup occurs within** parameters.</span></span>
    
11. <span data-ttu-id="e2142-177">**백업 작업** 아래의 **예약** 상자에 나열된 백업 일정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-177">Look at the backup schedule listed in the **Schedule** box under **Backup job**.</span></span> <span data-ttu-id="e2142-178">설치 일정을 사용자 지정하려면 일정을 클릭하고 필요에 따라 SQL Server 에이전트 일정을 조정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-178">To customize the schedule for your installation, click **Schedule**, and adjust the SQL Server Agent schedule, as required.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e2142-179">기본 데이터베이스에 사용한 것과 동일한 설정을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="e2142-179">Use the same settings that you used for the primary database.</span></span> 
  
12. <span data-ttu-id="e2142-180">**압축** 아래에서 **주 서버 설정 사용** 을 선택하고 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-180">Under **Compression**, select **Use the default server setting**, and click **OK**.</span></span>
    
13. <span data-ttu-id="e2142-181">**보조 서버 인스턴스 및 데이터베이스** 아래에서 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-181">Under **Secondary server instances and databases**, click **Add**.</span></span>
    
14. <span data-ttu-id="e2142-182">**연결** 을 클릭하고 보조 서버로 구성한 SQL Server 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-182">Click **Connect**, and connect to the instance of SQL Server that you have configured as your secondary server.</span></span>
    
15. <span data-ttu-id="e2142-183">**보조 데이터베이스** 상자의 목록에서 **mgc** 데이터베이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-183">In the **Secondary Database** box, select the **mgc** database from the list.</span></span>
    
16. <span data-ttu-id="e2142-184">**보조 데이터베이스 초기화** 탭에서 **아니요, 보조 데이터베이스가 초기화되었습니다.** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-184">On the **Initialize Secondary database** tab, select the option **No, the secondary database is initialized**.</span></span>
    
17. <span data-ttu-id="e2142-p119">**파일 복사** 탭의 **복사된 파일의 대상 폴더** 에 트랜잭션 로그 백업을 복사할 폴더 경로를 입력하고 **확인** 을 클릭합니다. 이 폴더는 주로 보조 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-p119">On the **Copy Files** tab, in **Destination folder for copied files**, type the path of the folder into which the transaction logs backups should be copied, and click **OK**. This folder is often located on the secondary server.</span></span>
    
18. <span data-ttu-id="e2142-187">**스크립트 구성** 드롭다운 목록에서 **구성을 새 쿼리 창으로 스크립팅** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-187">Open the **Script Configuration** drop-down list, and select **Script Configuration to New Query Window**.</span></span>
    
19. <span data-ttu-id="e2142-188">새 쿼리 창의 **데이터베이스 속성** 에서 **확인** 을 클릭하여 구성 프로세스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-188">In the new query window, in **Database Properties**, click **OK** to begin the configuration process.</span></span>
    
20. <span data-ttu-id="e2142-189">쿼리의 첫 번째 절반을 선택하고 실행합니다(18단계 참조). -- \* \* \* \* \* \* End: Script to be run at Primary: \* \* \* \* \* \* .</span><span class="sxs-lookup"><span data-stu-id="e2142-189">Select and run the first half of the query (see step 18) up to the line: -- \*\*\*\*\*\* End: Script to be run at Primary: \*\*\*\*\*\*.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e2142-190">로그 전달 구성에서 SQL Server Management Studio 기본 데이터베이스가 여러 개 지원되지 SQL Server 이 스크립트를 수동으로 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-190">Manually running this script is necessary because SQL Server Management Studio does not support multiple primary databases in a SQL Server Log Shipping configuration.</span></span> 
  
21. <span data-ttu-id="e2142-191">**취소** 를 선택하여 로그 파일 전달 구성 패널을 닫고 기본 데이터베이스 및 미러링된 데이터베이스(장애 조치(failover)의 경우) 모두 로그 파일 전달을 올바르게 구현하는 작동하는 설치를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-191">Select **Cancel** to close the Log File shipping configuration panel and to establish a working setup that correctly implements the log file shipping for both the primary and mirrored database (in case of failover).</span></span>
    
22. <span data-ttu-id="e2142-192">기본 영구 채팅 데이터베이스를 기본 데이터베이스로 수동으로 장애 조치(fail back)합니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-192">Manually fail back the primary Persistent Chat database to the primary.</span></span> <span data-ttu-id="e2142-193">이 수행은 비즈니스용 Skype 서버 관리 셸 및 **Invoke-CsDatabaseFailover** cmdlet을 사용하여 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2142-193">This is done by using the Skype for Business Server Management Shell, and the **Invoke-CsDatabaseFailover** cmdlet.</span></span>
    

