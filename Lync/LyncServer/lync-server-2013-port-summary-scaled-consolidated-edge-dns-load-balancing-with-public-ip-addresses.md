---
title: 'Lync Server 2013: 포트 요약-조정 된 통합에 지, 공용 IP 주소의 DNS 부하 분산'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: f7cbd0f1-841d-4116-8d17-e9d991daa4a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205394(v=OCS.15)
ms:contentKeyID: 48185865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5318f418c2bbd0876999aedcb33b559c5572b20a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534125"
---
# <a name="port-summary---scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="59edd-102">포트 요약-조정 된 통합에 지, Lync Server 2013의 공용 IP 주소를 사용한 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="59edd-102">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59edd-103">_**마지막으로 수정 된 항목:** 2013-04-03_</span><span class="sxs-lookup"><span data-stu-id="59edd-103">_**Topic Last Modified:** 2013-04-03_</span></span>

<span data-ttu-id="59edd-104">이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge Server 기능은 Lync Server 2010에서 구현 된 것과 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="59edd-105">가장 큰 차이점은 XMPP(Extensible Messaging and Presence Protocol)에 대한 포트 **5269 over TCP** 항목이 추가되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="59edd-106">Lync Server 2013는 선택적으로에 지 서버 또는에 지 풀 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버에 XMPP 프록시를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="59edd-107">이제에 지 서버는 IPv4 외에도 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="59edd-108">명확한 이해를 위해 시나리오에서는 IPv4만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="59edd-109">**확장 통합에 지에 대 한 엔터프라이즈 경계 네트워크, 공용 IP 주소의 DNS 부하 분산**</span><span class="sxs-lookup"><span data-stu-id="59edd-109">**Enterprise perimeter network for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses**</span></span>

<span data-ttu-id="59edd-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span><span class="sxs-lookup"><span data-stu-id="59edd-110">![96f5a8f5-16d2-464d-b86e-7c7ecfc89ead](images/JJ205394.96f5a8f5-16d2-464d-b86e-7c7ecfc89ead(OCS.15).jpg "96f5a8f5-16d2-464d-b86e-7c7ecfc89ead")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="59edd-111">포트 및 프로토콜 세부 정보</span><span class="sxs-lookup"><span data-stu-id="59edd-111">Port and Protocol Details</span></span>

<span data-ttu-id="59edd-112">외부 액세스를 제공할 기능을 지원하는 데 필요한 포트만 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="59edd-p103">원격 액세스가 에지 서비스에 작동하려면 SIP 트래픽이 인바운드/아웃바운드 에지 트래픽 그림에서처럼 양방향으로 전달될 수 있어야 합니다. 다른 방식으로 시작될 경우, 액세스 에지 서비스와 주고 받는 SIP 메시징에는 IM(인스턴트 메시징), 현재 상태, 웹 회의, A/V(오디오/비디오) 및 페더레이션이 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="59edd-115">확장 된 통합에 지에 대 한 방화벽 요약, 공용 IP 주소를 사용한 DNS 부하 분산: 외부 인터페이스-노드 1 및 노드 2 (예제)</span><span class="sxs-lookup"><span data-stu-id="59edd-115">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59edd-116">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="59edd-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="59edd-117">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-117">Source IP address</span></span></th>
<th><span data-ttu-id="59edd-118">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-118">Destination IP address</span></span></th>
<th><span data-ttu-id="59edd-119">참고</span><span class="sxs-lookup"><span data-stu-id="59edd-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59edd-120">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="59edd-120">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="59edd-121">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-121">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-122">XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="59edd-122">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="59edd-123">정의된 XMPP 페더레이션의 XMPP 연락처로부터 들어오는 트래픽을 XMPP 프록시 서비스에서 허용</span><span class="sxs-lookup"><span data-stu-id="59edd-123">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-124">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="59edd-124">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="59edd-125">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-126">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-126">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-127">인증서 해지/CRL 검사 및 검색</span><span class="sxs-lookup"><span data-stu-id="59edd-127">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-128">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="59edd-128">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="59edd-129">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-130">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-130">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-131">TCP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="59edd-131">DNS query over TCP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-132">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="59edd-132">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="59edd-133">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-133">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-134">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-134">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-135">UDP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="59edd-135">DNS query over UDP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-136">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="59edd-136">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="59edd-137">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-137">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-138">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-138">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-139">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="59edd-139">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-140">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="59edd-140">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="59edd-141">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-141">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-142">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-142">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-143">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="59edd-143">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-144">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="59edd-144">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="59edd-145">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-145">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-146">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-146">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-147">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="59edd-147">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-148">웹 회의/PSOM(TLS)TCP/443</span><span class="sxs-lookup"><span data-stu-id="59edd-148">Web Conferencing/PSOM(TLS)TCP/443</span></span></p></td>
<td><p><span data-ttu-id="59edd-149">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-149">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-150">에 지 서버 웹 회의에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-150">Edge Server Web Conferencing Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-151">웹 회의 미디어</span><span class="sxs-lookup"><span data-stu-id="59edd-151">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-152">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="59edd-152">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="59edd-153">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-153">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-154">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-154">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-155">Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와의 페더레이션에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-155">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-156">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="59edd-156">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="59edd-157">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-157">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-158">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-158">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-159">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-159">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-160">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="59edd-160">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="59edd-161">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-161">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-162">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-163">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="59edd-163">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-164">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="59edd-164">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="59edd-165">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-165">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-166">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-166">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-167">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="59edd-167">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-168">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="59edd-168">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="59edd-169">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-169">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-170">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-170">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-171">3478 아웃 바운드는 Lync Server가 통신 중인에 지 서버 및에 지 서버-에 지 서버에서의 미디어 트래픽에 대 한 버전을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-171">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="59edd-172">Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와의 페더레이션, 그리고 여러 개의에 지 풀이 회사 내에 배포 된 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-172">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-173">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="59edd-173">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="59edd-174">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-174">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-175">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-175">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-176">UDP/3478을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="59edd-176">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-177">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="59edd-177">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="59edd-178">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-178">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-179">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-179">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-180">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="59edd-180">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-181">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="59edd-181">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="59edd-182">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="59edd-182">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="59edd-183">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-183">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-184">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="59edd-184">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-internal-interface--node-1-and-node-2-example"></a><span data-ttu-id="59edd-185">조정된 통합 에지에 대한 방화벽 요약, 공용 IP 주소를 사용한 DNS 부하 분산: 내부 인터페이스 - 노드 1과 노드 2(예제)</span><span class="sxs-lookup"><span data-stu-id="59edd-185">Firewall Summary for Scaled Consolidated Edge, DNS Load Balancing with Public IP Addresses: Internal Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59edd-186">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="59edd-186">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="59edd-187">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-187">Source IP address</span></span></th>
<th><span data-ttu-id="59edd-188">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-188">Destination IP address</span></span></th>
<th><span data-ttu-id="59edd-189">설명</span><span class="sxs-lookup"><span data-stu-id="59edd-189">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59edd-190">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="59edd-190">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="59edd-191">Any (프런트 엔드 서버 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="59edd-191">Any (can be defined as Front End Server address, or Front End pool IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="59edd-192">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="59edd-193">프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="59edd-193">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-194">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="59edd-194">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="59edd-195">모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="59edd-195">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="59edd-196">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="59edd-197">아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소)에서에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-197">Outbound SIP traffic (from Director, Director pool IP address, Front End Server or Front End pool IP address) to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-198">SIP/MTLS/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="59edd-198">SIP/MTLS/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="59edd-199">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-199">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="59edd-200">모두 (디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="59edd-200">Any (can be defined as Director, Director pool IP address, Front End Server or Front End pool IP address)</span></span></p></td>
<td><p><span data-ttu-id="59edd-201">에 지 서버 내부 인터페이스에서 디렉터, 디렉터 풀 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소에 대 한 인바운드 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="59edd-201">Inbound SIP traffic (to Director, Director pool IP address, Front End Server or Front End pool IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-202">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="59edd-202">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="59edd-203">Any (프런트 엔드 서버 IP 주소 또는 프런트 엔드 풀의 각 프런트 엔드 서버 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="59edd-203">Any (can be defined as Front End Server IP address, or each Front End Server IP address in a Front End pool)</span></span></p></td>
<td><p><span data-ttu-id="59edd-204">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-204">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="59edd-205">프런트 엔드 서버 또는 풀의 각 프런트 엔드 서버에서에 지 서버 내부 인터페이스로의 웹 회의 트래픽</span><span class="sxs-lookup"><span data-stu-id="59edd-205">Web conferencing traffic from Front End Server or each Front End Server if in a pool, to Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-206">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="59edd-206">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="59edd-207">Any (프런트 엔드 서버 IP 주소, 또는 프런트 엔드 풀 IP 주소 또는이에 지 서버를 사용 하는 Sba (survivable 분기 서버로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="59edd-207">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="59edd-208">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-208">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="59edd-209">이에 지 서버를 사용 하 여 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소 또는 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에서 A/V 사용자 인증 (A/V 인증 서비스)</span><span class="sxs-lookup"><span data-stu-id="59edd-209">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-210">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="59edd-210">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="59edd-211">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-211">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-212">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-212">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="59edd-213">내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 설정 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="59edd-213">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-214">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="59edd-214">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="59edd-215">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-215">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-216">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-216">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="59edd-217">내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-217">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-218">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="59edd-218">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="59edd-219">Any (프런트 엔드 서버 IP 주소 또는 중앙 관리 저장소를 보유 하는 풀로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="59edd-219">Any (can be defined as the Front End Server IP address, or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="59edd-220">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-220">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="59edd-221">중앙 관리 저장소에서 에지 서버로 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="59edd-221">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-222">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="59edd-222">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="59edd-223">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-223">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-224">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-224">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="59edd-225">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="59edd-225">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-226">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="59edd-226">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="59edd-227">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-227">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-228">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-228">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="59edd-229">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="59edd-229">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-230">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="59edd-230">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="59edd-231">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-231">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-232">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59edd-232">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="59edd-233">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="59edd-233">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-federation"></a><span data-ttu-id="59edd-234">페더레이션에 대한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="59edd-234">Firewall Summary for Federation</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59edd-235">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="59edd-235">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="59edd-236">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-236">Source IP address</span></span></th>
<th><span data-ttu-id="59edd-237">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-237">Destination IP address</span></span></th>
<th><span data-ttu-id="59edd-238">참고</span><span class="sxs-lookup"><span data-stu-id="59edd-238">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59edd-239">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="59edd-239">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="59edd-240">액세스 에지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-240">Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-241">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-241">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-242">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="59edd-242">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary--public-instant-messaging-connectivity"></a><span data-ttu-id="59edd-243">방화벽 요약 - 공용 인스턴트 메시징 연결</span><span class="sxs-lookup"><span data-stu-id="59edd-243">Firewall Summary – Public Instant Messaging Connectivity</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59edd-244">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="59edd-244">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="59edd-245">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-245">Source IP address</span></span></th>
<th><span data-ttu-id="59edd-246">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-246">Destination IP address</span></span></th>
<th><span data-ttu-id="59edd-247">참고</span><span class="sxs-lookup"><span data-stu-id="59edd-247">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59edd-248">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="59edd-248">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="59edd-249">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="59edd-249">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="59edd-250">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="59edd-250">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="59edd-251">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="59edd-251">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-252">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="59edd-252">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="59edd-253">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="59edd-253">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="59edd-254">공용 IM 연결 파트너</span><span class="sxs-lookup"><span data-stu-id="59edd-254">Public IM connectivity partners</span></span></p></td>
<td><p><span data-ttu-id="59edd-255">SIP를 사용한 페더레이션 및 공용 IM 연결용</span><span class="sxs-lookup"><span data-stu-id="59edd-255">For federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-256">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="59edd-256">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="59edd-257">클라이언트</span><span class="sxs-lookup"><span data-stu-id="59edd-257">Clients</span></span></p></td>
<td><p><span data-ttu-id="59edd-258">에 지 서버 액세스에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="59edd-258">Edge Server Access Edge service</span></span></p></td>
<td><p><span data-ttu-id="59edd-259">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="59edd-259">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-260">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="59edd-260">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="59edd-261">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="59edd-261">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="59edd-262">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="59edd-262">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="59edd-263">공용 IM 연결이 구성된 경우 Windows Live Messenger와의 A/V 세션에 사용됨</span><span class="sxs-lookup"><span data-stu-id="59edd-263">Used for A/V sessions with Windows Live Messenger if public IM connectivity is configured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-264">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="59edd-264">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="59edd-265">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="59edd-265">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="59edd-266">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="59edd-266">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="59edd-267">Windows Live Messenger와의 공용 IM 연결 시 필수</span><span class="sxs-lookup"><span data-stu-id="59edd-267">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-268">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="59edd-268">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="59edd-269">Live Messenger 클라이언트</span><span class="sxs-lookup"><span data-stu-id="59edd-269">Live Messenger clients</span></span></p></td>
<td><p><span data-ttu-id="59edd-270">에 지 서버 A/V에 지 서비스</span><span class="sxs-lookup"><span data-stu-id="59edd-270">Edge Server A/V Edge service</span></span></p></td>
<td><p><span data-ttu-id="59edd-271">Windows Live Messenger와의 공용 IM 연결 시 필수</span><span class="sxs-lookup"><span data-stu-id="59edd-271">Required for public IM connectivity with Windows Live Messenger</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="firewall-summary-for-extensible-messaging-and-presence-protocol"></a><span data-ttu-id="59edd-272">확장 가능 메시징 및 현재 상태 프로토콜에 대한 방화벽 요약</span><span class="sxs-lookup"><span data-stu-id="59edd-272">Firewall Summary for Extensible Messaging and Presence Protocol</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="59edd-273">프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="59edd-273">Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="59edd-274">원본(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="59edd-274">Source (IP address)</span></span></th>
<th><span data-ttu-id="59edd-275">대상(IP 주소)</span><span class="sxs-lookup"><span data-stu-id="59edd-275">Destination (IP address)</span></span></th>
<th><span data-ttu-id="59edd-276">설명</span><span class="sxs-lookup"><span data-stu-id="59edd-276">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="59edd-277">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="59edd-277">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="59edd-278">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-278">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-279">에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-279">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-280">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-280">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="59edd-281">페더레이션 XMPP 파트너의에 지 서버 XMPP 프록시에 대 한 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-281">Allows communication to the Edge Server XMPP proxy from federated XMPP partners</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="59edd-282">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="59edd-282">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="59edd-283">에 지 서버 액세스에 지 서비스 인터페이스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="59edd-283">Edge Server Access Edge service interface IP address</span></span></p></td>
<td><p><span data-ttu-id="59edd-284">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-284">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-285">XMPP용 표준 서버 간 통신 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-285">Standard server-to-server communication port for XMPP.</span></span> <span data-ttu-id="59edd-286">에 지 서버 XMPP 프록시에서 페더레이션 XMPP 파트너와의 통신을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59edd-286">Allows communication from the Edge Server XMPP proxy to federated XMPP partners</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="59edd-287">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="59edd-287">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="59edd-288">모두</span><span class="sxs-lookup"><span data-stu-id="59edd-288">Any</span></span></p></td>
<td><p><span data-ttu-id="59edd-289">각 내부에 지 서버 인터페이스 IP</span><span class="sxs-lookup"><span data-stu-id="59edd-289">Each internal Edge Server Interface IP</span></span></p></td>
<td><p><span data-ttu-id="59edd-290">프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이에서에 지 서버 내부 IP 주소 또는 각에 지 풀 구성원의 내부 IP 주소로 내부 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="59edd-290">Internal XMPP traffic from the XMPP Gateway on the Front End Server or Front End pool to the Edge Server internal IP address or each Edge pool member’s internal IP address</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

