---
title: 포트 요약-공용 IP 주소의 단일 통합에 지
description: 포트 요약-공용 IP 주소의 단일 통합에 지입니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82ab2d89404fb174994d8e5b798f64bb68768326
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566404"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="b1be0-103">포트 요약-Lync Server 2013의 공용 IP 주소를 포함 하는 단일 통합에 지</span><span class="sxs-lookup"><span data-stu-id="b1be0-103">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b1be0-104">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b1be0-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b1be0-105">이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge Server 기능은 Lync Server 2010에서 구현 된 것과 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="b1be0-106">가장 큰 차이점은 XMPP(Extensible Messaging and Presence Protocol)에 대한 포트 **5269 over TCP** 항목이 추가되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="b1be0-107">Lync Server 2013는 선택적으로에 지 서버 또는에 지 풀 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버에 XMPP 프록시를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="b1be0-108">역방향 프록시와 페더레이션에 대 한 계획 정보는 lync server [2013의 역방향 프록시](lync-server-2013-scenarios-for-reverse-proxy.md) 에 대 한 시나리오와 [lync server 2013 섹션의 SIP, xmpp 페더레이션 및 공용 인스턴트 메시징](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) 에 대 한 계획에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-108">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="b1be0-109">이제에 지 서버는 IPv4 외에도 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-109">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="b1be0-110">명확한 이해를 위해 시나리오에서는 IPv4만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-110">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="b1be0-111">**공용 IP 주소 지정을 사용 하는 단일 통합에 지에 대 한 엔터프라이즈 경계 네트워크**</span><span class="sxs-lookup"><span data-stu-id="b1be0-111">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="b1be0-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="b1be0-112">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="b1be0-113">포트 및 프로토콜 세부 정보</span><span class="sxs-lookup"><span data-stu-id="b1be0-113">Port and Protocol Details</span></span>

<span data-ttu-id="b1be0-114">외부 액세스를 제공하는 기능을 지원하는 데 필요한 포트만 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-114">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="b1be0-p103">원격 액세스가 모든 에지 서비스에 대해 작동하도록 하려면 SIP 트래픽이 인바운드/아웃바운드 에지 트래픽 그림에 표시된 대로 양방향으로 이동할 수 있어야 합니다. 즉, 액세스 에지 서비스로의/서비스로부터의 SIP 메시징이 IM(인스턴트 메시징), 현재 상태, 웹 회의, A/V(오디오/비디오) 및 페더레이션에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="b1be0-117">공용 IP 주소를 포함하는 단일 통합 에지에 대한 방화벽 요약 정보: 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-117">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1be0-118">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="b1be0-118">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b1be0-119">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-119">Source IP address</span></span></th>
<th><span data-ttu-id="b1be0-120">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-120">Destination IP address</span></span></th>
<th><span data-ttu-id="b1be0-121">참고</span><span class="sxs-lookup"><span data-stu-id="b1be0-121">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-122">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b1be0-122">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b1be0-123">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-123">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-124">XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="b1be0-124">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="b1be0-125">정의된 XMPP 페더레이션의 XMPP 연락처로부터 들어오는 트래픽을 XMPP 프록시 서비스에서 허용</span><span class="sxs-lookup"><span data-stu-id="b1be0-125">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-126">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="b1be0-126">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="b1be0-127">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-127">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-128">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-128">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-129">인증서 해지/CRL 검사 및 검색</span><span class="sxs-lookup"><span data-stu-id="b1be0-129">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-130">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="b1be0-130">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="b1be0-131">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-131">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-132">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-132">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-133">TCP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="b1be0-133">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-134">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="b1be0-134">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="b1be0-135">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-135">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-136">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-136">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-137">UDP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="b1be0-137">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-138">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b1be0-138">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b1be0-139">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-139">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-140">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-140">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-141">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="b1be0-141">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-142">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b1be0-142">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b1be0-143">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-143">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-144">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-144">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-145">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="b1be0-145">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-146">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b1be0-146">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b1be0-147">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-147">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-148">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-148">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-149">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="b1be0-149">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-150">Web 회의/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b1be0-150">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b1be0-151">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-151">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-152">에 지 서버 웹 회의에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-152">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-153">웹 회의 미디어</span><span class="sxs-lookup"><span data-stu-id="b1be0-153">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-154">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b1be0-154">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b1be0-155">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-155">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-156">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-156">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-157">Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와의 페더레이션에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-157">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-158">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b1be0-158">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b1be0-159">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-160">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-160">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-161">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="b1be0-161">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-162">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b1be0-162">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b1be0-163">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-163">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-164">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-164">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-165">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-165">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-166">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b1be0-166">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b1be0-167">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-167">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-168">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-168">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-169">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-169">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-170">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b1be0-170">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b1be0-171">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-171">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-172">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-172">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-173">3478 아웃 바운드는 Lync Server가 통신 중인에 지 서버 및에 지 서버-에 지 서버에서의 미디어 트래픽에 대 한 버전을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-173">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="b1be0-174">Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와의 페더레이션, 그리고 여러 개의에 지 풀이 회사 내에 배포 된 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-174">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-175">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b1be0-175">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b1be0-176">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-176">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-177">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-177">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-178">UDP/3478을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="b1be0-178">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-179">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b1be0-179">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b1be0-180">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-180">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-181">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-181">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-182">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="b1be0-182">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-183">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b1be0-183">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b1be0-184">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-184">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-185">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-185">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-186">TCP/443을 통한 후보 STUN/TURN 협상</span><span class="sxs-lookup"><span data-stu-id="b1be0-186">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="b1be0-187">공용 IP 주소를 포함하는 단일 통합 에지에 대한 방화벽 요약 정보: 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-187">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1be0-188">Protocol/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="b1be0-188">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b1be0-189">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-189">Source IP address</span></span></th>
<th><span data-ttu-id="b1be0-190">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-190">Destination IP address</span></span></th>
<th><span data-ttu-id="b1be0-191">설명</span><span class="sxs-lookup"><span data-stu-id="b1be0-191">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-192">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b1be0-192">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b1be0-193">Any (Standard Edition server IP, Standard Edition server IP 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b1be0-193">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="b1be0-194">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-194">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b1be0-195">프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="b1be0-195">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-196">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b1be0-196">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b1be0-197">모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b1be0-197">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="b1be0-198">내부 인터페이스를 보유 하는에 지 서버 IP 또는 풀</span><span class="sxs-lookup"><span data-stu-id="b1be0-198">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="b1be0-199">아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)에서에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-199">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-200">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b1be0-200">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b1be0-201">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b1be0-202">모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b1be0-202">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="b1be0-203">에 지 서버 내부 인터페이스에서 디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소에 대 한 인바운드 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="b1be0-203">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-204">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="b1be0-204">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="b1be0-205">Any (프런트 엔드 서버 IP 주소 또는 프런트 엔드 풀의 각 프런트 엔드 서버 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b1be0-205">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="b1be0-206">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-206">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b1be0-207">프런트 엔드 서버 또는 풀의 각 프런트 엔드 서버에서에 지 서버 내부 인터페이스로의 웹 회의 트래픽</span><span class="sxs-lookup"><span data-stu-id="b1be0-207">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-208">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="b1be0-208">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="b1be0-209">Any (프런트 엔드 서버 IP 주소, 또는 프런트 엔드 풀 IP 주소 또는이에 지 서버를 사용 하는 Sba (survivable 분기 서버로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b1be0-209">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="b1be0-210">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-210">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b1be0-211">이에 지 서버를 사용 하 여 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소 또는 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에서 A/V 사용자 인증 (A/V 인증 서비스)</span><span class="sxs-lookup"><span data-stu-id="b1be0-211">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-212">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b1be0-212">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b1be0-213">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-213">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-214">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-214">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b1be0-215">내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 설정 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="b1be0-215">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-216">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b1be0-216">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b1be0-217">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-217">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-218">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-218">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b1be0-219">내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-219">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-220">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="b1be0-220">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="b1be0-221">Any (프런트 엔드 서버 IP 주소 또는 중앙 관리 저장소를 보유 하는 풀로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="b1be0-221">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="b1be0-222">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-222">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b1be0-223">중앙 관리 저장소에서 에지 서버로 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="b1be0-223">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-224">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="b1be0-224">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="b1be0-225">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-225">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-226">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-226">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b1be0-227">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="b1be0-227">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-228">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="b1be0-228">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="b1be0-229">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-229">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-230">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-230">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b1be0-231">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="b1be0-231">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-232">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="b1be0-232">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="b1be0-233">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-233">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-234">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1be0-234">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="b1be0-235">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="b1be0-235">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="b1be0-236">페더레이션에 대한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="b1be0-236">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1be0-237">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="b1be0-237">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b1be0-238">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-238">Source IP address</span></span></th>
<th><span data-ttu-id="b1be0-239">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-239">Destination IP address</span></span></th>
<th><span data-ttu-id="b1be0-240">참고</span><span class="sxs-lookup"><span data-stu-id="b1be0-240">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-241">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b1be0-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b1be0-242">액세스 에지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-242">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-243">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-243">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-244">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="b1be0-244">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="b1be0-245">방화벽 요약 - 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="b1be0-245">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1be0-246">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="b1be0-246">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b1be0-247">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-247">Source IP address</span></span></th>
<th><span data-ttu-id="b1be0-248">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-248">Destination IP address</span></span></th>
<th><span data-ttu-id="b1be0-249">참고</span><span class="sxs-lookup"><span data-stu-id="b1be0-249">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-250">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b1be0-250">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b1be0-251">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="b1be0-251">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b1be0-252">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b1be0-252">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b1be0-253">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="b1be0-253">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-254">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="b1be0-254">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="b1be0-255">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b1be0-255">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b1be0-256">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="b1be0-256">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="b1be0-257">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="b1be0-257">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-258">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="b1be0-258">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="b1be0-259">클라이언트</span><span class="sxs-lookup"><span data-stu-id="b1be0-259">Clients</span></span></p></td>
<td><p><span data-ttu-id="b1be0-260">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b1be0-260">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="b1be0-261">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="b1be0-261">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-262">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="b1be0-262">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="b1be0-263">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b1be0-263">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b1be0-264">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="b1be0-264">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b1be0-265">공용 IM 연결이 구성된 경우 Windows Live Messenger와의 A/V 세션에 사용됨</span><span class="sxs-lookup"><span data-stu-id="b1be0-265">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-266">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b1be0-266">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b1be0-267">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b1be0-267">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b1be0-268">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="b1be0-268">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b1be0-269">Windows Live Messenger와의 공용 IM 연결 시 필수</span><span class="sxs-lookup"><span data-stu-id="b1be0-269">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-270">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="b1be0-270">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="b1be0-271">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="b1be0-271">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="b1be0-272">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="b1be0-272">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="b1be0-273">Windows Live Messenger와의 공용 IM 연결 시 필수</span><span class="sxs-lookup"><span data-stu-id="b1be0-273">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="b1be0-274">확장 가능 메시징 및 현재 상태 프로토콜에 대한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="b1be0-274">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b1be0-275">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="b1be0-275">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="b1be0-276">원본(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="b1be0-276">Source (IP address)</span></span></th>
<th><span data-ttu-id="b1be0-277">대상(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="b1be0-277">Destination (IP address)</span></span></th>
<th><span data-ttu-id="b1be0-278">설명</span><span class="sxs-lookup"><span data-stu-id="b1be0-278">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-279">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b1be0-279">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b1be0-280">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-280">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-281">에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-281">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-282">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-282">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b1be0-283">페더레이션 XMPP 파트너의에 지 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-283">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b1be0-284">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="b1be0-284">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="b1be0-285">에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="b1be0-285">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="b1be0-286">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-286">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-287">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-287">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="b1be0-288">에 지 서버 XMPP 프록시에서 페더레이션 XMPP 파트너와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1be0-288">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b1be0-289">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="b1be0-289">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="b1be0-290">모두</span><span class="sxs-lookup"><span data-stu-id="b1be0-290">Any</span></span></p></td>
<td><p><span data-ttu-id="b1be0-291">각 내부에 지 서버 인터페이스 IP</span><span class="sxs-lookup"><span data-stu-id="b1be0-291">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="b1be0-292">프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서에 지 서버 내부 IP 주소 또는 각에 지 풀 구성원의 내부 IP 주소로 내부 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="b1be0-292">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

