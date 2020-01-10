---
title: 비즈니스용 Skype 서버 2015로 업그레이드
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 74ce73bc-356b-4705-83b1-341ee010fd19
description: '요약: Lync Server 2013에서 비즈니스용 Skype Server 2015으로 업그레이드 하는 방법에 대해 알아봅니다. Microsoft 평가 센터에서 비즈니스용 Skype Server 2015의 무료 평가판을 다운로드 https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server하세요.'
ms.openlocfilehash: d9ce950ead8b8a3a8857c53d421470a0e647ea23
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001878"
---
# <a name="upgrade-to-skype-for-business-server-2015"></a><span data-ttu-id="85a7b-104">비즈니스용 Skype 서버 2015로 업그레이드</span><span class="sxs-lookup"><span data-stu-id="85a7b-104">Upgrade to Skype for Business Server 2015</span></span>
 
<span data-ttu-id="85a7b-105">**요약:** Lync Server 2013에서 비즈니스용 Skype Server 2015으로 업그레이드 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-105">**Summary:** Learn how to upgrade from Lync Server 2013 to Skype for Business Server 2015.</span></span> <span data-ttu-id="85a7b-106">[Microsoft 평가 센터](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)에서 비즈니스용 Skype 서버 2015 무료 평가판을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="85a7b-106">Download a free trial of Skype for Business Server 2015 from the  [Microsoft Evaluation center](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="85a7b-107">비즈니스용 Skype 서버 토폴로지 작성기 및 새로운 현재 업그레이드 기능을 사용 하 여 Lync Server 2013에서 비즈니스용 Skype Server 2015으로 업그레이드 하려면이 문서의 절차를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-107">Use the procedures in this document to upgrade from Lync Server 2013 to Skype for Business Server 2015 by using the Skype for Business Server Topology Builder and the new In-Place Upgrade feature.</span></span> <span data-ttu-id="85a7b-108">Lync Server 2010 또는 Office Communications Server 2007 R2에서 업그레이드 하려는 경우 [비즈니스용 Skype Server 2015으로 업그레이드 계획](../plan-your-deployment/upgrade.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85a7b-108">If you want to upgrade from Lync Server 2010 or Office Communications Server 2007 R2, see [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>

> [!NOTE]
> <span data-ttu-id="85a7b-109">현재 위치 업그레이드는 비즈니스용 Skype 서버 2015에서 사용할 수 있었지만 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-109">In-place upgrades were available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="85a7b-110">나란히 coexistance 지원 되는 경우 자세한 내용은 [비즈니스용 Skype 서버 2019 마이그레이션을](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85a7b-110">Side by side coexistance is supported, see [Migration to Skype for Business Server 2019](../../SfBServer2019/migration/migration-to-skype-for-business-server-2019.md) for more information.</span></span>
  
## <a name="upgrade-from-lync-server-2013"></a><span data-ttu-id="85a7b-111">Lync Server 2013에서 업그레이드</span><span class="sxs-lookup"><span data-stu-id="85a7b-111">Upgrade from Lync Server 2013</span></span>

<span data-ttu-id="85a7b-112">Lync Server 2013을 비즈니스용 Skype Server 2015으로 업그레이드 하는 경우 비즈니스용 Skype Server 토폴로지 작성기를 사용 하 여 풀의 데이터베이스를 업그레이드 하 고 각각의 비즈니스용 Skype Server의 현재 위치 업그레이드를 사용 하 여 필수 소프트웨어를 설치 해야 합니다. 풀과 연결 된 서버</span><span class="sxs-lookup"><span data-stu-id="85a7b-112">Upgrading Lync Server 2013 to Skype for Business Server 2015 involves installing prerequisite software, using the Skype for Business Server Topology Builder to upgrade databases in the pool, and using the Skype for Business Server In-Place Upgrade on each of the servers associated with the pool.</span></span> <span data-ttu-id="85a7b-113">업그레이드를 완료 하려면이 항목의 8 단계를 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-113">To complete the upgrade, go through the eight steps in this topic.</span></span>
  
### <a name="before-you-begin"></a><span data-ttu-id="85a7b-114">시작 하기 전에</span><span class="sxs-lookup"><span data-stu-id="85a7b-114">Before you begin</span></span>

- <span data-ttu-id="85a7b-115">[비즈니스용 Skype 서버 2015 업그레이드 계획을](../plan-your-deployment/upgrade.md)검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-115">Review [Plan to upgrade to Skype for Business Server 2015](../plan-your-deployment/upgrade.md).</span></span>
    
- <span data-ttu-id="85a7b-116">[비즈니스용 Skype 서버 2015에 대 한 서버 요구 사항을](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-116">Review [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="85a7b-117">[비즈니스용 Skype 서버 2015에 대 한 필수 구성 요소를 설치](install/install-prerequisites.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-117">[Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md) .</span></span>
    
- <span data-ttu-id="85a7b-118">[비즈니스용 Skype 서버 2015을 설치](install/install.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-118">[Install Skype for Business Server 2015](install/install.md) .</span></span>
    
### <a name="step-1-install-administrator-tools-and-download-topology"></a><span data-ttu-id="85a7b-119">1 단계: 관리자 도구 설치 및 토폴로지 다운로드</span><span class="sxs-lookup"><span data-stu-id="85a7b-119">Step 1: Install Administrator tools and download topology</span></span>

1. <span data-ttu-id="85a7b-120">Lync OCSCore 또는 다른 Lync 구성 요소가 설치 되지 않은 토폴로지에서 컴퓨터에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-120">Connect to computer in the topology that does not have Lync OCSCore or any other Lync components installed.</span></span>
    
2. <span data-ttu-id="85a7b-121">비즈니스용 Skype Server 2015 설치 미디어에서 **setup.exe** **OCS_Volume \setup\amd64**를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-121">From Skype for Business Server 2015 installation media, run **Setup.exe** from **OCS_Volume\Setup\AMD64**.</span></span> 
    
3. <span data-ttu-id="85a7b-122">**설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-122">Click **Install**.</span></span> 
    
4. <span data-ttu-id="85a7b-123">사용권 계약에 동의 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-123">Accept the license agreement.</span></span>
    
5. <span data-ttu-id="85a7b-124">배포 마법사에서 **관리자 도구 설치**를 클릭 하 고 설치 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-124">On the Deployment Wizard, click **Install Administrator tools**, and follow the steps to install.</span></span>
    
     ![' 관리자 설치 ' 도구에 대 한 링크가 포함 된 배포 마법사 스크린샷](../media/5bbac2d6-a5b3-42b4-a243-7bcf2b04477a.png)
  
6. <span data-ttu-id="85a7b-126">Windows 시작 화면에서 비즈니스용 Skype 서버 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-126">From the Windows Start screen, open Skype for Business Server Topology Builder.</span></span>
    
7. <span data-ttu-id="85a7b-127">**기존 배포에서 토폴로지 다운로드**를 클릭 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-127">Click **Download topology from existing deployment**, and click **Next**.</span></span>
    
8. <span data-ttu-id="85a7b-128">토폴로지의 이름을 입력 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-128">Enter a name for the topology, and click **Save**.</span></span>
    
9. <span data-ttu-id="85a7b-129">토폴로지를 저장 한 위치로 이동 하 여 토폴로지의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-129">Go to location where you saved the topology, and make a copy of the topology.</span></span>
    
### <a name="step-2-upgrade-and-publish-topology-using-topology-builder"></a><span data-ttu-id="85a7b-130">2 단계: 토폴로지 작성기를 사용 하 여 토폴로지 업그레이드 및 게시</span><span class="sxs-lookup"><span data-stu-id="85a7b-130">Step 2: Upgrade and publish topology using Topology Builder</span></span>

<span data-ttu-id="85a7b-131">업그레이드 프로세스를 시작 하기 전에 업그레이드 하려는 풀에 대해 모든 서비스가 실행 중 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-131">Before you start the upgrade process, all services must be running for the pools you plan to upgrade.</span></span> <span data-ttu-id="85a7b-132">이렇게 하면 토폴로지 변경 내용이 풀에 있는 서버의 로컬 데이터베이스에 복제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-132">This is so the topology changes will be replicated to the local database of the servers in the pool.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="85a7b-133">업그레이드 하기 전에 토폴로지 파일의 복사본을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-133">Save a copy of your topology file before you upgrade.</span></span> <span data-ttu-id="85a7b-134">업그레이드 한 후에는 토폴로지를 다운 그레이드할 수 없습니다. 서비스가 데이터베이스와 같은 서버에 있는 경우 > 영구 채팅 서비스는 영구 채팅 데이터베이스와 같은 서버에 있으므로이 단계를 건너뛰고 4 단계로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-134">After you upgrade, you will not be able to downgrade the topology.>  If your services are on the same servers as your databases, like the Persistent Chat service is on the same server as the Persistent Chat database, skip this step, and go to step 4.</span></span> <span data-ttu-id="85a7b-135">서비스를 중지 한 후 각 서버에서 현재 위치 업그레이드 설정을 실행 하 여 로컬 데이터베이스를 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-135">After you stop the services, run the In-Place Upgrade setup on each server to upgrade the local databases.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85a7b-136">토폴로지에 미러링 되는 백 엔드 데이터베이스가 있는 경우 토폴로지 작성기를 사용 하 여 **토폴로지를 게시** 하면 주 데이터베이스와 미러된 데이터베이스가 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-136">If the topology has a back-end database that is mirrored then you will see both the Principal and the Mirrored databases show up **when you publish the topology** using Topology Builder.</span></span> <span data-ttu-id="85a7b-137">모든 데이터베이스가 주 서버에서 실행 되 고 있는지 확인 하 고 토폴로지를 게시할 때는 토폴로지가 아닌 사용자만 선택 하 고 토폴로지를 게시 한 후에는 경고가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-137">Make sure all of the databases are running on the Principal and only select the Principal, not the mirror, when publishing the topology otherwise you will see a warning after publishing the topology.</span></span>
  
<span data-ttu-id="85a7b-138">다음 옵션 중 하나를 선택 하 여 비즈니스용 Skype 서버 2015 토폴로지 작성기를 사용 하 여 새 토폴로지를 업그레이드 하 고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-138">Pick one of the options below to upgrade and publish a new topology by using the Skype for Business Server 2015 Topology Builder.</span></span> <span data-ttu-id="85a7b-139">단계를 완료 하 고 업데이트 된 토폴로지를 게시 한 후에는이 항목의 3 단계로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-139">After you complete the steps and publish the updated topology, move to Step 3 in this topic.</span></span>
  
#### <a name="option-1-upgrade-an-isolated-front-end-pool-and-associated-archiving-and-monitoring-stores"></a><span data-ttu-id="85a7b-140">옵션 1: isolated 프런트 엔드 풀 및 연결 된 보관 및 모니터링 저장소 업그레이드</span><span class="sxs-lookup"><span data-stu-id="85a7b-140">Option 1: Upgrade an isolated Front End pool and associated Archiving and Monitoring stores</span></span>

<span data-ttu-id="85a7b-141">업그레이드 하는 풀에 보관 및 모니터링 저장소 종속성이 있는 경우 다음 단계를 사용할 때 보관 및 모니터링 저장소도 업그레이드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-141">If the pool you're upgrading has an Archiving and Monitoring store dependency, when you use the following steps, the Archiving and Monitoring store will be upgraded as well.</span></span>
  
1. <span data-ttu-id="85a7b-142">토폴로지 작성기에서 Lync Server 2013 풀을 마우스 오른쪽 단추로 클릭 하 고 **비즈니스용 Skype Server 2015으로 업그레이드**를 선택 하 고 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-142">In Topology Builder, right-click a Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Lync Server 2013의 업그레이드 옵션을 사용 하 여 마우스 오른쪽 단추 클릭 메뉴 스크린샷](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
2. <span data-ttu-id="85a7b-144">토폴로지 작성기에서 **작업** > **게시 토폴로지** 또는 **작업** > **토폴로지** > **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-144">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
     ![토폴로지 작성기의 게시 토폴로지 옵션이 있는 작업 메뉴 스크린샷](../media/d6712634-9205-401f-a0b0-3ea096ca51bf.png)
  
3. <span data-ttu-id="85a7b-146">게시 하는 동안 보관 및 모니터링 저장소에 데이터베이스를 설치 하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-146">During publishing, choose to install a database on the Archiving and Monitoring store.</span></span>
    
#### <a name="option-2-upgrade-front-end-pool-without-upgrading-archiving-and-monitoring-stores"></a><span data-ttu-id="85a7b-147">옵션 2: 보관 및 모니터링 저장소를 업그레이드 하지 않고 프런트 엔드 풀 업그레이드</span><span class="sxs-lookup"><span data-stu-id="85a7b-147">Option 2: Upgrade Front End pool without upgrading Archiving and Monitoring stores</span></span>

<span data-ttu-id="85a7b-148">다음 단계를 사용 하는 경우 선택한 풀에 대 한 보관 및 모니터링을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-148">If you use the following steps, archiving and monitoring for the selected pool are disabled.</span></span> <span data-ttu-id="85a7b-149">업그레이드 후에는 풀에 보관 및 모니터링 저장소가 남아 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-149">The pool will not have Archiving and Monitoring stores after the upgrade.</span></span>
  
1. <span data-ttu-id="85a7b-150">토폴로지 작성기에서 업그레이드 하려는 Lync Server 2013 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-150">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span>
    
2. <span data-ttu-id="85a7b-151">Lync Server 2013 보관 및 모니터링 저장소에 대 한 종속성을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-151">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="85a7b-152">**작업** > 으로 이동**속성을 편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-152">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="85a7b-153">**보관** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-153">Clear the **Archiving** check box.</span></span>
    
     ![속성 편집 대화 상자의 보관 확인란 스크린샷](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="85a7b-155">**모니터링** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-155">Clear the **Monitoring** check box.</span></span>
    
     ![모니터링 확인란을 showsr 하는 속성 편집 대화 상자의 스크린샷](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="85a7b-157">Lync Server 2013 풀을 마우스 오른쪽 단추로 클릭 하 고 **비즈니스용 Skype Server 2015으로 업그레이드**를 선택 하 고 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-157">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Lync Server 2013의 업그레이드 옵션을 사용 하 여 마우스 오른쪽 단추 클릭 메뉴 스크린샷](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="85a7b-159">토폴로지 작성기에서 **작업** > **게시 토폴로지** 또는 **작업** > **토폴로지** > **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-159">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
#### <a name="option-3-upgrade-front-end-pool-and-associated-it-to-new-skype-for-business-server-2015-archiving-and-monitoring-stores"></a><span data-ttu-id="85a7b-160">옵션 3: 프런트 엔드 풀을 업그레이드 하 고 새 비즈니스용 Skype 서버 2015 보관 및 모니터링 저장소에 연결</span><span class="sxs-lookup"><span data-stu-id="85a7b-160">Option 3: Upgrade Front End pool and associated it to new Skype for Business Server 2015 Archiving and Monitoring stores</span></span>

<span data-ttu-id="85a7b-161">다음 단계를 사용 하는 경우 보관 및 모니터링이 이전 스토어에서 중지 되 고 만든 새 상점에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-161">If you use the following steps, archiving and monitoring will stop in the previous store and start in the new store you've created.</span></span> 
  
1. <span data-ttu-id="85a7b-162">토폴로지 작성기에서 업그레이드 하려는 Lync Server 2013 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-162">In Topology Builder, select the Lync Server 2013 pool that you want to upgrade.</span></span> 
    
2. <span data-ttu-id="85a7b-163">Lync Server 2013 보관 및 모니터링 저장소에 대 한 종속성을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-163">Remove the dependency to the Lync Server 2013 Archiving and Monitoring stores.</span></span> 
    
   - <span data-ttu-id="85a7b-164">**작업** > 으로 이동**속성을 편집**합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-164">Go to **Action** > **Edit properties**.</span></span>
    
   - <span data-ttu-id="85a7b-165">**보관** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-165">Clear the **Archiving** check box.</span></span>
    
     ![속성 편집 대화 상자의 보관 확인란 스크린샷](../media/9a88427e-80ee-49d0-a767-809fa9a5faf1.png)
  
   - <span data-ttu-id="85a7b-167">**모니터링** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-167">Clear the **Monitoring** check box.</span></span>
    
     ![모니터링 확인란을 showsr 하는 속성 편집 대화 상자의 스크린샷](../media/880acf33-57bb-4521-8717-cf5b67261ed4.png)
  
3. <span data-ttu-id="85a7b-169">Lync Server 2013 풀을 마우스 오른쪽 단추로 클릭 하 고 **비즈니스용 Skype Server 2015으로 업그레이드**를 선택 하 고 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-169">Right-click the Lync Server 2013 pool, select **Upgrade to Skype for Business Server 2015**, and follow the steps.</span></span> 
    
     ![Lync Server 2013의 업그레이드 옵션을 사용 하 여 마우스 오른쪽 단추 클릭 메뉴 스크린샷](../media/7d5b25b1-e5c0-474c-a024-a5ba33f1b3a1.png)
  
4. <span data-ttu-id="85a7b-171">보관을 위한 새 SQL 저장소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-171">Create a new SQL store for Archiving.</span></span> 
    
   - <span data-ttu-id="85a7b-172">풀 및 **작업** > **편집 속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-172">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="85a7b-173">**보관** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-173">Select the **Archiving** check box.</span></span>
    
   - <span data-ttu-id="85a7b-174">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-174">Click **New**.</span></span>
    
     ![보관 섹션의 새로 만들기 단추를 표시 하는 속성 편집 대화 상자의 스크린샷](../media/3a4a18e7-8251-4736-837c-2b486f64f896.png)
  
5. <span data-ttu-id="85a7b-176">모니터링을 위해 새 SQL 저장소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-176">Create a new SQL store for Monitoring.</span></span> 
    
   - <span data-ttu-id="85a7b-177">풀 및 **작업** > **편집 속성**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-177">Select the pool and **Action** > **Edit properties**.</span></span> 
    
   -  <span data-ttu-id="85a7b-178">**모니터링** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-178">Select the **Monitoring** check box.</span></span>
    
   - <span data-ttu-id="85a7b-179">**새로 만들기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-179">Click **New**.</span></span>
    
     ![모니터링 섹션 아래에 새로 만들기 단추가 표시 되는 속성 편집 대화 상자 스크린샷](../media/729c72a7-0068-4e0d-99dc-e480a6bfbf1d.png)
  
6. <span data-ttu-id="85a7b-181">토폴로지 작성기에서 **작업** > **게시 토폴로지** 또는 **작업** > **토폴로지** > **게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-181">In Topology Builder, click **Action** > **Publish topology** or **Action** > **Topology** > **Publish**.</span></span> 
    
7. <span data-ttu-id="85a7b-182">게시 하는 동안 새 보관 및 모니터링 저장소에 데이터베이스를 설치 하도록 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-182">During publishing, choose to install the database on the new Archiving and Monitoring store.</span></span>
    
### <a name="step-3-wait-for-replication"></a><span data-ttu-id="85a7b-183">3 단계: 복제 대기</span><span class="sxs-lookup"><span data-stu-id="85a7b-183">Step 3: Wait for replication</span></span>

<span data-ttu-id="85a7b-184">복제를 통해 환경의 모든 서버에 업데이트 된 토폴로지를 게시할 시간을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-184">Give replication some time to publish the updated topology to all the servers in the environment.</span></span>
  
### <a name="step-4-stop-all-services-in-pool-to-be-upgraded"></a><span data-ttu-id="85a7b-185">4 단계: 풀에서 업그레이드할 모든 서비스 중지</span><span class="sxs-lookup"><span data-stu-id="85a7b-185">Step 4: Stop all services in pool to be upgraded</span></span>

<span data-ttu-id="85a7b-186">업그레이드할 풀을 서비스 하는 각 서버에서 PowerShell에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-186">On each server that is servicing the pool that you're going to upgrade, run the following cmdlet in PowerShell:</span></span>
  
```powershell
Disable-CsComputer -Scorch
```

<span data-ttu-id="85a7b-187">현재 위치 업그레이드 프로세스를 진행 하는 동안 서버를 다시 부팅 해야 할 수 있으므로, Disable-CsComputer를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-187">We recommend using Disable-CsComputer because you may need to reboot the server during the In-Place Upgrade process.</span></span> <span data-ttu-id="85a7b-188">CsWindowsService를 사용 하는 경우 재부팅 후 일부 서비스가 자동으로 다시 시작 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-188">If you use Stop-CsWindowsService, some services may restart automatically after a reboot.</span></span> <span data-ttu-id="85a7b-189">이로 인해 현재 위치 업그레이드가 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-189">This may cause the In-Place Upgrade to fail.</span></span>
  
### <a name="step-5-upgrade-front-end-pools-and-non-front-end-pool-servers"></a><span data-ttu-id="85a7b-190">5 단계: 프런트 엔드 풀 및 비 프런트 엔드 풀 서버 업그레이드</span><span class="sxs-lookup"><span data-stu-id="85a7b-190">Step 5: Upgrade Front End pools and non-Front End pool servers</span></span>

> [!NOTE]
>  <span data-ttu-id="85a7b-191">업그레이드 하기 전에, 다음을 포함 하는 비즈니스용 Skype 서버 2015에 필요한 새 필수 구성 요소를 모두 설치 하세요. 업그레이드를 시도 하기 전에 최소한 32GB의 여유 공간이 >.</span><span class="sxs-lookup"><span data-stu-id="85a7b-191">Before upgrading please install all new prerequisites required for Skype for Business Server 2015 which include:>  At least 32GB of free space before attempting an upgrade.</span></span> <span data-ttu-id="85a7b-192">또한 드라이브가 고정 로컬 드라이브이 고 USB 또는 Firewire로 연결 되어 있지 않은지 확인 합니다 .은 (는) NTFS 파일 시스템으로 포맷 되었으며, 압축 되지 않고 페이지 파일이 포함 되어 있지 않습니다. > 최신 Lync Server 2013 누적 업데이트를 설치 합니다. > SQL Server 2012 SP1이 설치 되어 있습니다. Microsoft 업데이트를 사용 하는 경우 자동으로 설치 되는 다음 KB가 설치 된 > > windows server 2008 R2-[KB2533623](https://support.microsoft.com/kb/2533623) > windows server 2012-[KB2858668](https://support.microsoft.com/kb/2858668)> windows server 2012 r2- [KB2982006](https://support.microsoft.com/kb/2982006)</span><span class="sxs-lookup"><span data-stu-id="85a7b-192">In addition, make sure that the drive is a fixed local drive, is not connected by USB or Firewire, is formatted with NTFS file system, is not compressed, and does not contain a page file.>  PowerShell version 6.2.9200.0 or later.>  The latest Lync Server 2013 Cumulative Update installed.>  SQL Server 2012 SP1 installed.>  The following KB's installed (installed automatically if using Microsoft Update):>  Windows Server 2008 R2 -[KB2533623](https://support.microsoft.com/kb/2533623)>  Windows Server 2012 -[KB2858668](https://support.microsoft.com/kb/2858668)>  Windows Server 2012 R2 -[KB2982006](https://support.microsoft.com/kb/2982006)</span></span>
  
<span data-ttu-id="85a7b-193">각 서버의 현재 위치 업그레이드를 사용 하 여 프런트 엔드 풀, Edge 풀, 중재 서버 및 영구 채팅 풀을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-193">Use the In-Place Upgrade on each server to update the Front End pool, Edge pool, Mediation server, and the Persistent Chat pool.</span></span>
  
1. <span data-ttu-id="85a7b-194">각 서버에서 \Setup\amd64는 비즈니스용 Skype 서버 2015 설치 미디어의 **OCS_Volume** 에서 setup.exe를 실행 **합니다** .</span><span class="sxs-lookup"><span data-stu-id="85a7b-194">On each server, run **Setup.exe** from **OCS_Volume\Setup\amd64** on the Skype for Business Server 2015 installation media.</span></span>
    
2. <span data-ttu-id="85a7b-195">사용권 계약에 동의 하 고 현재 위치 업그레이드에 대 한 메시지를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-195">Accept the license agreement and follow the prompts for the In-Place Upgrade.</span></span>
    
3. <span data-ttu-id="85a7b-196">프런트 엔드 풀 및 각 비 프런트 엔드 풀 서버의 각 서버에 대해이 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-196">Repeat these steps for each server in the Front End pool and on each non-Front End pool server.</span></span>
    
> [!NOTE]
> <span data-ttu-id="85a7b-197">현재 위치 업그레이드 중에 서버를 다시 부팅 하 라는 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-197">You might be prompted to reboot the server during the In-Place Upgrade.</span></span> <span data-ttu-id="85a7b-198">괜찮아요.</span><span class="sxs-lookup"><span data-stu-id="85a7b-198">That's ok.</span></span> <span data-ttu-id="85a7b-199">다시 부팅 한 후에는 즉시 업그레이드를 계속 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-199">After you reboot, the In-Place Upgrade will continue from where it left off.</span></span> 
  
<span data-ttu-id="85a7b-200">현재 위치 업그레이드가 성공적으로 완료 되 면 다음 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-200">When the In-Place Upgrade completes successfully, you see the following message.</span></span>
  
![현재 위치 업그레이드를 성공적으로 완료 하 고 표시 하는 스크린샷.](../media/2f52cb50-9bb4-4714-a982-9c7a0865f78a.png)
  
### <a name="step-6-restart-services-on-all-upgraded-servers"></a><span data-ttu-id="85a7b-202">6 단계: 업그레이드 된 모든 서버에서 서비스 다시 시작</span><span class="sxs-lookup"><span data-stu-id="85a7b-202">Step 6: Restart services on all upgraded servers</span></span>

> [!NOTE]
> <span data-ttu-id="85a7b-203">서비스를 다시 시작 하기 전에 모든 프런트 엔드 서버 에%ProgramData%\WindowsFabric이 없는지 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="85a7b-203">Before restarting the services, please make sure %ProgramData%\WindowsFabric doesn't exist on all Front End Servers.</span></span> <span data-ttu-id="85a7b-204">서비스가 있는 경우 서비스를 시작 하기 전에 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-204">If it exists, delete it before starting the services.</span></span> 
  
- <span data-ttu-id="85a7b-205">프런트 엔드 풀의 모든 서버를 업그레이드 한 후 다음 PowerShell 명령을 사용 하 여 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-205">After you've upgraded all servers in the Front End pool, restart the services by using the following PowerShell command:</span></span> 
    
  ```powershell
  Start-CsPool
  ```

    > [!NOTE]
    > <span data-ttu-id="85a7b-206">현재 위치 업그레이드를 시작 하기 전에 이미 시스템을 다시 부팅 해야 하는 경우 현재 위치 업그레이드는 설치 종료 시 재부팅을 요청 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-206">If there is already a pending system reboot needed before you start running In-Place Upgrade, then In-Place Upgrade won't ask you to reboot at the end of the installation.</span></span> <span data-ttu-id="85a7b-207">이렇게 하면 시작-CSPool cmdlet을 사용 하 여 서비스를 시작 하려고 할 때 첫 번째 프런트 엔드 서버에 대해 일부 어셈블리 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-207">This will cause some assembly exceptions to be thrown against the first Front End server when you try to start services using the Start-CSPool cmdlet.</span></span> <span data-ttu-id="85a7b-208">이러한 오류를 해결 하려면 풀의 모든 서버를 다시 부팅 하 고 cmdlet을 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-208">To resolve these errors, reboot all of the servers in the pool and run the cmdlet again.</span></span> 
  
- <span data-ttu-id="85a7b-209">프런트 엔드 이외의 풀 서버에서 다음 명령을 사용 하 여 서비스를 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-209">On the non-Front End pool servers, restart the services by using the following command:</span></span>
    
  ```powershell
  Start-CsWindowsService
  ```

<span data-ttu-id="85a7b-210">현재 위치 업그레이드 페이지에서 **확인** 을 클릭 하면 다음 미리 알림이 표시 되어이 단계를 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-210">After you click **OK** on the In-Place Upgrade page, you'll see the following reminder to complete this step.</span></span>
  
![현재 위치 업그레이드가 성공적으로 완료 되 면 다음 단계를 보여 주는 스크린샷](../media/6a7236b6-9ef9-4df3-8682-b0e4021810f9.png)
  
### <a name="step-7-verify-skype-for-business-functionality-works"></a><span data-ttu-id="85a7b-212">7 단계: 비즈니스용 Skype 기능이 작동 하는지 확인</span><span class="sxs-lookup"><span data-stu-id="85a7b-212">Step 7: Verify Skype for Business functionality works</span></span>

<span data-ttu-id="85a7b-213">업그레이드의 성공 여부를 확인 하려면 업그레이드 된 풀에 대해 비즈니스용 Skype를 테스트 하 여 기능이 예상 대로 작동 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-213">To make sure the upgrade was successful, for the pool that was upgraded, test Skype for Business to make sure the functionality is working as expected.</span></span> 
  
### <a name="step-8-upgrade-secondary-pools"></a><span data-ttu-id="85a7b-214">8 단계: 보조 풀 업그레이드</span><span class="sxs-lookup"><span data-stu-id="85a7b-214">Step 8: Upgrade secondary pools</span></span>

<span data-ttu-id="85a7b-215">이 항목의 단계를 반복 하 여 환경에 보유 하 고 있는 추가 풀을 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-215">Repeat the steps in this topic to upgrade any additional pools that you have in your environment.</span></span>
  
## <a name="troubleshoot-issues-with-the-in-place-upgrade"></a><span data-ttu-id="85a7b-216">현재 위치 업그레이드 문제 해결</span><span class="sxs-lookup"><span data-stu-id="85a7b-216">Troubleshoot issues with the In-Place Upgrade</span></span>

<span data-ttu-id="85a7b-217">현재 위치 업그레이드에 실패 하면 다음 이미지와 비슷한 메시지가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-217">If the In-Place Upgrade fails, you might see a message similar to what's in the following image.</span></span> 
  
![필요한 누적 업데이트가 설치 되어 있지 않아 현재 위치 업그레이드에 실패 하는 스크린샷.](../media/f84db06b-0841-45a9-870d-7ba4b5a463d5.png)
  
<span data-ttu-id="85a7b-219">페이지의 맨 아래에 있는 전체 메시지를 검토 하 여 문제 해결을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-219">Review the full message at the bottom of the page to help you troubleshoot the issue.</span></span> <span data-ttu-id="85a7b-220">자세한 정보를 보려면 **로그 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-220">Click **View logs** to get more detail.</span></span>
  
<span data-ttu-id="85a7b-221">**업그레이드 준비를 확인** 하거나 **누락 된 필수 구성 요소를 설치**하는 동안 현재 위치 업그레이드에 실패 하는 경우 서버에 모든 최신 Windows server, Lync server, SQL server 업데이트가 적용 되었는지 확인 하 고 필요한 모든 소프트웨어와 역할이 설치 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="85a7b-221">If the In-Place Upgrade fails on **Verifying upgrade readiness** or **Installing missing prerequisites**, make sure the server has all the latest Windows Server, Lync Server, and SQL Server updates applied, and all the required software and roles are installed.</span></span> <span data-ttu-id="85a7b-222">필수 사항 목록은 비즈니스용 [Skype server 2015의 서버 요구 사항](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 및 비즈니스용 [skype server 2015의 필수 구성 요소 설치](install/install-prerequisites.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="85a7b-222">For a list of what's required, see [Server requirements for Skype for Business Server 2015](../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Install prerequisites for Skype for Business Server 2015](install/install-prerequisites.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="85a7b-223">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85a7b-223">See also</span></span>

[<span data-ttu-id="85a7b-224">비즈니스용 Skype 서버 2015 업그레이드 계획</span><span class="sxs-lookup"><span data-stu-id="85a7b-224">Plan to upgrade to Skype for Business Server 2015</span></span>](../plan-your-deployment/upgrade.md)
  
[<span data-ttu-id="85a7b-225">비즈니스용 Skype 서버 2015의 서버 요구 사항</span><span class="sxs-lookup"><span data-stu-id="85a7b-225">Server requirements for Skype for Business Server 2015</span></span>](../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[<span data-ttu-id="85a7b-226">비즈니스용 Skype 서버 2015에 대 한 필수 구성 요소 설치</span><span class="sxs-lookup"><span data-stu-id="85a7b-226">Install prerequisites for Skype for Business Server 2015</span></span>](install/install-prerequisites.md)
  
[<span data-ttu-id="85a7b-227">비즈니스용 Skype 서버 2015 설치</span><span class="sxs-lookup"><span data-stu-id="85a7b-227">Install Skype for Business Server 2015</span></span>](install/install.md)
