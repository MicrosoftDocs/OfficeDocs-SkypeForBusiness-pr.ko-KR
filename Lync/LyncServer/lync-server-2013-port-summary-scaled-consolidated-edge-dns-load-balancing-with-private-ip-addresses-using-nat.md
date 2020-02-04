---
title: 'Lync Server 2013: 포트 요약 - 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산'
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
ms.openlocfilehash: 20071cba55551a42ea6406723bb1f9ed55853afa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="d1d80-102">Lync Server 2013의 포트 요약 - 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="d1d80-102">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1d80-103">_**마지막으로 수정한 주제:** 2012-12-04_</span><span class="sxs-lookup"><span data-stu-id="d1d80-103">_**Topic Last Modified:** 2012-12-04_</span></span>

<span data-ttu-id="d1d80-104">이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge 서버 기능은 Lync Server 2010에서 구현 된 것과 매우 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="d1d80-105">가장 주목할 만한 추가 기능은 XMPP (extensible messaging 및 현재 상태 프로토콜)에 대 한 포트 **5269 (TCP over** )입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="d1d80-106">Lync Server 2013는 Edge 서버 또는 Edge 풀의 XMPP 프록시와 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버를 선택적으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="d1d80-107">IPv4 외에도 Edge 서버는 이제 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="d1d80-108">명확 하 게 하기 위해 시나리오에 IPv4만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="d1d80-109">**NAT를 사용 하 여 개인 IP 주소에 맞게 크기가 조정 된 통합 된 가장자리의 엔터프라이즈 경계 네트워크**</span><span class="sxs-lookup"><span data-stu-id="d1d80-109">**Enterprise perimeter network for scaled consolidated edge with private IP addresses using NAT**</span></span>

<span data-ttu-id="d1d80-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="d1d80-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="d1d80-111">포트 및 프로토콜 정보</span><span class="sxs-lookup"><span data-stu-id="d1d80-111">Port and Protocol Details</span></span>

<span data-ttu-id="d1d80-112">외부 액세스를 제공 하는 기능을 지 원하는 데 필요한 포트만을 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="d1d80-113">모든 edge 서비스에 대 한 원격 액세스의 경우 인바운드/아웃 바운드에 지 트래픽 그림에 표시 된 대로 SIP 트래픽이 directionally으로 이동 하도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="d1d80-114">또 다른 방법으로, 액세스에 지 서비스에 대 한 SIP 메시징은 인스턴트 메시징 (IM), 현재 상태, 웹 회의, 오디오/비디오 (A/V) 및 페더레이션에 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="d1d80-115">NAT를 사용 하는 개인 IP 주소가 포함 된 DNS 로드 균형 조정 통합 Edge의 크기 조정에 대 한 방화벽 요약: 노드 1 및 노드 2 (예제)</span><span class="sxs-lookup"><span data-stu-id="d1d80-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1d80-116">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="d1d80-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d1d80-117">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-117">Source IP address</span></span></th>
<th><span data-ttu-id="d1d80-118">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-118">Destination IP address</span></span></th>
<th><span data-ttu-id="d1d80-119">상속자</span><span class="sxs-lookup"><span data-stu-id="d1d80-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d1d80-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d1d80-121">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-121">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-122">XMPP 프록시 서비스 (액세스에 지 서비스가 있는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="d1d80-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="d1d80-123">XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처의 트래픽을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-124">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d1d80-124">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d1d80-125">XMPP 프록시 서비스 (액세스에 지 서비스가 있는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="d1d80-125">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="d1d80-126">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-126">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-127">XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처로 트래픽을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-127">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-128">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="d1d80-128">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="d1d80-129">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-130">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-130">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-131">인증서 해지/i p 확인 및 검색</span><span class="sxs-lookup"><span data-stu-id="d1d80-131">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-132">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="d1d80-132">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="d1d80-133">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-134">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-134">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-135">TCP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="d1d80-135">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-136">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="d1d80-136">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="d1d80-137">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-137">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-138">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-138">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-139">UDP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="d1d80-139">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-140">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d1d80-140">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d1d80-141">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-141">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-142">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-143">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="d1d80-143">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-144">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d1d80-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d1d80-145">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-145">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-146">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-146">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-147">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="d1d80-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-148">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d1d80-148">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d1d80-149">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-149">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-150">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-150">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-151">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="d1d80-151">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-152">웹 회의/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d1d80-152">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d1d80-153">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-153">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-154">Edge 서버 웹 회의에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-154">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-155">웹 회의 미디어</span><span class="sxs-lookup"><span data-stu-id="d1d80-155">Web Conferencing media</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-156">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="d1d80-156">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d1d80-157">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-158">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-158">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-159">Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와 페더레이션 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-159">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-160">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="d1d80-160">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d1d80-161">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-161">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-162">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-162">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-163">Office Communications Server 2007을 실행 하는 파트너와 페더레이션 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-163">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-164">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="d1d80-164">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d1d80-165">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-165">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-166">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-167">Office Communications Server 2007을 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="d1d80-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-168">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="d1d80-168">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d1d80-169">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-169">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-170">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-170">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-171">Office Communications Server 2007을 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="d1d80-171">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-172">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d1d80-172">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d1d80-173">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-173">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-174">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-174">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-175">3478 아웃 바운드는 Lync Server와 통신 하는 Edge 서버의 버전과 Edge 서버 간 미디어 소통에 대 한 정보를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-175">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="d1d80-176">Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와 페더레이션 하는 데 필요 하며, 여러 Edge 풀이 회사 내에 배포 된 경우에도 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-176">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-177">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d1d80-177">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d1d80-178">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-178">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-179">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-180">STUN/UDP/3478에서 후보자의 협상을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-180">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d1d80-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d1d80-182">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-182">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-183">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-183">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-184">TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-185">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d1d80-185">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d1d80-186">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-186">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-187">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-187">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-188">TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-188">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="d1d80-189">NAT를 사용 하 여 개인 IP 주소가 있는 DNS 로드 균형 조정 통합 된 Edge의 크기 조정에 대 한 방화벽 요약: 내부 인터페이스-노드 1 및 노드 2 (예제)</span><span class="sxs-lookup"><span data-stu-id="d1d80-189">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Private IP Addresses Using NAT: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1d80-190">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="d1d80-190">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d1d80-191">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-191">Source IP address</span></span></th>
<th><span data-ttu-id="d1d80-192">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-192">Destination IP address</span></span></th>
<th><span data-ttu-id="d1d80-193">메모</span><span class="sxs-lookup"><span data-stu-id="d1d80-193">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-194">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="d1d80-194">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="d1d80-195">Any (프런트 엔드 서버 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d1d80-195">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="d1d80-196">Edge 서버 내부 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-196">Edge Server internal interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d1d80-197">프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="d1d80-197">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d1d80-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d1d80-199">임의 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d1d80-199">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="d1d80-200">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1d80-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d1d80-201">아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)에서 Edge Server 내부 인터페이스로</span><span class="sxs-lookup"><span data-stu-id="d1d80-201">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-202">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d1d80-202">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d1d80-203">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1d80-203">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d1d80-204">임의 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d1d80-204">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="d1d80-205">Edge Server 내부 인터페이스에서 인바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="d1d80-205">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-206">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="d1d80-206">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="d1d80-207">Any (프런트 엔드 서버 IP 주소 또는 프런트 엔드 풀의 각 프런트 엔드 서버 IP 주소를 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d1d80-207">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="d1d80-208">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1d80-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d1d80-209">프런트 엔드 서버 또는 풀의 각 프런트 엔드 서버에서 Edge Server 내부 인터페이스로의 웹 회의 트래픽</span><span class="sxs-lookup"><span data-stu-id="d1d80-209">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-210">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="d1d80-210">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="d1d80-211">Any (프런트 엔드 서버 IP 주소 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는이 Edge 서버를 사용 하는 Survivable Branch 서버를 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d1d80-211">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="d1d80-212">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1d80-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d1d80-213">이 Edge 서버를 사용 하 여 프론트 엔드 서버 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는 Survivable Branch 서버에서 A/V 사용자 (A/V 인증 서비스) 인증</span><span class="sxs-lookup"><span data-stu-id="d1d80-213">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-214">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d1d80-214">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d1d80-215">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-215">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-216">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1d80-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d1d80-217">내부 및 외부 사용자 간 Survivable Branch 기기 또는 Survivable Branch 서버 간의 A/V 미디어 전송에 대 한 기본 설정 경로</span><span class="sxs-lookup"><span data-stu-id="d1d80-217">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-218">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d1d80-218">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d1d80-219">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-219">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-220">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1d80-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d1d80-221">내부 및 외부 사용자 간 A/V 미디어 전송의 대체 경로, Survivable Branch 기기 또는 Survivable Branch 서버 UDP 통신을 설정할 수 없는 경우 TCP는 파일 전송 및 데스크톱 공유에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-221">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-222">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="d1d80-222">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="d1d80-223">Any (중앙 관리 저장소를 보유 하는 프런트 엔드 서버 IP 주소 또는 풀로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d1d80-223">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="d1d80-224">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1d80-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d1d80-225">중앙 관리 저장소의 변경 내용을 Edge 서버로 복제</span><span class="sxs-lookup"><span data-stu-id="d1d80-225">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-226">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="d1d80-226">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="d1d80-227">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-227">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-228">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1d80-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d1d80-229">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="d1d80-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-230">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="d1d80-230">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="d1d80-231">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-231">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-232">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1d80-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d1d80-233">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="d1d80-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-234">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="d1d80-234">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="d1d80-235">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-235">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-236">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d1d80-236">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="d1d80-237">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="d1d80-237">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="d1d80-238">페더레이션에 대 한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="d1d80-238">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1d80-239">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="d1d80-239">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d1d80-240">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-240">Source IP address</span></span></th>
<th><span data-ttu-id="d1d80-241">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-241">Destination IP address</span></span></th>
<th><span data-ttu-id="d1d80-242">상속자</span><span class="sxs-lookup"><span data-stu-id="d1d80-242">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-243">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d1d80-243">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d1d80-244">액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-244">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="d1d80-245">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-245">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-246">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="d1d80-246">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="d1d80-247">방화벽 요약-공용 인스턴트 메시지 연결</span><span class="sxs-lookup"><span data-stu-id="d1d80-247">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1d80-248">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="d1d80-248">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d1d80-249">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-249">Source IP address</span></span></th>
<th><span data-ttu-id="d1d80-250">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-250">Destination IP address</span></span></th>
<th><span data-ttu-id="d1d80-251">상속자</span><span class="sxs-lookup"><span data-stu-id="d1d80-251">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-252">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d1d80-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d1d80-253">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="d1d80-253">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d1d80-254">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-255">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="d1d80-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-256">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="d1d80-256">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="d1d80-257">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-257">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-258">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="d1d80-258">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="d1d80-259">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="d1d80-259">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-260">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="d1d80-260">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="d1d80-261">클라이언트</span><span class="sxs-lookup"><span data-stu-id="d1d80-261">Clients</span></span></p></td>
<td><p><span data-ttu-id="d1d80-262">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-262">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-263">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="d1d80-263">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-264">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="d1d80-264">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="d1d80-265">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-266">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d1d80-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d1d80-267">공용 메신저 연결이 구성 되어 있는 경우 Windows Live Messenger를 사용 하 여 A/V 세션에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-267">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d1d80-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d1d80-269">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-269">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-270">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d1d80-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d1d80-271">Windows Live Messenger를 사용 하 여 공용 인스턴트 메시지 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-272">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="d1d80-272">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="d1d80-273">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="d1d80-273">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="d1d80-274">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="d1d80-274">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="d1d80-275">Windows Live Messenger를 사용 하 여 공용 인스턴트 메시지 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-275">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="d1d80-276">확장 가능한 메시징 및 현재 상태 프로토콜에 대 한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="d1d80-276">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1d80-277">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="d1d80-277">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="d1d80-278">원본 (IP 주소)</span><span class="sxs-lookup"><span data-stu-id="d1d80-278">Source (IP address)</span></span></th>
<th><span data-ttu-id="d1d80-279">대상 (IP 주소)</span><span class="sxs-lookup"><span data-stu-id="d1d80-279">Destination (IP address)</span></span></th>
<th><span data-ttu-id="d1d80-280">메모</span><span class="sxs-lookup"><span data-stu-id="d1d80-280">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-281">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d1d80-281">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d1d80-282">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-282">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-283">Edge 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d1d80-284">XMPP 용 표준 서버 대 서버 통신 포트.</span><span class="sxs-lookup"><span data-stu-id="d1d80-284">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d1d80-285">페더레이션된 XMPP 파트너의 Edge 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-285">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1d80-286">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="d1d80-286">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="d1d80-287">Edge 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="d1d80-287">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="d1d80-288">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-288">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-289">XMPP 용 표준 서버 대 서버 통신 포트.</span><span class="sxs-lookup"><span data-stu-id="d1d80-289">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="d1d80-290">Edge 서버 XMPP 프록시에서 페더레이션된 XMPP 파트너와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d1d80-290">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1d80-291">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="d1d80-291">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="d1d80-292">이상</span><span class="sxs-lookup"><span data-stu-id="d1d80-292">Any</span></span></p></td>
<td><p><span data-ttu-id="d1d80-293">각 내부에 지 서버 인터페이스 IP</span><span class="sxs-lookup"><span data-stu-id="d1d80-293">Each internal Edge Server interface IP</span></span></p></td>
<td><p><span data-ttu-id="d1d80-294">프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서 Edge Server 내부 IP 주소 또는 각 Edge 풀 구성원의 내부 IP 주소로의 내부 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="d1d80-294">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

