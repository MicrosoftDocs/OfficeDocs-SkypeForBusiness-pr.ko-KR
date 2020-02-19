---
title: 'Lync Server 2013: 중앙 사이트 음성 복구 계획'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for central site voice resiliency
ms:assetid: 52dd0c3e-cd3c-44cf-bef5-8c49ff5e4c7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398347(v=OCS.15)
ms:contentKeyID: 48184164
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af584c5a9ff1e061594ab5956b54032d56cd4ae4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139891"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-central-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="8038b-102">Lync Server 2013의 중앙 사이트 음성 복구 계획</span><span class="sxs-lookup"><span data-stu-id="8038b-102">Planning for central site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8038b-103">_**마지막으로 수정 된 항목:** 2013-10-30_</span><span class="sxs-lookup"><span data-stu-id="8038b-103">_**Topic Last Modified:** 2013-10-30_</span></span>

<span data-ttu-id="8038b-104">점점 많은 기업에서 전 세계에 여러 사이트를 확산시키고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-104">Increasingly, enterprises have multiple sites spread across the globe.</span></span> <span data-ttu-id="8038b-105">긴급 서비스 유지 관리, 지원 센터에 대 한 액세스 권한 및 중요 한 비즈니스 작업을 수행 하는 기능 (중앙 사이트의 서비스가 중단 된 경우)은 Enterprise Voice 복구 솔루션에 반드시 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-105">Maintaining emergency services, access to help desk, and the ability to conduct critical business tasks when a central site is out of service is essential for any Enterprise Voice resiliency solution.</span></span> <span data-ttu-id="8038b-106">중앙 사이트가 사용할 수 없게 된 경우 다음 조건을 충족해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-106">When a central site becomes unavailable, the following conditions must be met:</span></span>

  - <span data-ttu-id="8038b-107">음성 장애 조치가 제공되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-107">Voice failover must be provided.</span></span>

  - <span data-ttu-id="8038b-108">일반적으로 중앙 사이트의 프런트 엔드 풀에 등록 하는 사용자는 대체 프런트 엔드 풀을 사용 하 여 등록할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-108">Users who ordinarily register with the Front End pool at the central site must be able to register with an alternative Front End pool.</span></span> <span data-ttu-id="8038b-109">이렇게 하려면 각 중앙 사이트에서 디렉터 풀 또는 프런트 엔드 풀로 확인 되는 여러 DNS SRV 레코드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-109">This can be done by creating multiple DNS SRV records, each of which resolves to a Director pool or Front End pool in each of your central sites.</span></span> <span data-ttu-id="8038b-110">해당 중앙 사이트에서 처리 하는 사용자가 다른 SRV 레코드의 해당 디렉터 및 프런트 엔드 풀을 가져올 수 있도록 SRV 레코드의 우선 순위와 가중치를 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-110">You can adjust the priority and weights of the SRV records so that users who are served by that central site get the corresponding Director and Front End pool ahead of those in other SRV records.</span></span>

  - <span data-ttu-id="8038b-111">다른 사이트에 있는 사용자와의 통화가 PSTN으로 다시 라우팅되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-111">Calls to and from users located at other sites must be rerouted to the PSTN.</span></span>

<span data-ttu-id="8038b-112">이 항목에서는 중앙 사이트 음성 복구의 보안을 유지하는 권장 솔루션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-112">This topic describes the recommended solution for securing central site voice resiliency.</span></span>

<div>

## <a name="architecture-and-topology"></a><span data-ttu-id="8038b-113">아키텍처 및 토폴로지</span><span class="sxs-lookup"><span data-stu-id="8038b-113">Architecture and Topology</span></span>

<span data-ttu-id="8038b-114">중앙 사이트에서 음성 복구를 계획 하려면 음성 장애 조치 (failover)를 사용 하도록 설정 하는 경우 Lync Server 2013 등록자에서 실행 하는 중앙 역할에 대 한 기본적인 이해가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-114">Planning for voice resiliency at a central site requires a basic understanding of the central role played by the Lync Server 2013 Registrar in enabling voice failover.</span></span> <span data-ttu-id="8038b-115">Lync Server 등록자는 클라이언트 등록 및 인증을 가능 하 게 하 고 라우팅 서비스를 제공 하는 서버 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-115">The Lync Server Registrar is a server role that enables client registration and authentication and provides routing services.</span></span> <span data-ttu-id="8038b-116">이는 Standard Edition server, 프런트 엔드 서버, 디렉터 또는 Sba (survivable Branch 기기의 다른 구성 요소와 함께 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-116">It resides along with other components on a Standard Edition server, Front End Server, Director, or Survivable Branch Appliance.</span></span> <span data-ttu-id="8038b-117">등록자 풀은 프런트 엔드 풀에서 실행 되며 동일한 사이트에 있는 등록자 서비스로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-117">A Registrar pool consists of Registrar Services running on the Front End pool and residing at the same site.</span></span> <span data-ttu-id="8038b-118">프런트 엔드 풀의 부하를 분산 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-118">The Front End pool must be load balanced.</span></span> <span data-ttu-id="8038b-119">DNS 부하 분산을 권장 하지만 하드웨어 부하 분산을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-119">DNS load balancing is recommended, but hardware load balancing is acceptable.</span></span> <span data-ttu-id="8038b-120">Lync 클라이언트는 다음 검색 메커니즘을 통해 프런트 엔드 풀을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-120">A Lync client discovers the Front End pool through the following discovery mechanism:</span></span>

1.  <span data-ttu-id="8038b-121">DNS SRV 레코드</span><span class="sxs-lookup"><span data-stu-id="8038b-121">DNS SRV record</span></span>

2.  <span data-ttu-id="8038b-122">자동 검색 웹 서비스 (Lync Server 2013의 새로운)</span><span class="sxs-lookup"><span data-stu-id="8038b-122">Autodiscovery Web Service (new in Lync Server 2013)</span></span>

3.  <span data-ttu-id="8038b-123">DHCP 옵션 120</span><span class="sxs-lookup"><span data-stu-id="8038b-123">DHCP option 120</span></span>

<span data-ttu-id="8038b-124">Lync 클라이언트가 프런트 엔드 풀에 연결 되 면 부하 분산 장치는 풀의 프런트 엔드 서버 중 하나로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-124">After the Lync client connects to the Front End pool, it is directed by the load balancer to one of the Front End Servers in the pool.</span></span> <span data-ttu-id="8038b-125">그런 다음 프런트 엔드 서버는 풀의 기본 등록 기관으로 클라이언트를 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-125">That Front End Server, in turn, redirects the client to a preferred Registrar in the pool.</span></span>

<span data-ttu-id="8038b-126">Enterprise Voice를 사용 하도록 설정 된 각 사용자가 특정 등록자 풀에 할당 되어 해당 사용자의 기본 등록자 풀이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-126">Each user enabled for Enterprise Voice is assigned to a particular Registrar pool, which becomes that user’s primary Registrar pool.</span></span> <span data-ttu-id="8038b-127">지정된 사이트에서 일반적으로 수백 또는 수천 명의 사용자가 하나의 기본 등록자 풀을 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-127">At a given site, hundreds or thousands of users typically share a single primary Registrar pool.</span></span> <span data-ttu-id="8038b-128">현재 상태, 회의 또는 장애 조치를 중앙 사이트에 의존하는 분기 사이트 사용자의 중앙 사이트 리소스 사용을 계산하려면 각 분기 사이트 사용자를 중앙 사이트에 등록된 사용자로 간주하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-128">To account for the consumption of central site resources by any branch site users that rely on the central site for presence, conferencing, or failover, we recommend that you consider each branch site user as though the user were a user registered with the central site.</span></span> <span data-ttu-id="8038b-129">현재 Sba (survivable 분기 기기에 등록 된 사용자를 포함 하 여 분기 사이트 사용자 수에 대 한 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-129">There are currently no limits on the number of branch site users, including users registered with a Survivable Branch Appliance.</span></span>

<span data-ttu-id="8038b-130">중앙 사이트 실패 시 음성 복구를 지원하려면 기본 등록자 풀의 지정된 단일 백업 등록자 풀이 다른 사이트에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-130">To assure voice resiliency in the event of a central site failure, the primary Registrar pool must have a single designated backup Registrar pool located at another site.</span></span> <span data-ttu-id="8038b-131">토폴로지 작성기 복구 설정을 사용 하 여 백업을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-131">The backup can be configured by using Topology Builder resiliency settings.</span></span> <span data-ttu-id="8038b-132">두 사이트 간에 복구 가능한 WAN 링크가 있는 경우 기본 등록자 풀을 더 이상 사용할 수 없는 사용자는 자동으로 백업 등록자 풀에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-132">Assuming a resilient WAN link between the two sites, users whose primary Registrar pool is no longer available are automatically directed to the backup Registrar pool.</span></span>

<span data-ttu-id="8038b-133">다음 단계에서는 클라이언트 검색 및 등록 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-133">The following steps describe the client discovery and registration process:</span></span>

1.  <span data-ttu-id="8038b-134">클라이언트에서 DNS SRV 레코드를 통해 Lync Server를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-134">A client discovers Lync Server through DNS SRV records.</span></span> <span data-ttu-id="8038b-135">Lync Server 2013에서는 dns srv 쿼리에 대해 둘 이상의 FQDN을 반환 하도록 DNS SRV 레코드를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-135">In Lync Server 2013, DNS SRV records can be configured to return more than one FQDN to the DNS SRV query.</span></span> <span data-ttu-id="8038b-136">예를 들어 Contoso라는 회사에 세 개의 중앙 사이트(북미, 유럽 및 아시아 태평양)가 있고 각 중앙 사이트에 디렉터 풀이 있는 경우 DNS SRV 레코드는 각 위치의 디렉터 풀 FQDN을 가리킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-136">For example, if enterprise Contoso has three central sites (North America, Europe, and Asia-Pacific) and a Director pool at each central site, DNS SRV records can point to the Director pool FQDNs in each of the three locations.</span></span> <span data-ttu-id="8038b-137">위치 중 하나에 디렉터 풀을 사용할 수 있는 경우 클라이언트는 첫 번째 홉 Lync 서버에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-137">As long as the Director pool in one of the locations is available, the client can connect to the first hop Lync Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8038b-138">디렉터 풀을 사용 하는 것은 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-138">Using a Director pool is optional.</span></span> <span data-ttu-id="8038b-139">프런트 엔드 풀을 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-139">A Front End pool can be used instead.</span></span>

    
    </div>

2.  <span data-ttu-id="8038b-140">디렉터 풀은 Lync 클라이언트에 사용자의 기본 등록자 풀 및 백업 등록자 풀에 대 한 정보를 알려 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-140">The Director pool informs the Lync client about the user’s primary Registrar pool and backup Registrar pool.</span></span>

3.  <span data-ttu-id="8038b-141">Lync 클라이언트는 먼저 사용자의 기본 등록자 풀에 연결을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-141">The Lync client attempts to connect to the user’s primary Registrar pool first.</span></span> <span data-ttu-id="8038b-142">기본 등록자 풀을 사용할 수 있는 경우 등록자가 등록을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-142">If the primary Registrar pool is available, the Registrar accepts the registration.</span></span> <span data-ttu-id="8038b-143">기본 등록자 풀을 사용할 수 없는 경우 Lync 클라이언트는 백업 등록자 풀에 연결을 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-143">If the primary Registrar pool is unavailable, the Lync client attempts to connect to the backup Registrar pool.</span></span> <span data-ttu-id="8038b-144">백업 등록자 풀을 사용할 수 있고 이 풀에서 사용자의 기본 등록자 풀을 사용할 수 없는 것으로 확인(지정된 장애 조치 간격에 대한 하트비트 부족 감지)한 경우 백업 등록자 풀이 사용자의 등록을 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-144">If the backup Registrar pool is available and has determined that the user’s primary Registrar pool is unavailable (by detecting a lack of heartbeat for a specified failover interval) the backup Registrar pool accepts the user’s registration.</span></span> <span data-ttu-id="8038b-145">백업 등록자는 기본 등록자를 다시 사용할 수 있는 것으로 감지 하면 백업 등록자 풀은 장애 조치 (failover) Lync 클라이언트를 기본 풀로 리디렉션합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-145">After the backup Registrar detects that the primary Registrar is again available, the backup Registrar pool will redirect failover Lync clients to their primary pool.</span></span>

<span data-ttu-id="8038b-p110">다음 그림에서는 중앙 사이트 복구를 지원하는 권장 토폴로지를 보여 줍니다. 두 사이트는 복구 가능한 WAN 링크로 연결됩니다. 중앙 사이트가 사용할 수 없게 된 경우 해당 풀에 지정된 사용자는 등록을 위해 백업 사이트로 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-p110">The following figure shows the recommended topology for assuring central site resiliency. The two sites are connected by a resilient WAN link. If the central site becomes unavailable, users who are assigned to that pool are directed to the backup site for registration.</span></span>

<span data-ttu-id="8038b-149">**중앙 사이트 음성 복구를 위한 권장 토폴로지**</span><span class="sxs-lookup"><span data-stu-id="8038b-149">**Recommended topology for central site voice resiliency**</span></span>

<span data-ttu-id="8038b-150">![중앙 사이트 음성 복구용 토폴로지 토폴로지](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "중앙 사이트 음성 복구용 토폴로지 토폴로지")</span><span class="sxs-lookup"><span data-stu-id="8038b-150">![Topology for central site voice resliency](images/Gg398347.19ea3e74-8a5c-488c-a34e-fc180ab9a50a(OCS.15).jpg "Topology for central site voice resliency")</span></span>

</div>

<div>

## <a name="requirements-and-recommendations"></a><span data-ttu-id="8038b-151">요구 사항 및 권장 사항</span><span class="sxs-lookup"><span data-stu-id="8038b-151">Requirements and Recommendations</span></span>

<span data-ttu-id="8038b-152">다음은 대부분의 조직에 적절한 중앙 사이트 음성 복구 구현에 대한 요구 사항 및 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-152">The following requirements and recommendations for implementing central site voice resiliency are appropriate for most organizations:</span></span>

  - <span data-ttu-id="8038b-153">사이트의 기본 및 백업 등록자 풀이 복구 가능한 WAN 링크로 연결되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-153">The sites in which the primary and backup Registrar pools reside should be connected by a resilient WAN link.</span></span>

  - <span data-ttu-id="8038b-154">각 중앙 사이트에 하나 이상의 등록자로 구성된 등록자 풀이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-154">Each central site must contain a Registrar pool consisting of one or more Registrars.</span></span>

  - <span data-ttu-id="8038b-155">각 등록자 풀은 DNS 부하 분산, 하드웨어 부하 분산 또는 둘 다를 사용 하 여 로드 균형을 조정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-155">Each Registrar pool must be load-balanced by using DNS load balancing, hardware load balancing, or both.</span></span> <span data-ttu-id="8038b-156">부하 분산 구성을 계획 하는 방법에 대 한 자세한 내용은 [Lync Server 2013의 부하 분산 요구 사항](lync-server-2013-load-balancing-requirements.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8038b-156">For detailed information about planning your load balancing configuration, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

  - <span data-ttu-id="8038b-157">각 사용자는 Lync Server 관리 셸 **설정-CsUser** Cmdlet 또는 Lync server 제어판을 사용 하 여 기본 등록자 풀에 할당 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-157">Each user must be assigned to a primary Registrar pool by using either the Lync Server Management Shell **set-CsUser** cmdlet or the Lync Server Control Panel.</span></span>

  - <span data-ttu-id="8038b-158">기본 등록자 풀의 단일 백업 등록자 풀이 다른 중앙 사이트에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-158">The primary Registrar pool must have a single backup Registrar pool located in a different central site.</span></span>

  - <span data-ttu-id="8038b-159">기본 등록자 풀이 백업 등록자 풀로 장애 조치되도록 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-159">The primary Registrar pool must be configured to fail over to the backup Registrar pool.</span></span> <span data-ttu-id="8038b-160">기본적으로 기본 등록자는 300초 간격 후 백업 등록자 풀로 장애 조치되도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-160">By default, the primary Registrar is set to fail over to the backup Registrar pool after an interval of 300 seconds.</span></span> <span data-ttu-id="8038b-161">Lync Server 2013 토폴로지 작성기를 사용 하 여이 간격을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-161">You can change this interval by using the Lync Server 2013 Topology Builder.</span></span>

  - <span data-ttu-id="8038b-162">계획 설명서의 "[Lync Server 2013에서 장애 조치 (failover) 경로 구성](lync-server-2013-configuring-a-failover-route.md)" 항목에 설명 된 대로 장애 조치 경로를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-162">Configure a failover route, as described in the “[Configuring a failover route in Lync Server 2013](lync-server-2013-configuring-a-failover-route.md)” topic in the Planning documentation.</span></span> <span data-ttu-id="8038b-163">경로를 구성할 때 기본 경로에 지정된 게이트웨이에서 다른 사이트에 있는 게이트웨이를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-163">When configuring the route, specify a gateway that is located at a different site from the gateway specified in the primary route.</span></span>

  - <span data-ttu-id="8038b-164">중앙 사이트에 기본 관리 서버가 포함되고 사이트가 연장된 기간 동안 다운될 수 있는 경우 백업 사이트에 관리 도구를 다시 설치해야 합니다. 그러지 않으면 관리 설정을 변경할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-164">If the central site contained your primary management server and the site is likely to be down for an extended period, you will need to reinstall your management tools at the backup site; otherwise, you won’t be able to change any management settings.</span></span>

</div>

<div>

## <a name="dependencies"></a><span data-ttu-id="8038b-165">의존</span><span class="sxs-lookup"><span data-stu-id="8038b-165">Dependencies</span></span>

<span data-ttu-id="8038b-166">Lync Server는 다음 인프라 및 소프트웨어 구성 요소에 따라 달라 지 며 음성 복구를 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-166">Lync Server depends on the following infrastructure and software components to assure voice resiliency:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8038b-167"><strong>구성 요소</strong></span><span class="sxs-lookup"><span data-stu-id="8038b-167"><strong>Component</strong></span></span></p></td>
<td><p><span data-ttu-id="8038b-168"><strong>외적인</strong></span><span class="sxs-lookup"><span data-stu-id="8038b-168"><strong>Functional</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8038b-169">DNS</span><span class="sxs-lookup"><span data-stu-id="8038b-169">DNS</span></span></p></td>
<td><p><span data-ttu-id="8038b-170">SRV 레코드 및 A 레코드에서 서버 간 연결 및 서버와 클라이언트 간 연결 확인</span><span class="sxs-lookup"><span data-stu-id="8038b-170">Resolving SRV records and A records for server-server and server-client connectivity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8038b-171">Exchange와 EWV(Exchange 웹 서비스)</span><span class="sxs-lookup"><span data-stu-id="8038b-171">Exchange and Exchange Web Services (EWS)</span></span></p></td>
<td><p><span data-ttu-id="8038b-172">대화 상대 저장, 일정 데이터</span><span class="sxs-lookup"><span data-stu-id="8038b-172">Contact storage; calendar data</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8038b-173">Exchange 통합 메시징과 Exchange 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="8038b-173">Exchange Unified Messaging and Exchange Web Services</span></span></p></td>
<td><p><span data-ttu-id="8038b-174">통화 기록, 음성 메일 목록, 음성 메일</span><span class="sxs-lookup"><span data-stu-id="8038b-174">Call logs, voice mail list, voice mail</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8038b-175">DHCP 옵션 120</span><span class="sxs-lookup"><span data-stu-id="8038b-175">DHCP Options 120</span></span></p></td>
<td><p><span data-ttu-id="8038b-176">DNS SRV를 사용할 수 없는 경우 클라이언트에서는 DHCP 옵션 120을 사용하여 등록자를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-176">If DNS SRV is unavailable, the client will attempt to use DHCP Option 120 to discover the Registrar.</span></span> <span data-ttu-id="8038b-177">이 작업을 수행 하려면 DHCP 서버를 구성 해야 하거나, Lync Server 2013 DHCP를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-177">For this to work, either a DHCP server must be configured or Lync Server 2013 DHCP must be enabled.</span></span> <span data-ttu-id="8038b-178">자세한 내용은 <a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013의 분기 사이트 복구 요구 사항</a> 에 대 한 하드웨어 및 소프트웨어 요구 사항 항목을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8038b-178">For details, see Hardware and Software Requirements for Branch-Site Resiliency in <a href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</a> section.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="survivable-voice-features"></a><span data-ttu-id="8038b-179">지속 가능한 음성 기능</span><span class="sxs-lookup"><span data-stu-id="8038b-179">Survivable Voice Features</span></span>

<span data-ttu-id="8038b-180">위의 요구 사항 및 권장 사항이 구현된 경우 백업 등록자 풀에서 다음 음성 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-180">If the preceding requirements and recommendations have been implemented, the following voice features will be provided by the backup Registrar pool:</span></span>

  - <span data-ttu-id="8038b-181">아웃바운드 PSTN 통화</span><span class="sxs-lookup"><span data-stu-id="8038b-181">Outbound PSTN calls</span></span>

  - <span data-ttu-id="8038b-182">인바운드 PSTN 통화(전화 통신 서비스 공급자가 백업 사이트로의 장애 조치 기능을 지원하는 경우)</span><span class="sxs-lookup"><span data-stu-id="8038b-182">Inbound PSTN calls, if the telephony service provider supports the ability to fail over to a backup site</span></span>

  - <span data-ttu-id="8038b-183">같은 사이트에 있는 사용자 및 서로 다른 두 사이트 간의 엔터프라이즈 통화</span><span class="sxs-lookup"><span data-stu-id="8038b-183">Enterprise calls between users at both the same site and between two different sites</span></span>

  - <span data-ttu-id="8038b-184">통화 보류, 검색 및 전송을 포함한 기본적인 통화 처리</span><span class="sxs-lookup"><span data-stu-id="8038b-184">Basic call handling, including call hold, retrieval, and transfer</span></span>

  - <span data-ttu-id="8038b-185">같은 사이트에 있는 사용자 간의 오디오/비디오 공유 및 양자 간 인스턴트 메시징</span><span class="sxs-lookup"><span data-stu-id="8038b-185">Two-party instant messaging and sharing audio and video between users at the same site</span></span>

  - <span data-ttu-id="8038b-186">착신 전환, 동시 끝점 신호 울림, 통화 위임 및 팀 통화 서비스(통화 위임의 두 당사자 또는 모든 팀 구성원이 같은 사이트에 구성된 경우에만)</span><span class="sxs-lookup"><span data-stu-id="8038b-186">Call forwarding, simultaneous ringing of endpoints, call delegation, and team call services, but only if both parties to call delegation, or all team members, are configured at the same site.</span></span>

  - <span data-ttu-id="8038b-187">기존 전화 및 클라이언트는 계속 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-187">Existing phones and clients continue to work.</span></span>

  - <span data-ttu-id="8038b-188">CDR(통화 정보 기록)</span><span class="sxs-lookup"><span data-stu-id="8038b-188">Call detail recording (CDR)</span></span>

  - <span data-ttu-id="8038b-189">인증 및 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8038b-189">Authentication and authorization</span></span>

<span data-ttu-id="8038b-190">다음 음성 기능은 기본 중앙 사이트의 서비스가 중단된 경우 구성 방법에 따라 작동하거나 작동하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-190">Depending on how they are configured, the following voice features may or may not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="8038b-191">음성 메일 보관 및 검색</span><span class="sxs-lookup"><span data-stu-id="8038b-191">Voice mail deposit and retrieval</span></span>
    
    <span data-ttu-id="8038b-192">기본 중앙 사이트의 서비스가 중단된 경우 Exchange UM을 사용하려면 다음 중 하나를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-192">If you want to make Exchange UM available when the primary central site is out of service, you must do one of the following:</span></span>
    
      - <span data-ttu-id="8038b-193">중앙 사이트의 Exchange UM 서버가 다른 사이트에 있는 백업 Exchange UM 서버를 가리키도록 DNS SRV 레코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-193">Change DNS SRV records so that the Exchange UM servers at the central site point to backup Exchange UM servers at another site.</span></span>
    
      - <span data-ttu-id="8038b-194">각 사용자의 Exchange UM 다이얼 플랜을 중앙 사이트와 백업 사이트 모두에 포함 하도록 구성 하 되, 백업 Exchange UM 서버를 사용 하지 않도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-194">Configure each user’s Exchange UM dial plan to include Exchange UM servers at both the central site and the backup site, but designate the backup Exchange UM servers as disabled.</span></span> <span data-ttu-id="8038b-195">기본 사이트를 사용할 수 없게 되 면 Exchange 관리자가 백업 사이트에서 Exchange UM 서버를 사용 하도록 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-195">If the primary site becomes unavailable, the Exchange administrator has to mark the Exchange UM servers at the backup site as enabled.</span></span>
    
    <span data-ttu-id="8038b-196">위의 두 솔루션을 모두 수행할 수 없는 경우에는 중앙 사이트를 사용할 수 없게 되는 경우에 Exchange UM을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-196">If neither of the preceding solutions is possible, then Exchange UM will not be available in the event the central site becomes unavailable.</span></span>

  - <span data-ttu-id="8038b-197">모든 유형의 회의</span><span class="sxs-lookup"><span data-stu-id="8038b-197">Conferencing of all types</span></span>
    
    <span data-ttu-id="8038b-p116">백업 사이트로 장애 조치된 사용자는 풀을 사용할 수 있는 이끌이가 만들거나 호스팅하는 전화 회의에 참가할 수 있지만 더 이상 사용할 수 없는 자신의 기본 풀에서 전화 회의를 만들거나 호스팅할 수는 없습니다. 마찬가지로 다른 사용자는 영향을 받는 사용자의 기본 풀에서 호스팅되는 전화 회의에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-p116">A user who has failed over to a backup site can join a conference that is created or hosted by an organizer whose pool is available but cannot create or host a conference on his or her own primary pool, which is no longer available. Similarly, others users cannot join conferences that are hosted on the affected user’s primary pool.</span></span>

<span data-ttu-id="8038b-200">다음 음성 기능은 기본 중앙 사이트의 서비스가 중단된 경우 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8038b-200">The following voice features do not work when a primary central site is out of service:</span></span>

  - <span data-ttu-id="8038b-201">회의 자동 길잡이</span><span class="sxs-lookup"><span data-stu-id="8038b-201">Conference Auto-Attendant</span></span>

  - <span data-ttu-id="8038b-202">현재 상태 및 DND 기반 라우팅</span><span class="sxs-lookup"><span data-stu-id="8038b-202">Presence and DND-based routing</span></span>

  - <span data-ttu-id="8038b-203">착신 전환 설정 업데이트</span><span class="sxs-lookup"><span data-stu-id="8038b-203">Updating call forwarding settings</span></span>

  - <span data-ttu-id="8038b-204">응답 그룹 서비스 및 통화 대기</span><span class="sxs-lookup"><span data-stu-id="8038b-204">Response Group service and Call Park</span></span>

  - <span data-ttu-id="8038b-205">새 전화 및 클라이언트 프로비전</span><span class="sxs-lookup"><span data-stu-id="8038b-205">Provisioning new phones and clients</span></span>

  - <span data-ttu-id="8038b-206">주소록 웹 검색</span><span class="sxs-lookup"><span data-stu-id="8038b-206">Address Book Web Search</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8038b-207">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8038b-207">See Also</span></span>


[<span data-ttu-id="8038b-208">Lync Server 2013의 분기 사이트 음성 복구 계획</span><span class="sxs-lookup"><span data-stu-id="8038b-208">Planning for branch-site voice resiliency in Lync Server 2013</span></span>](lync-server-2013-planning-for-branch-site-voice-resiliency.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

