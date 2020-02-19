---
title: 'Lync Server 2013: 포트 요약-조정 된 통합에 지, NAT 사용 개인 IP 주소의 DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: a296c2af-54d4-4b4f-9795-9191baf688cb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412756(v=OCS.15)
ms:contentKeyID: 48184955
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a90da0679fb48396cf3441464646a27bd2e0caa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="9de81-102">포트 요약-조정 된 통합에 지, Lync Server 2013에서 NAT를 사용 하는 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="9de81-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9de81-103">_**마지막으로 수정 된 항목:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="9de81-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="9de81-104">이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge Server 기능은 Lync Server 2010에서 구현 된 것과 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="9de81-105">가장 큰 차이점은 XMPP(Extensible Messaging and Presence Protocol)에 대한 포트 **5269 over TCP** 항목이 추가되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="9de81-106">Lync Server 2013는 선택적으로에 지 서버 또는에 지 풀 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버에 XMPP 프록시를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="9de81-107">이제에 지 서버는 IPv4 외에도 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="9de81-108">명확한 이해를 위해 시나리오에서는 IPv4만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="9de81-109">**NAT를 사용 하는 개인 IP 주소가 포함 된 확장 통합에 지에 대 한 엔터프라이즈 경계 네트워크**</span><span class="sxs-lookup"><span data-stu-id="9de81-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="9de81-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="9de81-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="9de81-111">포트 및 프로토콜 세부 정보</span><span class="sxs-lookup"><span data-stu-id="9de81-111">Port and Protocol Details</span></span>

<span data-ttu-id="9de81-112">외부 액세스를 제공할 기능을 지원하는 데 필요한 포트만 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="9de81-p103">원격 액세스가 에지 서비스에 작동하려면 SIP 트래픽이 인바운드/아웃바운드 에지 트래픽 그림에서처럼 양방향으로 전달될 수 있어야 합니다. 다른 방식으로 시작될 경우, 액세스 에지 서비스와 주고 받는 SIP 메시징에는 IM(인스턴트 메시징), 현재 상태, 웹 회의, A/V(오디오/비디오) 및 페더레이션이 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="9de81-115">확장 통합에 지에 대 한 방화벽 요약, NAT 사용 개인 IP 주소의 DNS 부하 분산 (예: 외부 인터페이스-노드 1 및 노드 2)</span><span class="sxs-lookup"><span data-stu-id="9de81-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9de81-116">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="9de81-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9de81-117">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-117">Source IP address</span></span></th>
<th><span data-ttu-id="9de81-118">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-118">Destination IP address</span></span></th>
<th><span data-ttu-id="9de81-119">Notes</span><span class="sxs-lookup"><span data-stu-id="9de81-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9de81-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9de81-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9de81-121">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-121">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-122">XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="9de81-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="9de81-123">정의된 XMPP 페더레이션의 XMPP 연락처로부터 들어오는 트래픽을 XMPP 프록시 서비스에서 허용</span><span class="sxs-lookup"><span data-stu-id="9de81-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9de81-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9de81-125">XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="9de81-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="9de81-126">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-126">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-127">XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처로 트래픽을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="9de81-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="9de81-129">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-130">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-130">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-131">인증서 해지/CRL 검사 및 검색</span><span class="sxs-lookup"><span data-stu-id="9de81-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="9de81-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="9de81-133">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-134">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-134">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-135">TCP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="9de81-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="9de81-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="9de81-137">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-138">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-138">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-139">UDP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="9de81-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-140">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9de81-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9de81-141">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-141">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-142">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-143">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="9de81-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-144">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9de81-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9de81-145">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-145">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-146">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-147">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="9de81-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-148">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9de81-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9de81-149">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-150">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-150">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-151">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="9de81-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-152">Web 회의/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9de81-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9de81-153">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-153">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-154">에 지 서버 웹 회의에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-155">웹 회의 미디어</span><span class="sxs-lookup"><span data-stu-id="9de81-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-156">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="9de81-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9de81-157">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-158">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-158">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-159">Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와의 페더레이션에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-160">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="9de81-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9de81-161">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-162">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-162">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-163">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-164">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="9de81-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9de81-165">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-165">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-166">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-167">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="9de81-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-168">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="9de81-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9de81-169">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-169">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-170">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-171">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="9de81-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-172">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9de81-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9de81-173">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-174">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-174">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-175">3478 아웃 바운드는 Lync Server가 통신 중인에 지 서버 및에 지 서버-에 지 서버에서의 미디어 트래픽에 대 한 버전을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="9de81-176">Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와의 페더레이션, 그리고 여러 개의에 지 풀이 회사 내에 배포 된 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-177">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9de81-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9de81-178">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-178">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-179">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-180">UDP/3478을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="9de81-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9de81-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9de81-182">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-182">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-183">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-184">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="9de81-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-185">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9de81-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9de81-186">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-187">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-187">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-188">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="9de81-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="9de81-189">확장 통합에 지에 대 한 방화벽 요약, NAT 사용 개인 IP 주소의 DNS 부하 분산: 내부 인터페이스-노드 1 및 노드 2 (예제)</span><span class="sxs-lookup"><span data-stu-id="9de81-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9de81-190">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="9de81-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9de81-191">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-191">Source IP address</span></span></th>
<th><span data-ttu-id="9de81-192">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-192">Destination IP address</span></span></th>
<th><span data-ttu-id="9de81-193">설명</span><span class="sxs-lookup"><span data-stu-id="9de81-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9de81-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9de81-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9de81-195">Any (프런트 엔드 서버 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="9de81-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="9de81-196">에 지 서버 내부 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9de81-197">프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="9de81-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9de81-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9de81-199">모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="9de81-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9de81-200">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de81-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9de81-201">아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)에서에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de81-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9de81-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9de81-203">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de81-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9de81-204">모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="9de81-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="9de81-205">에 지 서버 내부 인터페이스에서 디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소에 대 한 인바운드 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="9de81-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="9de81-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="9de81-207">Any (프런트 엔드 서버 IP 주소 또는 프런트 엔드 풀의 각 프런트 엔드 서버 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="9de81-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="9de81-208">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de81-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9de81-209">프런트 엔드 서버 또는 풀의 각 프런트 엔드 서버에서에 지 서버 내부 인터페이스로의 웹 회의 트래픽</span><span class="sxs-lookup"><span data-stu-id="9de81-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="9de81-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="9de81-211">Any (프런트 엔드 서버 IP 주소, 또는 프런트 엔드 풀 IP 주소 또는이에 지 서버를 사용 하는 Sba (survivable 분기 서버로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="9de81-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="9de81-212">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de81-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9de81-213">이에 지 서버를 사용 하 여 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소 또는 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에서 A/V 사용자 인증 (A/V 인증 서비스)</span><span class="sxs-lookup"><span data-stu-id="9de81-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9de81-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9de81-215">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-215">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-216">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de81-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9de81-217">내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 설정 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="9de81-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9de81-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9de81-219">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-219">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-220">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de81-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9de81-221">내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="9de81-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="9de81-223">Any (프런트 엔드 서버 IP 주소 또는 중앙 관리 저장소를 보유 하는 풀로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="9de81-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="9de81-224">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de81-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9de81-225">중앙 관리 저장소에서 에지 서버로 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="9de81-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="9de81-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="9de81-227">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-227">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-228">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de81-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9de81-229">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령 줄 (ClsController .exe) 또는 에이전트 (Clscontroller) 명령 및 로그 수집을 사용 하는 중앙화 된 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="9de81-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="9de81-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="9de81-231">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-231">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-232">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de81-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9de81-233">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령 줄 (ClsController .exe) 또는 에이전트 (Clscontroller) 명령 및 로그 수집을 사용 하는 중앙화 된 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="9de81-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="9de81-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="9de81-235">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-235">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-236">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9de81-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="9de81-237">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령 줄 (ClsController .exe) 또는 에이전트 (Clscontroller) 명령 및 로그 수집을 사용 하는 중앙화 된 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="9de81-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="9de81-238">페더레이션에 대한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="9de81-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9de81-239">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="9de81-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9de81-240">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-240">Source IP address</span></span></th>
<th><span data-ttu-id="9de81-241">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-241">Destination IP address</span></span></th>
<th><span data-ttu-id="9de81-242">Notes</span><span class="sxs-lookup"><span data-stu-id="9de81-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9de81-243">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9de81-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9de81-244">액세스 에지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="9de81-245">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-245">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-246">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="9de81-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="9de81-247">방화벽 요약 - 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="9de81-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9de81-248">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="9de81-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9de81-249">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-249">Source IP address</span></span></th>
<th><span data-ttu-id="9de81-250">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-250">Destination IP address</span></span></th>
<th><span data-ttu-id="9de81-251">Notes</span><span class="sxs-lookup"><span data-stu-id="9de81-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9de81-252">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9de81-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9de81-253">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="9de81-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9de81-254">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-255">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="9de81-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-256">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="9de81-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="9de81-257">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-258">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="9de81-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="9de81-259">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="9de81-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-260">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="9de81-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="9de81-261">클라이언트</span><span class="sxs-lookup"><span data-stu-id="9de81-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="9de81-262">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-263">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="9de81-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-264">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="9de81-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="9de81-265">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-266">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9de81-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9de81-267">공용 IM 연결이 구성된 경우 Windows Live Messenger와의 A/V 세션에 사용됨</span><span class="sxs-lookup"><span data-stu-id="9de81-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9de81-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9de81-269">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-270">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9de81-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9de81-271">Windows Live Messenger와의 공용 IM 연결 시 필수</span><span class="sxs-lookup"><span data-stu-id="9de81-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-272">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="9de81-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="9de81-273">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="9de81-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="9de81-274">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="9de81-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="9de81-275">Windows Live Messenger와의 공용 IM 연결 시 필수</span><span class="sxs-lookup"><span data-stu-id="9de81-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="9de81-276">확장 가능 메시징 및 현재 상태 프로토콜에 대한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="9de81-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9de81-277">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="9de81-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="9de81-278">원본(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="9de81-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="9de81-279">대상(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="9de81-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="9de81-280">설명</span><span class="sxs-lookup"><span data-stu-id="9de81-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9de81-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9de81-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9de81-282">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-282">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-283">에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9de81-284">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9de81-285">페더레이션 XMPP 파트너의에 지 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9de81-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="9de81-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="9de81-287">에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="9de81-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="9de81-288">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-288">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-289">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="9de81-290">에 지 서버 XMPP 프록시에서 페더레이션 XMPP 파트너와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9de81-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9de81-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="9de81-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="9de81-292">모두</span><span class="sxs-lookup"><span data-stu-id="9de81-292">Any</span></span></p></td>
<td><p><span data-ttu-id="9de81-293">각 내부에 지 서버 인터페이스 IP</span><span class="sxs-lookup"><span data-stu-id="9de81-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="9de81-294">프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서에 지 서버 내부 IP 주소 또는 각에 지 풀 구성원의 내부 IP 주소로 내부 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="9de81-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

