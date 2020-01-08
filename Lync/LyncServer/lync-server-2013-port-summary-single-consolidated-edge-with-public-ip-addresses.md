---
title: 포트 요약 - 공용 IP 주소의 단일 통합 에지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Single consolidated edge with public IP addresses
ms:assetid: 28407acc-8b92-4f78-875c-fd6b4323b602
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204756(v=OCS.15)
ms:contentKeyID: 48183685
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c1a61341908bef3a3098e70b06816bbf5ea328b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975313"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---single-consolidated-edge-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="1ce61-102">Lync Server 2013의 포트 요약 - 공용 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="1ce61-102">Port summary - Single consolidated edge with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ce61-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="1ce61-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="1ce61-104">이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge 서버 기능은 Lync Server 2010에서 구현 된 것과 매우 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="1ce61-105">가장 주목할 만한 추가 기능은 XMPP (extensible messaging 및 현재 상태 프로토콜)에 대 한 포트 **5269 (TCP over** )입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="1ce61-106">Lync Server 2013는 Edge 서버 또는 Edge 풀의 XMPP 프록시와 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버를 선택적으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="1ce61-107">역방향 프록시 및 페더레이션에 대 한 계획 정보는 lync [server 2013의 리버스 프록시에 대 한 시나리오](lync-server-2013-scenarios-for-reverse-proxy.md) 에서 각각 [lync server 2013 섹션에서 SIP, xmpp 페더레이션 및 공용 인스턴트 메시지에 대 한 계획](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) 을 찾아 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-107">Planning information for the reverse proxy and federation are found in [Scenarios for reverse proxy in Lync Server 2013](lync-server-2013-scenarios-for-reverse-proxy.md) and [Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md) sections, respectively.</span></span>

<span data-ttu-id="1ce61-108">IPv4 외에도 Edge 서버는 이제 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="1ce61-109">명확 하 게 하기 위해 시나리오에 IPv4만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="1ce61-110">**공용 IP 주소 지정이 있는 단일 통합 edge의 엔터프라이즈 경계 네트워크**</span><span class="sxs-lookup"><span data-stu-id="1ce61-110">**Enterprise perimeter network for single consolidated edge with public IP addressing**</span></span>

<span data-ttu-id="1ce61-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span><span class="sxs-lookup"><span data-stu-id="1ce61-111">![f8c144c5-e5fb-498a-823e-eb39f26b6847](images/Gg425891.f8c144c5-e5fb-498a-823e-eb39f26b6847(OCS.15).jpg "f8c144c5-e5fb-498a-823e-eb39f26b6847")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="1ce61-112">포트 및 프로토콜 정보</span><span class="sxs-lookup"><span data-stu-id="1ce61-112">Port and Protocol Details</span></span>

<span data-ttu-id="1ce61-113">외부 액세스를 제공 하는 기능을 지 원하는 데 필요한 포트만을 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-113">We recommend that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="1ce61-114">모든 edge 서비스에 대 한 원격 액세스의 경우 인바운드/아웃 바운드에 지 트래픽 그림에 표시 된 대로 SIP 트래픽이 bidirectionally 흐름을 허용 하도록 하는 것이 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-114">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bidirectionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="1ce61-115">또 다른 방법으로, 액세스에 지 서비스에 대 한 SIP 메시징은 인스턴트 메시징 (IM), 현재 상태, 웹 회의, 오디오/비디오 (A/V) 및 페더레이션에 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-115">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-external-interface"></a><span data-ttu-id="1ce61-116">공용 IP 주소가 있는 통합 된 단일 Edge에 대 한 방화벽 요약: 외부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-116">Firewall Summary for Single Consolidated Edge with Public IP Addresses: External Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ce61-117">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="1ce61-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1ce61-118">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-118">Source IP address</span></span></th>
<th><span data-ttu-id="1ce61-119">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-119">Destination IP address</span></span></th>
<th><span data-ttu-id="1ce61-120">상속자</span><span class="sxs-lookup"><span data-stu-id="1ce61-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-121">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="1ce61-121">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="1ce61-122">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-122">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-123">XMPP 프록시 서비스 (액세스에 지 서비스가 있는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="1ce61-123">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="1ce61-124">XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처의 트래픽을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-124">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-125">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="1ce61-125">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="1ce61-126">Edge 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-127">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-127">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-128">인증서 해지/i p 확인 및 검색</span><span class="sxs-lookup"><span data-stu-id="1ce61-128">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-129">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="1ce61-129">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="1ce61-130">Edge 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-131">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-131">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-132">TCP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="1ce61-132">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-133">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="1ce61-133">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="1ce61-134">Edge 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-134">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-135">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-135">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-136">UDP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="1ce61-136">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-137">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1ce61-137">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1ce61-138">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-138">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-139">Edge 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-139">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-140">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="1ce61-140">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-141">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1ce61-141">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1ce61-142">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-142">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-143">Edge 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-143">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-144">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="1ce61-144">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-145">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1ce61-145">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1ce61-146">Edge 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-146">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-147">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-147">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-148">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="1ce61-148">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-149">웹 회의/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1ce61-149">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1ce61-150">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-150">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-151">Edge 서버 웹 회의에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-151">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-152">웹 회의 미디어</span><span class="sxs-lookup"><span data-stu-id="1ce61-152">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-153">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="1ce61-153">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1ce61-154">Edge 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-154">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-155">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-155">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-156">Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와 페더레이션 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-156">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-157">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="1ce61-157">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1ce61-158">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-158">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-159">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-159">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-160">Office Communications Server 2007을 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="1ce61-160">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-161">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="1ce61-161">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1ce61-162">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-162">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-163">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-164">Office Communications Server 2007을 실행 하는 파트너와 페더레이션 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-164">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-165">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="1ce61-165">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1ce61-166">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-166">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-167">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-167">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-168">Office Communications Server 2007을 실행 하는 파트너와 페더레이션 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-168">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-169">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1ce61-169">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1ce61-170">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-170">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-171">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-171">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-172">3478 아웃 바운드는 Lync Server와 통신 하는 Edge 서버의 버전과 Edge 서버 간 미디어 소통에 대 한 정보를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-172">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="1ce61-173">Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와 페더레이션 하는 데 필요 하며, 여러 Edge 풀이 회사 내에 배포 된 경우에도 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-173">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-174">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1ce61-174">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1ce61-175">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-175">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-176">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-176">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-177">STUN/UDP/3478에서 후보자의 협상을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-177">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-178">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1ce61-178">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1ce61-179">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-179">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-180">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-180">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-181">TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-181">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-182">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1ce61-182">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1ce61-183">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-183">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-184">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-184">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-185">TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-185">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-single-consolidated-edge-with-public-ip-addresses-internal-interface"></a><span data-ttu-id="1ce61-186">공용 IP 주소가 있는 통합 된 단일 Edge에 대 한 방화벽 요약: 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-186">Firewall Summary for Single Consolidated Edge with Public IP Addresses: Internal Interface</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ce61-187">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="1ce61-187">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1ce61-188">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-188">Source IP address</span></span></th>
<th><span data-ttu-id="1ce61-189">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-189">Destination IP address</span></span></th>
<th><span data-ttu-id="1ce61-190">메모</span><span class="sxs-lookup"><span data-stu-id="1ce61-190">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-191">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="1ce61-191">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="1ce61-192">Any (Standard Edition server IP, Standard Edition 서버 IP 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="1ce61-192">Any (can be defined as Standard Edition server IP, Standard Edition server IP address, or pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="1ce61-193">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1ce61-194">프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="1ce61-194">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-195">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1ce61-195">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1ce61-196">임의 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="1ce61-196">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="1ce61-197">Edge 서버 IP 또는 내부 인터페이스를 보유 하는 풀</span><span class="sxs-lookup"><span data-stu-id="1ce61-197">Edge Server IP, or pool that holds the internal interface</span></span></p></td>
<td><p><span data-ttu-id="1ce61-198">아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)에서 Edge Server 내부 인터페이스로</span><span class="sxs-lookup"><span data-stu-id="1ce61-198">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-199">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1ce61-199">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1ce61-200">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1ce61-201">임의 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="1ce61-201">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool address)</span></span></p></td>
<td><p><span data-ttu-id="1ce61-202">Edge Server 내부 인터페이스에서 인바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="1ce61-202">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-203">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="1ce61-203">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="1ce61-204">Any (프런트 엔드 서버 IP 주소 또는 프런트 엔드 풀의 각 프런트 엔드 서버 IP 주소를 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="1ce61-204">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="1ce61-205">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-205">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1ce61-206">프런트 엔드 서버 또는 풀의 각 프런트 엔드 서버에서 Edge Server 내부 인터페이스로의 웹 회의 트래픽</span><span class="sxs-lookup"><span data-stu-id="1ce61-206">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-207">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="1ce61-207">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="1ce61-208">Any (프런트 엔드 서버 IP 주소 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는이 Edge 서버를 사용 하는 Survivable Branch 서버를 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="1ce61-208">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="1ce61-209">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-209">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1ce61-210">이 Edge 서버를 사용 하 여 프론트 엔드 서버 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는 Survivable Branch 서버에서 A/V 사용자 (A/V 인증 서비스) 인증</span><span class="sxs-lookup"><span data-stu-id="1ce61-210">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-211">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1ce61-211">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1ce61-212">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-212">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-213">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-213">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1ce61-214">내부 및 외부 사용자 간 Survivable Branch 기기 또는 Survivable Branch 서버 간의 A/V 미디어 전송에 대 한 기본 설정 경로</span><span class="sxs-lookup"><span data-stu-id="1ce61-214">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-215">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1ce61-215">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1ce61-216">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-216">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-217">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-217">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1ce61-218">내부 및 외부 사용자 간 A/V 미디어 전송의 대체 경로, Survivable Branch 기기 또는 Survivable Branch 서버 UDP 통신을 설정할 수 없는 경우 TCP는 파일 전송 및 데스크톱 공유에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-218">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-219">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="1ce61-219">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="1ce61-220">Any (중앙 관리 저장소를 보유 하는 프런트 엔드 서버 IP 주소 또는 풀로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="1ce61-220">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="1ce61-221">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-221">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1ce61-222">중앙 관리 저장소의 변경 내용을 Edge 서버로 복제</span><span class="sxs-lookup"><span data-stu-id="1ce61-222">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-223">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="1ce61-223">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="1ce61-224">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-224">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-225">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-225">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1ce61-226">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="1ce61-226">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-227">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="1ce61-227">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="1ce61-228">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-228">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-229">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-229">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1ce61-230">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="1ce61-230">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-231">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="1ce61-231">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="1ce61-232">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-232">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-233">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1ce61-233">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="1ce61-234">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="1ce61-234">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="1ce61-235">페더레이션에 대 한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="1ce61-235">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ce61-236">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="1ce61-236">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1ce61-237">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-237">Source IP address</span></span></th>
<th><span data-ttu-id="1ce61-238">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-238">Destination IP address</span></span></th>
<th><span data-ttu-id="1ce61-239">상속자</span><span class="sxs-lookup"><span data-stu-id="1ce61-239">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-240">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1ce61-240">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1ce61-241">액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-241">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-242">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-242">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-243">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="1ce61-243">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="1ce61-244">방화벽 요약-공용 인스턴트 메시지 연결</span><span class="sxs-lookup"><span data-stu-id="1ce61-244">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ce61-245">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="1ce61-245">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1ce61-246">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-246">Source IP address</span></span></th>
<th><span data-ttu-id="1ce61-247">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-247">Destination IP address</span></span></th>
<th><span data-ttu-id="1ce61-248">상속자</span><span class="sxs-lookup"><span data-stu-id="1ce61-248">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-249">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1ce61-249">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1ce61-250">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="1ce61-250">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="1ce61-251">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="1ce61-251">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="1ce61-252">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="1ce61-252">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-253">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="1ce61-253">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="1ce61-254">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="1ce61-254">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="1ce61-255">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="1ce61-255">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="1ce61-256">SIP를 사용 하는 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="1ce61-256">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-257">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="1ce61-257">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="1ce61-258">클라이언트</span><span class="sxs-lookup"><span data-stu-id="1ce61-258">Clients</span></span></p></td>
<td><p><span data-ttu-id="1ce61-259">Edge 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="1ce61-259">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="1ce61-260">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="1ce61-260">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-261">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="1ce61-261">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="1ce61-262">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="1ce61-262">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="1ce61-263">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="1ce61-263">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="1ce61-264">공용 메신저 연결이 구성 되어 있는 경우 Windows Live Messenger를 사용 하 여 A/V 세션에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-264">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-265">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1ce61-265">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1ce61-266">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="1ce61-266">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="1ce61-267">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="1ce61-267">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="1ce61-268">Windows Live Messenger를 사용 하 여 공용 인스턴트 메시지 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-268">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-269">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="1ce61-269">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="1ce61-270">실시간 메신저 클라이언트</span><span class="sxs-lookup"><span data-stu-id="1ce61-270">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="1ce61-271">Edge 서버 A/V Edge 서비스</span><span class="sxs-lookup"><span data-stu-id="1ce61-271">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="1ce61-272">Windows Live Messenger를 사용 하 여 공용 인스턴트 메시지 연결에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-272">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="1ce61-273">확장 가능한 메시징 및 현재 상태 프로토콜에 대 한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="1ce61-273">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ce61-274">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="1ce61-274">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="1ce61-275">원본 (IP 주소)</span><span class="sxs-lookup"><span data-stu-id="1ce61-275">Source (IP address)</span></span></th>
<th><span data-ttu-id="1ce61-276">대상 (IP 주소)</span><span class="sxs-lookup"><span data-stu-id="1ce61-276">Destination (IP address)</span></span></th>
<th><span data-ttu-id="1ce61-277">메모</span><span class="sxs-lookup"><span data-stu-id="1ce61-277">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-278">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="1ce61-278">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="1ce61-279">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-279">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-280">Edge 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-280">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-281">XMPP 용 표준 서버 대 서버 통신 포트.</span><span class="sxs-lookup"><span data-stu-id="1ce61-281">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="1ce61-282">페더레이션된 XMPP 파트너의 Edge 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-282">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ce61-283">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="1ce61-283">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="1ce61-284">Edge 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="1ce61-284">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="1ce61-285">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-285">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-286">XMPP 용 표준 서버 대 서버 통신 포트.</span><span class="sxs-lookup"><span data-stu-id="1ce61-286">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="1ce61-287">Edge 서버 XMPP 프록시에서 페더레이션된 XMPP 파트너와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ce61-287">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ce61-288">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="1ce61-288">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="1ce61-289">이상</span><span class="sxs-lookup"><span data-stu-id="1ce61-289">Any</span></span></p></td>
<td><p><span data-ttu-id="1ce61-290">각 내부에 지 서버 인터페이스 IP</span><span class="sxs-lookup"><span data-stu-id="1ce61-290">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="1ce61-291">프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서 Edge Server 내부 IP 주소 또는 각 Edge 풀 구성원의 내부 IP 주소로의 내부 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="1ce61-291">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

