---
title: 포트 요약-공용 IP 주소의 단일 통합에 지
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
ms.openlocfilehash: 6aa6c3e2ad475cb641a2df50c1dc0016a5ac2fd9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534015"
---
# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="8292a-102">포트 요약-Lync Server 2013의 공용 IP 주소를 포함 하는 단일 통합에 지</span><span class="sxs-lookup"><span data-stu-id="8292a-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8292a-103">_**마지막으로 수정 된 항목:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="8292a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="8292a-104">이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge Server 기능은 Lync Server 2010에서 구현 된 것과 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="8292a-105">가장 큰 차이점은 XMPP(Extensible Messaging and Presence Protocol)에 대한 포트 **5269 over TCP** 항목이 추가되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="8292a-106">Lync Server 2013는 선택적으로에 지 서버 또는에 지 풀 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버에 XMPP 프록시를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="8292a-107">역방향 프록시와 페더레이션에 대 한 계획 정보는 lync server [2013의 역방향 프록시](lync-server-2013-scenarios-for-reverse-proxy.md) 에 대 한 시나리오와 [lync server 2013 섹션의 SIP, xmpp 페더레이션 및 공용 인스턴트 메시징](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) 에 대 한 계획에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="8292a-108">이제에 지 서버는 IPv4 외에도 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="8292a-109">명확한 이해를 위해 시나리오에서는 IPv4만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="8292a-110">**공용 IP 주소 지정을 사용 하는 단일 통합에 지에 대 한 엔터프라이즈 경계 네트워크**</span><span class="sxs-lookup"><span data-stu-id="8292a-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="8292a-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="8292a-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="8292a-112">포트 및 프로토콜 세부 정보</span><span class="sxs-lookup"><span data-stu-id="8292a-112">Port and Protocol Details</span></span>

<span data-ttu-id="8292a-113">외부 액세스를 제공하는 기능을 지원하는 데 필요한 포트만 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="8292a-p103">원격 액세스가 모든 에지 서비스에 대해 작동하도록 하려면 SIP 트래픽이 인바운드/아웃바운드 에지 트래픽 그림에 표시된 대로 양방향으로 이동할 수 있어야 합니다. 즉, 액세스 에지 서비스로의/서비스로부터의 SIP 메시징이 IM(인스턴트 메시징), 현재 상태, 웹 회의, A/V(오디오/비디오) 및 페더레이션에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="8292a-116">공용 IP 주소를 포함하는 단일 통합 에지에 대한 방화벽 요약 정보: 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8292a-117">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="8292a-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8292a-118">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-118">Source IP address</span></span></th>
<th><span data-ttu-id="8292a-119">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-119">Destination IP address</span></span></th>
<th><span data-ttu-id="8292a-120">참고</span><span class="sxs-lookup"><span data-stu-id="8292a-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8292a-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8292a-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8292a-122">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-122">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-123">XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="8292a-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="8292a-124">정의된 XMPP 페더레이션의 XMPP 연락처로부터 들어오는 트래픽을 XMPP 프록시 서비스에서 허용</span><span class="sxs-lookup"><span data-stu-id="8292a-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="8292a-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="8292a-126">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-127">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-127">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-128">인증서 해지/CRL 검사 및 검색</span><span class="sxs-lookup"><span data-stu-id="8292a-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="8292a-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="8292a-130">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-131">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-131">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-132">TCP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="8292a-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="8292a-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="8292a-134">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-135">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-135">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-136">UDP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="8292a-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-137">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8292a-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8292a-138">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-138">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-139">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-140">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="8292a-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-141">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8292a-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8292a-142">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-142">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-143">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-144">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="8292a-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-145">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8292a-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8292a-146">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-147">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-147">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-148">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="8292a-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-149">Web 회의/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8292a-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8292a-150">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-150">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-151">에 지 서버 웹 회의에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-152">웹 회의 미디어</span><span class="sxs-lookup"><span data-stu-id="8292a-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-153">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="8292a-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8292a-154">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-155">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-155">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-156">Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와의 페더레이션에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-157">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="8292a-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8292a-158">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-159">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-159">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-160">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="8292a-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-161">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="8292a-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8292a-162">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-162">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-163">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-164">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-165">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="8292a-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8292a-166">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-166">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-167">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-168">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8292a-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8292a-170">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-171">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-171">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-172">3478 아웃 바운드는 Lync Server가 통신 중인에 지 서버 및에 지 서버-에 지 서버에서의 미디어 트래픽에 대 한 버전을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="8292a-173">Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와의 페더레이션, 그리고 여러 개의에 지 풀이 회사 내에 배포 된 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8292a-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8292a-175">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-175">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-176">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-177">UDP/3478을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="8292a-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8292a-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8292a-179">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-179">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-180">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-181">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="8292a-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8292a-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8292a-183">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-184">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-184">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-185">TCP/443을 통한 후보 STUN/TURN 협상</span><span class="sxs-lookup"><span data-stu-id="8292a-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="8292a-186">공용 IP 주소를 포함하는 단일 통합 에지에 대한 방화벽 요약 정보: 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8292a-187">Protocol/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="8292a-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8292a-188">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-188">Source IP address</span></span></th>
<th><span data-ttu-id="8292a-189">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-189">Destination IP address</span></span></th>
<th><span data-ttu-id="8292a-190">설명</span><span class="sxs-lookup"><span data-stu-id="8292a-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8292a-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="8292a-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="8292a-192">Any (Standard Edition server IP, Standard Edition server IP 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="8292a-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="8292a-193">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8292a-194">프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="8292a-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8292a-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8292a-196">모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="8292a-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="8292a-197">내부 인터페이스를 보유 하는에 지 서버 IP 또는 풀</span><span class="sxs-lookup"><span data-stu-id="8292a-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="8292a-198">아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)에서에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8292a-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8292a-200">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8292a-201">모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="8292a-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="8292a-202">에 지 서버 내부 인터페이스에서 디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소에 대 한 인바운드 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="8292a-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="8292a-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="8292a-204">Any (프런트 엔드 서버 IP 주소 또는 프런트 엔드 풀의 각 프런트 엔드 서버 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="8292a-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="8292a-205">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8292a-206">프런트 엔드 서버 또는 풀의 각 프런트 엔드 서버에서에 지 서버 내부 인터페이스로의 웹 회의 트래픽</span><span class="sxs-lookup"><span data-stu-id="8292a-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="8292a-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="8292a-208">Any (프런트 엔드 서버 IP 주소, 또는 프런트 엔드 풀 IP 주소 또는이에 지 서버를 사용 하는 Sba (survivable 분기 서버로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="8292a-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="8292a-209">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8292a-210">이에 지 서버를 사용 하 여 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소 또는 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에서 A/V 사용자 인증 (A/V 인증 서비스)</span><span class="sxs-lookup"><span data-stu-id="8292a-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8292a-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8292a-212">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-212">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-213">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8292a-214">내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 설정 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="8292a-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8292a-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8292a-216">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-216">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-217">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8292a-218">내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="8292a-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="8292a-220">Any (프런트 엔드 서버 IP 주소 또는 중앙 관리 저장소를 보유 하는 풀로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="8292a-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="8292a-221">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8292a-222">중앙 관리 저장소에서 에지 서버로 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="8292a-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="8292a-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="8292a-224">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-224">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-225">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8292a-226">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="8292a-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="8292a-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="8292a-228">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-228">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-229">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8292a-230">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="8292a-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="8292a-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="8292a-232">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-232">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-233">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8292a-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="8292a-234">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="8292a-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="8292a-235">페더레이션에 대한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="8292a-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8292a-236">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="8292a-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8292a-237">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-237">Source IP address</span></span></th>
<th><span data-ttu-id="8292a-238">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-238">Destination IP address</span></span></th>
<th><span data-ttu-id="8292a-239">참고</span><span class="sxs-lookup"><span data-stu-id="8292a-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8292a-240">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8292a-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8292a-241">액세스 에지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-242">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-242">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-243">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="8292a-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="8292a-244">방화벽 요약 - 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="8292a-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8292a-245">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="8292a-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8292a-246">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-246">Source IP address</span></span></th>
<th><span data-ttu-id="8292a-247">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-247">Destination IP address</span></span></th>
<th><span data-ttu-id="8292a-248">참고</span><span class="sxs-lookup"><span data-stu-id="8292a-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8292a-249">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8292a-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8292a-250">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="8292a-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8292a-251">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="8292a-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8292a-252">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="8292a-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-253">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="8292a-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="8292a-254">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="8292a-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8292a-255">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="8292a-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="8292a-256">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="8292a-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-257">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="8292a-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="8292a-258">클라이언트</span><span class="sxs-lookup"><span data-stu-id="8292a-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="8292a-259">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="8292a-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="8292a-260">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="8292a-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-261">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="8292a-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="8292a-262">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="8292a-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8292a-263">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="8292a-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8292a-264">공용 IM 연결이 구성된 경우 Windows Live Messenger와의 A/V 세션에 사용됨</span><span class="sxs-lookup"><span data-stu-id="8292a-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8292a-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8292a-266">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="8292a-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8292a-267">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="8292a-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8292a-268">Windows Live Messenger와의 공용 IM 연결 시 필수</span><span class="sxs-lookup"><span data-stu-id="8292a-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="8292a-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="8292a-270">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="8292a-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="8292a-271">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="8292a-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="8292a-272">Windows Live Messenger와의 공용 IM 연결 시 필수</span><span class="sxs-lookup"><span data-stu-id="8292a-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="8292a-273">확장 가능 메시징 및 현재 상태 프로토콜에 대한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="8292a-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8292a-274">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="8292a-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="8292a-275">원본(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="8292a-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="8292a-276">대상(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="8292a-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="8292a-277">설명</span><span class="sxs-lookup"><span data-stu-id="8292a-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8292a-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8292a-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8292a-279">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-279">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-280">에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-281">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="8292a-282">페더레이션 XMPP 파트너의에 지 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8292a-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="8292a-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="8292a-284">에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="8292a-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="8292a-285">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-285">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-286">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="8292a-287">에 지 서버 XMPP 프록시에서 페더레이션 XMPP 파트너와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8292a-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8292a-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="8292a-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="8292a-289">모두</span><span class="sxs-lookup"><span data-stu-id="8292a-289">Any</span></span></p></td>
<td><p><span data-ttu-id="8292a-290">각 내부에 지 서버 인터페이스 IP</span><span class="sxs-lookup"><span data-stu-id="8292a-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="8292a-291">프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서에 지 서버 내부 IP 주소 또는 각에 지 풀 구성원의 내부 IP 주소로 내부 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="8292a-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

