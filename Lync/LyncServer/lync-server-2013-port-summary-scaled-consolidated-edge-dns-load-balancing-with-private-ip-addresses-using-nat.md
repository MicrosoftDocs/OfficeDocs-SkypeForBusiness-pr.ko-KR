---
title: 'Lync Server 2013: 포트 요약-조정 된 통합에 지, NAT 사용 개인 IP 주소의 DNS 부하 분산'
description: 'Lync Server 2013: 포트 요약-조정 된 통합에 지, NAT 사용 개인 IP 주소의 DNS 부하 분산입니다.'
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
ms.openlocfilehash: e0402b6682e86e5edf263fca78dfbe0f8fa070b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563944"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="b009e-103">포트 요약-조정 된 통합에 지, Lync Server 2013에서 NAT를 사용 하는 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="b009e-103">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b009e-104">_**마지막으로 수정 된 항목:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="b009e-104">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="b009e-105">이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge Server 기능은 Lync Server 2010에서 구현 된 것과 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="b009e-106">가장 큰 차이점은 XMPP(Extensible Messaging and Presence Protocol)에 대한 포트 **5269 over TCP** 항목이 추가되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="b009e-107">Lync Server 2013는 선택적으로에 지 서버 또는에 지 풀 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버에 XMPP 프록시를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="b009e-108">이제에 지 서버는 IPv4 외에도 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="b009e-109">명확한 이해를 위해 시나리오에서는 IPv4만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="b009e-110">**NAT를 사용 하는 개인 IP 주소가 포함 된 확장 통합에 지에 대 한 엔터프라이즈 경계 네트워크**</span><span class="sxs-lookup"><span data-stu-id="b009e-110">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="b009e-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="b009e-111">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b009e-112">포트 및 프로토콜 세부 정보</span><span class="sxs-lookup"><span data-stu-id="b009e-112">Port and Protocol Details</span></span>

<span data-ttu-id="b009e-113">외부 액세스를 제공할 기능을 지원하는 데 필요한 포트만 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="b009e-p103">원격 액세스가 에지 서비스에 작동하려면 SIP 트래픽이 인바운드/아웃바운드 에지 트래픽 그림에서처럼 양방향으로 전달될 수 있어야 합니다. 다른 방식으로 시작될 경우, 액세스 에지 서비스와 주고 받는 SIP 메시징에는 IM(인스턴트 메시징), 현재 상태, 웹 회의, A/V(오디오/비디오) 및 페더레이션이 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="b009e-116">확장 통합에 지에 대 한 방화벽 요약, NAT 사용 개인 IP 주소의 DNS 부하 분산 (예: 외부 인터페이스-노드 1 및 노드 2)</span><span class="sxs-lookup"><span data-stu-id="b009e-116">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b009e-117">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="b009e-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b009e-118">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-118">Source IP address</span></span></th>
<th><span data-ttu-id="b009e-119">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-119">Destination IP address</span></span></th>
<th><span data-ttu-id="b009e-120">참고</span><span class="sxs-lookup"><span data-stu-id="b009e-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b009e-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b009e-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b009e-122">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-122">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-123">XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="b009e-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b009e-124">정의된 XMPP 페더레이션의 XMPP 연락처로부터 들어오는 트래픽을 XMPP 프록시 서비스에서 허용</span><span class="sxs-lookup"><span data-stu-id="b009e-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-125">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b009e-125">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b009e-126">XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="b009e-126">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b009e-127">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-127">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-128">XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처로 트래픽을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-128">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-129">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b009e-129">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b009e-130">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-130">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-131">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-131">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-132">인증서 해지/CRL 검사 및 검색</span><span class="sxs-lookup"><span data-stu-id="b009e-132">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-133">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="b009e-133">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="b009e-134">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-134">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-135">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-135">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-136">TCP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="b009e-136">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-137">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="b009e-137">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="b009e-138">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-139">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-139">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-140">UDP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="b009e-140">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-141">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b009e-141">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b009e-142">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-142">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-143">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-143">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-144">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="b009e-144">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-145">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b009e-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b009e-146">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-146">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-147">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-147">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-148">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="b009e-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-149">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b009e-149">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b009e-150">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-150">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-151">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-151">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-152">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="b009e-152">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-153">Web 회의/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b009e-153">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b009e-154">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-154">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-155">에 지 서버 웹 회의에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-155">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-156">웹 회의 미디어</span><span class="sxs-lookup"><span data-stu-id="b009e-156">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-157">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b009e-157">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b009e-158">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-158">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-159">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-159">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-160">Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와의 페더레이션에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-160">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-161">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b009e-161">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b009e-162">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-163">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-163">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-164">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-165">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b009e-165">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b009e-166">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-166">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-167">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-167">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-168">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="b009e-168">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-169">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b009e-169">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b009e-170">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-170">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-171">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-171">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-172">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="b009e-172">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b009e-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b009e-174">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-174">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-175">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-175">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-176">3478 아웃 바운드는 Lync Server가 통신 중인에 지 서버 및에 지 서버-에 지 서버에서의 미디어 트래픽에 대 한 버전을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-176">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="b009e-177">Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와의 페더레이션, 그리고 여러 개의에 지 풀이 회사 내에 배포 된 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-177">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-178">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b009e-178">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b009e-179">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-179">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-180">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-180">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-181">UDP/3478을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="b009e-181">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b009e-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b009e-183">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-183">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-184">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-184">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-185">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="b009e-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-186">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b009e-186">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b009e-187">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-187">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-188">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-188">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-189">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="b009e-189">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="b009e-190">확장 통합에 지에 대 한 방화벽 요약, NAT 사용 개인 IP 주소의 DNS 부하 분산: 내부 인터페이스-노드 1 및 노드 2 (예제)</span><span class="sxs-lookup"><span data-stu-id="b009e-190">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b009e-191">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="b009e-191">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b009e-192">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-192">Source IP address</span></span></th>
<th><span data-ttu-id="b009e-193">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-193">Destination IP address</span></span></th>
<th><span data-ttu-id="b009e-194">설명</span><span class="sxs-lookup"><span data-stu-id="b009e-194">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b009e-195">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b009e-195">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b009e-196">Any (프런트 엔드 서버 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b009e-196">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="b009e-197">에 지 서버 내부 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-197">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b009e-198">프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="b009e-198">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b009e-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b009e-200">모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b009e-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b009e-201">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b009e-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b009e-202">아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)에서에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b009e-202">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-203">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b009e-203">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b009e-204">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b009e-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b009e-205">모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b009e-205">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b009e-206">에 지 서버 내부 인터페이스에서 디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소에 대 한 인바운드 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="b009e-206">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-207">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="b009e-207">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="b009e-208">Any (프런트 엔드 서버 IP 주소 또는 프런트 엔드 풀의 각 프런트 엔드 서버 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b009e-208">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="b009e-209">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b009e-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b009e-210">프런트 엔드 서버 또는 풀의 각 프런트 엔드 서버에서에 지 서버 내부 인터페이스로의 웹 회의 트래픽</span><span class="sxs-lookup"><span data-stu-id="b009e-210">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-211">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="b009e-211">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="b009e-212">Any (프런트 엔드 서버 IP 주소, 또는 프런트 엔드 풀 IP 주소 또는이에 지 서버를 사용 하는 Sba (survivable 분기 서버로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b009e-212">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="b009e-213">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b009e-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b009e-214">이에 지 서버를 사용 하 여 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소 또는 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에서 A/V 사용자 인증 (A/V 인증 서비스)</span><span class="sxs-lookup"><span data-stu-id="b009e-214">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-215">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b009e-215">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b009e-216">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-216">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-217">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b009e-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b009e-218">내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 설정 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="b009e-218">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-219">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b009e-219">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b009e-220">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-220">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-221">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b009e-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b009e-222">내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-222">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-223">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b009e-223">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b009e-224">Any (프런트 엔드 서버 IP 주소 또는 중앙 관리 저장소를 보유 하는 풀로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b009e-224">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="b009e-225">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b009e-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b009e-226">중앙 관리 저장소에서 에지 서버로 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="b009e-226">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-227">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b009e-227">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b009e-228">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-228">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-229">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b009e-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b009e-230">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="b009e-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-231">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b009e-231">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b009e-232">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-232">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-233">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b009e-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b009e-234">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="b009e-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-235">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b009e-235">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b009e-236">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-236">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-237">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b009e-237">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b009e-238">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="b009e-238">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="b009e-239">페더레이션에 대한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="b009e-239">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b009e-240">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="b009e-240">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b009e-241">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-241">Source IP address</span></span></th>
<th><span data-ttu-id="b009e-242">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-242">Destination IP address</span></span></th>
<th><span data-ttu-id="b009e-243">참고</span><span class="sxs-lookup"><span data-stu-id="b009e-243">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b009e-244">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b009e-244">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b009e-245">액세스 에지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-245">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b009e-246">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-246">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-247">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="b009e-247">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b009e-248">방화벽 요약 - 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="b009e-248">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b009e-249">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="b009e-249">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b009e-250">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-250">Source IP address</span></span></th>
<th><span data-ttu-id="b009e-251">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-251">Destination IP address</span></span></th>
<th><span data-ttu-id="b009e-252">참고</span><span class="sxs-lookup"><span data-stu-id="b009e-252">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b009e-253">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b009e-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b009e-254">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="b009e-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b009e-255">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-256">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="b009e-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-257">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b009e-257">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b009e-258">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-259">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="b009e-259">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b009e-260">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="b009e-260">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-261">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b009e-261">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b009e-262">클라이언트</span><span class="sxs-lookup"><span data-stu-id="b009e-262">Clients</span></span></p></td>
<td><p><span data-ttu-id="b009e-263">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-263">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-264">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="b009e-264">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-265">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b009e-265">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b009e-266">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-267">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="b009e-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b009e-268">공용 IM 연결이 구성된 경우 Windows Live Messenger와의 A/V 세션에 사용됨</span><span class="sxs-lookup"><span data-stu-id="b009e-268">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b009e-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b009e-270">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-271">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="b009e-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b009e-272">Windows Live Messenger와의 공용 IM 연결 시 필수</span><span class="sxs-lookup"><span data-stu-id="b009e-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-273">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b009e-273">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b009e-274">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="b009e-274">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b009e-275">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b009e-275">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b009e-276">Windows Live Messenger와의 공용 IM 연결 시 필수</span><span class="sxs-lookup"><span data-stu-id="b009e-276">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="b009e-277">확장 가능 메시징 및 현재 상태 프로토콜에 대한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="b009e-277">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b009e-278">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="b009e-278">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b009e-279">원본(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="b009e-279">Source (IP address)</span></span></th>
<th><span data-ttu-id="b009e-280">대상(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="b009e-280">Destination (IP address)</span></span></th>
<th><span data-ttu-id="b009e-281">설명</span><span class="sxs-lookup"><span data-stu-id="b009e-281">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b009e-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b009e-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b009e-283">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-283">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-284">에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b009e-285">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b009e-286">페더레이션 XMPP 파트너의에 지 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-286">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b009e-287">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b009e-287">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b009e-288">에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b009e-288">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b009e-289">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-289">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-290">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-290">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b009e-291">에 지 서버 XMPP 프록시에서 페더레이션 XMPP 파트너와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b009e-291">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b009e-292">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b009e-292">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b009e-293">모두</span><span class="sxs-lookup"><span data-stu-id="b009e-293">Any</span></span></p></td>
<td><p><span data-ttu-id="b009e-294">각 내부에 지 서버 인터페이스 IP</span><span class="sxs-lookup"><span data-stu-id="b009e-294">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="b009e-295">프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서에 지 서버 내부 IP 주소 또는 각에 지 풀 구성원의 내부 IP 주소로 내부 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="b009e-295">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

