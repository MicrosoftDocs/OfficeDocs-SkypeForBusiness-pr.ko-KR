---
title: Lync Server 2013 하드웨어 부하 분산 장치 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware load balancer requirements
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49287208
ms.date: 05/11/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85ed4195d80ecc755faea74ddedb790c9f41ebfb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="b3aa6-102">Lync Server 2013에 대한 하드웨어 부하 분산 장치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3aa6-102">Hardware load balancer requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3aa6-103">_**마지막으로 수정한 주제:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="b3aa6-103">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="b3aa6-104">Lync Server 2013 배율 조정 된 통합에 지 토폴로지는 기본적으로 Lync Server를 사용 하 여 다른 조직에 페더레이션 하는 새 배포에 대 한 DNS 부하 분산에 최적화 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-104">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="b3aa6-105">다음 시나리오에 대해 높은 가용성을 요구 하는 경우에는 다음과 같은 경우에 대 한 하드웨어 부하 분산 장치를 Edge 서버 풀에 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-105">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="b3aa6-106">Office Communications Server 2007 R2 또는 Office Communications Server 2007를 사용 하는 조직과의 페더레이션</span><span class="sxs-lookup"><span data-stu-id="b3aa6-106">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="b3aa6-107">Exchange 2010 SP1 이전에 exchange UM을 사용 하는 원격 사용자 용 exchange UM</span><span class="sxs-lookup"><span data-stu-id="b3aa6-107">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="b3aa6-108">공용 IM 사용자에 대 한 연결</span><span class="sxs-lookup"><span data-stu-id="b3aa6-108">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3aa6-109">한 인터페이스에서 DNS 부하 분산을 사용 하는 것은 불가능 하지만, 하드웨어 부하 분산이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-109">Using DNS load balancing on one interface and hardware load balancing on the other is not supported.</span></span> <span data-ttu-id="b3aa6-110">둘 다에 대해 인터페이스 또는 DNS 부하 분산에 대해 하드웨어 부하 분산을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-110">You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b3aa6-111">하드웨어 부하 분산 장치를 사용 하는 경우에는 내부 네트워크와의 연결에 대해 배포 된 부하 분산 장치를 구성 하 여 액세스에 지 서비스를 실행 하는 서버와 A/V에 대 한 서비스 소통량만 로드 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-111">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service.</span></span> <span data-ttu-id="b3aa6-112">내부 웹 회의 Edge 서비스 또는 내부 XMPP 프록시 서비스에 대 한 트래픽의 부하 균형을 조정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-112">It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b3aa6-113">DSR (direct server return) NAT는 Lync Server 2013에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-113">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="b3aa6-114">하드웨어 부하 분산 장치가 Lync Server 2013에서 요구 하는 필수 기능을 지원 하는지 여부를 확인 하려면에서 [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452)"Lync Server 2010 부하 분산 장치 파트너"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-114">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="b3aa6-115">A/V Edge 서비스를 실행 하는 Edge 서버의 하드웨어 부하 분산 장치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3aa6-115">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="b3aa6-116">다음은 A/V Edge 서비스를 실행 하는 Edge 서버의 하드웨어 부하 분산 장치 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-116">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="b3aa6-117">내부 및 외부 포트 443에 대해 TCP nagling를 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-117">Turn off TCP nagling for both internal and external ports 443.</span></span> <span data-ttu-id="b3aa6-118">Nagling는 여러 개의 작은 패킷을 하나의 대형 패킷으로 결합 하 여 효율적인 전송을 위해 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-118">Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="b3aa6-119">외부 포트 범위 5만-59999에 대해 TCP nagling을 끄십시오.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-119">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="b3aa6-120">내부 또는 외부 방화벽에서 NAT를 사용 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-120">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="b3aa6-121">Edge 내부 인터페이스는 Edge 서버 외부 인터페이스와 다른 네트워크에 있어야 하 고 그 사이의 라우팅은 비활성화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-121">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="b3aa6-122">A/V Edge 서비스를 실행 하는 Edge 서버의 외부 인터페이스는 공용 라우팅할 수 있는 IP 주소를 사용 해야 하며, 모든 Edge 외부 IP 주소에서 NAT 또는 포트 번역이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-122">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="b3aa6-123">하드웨어 부하 분산 장치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3aa6-123">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="b3aa6-124">웹 서비스의 Lync Server 2013에서 쿠키 기반 선호도 요구 사항이 크게 줄어들었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-124">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="b3aa6-125">Lync Server 2013을 배포 하 고 Lync Server 2010 프런트 엔드 서버 또는 프런트 엔드 풀을 유지 하지 않는 경우에는 쿠키 기반 지 속성이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-125">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="b3aa6-126">그러나 Lync Server 2010 프런트 엔드 서버 또는 프런트 엔드 풀을 일시적으로 또는 영구적으로 유지 하는 경우에는 Lync Server 2010에 대해 배포 하 고 구성 하는 동안에도 쿠키 기반 유지를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-126">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3aa6-127"><STRONG>배포에 필요 하지 않은 쿠키 기반 선호도를 사용 하기로 결정 한 경우</STRONG>, 이렇게 해도 부정적인 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-127"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="b3aa6-128">쿠키 기반 선호도를 **사용 하지** 않는 배포에는 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-128">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="b3aa6-129">포트 4443에 대 한 역방향 프록시 게시 규칙에서 **정방향 호스트 헤더** 를 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-129">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="b3aa6-130">이렇게 하면 원래 URL이 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-130">This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="b3aa6-131">쿠키 기반 선호도를 **사용** 하는 배포의 경우:</span><span class="sxs-lookup"><span data-stu-id="b3aa6-131">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="b3aa6-132">포트 4443에 대 한 역방향 프록시 게시 규칙에서 **정방향 호스트 헤더** 를 True로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-132">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True.</span></span> <span data-ttu-id="b3aa6-133">이렇게 하면 원래 URL이 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-133">This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="b3aa6-134">하드웨어 부하 분산 장치 쿠키는 httpOnly로 표시 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-134">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="b3aa6-135">하드웨어 부하 분산 장치 쿠키에는 만료 시간이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-135">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="b3aa6-136">하드웨어 부하 분산 장치 쿠키는 **MS-WSMAN** (웹 서비스에서 예상 하는 값 이며 변경할 수 없음)로 명명 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-136">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="b3aa6-137">동일한 TCP 연결에 대 한 이전 HTTP 응답에서 쿠키를 이미 가져왔는지 여부에 관계 없이 들어오는 HTTP 요청에 쿠키가 없는 모든 HTTP 응답에서 하드웨어 부하 분산 장치 쿠키를 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-137">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie.</span></span> <span data-ttu-id="b3aa6-138">부하 분산 장치가 TCP 연결 당 쿠키 삽입이 발생 하도록 최적화 하면 해당 최적화를 사용 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-138">If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b3aa6-139">일반적인 하드웨어 부하 분산 장치 구성에서는 클라이언트 사용 및/또는 응용 프로그램 조작을 통해 세션 상태가 유지 관리 되므로 Lync Server 및 Lync 2013 클라이언트에 적합 한 원본 주소 선호도 및 20 분 TCP 세션 수명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-139">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="b3aa6-140">모바일 장치를 배포 하는 경우 하드웨어 로드 균형 조정기는 TCP 세션 내에서 개별 요청에 대 한 부하 분산을 수행할 수 있어야 합니다 (즉, 대상 IP 주소를 기반으로 개별 요청의 부하를 분산할 수 있어야 함).</span><span class="sxs-lookup"><span data-stu-id="b3aa6-140">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b3aa6-141">F5 하드웨어 부하 분산 장치에는 TCP 연결 내의 각 요청이 개별적으로 부하 분산 됨을 확인 하는 OneConnect 이라는 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-141">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced.</span></span> <span data-ttu-id="b3aa6-142">모바일 장치를 배포 하는 경우 하드웨어 부하 분산 장치 공급 업체에서 동일한 기능을 지원 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-142">If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality.</span></span> <span data-ttu-id="b3aa6-143">최신 Apple iOS 모바일 앱에는 TLS (전송 계층 보안) 버전 1.2이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-143">The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2.</span></span> <span data-ttu-id="b3aa6-144">F5 키를 눌러이에 대 한 특정 설정을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-144">F5 provides specific settings for this.</span></span><BR><span data-ttu-id="b3aa6-145">타사 하드웨어 부하 분산 장치에 대 한 자세한 내용은 다음을 참조 하세요.<A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="b3aa6-145">For details on third party hardware load balancers, see <A href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="b3aa6-146">다음은 디렉터 및 프런트 엔드 풀 웹 서비스에 대 한 하드웨어 부하 분산 장치 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-146">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="b3aa6-147">내부 웹 서비스 Vip의 경우 하드웨어 부하\_분산 장치에서 원본 주소 지 속성 (내부 포트 80, 443)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-147">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="b3aa6-148">Lync Server 2013의 경우 원본\_주소 유지를 통해 단일 IP 주소에서 들어오는 여러 연결이 항상 하나의 서버로 전송 되어 세션 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-148">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="b3aa6-149">TCP 유휴 시간 제한 (1800 초)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-149">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="b3aa6-150">리버스 프록시와 다음 홉 풀의 하드웨어 부하 분산 장치 사이에 있는 방화벽에서 https: 포트 4443에서 트래픽을 허용 하는 규칙을 만듭니다 (역방향 프록시에서 하드웨어 로드 균형 조정기).</span><span class="sxs-lookup"><span data-stu-id="b3aa6-150">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer.</span></span> <span data-ttu-id="b3aa6-151">포트 80, 443 및 4443에서 수신 하도록 하드웨어 로드 균형 조정기를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-151">The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b3aa6-152">하드웨어 부하 분산 장치 구성에 대 한 자세한 내용은 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">포트 요약-확장 된 통합 모서리와 Lync Server 2013의 하드웨어 부하 분산 장치</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-152">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="b3aa6-153">하드웨어 부하 분산 장치 선호도 요구 사항 요약</span><span class="sxs-lookup"><span data-stu-id="b3aa6-153">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3aa6-154">클라이언트/사용자 위치</span><span class="sxs-lookup"><span data-stu-id="b3aa6-154">Client/user location</span></span></th>
<th><span data-ttu-id="b3aa6-155">외부 웹 서비스 FQDN 선호도 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3aa6-155">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="b3aa6-156">내부 웹 서비스 FQDN 선호도 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b3aa6-156">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3aa6-157">Lync Web App (내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="b3aa6-157">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="b3aa6-158">모바일 장치 (내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="b3aa6-158">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-159">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="b3aa6-159">No affinity</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-160">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="b3aa6-160">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3aa6-161">Lync Web App (외부 사용자만 해당)</span><span class="sxs-lookup"><span data-stu-id="b3aa6-161">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="b3aa6-162">모바일 장치 (내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="b3aa6-162">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-163">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="b3aa6-163">No affinity</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-164">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="b3aa6-164">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3aa6-165">Lync Web App (내부 사용자만 해당)</span><span class="sxs-lookup"><span data-stu-id="b3aa6-165">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="b3aa6-166">모바일 장치 (배포 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="b3aa6-166">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-167">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="b3aa6-167">No affinity</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-168">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="b3aa6-168">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="b3aa6-169">하드웨어 부하 분산 장치에 대 한 포트 모니터링</span><span class="sxs-lookup"><span data-stu-id="b3aa6-169">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="b3aa6-170">하드웨어 부하 분산 장치에서 포트 모니터링을 정의 하 여 하드웨어 또는 통신 오류로 인해 특정 서비스를 더 이상 사용할 수 없는 경우를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-170">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="b3aa6-171">예를 들어 프런트 엔드 서버 또는 프런트 엔드 풀에 오류가 발생 하 여 프런트 엔드 서버 서비스 (RTCSRV)가 중지 되는 경우 HLB 모니터링에서 웹 서비스의 트래픽 수신도 중지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-171">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="b3aa6-172">HLB에서 포트 모니터링을 구현 하 여 다음을 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3aa6-172">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="b3aa6-173">프런트 엔드 서버 사용자 풀 – HLB 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3aa6-173">Front End Server User Pool – HLB Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3aa6-174">가상 IP/포트</span><span class="sxs-lookup"><span data-stu-id="b3aa6-174">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="b3aa6-175">노드 포트</span><span class="sxs-lookup"><span data-stu-id="b3aa6-175">Node Port</span></span></th>
<th><span data-ttu-id="b3aa6-176">노드 컴퓨터/모니터</span><span class="sxs-lookup"><span data-stu-id="b3aa6-176">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="b3aa6-177">지 속성 프로필</span><span class="sxs-lookup"><span data-stu-id="b3aa6-177">Persistence Profile</span></span></th>
<th><span data-ttu-id="b3aa6-178">상속자</span><span class="sxs-lookup"><span data-stu-id="b3aa6-178">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3aa6-179">&lt;pool&gt;웹-int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="b3aa6-179">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="b3aa6-180">443</span><span class="sxs-lookup"><span data-stu-id="b3aa6-180">443</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-181">443</span><span class="sxs-lookup"><span data-stu-id="b3aa6-181">443</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-182">프론트 엔드</span><span class="sxs-lookup"><span data-stu-id="b3aa6-182">Front End</span></span></p>
<p><span data-ttu-id="b3aa6-183">5061</span><span class="sxs-lookup"><span data-stu-id="b3aa6-183">5061</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-184">Source</span><span class="sxs-lookup"><span data-stu-id="b3aa6-184">Source</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b3aa6-185">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3aa6-186">&lt;pool&gt;웹-int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="b3aa6-186">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="b3aa6-187">80</span><span class="sxs-lookup"><span data-stu-id="b3aa6-187">80</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-188">80</span><span class="sxs-lookup"><span data-stu-id="b3aa6-188">80</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-189">프론트 엔드</span><span class="sxs-lookup"><span data-stu-id="b3aa6-189">Front End</span></span></p>
<p><span data-ttu-id="b3aa6-190">5061</span><span class="sxs-lookup"><span data-stu-id="b3aa6-190">5061</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-191">Source</span><span class="sxs-lookup"><span data-stu-id="b3aa6-191">Source</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-192">HTTP</span><span class="sxs-lookup"><span data-stu-id="b3aa6-192">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="b3aa6-193">프런트 엔드 서버 사용자 풀-HLB 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b3aa6-193">Front End Server User Pool – HLB External Interface</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3aa6-194">가상 IP/포트</span><span class="sxs-lookup"><span data-stu-id="b3aa6-194">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="b3aa6-195">노드 포트</span><span class="sxs-lookup"><span data-stu-id="b3aa6-195">Node Port</span></span></th>
<th><span data-ttu-id="b3aa6-196">노드 컴퓨터/모니터</span><span class="sxs-lookup"><span data-stu-id="b3aa6-196">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="b3aa6-197">지 속성 프로필</span><span class="sxs-lookup"><span data-stu-id="b3aa6-197">Persistence Profile</span></span></th>
<th><span data-ttu-id="b3aa6-198">상속자</span><span class="sxs-lookup"><span data-stu-id="b3aa6-198">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3aa6-199">&lt;풀&gt;web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="b3aa6-199">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="b3aa6-200">443</span><span class="sxs-lookup"><span data-stu-id="b3aa6-200">443</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-201">4443</span><span class="sxs-lookup"><span data-stu-id="b3aa6-201">4443</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-202">프론트 엔드</span><span class="sxs-lookup"><span data-stu-id="b3aa6-202">Front End</span></span></p>
<p><span data-ttu-id="b3aa6-203">5061</span><span class="sxs-lookup"><span data-stu-id="b3aa6-203">5061</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-204">없음</span><span class="sxs-lookup"><span data-stu-id="b3aa6-204">None</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-205">HTTPS</span><span class="sxs-lookup"><span data-stu-id="b3aa6-205">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3aa6-206">&lt;풀&gt;web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="b3aa6-206">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="b3aa6-207">80</span><span class="sxs-lookup"><span data-stu-id="b3aa6-207">80</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-208">8080</span><span class="sxs-lookup"><span data-stu-id="b3aa6-208">8080</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-209">프론트 엔드</span><span class="sxs-lookup"><span data-stu-id="b3aa6-209">Front End</span></span></p>
<p><span data-ttu-id="b3aa6-210">5061</span><span class="sxs-lookup"><span data-stu-id="b3aa6-210">5061</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-211">없음</span><span class="sxs-lookup"><span data-stu-id="b3aa6-211">None</span></span></p></td>
<td><p><span data-ttu-id="b3aa6-212">HTTP</span><span class="sxs-lookup"><span data-stu-id="b3aa6-212">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

