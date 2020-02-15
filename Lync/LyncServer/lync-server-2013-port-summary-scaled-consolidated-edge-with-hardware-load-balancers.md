---
title: 포트 요약-하드웨어 부하 분산 장치로 확장 된 통합에 지
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
ms.openlocfilehash: a3cad84208df5129b3a10c1e80aa28442ebcbd44
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="69305-102">포트 요약-Lync Server 2013의 하드웨어 부하 분산 장치로 확장 된 통합에 지</span><span class="sxs-lookup"><span data-stu-id="69305-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69305-103">_**마지막으로 수정 된 항목:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="69305-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="69305-104">이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge Server 기능은 Lync Server 2010에서 구현 된 것과 매우 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="69305-105">가장 큰 차이점은 XMPP(Extensible Messaging and Presence Protocol)에 대한 포트 **5269 over TCP** 항목이 추가되었다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="69305-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="69305-106">Lync Server 2013는 선택적으로에 지 서버 또는에 지 풀 및 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버에 XMPP 프록시를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="69305-107">이제에 지 서버는 IPv4 외에도 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="69305-108">명확한 이해를 위해 시나리오에서는 IPv4만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="69305-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="69305-109">**하드웨어 부하 분산을 사용 하 여 확장 된 통합에 지**</span><span class="sxs-lookup"><span data-stu-id="69305-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="69305-110">![에 지 서버 경계 네트워크 포트 및 프로토콜](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "에 지 서버 경계 네트워크 포트 및 프로토콜")</span><span class="sxs-lookup"><span data-stu-id="69305-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="69305-111">포트 및 프로토콜 세부 정보</span><span class="sxs-lookup"><span data-stu-id="69305-111">Port and Protocol Details</span></span>

<span data-ttu-id="69305-112">외부 액세스를 제공할 기능을 지원하는 데 필요한 포트만 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="69305-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="69305-p103">원격 액세스가 에지 서비스에 작동하려면 SIP 트래픽이 인바운드/아웃바운드 에지 트래픽 그림에서처럼 양방향으로 전달될 수 있어야 합니다. 다른 방식으로 시작될 경우, 액세스 에지 서비스와 주고 받는 SIP 메시징에는 IM(인스턴트 메시징), 현재 상태, 웹 회의, A/V(오디오/비디오) 및 페더레이션이 수반됩니다.</span><span class="sxs-lookup"><span data-stu-id="69305-p103">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure. Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="69305-115">확장 통합에 지에 대 한 방화벽 요약, 하드웨어 부하 분산: 외부 인터페이스-노드 1 및 노드 2 (예제)</span><span class="sxs-lookup"><span data-stu-id="69305-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69305-116">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="69305-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="69305-117">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-117">Source IP address</span></span></th>
<th><span data-ttu-id="69305-118">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-118">Destination IP address</span></span></th>
<th><span data-ttu-id="69305-119">Notes</span><span class="sxs-lookup"><span data-stu-id="69305-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69305-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="69305-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="69305-121">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="69305-122">모두</span><span class="sxs-lookup"><span data-stu-id="69305-122">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-123">인증서 해지/CRL 검사 및 검색</span><span class="sxs-lookup"><span data-stu-id="69305-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="69305-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="69305-125">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="69305-126">모두</span><span class="sxs-lookup"><span data-stu-id="69305-126">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-127">TCP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="69305-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="69305-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="69305-129">에 지 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="69305-130">모두</span><span class="sxs-lookup"><span data-stu-id="69305-130">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-131">UDP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="69305-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-132">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="69305-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="69305-133">에 지 서버 A/V에 지 서비스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="69305-134">모두</span><span class="sxs-lookup"><span data-stu-id="69305-134">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-135">Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와의 페더레이션에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-136">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="69305-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="69305-137">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="69305-138">모두</span><span class="sxs-lookup"><span data-stu-id="69305-138">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-139">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-140">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="69305-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="69305-141">모두</span><span class="sxs-lookup"><span data-stu-id="69305-141">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-142">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="69305-143">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="69305-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-144">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="69305-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="69305-145">모두</span><span class="sxs-lookup"><span data-stu-id="69305-145">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-146">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="69305-147">Office Communications Server 2007를 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="69305-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="69305-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="69305-149">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="69305-150">모두</span><span class="sxs-lookup"><span data-stu-id="69305-150">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-151">3478 아웃 바운드는 Lync Server가 통신 중인에 지 서버 및에 지 서버-에 지 서버에서의 미디어 트래픽에 대 한 버전을 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69305-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="69305-152">Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와의 페더레이션, 그리고 여러 개의에 지 풀이 회사 내에 배포 된 경우에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-153">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="69305-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="69305-154">모두</span><span class="sxs-lookup"><span data-stu-id="69305-154">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-155">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="69305-156">UDP/3478을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="69305-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-157">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="69305-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="69305-158">모두</span><span class="sxs-lookup"><span data-stu-id="69305-158">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-159">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="69305-160">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="69305-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-161">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="69305-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="69305-162">에 지 서버 A/V에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="69305-163">모두</span><span class="sxs-lookup"><span data-stu-id="69305-163">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-164">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="69305-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="69305-165">확장 통합에 지에 대 한 방화벽 요약, 하드웨어 부하 분산: 내부 인터페이스 노드 1 및 노드 2</span><span class="sxs-lookup"><span data-stu-id="69305-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69305-166">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="69305-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="69305-167">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-167">Source IP address</span></span></th>
<th><span data-ttu-id="69305-168">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-168">Destination IP address</span></span></th>
<th><span data-ttu-id="69305-169">Notes</span><span class="sxs-lookup"><span data-stu-id="69305-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69305-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="69305-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="69305-171">Any (프런트 엔드 서버 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="69305-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="69305-172">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="69305-173">프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="69305-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="69305-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="69305-175">Any (중앙 관리 저장소를 포함 하는 프런트 엔드 서버 서버 IP 또는 풀로 정의 가능)</span><span class="sxs-lookup"><span data-stu-id="69305-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="69305-176">에지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="69305-177">중앙 관리 저장소에서 에지 서버로 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="69305-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="69305-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="69305-179">모두 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="69305-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="69305-180">에지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="69305-181">내부 배포에서 내부 에지 서버 인터페이스로의 웹 회의 트래픽</span><span class="sxs-lookup"><span data-stu-id="69305-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="69305-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="69305-183">모두 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="69305-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="69305-184">에지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="69305-185">내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 설정 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server</span><span class="sxs-lookup"><span data-stu-id="69305-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="69305-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="69305-187">모두 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="69305-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="69305-188">에지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="69305-189">내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로, Sba (survivable Branch 어플라이언스 또는 Sba (survivable Branch Server UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69305-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="69305-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="69305-191">모두</span><span class="sxs-lookup"><span data-stu-id="69305-191">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-192">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="69305-193">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령 줄 (ClsController .exe) 또는 에이전트 (Clscontroller) 명령 및 로그 수집을 사용 하는 중앙화 된 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="69305-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="69305-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="69305-195">모두</span><span class="sxs-lookup"><span data-stu-id="69305-195">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-196">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="69305-197">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령 줄 (ClsController .exe) 또는 에이전트 (Clscontroller) 명령 및 로그 수집을 사용 하는 중앙화 된 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="69305-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="69305-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="69305-199">모두</span><span class="sxs-lookup"><span data-stu-id="69305-199">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-200">에 지 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="69305-201">Lync Server 관리 셸 및 중앙화 된 로깅 서비스 cmdlet, ClsController 명령 줄 (ClsController .exe) 또는 에이전트 (Clscontroller) 명령 및 로그 수집을 사용 하는 중앙화 된 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="69305-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69305-202">하드웨어 부하 분산 장치는 Lync Server에 대 한 가용성 및 부하 분산을 제공 하기 위해 배포할 때 특정 요구 사항을 충족 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="69305-203">요구 사항은 다음 그림 및 표에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69305-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="69305-204">타사 공급 업체는 여기에 정의 된 요구 사항에 서로 다른 용어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69305-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="69305-205">Lync Server의 요구 사항을 하드웨어 부하 분산 장치 공급 업체에서 제공 하는 기능 및 구성 옵션에 매핑해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="69305-206">하드웨어 부하 분산 장치를 구성 하는 경우 다음 요구 사항을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="69305-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="69305-207">액세스에 지 서비스 및 웹 회의에 지 서비스에 대 한 HLB (하드웨어 부하 분산 장치)에서 원본 네트워크 주소 변환 (SNAT)을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69305-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="69305-208">SNAT가 A/V에 지 서비스에서 구성 될 수 없음-A/V에 지 서비스는 HLB VIP (가상 IP)가 아니라 실제 서버 주소를 사용 하 여 응답 해야 하며, STUN (relay NAT를 통한 UDP (TURN)/페더레이션 사용 (FTURN)이 정상적으로 작동 하려면이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="69305-209">클라이언트가 HLB에 요청을 보내면 응답은 HLB VIP에서 반환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="69305-210">클라이언트가 Edge에 요청을 보내면 응답은에 지 IP에서 반환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="69305-211">공용 IP 주소는 각 서버 인터페이스 및 HLB의 Vip에서 사용 되며, 공용 ip 주소 요구 사항은 N + 1 이며 각 실제 서버 인터페이스에 대 한 공용 IP 주소와 각 HLB VIP에 대해 하나씩 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69305-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="69305-212">풀에에 두 개의에 지 서버가 있는 경우에는 HLB Vip에 대해 3이 사용 되 고 각에 지 서버 인터페이스 (서버에 대 한 총 6 개)에 대해 9 개의 공용 IP 주소가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69305-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="69305-213">액세스에 지 서비스 및 웹 회의에 지 서비스의 경우와 HLB에서 NAT를 사용 하는 경우 클라이언트는 VIP에 연결 하 고, VIP는 클라이언트의 원본 IP 주소를 자체 IP 주소로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="69305-214">서버 인터페이스는 보낸 사람 주소를 VIP로, VIP는 서버 인터페이스 IP 주소에서 원본 주소를 변경 하 고 해당 패킷을 클라이언트에 게 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="69305-215">A/V에 지 서비스의 경우 VIP가 원본 IP 주소를 변경 하지 않아야 하며, 실제 서버 주소가 클라이언트에 직접 반환 되며, AV 트래픽에 대해 HLB에 NAT를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69305-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="69305-216">클라이언트가 HLB VIP로 요청을 보내면 응답은 HLB VIP에서 반환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="69305-217">클라이언트에서에 지 IP로 요청을 전송 하는 경우에는에 지 IP에서 응답을 다시 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="69305-218">AV의 경우 외부 방화벽은 모든 패킷에 대해 실제 서버 공용 IP 주소를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="69305-219">일단 설정 되 면 클라이언트에서 A/V에 지 서비스 통신은 HLB가 아니라 실제 서버에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69305-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="69305-220">내부에 지/내부 서버 및 클라이언트를 라우팅해야 하며, 서버 또는 클라이언트를 호스트 하는 모든 내부 네트워크에 대해 영구 경로가 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="69305-221">HLB 액세스에 지 서비스 VIP가 각에 지 서버 인터페이스에 대 한 기본 게이트웨이 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="69305-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="69305-222">NAT 계획 및 기능에 대 한 자세한 내용은 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013의 하드웨어 부하 분산 장치 요구 사항을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="69305-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="69305-223">![에 지 서버 포트 및 프로토콜 세부 정보](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "에 지 서버 포트 및 프로토콜 세부 정보")</span><span class="sxs-lookup"><span data-stu-id="69305-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="69305-224">확장 통합에 지에 필요한 외부 포트 설정, 하드웨어 부하 분산: 외부 인터페이스 가상 Ip</span><span class="sxs-lookup"><span data-stu-id="69305-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69305-225">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="69305-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="69305-226">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-226">Source IP address</span></span></th>
<th><span data-ttu-id="69305-227">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-227">Destination IP address</span></span></th>
<th><span data-ttu-id="69305-228">Notes</span><span class="sxs-lookup"><span data-stu-id="69305-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69305-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="69305-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="69305-230">모두</span><span class="sxs-lookup"><span data-stu-id="69305-230">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-231">XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="69305-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="69305-232">정의된 XMPP 페더레이션의 XMPP 연락처로부터 들어오는 트래픽을 XMPP 프록시 서비스에서 허용</span><span class="sxs-lookup"><span data-stu-id="69305-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="69305-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="69305-234">XMPP 프록시 서비스 (액세스에 지 서비스를 사용 하는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="69305-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="69305-235">모두</span><span class="sxs-lookup"><span data-stu-id="69305-235">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-236">XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처로 트래픽을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="69305-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-237">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="69305-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="69305-238">모두</span><span class="sxs-lookup"><span data-stu-id="69305-238">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-239">액세스에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="69305-240">외부 사용자 액세스를 위한 클라이언트-서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="69305-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-241">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="69305-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="69305-242">모두</span><span class="sxs-lookup"><span data-stu-id="69305-242">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-243">액세스에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="69305-244">Sip를 사용한 SIP 신호, 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="69305-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-245">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="69305-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="69305-246">액세스에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="69305-247">페더레이션 파트너</span><span class="sxs-lookup"><span data-stu-id="69305-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="69305-248">Sip를 사용한 SIP 신호, 페더레이션 및 공용 IM 연결</span><span class="sxs-lookup"><span data-stu-id="69305-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-249">Web 회의/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="69305-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="69305-250">모두</span><span class="sxs-lookup"><span data-stu-id="69305-250">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-251">에 지 서버 웹 회의에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="69305-252">웹 회의 미디어</span><span class="sxs-lookup"><span data-stu-id="69305-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-253">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="69305-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="69305-254">모두</span><span class="sxs-lookup"><span data-stu-id="69305-254">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-255">에 지 서버 A/V에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="69305-256">UDP/3478을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="69305-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-257">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="69305-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="69305-258">모두</span><span class="sxs-lookup"><span data-stu-id="69305-258">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-259">에 지 서버 A/V에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="69305-260">TCP/443을 통한 STUN/TURN 후보 협상</span><span class="sxs-lookup"><span data-stu-id="69305-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="69305-261">확장 통합에 지에 대 한 방화벽 요약, 하드웨어 부하 분산: 내부 인터페이스 가상 Ip</span><span class="sxs-lookup"><span data-stu-id="69305-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69305-262">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="69305-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="69305-263">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-263">Source IP address</span></span></th>
<th><span data-ttu-id="69305-264">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="69305-264">Destination IP address</span></span></th>
<th><span data-ttu-id="69305-265">Notes</span><span class="sxs-lookup"><span data-stu-id="69305-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69305-266">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="69305-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="69305-267">모두 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="69305-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="69305-268">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="69305-269">내부에 지 VIP로의 아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="69305-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-270">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="69305-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="69305-271">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="69305-272">모두 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="69305-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="69305-273">에 지 서버 내부 인터페이스에서 디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소에 대 한 인바운드 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="69305-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="69305-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="69305-275">Any (프런트 엔드 서버 IP 주소, 또는 프런트 엔드 풀 IP 주소 또는이에 지 서버를 사용 하는 Sba (survivable 분기 서버로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="69305-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="69305-276">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="69305-277">이에 지 서버를 사용 하 여 프런트 엔드 서버 또는 프런트 엔드 풀 IP 주소 또는 Sba (survivable Branch 기기 또는 Sba (survivable 분기 서버에서 A/V 사용자 인증 (A/V 인증 서비스)</span><span class="sxs-lookup"><span data-stu-id="69305-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="69305-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="69305-279">모두</span><span class="sxs-lookup"><span data-stu-id="69305-279">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-280">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="69305-281">내부 사용자와 외부 사용자 간의 A/V 미디어 전송을 위한 기본 경로</span><span class="sxs-lookup"><span data-stu-id="69305-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69305-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="69305-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="69305-283">모두</span><span class="sxs-lookup"><span data-stu-id="69305-283">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-284">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="69305-285">UDP 통신을 설정할 수 없는 경우 내부 사용자와 외부 사용자 간 A/V 미디어 전송을 위한 대체 경로, TCP는 파일 전송 및 데스크톱 공유용으로 사용됨</span><span class="sxs-lookup"><span data-stu-id="69305-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69305-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="69305-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="69305-287">에 지 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69305-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="69305-288">모두</span><span class="sxs-lookup"><span data-stu-id="69305-288">Any</span></span></p></td>
<td><p><span data-ttu-id="69305-289">UDP 통신을 설정할 수 없는 경우 내부 사용자와 외부 사용자 간 A/V 미디어 전송을 위한 대체 경로, TCP는 파일 전송 및 데스크톱 공유용으로 사용됨</span><span class="sxs-lookup"><span data-stu-id="69305-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

