---
title: 'Lync Server 2013: Lync Server federation에 사용 되는에 지 풀 장애 조치 (failover)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1589fe63c41cb2c4cbff9b72f42a3cc06b43e5d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="77502-102">Lync Server 2013의 Lync Server federation에 사용 되는에 지 풀 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="77502-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77502-103">_**마지막으로 수정 된 항목:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="77502-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="77502-104">Lync Server 페더레이션을 구성한 에지 풀이 다운될 경우 페더레이션이 작동하도록 하려면 다른 에지 풀을 사용하도록 페더레이션을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77502-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="77502-105">Lync Server 페더레이션에 사용된 에지 풀 장애 조치(Failover)</span><span class="sxs-lookup"><span data-stu-id="77502-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="77502-p101">프런트 엔드 서버에서 토폴로지 작성기를 엽니다. **에지 풀**을 확장하고 현재 페더레이션에 대해 구성된 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **속성 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77502-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>

2.  <span data-ttu-id="77502-p102">**일반** 아래의 **속성 편집**에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 의 선택을 취소합니다. **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77502-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

3.  <span data-ttu-id="77502-p103">**에지 풀**을 확장한 후 현재 페더레이션에 대해 사용할 에지 서버 또는 에지 서버 풀을 마우스 오른쪽 단추로 클릭합니다. **에지 속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77502-p103">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation. Select **Edit properties**.</span></span>

4.  <span data-ttu-id="77502-p104">**일반** 아래의 **속성 편집**에서 **이 에지 풀에 페더레이션 사용(포트 5061)** 을 선택합니다. **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77502-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="77502-p105">**작업**을 클릭하고, **토폴로지**, **게시**를 차례로 클릭합니다. **토폴로지 게시** 프롬프트가 표시되면 **다음**을 클릭합니다. 게시가 완료되면 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77502-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="77502-p106">에지 서버에서 Lync Server 배포 마법사를 엽니다. **Lync Server 시스템 설치 또는 업데이트**를 클릭한 후 **Lync Server 구성 요소 설치 또는 제거**를 클릭합니다. **다시 실행**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="77502-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>

7.  <span data-ttu-id="77502-p107">Lync Server 구성 요소 설치에서 **다음**을 클릭합니다. 요약 화면에 실행되는 작업이 표시됩니다. 배포가 완료되었으면 **로그 보기**를 클릭하여 사용 가능한 로그 파일을 확인합니다. **마침**을 클릭하여 배포를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="77502-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="77502-125">실패한 에지 풀을 포함하는 사이트에 아직 실행 중인 프런트 엔드 서버가 포함된 경우 아직 실행 중인 원격 사이트의 에지 풀을 사용하도록 해당 프런트 엔드 풀에서 웹 회의 서비스 및 A/V 회의 서비스를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="77502-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="77502-126">자세한 내용은 [Lync Server 2013에서 프런트 엔드 풀과 연결 된에 지 풀 변경을](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="77502-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77502-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77502-127">See Also</span></span>


[<span data-ttu-id="77502-128">Lync Server 2013의 XMPP 페더레이션에 사용 되는에 지 풀 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="77502-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="77502-129">Lync Server 2013에서 Lync Server 페더레이션 또는 XMPP 페더레이션에 사용 되는에 지 풀 장애 복구 (failback)</span><span class="sxs-lookup"><span data-stu-id="77502-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="77502-130">Lync Server 2013의에 지 서버 재해 복구</span><span class="sxs-lookup"><span data-stu-id="77502-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

