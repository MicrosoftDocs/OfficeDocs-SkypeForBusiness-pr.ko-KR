---
title: 'Lync Server 2013: 재해 복구를 위해 페어링된 프런트 엔드 풀 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 309c8f7ac7da4e40f2b16e5d13015330b2d9b611
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514535"
---
# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="44271-102">Lync Server 2013에서 재해 복구를 위한 페어링된 프런트 엔드 풀 배포</span><span class="sxs-lookup"><span data-stu-id="44271-102">Deploying paired Front End pools for disaster recovery in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44271-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="44271-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="44271-104">토폴로지 작성기를 사용 하 여 쌍으로 된 프런트 엔드 풀의 재해 복구 토폴로지를 쉽게 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44271-104">You can easily deploy the disaster recovery topology of paired Front End pools using Topology Builder.</span></span>

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a><span data-ttu-id="44271-105">프런트 엔드 풀 쌍을 배포하려면</span><span class="sxs-lookup"><span data-stu-id="44271-105">To deploy a pair of Front End pools</span></span>

1.  <span data-ttu-id="44271-106">풀이 새로 생성 되었지만 아직 정의 되지 않은 경우 토폴로지 작성기를 사용 하 여 풀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="44271-106">If the pools are new and not yet defined, use Topology Builder to create the pools.</span></span>

2.  <span data-ttu-id="44271-107">토폴로지 작성기에서 두 풀 중 하나를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="44271-107">In Topology Builder, right-click one of the two pools, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="44271-108">왼쪽 창에서 **탄성**을 클릭하고 오른쪽 창에서 **연결된 백업 풀**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="44271-108">Click **Resiliency** in the left pane, and then select **Associated Backup Pool** in the right pane.</span></span>

4.  <span data-ttu-id="44271-p101">**연결된 백업 풀** 아래 상자에서 이 풀과 쌍으로 지정할 풀을 선택합니다. 이미 다른 풀과 쌍으로 지정되어 있지 않은 기존 풀만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44271-p101">In the box below **Associated Backup Pool**, select the pool that you want to pair with this pool. Only existing pools that are not already paired with another pool will be available to select from.</span></span>
    
    <span data-ttu-id="44271-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span><span class="sxs-lookup"><span data-stu-id="44271-111">![36080581-db76-497d-bf9e-f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")</span></span>  

5.  <span data-ttu-id="44271-112">**자동 음성 장애 조치(failover) 및 장애 복구(failback)** 를 선택하고 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="44271-112">Select **Automatic failover and failback for Voice**, and then click **OK**.</span></span>
    
    <span data-ttu-id="44271-113">이제 이 풀에 대한 세부 정보를 표시하면 연결된 풀이 오른쪽 창의 **탄성** 아래에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="44271-113">When you view the details about this pool, the associated pool now appears in the right pane under **Resiliency**.</span></span>

6.  <span data-ttu-id="44271-114">토폴로지 작성기를 사용 하 여 토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="44271-114">Use Topology Builder to publish the topology.</span></span>

7.  <span data-ttu-id="44271-p102">두 풀이 아직 배포되지 않은 경우 지금 배포하면 구성이 완료됩니다. 이 절차의 마지막 두 단계는 건너뛰어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44271-p102">If the two pools were not yet deployed, deploy them now and the configuration will be complete. You can skip the final two steps in this procedure.</span></span>
    
    <span data-ttu-id="44271-117">그러나 쌍으로 지정된 관계를 정의하기 전에 풀을 이미 배포한 경우에는 다음의 마지막 두 단계를 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44271-117">However, if the pools were already deployed before you defined the paired relationship, you must complete the following two final steps.</span></span>

8.  <span data-ttu-id="44271-118">두 풀에 모두 포함되어 있는 모든 프런트 엔드 서버에서 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="44271-118">On every Front End Server in both pools, run the following:</span></span>
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    <span data-ttu-id="44271-119">그러면 백업 페어링이 올바르게 작동하는 데 필요한 다른 서비스가 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="44271-119">This configures other services required for backup pairing to work correctly.</span></span>

9.  <span data-ttu-id="44271-120">Lync Server 관리 셸 명령 프롬프트에서 다음을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="44271-120">From a Lync Server Management Shell command prompt, run the following:</span></span>
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. <span data-ttu-id="44271-121">다음 cmdlet을 사용하여 두 풀의 사용자 및 전화 회의 데이터가 서로 동기화되도록 강제 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="44271-121">Force the user and conference data of both pools to be synchronized with each other, with the following cmdlets:</span></span>
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    <span data-ttu-id="44271-122">데이터를 동기화하는 데는 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44271-122">Synchronizing the data may take some time.</span></span> <span data-ttu-id="44271-123">다음 cmdlet을 사용하여 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44271-123">You can use the following cmdlets to check the status.</span></span> <span data-ttu-id="44271-124">두 방향의 상태가 모두 안정 된 상태 인지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="44271-124">Make sure that the status in both directions is in steady state.</span></span>
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> <span data-ttu-id="44271-125">토폴로지 작성기에서 <STRONG>자동 장애 조치 (failover) 및</STRONG> 연결 된 시간 간격은 Lync Server 2010에 도입 된 음성 복구 기능에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44271-125">The <STRONG>Automatic failover and failback for Voice</STRONG> option and the associated time intervals in Topology Builder apply only to the voice resiliency features that were introduced in Lync Server 2010.</span></span> <span data-ttu-id="44271-126">해당 옵션을 선택해도 이 문서에서 설명하는 풀 장애 조치(failover)가 자동으로 수행되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="44271-126">Selecting this option does not imply that the pool failover discussed in this document is automatic.</span></span> <span data-ttu-id="44271-127">풀 장애 조치(failover) 및 장애 복구(failback)를 수행하려면 항상 관리자가 장애 조치(failover) 및 장애 복구(failback) cmdlet을 각각 수동으로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44271-127">Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

