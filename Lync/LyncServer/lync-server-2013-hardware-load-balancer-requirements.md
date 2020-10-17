---
title: Lync Server 2013 하드웨어 부하 분산 장치 요구 사항
description: Lync Server 2013 하드웨어 부하 분산 장치 요구 사항
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
ms.openlocfilehash: 69cbf79c1fd7551dfd428c23ed22c924d0805c43
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552924"
---
# <a name="hardware-load-balancer-requirements-for-lync-server-2013"></a><span data-ttu-id="0c2e4-103">Lync Server 2013에 대 한 하드웨어 부하 분산 장치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c2e4-103">Hardware load balancer requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c2e4-104">_**마지막으로 수정 된 항목:** 2015-05-11_</span><span class="sxs-lookup"><span data-stu-id="0c2e4-104">_**Topic Last Modified:** 2015-05-11_</span></span>

<span data-ttu-id="0c2e4-105">Lync Server 2013 확장 통합에 지 토폴로지는 기본적으로 Lync Server를 사용 하는 다른 조직과 함께 새 배포에 대 한 DNS 부하 분산에 최적화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-105">The Lync Server 2013 scaled consolidated Edge topology is optimized for DNS load balancing for new deployments federating primarily with other organizations using Lync Server.</span></span> <span data-ttu-id="0c2e4-106">다음과 같은 시나리오에 고가용성이 필요한 경우에는 에지 서버 풀에서 다음에 대해 하드웨어 부하 분산 장치를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-106">If high availability is required for any of the following scenarios, a hardware load balancer must be used on Edge Server pools for the following:</span></span>

  - <span data-ttu-id="0c2e4-107">Office Communications Server 2007 R2 또는 Office Communications Server 2007을 사용 하는 조직과의 페더레이션</span><span class="sxs-lookup"><span data-stu-id="0c2e4-107">Federation with organizations using Office Communications Server 2007 R2 or Office Communications Server 2007</span></span>

  - <span data-ttu-id="0c2e4-108">Exchange 2010 SP1 이전 버전에서 exchange UM을 사용 하는 원격 사용자를 위한 exchange UM</span><span class="sxs-lookup"><span data-stu-id="0c2e4-108">Exchange UM for remote users using Exchange UM prior to Exchange 2010 with SP1</span></span>

  - <span data-ttu-id="0c2e4-109">공용 IM 사용자 연결</span><span class="sxs-lookup"><span data-stu-id="0c2e4-109">Connectivity to public IM users</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0c2e4-p102">DNS 부하 분산과 하드웨어 부하 분산을 서로 다른 인터페이스에서 사용할 수 없습니다. 두 인터페이스에서 모두 하드웨어 부하 분산 또는 DNS 부하 분산을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0c2e4-p103">하드웨어 부하 분산 장치를 사용하는 경우, 내부 네트워크와의 연결을 위해 배포된 부하 분산 장치는 액세스 에지 서비스와 A/V 에지 서비스를 실행 중인 서버의 트래픽 부하만 분산하도록 구성해야 합니다. 즉, 이 부하 분산 장치를 사용하여 내부 웹 회의 에지 서비스 또는 내부 XMPP 프록시 서비스에 대한 트래픽 부하 분산을 수행할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-p103">If you are using a hardware load balancer, the load balancer deployed for connections with the internal network must be configured to load balance only the traffic to servers running the Access Edge service and the A/V Edge service. It cannot load balance the traffic to the internal Web Conferencing Edge service or the internal XMPP Proxy service.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="0c2e4-114">DSR (direct server return) NAT는 Lync Server 2013에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-114">The direct server return (DSR) NAT is not supported with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="0c2e4-115">하드웨어 부하 분산 장치에서 Lync Server 2013에 필요한 필요한 기능을 지원 하는지 여부를 확인 하려면 "Lync Server 2010 부하 분산 장치 파트너"를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452) .</span><span class="sxs-lookup"><span data-stu-id="0c2e4-115">To determine whether your hardware load balancer supports the necessary features required by Lync Server 2013, see "Lync Server 2010 Load Balancer Partners" at [https://go.microsoft.com/fwlink/p/?linkId=202452](https://go.microsoft.com/fwlink/p/?linkid=202452).</span></span>

<div>

## <a name="hardware-load-balancer-requirements-for-edge-servers-running-the-av-edge-service"></a><span data-ttu-id="0c2e4-116">A/V 에지 서비스를 실행하는 에지 서버에 대한 하드웨어 부하 분산 장치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c2e4-116">Hardware Load Balancer Requirements for Edge Servers Running the A/V Edge Service</span></span>

<span data-ttu-id="0c2e4-117">다음은 A/V에 지 서비스를 실행 하는에 지 서버에 대 한 하드웨어 부하 분산 장치 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-117">Following are the hardware load balancer requirements for Edge Servers running the A/V Edge service:</span></span>

  - <span data-ttu-id="0c2e4-p104">내부 및 외부 포트 443에 대해 TCP Nagling을 해제합니다. Nagling은 보다 효율적인 전송을 위해 여러 개의 작은 패킷을 하나의 큰 패킷으로 결합하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-p104">Turn off TCP nagling for both internal and external ports 443. Nagling is the process of combining several small packets into a single, larger packet for more efficient transmission.</span></span>

  - <span data-ttu-id="0c2e4-120">외부 포트 범위 50,000~59,999에 대해 TCP Nagling을 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-120">Turn off TCP nagling for external port range 50,000 – 59,999.</span></span>

  - <span data-ttu-id="0c2e4-121">내부 또는 외부 방화벽에 NAT를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-121">Do not use NAT on the internal or external firewall.</span></span>

  - <span data-ttu-id="0c2e4-122">에지 내부 인터페이스는 에지 서버 외부 인터페이스와 다른 네트워크에 있어야 하며 두 인터페이스 간의 라우팅은 사용할 수 없도록 설정되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-122">The edge internal interface must be on a different network than the Edge Server external interface and routing between them must be disabled.</span></span>

  - <span data-ttu-id="0c2e4-123">A/V에 지 서비스를 실행 하는에 지 서버의 외부 인터페이스는 공용으로 라우팅할 수 있는 IP 주소를 사용 해야 하며,에 지 외부 IP 주소에 NAT 또는 포트 변환이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-123">The external interface of the Edge Server running the A/V Edge Service must use publicly routable IP addresses and no NAT or port translation on any of the edge external IP addresses.</span></span>

</div>

<div>

## <a name="hardware-load-balancer-requirements"></a><span data-ttu-id="0c2e4-124">하드웨어 부하 분산 장치 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c2e4-124">Hardware Load Balancer Requirements</span></span>

<span data-ttu-id="0c2e4-125">웹 서비스의 경우 Lync Server 2013에서 쿠키 기반 선호도 요구 사항이 크게 감소 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-125">Cookie-based affinity requirements are greatly reduced in Lync Server 2013 for Web services.</span></span> <span data-ttu-id="0c2e4-126">Lync Server 2013을 배포 하 고 Lync Server 2010 프런트 엔드 서버 또는 프런트 엔드 풀을 유지 하지 않을 경우에는 쿠키 기반 지 속성을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-126">If you are deploying Lync Server 2013 and will not retain any Lync Server 2010 Front End Servers or Front End pools, you do not need cookie-based persistence.</span></span> <span data-ttu-id="0c2e4-127">그러나 Lync server 2010 프런트 엔드 서버 또는 프런트 엔드 풀을 일시적으로 나 영구적으로 유지 하려는 경우에도 Lync Server 2010에 대해 배포 되 고 구성 될 때 쿠키 기반 지 속성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-127">However, if you will temporarily or permanently retain any Lync Server 2010 Front End Servers or Front End pools, you still use cookie-based persistence as it is deployed and configured for Lync Server 2010.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c2e4-128"><STRONG>배포에서 필요하지 않은 경우에도 쿠키 기반 선호도를 사용하려는 경우</STRONG> 부정적인 영향은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-128"><STRONG>If you decide to use cookie-based affinity even though your deployment does not require it</STRONG>, there is no negative impact to doing so.</span></span>



</div>

<span data-ttu-id="0c2e4-129">쿠키 기반 선호도를 **사용하지 않는** 배포에는 다음이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-129">For deployments that **will not use** cookie-based affinity:</span></span>

  - <span data-ttu-id="0c2e4-p106">포트 4443에 대한 역방향 프록시 게시 규칙에 대해 **호스트 헤더 전달**을 True로 설정합니다. 그러면 원래 URL이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-p106">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

<span data-ttu-id="0c2e4-132">쿠키 기반 선호도를 **사용하는** 배포에는 다음이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-132">For deployments that **will use** cookie-based affinity:</span></span>

  - <span data-ttu-id="0c2e4-p107">포트 4443에 대한 역방향 프록시 게시 규칙에 대해 **호스트 헤더 전달**을 True로 설정합니다. 그러면 원래 URL이 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-p107">On the reverse proxy publishing rule for port 4443, set **Forward host header** to True. This will ensure that the original URL is forwarded.</span></span>

  - <span data-ttu-id="0c2e4-135">하드웨어 부하 분산 장치 쿠키는 httpOnly로 표시해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-135">Hardware load balancer cookie MUST NOT be marked httpOnly</span></span>

  - <span data-ttu-id="0c2e4-136">하드웨어 부하 분산 장치 쿠키에 만료 시간이 있어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-136">Hardware load balancer cookie MUST NOT have an expiration time</span></span>

  - <span data-ttu-id="0c2e4-137">하드웨어 부하 분산 장치 쿠키 이름은 **MS-WSMAN**(웹 서비스에 필요한 값이며 변경할 수 없음)으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-137">Hardware load balancer cookie MUST be named **MS-WSMAN** (This is the value that the Web services expect, and cannot be changed)</span></span>

  - <span data-ttu-id="0c2e4-p108">동일한 TCP 연결의 이전 HTTP 응답에서 이미 쿠키를 가져왔는지 여부에 관계없이, 들어오는 HTTP 요청에 쿠키가 없었던 모든 HTTP 응답에서 하드웨어 부하 분산 장치 쿠키를 설정해야 합니다. 부하 분산 장치에서 TCP 연결당 한 번만 쿠키 삽입이 수행되도록 최적화하는 경우에는 해당 최적화를 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-p108">Hardware load balancer cookie MUST be set in every HTTP response for which the incoming HTTP request did not have a cookie, regardless of whether a previous HTTP response on that same TCP connection had already obtained a cookie. If the load balancer optimizes cookie insert to only occur once per TCP connection, that optimization MUST NOT be used</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c2e4-140">일반적인 하드웨어 부하 분산 장치 구성에서는 클라이언트 사용 및/또는 응용 프로그램 상호 작용을 통해 세션 상태를 유지 관리 하므로 Lync Server 및 Lync 2013 클라이언트에 적합 한 원본 주소 선호도 및 20 분 TCP 세션 수명을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-140">Typical hardware load balancer configurations use source-address affinity and a 20 min. TCP session lifetime, which is fine for Lync Server and Lync 2013 clients because session state is maintained through client usage and/or and application interaction.</span></span>



</div>

<span data-ttu-id="0c2e4-141">모바일 장치를 배포하는 경우 하드웨어 부하 분산 장치는 TCP 세션 내의 개별 요청 부하를 분산할 수 있어야 합니다(대상 IP 주소를 기준으로 개별 요청 부하를 분산할 수 있어야 함).</span><span class="sxs-lookup"><span data-stu-id="0c2e4-141">If you are deploying mobile devices, your hardware load balancer must be able to load balance individual request within a TCP session (in effect, you must be able to load balance an individual request based on the target IP address).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0c2e4-p109">F5 하드웨어 부하 분산 장치에는 TCP 연결 내의 각 요청이 개별적으로 부하 분산되도록 하는 OneConnect라는 기능이 있습니다. 모바일 장치를 배포하는 경우 하드웨어 부하 분산 장치 공급업체에서 이와 동일한 기능을 지원하는지 확인하십시오. 최신 Apple iOS 모바일 앱의 경우 TLS(전송 계층 보안) 버전 1.2가 필요합니다. F5는 이 버전을 위한 특정 설정을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-p109">F5 hardware load balancers have a feature called OneConnect that ensures each request within a TCP connection is individually load balanced. If you are deploying mobile devices, ensure your hardware load balancer vendor supports the same functionality. The latest Apple iOS mobile apps require Transport Layer Security (TLS) version 1.2. F5 provides specific settings for this.</span></span><BR><span data-ttu-id="0c2e4-146">타사 하드웨어 부하 분산 장치에 대 한 자세한 내용은 <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span><span class="sxs-lookup"><span data-stu-id="0c2e4-146">For details on third party hardware load balancers, see <A href="https://go.microsoft.com/fwlink/p/?linkid=230700">https://go.microsoft.com/fwlink/p/?linkId=230700</A></span></span>



</div>

<span data-ttu-id="0c2e4-147">다음은 디렉터 및 프런트 엔드 풀 웹 서비스에 대한 하드웨어 부하 분산 장치 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-147">Following are the hardware load balancer requirements for Director and Front End pool Web Services:</span></span>

  - <span data-ttu-id="0c2e4-148">내부 웹 서비스 Vip의 경우 \_ 하드웨어 부하 분산 장치에서 원본 주소 지 속성 (내부 포트 80, 443)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-148">For internal Web Services VIPs, set Source\_addr persistence (internal port 80, 443) on the hardware load balancer.</span></span> <span data-ttu-id="0c2e4-149">Lync Server 2013의 경우 원본 \_ 주소 지 속성은 단일 IP 주소에서 들어오는 여러 연결이 세션 상태를 유지 하기 위해 항상 하나의 서버로 전송 되는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-149">For Lync Server 2013, Source\_addr persistence means that multiple connections coming from a single IP address are always sent to one server to maintain session state.</span></span>

  - <span data-ttu-id="0c2e4-150">1800초의 TCP 유휴 시간 제한을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-150">Use TCP idle timeout of 1800 seconds.</span></span>

  - <span data-ttu-id="0c2e4-p111">역방향 프록시와 다음 홉 풀의 하드웨어 부하 분산 장치 사이에 있는 방화벽에 역방향 프록시에서 하드웨어 부하 분산 장치로 전송되는 https: 트래픽(포트 4443)을 허용하는 규칙을 만듭니다. 하드웨어 부하 분산 장치는 포트 80, 443 및 4443에서 수신 대기하도록 구성되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-p111">On the firewall between the reverse proxy and the next hop pool’s hardware load balancer, create a rule to allow https: traffic on port 4443, from the reverse proxy to the hardware load balancer. The hardware load balancer must be configured to listen on ports 80, 443, and 4443.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0c2e4-153">하드웨어 부하 분산 장치의 구성에 대 한 자세한 내용을 보려면 <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Lync Server 2013에서 포트 요약-확장 된 통합에 지를 하드웨어 부하 분산 장치</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-153">For further reading on configuration of the hardware load balancer, please review <A href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="summary-of-hardware-load-balancer-affinity-requirements"></a><span data-ttu-id="0c2e4-154">하드웨어 부하 분산 장치 선호도 요구 사항 요약</span><span class="sxs-lookup"><span data-stu-id="0c2e4-154">Summary of Hardware Load Balancer Affinity Requirements</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c2e4-155">클라이언트/사용자 위치</span><span class="sxs-lookup"><span data-stu-id="0c2e4-155">Client/user location</span></span></th>
<th><span data-ttu-id="0c2e4-156">외부 웹 서비스 FQDN 선호도 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c2e4-156">External web services FQDN affinity requirements</span></span></th>
<th><span data-ttu-id="0c2e4-157">내부 웹 서비스 FQDN 선호도 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0c2e4-157">Internal web services FQDN affinity requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c2e4-158">Lync Web App (내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="0c2e4-158">Lync Web App (internal and external users)</span></span></p>
<p><span data-ttu-id="0c2e4-159">모바일 장치(내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="0c2e4-159">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-160">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="0c2e4-160">No affinity</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-161">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="0c2e4-161">Source address affinity</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c2e4-162">Lync Web App (외부 사용자만 해당)</span><span class="sxs-lookup"><span data-stu-id="0c2e4-162">Lync Web App (external users only)</span></span></p>
<p><span data-ttu-id="0c2e4-163">모바일 장치(내부 및 외부 사용자)</span><span class="sxs-lookup"><span data-stu-id="0c2e4-163">Mobile device (internal and external users)</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-164">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="0c2e4-164">No affinity</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-165">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="0c2e4-165">Source address affinity</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c2e4-166">Lync Web App (내부 사용자만 해당)</span><span class="sxs-lookup"><span data-stu-id="0c2e4-166">Lync Web App (internal users only)</span></span></p>
<p><span data-ttu-id="0c2e4-167">모바일 장치(배포되지 않음)</span><span class="sxs-lookup"><span data-stu-id="0c2e4-167">Mobile device (not deployed)</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-168">선호도 없음</span><span class="sxs-lookup"><span data-stu-id="0c2e4-168">No affinity</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-169">원본 주소 선호도</span><span class="sxs-lookup"><span data-stu-id="0c2e4-169">Source address affinity</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="port-monitoring-for-hardware-load-balancers"></a><span data-ttu-id="0c2e4-170">하드웨어 부하 분산 장치용 포트 모니터링</span><span class="sxs-lookup"><span data-stu-id="0c2e4-170">Port Monitoring for Hardware Load Balancers</span></span>

<span data-ttu-id="0c2e4-171">하드웨어 부하 분산 장치에 대해 포트 모니터링을 정의하여 하드웨어 또는 통신 오류로 인해 특정 서비스를 더 이상 사용할 수 없는 시기를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-171">You define port monitoring on the hardware load balancers to determine when specific services are no longer available due to hardware or communications failure.</span></span> <span data-ttu-id="0c2e4-172">예를 들어 프런트 엔드 서버 또는 프런트 엔드 풀에 오류가 발생 하 여 프런트 엔드 서버 서비스 (RTCSRV)가 중지 되는 경우 HLB 모니터링에서는 웹 서비스의 트래픽 수신도 중지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-172">For example, if the Front End Server service (RTCSRV) stops because the Front End Server or Front End pool fails, the HLB monitoring should also stop receiving traffic on the Web Services.</span></span> <span data-ttu-id="0c2e4-173">HLB에 대해 포트 모니터링을 구현하여 다음 항목을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="0c2e4-173">You implement port monitoring on the HLB to monitor the following:</span></span>

### <a name="front-end-server-user-pool--hlb-internal-interface"></a><span data-ttu-id="0c2e4-174">프런트 엔드 서버 사용자 풀-HLB 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0c2e4-174">Front End Server User Pool – HLB Internal Interface</span></span>

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
<th><span data-ttu-id="0c2e4-175">가상 IP/포트</span><span class="sxs-lookup"><span data-stu-id="0c2e4-175">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="0c2e4-176">노드 포트</span><span class="sxs-lookup"><span data-stu-id="0c2e4-176">Node Port</span></span></th>
<th><span data-ttu-id="0c2e4-177">노드 컴퓨터/모니터</span><span class="sxs-lookup"><span data-stu-id="0c2e4-177">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="0c2e4-178">지속성 프로필</span><span class="sxs-lookup"><span data-stu-id="0c2e4-178">Persistence Profile</span></span></th>
<th><span data-ttu-id="0c2e4-179">참고</span><span class="sxs-lookup"><span data-stu-id="0c2e4-179">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c2e4-180">&lt;풀 &gt; 웹-int_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="0c2e4-180">&lt;pool&gt;web-int_mco_443_vs</span></span></p>
<p><span data-ttu-id="0c2e4-181">443</span><span class="sxs-lookup"><span data-stu-id="0c2e4-181">443</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-182">443</span><span class="sxs-lookup"><span data-stu-id="0c2e4-182">443</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-183">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="0c2e4-183">Front End</span></span></p>
<p><span data-ttu-id="0c2e4-184">5061</span><span class="sxs-lookup"><span data-stu-id="0c2e4-184">5061</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-185">원본</span><span class="sxs-lookup"><span data-stu-id="0c2e4-185">Source</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-186">H</span><span class="sxs-lookup"><span data-stu-id="0c2e4-186">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c2e4-187">&lt;풀 &gt; 웹-int_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="0c2e4-187">&lt;pool&gt;web-int_mco_80_vs</span></span></p>
<p><span data-ttu-id="0c2e4-188">80</span><span class="sxs-lookup"><span data-stu-id="0c2e4-188">80</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-189">80</span><span class="sxs-lookup"><span data-stu-id="0c2e4-189">80</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-190">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="0c2e4-190">Front End</span></span></p>
<p><span data-ttu-id="0c2e4-191">5061</span><span class="sxs-lookup"><span data-stu-id="0c2e4-191">5061</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-192">원본</span><span class="sxs-lookup"><span data-stu-id="0c2e4-192">Source</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-193">HTTP</span><span class="sxs-lookup"><span data-stu-id="0c2e4-193">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="front-end-server-user-pool--hlb-external-interface"></a><span data-ttu-id="0c2e4-194">프런트 엔드 서버 사용자 풀-HLB External Interface</span><span class="sxs-lookup"><span data-stu-id="0c2e4-194">Front End Server User Pool – HLB External Interface</span></span>

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
<th><span data-ttu-id="0c2e4-195">가상 IP/포트</span><span class="sxs-lookup"><span data-stu-id="0c2e4-195">Virtual IP/Port</span></span></th>
<th><span data-ttu-id="0c2e4-196">노드 포트</span><span class="sxs-lookup"><span data-stu-id="0c2e4-196">Node Port</span></span></th>
<th><span data-ttu-id="0c2e4-197">노드 컴퓨터/모니터</span><span class="sxs-lookup"><span data-stu-id="0c2e4-197">Node Machine/Monitor</span></span></th>
<th><span data-ttu-id="0c2e4-198">지속성 프로필</span><span class="sxs-lookup"><span data-stu-id="0c2e4-198">Persistence Profile</span></span></th>
<th><span data-ttu-id="0c2e4-199">참고</span><span class="sxs-lookup"><span data-stu-id="0c2e4-199">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c2e4-200">&lt;풀 &gt; web_mco_443_vs</span><span class="sxs-lookup"><span data-stu-id="0c2e4-200">&lt;pool&gt;web_mco_443_vs</span></span></p>
<p><span data-ttu-id="0c2e4-201">443</span><span class="sxs-lookup"><span data-stu-id="0c2e4-201">443</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-202">4443</span><span class="sxs-lookup"><span data-stu-id="0c2e4-202">4443</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-203">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="0c2e4-203">Front End</span></span></p>
<p><span data-ttu-id="0c2e4-204">5061</span><span class="sxs-lookup"><span data-stu-id="0c2e4-204">5061</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-205">없음</span><span class="sxs-lookup"><span data-stu-id="0c2e4-205">None</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-206">H</span><span class="sxs-lookup"><span data-stu-id="0c2e4-206">HTTPS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c2e4-207">&lt;풀 &gt; web_mco_80_vs</span><span class="sxs-lookup"><span data-stu-id="0c2e4-207">&lt;pool&gt;web_mco_80_vs</span></span></p>
<p><span data-ttu-id="0c2e4-208">80</span><span class="sxs-lookup"><span data-stu-id="0c2e4-208">80</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-209">8080</span><span class="sxs-lookup"><span data-stu-id="0c2e4-209">8080</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-210">프런트 엔드</span><span class="sxs-lookup"><span data-stu-id="0c2e4-210">Front End</span></span></p>
<p><span data-ttu-id="0c2e4-211">5061</span><span class="sxs-lookup"><span data-stu-id="0c2e4-211">5061</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-212">없음</span><span class="sxs-lookup"><span data-stu-id="0c2e4-212">None</span></span></p></td>
<td><p><span data-ttu-id="0c2e4-213">HTTP</span><span class="sxs-lookup"><span data-stu-id="0c2e4-213">HTTP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

