---
title: 포트 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Port summary - Scaled consolidated edge with hardware load balancers
ms:assetid: 91213b1e-f875-464b-83e8-fe3a351595a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398739(v=OCS.15)
ms:contentKeyID: 48184841
ms.date: 04/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60250db155922999ce677248a41c3f4158aba466
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975331"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="port-summary---scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a><span data-ttu-id="a4ac3-102">Lync Server 2013의 포트 요약 - 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지</span><span class="sxs-lookup"><span data-stu-id="a4ac3-102">Port summary - Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a4ac3-103">_**마지막으로 수정한 주제:** 2015-04-27_</span><span class="sxs-lookup"><span data-stu-id="a4ac3-103">_**Topic Last Modified:** 2015-04-27_</span></span>

<span data-ttu-id="a4ac3-104">이 시나리오 아키텍처에서 설명 하는 Lync Server 2013, Edge 서버 기능은 Lync Server 2010에서 구현 된 것과 매우 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-104">The Lync Server 2013, Edge Server functionality described in this scenario architecture is very similar to what was implemented in Lync Server 2010.</span></span> <span data-ttu-id="a4ac3-105">가장 주목할 만한 추가 기능은 XMPP (extensible messaging 및 현재 상태 프로토콜)에 대 한 포트 **5269 (TCP over** )입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-105">The most noticeable addition is the port **5269 over TCP** entry for the extensible messaging and presence protocol (XMPP).</span></span> <span data-ttu-id="a4ac3-106">Lync Server 2013는 Edge 서버 또는 Edge 풀의 XMPP 프록시와 프런트 엔드 서버 또는 프런트 엔드 풀의 XMPP 게이트웨이 서버를 선택적으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-106">Lync Server 2013 optionally deploys an XMPP proxy on the Edge Server or Edge pool and the XMPP gateway server on the Front End Server or Front End pool.</span></span>

<span data-ttu-id="a4ac3-107">IPv4 외에도 Edge 서버는 이제 IPv6을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-107">In addition to IPv4, the Edge Server now supports IPv6.</span></span> <span data-ttu-id="a4ac3-108">명확 하 게 하기 위해 시나리오에 IPv4만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-108">For clarity, only IPv4 is used in the scenarios.</span></span>

<span data-ttu-id="a4ac3-109">**하드웨어 부하 분산을 사용 하 여 크기가 조정 된 통합 된 가장자리**</span><span class="sxs-lookup"><span data-stu-id="a4ac3-109">**Scaled Consolidated Edge using Hardware Load Balancing**</span></span>

<span data-ttu-id="a4ac3-110">![Edge 서버 경계 네트워크 포트 및 프로토콜](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge 서버 경계 네트워크 포트 및 프로토콜")</span><span class="sxs-lookup"><span data-stu-id="a4ac3-110">![Edge Server Perimeter Network ports and protocols](images/Gg398739.063f7dd1-16db-4cc7-8708-bca9bc41184d(OCS.15).jpg "Edge Server Perimeter Network ports and protocols")</span></span>

<div>

## <a name="port-and-protocol-details"></a><span data-ttu-id="a4ac3-111">포트 및 프로토콜 정보</span><span class="sxs-lookup"><span data-stu-id="a4ac3-111">Port and Protocol Details</span></span>

<span data-ttu-id="a4ac3-112">외부 액세스를 제공 하는 기능을 지 원하는 데 필요한 포트만을 여는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-112">It is recommended that you open only the ports required to support the functionality for which you are providing external access.</span></span>

<span data-ttu-id="a4ac3-113">모든 edge 서비스에 대 한 원격 액세스의 경우 인바운드/아웃 바운드에 지 트래픽 그림에 표시 된 대로 SIP 트래픽이 directionally으로 이동 하도록 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-113">For remote access to work for any edge service, it is mandatory that SIP traffic is allowed to flow bi-directionally as shown in the Inbound/Outbound edge traffic figure.</span></span> <span data-ttu-id="a4ac3-114">또 다른 방법으로, 액세스에 지 서비스에 대 한 SIP 메시징은 인스턴트 메시징 (IM), 현재 상태, 웹 회의, 오디오/비디오 (A/V) 및 페더레이션에 관련 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-114">Stated another way, the SIP messaging to and from the Access Edge service is involved in instant messaging (IM), presence, web conferencing, audio/video (A/V) and federation.</span></span>

### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-external-interface--node-1-and-node-2-example"></a><span data-ttu-id="a4ac3-115">축소 된 통합 된 가장자리에 대 한 방화벽 요약, 하드웨어 부하 분산: 외부 인터페이스-노드 1 및 노드 2 (예제)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-115">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: External Interface – Node 1 and Node 2 (Example)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4ac3-116">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="a4ac3-116">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a4ac3-117">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-117">Source IP address</span></span></th>
<th><span data-ttu-id="a4ac3-118">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-118">Destination IP address</span></span></th>
<th><span data-ttu-id="a4ac3-119">상속자</span><span class="sxs-lookup"><span data-stu-id="a4ac3-119">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-120">Access/HTTP/TCP/80</span><span class="sxs-lookup"><span data-stu-id="a4ac3-120">Access/HTTP/TCP/80</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-121">Edge 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-121">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-122">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-122">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-123">인증서 해지/i p 확인 및 검색</span><span class="sxs-lookup"><span data-stu-id="a4ac3-123">Certificate revocation/CRL check and retrieval</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-124">Access/DNS/TCP/53</span><span class="sxs-lookup"><span data-stu-id="a4ac3-124">Access/DNS/TCP/53</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-125">Edge 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-125">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-126">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-126">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-127">TCP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="a4ac3-127">DNS query over TCP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-128">Access/DNS/UDP/53</span><span class="sxs-lookup"><span data-stu-id="a4ac3-128">Access/DNS/UDP/53</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-129">Edge 서버 액세스에 지 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-129">Edge Server Access Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-130">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-130">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-131">UDP를 통한 DNS 쿼리</span><span class="sxs-lookup"><span data-stu-id="a4ac3-131">DNS query over UDP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-132">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="a4ac3-132">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-133">Edge 서버 A/V Edge 서비스 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-133">Edge Server A/V Edge service IP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-134">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-134">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-135">Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013를 실행 하는 파트너와 페더레이션 하는 데 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-135">Required for federating with partners running Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-136">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="a4ac3-136">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-137">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-137">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-138">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-138">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-139">Office Communications Server 2007을 실행 하는 파트너와 페더레이션 하는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-139">Required only for federation with partners running Office Communications Server 2007.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-140">A/V/RTP/TCP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="a4ac3-140">A/V/RTP/TCP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-141">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-141">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-142">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-142">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-143">Office Communications Server 2007을 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="a4ac3-143">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-144">A/V/RTP/UDP/50000-59999</span><span class="sxs-lookup"><span data-stu-id="a4ac3-144">A/V/RTP/UDP/50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-145">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-145">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-146">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-146">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-147">Office Communications Server 2007을 실행 하는 파트너와의 페더레이션에만 필요</span><span class="sxs-lookup"><span data-stu-id="a4ac3-147">Required only for federation with partners running Office Communications Server 2007</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-148">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a4ac3-148">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-149">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-149">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-150">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-150">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-151">3478 아웃 바운드는 Lync Server와 통신 하는 Edge 서버의 버전과 Edge 서버 간 미디어 소통에 대 한 정보를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-151">3478 outbound is used to determine the version of Edge Server that Lync Server is communicating with and also for media traffic from Edge Server-to-Edge Server.</span></span> <span data-ttu-id="a4ac3-152">Lync Server 2010, Windows Live Messenger 및 Office Communications Server 2007 R2와 페더레이션 하는 데 필요 하며, 여러 Edge 풀이 회사 내에 배포 된 경우에도 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-152">Required for federation with Lync Server 2010, Windows Live Messenger, and Office Communications Server 2007 R2, and also if multiple Edge pools are deployed within a company.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-153">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a4ac3-153">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-154">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-154">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-155">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-155">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-156">STUN/UDP/3478에서 후보자의 협상을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-156">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-157">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a4ac3-157">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-158">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-158">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-159">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-159">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-160">TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-160">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-161">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a4ac3-161">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-162">Edge 서버 A/V Edge 서비스 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-162">Edge Server A/V Edge service public IP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-163">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-163">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-164">TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-164">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-node-1-and-node-2"></a><span data-ttu-id="a4ac3-165">축소 된 통합 된 가장자리에 대 한 방화벽 요약, 하드웨어 부하 분산: 내부 인터페이스 노드 1 및 노드 2</span><span class="sxs-lookup"><span data-stu-id="a4ac3-165">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Node 1 and Node 2</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4ac3-166">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="a4ac3-166">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a4ac3-167">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-167">Source IP address</span></span></th>
<th><span data-ttu-id="a4ac3-168">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-168">Destination IP address</span></span></th>
<th><span data-ttu-id="a4ac3-169">상속자</span><span class="sxs-lookup"><span data-stu-id="a4ac3-169">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-170">XMPP/MTLS/TCP/23456</span><span class="sxs-lookup"><span data-stu-id="a4ac3-170">XMPP/MTLS/TCP/23456</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-171">Any (프런트 엔드 서버 주소 또는 XMPP 게이트웨이 서비스를 실행 하는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-171">Any (can be defined as Front End Server address, or Front End pool virtual IP address running the XMPP Gateway service)</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-172">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-172">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-173">프런트 엔드 서버 또는 프런트 엔드 풀에서 실행 되는 XMPP 게이트웨이 서비스의 아웃 바운드 XMPP 트래픽</span><span class="sxs-lookup"><span data-stu-id="a4ac3-173">Outbound XMPP traffic from XMPP Gateway service running on Front End Server or Front End pool</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-174">HTTPS/TCP/4443</span><span class="sxs-lookup"><span data-stu-id="a4ac3-174">HTTPS/TCP/4443</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-175">Any (중앙 관리 저장소를 보유 하는 프런트 엔드 서버 서버 IP 또는 풀로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-175">Any (can be defined as the Front End Server server IP or pool that holds the Central Management store)</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-176">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-176">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-177">중앙 관리 저장소의 변경 내용을 Edge 서버로 복제</span><span class="sxs-lookup"><span data-stu-id="a4ac3-177">Replication of changes from the Central Management store to the Edge Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-178">PSOM/MTLS/TCP/8057</span><span class="sxs-lookup"><span data-stu-id="a4ac3-178">PSOM/MTLS/TCP/8057</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-179">임의 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-179">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-180">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-180">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-181">내부 배포에서 내부에 지 서버 인터페이스로 웹 회의 소통량</span><span class="sxs-lookup"><span data-stu-id="a4ac3-181">Web conferencing traffic from Internal deployment to Internal Edge Server interface</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-182">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a4ac3-182">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-183">임의 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-183">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-184">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-184">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-185">내부 및 외부 사용자 간 Survivable Branch 기기 또는 Survivable Branch 서버 간의 A/V 미디어 전송에 대 한 기본 설정 경로</span><span class="sxs-lookup"><span data-stu-id="a4ac3-185">Preferred path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-186">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a4ac3-186">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-187">임의 (디렉터 IP, 프런트 엔드 서버 IP 또는 풀 가상 IP로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-187">Any (can be defined as Director IP, Front End Server IP or Pool virtual IP)</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-188">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-188">Edge Server Internal interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-189">내부 및 외부 사용자 간 A/V 미디어 전송의 대체 경로, Survivable Branch 기기 또는 Survivable Branch 서버 UDP 통신을 설정할 수 없는 경우 TCP는 파일 전송 및 데스크톱 공유에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-189">Fallback path for A/V media transfer between internal and external users, Survivable Branch Appliance or Survivable Branch Server if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-190">MTLS/TCP/50001</span><span class="sxs-lookup"><span data-stu-id="a4ac3-190">MTLS/TCP/50001</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-191">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-191">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-192">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-192">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-193">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="a4ac3-193">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-194">MTLS/TCP/50002</span><span class="sxs-lookup"><span data-stu-id="a4ac3-194">MTLS/TCP/50002</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-195">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-195">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-196">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-196">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-197">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="a4ac3-197">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-198">MTLS/TCP/50003</span><span class="sxs-lookup"><span data-stu-id="a4ac3-198">MTLS/TCP/50003</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-199">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-199">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-200">Edge 서버 내부 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-200">Edge Server internal interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-201">Lync Server Management Shell 및 중앙 로깅 서비스 cmdlet, ClsController 명령줄 (ClsController .exe) 또는 에이전트 (Clscontroller .exe) 명령 및 로그 수집을 사용 하는 중앙 로깅 서비스 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="a4ac3-201">Centralized Logging Service controller using Lync Server Management Shell and Centralized Logging Service cmdlets, ClsController command line (ClsController.exe) or agent (ClsAgent.exe) commands and log collection</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="a4ac3-202">하드웨어 로드 균형 조정기에는 Lync Server에 대 한 가용성 및 부하 분산을 제공 하기 위해 배포 되는 특정 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-202">Hardware load balancers have specific requirements when deployed to provide availability and load balancing for Lync Server.</span></span> <span data-ttu-id="a4ac3-203">요구 사항은 다음 그림과 표에 정의 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-203">The requirements are defined in the following figure and tables.</span></span> <span data-ttu-id="a4ac3-204">제 3 자 공급 업체는 여기에 정의 된 요구 사항에 대해 다른 용어를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-204">Third party vendors may use different terminology for the requirements defined here.</span></span> <span data-ttu-id="a4ac3-205">Lync Server의 요구 사항을 하드웨어 부하 분산 장치 공급 업체에서 제공 하는 기능 및 구성 옵션에 매핑하는 것이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-205">It will be necessary to map the requirements of Lync Server to the features and configuration options provided by your hardware load balancer vendor.</span></span>

<span data-ttu-id="a4ac3-206">하드웨어 부하 분산 장치를 구성할 때 다음 요구 사항을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-206">When configuring hardware load balancers, consider the following requirements:</span></span>

  - <span data-ttu-id="a4ac3-207">HLB (하드웨어 부하 분산 장치)에서 액세스에 지 서비스 및 웹 회의에 지 서비스에 대 한 원본 네트워크 주소 변환 (SNAT)을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-207">Source Network Address Translation (SNAT) can be configured on the hardware load balancer (HLB) for Access Edge service and Web Conferencing Edge service</span></span>

  - <span data-ttu-id="a4ac3-208">SNAT은 A/V에 지 서비스에 대해 구성할 수 없습니다. A/V Edge 서비스는 HLB (STUN) over NAT를 사용 하 여 UDP의 단순 트래버스를 위한 VIP (가상 IP)가 아닌 실제 서버 주소로 응답 해야 하며, 릴레이 NAT (TURN)/페더레이션 회전 (FTURN)을 올바르게 작동 하려면</span><span class="sxs-lookup"><span data-stu-id="a4ac3-208">SNAT cannot be configured on the A/V Edge service– the A/V Edge service must respond with the real server address, not the HLB virtual IP (VIP), for simple traversal of UDP over NAT (STUN)/traversal using relay NAT (TURN)/federation TURN (FTURN) to work properly</span></span>
    
      - <span data-ttu-id="a4ac3-209">클라이언트가 HLB에 대 한 요청을 보내는 경우, HLB VIP에서 응답을 다시 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-209">If the client sends a request to the HLB, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="a4ac3-210">클라이언트가 Edge에 요청을 보내는 경우에는 Edge IP에서 응답을 다시 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-210">If the client sends a request to the Edge, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="a4ac3-211">공용 IP 주소는 각 서버 인터페이스와 HLB의 Vip에 사용 되며, 공용 IP 주소 요구 사항은 N + 1 이며 각 실제 서버 인터페이스에 대 한 공용 IP 주소와 각 HLB VIP에 대해 하나씩 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-211">Public IP addresses are used on each server interface and on the VIPs of the HLB, and your public IP address requirements are N+1, where there is a public IP address for each real server interface and one for each HLB VIP.</span></span> <span data-ttu-id="a4ac3-212">풀에 두 개의 Edge 서버가 있는 경우,이는 HLB Vip에 3이 사용 되 고 각 Edge 서버 인터페이스 (서버에 대해 총 6 개)에 대해 9 개의 공용 IP 주소를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-212">Where you have 2 Edge servers in the pool, this results in 9 public IP addresses, where 3 are used for the HLB VIPs, and one for each Edge server interface (a total of six for the servers)</span></span>

  - <span data-ttu-id="a4ac3-213">액세스에 지 서비스 및 웹 회의에 지 서비스의 경우, 클라이언트가 VIP에 접속 하 여 VIP가 클라이언트에서 자신의 IP 주소로 원본 IP 주소를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-213">For the Access Edge service and Web Conferencing Edge service, (and using NAT on the HLB) the client contacts the VIP, the VIP changes the source IP address from the client to its own IP address.</span></span> <span data-ttu-id="a4ac3-214">서버 인터페이스는 VIP로 반환 주소를 처리 하 고, VIP는 서버 인터페이스 IP 주소에서 원본 주소를 변경 하 고 패킷을 클라이언트로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-214">The server interface addresses the return address to the VIP, the VIP changes the source address from the server interface IP address and sends the packet to the client</span></span>

  - <span data-ttu-id="a4ac3-215">A/V Edge 서비스의 경우 VIP는 원본 IP 주소를 변경 하지 않아야 하며, 실제 서버 주소는 클라이언트에 직접 반환 되며, AV 트래픽에 대 한 HLB에서 NAT를 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-215">For the A/V Edge service, the VIP must NOT change the source IP address, and the real server address is returned to the client directly – you cannot configure NAT on the HLB for AV traffic</span></span>
    
      - <span data-ttu-id="a4ac3-216">클라이언트가 HLB VIP에 대 한 요청을 보내는 경우, HLB VIP에서 응답을 다시 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-216">If the client sends a request to the HLB VIP, the response must come back from the HLB VIP</span></span>
    
      - <span data-ttu-id="a4ac3-217">클라이언트가 Edge IP에 요청을 보내는 경우에는 Edge IP에서 응답을 다시 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-217">If the client sends a request to the Edge IP, the response must come back from the Edge IP</span></span>

  - <span data-ttu-id="a4ac3-218">AV의 경우 외부 방화벽은 모든 패킷에 대 한 실제 서버 공개 IP 주소를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-218">For AV, the external firewall will retain the real server public IP address for all packets</span></span>

  - <span data-ttu-id="a4ac3-219">일단 설정한 후에는 클라이언트가 A/V Edge 서비스 통신을 HLB 아닌 실제 서버에 게 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-219">Once established, client to A/V Edge service communication is to the real server, not the HLB</span></span>

  - <span data-ttu-id="a4ac3-220">내부에 지 내부 서버 및 클라이언트는 라우팅 되어야 하 고, 서버 또는 클라이언트를 호스트 하는 모든 내부 네트워크에 대해 영구 경로가 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-220">Internal edge to internal servers and clients must be routed, and persistent routes are set for all internal networks that host servers or clients</span></span>

  - <span data-ttu-id="a4ac3-221">HLB 액세스에 지 서비스 VIP가 각 Edge 서버 인터페이스에 대 한 기본 게이트웨이의 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-221">The HLB Access Edge service VIP will act as the default gateway for each Edge server interface</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="a4ac3-222">NAT 계획 및 기능에 대 한 자세한 내용은 <A href="lync-server-2013-hardware-load-balancer-requirements.md">Lync Server 2013의 하드웨어 부하 분산 장치 요구 사항</A>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-222">For further information on NAT planning and functionality, please refer to <A href="lync-server-2013-hardware-load-balancer-requirements.md">Hardware load balancer requirements for Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="a4ac3-223">![Edge 서버 포트 및 프로토콜 세부 정보](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "edge 서버 포트 및 프로토콜 세부 정보")</span><span class="sxs-lookup"><span data-stu-id="a4ac3-223">![Edge Server ports and protocols details](images/Gg398739.1c193b80-98ab-4d59-a854-dbfdb5e209e2(OCS.15).jpg "Edge Server ports and protocols details")</span></span>

### <a name="external-port-settings-required-for-scaled-consolidated-edge-hardware-load-balanced-external-interface-virtual-ips"></a><span data-ttu-id="a4ac3-224">크기가 조정 된 통합 된 가장자리에 필요한 외부 포트 설정, 하드웨어 부하 분산: 외부 인터페이스 가상 Ip</span><span class="sxs-lookup"><span data-stu-id="a4ac3-224">External Port Settings Required for Scaled Consolidated Edge, Hardware Load Balanced: External Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4ac3-225">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="a4ac3-225">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a4ac3-226">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-226">Source IP address</span></span></th>
<th><span data-ttu-id="a4ac3-227">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-227">Destination IP address</span></span></th>
<th><span data-ttu-id="a4ac3-228">상속자</span><span class="sxs-lookup"><span data-stu-id="a4ac3-228">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-229">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a4ac3-229">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-230">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-230">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-231">XMPP 프록시 서비스 (액세스에 지 서비스가 있는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-231">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-232">XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처의 트래픽을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-232">XMPP Proxy service accepts traffic from XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-233">XMPP/TCP/5269</span><span class="sxs-lookup"><span data-stu-id="a4ac3-233">XMPP/TCP/5269</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-234">XMPP 프록시 서비스 (액세스에 지 서비스가 있는 공유 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-234">XMPP Proxy service (shares IP address with Access Edge service)</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-235">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-235">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-236">XMPP 프록시 서비스는 정의 된 XMPP 페더레이션에서 XMPP 연락처로 트래픽을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-236">XMPP Proxy service sends traffic to XMPP contacts in defined XMPP federations</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-237">TLS (액세스/SIP)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a4ac3-237">Access/SIP(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-238">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-238">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-239">액세스에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-239">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-240">외부 사용자 액세스를 위한 클라이언트 대 서버 SIP 트래픽</span><span class="sxs-lookup"><span data-stu-id="a4ac3-240">Client-to-server SIP traffic for external user access</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-241">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a4ac3-241">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-242">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-242">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-243">액세스에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-243">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-244">SIP를 사용 하 여 SIP 신호, 페더레이션 및 공용 인스턴트 메시지 연결</span><span class="sxs-lookup"><span data-stu-id="a4ac3-244">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-245">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a4ac3-245">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-246">액세스에 지 서비스 공용 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-246">Access Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-247">페더레이션 파트너</span><span class="sxs-lookup"><span data-stu-id="a4ac3-247">Federated partner</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-248">SIP를 사용 하 여 SIP 신호, 페더레이션 및 공용 인스턴트 메시지 연결</span><span class="sxs-lookup"><span data-stu-id="a4ac3-248">SIP signaling, federated and public IM connectivity using SIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-249">웹 회의/PSOM (TLS)/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a4ac3-249">Web Conferencing/PSOM(TLS)/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-250">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-250">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-251">Edge 서버 웹 회의에 지 서비스 공개 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-251">Edge Server Web Conferencing Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-252">웹 회의 미디어</span><span class="sxs-lookup"><span data-stu-id="a4ac3-252">Web Conferencing media</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-253">A/V/STUN, MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a4ac3-253">A/V/STUN,MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-254">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-254">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-255">Edge 서버 A/V Edge 서비스 공개 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-255">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-256">STUN/UDP/3478에서 후보자의 협상을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-256">STUN/TURN negotiation of candidates over UDP/3478</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-257">A/V/STUN, MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a4ac3-257">A/V/STUN,MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-258">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-258">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-259">Edge 서버 A/V Edge 서비스 공개 VIP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-259">Edge Server A/V Edge service public VIP address</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-260">TCP/443을 통해 후보의 협상을 STUN/설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-260">STUN/TURN negotiation of candidates over TCP/443</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="firewall-summary-for-scaled-consolidated-edge-hardware-load-balanced-internal-interface-virtual-ips"></a><span data-ttu-id="a4ac3-261">축소 된 통합 된 가장자리에 대 한 방화벽 요약, 하드웨어 부하 분산: 내부 인터페이스 가상 Ip</span><span class="sxs-lookup"><span data-stu-id="a4ac3-261">Firewall Summary for Scaled Consolidated Edge, Hardware Load Balanced: Internal Interface Virtual IPs</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a4ac3-262">역할/프로토콜/TCP 또는 UDP/포트</span><span class="sxs-lookup"><span data-stu-id="a4ac3-262">Role/Protocol/TCP or UDP/Port</span></span></th>
<th><span data-ttu-id="a4ac3-263">원본 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-263">Source IP address</span></span></th>
<th><span data-ttu-id="a4ac3-264">대상 IP 주소</span><span class="sxs-lookup"><span data-stu-id="a4ac3-264">Destination IP address</span></span></th>
<th><span data-ttu-id="a4ac3-265">상속자</span><span class="sxs-lookup"><span data-stu-id="a4ac3-265">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-266">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a4ac3-266">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-267">임의 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-267">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-268">Edge 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-268">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-269">아웃 바운드 SIP 트래픽 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소)에서 내부 경계 VIP로</span><span class="sxs-lookup"><span data-stu-id="a4ac3-269">Outbound SIP traffic (from Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)to Internal Edge VIP</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-270">MTLS (액세스/SIP)/TCP/5061</span><span class="sxs-lookup"><span data-stu-id="a4ac3-270">Access/SIP(MTLS)/TCP/5061</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-271">Edge 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-271">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-272">임의 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소로 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-272">Any (can be defined as Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address)</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-273">Edge Server 내부 인터페이스에서 인바운드 SIP 트래픽 (디렉터, 디렉터 풀 가상 IP 주소, 프런트 엔드 서버 또는 프런트 엔드 풀 가상 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-273">Inbound SIP traffic (to Director, Director pool virtual IP address, Front End Server or Front End pool virtual IP address) from Edge Server internal interface</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-274">SIP/MTLS/TCP/5062</span><span class="sxs-lookup"><span data-stu-id="a4ac3-274">SIP/MTLS/TCP/5062</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-275">Any (프런트 엔드 서버 IP 주소 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는이 Edge 서버를 사용 하는 Survivable Branch 서버를 정의할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="a4ac3-275">Any (can be defined as Front End Server IP address, or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server)</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-276">Edge 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-276">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-277">이 Edge 서버를 사용 하 여 프론트 엔드 서버 또는 프론트 엔드 풀 IP 주소 또는 Survivable Branch 기기 또는 Survivable Branch 서버에서 A/V 사용자 (A/V 인증 서비스) 인증</span><span class="sxs-lookup"><span data-stu-id="a4ac3-277">Authentication of A/V users (A/V authentication service) from Front End Server or Front End pool IP address or any Survivable Branch Appliance or Survivable Branch Server using this Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-278">STUN/MSTURN/UDP/3478</span><span class="sxs-lookup"><span data-stu-id="a4ac3-278">STUN/MSTURN/UDP/3478</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-279">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-279">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-280">Edge 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-280">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-281">내부 및 외부 사용자 간의 A/V 미디어 전송에 대 한 기본 경로</span><span class="sxs-lookup"><span data-stu-id="a4ac3-281">Preferred path for A/V media transfer between internal and external users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a4ac3-282">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a4ac3-282">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-283">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-283">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-284">Edge 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-284">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-285">내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로 UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-285">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a4ac3-286">STUN/MSTURN/TCP/443</span><span class="sxs-lookup"><span data-stu-id="a4ac3-286">STUN/MSTURN/TCP/443</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-287">Edge 서버 내부 VIP 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a4ac3-287">Edge Server Internal VIP interface</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-288">이상</span><span class="sxs-lookup"><span data-stu-id="a4ac3-288">Any</span></span></p></td>
<td><p><span data-ttu-id="a4ac3-289">내부 및 외부 사용자 간 A/V 미디어 전송에 대 한 대체 경로 UDP 통신을 설정할 수 없는 경우 파일 전송 및 데스크톱 공유에 TCP가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ac3-289">Fallback path for A/V media transfer between internal and external users if UDP communication cannot be established, TCP is used for file transfer and desktop sharing</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

