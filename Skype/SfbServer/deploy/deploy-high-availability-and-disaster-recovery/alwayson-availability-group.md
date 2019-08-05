---
title: 비즈니스용 Skype 서버의 백 엔드 서버에 Always On 가용성 그룹 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: 비즈니스용 Skype 서버 배포에서 Always On 가용성 그룹을 배포 (설치) 합니다.
ms.openlocfilehash: a01953abbf2233eab91c4a141580e8c452858934
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196975"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="16766-103">비즈니스용 Skype 서버의 백 엔드 서버에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="16766-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="16766-104">비즈니스용 Skype 서버 배포에서 AG (항상 On 가용성 그룹)를 배포 (설치) 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="16766-105">AG를 배포 하는 방법은 미러를 사용 하는 기존 풀에 배포 하 고 있는지 여부 또는 현재 백 엔드 데이터베이스에 대 한 가용성이 높은 기존 풀에 배포할지에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="16766-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16766-106">영구 채팅 서버 역할에서 AG를 사용 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="16766-107">새 프런트 엔드 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="16766-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="16766-108">데이터베이스 미러링을 사용 하는 기존 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="16766-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="16766-109">데이터베이스 미러링을 사용 하지 않는 기존 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="16766-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="16766-110">새 프런트 엔드 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="16766-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="16766-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="16766-111"></span></span>

1. <span data-ttu-id="16766-112">AG에 포함 되는 모든 데이터베이스 서버에서 장애 조치 클러스터링 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="16766-113">각 서버에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="16766-114">서버 관리자를 열고 **역할 및 기능 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="16766-115">**기능 선택** 상자에 도달할 때까지 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="16766-116">**장애 조치 클러스터링** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="16766-117">**장애 조치 클러스터링용으로 필요한 기능 추가** 상자에서 **기능 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="16766-118">**설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="16766-119">클러스터 구성의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="16766-120">서버 관리자에서 **도구** 메뉴를 클릭 한 다음 **장애 조치 클러스터 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="16766-121">화면 오른쪽에 있는 **작업** 에서 **구성 유효성 검사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="16766-122">**시작 하기 전에** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-123">클러스터에 추가할 서버를 선택 하 고 **모든 테스트 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="16766-124">**요약** 상자에서 마법사가 보고 하는 오류를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="16766-125">그런 다음 **마침을** 클릭 하 여 유효성 검사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="16766-126">특히 공유 저장소를 사용 하지 않는 경우 마법사에서 여러 가지 경고를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="16766-127">공유 저장소를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-127">You are not required to use shared storage.</span></span> <span data-ttu-id="16766-128">그러나 **오류** 메시지가 표시 되는 경우 계속 하기 전에 해당 문제를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="16766-129">WSFC (Windows Server 장애 조치 (Failover) 클러스터)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="16766-130">**장애 조치 (Failover) 클러스터 관리** 마법사에서 **장애 조치 클러스터 관리**를 마우스 오른쪽 단추로 클릭 한 다음 **클러스터 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="16766-131">**시작 하기 전에** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-132">클러스터 이름 및 IP 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="16766-133">설정이 확인 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-134">확인 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-135">클러스터를 만든 후 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="16766-136">파일 공유 감시를 사용 하도록 클러스터 쿼럼 설정을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="16766-137">이렇게 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="16766-138">클러스터 이름을 마우스 오른쪽 단추로 클릭 하 고 **기타 작업**을 클릭 한 다음 **클러스터 쿼럼 설정 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="16766-139">**쿼럼 구성 옵션 선택** 페이지에서 **쿼럼 감시 선택**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="16766-140">**쿼럼 감시 선택** 페이지에서 **파일 공유 감시 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="16766-141">**파일 공유 감시 구성** 페이지에서 사용할 파일 공유 경로를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="16766-142">**확인** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="16766-143">클러스터의 각 서버에서 SQL Server 구성 관리자의 AG 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="16766-144">SQL Server 구성 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16766-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="16766-145">화면 왼쪽의 트리에서 **Sql Server 서비스**를 클릭 한 다음 sql server 서비스를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="16766-146">**속성** 상자에서 **alwayson** 고가용성 탭을 선택 합니다. **alwayson 가용성 그룹 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="16766-147">메시지가 표시 되 면 SQL Server 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="16766-148">비즈니스용 [Skype 서버에서 새 토폴로지 만들기 및 게시](../../deploy/install/create-and-publish-new-topology.md)에 설명 된 대로 토폴로지 작성기를 사용 하 여 프런트 엔드 풀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="16766-149">이 작업을 수행 하는 경우 AG를 풀에 대 한 SQL store로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="16766-150">가용성 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="16766-151">SQL Server Management Studio를 열고 SQL Server 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="16766-152">개체 탐색기에서 **Always On 고가용성** 폴더를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="16766-153">**가용성 그룹** 폴더를 마우스 오른쪽 단추로 클릭 하 고 **새 가용성 그룹 마법사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="16766-154">**소개** 페이지가 나타나면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-155">**가용성 그룹 이름 지정** 페이지에서 가용성 그룹의 이름을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="16766-156">데이터베이스 선택 페이지에서 AlwaysOn 가용성 그룹에 포함 하려는 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="16766-157">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="16766-158">이 시나리오에서는 지원 되지 않으므로, AlwaysOn 가용성 그룹에 **ReportServer**, **reportservertempdb**또는 영구 채팅 데이터베이스를 포함 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="16766-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="16766-159">다른 모든 비즈니스용 Skype 서버 데이터베이스를 AlwaysOn 가용성 그룹에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="16766-160">**복제본 지정** 페이지에서 **복제본** 탭을 클릭 합니다. 그런 다음 **복제본 추가** 단추를 클릭 하 고 Windows Server 장애 조치 (Failover) 클러스터의 노드로 가입한 다른 SQL 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="16766-161">각 인스턴스에 대해 **자동 장애 조치** 및 **동기 커밋** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="16766-162">**읽을 수 있는 보조** 옵션을 선택 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="16766-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="16766-163">**끝점** 탭을 클릭 하 고 **포트 번호가** 5022로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="16766-164">**수신기** 탭을 클릭 하 고 **가용성 그룹 수신기 만들기** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="16766-165">이 옵션 아래에 수신기의 이름을 입력 하 고 **포트** 를 1433로 설정 합니다 (다른 포트는이 옵션에 지원 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="16766-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="16766-166">**추가**를 클릭 한 다음 **IPv4 주소** 상자에 기본 가상 IP 주소를 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="16766-167">**초기 데이터 동기화 선택** 페이지에서 전체를 선택 하 고, 복제본에 액세스할 수 있는 폴더를 지정 하 고, 두 복제본에서 사용 하는 SQL Server 서비스 계정에 쓰기 권한이 있는지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="16766-168">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="16766-169">이 파일 공유는 데이터베이스를 초기화할 때 일시적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16766-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="16766-170">대용량 데이터베이스를 처리 하는 경우 네트워크 대역폭이 데이터베이스 백업의 크기를 수용할 수 없는 경우를 포함 하 여 수동으로 초기화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="16766-171">유효성 검사 페이지에서 모든 유효성 검사가 성공 했는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="16766-172">**요약** 페이지에서 모든 설정을 확인 하 고 마침을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="16766-173">풀 및 AG가 배포 된 후 몇 가지 마지막 단계를 수행 하 여 SQL 로그인이 AlwaysOn 가용성 그룹의 각 복제본에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="16766-174">토폴로지 작성기를 열고 **기존 배포에서 토폴로지 다운로드**를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="16766-175">비즈니스용 Skype 서버를 확장 하 고, 토폴로지를 확장 하 고, **SQL Server 스토어**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="16766-176">새 AlwaysOn 가용성 그룹의 SQL 저장소를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="16766-177">페이지의 맨 아래에 있는 **SQL SERVER FQDN** 상자에서 값을 AG 수신기의 FQDN으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="16766-178">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-178">Publish the topology.</span></span> <span data-ttu-id="16766-179">**작업** 메뉴에서 **토폴로지** , **게시**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="16766-180">확인 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="16766-181">그런 다음 새 토폴로지가 복제 될 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="16766-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="16766-182">SQL Server Management Studio를 열고 AG로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="16766-183">보조 복제본으로 장애 조치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="16766-184">비즈니스용 Skype Server Management Shell을 열고 다음 cmdlet을 입력 하 여이 복제본에 대 한 SQL 로그인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="16766-185">그룹의 각 복제본에 대해 앞의 두 단계 (그룹을 보조 복제본으로 장애 `Install-CsDatabase -Update`조치 하 고 사용)를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="16766-186">데이터베이스 미러링을 사용 하는 기존 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="16766-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="16766-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="16766-187"></span></span>

> [!NOTE]
> <span data-ttu-id="16766-188">AG로 업그레이드 하는 풀이 조직의 중앙 관리 저장소를 호스트 하는 경우이 풀을 업그레이드 하기 전에 먼저 CMS를 다른 풀로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="16766-189">이동-CsManagementServer cmdlet을 사용 하 여 풀을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="16766-190">조직에 다른 풀이 없는 경우 풀을 AG로 업그레이드 하기 전에 표준 버전 서버를 임시로 배포 하 고이 서버로 CMS를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="16766-191">비즈니스용 Skype Server Management Shell을 열고 다음 cmdlet을 입력 하 여 미러에서의 모든 데이터를 주 노드로 장애 조치 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="16766-192">풀의 각 데이터베이스 유형에 대해이 cmdlet을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="16766-193">다음 cmdlet을 사용 하 여이 풀에 저장 된 데이터베이스 형식을 모두 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="16766-194">토폴로지 작성기를 사용 하 여 풀에서 데이터베이스 미러링을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="16766-195">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16766-195">Open Topology Builder.</span></span> <span data-ttu-id="16766-196">토폴로지에서 **Enterprise Edition 프런트 엔드 풀**을 확장 하 고 풀의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="16766-197">풀의 각 SQL 저장소 유형에 대해 **Sql 저장소 미러링 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="16766-198">변경 된 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-198">Publish the changed topology.</span></span> <span data-ttu-id="16766-199">**작업** 메뉴에서 **토폴로지** , **게시**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="16766-200">확인 페이지에서 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="16766-201">SQL Server Management Studio를 사용 하 여 미러를 중단 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="16766-202">SQL Server Management Studio를 열고 데이터베이스로 이동한 다음 **작업** 을 마우스 오른쪽 단추로 클릭 하 고 **미러**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="16766-203">그런 다음 **미러링 제거** 를 클릭 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="16766-204">AG로 변환 될 풀의 모든 데이터베이스에 대해이를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="16766-205">AG에 속하는 모든 데이터베이스 서버에 장애 조치 클러스터링 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="16766-206">각 서버에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="16766-207">서버 관리자를 열고 **역할 및 기능 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="16766-208">**기능 선택** 상자에 도달할 때까지 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="16766-209">**장애 조치 클러스터링** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="16766-210">**장애 조치 클러스터링용으로 필요한 기능 추가** 상자에서 **기능 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="16766-211">**설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="16766-212">클러스터 구성의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="16766-213">서버 관리자에서 **도구** 메뉴를 클릭 한 다음 **장애 조치 클러스터 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="16766-214">화면 오른쪽에 있는 **작업** 에서 **구성 유효성 검사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="16766-215">**시작 하기 전에** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-216">클러스터에 추가할 서버를 선택 하 고 **모든 테스트 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="16766-217">**요약** 상자에서 마법사가 보고 하는 오류를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="16766-218">그런 다음 **마침을** 클릭 하 여 유효성 검사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="16766-219">특히 공유 저장소를 사용 하지 않는 경우 마법사에서 여러 가지 경고를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="16766-220">공유 저장소를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-220">You are not required to use shared storage.</span></span> <span data-ttu-id="16766-221">그러나 **오류** 메시지가 표시 되는 경우 계속 하기 전에 해당 문제를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="16766-222">Windows Server 장애 조치 (Failover) 클러스터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="16766-223">**장애 조치 (Failover) 클러스터 관리** 마법사에서 **장애 조치 클러스터 관리**를 마우스 오른쪽 단추로 클릭 한 다음 **클러스터 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="16766-224">**시작 하기 전에** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-225">클러스터 이름 및 IP 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="16766-226">설정이 확인 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-227">확인 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-228">클러스터를 만든 후 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="16766-229">파일 공유 감시를 사용 하도록 클러스터 쿼럼 설정을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="16766-230">이렇게 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="16766-231">클러스터 이름을 마우스 오른쪽 단추로 클릭 하 고 **기타 작업**을 클릭 한 다음 **클러스터 쿼럼 설정 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="16766-232">**쿼럼 구성 옵션 선택** 페이지에서 **쿼럼 감시 선택**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="16766-233">**쿼럼 감시 선택** 페이지에서 **파일 공유 감시 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="16766-234">**파일 공유 감시 구성** 페이지에서 사용할 파일 공유 경로를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="16766-235">**확인** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="16766-236">클러스터의 각 서버에서 SQL Server 구성 관리자의 AG 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="16766-237">SQL Server 구성 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16766-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="16766-238">화면 왼쪽의 트리에서 **Sql Server 서비스**를 클릭 한 다음 sql server 서비스를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="16766-239">**속성** 상자에서 **alwayson** 고가용성 탭을 선택 합니다. **alwayson 가용성 그룹 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="16766-240">메시지가 표시 되 면 SQL Server 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="16766-241">가용성 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="16766-242">SQL Server Management Studio를 열고 SQL Server 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="16766-243">개체 탐색기에서 **Always On 고가용성** 폴더를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="16766-244">**가용성 그룹** 폴더를 마우스 오른쪽 단추로 클릭 하 고 **새 가용성 그룹 마법사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="16766-245">**소개** 페이지가 나타나면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="16766-246">**가용성 그룹 이름 지정** 페이지에서 가용성 그룹의 이름을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="16766-247">데이터베이스 선택 페이지에서 AlwaysOn 가용성 그룹에 포함 하려는 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="16766-248">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="16766-249">이 시나리오에서는 지원 되지 않으므로, AlwaysOn 가용성 그룹에 **ReportServer**, **reportservertempdb**또는 영구 채팅 데이터베이스를 포함 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="16766-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="16766-250">다른 모든 비즈니스용 Skype 서버 데이터베이스를 AlwaysOn 가용성 그룹에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="16766-251">**복제본 지정** 페이지에서 **복제본** 탭을 클릭 합니다. 그런 다음 **복제본 추가** 단추를 클릭 하 고 Windows Server 장애 조치 (Failover) 클러스터의 노드로 가입한 다른 SQL 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="16766-252">각 인스턴스에 대해 **자동 장애 조치** 및 **동기 커밋** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="16766-253">**읽을 수 있는 보조** 옵션을 선택 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="16766-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="16766-254">**끝점** 탭을 클릭 하 고 **포트 번호가** 5022로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="16766-255">**수신기** 탭을 클릭 하 고 **가용성 그룹 수신기 만들기** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="16766-256">이 옵션 아래에 수신기의 이름을 입력 하 고 **포트** 를 1433로 설정 합니다 (다른 포트는이 옵션에 지원 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="16766-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="16766-257">**추가**를 클릭 한 다음 **IPv4 주소** 상자에 기본 가상 IP 주소를 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="16766-258">**초기 데이터 동기화 선택** 페이지에서 전체를 선택 하 고, 복제본에 액세스할 수 있는 폴더를 지정 하 고, 두 복제본에서 사용 하는 SQL Server 서비스 계정에 쓰기 권한이 있는지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="16766-259">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="16766-260">이 파일 공유는 데이터베이스를 초기화할 때 일시적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16766-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="16766-261">대용량 데이터베이스를 처리 하는 경우 네트워크 대역폭이 데이터베이스 백업의 크기를 수용할 수 없는 경우를 포함 하 여 수동으로 초기화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="16766-262">유효성 검사 페이지에서 모든 유효성 검사가 성공 했는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="16766-263">**요약** 페이지에서 모든 설정을 확인 하 고 마침을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="16766-264">AG 수신기를 지정 하 고 AG의 기본 노드로 기존 미러의 사용자를 지정 하는 새 저장소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="16766-265">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16766-265">Open Topology Builder.</span></span> <span data-ttu-id="16766-266">토폴로지에서 **공유 구성 요소**를 확장 하 고 **SQL server 저장소**를 마우스 오른쪽 단추로 클릭 한 다음 **새 sql server 스토어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="16766-267">**새 SQL Store 정의** 페이지에서 먼저 고가용성 **설정** 확인란을 선택한 다음 드롭다운 상자에 SQL AlwaysOn 가용성 그룹이 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="16766-268">**SQL Server 사용 가능성 수신기 FQDN** 상자에 가용성 그룹을 만들 때 만든 수신기의 fqdn을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="16766-269">**SQL SERVER FQDN** 상자에 AG의 기본 노드에 대 한 fqdn을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="16766-270">이 저장소에 대 한 이전 미러의 주 서버 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="16766-271">새 AG를 프런트 엔드 풀에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="16766-272">토폴로지 작성기에서 AG와 연결할 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="16766-273">**연결**의 **SQL Server 스토어** 상자에서 AG를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="16766-274">풀에서 AG로 이동 하려는 다른 데이터베이스에 대해 동일한 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="16766-275">필요한 모든 데이터베이스가 AG로 설정 되어 있는 경우 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="16766-276">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-276">Publish the topology.</span></span> <span data-ttu-id="16766-277">**작업** 메뉴에서 **토폴로지** , **게시**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="16766-278">확인 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="16766-279">마지막 단계를 수행 하 여 SQL 로그인이 AlwaysOn 가용성 그룹의 각 복제본에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="16766-280">토폴로지 작성기를 열고 **기존 배포에서 토폴로지 다운로드**를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="16766-281">비즈니스용 Skype 서버를 확장 하 고, 토폴로지를 확장 하 고, **SQL Server 스토어**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="16766-282">새 AG의 SQL 저장소를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="16766-283">페이지의 맨 아래에 있는 **SQL SERVER FQDN** 상자에서 값을 AG 수신기의 FQDN으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="16766-284">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-284">Publish the topology.</span></span> <span data-ttu-id="16766-285">**작업** 메뉴에서 **토폴로지** , **게시**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="16766-286">확인 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="16766-287">그런 다음 새 토폴로지가 복제 될 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="16766-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="16766-288">SQL Server Management Studio를 열고 AG로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="16766-289">보조 복제본으로 장애 조치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="16766-290">비즈니스용 Skype Server Management Shell을 열고 다음 cmdlet을 입력 하 여이 복제본에 대 한 SQL 로그인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="16766-291">그룹의 각 복제본에 대해 앞의 두 단계 (그룹을 보조 복제본으로 장애 `Install-CsDatabase -Update`조치 하 고 사용)를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="16766-292">데이터베이스 미러링을 사용 하지 않는 기존 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="16766-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="16766-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="16766-293"></span></span>

> [!NOTE]
> <span data-ttu-id="16766-294">AG로 업그레이드 하는 풀이 조직의 중앙 관리 저장소를 호스트 하는 경우이 풀을 업그레이드 하기 전에 먼저 CMS를 다른 풀로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="16766-295">이동-CsManagementServer cmdlet을 사용 하 여 풀을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="16766-296">조직에 다른 풀이 없는 경우 풀을 AG로 업그레이드 하기 전에 표준 버전 서버를 임시로 배포 하 고이 서버로 CMS를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="16766-297">AG에 속하는 모든 데이터베이스 서버에 장애 조치 클러스터링 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="16766-298">각 서버에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="16766-299">서버 관리자를 열고 **역할 및 기능 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="16766-300">**기능 선택** 상자에 도달할 때까지 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="16766-301">**장애 조치 클러스터링** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="16766-302">**장애 조치 클러스터링용으로 필요한 기능 추가** 상자에서 **기능 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="16766-303">**설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="16766-304">클러스터 구성의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="16766-305">서버 관리자에서 **도구** 메뉴를 클릭 한 다음 **장애 조치 클러스터 관리자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="16766-306">화면 오른쪽에 있는 **작업** 에서 **구성 유효성 검사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="16766-307">**시작 하기 전에** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-308">클러스터에 추가할 서버를 선택 하 고 **모든 테스트 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="16766-309">**요약** 상자에서 마법사가 보고 하는 오류를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="16766-310">그런 다음 **마침을** 클릭 하 여 유효성 검사를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="16766-311">특히 공유 저장소를 사용 하지 않는 경우 마법사에서 여러 가지 경고를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="16766-312">공유 저장소를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-312">You are not required to use shared storage.</span></span> <span data-ttu-id="16766-313">그러나 **오류** 메시지가 표시 되는 경우 계속 하기 전에 해당 문제를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="16766-314">WSFC (Windows Server 장애 조치 (Failover) 클러스터)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="16766-315">**장애 조치 (Failover) 클러스터 관리** 마법사에서 **장애 조치 클러스터 관리**를 마우스 오른쪽 단추로 클릭 한 다음 **클러스터 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="16766-316">**시작 하기 전에** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-317">클러스터 이름 및 IP 주소를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="16766-318">설정이 확인 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-319">확인 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-320">클러스터를 만든 후 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="16766-321">파일 공유 감시를 사용 하도록 클러스터 쿼럼 설정을 구성 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="16766-322">이렇게 하려면 다음 단계를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="16766-323">클러스터 이름을 마우스 오른쪽 단추로 클릭 하 고 **기타 작업**을 클릭 한 다음 **클러스터 쿼럼 설정 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="16766-324">**쿼럼 구성 옵션 선택** 페이지에서 **쿼럼 감시 선택**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="16766-325">**쿼럼 감시 선택** 페이지에서 **파일 공유 감시 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="16766-326">**파일 공유 감시 구성** 페이지에서 사용할 파일 공유 경로를 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="16766-327">**확인** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="16766-328">클러스터의 각 서버에서 SQL Server 구성 관리자의 AG를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="16766-329">SQL Server 구성 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16766-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="16766-330">화면 왼쪽의 트리에서 **Sql Server 서비스**를 클릭 한 다음 sql server 서비스를 두 번 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="16766-331">**속성** 상자에서 **alwayson** 고가용성 탭을 선택 합니다. **alwayson 가용성 그룹 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="16766-332">메시지가 표시 되 면 SQL Server 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="16766-333">가용성 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="16766-334">SQL Server Management Studio를 열고 SQL Server 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="16766-335">개체 탐색기에서 **Always On 고가용성** 폴더를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="16766-336">**가용성 그룹** 폴더를 마우스 오른쪽 단추로 클릭 하 고 **새 가용성 그룹 마법사**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="16766-337">**소개** 페이지가 나타나면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="16766-338">**가용성 그룹 이름 지정** 페이지에서 가용성 그룹의 이름을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="16766-339">데이터베이스 선택 페이지에서 AG에 포함 하려는 데이터베이스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="16766-340">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="16766-341">이 시나리오에서는 지원 되지 않으므로 **ReportServer**, **Reportservertempdb**또는 영구 채팅 데이터베이스를 AG에 포함 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="16766-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="16766-342">AG에 다른 모든 비즈니스용 Skype 서버 데이터베이스를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="16766-343">**복제본 지정** 페이지에서 **복제본** 탭을 클릭 합니다. 그런 다음 **복제본 추가** 단추를 클릭 하 고 WSFC의 노드로 가입한 다른 SQL 인스턴스에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="16766-344">각 인스턴스에 대해 **자동 장애 조치** 및 **동기 커밋** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="16766-345">**읽을 수 있는 보조** 옵션을 선택 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="16766-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="16766-346">**끝점** 탭을 클릭 하 고 **포트 번호가** 5022로 설정 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="16766-347">**수신기** 탭을 클릭 하 고 **가용성 그룹 수신기 만들기** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="16766-348">이 옵션 아래에 수신기의 이름을 입력 하 고 **포트** 를 1433로 설정 합니다 (다른 포트는이 옵션에 지원 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="16766-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="16766-349">**추가**를 클릭 한 다음 **IPv4 주소** 상자에 기본 가상 IP 주소를 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="16766-350">**초기 데이터 동기화 선택** 페이지에서 전체를 선택 하 고, 복제본에 액세스할 수 있는 폴더를 지정 하 고, 두 복제본에서 사용 하는 SQL Server 서비스 계정에 쓰기 권한이 있는지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="16766-351">그런 후 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="16766-352">이 파일 공유는 데이터베이스를 초기화할 때 일시적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="16766-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="16766-353">대용량 데이터베이스를 처리 하는 경우 네트워크 대역폭이 데이터베이스 백업의 크기를 수용할 수 없는 경우를 포함 하 여 수동으로 초기화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="16766-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="16766-354">유효성 검사 페이지에서 모든 유효성 검사가 성공 했는지 확인 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="16766-355">**요약** 페이지에서 모든 설정을 확인 하 고 마침을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="16766-356">AG 수신기를 지정 하는 새 저장소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="16766-357">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="16766-357">Open Topology Builder.</span></span> <span data-ttu-id="16766-358">토폴로지에서 **공유 구성 요소**를 확장 하 고 **SQL server 저장소**를 마우스 오른쪽 단추로 클릭 한 다음 **새 sql server 스토어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="16766-359">**새 SQL Store 정의** 페이지에서 먼저 고가용성 **설정** 확인란을 선택한 다음 드롭다운 상자에 SQL AlwaysOn 가용성 그룹이 표시 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="16766-360">**SQL Server 사용 가능성 수신기 FQDN** 상자에 가용성 그룹을 만들 때 만든 수신기의 fqdn을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="16766-361">**SQL SERVER FQDN** 상자에 AG의 기본 노드에 대 한 fqdn을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="16766-362">새 Always On 가용성 그룹과 프런트 엔드 풀을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="16766-363">토폴로지 작성기에서 AG와 연결할 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="16766-364">**연결**의 **SQL Server 스토어** 상자에서 AG를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="16766-365">풀에서 AG로 이동 하려는 다른 데이터베이스에 대해 동일한 그룹을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="16766-366">필요한 모든 데이터베이스가 AG로 설정 되어 있는 경우 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="16766-367">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-367">Publish the topology.</span></span> <span data-ttu-id="16766-368">**작업** 메뉴에서 **토폴로지** , **게시**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="16766-369">확인 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="16766-370">마지막 단계를 수행 하 여 SQL 로그인이 AG의 각 복제본에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="16766-371">토폴로지 작성기를 열고 **기존 배포에서 토폴로지 다운로드**를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="16766-372">비즈니스용 Skype 서버를 확장 하 고, 토폴로지를 확장 하 고, **SQL Server 스토어**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="16766-373">새 AG의 SQL 저장소를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="16766-374">페이지의 맨 아래에 있는 **SQL SERVER FQDN** 상자에서 값을 AG 수신기의 FQDN으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="16766-375">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-375">Publish the topology.</span></span> <span data-ttu-id="16766-376">**작업** 메뉴에서 **토폴로지** , **게시**를 차례로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="16766-377">확인 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="16766-378">그런 다음 새 토폴로지가 복제 될 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="16766-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="16766-379">SQL Server Management Studio를 열고 AG로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="16766-380">보조 복제본으로 장애 조치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="16766-381">비즈니스용 Skype Server Management Shell을 열고 다음 cmdlet을 입력 하 여이 복제본에 대 한 SQL 로그인을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="16766-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="16766-382">그룹의 각 복제본에 대해 앞의 두 단계 (그룹을 보조 복제본으로 장애 `Install-CsDatabase -Update`조치 하 고 사용)를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="16766-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
