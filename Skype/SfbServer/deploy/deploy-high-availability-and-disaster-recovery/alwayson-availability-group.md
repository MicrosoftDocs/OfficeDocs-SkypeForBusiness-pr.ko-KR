---
title: 비즈니스용 Skype 서버에서 백 엔드 서버에 Always On 가용성 그룹 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c93c01e6-626c-40ad-92dd-373b0fe9189f
description: 비즈니스용 Skype 서버 배포에 Always On 가용성 그룹을 배포(설치)합니다.
ms.openlocfilehash: 83565efe850570ac5ab9a0695757e708f3eae566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830658"
---
# <a name="deploy-an-always-on-availability-group-on-a-back-end-server-in-skype-for-business-server"></a><span data-ttu-id="3e5ed-103">비즈니스용 Skype 서버에서 백 엔드 서버에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="3e5ed-103">Deploy an Always On Availability Group on a Back End Server in Skype for Business Server</span></span>
 
<span data-ttu-id="3e5ed-104">비즈니스용 Skype 서버 배포에 Always On AG(가용성 그룹)를 배포(설치)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-104">Deploy (install) an Always On Availability Group (AG) in your Skype for Business Server deployment.</span></span>
  
<span data-ttu-id="3e5ed-105">AG를 배포하는 방법은 새 풀에 배포하는지, 미러링을 사용하는 기존 풀 또는 현재 백 엔드 데이터베이스에 대해 고가용성이 없는 기존 풀에 배포하는지 여부에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-105">How you deploy an AG depends on whether you are deploying it in a new pool, an existing pool that uses mirroring, or an existing pool that currently has no high availability for the Back End database.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3e5ed-106">영구 채팅 서버 역할과 함께 AG를 사용하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-106">Using an AG with a Persistent Chat Server role is not supported.</span></span> 
  
- [<span data-ttu-id="3e5ed-107">새 프런트 엔드 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="3e5ed-107">Deploy an Always On Availability Group on a new Front End pool</span></span>](alwayson-availability-group.md#BKMK_NewPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="3e5ed-108">데이터베이스 미러링을 사용하는 기존 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="3e5ed-108">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>](alwayson-availability-group.md#BKMK_MirroredPool_CreateAlwaysOnGroup)
    
- [<span data-ttu-id="3e5ed-109">데이터베이스 미러링을 사용하지 않는 기존 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="3e5ed-109">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>](alwayson-availability-group.md#BKMK_NoHAPool_CreateAlwaysOnGroup)
    
## <a name="deploy-an-always-on-availability-group-on-a-new-front-end-pool"></a><span data-ttu-id="3e5ed-110">새 프런트 엔드 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="3e5ed-110">Deploy an Always On Availability Group on a new Front End pool</span></span>
<span data-ttu-id="3e5ed-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="3e5ed-111"><a name="BKMK_NewPool_CreateAlwaysOnGroup"> </a></span></span>

1. <span data-ttu-id="3e5ed-112">AG의 일부가 될 모든 데이터베이스 서버에서 장애 조치(failover) 클러스터링 기능을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-112">Enable the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="3e5ed-113">각 서버에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-113">On each server, do the following</span></span>
    
   - <span data-ttu-id="3e5ed-114">서버 관리자를 열고 역할 **및 기능 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-114">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="3e5ed-115">기능 **선택 상자에** 도달할 때까지 **다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-115">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="3e5ed-116">여기서 장애 **조치(failover) 클러스터링 확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-116">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="3e5ed-117">장애 **조치(failover) 클러스터링에** 필요한 기능 추가 상자에서 기능 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-117">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="3e5ed-118">**설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-118">Click **Install**.</span></span>
    
2. <span data-ttu-id="3e5ed-119">클러스터 구성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-119">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="3e5ed-120">서버 관리자에서 도구 **메뉴를** 클릭한 다음 장애 **조치(failover) 클러스터 관리자를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-120">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="3e5ed-121">화면 **오른쪽의** 작업 아래에서 구성 유효성 검사를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-121">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="3e5ed-122">**시작하기 전에** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-122">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-123">클러스터에 추가할 서버를 선택하고 모든 테스트 **실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-123">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="3e5ed-124">요약 **상자에서** 마법사에서 보고하는 오류를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-124">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="3e5ed-125">그런 다음 **완료를** 클릭하여 유효성 검사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-125">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="3e5ed-126">특히 공유 저장소를 사용하지 않는 경우 마법사에서 여러 경고를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-126">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="3e5ed-127">공유 저장소를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-127">You are not required to use shared storage.</span></span> <span data-ttu-id="3e5ed-128">그러나 오류 메시지가  표시되는 경우 계속하기 전에 이러한 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-128">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="3e5ed-129">WSFC(Windows Server 장애 조치(Failover) 클러스터)를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-129">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="3e5ed-130">장애 조치 클러스터 관리 마법사에서 장애 **조치(failover)** 클러스터 관리를 마우스 **오른쪽** 단추로 클릭한 다음 클러스터 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-130">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="3e5ed-131">**시작하기 전에** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-131">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-132">클러스터 이름 및 IP 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-132">Add the cluster name and IP address.</span></span> <span data-ttu-id="3e5ed-133">설정의 유효성을 검사하면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-133">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-134">확인페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-134">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-135">클러스터를 만든 후 마친 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-135">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="3e5ed-136">파일 공유 미러링계를 사용하도록 클러스터 쿼럼 설정을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-136">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="3e5ed-137">이렇게 하여 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-137">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="3e5ed-138">클러스터 이름을 마우스 오른쪽 단추로 클릭하고 추가 **작업을** 클릭한 다음 클러스터 쿼럼 **설정 구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-138">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="3e5ed-139">**쿼럼 구성** 옵션 선택 페이지에서 쿼럼 미러링계 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-139">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="3e5ed-140">**쿼럼 미러링 확인** 선택 페이지에서 파일 공유 미러링계 **구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-140">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="3e5ed-141">파일 **공유** 미러링 금지 구성 페이지에서 사용할 파일 공유의 경로를 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-141">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-142">**확인** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-142">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="3e5ed-143">클러스터의 각 서버에서 Configuration Manager에서 AG SQL Server 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-143">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="3e5ed-144">SQL Server 구성 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-144">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="3e5ed-145">화면 왼쪽의 트리에서 SQL Server 서비스를 클릭한 다음 서비스 SQL Server 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-145">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="3e5ed-146">속성 **상자에서** **AlwaysOn 고가용성 탭을** 선택합니다. **AlwaysOn 가용성 그룹 사용 확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-146">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="3e5ed-147">메시지가 표시 SQL Server 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-147">Restart the SQL Server service when prompted.</span></span>
   
6. <span data-ttu-id="3e5ed-148">비즈니스용 Skype 서버에서 새 토폴로지 만들기 및 게시에 설명된 토폴로지 작성기에서 설명하는 프런트 엔드 풀을 [만들 수 있습니다.](../../deploy/install/create-and-publish-new-topology.md)</span><span class="sxs-lookup"><span data-stu-id="3e5ed-148">Use Topology Builder to create the Front End pool, as explained in [Create and publish new topology in Skype for Business Server](../../deploy/install/create-and-publish-new-topology.md).</span></span> <span data-ttu-id="3e5ed-149">이 경우 AG를 풀의 SQL 저장소로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-149">When you do, specify the AG as the SQL store for the pool.</span></span>
    
7. <span data-ttu-id="3e5ed-150">가용성 그룹을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-150">Create the availability group.</span></span>
    
   - <span data-ttu-id="3e5ed-151">이 SQL Server Management Studio 열고 SQL Server 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-151">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="3e5ed-152">개체 탐색기에서 **Always On 고가용성 폴더를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-152">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="3e5ed-153">가용성 그룹 **폴더를** 마우스 오른쪽 단추로 클릭하고 새 가용성 그룹 **마법사를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-153">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="3e5ed-154">소개 **페이지가** 나타나면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-154">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-155">가용성 그룹 **이름** 지정 페이지에서 가용성 그룹의 이름을 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-155">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-156">데이터베이스 선택 페이지에서 AlwaysOn 가용성 그룹에 포함할 데이터베이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-156">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="3e5ed-157">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-157">Then click **Next**.</span></span>
    
     <span data-ttu-id="3e5ed-158">이 시나리오에서는 지원되지 않는 **ReportServer,** **ReportServerTempDB** 또는 영구 채팅 데이터베이스를 AlwaysOn 가용성 그룹에 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-158">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="3e5ed-159">AlwaysOn 가용성 그룹에 다른 모든 비즈니스용 Skype 서버 데이터베이스를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-159">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
   - <span data-ttu-id="3e5ed-160">복제본 **지정 페이지에서** 복제 데이터베이스 **탭을** 클릭합니다. 그런 다음  복제본 추가 단추를 클릭하고 Windows Server 장애 조치(failover) SQL 노드로 가입한 다른 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-160">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="3e5ed-161">각 인스턴스에 대해 자동 장애 **조치(Failover)** 및 **동기** 커밋 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-161">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="3e5ed-162">읽을 수 있는 보조 **옵션을 선택하지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-162">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="3e5ed-163">끝점 **탭을** 클릭하고  포트 번호가 5022로 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-163">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="3e5ed-164">수신기 **탭을 클릭하고** 가용성 그룹 수신기 **만들기 옵션을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-164">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="3e5ed-165">이 옵션 아래에 수신기 이름을 입력하고 **포트를** 1433으로 설정합니다(이 옵션에 대해 다른 포트는 지원되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="3e5ed-165">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="3e5ed-166">**추가를** 클릭한 다음 **IPv4** 주소 상자에서 기본 설정 가상 IP 주소를 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-166">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="3e5ed-167">초기 **데이터** 동기화 선택 페이지에서 전체를 선택하고 복제본에 액세스할 수 있는 폴더를 지정하고 두 복제본에서 사용하는 SQL Server 서비스 계정에 쓰기 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-167">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="3e5ed-168">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-168">Then click **Next**.</span></span>
    
     <span data-ttu-id="3e5ed-169">이 파일 공유는 데이터베이스를 초기화할 때 일시적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-169">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="3e5ed-170">대규모 데이터베이스를 사용하는 경우 네트워크 대역폭이 데이터베이스 백업의 크기를 수용할 수 없는 경우 수동으로 초기화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-170">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
   - <span data-ttu-id="3e5ed-171">유효성 검사 페이지에서 모든 유효성 검사가 성공적이면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-171">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-172">요약 **페이지에서** 모든 설정을 확인하고 마친을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-172">In the **Summary** page, verify all settings and click Finish.</span></span>
      
8. <span data-ttu-id="3e5ed-173">풀 및 AG를 배포한 후 몇 가지 최종 단계를 수행하여 alwaysOn 가용성 그룹의 SQL 복제본에 대한 로그인이 있는지 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-173">After the pool and the AG are deployed, perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span> 
    
   - <span data-ttu-id="3e5ed-174">토폴로지 작성기 열기, 기존 배포에서 **토폴로지 다운로드를** 선택한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-174">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
   - <span data-ttu-id="3e5ed-175">비즈니스용 Skype 서버를 확장하고, 토폴로지 및 저장소를 **SQL Server 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-175">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="3e5ed-176">새 AlwaysOn 가용성 SQL 저장소를 마우스 오른쪽 단추로 클릭하고 속성 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-176">Right-click the SQL store of the new AlwaysOn Availability Group, and click **Edit Properties**.</span></span>
    
     - <span data-ttu-id="3e5ed-177">페이지 아래쪽의 SQL Server **FQDN** 상자에서 값을 AG 수신기 FQDN으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-177">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
   - <span data-ttu-id="3e5ed-178">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-178">Publish the topology.</span></span> <span data-ttu-id="3e5ed-179">작업 **메뉴에서** **토폴로지** 및 게시를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-179">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="3e5ed-180">그런 다음 확인 페이지에서 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-180">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="3e5ed-181">그런 다음 새 토폴로지가 복제될 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-181">Then wait a few minutes for the new topology to replicate.</span></span>
    
   - <span data-ttu-id="3e5ed-182">사용자 SQL Server Management Studio 열고 AG로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-182">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="3e5ed-183">보조 복제본으로 장애 조치(fail over)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-183">Fail it over to a secondary replica.</span></span>
    
   - <span data-ttu-id="3e5ed-184">비즈니스용 Skype 서버 관리 셸을 열고 다음 cmdlet을 입력하여 이 SQL 로그인을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-184">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
   ```powershell
   Install-CsDatabase -Update
   ```

   - <span data-ttu-id="3e5ed-185">그룹의 각 복제본에 대해 이전 두 단계를 반복합니다(그룹을 보조 복제본으로 장애 조치한 다음  `Install-CsDatabase -Update` 사용).</span><span class="sxs-lookup"><span data-stu-id="3e5ed-185">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-uses-database-mirroring"></a><span data-ttu-id="3e5ed-186">데이터베이스 미러링을 사용하는 기존 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="3e5ed-186">Deploy an Always On Availability Group on an existing pool that uses database mirroring</span></span>
<span data-ttu-id="3e5ed-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="3e5ed-187"><a name="BKMK_MirroredPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="3e5ed-188">AG로 업그레이드하는 풀이 조직의 중앙 관리 저장소를 호스팅하는 경우 이 풀을 업그레이드하기 전에 먼저 CMS를 다른 풀로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-188">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="3e5ed-189">풀을 Move-CsManagementServer cmdlet을 사용하여 풀을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-189">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="3e5ed-190">조직에 다른 풀이 없는 경우 풀을 AG로 업그레이드하기 전에 Standard Edition 서버를 일시적으로 배포하고 CMS를 이 서버로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-190">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="3e5ed-191">비즈니스용 Skype 서버 관리 셸을 열고 다음 cmdlet을 입력하여 미러에서 주 노드로 모든 데이터를 장애 조치(fail over)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-191">Fail over all data from the mirror to the principal node by opening Skype for Business Server Management Shell and typing the following cmdlet.</span></span>
    
   ```powershell
   Invoke-CsDatabaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <DatabaseType> -NewPrincipal "Primary"
   ```

    <span data-ttu-id="3e5ed-192">풀의 각 데이터베이스 유형에 대해 이 cmdlet을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-192">Repeat this cmdlet for each database type in the pool.</span></span> <span data-ttu-id="3e5ed-193">다음 cmdlet을 사용하여 이 풀에 저장된 모든 데이터베이스 유형을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-193">You can use the following cmdlet to find all the database types stored in this pool.</span></span>
     
   ```powershell
   Get-CsPool -Identity <Pool FQDN>
   ```

2. <span data-ttu-id="3e5ed-194">토폴로지 작성기를 사용하여 풀에서 데이터베이스 미러링을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-194">Use Topology Builder to remove database mirroring from the pool.</span></span>
    
   - <span data-ttu-id="3e5ed-195">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-195">Open Topology Builder.</span></span> <span data-ttu-id="3e5ed-196">토폴로지에서 **Enterprise Edition** 프런트 엔드 풀을 확장하고 풀의 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-196">In your topology, expand **Enterprise Edition Front End Pools**, right-click the name of the pool, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="3e5ed-197">풀의 각 SQL 저장소 유형에 대해 SQL 저장소 미러링 사용 **확인란의 선택을** 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-197">For each type of SQL store in the pool, clear the **Enable SQL Store Mirroring** check box.</span></span>
    
3. <span data-ttu-id="3e5ed-198">변경된 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="3e5ed-198">Publish the changed topology.</span></span> <span data-ttu-id="3e5ed-199">작업 **메뉴에서** **토폴로지** 및 게시를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-199">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="3e5ed-200">그런 다음 확인 페이지에서 **다음을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-200">Then in the confirmation page click **Next**</span></span>
    
4. <span data-ttu-id="3e5ed-201">이 SQL Server Management Studio 미러를 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-201">Use SQL Server Management Studio to break the mirror.</span></span>
    
   - <span data-ttu-id="3e5ed-202">데이터베이스 SQL Server Management Studio 열고 데이터베이스로 이동한 다음 **작업을** 마우스 오른쪽 단추로 클릭한 다음 미러를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-202">Open SQL Server Management Studio, navigate to your databases, right-click **Tasks** and click **Mirror**.</span></span> <span data-ttu-id="3e5ed-203">그런 다음 **미러링 제거를 클릭하고** 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-203">Then click **Remove Mirroring** and click **OK**.</span></span>
    
   - <span data-ttu-id="3e5ed-204">풀에서 AG로 변환될 모든 데이터베이스에 대해 이 작업을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-204">Repeat this for all databases in the pool which will be converted to an AG.</span></span>
    
5. <span data-ttu-id="3e5ed-205">AG의 일부가 될 모든 데이터베이스 서버에서 장애 조치(failover) 클러스터링 기능을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-205">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="3e5ed-206">각 서버에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-206">On each server, do the following</span></span>
    
   - <span data-ttu-id="3e5ed-207">서버 관리자를 열고 역할 **및 기능 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-207">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="3e5ed-208">기능 **선택 상자에** 도달할 때까지 **다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-208">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="3e5ed-209">여기서 장애 **조치(failover) 클러스터링 확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-209">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="3e5ed-210">장애 **조치(failover) 클러스터링에** 필요한 기능 추가 상자에서 기능 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-210">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="3e5ed-211">**설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-211">Click **Install**.</span></span>
    
6. <span data-ttu-id="3e5ed-212">클러스터 구성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-212">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="3e5ed-213">서버 관리자에서 도구 **메뉴를** 클릭한 다음 장애 **조치(failover) 클러스터 관리자를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-213">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="3e5ed-214">화면 **오른쪽의** 작업 아래에서 구성 유효성 검사를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-214">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="3e5ed-215">**시작하기 전에** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-215">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-216">클러스터에 추가할 서버를 선택하고 모든 테스트 **실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-216">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="3e5ed-217">요약 **상자에서** 마법사에서 보고하는 오류를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-217">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="3e5ed-218">그런 다음 **완료를** 클릭하여 유효성 검사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-218">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="3e5ed-219">특히 공유 저장소를 사용하지 않는 경우 마법사에서 여러 경고를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-219">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="3e5ed-220">공유 저장소를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-220">You are not required to use shared storage.</span></span> <span data-ttu-id="3e5ed-221">그러나 오류 메시지가  표시되는 경우 계속하기 전에 이러한 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-221">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
7. <span data-ttu-id="3e5ed-222">Windows Server 장애 조치(failover) 클러스터를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-222">Create the Windows Server Failover Cluster.</span></span>
    
   - <span data-ttu-id="3e5ed-223">장애 조치 클러스터 관리 마법사에서 장애 **조치(failover)** 클러스터 관리를 마우스 **오른쪽** 단추로 클릭한 다음 클러스터 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-223">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="3e5ed-224">**시작하기 전에** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-224">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-225">클러스터 이름 및 IP 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-225">Add the cluster name and IP address.</span></span> <span data-ttu-id="3e5ed-226">설정의 유효성을 검사하면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-226">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-227">확인페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-227">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-228">클러스터를 만든 후 마친 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-228">After the cluster is created, click **Finish**.</span></span>
    
8. <span data-ttu-id="3e5ed-229">파일 공유 미러링계를 사용하도록 클러스터 쿼럼 설정을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-229">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="3e5ed-230">이렇게 하여 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-230">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="3e5ed-231">클러스터 이름을 마우스 오른쪽 단추로 클릭하고 추가 **작업을** 클릭한 다음 클러스터 쿼럼 **설정 구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-231">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="3e5ed-232">**쿼럼 구성** 옵션 선택 페이지에서 쿼럼 미러링계 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-232">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="3e5ed-233">**쿼럼 미러링 확인** 선택 페이지에서 파일 공유 미러링계 **구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-233">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="3e5ed-234">파일 **공유** 미러링 금지 구성 페이지에서 사용할 파일 공유의 경로를 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-234">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-235">**확인** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-235">On the **Confirmation** page, click **Next**.</span></span>
    
9. <span data-ttu-id="3e5ed-236">클러스터의 각 서버에서 Configuration Manager에서 AG SQL Server 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-236">On each server in the cluster, enable the AG feature in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="3e5ed-237">SQL Server 구성 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-237">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="3e5ed-238">화면 왼쪽의 트리에서 SQL Server 서비스를 클릭한 다음 서비스 SQL Server 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-238">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="3e5ed-239">속성 **상자에서** **AlwaysOn 고가용성 탭을** 선택합니다. **AlwaysOn 가용성 그룹 사용 확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-239">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="3e5ed-240">메시지가 표시 SQL Server 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-240">Restart the SQL Server service when prompted.</span></span>
    
10. <span data-ttu-id="3e5ed-241">가용성 그룹을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-241">Create the availability group.</span></span>
    
    - <span data-ttu-id="3e5ed-242">이 SQL Server Management Studio 열고 SQL Server 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-242">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
    - <span data-ttu-id="3e5ed-243">개체 탐색기에서 **Always On 고가용성 폴더를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-243">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="3e5ed-244">가용성 그룹 **폴더를** 마우스 오른쪽 단추로 클릭하고 새 가용성 그룹 **마법사를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-244">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
    - <span data-ttu-id="3e5ed-245">소개 **페이지가** 나타나면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-245">If the **Introduction** page appears, click **Next**.</span></span>
    
    - <span data-ttu-id="3e5ed-246">가용성 그룹 **이름** 지정 페이지에서 가용성 그룹의 이름을 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-246">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
    - <span data-ttu-id="3e5ed-247">데이터베이스 선택 페이지에서 AlwaysOn 가용성 그룹에 포함할 데이터베이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-247">In the Select Databases page, select the databases that you want to include in the AlwaysOn Availability Group.</span></span> <span data-ttu-id="3e5ed-248">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-248">Then click **Next**.</span></span>
    
    <span data-ttu-id="3e5ed-249">이 시나리오에서는 지원되지 않는 **ReportServer,** **ReportServerTempDB** 또는 영구 채팅 데이터베이스를 AlwaysOn 가용성 그룹에 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-249">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AlwaysOn Availability Group, as these are not supported in this scenario.</span></span> <span data-ttu-id="3e5ed-250">AlwaysOn 가용성 그룹에 다른 모든 비즈니스용 Skype 서버 데이터베이스를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-250">You can include all other Skype for Business Server databases in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="3e5ed-251">복제본 **지정 페이지에서** 복제 데이터베이스 **탭을** 클릭합니다. 그런 다음  복제본 추가 단추를 클릭하고 Windows Server 장애 조치(failover) SQL 노드로 가입한 다른 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-251">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the Windows Server Failover Cluster.</span></span>
    
    - <span data-ttu-id="3e5ed-252">각 인스턴스에 대해 자동 장애 **조치(Failover)** 및 **동기** 커밋 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-252">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="3e5ed-253">읽을 수 있는 보조 **옵션을 선택하지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-253">Do not select the **Readable Secondary** option.</span></span>
    
    - <span data-ttu-id="3e5ed-254">끝점 **탭을** 클릭하고  포트 번호가 5022로 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-254">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
      - <span data-ttu-id="3e5ed-255">수신기 **탭을 클릭하고** 가용성 그룹 수신기 **만들기 옵션을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-255">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="3e5ed-256">이 옵션 아래에 수신기 이름을 입력하고 **포트를** 1433으로 설정합니다(이 옵션에 대해 다른 포트는 지원되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="3e5ed-256">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
    - <span data-ttu-id="3e5ed-257">**추가를** 클릭한 다음 **IPv4** 주소 상자에서 기본 설정 가상 IP 주소를 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-257">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
    - <span data-ttu-id="3e5ed-258">초기 **데이터** 동기화 선택 페이지에서 전체를 선택하고 복제본에 액세스할 수 있는 폴더를 지정하고 두 복제본에서 사용하는 SQL Server 서비스 계정에 쓰기 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-258">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="3e5ed-259">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-259">Then click **Next**.</span></span>
    
    <span data-ttu-id="3e5ed-260">이 파일 공유는 데이터베이스를 초기화할 때 일시적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-260">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="3e5ed-261">대규모 데이터베이스를 사용하는 경우 네트워크 대역폭이 데이터베이스 백업의 크기를 수용할 수 없는 경우 수동으로 초기화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-261">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
    - <span data-ttu-id="3e5ed-262">유효성 검사 페이지에서 모든 유효성 검사가 성공적이면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-262">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
    - <span data-ttu-id="3e5ed-263">요약 **페이지에서** 모든 설정을 확인하고 마친을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-263">In the **Summary** page, verify all settings and click Finish.</span></span>
    
11. <span data-ttu-id="3e5ed-264">AG 수신기 및 이전 미러의 주 노드를 AG의 기본 노드로 지정하는 새 저장소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-264">Create a new store specifying the AG listener, and specifying the principal of the old mirror as the primary node of the AG.</span></span>
    
    - <span data-ttu-id="3e5ed-265">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-265">Open Topology Builder.</span></span> <span data-ttu-id="3e5ed-266">토폴로지에서 공유 구성 요소를 확장하고 SQL Server 마우스 오른쪽 단추로 클릭한 다음 새 **저장소를 SQL Server 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-266">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
    - <span data-ttu-id="3e5ed-267">새 SQL **저장소** 정의 페이지에서 먼저 고가용성 설정 확인란을 선택한 다음 SQL AlwaysOn 가용성 그룹이 드롭다운 상자에 나타나는지 확인합니다. </span><span class="sxs-lookup"><span data-stu-id="3e5ed-267">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
    - <span data-ttu-id="3e5ed-268">SQL Server **수신기 FQDN** 상자에 가용성 그룹을 만들 때 만든 수신기 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-268">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
    - <span data-ttu-id="3e5ed-269">SQL Server **FQDN** 상자에 AG 기본 노드의 FQDN을 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-269">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span> <span data-ttu-id="3e5ed-270">이 저장소는 이 저장소에 대한 이전 미러의 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-270">This should be the principal of the old mirror for this store.</span></span>
    
12. <span data-ttu-id="3e5ed-271">새 AG를 프런트 엔드 풀과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-271">Associate the new AG with the Front End pool.</span></span>
    
    - <span data-ttu-id="3e5ed-272">토폴로지 작성기에서 AG에 연결하려면 풀을 마우스 오른쪽 단추로 클릭하고 속성 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-272">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="3e5ed-273">**연결의** SQL Server **저장소** 상자에서 AG를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-273">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="3e5ed-274">풀에서 AG로 이동할 다른 데이터베이스에 대해 동일한 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-274">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
    - <span data-ttu-id="3e5ed-275">필요한 모든 데이터베이스가 AG로 설정되어 있는지 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-275">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
13. <span data-ttu-id="3e5ed-276">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-276">Publish the topology.</span></span> <span data-ttu-id="3e5ed-277">작업 **메뉴에서** **토폴로지** 및 게시를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-277">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="3e5ed-278">그런 다음 확인 페이지에서 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-278">Then in the confirmation page click **Next**.</span></span>
    
14. <span data-ttu-id="3e5ed-279">AlwaysOn 가용성 그룹의 각 복제본에 SQL 로그인이 있는지 확인하도록 마지막 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-279">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AlwaysOn Availability Group.</span></span>
    
    - <span data-ttu-id="3e5ed-280">토폴로지 작성기 열기, 기존 배포에서 **토폴로지 다운로드를** 선택한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-280">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="3e5ed-281">비즈니스용 Skype 서버를 확장하고, 토폴로지 및 저장소를 **SQL Server 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-281">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="3e5ed-282">새 AG의 SQL 마우스 오른쪽 단추로 클릭하고 **속성 편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-282">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="3e5ed-283">페이지 아래쪽의 SQL Server **FQDN** 상자에서 값을 AG 수신기 FQDN으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-283">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="3e5ed-284">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-284">Publish the topology.</span></span> <span data-ttu-id="3e5ed-285">작업 **메뉴에서** **토폴로지** 및 게시를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-285">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="3e5ed-286">그런 다음 확인 페이지에서 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-286">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="3e5ed-287">그런 다음 새 토폴로지가 복제될 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-287">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="3e5ed-288">사용자 SQL Server Management Studio 열고 AG로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-288">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="3e5ed-289">보조 복제본으로 장애 조치(fail over)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-289">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="3e5ed-290">비즈니스용 Skype 서버 관리 셸을 열고 다음 cmdlet을 입력하여 이 SQL 로그인을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-290">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
    ```powershell
    Install-CsDatabase -Update
    ```

    - <span data-ttu-id="3e5ed-291">그룹의 각 복제본에 대해 이전 두 단계를 반복합니다(그룹을 보조 복제본으로 장애 조치한 다음  `Install-CsDatabase -Update` 사용).</span><span class="sxs-lookup"><span data-stu-id="3e5ed-291">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
    
## <a name="deploy-an-always-on-availability-group-on-an-existing-pool-that-does-not-use-database-mirroring"></a><span data-ttu-id="3e5ed-292">데이터베이스 미러링을 사용하지 않는 기존 풀에 Always On 가용성 그룹 배포</span><span class="sxs-lookup"><span data-stu-id="3e5ed-292">Deploy an Always On Availability Group on an existing pool that does not use database mirroring</span></span>
<span data-ttu-id="3e5ed-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span><span class="sxs-lookup"><span data-stu-id="3e5ed-293"><a name="BKMK_NoHAPool_CreateAlwaysOnGroup"> </a></span></span>

> [!NOTE]
> <span data-ttu-id="3e5ed-294">AG로 업그레이드하는 풀이 조직의 중앙 관리 저장소를 호스팅하는 경우 이 풀을 업그레이드하기 전에 먼저 CMS를 다른 풀로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-294">If the pool you are upgrading to an AG hosts the Central Management store for your organization, you must first move the CMS to another pool before you upgrade this pool.</span></span> <span data-ttu-id="3e5ed-295">풀을 Move-CsManagementServer cmdlet을 사용하여 풀을 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-295">Use the Move-CsManagementServer cmdlet to move the pool.</span></span> <span data-ttu-id="3e5ed-296">조직에 다른 풀이 없는 경우 풀을 AG로 업그레이드하기 전에 Standard Edition 서버를 일시적으로 배포하고 CMS를 이 서버로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-296">If you do not have another pool in your organization, you can deploy a Standard Edition server temporarily and move the CMS to this server before you upgrade your pool to the AG.</span></span> 
  
1. <span data-ttu-id="3e5ed-297">AG의 일부가 될 모든 데이터베이스 서버에서 장애 조치(failover) 클러스터링 기능을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-297">Set up the Failover Clustering feature on all the database servers which will be part of the AG.</span></span> <span data-ttu-id="3e5ed-298">각 서버에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-298">On each server, do the following</span></span>
    
   - <span data-ttu-id="3e5ed-299">서버 관리자를 열고 역할 **및 기능 추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-299">Open Server Manager and click **Add roles and features**.</span></span>
    
   - <span data-ttu-id="3e5ed-300">기능 **선택 상자에** 도달할 때까지 **다음을** 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-300">Click **Next** until you reach the **Select features** box.</span></span> <span data-ttu-id="3e5ed-301">여기서 장애 **조치(failover) 클러스터링 확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-301">Here, select the **Failover Clustering** check box.</span></span>
    
   - <span data-ttu-id="3e5ed-302">장애 **조치(failover) 클러스터링에** 필요한 기능 추가 상자에서 기능 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-302">In the **Add features that are required for Failover Clustering?** box, click **Add Features**.</span></span>
    
   - <span data-ttu-id="3e5ed-303">**설치** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-303">Click **Install**.</span></span>
    
2. <span data-ttu-id="3e5ed-304">클러스터 구성의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-304">Validate the cluster configuration.</span></span>
    
   - <span data-ttu-id="3e5ed-305">서버 관리자에서 도구 **메뉴를** 클릭한 다음 장애 **조치(failover) 클러스터 관리자를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-305">In Server Manager, click the **Tools** menu and then click **Failover Cluster Manager**.</span></span>
    
   - <span data-ttu-id="3e5ed-306">화면 **오른쪽의** 작업 아래에서 구성 유효성 검사를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-306">Under **Actions** on the right side of the screen, click **Validate Configuration**.</span></span>
    
   - <span data-ttu-id="3e5ed-307">**시작하기 전에** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-307">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-308">클러스터에 추가할 서버를 선택하고 모든 테스트 **실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-308">Select the servers to add to the cluster, and then click **Run all tests**.</span></span>
    
   - <span data-ttu-id="3e5ed-309">요약 **상자에서** 마법사에서 보고하는 오류를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-309">In the **Summary** box, check any errors that the wizard reports.</span></span> <span data-ttu-id="3e5ed-310">그런 다음 **완료를** 클릭하여 유효성 검사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-310">Then click **Finish** to complete the validation.</span></span>
    
     <span data-ttu-id="3e5ed-311">특히 공유 저장소를 사용하지 않는 경우 마법사에서 여러 경고를 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-311">The wizard will probably report several warnings, especially if you are not using shared storage.</span></span> <span data-ttu-id="3e5ed-312">공유 저장소를 사용할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-312">You are not required to use shared storage.</span></span> <span data-ttu-id="3e5ed-313">그러나 오류 메시지가  표시되는 경우 계속하기 전에 이러한 문제를 해결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-313">However, if you see any **Error** messages, you must fix those issues before continuing.</span></span>
    
3. <span data-ttu-id="3e5ed-314">WSFC(Windows Server 장애 조치(Failover) 클러스터)를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-314">Create the Windows Server Failover Cluster (WSFC).</span></span>
    
   - <span data-ttu-id="3e5ed-315">장애 조치 클러스터 관리 마법사에서 장애 **조치(failover)** 클러스터 관리를 마우스 **오른쪽** 단추로 클릭한 다음 클러스터 **만들기를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-315">In the **Failover Cluster Management** wizard, right-click **Failover Cluster Management**, then click **Create Cluster**.</span></span>
    
   - <span data-ttu-id="3e5ed-316">**시작하기 전에** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-316">On the **Before You Begin** page, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-317">클러스터 이름 및 IP 주소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-317">Add the cluster name and IP address.</span></span> <span data-ttu-id="3e5ed-318">설정의 유효성을 검사하면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-318">When the settings are validated, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-319">확인페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-319">On the Confirmation page, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-320">클러스터를 만든 후 마친 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-320">After the cluster is created, click **Finish**.</span></span>
    
4. <span data-ttu-id="3e5ed-321">파일 공유 미러링계를 사용하도록 클러스터 쿼럼 설정을 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-321">We recommend that you configure the cluster quorum settings to use a file share witness.</span></span> <span data-ttu-id="3e5ed-322">이렇게 하여 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-322">To do so, use these steps:</span></span>
    
   - <span data-ttu-id="3e5ed-323">클러스터 이름을 마우스 오른쪽 단추로 클릭하고 추가 **작업을** 클릭한 다음 클러스터 쿼럼 **설정 구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-323">Right-click the cluster name, click **More Actions**, and click **Configure Cluster Quorum Settings**.</span></span>
    
   - <span data-ttu-id="3e5ed-324">**쿼럼 구성** 옵션 선택 페이지에서 쿼럼 미러링계 **선택을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-324">In the **Select Quorum Configuration Option** page, click **Select the quorum witness**.</span></span>
    
   - <span data-ttu-id="3e5ed-325">**쿼럼 미러링 확인** 선택 페이지에서 파일 공유 미러링계 **구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-325">In the **Select Quorum Witness** page, click **Configure a file share witness**.</span></span>
    
   - <span data-ttu-id="3e5ed-326">파일 **공유** 미러링 금지 구성 페이지에서 사용할 파일 공유의 경로를 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-326">In the **Configure File Share Witness** page, type the path of the file share you want to use, and then click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-327">**확인** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-327">On the **Confirmation** page, click **Next**.</span></span>
    
5. <span data-ttu-id="3e5ed-328">클러스터의 각 서버에서 Configuration Manager에서 AG를 SQL Server 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-328">On each server in the cluster, enable AG in SQL Server Configuration Manager.</span></span>
    
   - <span data-ttu-id="3e5ed-329">SQL Server 구성 관리자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-329">Open SQL Server Configuration Manager.</span></span> <span data-ttu-id="3e5ed-330">화면 왼쪽의 트리에서 SQL Server 서비스를 클릭한 다음 서비스 SQL Server 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-330">In the tree on the left side of the screen, click **SQL Server Services**, then double-click the SQL Server service.</span></span> 
    
   - <span data-ttu-id="3e5ed-331">속성 **상자에서** **AlwaysOn 고가용성 탭을** 선택합니다. **AlwaysOn 가용성 그룹 사용 확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-331">In the **Properties** box, select the **AlwaysOn High Availability** tab. Select the **Enable AlwaysOn Availability Groups** check box.</span></span> <span data-ttu-id="3e5ed-332">메시지가 표시 SQL Server 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-332">Restart the SQL Server service when prompted.</span></span>
    
6. <span data-ttu-id="3e5ed-333">가용성 그룹을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-333">Create the availability group.</span></span>
    
   - <span data-ttu-id="3e5ed-334">이 SQL Server Management Studio 열고 SQL Server 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-334">Open SQL Server Management Studio, and connect to the SQL Server instance.</span></span>
    
   - <span data-ttu-id="3e5ed-335">개체 탐색기에서 **Always On 고가용성 폴더를 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-335">In Object Explorer, expand the **Always On High Availability** folder.</span></span> <span data-ttu-id="3e5ed-336">가용성 그룹 **폴더를** 마우스 오른쪽 단추로 클릭하고 새 가용성 그룹 **마법사를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-336">Right-click the **Availability Groups** folder and click **New Availability Group Wizard**.</span></span>
    
   - <span data-ttu-id="3e5ed-337">소개 **페이지가** 나타나면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-337">If the **Introduction** page appears, click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-338">가용성 그룹 **이름** 지정 페이지에서 가용성 그룹의 이름을 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-338">In the **Specify Availability Group Name** page, type the name of the Availability group, and click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-339">데이터베이스 선택 페이지에서 AG에 포함할 데이터베이스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-339">In the Select Databases page, select the databases that you want to include in the AG.</span></span> <span data-ttu-id="3e5ed-340">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-340">Then click **Next**.</span></span>
    
     <span data-ttu-id="3e5ed-341">이 시나리오에서는 지원되지 않는 **ReportServer,** **ReportServerTempDB** 또는 영구 채팅 데이터베이스를 AG에 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-341">Do not include the **ReportServer**, **ReportServerTempDB**, or Persistent Chat databases in the AG, as these are not supported in this scenario.</span></span> <span data-ttu-id="3e5ed-342">다른 모든 비즈니스용 Skype 서버 데이터베이스를 AG에 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-342">You can include all other Skype for Business Server databases in the AG.</span></span>
    
   - <span data-ttu-id="3e5ed-343">복제본 **지정 페이지에서** 복제 데이터베이스 **탭을** 클릭합니다. 그런 다음  복제본 추가 단추를 클릭하고 WSFC의 노드로 SQL 다른 SQL 인스턴스에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-343">In the **Specify Replicas** page, click the **Replicas** tab. Then click the **Add Replicas** button, and connect to the other SQL instances that you joined as nodes of the WSFC.</span></span>
    
   - <span data-ttu-id="3e5ed-344">각 인스턴스에 대해 자동 장애 **조치(Failover)** 및 **동기** 커밋 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-344">For each instance, select the **Automatic Failover** and **Synchronous Commit** options.</span></span> <span data-ttu-id="3e5ed-345">읽을 수 있는 보조 **옵션을 선택하지** 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-345">Do not select the **Readable Secondary** option.</span></span>
    
   - <span data-ttu-id="3e5ed-346">끝점 **탭을** 클릭하고  포트 번호가 5022로 설정되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-346">Click the **Endpoints** tab and verify that **Port Number** is set to 5022.</span></span>
    
   - <span data-ttu-id="3e5ed-347">수신기 **탭을 클릭하고** 가용성 그룹 수신기 **만들기 옵션을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-347">Click the **Listener** tab, and select the **Create an availability group listener** option.</span></span> <span data-ttu-id="3e5ed-348">이 옵션 아래에 수신기 이름을 입력하고 **포트를** 1433으로 설정합니다(이 옵션에 대해 다른 포트는 지원되지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="3e5ed-348">Under that option, type a name for the listener, and set the **Port** to 1433 (other ports are not supported for this option).</span></span>
    
   - <span data-ttu-id="3e5ed-349">**추가를** 클릭한 다음 **IPv4** 주소 상자에서 기본 설정 가상 IP 주소를 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-349">Click **Add**, and then in the **IPv4 Address** box, provide your preferred virtual IP address, and then click **OK**.</span></span>
    
   - <span data-ttu-id="3e5ed-350">초기 **데이터** 동기화 선택 페이지에서 전체를 선택하고 복제본에 액세스할 수 있는 폴더를 지정하고 두 복제본에서 사용하는 SQL Server 서비스 계정에 쓰기 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-350">In the **Select Initial Data Synchronization** page, select Full, and specify a folder that is accessible to the replicas, and that the SQL Server service account used by both replicas has Write permissions for.</span></span> <span data-ttu-id="3e5ed-351">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-351">Then click **Next**.</span></span>
    
     <span data-ttu-id="3e5ed-352">이 파일 공유는 데이터베이스를 초기화할 때 일시적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-352">This file share will be used temporarily when you initialize the databases.</span></span> <span data-ttu-id="3e5ed-353">대규모 데이터베이스를 사용하는 경우 네트워크 대역폭이 데이터베이스 백업의 크기를 수용할 수 없는 경우 수동으로 초기화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-353">If you are dealing with large databases, we recommend that you manually initialize them in case your network bandwidth cannot accommodate the size of the database backups.</span></span>
    
     - <span data-ttu-id="3e5ed-354">유효성 검사 페이지에서 모든 유효성 검사가 성공적이면 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-354">In the Validation page, verify that all validation checks are successful, then click **Next**.</span></span>
    
   - <span data-ttu-id="3e5ed-355">요약 **페이지에서** 모든 설정을 확인하고 마친을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-355">In the **Summary** page, verify all settings and click Finish.</span></span>
    
7. <span data-ttu-id="3e5ed-356">AG 수신기 지정을 지정하는 새 저장소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-356">Create a new store specifying the AG listener.</span></span>
    
   - <span data-ttu-id="3e5ed-357">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-357">Open Topology Builder.</span></span> <span data-ttu-id="3e5ed-358">토폴로지에서 공유 구성 요소를 확장하고 SQL Server 마우스 오른쪽 단추로 클릭한 다음 새 **저장소를 SQL Server 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-358">In your topology, expand **Shared Components**, right-click **SQL Server Stores**, and click **New SQL Server Store**.</span></span>
    
   - <span data-ttu-id="3e5ed-359">새 SQL **저장소** 정의 페이지에서 먼저 고가용성 설정 확인란을 선택한 다음 SQL AlwaysOn 가용성 그룹이 드롭다운 상자에 나타나는지 확인합니다. </span><span class="sxs-lookup"><span data-stu-id="3e5ed-359">In the **Define New SQL Store** page, first select the **High Availability Settings** check box, and then make sure that SQL AlwaysOn Availability Groups appears in the drop-down box.</span></span>
    
   - <span data-ttu-id="3e5ed-360">SQL Server **수신기 FQDN** 상자에 가용성 그룹을 만들 때 만든 수신기 FQDN을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-360">In the **SQL Server Availability Listener FQDN** box, type the FQDN of the listener you created when you created the availability group.</span></span>
    
   - <span data-ttu-id="3e5ed-361">SQL Server **FQDN** 상자에 AG 기본 노드의 FQDN을 입력하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-361">In the **SQL Server FQDN** box, type the FQDN of the primary node of the AG, and then click **OK**.</span></span>
    
8. <span data-ttu-id="3e5ed-362">새 Always On 가용성 그룹을 프런트 엔드 풀과 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-362">Associate the new Always On Availability Group with the Front End pool.</span></span>
    
   - <span data-ttu-id="3e5ed-363">토폴로지 작성기에서 AG에 연결하려면 풀을 마우스 오른쪽 단추로 클릭하고 속성 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-363">In Topology Builder, right-click the pool to associate with the AG, and click **Edit Properties**.</span></span>
    
   - <span data-ttu-id="3e5ed-364">**연결의** SQL Server **저장소** 상자에서 AG를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-364">Under **Associations**, in the **SQL Server Store** box, select the AG.</span></span> <span data-ttu-id="3e5ed-365">풀에서 AG로 이동할 다른 데이터베이스에 대해 동일한 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-365">Select the same group for any other databases in the pool which you want to move to the AG.</span></span>
    
   - <span data-ttu-id="3e5ed-366">필요한 모든 데이터베이스가 AG로 설정되어 있는지 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-366">When you're sure that all needed databases are set to the AG, click **OK**.</span></span>
    
9. <span data-ttu-id="3e5ed-367">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-367">Publish the topology.</span></span> <span data-ttu-id="3e5ed-368">작업 **메뉴에서** **토폴로지** 및 게시를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-368">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="3e5ed-369">그런 다음 확인 페이지에서 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-369">Then in the confirmation page click **Next**.</span></span>
    
10. <span data-ttu-id="3e5ed-370">AG의 각 복제본에 SQL 최종 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-370">Perform some final steps to make sure that the SQL logins are on each of the replicas in the AG.</span></span>
    
    - <span data-ttu-id="3e5ed-371">토폴로지 작성기 열기, 기존 배포에서 **토폴로지 다운로드를** 선택한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-371">Open Topology Builder, select **Download topology from existing deployment**, and click **OK**.</span></span>
    
    - <span data-ttu-id="3e5ed-372">비즈니스용 Skype 서버를 확장하고, 토폴로지 및 저장소를 **SQL Server 확장합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-372">Expand Skype for Business Server, expand your topology, and expand **SQL Server Stores**.</span></span> <span data-ttu-id="3e5ed-373">새 AG의 SQL 마우스 오른쪽 단추로 클릭하고 **속성 편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-373">Right-click the SQL store of the new AG, and click **Edit Properties**.</span></span>
    
    - <span data-ttu-id="3e5ed-374">페이지 아래쪽의 SQL Server **FQDN** 상자에서 값을 AG 수신기 FQDN으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-374">At the bottom of the page, in the **SQL Server FQDN** box, change the value to the FQDN of the Listener of the AG.</span></span>
    
    - <span data-ttu-id="3e5ed-375">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-375">Publish the topology.</span></span> <span data-ttu-id="3e5ed-376">작업 **메뉴에서** **토폴로지** 및 게시를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-376">From the **Action** menu click **Topology** and then **Publish**.</span></span> <span data-ttu-id="3e5ed-377">그런 다음 확인 페이지에서 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="3e5ed-377">Then in the confirmation page click **Next**.</span></span> <span data-ttu-id="3e5ed-378">그런 다음 새 토폴로지가 복제될 때까지 몇 분 정도 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-378">Then wait a few minutes for the new topology to replicate.</span></span>
    
    - <span data-ttu-id="3e5ed-379">사용자 SQL Server Management Studio 열고 AG로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-379">Open SQL Server Management Studio, and navigate to the AG.</span></span> <span data-ttu-id="3e5ed-380">보조 복제본으로 장애 조치(fail over)합니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-380">Fail it over to a secondary replica.</span></span>
    
    - <span data-ttu-id="3e5ed-381">비즈니스용 Skype 서버 관리 셸을 열고 다음 cmdlet을 입력하여 이 SQL 로그인을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e5ed-381">Open Skype for Business Server Management Shell and type the following cmdlet to create the SQL logins on this replica:</span></span>
    
      ```powershell
      Install-CsDatabase -Update
      ```

      - <span data-ttu-id="3e5ed-382">그룹의 각 복제본에 대해 이전 두 단계를 반복합니다(그룹을 보조 복제본으로 장애 조치한 다음  `Install-CsDatabase -Update` 사용).</span><span class="sxs-lookup"><span data-stu-id="3e5ed-382">Repeat the previous two steps (fail over the group to a secondary replica, then use  `Install-CsDatabase -Update`) for each replica in the group.</span></span>
