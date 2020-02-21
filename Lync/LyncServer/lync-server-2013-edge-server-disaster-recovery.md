---
title: Lync Server 2013:에 지 서버 재해 복구
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff0c4b685c607850921be6b15b2611e427e5e226
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a><span data-ttu-id="96c02-102">Lync Server 2013의에 지 서버 재해 복구</span><span class="sxs-lookup"><span data-stu-id="96c02-102">Edge Server disaster recovery in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96c02-103">_**마지막으로 수정 된 항목:** 2014-03-12_</span><span class="sxs-lookup"><span data-stu-id="96c02-103">_**Topic Last Modified:** 2014-03-12_</span></span>

<span data-ttu-id="96c02-p101">다른 서버 역할과 마찬가지로, 에지 서버에 대해 고가용성을 제공하는 가장 효율적인 방법은 각 사이트의 풀에서 여러 에지 서버를 배포하는 것입니다. 이 경우 에지 서버 하나가 다운되면 풀의 다른 서버가 에지 서비스를 계속 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-p101">As with other server roles, the best way for you to provide high availability for your Edge Servers is to deploy multiple Edge servers in pools in each site. If one Edge Server goes down, the other servers in the pool will continue to provide Edge services.</span></span>

<span data-ttu-id="96c02-p102">재해 복구 절차를 수행할 수 있도록 설정하려면 서로 다른 사이트에 개별 에지 서버 풀을 배포한 상태여야 합니다. 프런트 엔드 풀에서처럼 에지 풀 쌍을 명시적으로 지정할 필요는 없지만, 여러 에지 풀을 포함하는 경우 전체 에지 풀 하나가 다운되어도 작업을 계속할 수 있습니다. 다음 섹션에서는 다양한 에지 서버 기능의 재해 복구에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-p102">To enable disaster recovery procedures, you must have separate Edge Server pools deployed at separate sites. You do not need to explicitly pair Edge pools together as you do with Front End pools, but having multiple Edge pools still provides the availability to carry on if one entire Edge pool goes down. The following sections provide details on disaster recovery for the various functions of Edge Servers.</span></span>

<div>

## <a name="remote-access"></a><span data-ttu-id="96c02-109">원격 액세스</span><span class="sxs-lookup"><span data-stu-id="96c02-109">Remote Access</span></span>

<span data-ttu-id="96c02-110">각각에 지 서버 풀을 포함 하는 여러 사이트가 있고, 하나의 전체에 지 풀에 오류가 발생 하는 경우에는 원격 액세스 서비스가 관리자 작업 없이도 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-110">If you have multiple sites, each with a pool of Edge servers, and one entire Edge pool fails, the remote access services will continue to function without needing administrator action.</span></span> <span data-ttu-id="96c02-111">서로 다른 사이트에에 지 풀을 만들 때는 동일한 FQDN을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-111">When creating Edge pools in different sites, you cannot use the same FQDN.</span></span> <span data-ttu-id="96c02-112">각에 지 풀에는 고유 Fqdn (내부 및 외부)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-112">Each Edge pool must have unique FQDNs (internal and external).</span></span> <span data-ttu-id="96c02-113">에 지 풀은 역방향 프록시 게시 규칙을 사용 하 여 프런트 엔드 서버와 통신 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-113">The Edge pools do not use reverse proxy publishing rules to talk to the Front End servers.</span></span> <span data-ttu-id="96c02-114">자동 장애 조치 (failover)는 클라이언트가 원격 액세스 DNS 서비스 레코드를 다시 쿼리하거나 원격 사용자가 다른 사이트의에 지 서버로 라우팅되는 경우 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-114">Automatic failover occurs when the client re-queries the remote access DNS service records, and remote users are routed to the Edge servers in another site.</span></span> <span data-ttu-id="96c02-115">클라이언트는 DNS SRV 레코드의 우선 순위에 따라 각 외부에 지 FQDN을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-115">The client attempts each external Edge FQDN according to the priority of the DNS SRV records.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="96c02-116">장애 조치 (failover)가 원활 하 게 작동 하려면 모든 풀의 프런트 엔드 서버가 모든에 지 서버와 통신할 수 있도록 하는 방화벽을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-116">For failover to work smoothly, ensure that the firewall allows the Front End servers from every pool to communicate with all Edge servers.</span></span>



</div>

</div>

<div>

## <a name="federation"></a><span data-ttu-id="96c02-117">연결</span><span class="sxs-lookup"><span data-stu-id="96c02-117">Federation</span></span>

<span data-ttu-id="96c02-118">Lync Server를 실행 하는 다른 조직과의 페더레이션 관계의 경우 지리적 DNS GTM 같은 해결 방법이 있으면 인바운드 페더레이션 요청이 계속 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-118">For federation relationships with other organizations running Lync Server, inbound federation requests will continue to work as long as you have solutions like Geo-DNS GTM.</span></span> <span data-ttu-id="96c02-119">페더레이션 장애 조치 (failover)에서는 SRV 레코드의 우선 순위를 사용 하 여 장애 조치 (failover)를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-119">It’s important to understand that federation failover does not provide failover with priority in SRV records.</span></span> <span data-ttu-id="96c02-120">이전에 제공 된 솔루션은 인바운드 페더레이션에 대 한 재해 복구 기능을 제공 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-120">A solution provided earlier can help you provide disaster recovery capabilities for inbound federation.</span></span>

<span data-ttu-id="96c02-121">아웃바운드 페더레이션은 항상 조직의 게시된 에지 풀 또는 에지 서버 하나를 통해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-121">Outbound federation is always set up through one published Edge pool or Edge Server in the organization.</span></span> <span data-ttu-id="96c02-122">이 에지 풀이 다운되는 경우에는 토폴로지 작성기를 사용하여 계속 실행 중인 에지 풀을 사용하도록 아웃바운드 페더레이션 경로를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-122">If this Edge pool has gone down, you must use Topology Builder to change the outbound federation route to use an Edge pool which is still running.</span></span> <span data-ttu-id="96c02-123">자세한 내용은 [Lync server 2013의 Lync server federation에 사용 된에 지 풀 장애 조치](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md) (failover)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96c02-123">For details, see [Failing over the Edge pool used for Lync Server federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)</span></span>

</div>

<div>

## <a name="xmpp-federation"></a><span data-ttu-id="96c02-124">XMPP 페더레이션</span><span class="sxs-lookup"><span data-stu-id="96c02-124">XMPP Federation</span></span>

<span data-ttu-id="96c02-125">XMPP 페더레이션의 경우에는 XMPP 페더레이션 게이트웨이로 지정된 에지 풀이 다운되는 경우 아웃바운드 및 인바운드 트래픽에서 모두 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-125">For XMPP federation, both outbound and inbound traffic will fail if the Edge pool which is designated as the XMPP federation gateway goes down.</span></span> <span data-ttu-id="96c02-126">XMPP 페더레이션이 다시 작동하도록 하려면 다른 에지 풀을 사용하도록 XMPP 페더레이션을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-126">To make XMPP federation work again, you must change XMPP federation to use a different Edge pool.</span></span> <span data-ttu-id="96c02-127">자세한 내용은 [Lync Server 2013에서 XMPP 페더레이션에 사용 되는에 지 풀 장애 조치](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)(failover)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="96c02-127">For details, see [Failing over the Edge pool used for XMPP federation in Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).</span></span>

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a><span data-ttu-id="96c02-128">에지 풀에 오류가 발생해도 프런트 엔드 풀은 계속 실행됨</span><span class="sxs-lookup"><span data-stu-id="96c02-128">Edge Pool Fails But Front End Pool Is Still Running</span></span>

<span data-ttu-id="96c02-129">사이트에서 에지 풀에 오류가 발생했는데 해당 사이트의 프런트 엔드 풀은 계속 실행되는 경우에는 첫 번째 에지 풀이 다운된 동안 다른 사이트의 다른 에지 풀을 사용하도록 프런트 엔드 풀을 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96c02-129">If an Edge pool fails at a site, but the Front End pool at that site is still running, you will need to change the Front End pool to use a different Edge pool at a different site while that first Edge pool is down.</span></span> <span data-ttu-id="96c02-130">자세한 내용은 [Lync Server 2013에서 프런트 엔드 풀과 연결 된에 지 풀 변경을](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="96c02-130">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

