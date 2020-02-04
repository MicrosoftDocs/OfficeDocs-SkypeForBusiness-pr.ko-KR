---
title: 포트 요약 - NAT 사용 개인 IP 주소의 단일 통합 에지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 3c1a389f-5f42-4719-a05b-e0b84aa3eb9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425891(v=OCS.15)
ms:contentKeyID: 48183877
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a425a07bf5ff615fb4766d50f21c6467512d110e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="97ce4-102">Lync Server 2013의 포트 요약 - NAT 사용 개인 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="97ce4-102">Port summary - Single consolidated edge with private IP addresses using NAT in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97ce4-103">_**마지막으로 수정한 주제:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="97ce4-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="97ce4-104">이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge 서버 기능은 Lync Server 2010에서 구현 된 것과 매우 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="97ce4-105">가장 주목할 만한 추가 기능은 XMPP (extensible messaging 및 현재 상태 프로토콜)에 대 한 포트 **5269 (TCP over** )입니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="97ce4-106">Lync Server 2013는 Edge 서버 또는 Edge 풀의 XMPP 프록시와 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버를 선택적으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="97ce4-107">IPv4 외에도 Edge 서버는 이제 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="97ce4-108">명확 하 게 하기 위해 시나리오에 IPv4만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="97ce4-109">**NAT를 사용 하 여 개인 IP 주소를 가진 단일 통합 된 Edge 서버의 네트워크 경계**</span><span class="sxs-lookup"><span data-stu-id="97ce4-109">**Network Perimeter for a Single Consolidated Edge Server with Private IP Addressing Using NAT**</span></span>

<span data-ttu-id="97ce4-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="97ce4-110">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="97ce4-111">포트 및 프로토콜 정보</span><span class="sxs-lookup"><span data-stu-id="97ce4-111">Port and Protocol Details</span></span>

<span data-ttu-id="97ce4-112">외부 액세스를 제공 하는 기능을 지 원하는 데 필요한 포트만을 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-112">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="97ce4-113">모든 edge 서비스에 대 한 원격 액세스의 경우 인바운드/아웃 바운드에 지 트래픽 그림에 표시 된 대로 SIP 트래픽이 directionally으로 이동 하도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="97ce4-114">또 다른 방법으로, 액세스에 지 서비스에 대 한 SIP 메시징은 인스턴트 메시징 (IM), 현재 상태, 웹 회의, 오디오/비디오 (A/V), 페더레이션에 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V), and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-external-interface"></a><span data-ttu-id="97ce4-115">NAT를 사용 하 여 개인 IP 주소가 있는 단일 통합 된 가장자리에 대 한 방화벽 요약: 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-115">Firewall Summary for Single Consolidated Edge with Private IP Addresses using NAT: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97ce4-116">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="97ce4-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="97ce4-117">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="97ce4-117">Source IP address</span></span></th>
<th><span data-ttu-id="97ce4-118">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="97ce4-118">Destination IP address</span></span></th>
<th><span data-ttu-id="97ce4-119">상속자</span><span class="sxs-lookup"><span data-stu-id="97ce4-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="97ce4-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="97ce4-121">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-121">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-122">XMPP 프록시 서비스 (액세스에 지 서비스가 있는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="97ce4-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="97ce4-123">XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처의 트래픽을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="97ce4-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="97ce4-125">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-125">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-126">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-126">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-127">인증서 해지/i p 확인 및 검색</span><span class="sxs-lookup"><span data-stu-id="97ce4-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="97ce4-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="97ce4-129">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-129">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-130">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-130">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-131">TCP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="97ce4-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="97ce4-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="97ce4-133">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-133">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-134">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-134">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-135">UDP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="97ce4-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-136">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="97ce4-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="97ce4-137">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-137">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-138">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-138">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-139">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="97ce4-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-140">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="97ce4-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="97ce4-141">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-141">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-142">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-142">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-143">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="97ce4-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-144">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="97ce4-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="97ce4-145">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-145">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-146">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-146">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-147">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="97ce4-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-148">웹 회의/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="97ce4-148">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="97ce4-149">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-149">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-150">Edge 서버 웹 회의에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-150">Edge Server Web Conferencing Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-151">웹 회의 미디어</span><span class="sxs-lookup"><span data-stu-id="97ce4-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="97ce4-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="97ce4-153">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-153">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-154">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-154">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-155">Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와 페더레이션 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="97ce4-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="97ce4-157">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-157">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-158">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-158">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-159">Office Communications Server 2007을 실행 하는 파트너와 페더레이션 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="97ce4-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="97ce4-161">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-161">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-162">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-162">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-163">Office Communications Server 2007을 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="97ce4-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="97ce4-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="97ce4-165">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-165">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-166">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-166">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-167">Office Communications Server 2007을 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="97ce4-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="97ce4-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="97ce4-169">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-169">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-170">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-170">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-171">3478 아웃 바운드는 Lync Server와 통신 하는 Edge 서버의 버전과 Edge 서버 간 미디어 소통에 대 한 정보를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="97ce4-172">Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와 페더레이션 하는 데 필요 하며, 여러 Edge 풀이 회사 내에 배포 된 경우에도 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="97ce4-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="97ce4-174">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-174">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-175">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-175">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-176">STUN/UDP/3478에서 후보자의 협상을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="97ce4-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="97ce4-178">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-178">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-179">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-179">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-180">TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="97ce4-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="97ce4-182">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-183">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-183">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-184">TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-private-ip-addresses-using-nat-internal-interface"></a><span data-ttu-id="97ce4-185">NAT를 사용 하 여 개인 IP 주소가 있는 단일 통합 된 가장자리에 대 한 방화벽 요약: 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-185">Firewall Summary for Single Consolidated Edge with Private IP Addresses Using NAT: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97ce4-186">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="97ce4-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="97ce4-187">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="97ce4-187">Source IP address</span></span></th>
<th><span data-ttu-id="97ce4-188">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="97ce4-188">Destination IP address</span></span></th>
<th><span data-ttu-id="97ce4-189">메모</span><span class="sxs-lookup"><span data-stu-id="97ce4-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="97ce4-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="97ce4-191">Any (Standard Edition server IP, Standard Edition 서버 IP 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="97ce4-191">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="97ce4-192">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="97ce4-193">프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="97ce4-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="97ce4-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="97ce4-195">임의 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="97ce4-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="97ce4-196">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="97ce4-197">아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)에서 Edge Server 내부 인터페이스로</span><span class="sxs-lookup"><span data-stu-id="97ce4-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="97ce4-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="97ce4-199">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="97ce4-200">임의 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="97ce4-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="97ce4-201">Edge Server 내부 인터페이스에서 인바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="97ce4-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="97ce4-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="97ce4-203">Any (프런트 엔드 서버 IP 주소 또는 프런트 엔드 풀의 각 프런트 엔드 서버 IP 주소를 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="97ce4-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="97ce4-204">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="97ce4-205">프런트 엔드 서버 또는 풀의 각 프런트 엔드 서버에서 Edge Server 내부 인터페이스로의 웹 회의 트래픽</span><span class="sxs-lookup"><span data-stu-id="97ce4-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="97ce4-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="97ce4-207">Any (프런트 엔드 서버 IP 주소 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는이 Edge 서버를 사용 하는 Survivable Branch 서버를 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="97ce4-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="97ce4-208">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="97ce4-209">이 Edge 서버를 사용 하 여 프론트 엔드 서버 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는 Survivable Branch 서버에서 A/V 사용자 (A/V 인증 서비스) 인증</span><span class="sxs-lookup"><span data-stu-id="97ce4-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="97ce4-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="97ce4-211">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-211">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-212">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="97ce4-213">내부 및 외부 사용자 간 Survivable Branch 기기 또는 Survivable Branch 서버 간의 A/V 미디어 전송에 대 한 기본 설정 경로</span><span class="sxs-lookup"><span data-stu-id="97ce4-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="97ce4-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="97ce4-215">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-215">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-216">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="97ce4-217">내부 및 외부 사용자 간 A/V 미디어 전송의 대체 경로, Survivable Branch 기기 또는 Survivable Branch 서버 UDP 통신을 설정할 수 없는 경우 TCP는 파일 전송 및 데스크톱 공유에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="97ce4-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="97ce4-219">Any (중앙 관리 저장소를 보유 하는 프런트 엔드 서버 IP 주소 또는 풀로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="97ce4-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="97ce4-220">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="97ce4-221">중앙 관리 저장소의 변경 내용을 Edge 서버로 복제</span><span class="sxs-lookup"><span data-stu-id="97ce4-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="97ce4-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="97ce4-223">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-223">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-224">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="97ce4-225">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="97ce4-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="97ce4-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="97ce4-227">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-227">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-228">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="97ce4-229">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="97ce4-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="97ce4-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="97ce4-231">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-231">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-232">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="97ce4-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="97ce4-233">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="97ce4-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="97ce4-234">페더레이션에 대 한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="97ce4-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97ce4-235">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="97ce4-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="97ce4-236">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="97ce4-236">Source IP address</span></span></th>
<th><span data-ttu-id="97ce4-237">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="97ce4-237">Destination IP address</span></span></th>
<th><span data-ttu-id="97ce4-238">상속자</span><span class="sxs-lookup"><span data-stu-id="97ce4-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-239">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="97ce4-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="97ce4-240">액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="97ce4-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="97ce4-241">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-241">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-242">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="97ce4-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="97ce4-243">방화벽 요약-공용 인스턴트 메시지 연결</span><span class="sxs-lookup"><span data-stu-id="97ce4-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97ce4-244">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="97ce4-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="97ce4-245">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="97ce4-245">Source IP address</span></span></th>
<th><span data-ttu-id="97ce4-246">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="97ce4-246">Destination IP address</span></span></th>
<th><span data-ttu-id="97ce4-247">상속자</span><span class="sxs-lookup"><span data-stu-id="97ce4-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-248">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="97ce4-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="97ce4-249">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="97ce4-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="97ce4-250">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-251">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="97ce4-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-252">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="97ce4-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="97ce4-253">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-254">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="97ce4-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="97ce4-255">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="97ce4-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-256">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="97ce4-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="97ce4-257">클라이언트</span><span class="sxs-lookup"><span data-stu-id="97ce4-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="97ce4-258">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-259">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="97ce4-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="97ce4-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="97ce4-261">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-262">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="97ce4-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="97ce4-263">공용 메신저 연결이 구성 되어 있는 경우 Windows Live Messenger를 사용 하 여 A/V 세션에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="97ce4-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="97ce4-265">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-266">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="97ce4-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="97ce4-267">Windows Live Messenger를 사용 하 여 공용 인스턴트 메시지 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="97ce4-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="97ce4-269">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="97ce4-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="97ce4-270">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="97ce4-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="97ce4-271">Windows Live Messenger를 사용 하 여 공용 인스턴트 메시지 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="97ce4-272">확장 가능한 메시징 및 현재 상태 프로토콜에 대 한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="97ce4-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97ce4-273">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="97ce4-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="97ce4-274">원본 (IP 주소)</span><span class="sxs-lookup"><span data-stu-id="97ce4-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="97ce4-275">대상 (IP 주소)</span><span class="sxs-lookup"><span data-stu-id="97ce4-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="97ce4-276">메모</span><span class="sxs-lookup"><span data-stu-id="97ce4-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="97ce4-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="97ce4-278">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-278">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-279">Edge 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="97ce4-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="97ce4-280">XMPP 용 표준 서버 대 서버 통신 포트.</span><span class="sxs-lookup"><span data-stu-id="97ce4-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="97ce4-281">페더레이션된 XMPP 파트너의 Edge 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97ce4-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="97ce4-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="97ce4-283">Edge 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="97ce4-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="97ce4-284">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-284">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-285">XMPP 용 표준 서버 대 서버 통신 포트.</span><span class="sxs-lookup"><span data-stu-id="97ce4-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="97ce4-286">Edge 서버 XMPP 프록시에서 페더레이션된 XMPP 파트너와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ce4-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97ce4-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="97ce4-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="97ce4-288">이상</span><span class="sxs-lookup"><span data-stu-id="97ce4-288">Any</span></span></p></td>
<td><p><span data-ttu-id="97ce4-289">각 내부에 지 서버 인터페이스 IP</span><span class="sxs-lookup"><span data-stu-id="97ce4-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="97ce4-290">프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서 Edge Server 내부 IP 주소 또는 각 Edge 풀 구성원의 내부 IP 주소로의 내부 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="97ce4-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

