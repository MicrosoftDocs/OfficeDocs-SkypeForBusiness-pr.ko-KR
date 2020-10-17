---
title: 포트 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지
description: 포트 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a03acb3644d83669bcf0065ebb20c526ef5fa32
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564594"
---
# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="46d6d-103">포트 요약-Lync Server 2013의 하드웨어 부하 분산 장치로 확장 된 통합에 지</span><span class="sxs-lookup"><span data-stu-id="46d6d-103">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46d6d-104">_**마지막으로 수정 된 항목:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="46d6d-104">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="46d6d-105">이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge Server 기능은 Lync Server 2010에서 구현 된 것과 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-105">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="46d6d-106">가장 큰 차이점은 XMPP(Extensible Messaging and Presence Protocol)에 대한 포트 **5269 over TCP** 항목이 추가되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-106">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="46d6d-107">Lync Server 2013는 선택적으로에 지 서버 또는에 지 풀 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버에 XMPP 프록시를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-107">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="46d6d-108">이제에 지 서버는 IPv4 외에도 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-108">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="46d6d-109">명확한 이해를 위해 시나리오에서는 IPv4만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-109">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="46d6d-110">**하드웨어 부하 분산을 사용 하 여 확장 된 통합에 지**</span><span class="sxs-lookup"><span data-stu-id="46d6d-110">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="46d6d-111">![에 지 서버 경계 네트워크 포트 및 프로토콜](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "에 지 서버 경계 네트워크 포트 및 프로토콜")</span><span class="sxs-lookup"><span data-stu-id="46d6d-111">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="46d6d-112">포트 및 프로토콜 세부 정보</span><span class="sxs-lookup"><span data-stu-id="46d6d-112">Port and Protocol Details</span></span>

<span data-ttu-id="46d6d-113">외부 액세스를 제공할 기능을 지원하는 데 필요한 포트만 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-113">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="46d6d-p103">원격 액세스가 에지 서비스에 작동하려면 SIP 트래픽이 인바운드/아웃바운드 에지 트래픽 그림에서처럼 양방향으로 전달될 수 있어야 합니다. 다른 방식으로 시작될 경우, 액세스 에지 서비스와 주고 받는 SIP 메시징에는 IM(인스턴트 메시징), 현재 상태, 웹 회의, A/V(오디오/비디오) 및 페더레이션이 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="46d6d-116">확장 통합에 지에 대 한 방화벽 요약, 하드웨어 부하 분산: 외부 인터페이스-노드 1 및 노드 2 (예제)</span><span class="sxs-lookup"><span data-stu-id="46d6d-116">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46d6d-117">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="46d6d-117">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="46d6d-118">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-118">Source IP address</span></span></th>
<th><span data-ttu-id="46d6d-119">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-119">Destination IP address</span></span></th>
<th><span data-ttu-id="46d6d-120">참고</span><span class="sxs-lookup"><span data-stu-id="46d6d-120">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-121">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="46d6d-121">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="46d6d-122">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-122">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-123">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-123">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-124">인증서 해지/CRL 검사 및 검색</span><span class="sxs-lookup"><span data-stu-id="46d6d-124">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-125">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="46d6d-125">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="46d6d-126">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-126">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-127">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-127">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-128">TCP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="46d6d-128">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-129">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="46d6d-129">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="46d6d-130">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-130">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-131">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-131">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-132">UDP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="46d6d-132">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-133">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="46d6d-133">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="46d6d-134">에 지 서버 A/V에 지 서비스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-134">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-135">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-135">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-136">Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와의 페더레이션에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-136">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-137">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="46d6d-137">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="46d6d-138">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-138">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-139">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-139">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-140">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-140">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-141">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="46d6d-141">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="46d6d-142">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-142">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-143">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-143">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-144">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="46d6d-144">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-145">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="46d6d-145">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="46d6d-146">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-146">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-147">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-147">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-148">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="46d6d-148">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-149">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46d6d-149">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46d6d-150">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-150">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-151">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-151">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-152">3478 아웃 바운드는 Lync Server가 통신 중인에 지 서버 및에 지 서버-에 지 서버에서의 미디어 트래픽에 대 한 버전을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-152">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="46d6d-153">Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와의 페더레이션, 그리고 여러 개의에 지 풀이 회사 내에 배포 된 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-153">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-154">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46d6d-154">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46d6d-155">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-155">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-156">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-156">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-157">UDP/3478을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="46d6d-157">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-158">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46d6d-158">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46d6d-159">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-159">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-160">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-160">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-161">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="46d6d-161">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-162">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46d6d-162">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46d6d-163">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-163">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-164">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-164">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-165">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="46d6d-165">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="46d6d-166">확장 통합에 지에 대 한 방화벽 요약, 하드웨어 부하 분산: 내부 인터페이스 노드 1 및 노드 2</span><span class="sxs-lookup"><span data-stu-id="46d6d-166">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46d6d-167">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="46d6d-167">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="46d6d-168">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-168">Source IP address</span></span></th>
<th><span data-ttu-id="46d6d-169">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-169">Destination IP address</span></span></th>
<th><span data-ttu-id="46d6d-170">참고</span><span class="sxs-lookup"><span data-stu-id="46d6d-170">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-171">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="46d6d-171">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="46d6d-172">Any (프런트 엔드 서버 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="46d6d-172">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="46d6d-173">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-173">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-174">프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="46d6d-174">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-175">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="46d6d-175">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="46d6d-176">Any (중앙 관리 저장소를 포함 하는 프런트 엔드 서버 서버 IP 또는 풀로 정의 가능)</span><span class="sxs-lookup"><span data-stu-id="46d6d-176">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="46d6d-177">에지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-177">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-178">중앙 관리 저장소에서 에지 서버로 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="46d6d-178">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-179">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="46d6d-179">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="46d6d-180">모두 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="46d6d-180">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="46d6d-181">에지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-181">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-182">내부 배포에서 내부 에지 서버 인터페이스로의 웹 회의 트래픽</span><span class="sxs-lookup"><span data-stu-id="46d6d-182">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-183">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46d6d-183">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46d6d-184">모두 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="46d6d-184">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="46d6d-185">에지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-185">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-186">내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 설정 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="46d6d-186">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-187">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46d6d-187">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46d6d-188">모두 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="46d6d-188">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="46d6d-189">에지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-189">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-190">내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-190">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-191">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="46d6d-191">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="46d6d-192">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-192">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-193">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-193">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-194">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="46d6d-194">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-195">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="46d6d-195">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="46d6d-196">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-196">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-197">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-197">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-198">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="46d6d-198">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-199">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="46d6d-199">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="46d6d-200">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-200">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-201">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-201">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-202">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController.exe) 또는 에이전트 (ClsAgent.exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="46d6d-202">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="46d6d-203">하드웨어 부하 분산 장치는 Lync Server에 대 한 가용성 및 부하 분산을 제공 하기 위해 배포할 때 특정 요구 사항을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-203">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="46d6d-204">요구 사항은 다음 그림 및 표에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-204">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="46d6d-205">타사 공급 업체는 여기에 정의 된 요구 사항에 서로 다른 용어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-205">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="46d6d-206">Lync Server의 요구 사항을 하드웨어 부하 분산 장치 공급 업체에서 제공 하는 기능 및 구성 옵션에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-206">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="46d6d-207">하드웨어 부하 분산 장치를 구성 하는 경우 다음 요구 사항을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="46d6d-207">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="46d6d-208">액세스에 지 서비스 및 웹 회의에 지 서비스에 대 한 HLB (하드웨어 부하 분산 장치)에서 원본 네트워크 주소 변환 (SNAT)을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-208">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="46d6d-209">SNAT가 A/V에 지 서비스에서 구성 될 수 없음-A/V에 지 서비스는 HLB VIP (가상 IP)가 아니라 실제 서버 주소를 사용 하 여 응답 해야 하며, STUN (relay NAT를 통한 UDP (TURN)/페더레이션 사용 (FTURN)이 정상적으로 작동 하려면이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-209">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="46d6d-210">클라이언트가 HLB에 요청을 보내면 응답은 HLB VIP에서 반환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-210">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="46d6d-211">클라이언트가 Edge에 요청을 보내면 응답은에 지 IP에서 반환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-211">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="46d6d-212">공용 IP 주소는 각 서버 인터페이스 및 HLB의 Vip에서 사용 되며, 공용 ip 주소 요구 사항은 N + 1 이며 각 실제 서버 인터페이스에 대 한 공용 IP 주소와 각 HLB VIP에 대해 하나씩 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-212">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="46d6d-213">풀에에 두 개의에 지 서버가 있는 경우에는 HLB Vip에 대해 3이 사용 되 고 각에 지 서버 인터페이스 (서버에 대 한 총 6 개)에 대해 9 개의 공용 IP 주소가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-213">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="46d6d-214">액세스에 지 서비스 및 웹 회의에 지 서비스의 경우와 HLB에서 NAT를 사용 하는 경우 클라이언트는 VIP에 연결 하 고, VIP는 클라이언트의 원본 IP 주소를 자체 IP 주소로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-214">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="46d6d-215">서버 인터페이스는 보낸 사람 주소를 VIP로, VIP는 서버 인터페이스 IP 주소에서 원본 주소를 변경 하 고 해당 패킷을 클라이언트에 게 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-215">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="46d6d-216">A/V에 지 서비스의 경우 VIP가 원본 IP 주소를 변경 하지 않아야 하며, 실제 서버 주소가 클라이언트에 직접 반환 되며, AV 트래픽에 대해 HLB에 NAT를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-216">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="46d6d-217">클라이언트가 HLB VIP로 요청을 보내면 응답은 HLB VIP에서 반환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-217">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="46d6d-218">클라이언트에서에 지 IP로 요청을 전송 하는 경우에는에 지 IP에서 응답을 다시 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-218">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="46d6d-219">AV의 경우 외부 방화벽은 모든 패킷에 대해 실제 서버 공용 IP 주소를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-219">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="46d6d-220">일단 설정 되 면 클라이언트에서 A/V에 지 서비스 통신은 HLB가 아니라 실제 서버에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-220">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="46d6d-221">내부에 지/내부 서버 및 클라이언트를 라우팅해야 하며, 서버 또는 클라이언트를 호스트 하는 모든 내부 네트워크에 대해 영구 경로가 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-221">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="46d6d-222">HLB 액세스에 지 서비스 VIP가 각에 지 서버 인터페이스에 대 한 기본 게이트웨이 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-222">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="46d6d-223">NAT 계획 및 기능에 대 한 자세한 내용은 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013의 하드웨어 부하 분산 장치 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="46d6d-223">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="46d6d-224">![에 지 서버 포트 및 프로토콜 세부 정보](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "에 지 서버 포트 및 프로토콜 세부 정보")</span><span class="sxs-lookup"><span data-stu-id="46d6d-224">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="46d6d-225">확장 통합에 지에 필요한 외부 포트 설정, 하드웨어 부하 분산: 외부 인터페이스 가상 Ip</span><span class="sxs-lookup"><span data-stu-id="46d6d-225">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46d6d-226">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="46d6d-226">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="46d6d-227">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-227">Source IP address</span></span></th>
<th><span data-ttu-id="46d6d-228">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-228">Destination IP address</span></span></th>
<th><span data-ttu-id="46d6d-229">참고</span><span class="sxs-lookup"><span data-stu-id="46d6d-229">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-230">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="46d6d-230">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="46d6d-231">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-231">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-232">XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="46d6d-232">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="46d6d-233">정의된 XMPP 페더레이션의 XMPP 연락처로부터 들어오는 트래픽을 XMPP 프록시 서비스에서 허용</span><span class="sxs-lookup"><span data-stu-id="46d6d-233">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-234">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="46d6d-234">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="46d6d-235">XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="46d6d-235">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="46d6d-236">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-236">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-237">XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처로 트래픽을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="46d6d-237">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-238">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46d6d-238">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46d6d-239">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-239">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-240">액세스에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-240">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-241">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="46d6d-241">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-242">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="46d6d-242">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46d6d-243">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-243">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-244">액세스에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-244">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-245">Sip를 사용한 SIP 신호, 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="46d6d-245">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-246">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="46d6d-246">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46d6d-247">액세스에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-247">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-248">페더레이션 파트너</span><span class="sxs-lookup"><span data-stu-id="46d6d-248">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="46d6d-249">Sip를 사용한 SIP 신호, 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="46d6d-249">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-250">Web 회의/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46d6d-250">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46d6d-251">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-251">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-252">에 지 서버 웹 회의에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-252">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-253">웹 회의 미디어</span><span class="sxs-lookup"><span data-stu-id="46d6d-253">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-254">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46d6d-254">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46d6d-255">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-255">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-256">에 지 서버 A/V에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-256">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-257">UDP/3478을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="46d6d-257">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-258">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46d6d-258">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46d6d-259">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-259">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-260">에 지 서버 A/V에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-260">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="46d6d-261">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="46d6d-261">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="46d6d-262">확장 통합에 지에 대 한 방화벽 요약, 하드웨어 부하 분산: 내부 인터페이스 가상 Ip</span><span class="sxs-lookup"><span data-stu-id="46d6d-262">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="46d6d-263">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="46d6d-263">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="46d6d-264">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-264">Source IP address</span></span></th>
<th><span data-ttu-id="46d6d-265">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="46d6d-265">Destination IP address</span></span></th>
<th><span data-ttu-id="46d6d-266">참고</span><span class="sxs-lookup"><span data-stu-id="46d6d-266">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-267">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="46d6d-267">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46d6d-268">모두 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="46d6d-268">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="46d6d-269">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-269">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-270">내부에 지 VIP로의 아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="46d6d-270">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-271">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="46d6d-271">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="46d6d-272">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-272">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-273">모두 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="46d6d-273">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="46d6d-274">에 지 서버 내부 인터페이스에서 디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소에 대 한 인바운드 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="46d6d-274">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-275">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="46d6d-275">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="46d6d-276">Any (프런트 엔드 서버 IP 주소, 또는 프런트 엔드 풀 IP 주소 또는이에 지 서버를 사용 하는 Sba (survivable 분기 서버로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="46d6d-276">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="46d6d-277">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-277">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-278">이에 지 서버를 사용 하 여 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소 또는 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에서 A/V 사용자 인증 (A/V 인증 서비스)</span><span class="sxs-lookup"><span data-stu-id="46d6d-278">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-279">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="46d6d-279">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="46d6d-280">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-280">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-281">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-281">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-282">내부 사용자와 외부 사용자 간의 A/V 미디어 전송을 위한 기본 경로</span><span class="sxs-lookup"><span data-stu-id="46d6d-282">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="46d6d-283">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46d6d-283">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46d6d-284">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-284">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-285">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-285">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-286">UDP 통신을 설정할 수 없는 경우 내부 사용자와 외부 사용자 간 A/V 미디어 전송을 위한 대체 경로, TCP는 파일 전송 및 데스크톱 공유용으로 사용됨</span><span class="sxs-lookup"><span data-stu-id="46d6d-286">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="46d6d-287">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="46d6d-287">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="46d6d-288">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="46d6d-288">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="46d6d-289">모두</span><span class="sxs-lookup"><span data-stu-id="46d6d-289">Any</span></span></p></td>
<td><p><span data-ttu-id="46d6d-290">UDP 통신을 설정할 수 없는 경우 내부 사용자와 외부 사용자 간 A/V 미디어 전송을 위한 대체 경로, TCP는 파일 전송 및 데스크톱 공유용으로 사용됨</span><span class="sxs-lookup"><span data-stu-id="46d6d-290">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

