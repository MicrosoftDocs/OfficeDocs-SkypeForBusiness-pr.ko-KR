---
title: 'Lync Server 2013: 프런트 엔드 서버 업그레이드 또는 업데이트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update Front End Servers
ms:assetid: 20fa39ae-ecfb-4c72-9cc4-8e183d3c752f
ms:mtpsurl: https://technet.microsoft.com/library/JJ204736(v=OCS.15)
ms:contentKeyID: 48183597
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a537dc701f7b3e613cc9364c786cb561cadb50
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530325"
---
# <a name="upgrade-or-update-front-end-servers-in-lync-server-2013"></a><span data-ttu-id="99417-102">Lync Server 2013에서 프런트 엔드 서버 업그레이드 또는 업데이트</span><span class="sxs-lookup"><span data-stu-id="99417-102">Upgrade or update Front End Servers in Lync Server 2013</span></span>

<div data-xmlns="https://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99417-103">_**마지막으로 수정 된 항목:** 2013-06-28_</span><span class="sxs-lookup"><span data-stu-id="99417-103">_**Topic Last Modified:** 2013-06-28_</span></span>

<span data-ttu-id="99417-104">Enterprise Edition 풀의 프런트 엔드 서버는 *업그레이드 도메인*으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="99417-104">The Front End Servers in an Enterprise Edition pool are organized into *upgrade domains*.</span></span> <span data-ttu-id="99417-105">이러한 도메인은 풀에 있는 프런트 엔드 서버의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="99417-105">These are subsets of Front End Servers in the pool.</span></span> <span data-ttu-id="99417-106">업그레이드 도메인은 토폴로지 작성기에 의해 자동으로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="99417-106">Upgrade Domains are created automatically by Topology Builder.</span></span>

<span data-ttu-id="99417-107">서버를 업그레이드할 때는 한 번에 하나씩 업그레이드 도메인을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-107">When you upgrade servers, you must do so one Upgrade Domain at a time.</span></span> <span data-ttu-id="99417-108">한 업그레이드 도메인에서 각 서버를 아래로 가져와서 업그레이드 한 다음 다른 업그레이드 도메인으로 이동 하기 전에 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-108">Bring each Server in one Upgrade Domain down, upgrade it, and then restart it before you move on to another Upgrade Domain.</span></span> <span data-ttu-id="99417-109">지금까지 업그레이드 한 업그레이드 도메인 및 서버를 계속 추적 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-109">Be sure to keep track of which Upgrade Domains and Servers that you have upgraded so far.</span></span> <span data-ttu-id="99417-110">각 서버를 업그레이드할 때 다음 순서도 다이어그램을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-110">Use the following flowchart diagram when upgrading each server.</span></span>

![프런트 엔드 서버 업그레이드 또는 업데이트](images/upgradeupdatefrontendserverslync2013.png)

<div>

## <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="99417-112">풀의 프런트 엔드 서버에 업그레이드를 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="99417-112">To apply an upgrade to the Front End servers in a pool</span></span>

1.  <span data-ttu-id="99417-113">풀의 프런트 엔드 서버에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-113">On a Front End Server in the pool, run the following cmdlet:</span></span>
    
    <span data-ttu-id="99417-114">**Get-cspoolupgradereadinessstate**</span><span class="sxs-lookup"><span data-stu-id="99417-114">**Get-CsPoolUpgradeReadinessState**</span></span>
    
    <span data-ttu-id="99417-115">*Poolupgradestate* 의 값이 **바빠서**10 분 동안 기다린 후 **get-cspoolupgradereadinessstate** 를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-115">If the value of *PoolUpgradeState* is **Busy**, wait for 10 minutes, and then try **Get-CsPoolUpgradeReadinessState** again.</span></span> <span data-ttu-id="99417-116">세 번 이상 연속 해 서 **약속이** 있거나, 각 시도 사이에 10 분 동안 대기한 후 또는 **poolupgradestate** 에 대 한 **InsufficientActiveFrontEnds** 의 결과가 표시 되 면 풀에 문제가 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="99417-116">If you see **Busy** for at least three consecutive times, after waiting 10 minutes in between each attempt, or if you see any result of **InsufficientActiveFrontEnds** for **PoolUpgradeState,** then there is an issue with the pool.</span></span> <span data-ttu-id="99417-117">이 풀이 재해 복구 토폴로지의 다른 프런트 엔드 풀과 쌍으로 지정되어 있는 경우 해당 풀을 백업 풀로 장애 조치(failover)한 후 이 풀의 서버를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-117">If this pool is paired with another Front End pool in a disaster recovery topology, you should fail the pool over to the backup pool, and then update the servers in this pool.</span></span> <span data-ttu-id="99417-118">자세한 내용은 [Lync Server 2013에서 풀 장애 조치](lync-server-2013-failing-over-a-pool.md)(failover)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="99417-118">For details, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span>
    
    <span data-ttu-id="99417-119">*PoolUpgradeState*의 값이 **Ready**이면 2단계로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-119">If the value of *PoolUpgradeState* is **Ready**, go to step 2.</span></span>

2.  <span data-ttu-id="99417-120">**Get-cspoolupgradereadinessstate** cmdlet은 또한 풀의 각 업그레이드 도메인 및 각 업그레이드 도메인에 있는 프런트 엔드 서버에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-120">The **Get-CsPoolUpgradeReadinessState** cmdlet also returns information about each upgrade domain in the pool, and about which Front End Servers are in each upgrade domain.</span></span> <span data-ttu-id="99417-121">업그레이드할 서버가 있는 서버를 포함 하는 업그레이드 도메인의 **ReadyforUpgrade** 값이 **True** 인 경우 해당 서버를 지금 안전 하 게 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99417-121">If the **ReadyforUpgrade** value is **True** for the upgrade domain that contains the server or servers you want to upgrade, you can safely upgrade those servers now.</span></span> <span data-ttu-id="99417-122">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-122">To do so, do the following:</span></span>
    
    1.  <span data-ttu-id="99417-123">Cmdlet을 사용 하 여 업그레이드할 프런트 엔드 서버에 대 한 새 연결을 중지 `Stop-CsWindowsService -Graceful -Verbose` 합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-123">Stop new connections to the Front End Servers you are going to upgrade by using the `Stop-CsWindowsService -Graceful -Verbose` cmdlet.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="99417-124">예약 된 서버 가동 중지 시간 동안 이러한 서버 업그레이드를 수행 하는 경우에는 <STRONG>Stop-CsWindowsService</STRONG>와 같이 '-<STRONG>정상</STRONG>' 매개 변수를 사용 하지 않고이 cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99417-124">If you are performing these server upgrades during a scheduled server downtime, you can run this cmdlet without the ‘-<STRONG>Graceful</STRONG>‘ parameter, as follows: <STRONG>Stop-CsWindowsService</STRONG>.</span></span> <span data-ttu-id="99417-125">이렇게 하면 모든 기존 서비스 요청이 채워질 때까지 기다리지 않고 서비스가 즉시 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="99417-125">This will immediately shut down services, without waiting for all existing service requests to be filled.</span></span>

        
        </div>
    
    2.  <span data-ttu-id="99417-126">이 업그레이드 도메인과 연결 된 서버를 업그레이드 합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-126">Upgrade the servers associated with this the Upgrade Domain.</span></span>
    
    3.  <span data-ttu-id="99417-127">서버를 다시 시작 하 고 새 연결을 수락 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-127">Restart the servers, and make sure they are accepting new connections.</span></span>

3.  <span data-ttu-id="99417-128">모든 프런트 엔드 서버가 업그레이드 될 때까지 풀의 각 업그레이드 도메인에 대해 1 ~ 2 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="99417-128">Repeat Steps 1 and 2 for each other Upgrade Domain in the pool, until all Front End Servers have been upgraded.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

