---
title: Lync Server 페더레이션 또는 XMPP 페더레이션에 사용 되는에 지 풀 장애 복구 (failback)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3531e50efec5d981249e892c692a20095bef9eff
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="b9ab2-102">Lync Server 2013에서 Lync Server 페더레이션 또는 XMPP 페더레이션에 사용 되는에 지 풀 장애 복구 (failback)</span><span class="sxs-lookup"><span data-stu-id="b9ab2-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9ab2-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b9ab2-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b9ab2-104">페더레이션을 호스트 하는 데 사용 된 오류가 발생 한에 지 풀이 다시 온라인 상태가 된 후에이 절차를 사용 하 여 Lync Server 페더레이션 경로 및/또는 XMPP 페더레이션 경로를 장애 복구 하 여 복원 된이에 지 풀을 다시 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="b9ab2-105">복원 된에 지 풀로 페더레이션 장애 복구</span><span class="sxs-lookup"><span data-stu-id="b9ab2-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="b9ab2-106">이제 다시 사용할 수 있는에 지 풀에서에 지 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="b9ab2-107">복원 된에 지 서버를 사용 하도록 Lync Server 페더레이션 경로를 장애 복구 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="b9ab2-p101">프런트 엔드 서버에서 토폴로지 작성기를 엽니다. **에지 풀**을 확장하고 현재 페더레이션에 대해 구성된 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **속성 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="b9ab2-p102">**일반** 아래의 **속성 편집**에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 의 선택을 취소합니다. **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="b9ab2-113">에 **지 풀**을 확장 한 다음 페더레이션에 사용할 원래에 지 서버 또는에 지 서버 풀을 마우스 오른쪽 단추로 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-113">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="b9ab2-114">**에지 속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-114">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="b9ab2-p104">**일반** 아래의 **속성 편집**에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 을 선택합니다. **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="b9ab2-p105">**작업**을 클릭하고, **토폴로지**, **게시**를 차례로 클릭합니다. **토폴로지 게시** 프롬프트가 표시되면 **다음**을 클릭합니다. 게시가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="b9ab2-p106">에지 서버에서 Lync Server 배포 마법사를 엽니다. **Lync Server 시스템 설치 또는 업데이트**를 클릭한 후 **Lync Server 구성 요소 설치 또는 제거**를 클릭합니다. **다시 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>
    
      - <span data-ttu-id="b9ab2-p107">Lync Server 구성 요소 설치에서 **다음**을 클릭합니다. 요약 화면에 실행되는 작업이 표시됩니다. 배포가 완료되었으면 **로그 보기**를 클릭하여 사용 가능한 로그 파일을 확인합니다. **마침**을 클릭하여 배포를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="b9ab2-127">복원 된에 지 서버를 사용 하도록 XMPP 페더레이션 경로를 장애 복구 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="b9ab2-128">다음 cmdlet을 실행 하 여 xmpp 페더레이션을 호스팅할에 지 풀에 대 한 XMPP 페더레이션 경로를 다시 가리키도록 합니다 (이 예에서는 EdgeServer1).</span><span class="sxs-lookup"><span data-stu-id="b9ab2-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="b9ab2-129">이 예제에서 Site1는 이제 XMPP 페더레이션 경로를 호스트 하는에 지 풀이 포함 된 사이트이 고 EdgeServer1.contoso.com는 해당 풀에 있는에 지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="b9ab2-p108">이제 XMPP 페더레이션을 호스팅할 에지 풀로 확인되는 XMPP 페더레이션용 DNS SRV 레코드가 없으면 다음 예에 표시된 것처럼 지금 추가해야 합니다. 이 SRV 레코드는 포트 값 5269를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-p108">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="b9ab2-132">외부 DNS 서버에서 XMPP 페더레이션용 DNS A 레코드를 EdgeServer2.contoso.com을 가리키도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="b9ab2-133">이제 XMPP 페더레이션을 호스팅할 에지 풀의 포트 5269가 외부적으로 열려 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="b9ab2-134">오류가 발생 하 여 복원 된에 지 풀이 포함 된 사이트에서 프런트 엔드 풀이 계속 실행 되 고 있으면 이러한 프런트 엔드 풀에서 웹 회의 서비스 및 A/V 회의 서비스를 업데이트 하 여 로컬 사이트에서에 지 풀을 다시 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="b9ab2-135">자세한 내용은 [Lync Server 2013에서 프런트 엔드 풀과 연결 된에 지 풀 변경을](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="b9ab2-136">오류가 발생 한에 지 풀과 동일한 사이트의 프런트 엔드 풀에도 오류가 발생 한 경우에는 Invoke – Invoke-cspoolfailback을 사용 하 여 프런트 엔드 풀을 장애 조치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9ab2-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b9ab2-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9ab2-137">See Also</span></span>


[<span data-ttu-id="b9ab2-138">Lync Server 2013의 Lync Server federation에 사용 되는에 지 풀 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="b9ab2-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="b9ab2-139">Lync Server 2013의 XMPP 페더레이션에 사용 되는에 지 풀 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="b9ab2-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="b9ab2-140">Lync Server 2013의에 지 서버 재해 복구</span><span class="sxs-lookup"><span data-stu-id="b9ab2-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

