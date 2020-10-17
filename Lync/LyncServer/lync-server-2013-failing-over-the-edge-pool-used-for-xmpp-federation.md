---
title: 'Lync Server 2013: XMPP 페더레이션에 사용 되는에 지 풀 장애 조치 (Failover)'
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
ms.openlocfilehash: 54230fb489a62ed5d7a80bfe871af3bc097e35e0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530895"
---
# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="17675-102">Lync Server 2013의 XMPP 페더레이션에 사용 되는에 지 풀 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="17675-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17675-103">_**마지막으로 수정 된 항목:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="17675-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="17675-p101">조직에는 XMPP 페더레이션에 사용할 풀로 하나의 에지 풀이 지정됩니다. 이 풀이 다운되면 XMPP 페더레이션이 다시 작동하기 전에 다른 에지 풀을 사용하도록 XMPP 페더레이션을 장애 조치(failover)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17675-p101">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="17675-106">에지 풀을 처음 설치하고 XMPP 페더레이션을 사용하도록 설정할 때는 XMPP 페더레이션용으로 모든 에지 풀에 대해 하나가 아니라 여러 개의 외부 DNS SRV 레코드를 설정하여 재해 복구 프로세스를 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17675-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="17675-107">이러한 각 SRV 레코드에는 우선 순위를 다르게 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17675-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="17675-108">모든 XMPP 페더레이션 트래픽은 우선 순위가 가장 높은 SRV 레코드가 포함된 풀을 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="17675-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="17675-109">XMPP 페더레이션을 설정 하 고 설정 하는 방법에 대 한 자세한 내용은 [Lync Server 2013에서 up a XMPP federation](lync-server-2013-setting-up-xmpp-federation.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="17675-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="17675-110">다음 절차에서 EdgePool1은 원래 XMPP 페더레이션을 호스팅한 풀이고 EdgePool2는 XMPP 페더레이션을 이제 호스팅할 풀입니다.</span><span class="sxs-lookup"><span data-stu-id="17675-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="17675-111">XMPP 페더레이션에 사용된 에지 풀 장애 조치(Failover)</span><span class="sxs-lookup"><span data-stu-id="17675-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="17675-112">아직 다른 에지 풀을 배포하지 않았으면(현재 다운된 에지 풀과 별도) 해당 풀을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="17675-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="17675-113">자세한 내용은 [Lync Server 2013에서 외부 사용자 액세스 배포](lync-server-2013-deploying-external-user-access.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="17675-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="17675-114">이제 XMPP 페더레이션을 호스팅할 새로운 에지 풀(EdgePool2)의 각 에지 서버에서 다음 cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="17675-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="17675-115">다음 cmdlet을 실행하여 XMPP 페더레이션 경로를 다시 EdgePool2로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17675-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="17675-116">이 예에서 Site2는 XMPP 페더레이션 경로를 이제 호스팅할 에지 풀이 포함된 사이트입니다. EdgeServer2.contoso.com은 이 풀에 있는 에지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="17675-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="17675-117">외부 DNS 서버에서 XMPP 페더레이션용 DNS A 레코드를 EdgeServer2.contoso.com을 가리키도록 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="17675-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="17675-p104">이제 XMPP 페더레이션을 호스팅할 에지 풀로 확인되는 XMPP 페더레이션용 DNS SRV 레코드가 없으면 다음 예에 표시된 것처럼 지금 추가해야 합니다. 이 SRV 레코드는 포트 값 5269를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17675-p104">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="17675-120">이제 XMPP 페더레이션을 호스팅할 에지 풀의 포트 5269가 외부적으로 열려 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="17675-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="17675-121">이제 XMPP 페더레이션을 호스팅할 에지 풀의 모든 에지 서버에서 서비스를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="17675-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

