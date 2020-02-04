---
title: 'Lync Server 2013: XMPP 페더레이션에 사용되는 에지 풀 장애 조치(failover)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d1c76dc37ce1abb2d34c474d4144b0894d93a0f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="529e1-102">Lync Server 2013에서 XMPP 페더레이션에 사용되는 에지 풀 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="529e1-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="529e1-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="529e1-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="529e1-104">조직에서 XMPP 페더레이션에 사용할 풀로 지정 된 하나의 Edge 풀이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-104">In your organization, there is one Edge pool designated as the pool to use for XMPP federation.</span></span> <span data-ttu-id="529e1-105">이 풀이 중단 되 면 xmpp federation에서 다시 작동할 수 있도록 XMPP federation를 장애 조치 하 여 다른 Edge 풀을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-105">If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="529e1-106">Edge 풀을 처음 설치 하 고 XMPP 페더레이션을 사용 하면 XMPP 페더레이션의 모든 Edge 풀에 대해 외부 DNS SRV 레코드를 하나만 설정 하는 것이 아니라 장애 복구 프로세스를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="529e1-107">이러한 각각의 SRV 레코드에는 다른 우선 순위가 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="529e1-108">모든 XMPP 페더레이션 트래픽은 우선 순위가 가장 높은 SRV 레코드를 사용 하 여 풀을 거칩니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="529e1-109">XMPP 페더레이션을 사용 하 고 설정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 XMPP 페더레이션 설정을](lync-server-2013-setting-up-xmpp-federation.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="529e1-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="529e1-110">다음 절차에서는 EdgePool1가 원래 XMPP 페더레이션을 호스팅하는 풀 이며, EdgePool2는 이제 XMPP federation를 호스트 하는 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="529e1-111">XMPP 페더레이션에 사용 되는 Edge 풀을 통해 장애 조치</span><span class="sxs-lookup"><span data-stu-id="529e1-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="529e1-112">현재 사용 중인 다른 Edge 풀을 아직 배포 하지 않은 경우에는 해당 풀을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="529e1-113">자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="529e1-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="529e1-114">이제 XMPP 페더레이션 (EdgePool2)을 호스트 하는 새 Edge 풀의 각 Edge 서버에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="529e1-115">XMPP 페더레이션 경로를 EdgePool2로 다시 가리키도록 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="529e1-116">이 예제에서 Site2는 이제 XMPP 페더레이션 경로를 호스팅하는 Edge 풀을 포함 하는 사이트 이며, EdgeServer2.contoso.com는 해당 풀에 있는 Edge 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="529e1-117">외부 DNS 서버에서 XMPP 페더레이션의 DNS A 레코드를 EdgeServer2.contoso.com를 가리키도록 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="529e1-118">이제 XMPP 페더레이션을 호스트 하는 Edge 풀로 확인 되는 DNS SRV 레코드가 아직 없는 경우 다음 예제와 같이 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-118">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="529e1-119">이 SRV 레코드의 포트 값은 5269 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-119">This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="529e1-120">이제 XMPP federation host에 호스트 되는 Edge 풀에 포트 5269이 외부적으로 열려 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="529e1-121">이제 Edge 풀에서 XMPP 페더레이션을 호스트 하는 모든 Edge 서버에서 서비스를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="529e1-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

