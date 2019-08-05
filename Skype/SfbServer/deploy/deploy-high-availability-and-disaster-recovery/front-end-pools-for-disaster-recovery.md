---
title: 비즈니스용 Skype 서버에서 재해 복구용으로 쌍을 이루는 프런트 엔드 풀 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 페어링 된 프런트 엔드 풀을 사용 하 여 재해 복구 보호를 제공 하기로 결정할 수 있지만, 반드시 그럴 필요는 없습니다.
ms.openlocfilehash: 49af49a4a8ff3dd0f543de6f1b13bfbe5b571788
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196971"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a><span data-ttu-id="978e3-103">비즈니스용 Skype 서버에서 재해 복구용으로 쌍을 이루는 프런트 엔드 풀 배포</span><span class="sxs-lookup"><span data-stu-id="978e3-103">Deploy paired Front End pools for disaster recovery in Skype for Business Server</span></span>
 
<span data-ttu-id="978e3-104">페어링 된 프런트 엔드 풀을 사용 하 여 재해 복구 보호를 제공 하기로 결정할 수 있지만, 반드시 그럴 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-104">You may decide to use paired Front End pools to provide disaster recovery protection, but doing so is not a requirement.</span></span>
  
<span data-ttu-id="978e3-105">토폴로지 작성기를 사용 하 여 페어링 된 프런트 엔드 풀의 장애 복구 토폴로지를 쉽게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-105">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span> 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="978e3-106">프런트 엔드 풀 쌍을 배포 하려면</span><span class="sxs-lookup"><span data-stu-id="978e3-106">To deploy a pair of Front End pools</span></span>

1. <span data-ttu-id="978e3-107">풀이 신규이 고 아직 정의 되지 않은 경우 토폴로지 작성기를 사용 하 여 풀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-107">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>
    
2. <span data-ttu-id="978e3-108">토폴로지 작성기에서 두 풀 중 하나를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-108">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="978e3-109">왼쪽 창에서 **복구 력을** 클릭 한 다음 오른쪽 창에서 **연결 된 백업 풀** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-109">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>
    
4. <span data-ttu-id="978e3-110">**연결 된 백업 풀**아래 상자에서이 풀과 페어링 할 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-110">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool.</span></span> <span data-ttu-id="978e3-111">다른 풀과 아직 페어링되지 않은 기존 풀만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-111">Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
5. <span data-ttu-id="978e3-112">**자동 장애 조치 및 음성 장애 복구**를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="978e3-113">이 풀에 대 한 세부 정보를 볼 때 이제 오른쪽 창의 **복원 력**아래에 연결 된 풀이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span> 
    
6. <span data-ttu-id="978e3-114">토폴로지 작성기를 사용 하 여 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-114">Use Topology Builder to publish the topology.</span></span>
    
7. <span data-ttu-id="978e3-115">두 풀이 아직 배포 되지 않은 경우 지금 배포 하면 구성이 완료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-115">If the two pools were not yet deployed, deploy them now and the configuration will be complete.</span></span> <span data-ttu-id="978e3-116">이 절차의 마지막 두 단계는 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-116">You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="978e3-117">그러나 짝이 되는 관계를 정의 하기 전에 풀이 이미 배포 된 경우에는 다음 두 가지 최종 단계를 완료 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>
    
8. <span data-ttu-id="978e3-118">두 풀의 모든 프런트 엔드 서버에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-118">On every Front End Server in both pools, run the following:</span></span>
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    <span data-ttu-id="978e3-119">이렇게 하면 백업 페어링에 필요한 다른 서비스가 제대로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-119">This configures other services required for backup pairing to work correctly.</span></span>
    
9. <span data-ttu-id="978e3-120">비즈니스용 Skype 서버 관리 셸 명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-120">From a Skype for Business Server Management Shell command prompt, run the following:</span></span> 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. <span data-ttu-id="978e3-121">다음 cmdlet을 사용 하 여 두 풀의 사용자 및 컨퍼런스 데이터를 서로 동기화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    <span data-ttu-id="978e3-122">데이터를 동기화 하는 데 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-122">Synchronizing the data may take some time.</span></span> <span data-ttu-id="978e3-123">다음 cmdlet을 사용 하 여 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-123">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="978e3-124">두 방향의 상태가 모두 안정 된 상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-124">Make sure that the status in both directions is in steady state.</span></span>
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> <span data-ttu-id="978e3-125">**자동 장애 조치 및 음성 복구** 옵션 및 토폴로지 작성기의 관련 시간 간격은 Lync Server에 도입 된 음성 복원 기능에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-125">The **Automatic failover and failback for Voice** option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server.</span></span> <span data-ttu-id="978e3-126">이 옵션을 선택 하면이 문서에서 설명 하는 풀 장애 조치 (failover)가 자동으로 수행 된다는 의미는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="978e3-127">풀 장애 조치 및 장애 복구를 위해 관리자는 항상 장애 조치 및 장애 복구 cmdlet을 수동으로 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="978e3-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="978e3-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="978e3-128">See also</span></span>

[<span data-ttu-id="978e3-129">비즈니스용 Skype 서버의 프론트 엔드 풀 재해 복구</span><span class="sxs-lookup"><span data-stu-id="978e3-129">Front End pool disaster recovery in Skype for Business Server</span></span>](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
