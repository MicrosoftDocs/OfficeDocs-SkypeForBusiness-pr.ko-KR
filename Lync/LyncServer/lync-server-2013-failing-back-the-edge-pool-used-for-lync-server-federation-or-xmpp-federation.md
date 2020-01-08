---
title: Lync Server 페더레이션 또는 XMPP 페더레이션에 사용되는 에지 풀 장애 복구(failback)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983425"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="2b116-102">Lync Server 2013에서 Lync Server 페더레이션 또는 XMPP 페더레이션에 사용되는 에지 풀 장애 복구(failback)</span><span class="sxs-lookup"><span data-stu-id="2b116-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b116-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2b116-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2b116-104">페더레이션을 호스트 하는 데 사용 되는 실패 한 쪽 풀이 온라인 상태가 되 면이 절차를 사용 하 여 Lync Server 페더레이션 경로 및/또는 XMPP 페더레이션 경로를 다시 사용 하 여 복원 된이 Edge 풀을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="2b116-105">복원 된 Edge 풀로의 페더레이션을 장애 복구</span><span class="sxs-lookup"><span data-stu-id="2b116-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="2b116-106">지금 다시 사용할 수 있는 Edge 풀에서 Edge 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="2b116-107">복원 된 Edge 서버를 사용 하기 위해 Lync Server 페더레이션 경로를 장애 복구 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="2b116-108">프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-108">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="2b116-109">**Edge 풀**을 확장 한 다음, 현재 페더레이션에 대해 구성 된 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-109">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="2b116-110">**속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-110">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="2b116-111">**일반**아래의 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-111">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="2b116-112">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-112">Click **OK**.</span></span>
    
      - <span data-ttu-id="2b116-113">**Edge 풀**을 확장 한 다음 페더레이션에 사용할 원본 edge 서버 또는 edge 서버 풀을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-113">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="2b116-114">**속성 편집**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-114">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="2b116-115">**일반**아래에서 **속성 편집** 에서 **이 Edge 풀에 페더레이션 사용 (포트 5061)** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-115">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="2b116-116">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-116">Click **OK**.</span></span>
    
      - <span data-ttu-id="2b116-117">**작업**을 클릭 하 고 **토폴로지**를 선택한 다음 **게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-117">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="2b116-118">**토폴로지를 게시할**것인지 묻는 메시지가 표시 되 면 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-118">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="2b116-119">게시가 완료 되 면 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-119">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="2b116-120">Edge 서버에서 Lync Server 배포 마법사를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-120">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="2b116-121">**Lync Server 시스템 설치 또는 업데이트**를 클릭 한 다음 **설정 또는 Lync Server 구성 요소 제거**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-121">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="2b116-122">**다시 실행**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-122">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="2b116-123">Lync Server 구성 요소를 설정 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-123">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="2b116-124">요약 화면에 실행 되는 작업이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-124">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="2b116-125">배포가 완료 되 면 **로그 보기** 를 클릭 하 여 사용 가능한 로그 파일을 봅니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-125">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="2b116-126">**마침을** 클릭 하 여 배포를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-126">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="2b116-127">XMPP 페더레이션 경로를 장애 복구 하 여 복원 된 Edge 서버를 사용 하려는 경우 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="2b116-128">다음 cmdlet을 실행 하 여 XMPP 페더레이션 경로를 다시 지정 합니다. 이제 XMPP 페더레이션 (이 예제에서는 EdgeServer1)을 호스트 하는 Edge 풀을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="2b116-129">이 예제에서 Site1는 이제 XMPP 페더레이션 경로를 호스팅하는 Edge 풀을 포함 하는 사이트 이며, EdgeServer1.contoso.com는 해당 풀에 있는 Edge 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="2b116-130">이제 XMPP 페더레이션을 호스트 하는 Edge 풀로 확인 되는 DNS SRV 레코드가 아직 없는 경우 다음 예제와 같이 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-130">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="2b116-131">이 SRV 레코드의 포트 값은 5269 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-131">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="2b116-132">외부 DNS 서버에서 XMPP 페더레이션의 DNS A 레코드를 EdgeServer2.contoso.com를 가리키도록 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="2b116-133">이제 XMPP federation host에 호스트 되는 Edge 풀에 포트 5269이 외부적으로 열려 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="2b116-134">실패 한 Edge 풀을 포함 하는 사이트에서 프런트 엔드 풀이 계속 실행 되 고 있는 경우에는 이러한 프런트 엔드 풀의 웹 회의 서비스와 A/V 회의 서비스를 업데이트 하 여 로컬 사이트의 Edge 풀을 다시 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="2b116-135">자세한 내용은 [Lync Server 2013의 프런트 엔드 풀에 연결 된 Edge 풀 변경을](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b116-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="2b116-136">실패 한 Edge 풀과 동일한 사이트의 프런트 엔드 풀에도 실패 한 경우에는 Invoke – CsPoolFailback를 사용 하 여 프런트 엔드 풀을 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b116-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b116-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b116-137">See Also</span></span>


[<span data-ttu-id="2b116-138">Lync Server 2013에서 Lync Server 페더레이션에 사용되는 에지 풀 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="2b116-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="2b116-139">Lync Server 2013에서 XMPP 페더레이션에 사용되는 에지 풀 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="2b116-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="2b116-140">Lync Server 2013의 에지 서버 재해 복구</span><span class="sxs-lookup"><span data-stu-id="2b116-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

