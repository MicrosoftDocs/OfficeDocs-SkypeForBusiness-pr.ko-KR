---
title: 'Lync Server 2013: 외부 A/V 방화벽 및 포트 요구 사항 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Determine external A/V firewall and port requirements
ms:assetid: 3b849dc7-175d-40d1-820d-80e6ade6d332
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425882(v=OCS.15)
ms:contentKeyID: 48183872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5519ef37ff334ddf196e94b40aa7df14d69d25
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="determine-external-av-firewall-and-port-requirements-for-lync-server-2013"></a><span data-ttu-id="c87ef-102">Lync Server 2013에 대한 외부 A/V 방화벽 및 포트 요구 사항 확인</span><span class="sxs-lookup"><span data-stu-id="c87ef-102">Determine external A/V firewall and port requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c87ef-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="c87ef-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c87ef-104">오디오/비디오 (A/V) 통신은 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-104">Audio/Video (A/V) communication can be a complex.</span></span> <span data-ttu-id="c87ef-105">A/V에 사용 되는 프로토콜의 특성과 클라이언트 및 서버에서 프로토콜을 사용 하는 방법 때문에, 특별 섹션은 클라이언트와 서버 버전 간의 차이점을 설명 하도록 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-105">Because of the nature of protocols used in A/V and how clients and servers use the protocols, a special section is warranted to explain the differences between client and server versions.</span></span>

<span data-ttu-id="c87ef-106">다음 A/V 방화벽과 포트 테이블을 사용 하 여 방화벽 요구 사항과 열 포트를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-106">Use the following A/V Firewall and Port table to determine firewall requirements and which ports to open.</span></span> <span data-ttu-id="c87ef-107">그런 다음 NAT를 다양 한 방식으로 구현할 수 있으므로 NAT (network address translation) 용어를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-107">Then, review the network address translation (NAT) terminology because NAT can be implemented in many different ways.</span></span> <span data-ttu-id="c87ef-108">방화벽 포트 설정에 대 한 자세한 예제는 [Lync Server 2013에서 외부 사용자 액세스를 위한 시나리오](lync-server-2013-scenarios-for-external-user-access.md)의 참조 아키텍처를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c87ef-108">For a detailed example of firewall port settings, see the reference architectures in [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

### <a name="general-protocol-usage-for-udp-and-tcp-in-audiovideo-and-media-traffic"></a><span data-ttu-id="c87ef-109">오디오/비디오 및 미디어 트래픽에 대 한 UDP 및 TCP의 일반 프로토콜 사용</span><span class="sxs-lookup"><span data-stu-id="c87ef-109">General Protocol Usage for UDP and TCP in Audio/Video and Media Traffic</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c87ef-110">오디오/비디오 전송</span><span class="sxs-lookup"><span data-stu-id="c87ef-110">Audio/Video Transport</span></span></th>
<th><span data-ttu-id="c87ef-111">용도</span><span class="sxs-lookup"><span data-stu-id="c87ef-111">Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c87ef-112">UDP</span><span class="sxs-lookup"><span data-stu-id="c87ef-112">UDP</span></span></p></td>
<td><p><span data-ttu-id="c87ef-113">오디오 및 비디오에 대 한 기본 전송 계층 프로토콜</span><span class="sxs-lookup"><span data-stu-id="c87ef-113">Preferred transport layer protocol for audio and video</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c87ef-114">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="c87ef-114">TCP</span></span></p></td>
<td><p><span data-ttu-id="c87ef-115">오디오 및 비디오에 대 한 대체 전송 계층 프로토콜</span><span class="sxs-lookup"><span data-stu-id="c87ef-115">Fallback transport layer protocol for audio and video</span></span></p>
<p><span data-ttu-id="c87ef-116">Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013에 대 한 응용 프로그램 공유에 필요한 전송 계층 프로토콜</span><span class="sxs-lookup"><span data-stu-id="c87ef-116">Required transport layer protocol for application sharing to Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013</span></span></p>
<p><span data-ttu-id="c87ef-117">Lync Server 2010 및 Lync Server 2013에 파일을 전송 하는 데 필요한 전송 계층 프로토콜</span><span class="sxs-lookup"><span data-stu-id="c87ef-117">Required transport layer protocol for file transfer to Lync Server 2010 and Lync Server 2013</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="external-av-firewall-port-requirements-for-external-user-access"></a><span data-ttu-id="c87ef-118">외부 사용자 액세스를 위한 외부 A/V 방화벽 포트 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c87ef-118">External A/V Firewall Port Requirements for External User Access</span></span>

<span data-ttu-id="c87ef-119">외부 (및 내부) SIP 및 회의 인터페이스에 대 한 방화벽 포트 요구 사항은 클라이언트 버전 또는 페더레이션 파트너 버전에 관계 없이 일관성을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-119">The firewall port requirements for external (and internal) SIP and conferencing interfaces are consistent, regardless of the version of your client or the version of the federation partner.</span></span>

<span data-ttu-id="c87ef-120">오디오/비디오 가장자리 외부 인터페이스에는 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-120">The same is not true for the Audio/Video Edge external interface.</span></span> <span data-ttu-id="c87ef-121">Office Communications Server 2007의 페더레이션에서 A/V Edge 서비스를 사용 하려면 5만 ~ 59999 포트 범위의 RTP/TCP 및 RTP/UDP 트래픽이 양방향으로 이동 하도록 하는 외부 방화벽 규칙이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-121">For federation with Office Communications Server 2007, the A/V Edge service requires that external firewall rules allow RTP/TCP and RTP/UDP traffic in the 50,000 through 59,999 port range to flow in both directions.</span></span> <span data-ttu-id="c87ef-122">이전 표에는 Lync Server 2013이 기본 페더레이션 파트너가 고 나열 된 다른 페더레이션 파트너 종류 중 하 나와 통신 하도록 구성 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-122">The previous table assumes that Lync Server 2013 is the primary federation partner and it is being configured to communicate with one of the other federation partner types listed.</span></span>

<span data-ttu-id="c87ef-123">50000-59999의 오디오/비디오 범위 구성 포트 범위에는 페더레이션 파트너와의 통신을 위한 원본 포트가 포함 되어야 한다는 것을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-123">Configuring the Audio/Video port range of 50,000-59,999 must take into account that the port range will contain the source ports for communications to federation partners.</span></span> <span data-ttu-id="c87ef-124">자세한 내용은 페더레이션 파트너에서 통신을 시작 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-124">In detail, consider that a communication is initiated from a federation partner.</span></span> <span data-ttu-id="c87ef-125">50000-59999 범위의 A/V Edge 서비스 포트와 통신 하는 경우 파트너의 A/V Edge 서비스의 예상 포트 TCP 443에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-125">The communication from the A/V Edge service ports in the 50,000-59,999 range will connect to the expected port TCP 443 of the partner’s A/V Edge service.</span></span> <span data-ttu-id="c87ef-126">반대로, A/V Edge 서비스 포트 TCP 443에 대 한 인바운드 트래픽에는 50000-59999 범위의 원본 포트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-126">Conversely, inbound traffic to your A/V Edge service port TCP 443 will have a source port in the range of 50,000-59,999.</span></span>

<span data-ttu-id="c87ef-127">방화벽 관리를 위한 방화벽 및 정책에 따라 대상 규칙만 구성 해야 하거나 원본 및 대상을 모두 구성 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-127">Different firewalls and policies for firewall administration may require only destination rules to be configured, or they may require both source and destination to be configured.</span></span> <span data-ttu-id="c87ef-128">요구 사항이 대상 포트에만 해당 하는 경우 오디오/비디오 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-128">If your requirements are for destination ports only, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c87ef-129">원본 IP</span><span class="sxs-lookup"><span data-stu-id="c87ef-129">Source IP</span></span></th>
<th><span data-ttu-id="c87ef-130">대상 IP</span><span class="sxs-lookup"><span data-stu-id="c87ef-130">Destination IP</span></span></th>
<th><span data-ttu-id="c87ef-131">대상 포트</span><span class="sxs-lookup"><span data-stu-id="c87ef-131">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c87ef-132">A/V Edge 서비스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c87ef-132">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="c87ef-133">이상</span><span class="sxs-lookup"><span data-stu-id="c87ef-133">Any</span></span></p></td>
<td><p><span data-ttu-id="c87ef-134">TCP 443</span><span class="sxs-lookup"><span data-stu-id="c87ef-134">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c87ef-135">A/V Edge 서비스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c87ef-135">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="c87ef-136">이상</span><span class="sxs-lookup"><span data-stu-id="c87ef-136">Any</span></span></p></td>
<td><p><span data-ttu-id="c87ef-137">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="c87ef-137">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c87ef-138">이상</span><span class="sxs-lookup"><span data-stu-id="c87ef-138">Any</span></span></p></td>
<td><p><span data-ttu-id="c87ef-139">A/V Edge 서비스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c87ef-139">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="c87ef-140">TCP 443</span><span class="sxs-lookup"><span data-stu-id="c87ef-140">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c87ef-141">이상</span><span class="sxs-lookup"><span data-stu-id="c87ef-141">Any</span></span></p></td>
<td><p><span data-ttu-id="c87ef-142">A/V Edge 서비스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c87ef-142">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="c87ef-143">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="c87ef-143">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c87ef-144">정책에 인바운드와 아웃 바운드 방화벽 규칙 정의가 모두 필요한 경우 오디오/비디오 요구 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-144">If your policies require both inbound and outbound firewall rule definitions, the Audio/Video requirements are:</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c87ef-145">원본 IP</span><span class="sxs-lookup"><span data-stu-id="c87ef-145">Source IP</span></span></th>
<th><span data-ttu-id="c87ef-146">대상 IP</span><span class="sxs-lookup"><span data-stu-id="c87ef-146">Destination IP</span></span></th>
<th><span data-ttu-id="c87ef-147">원본 포트</span><span class="sxs-lookup"><span data-stu-id="c87ef-147">Source Port</span></span></th>
<th><span data-ttu-id="c87ef-148">대상 포트</span><span class="sxs-lookup"><span data-stu-id="c87ef-148">Destination Port</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c87ef-149">A/V Edge 서비스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c87ef-149">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="c87ef-150">이상</span><span class="sxs-lookup"><span data-stu-id="c87ef-150">Any</span></span></p></td>
<td><p><span data-ttu-id="c87ef-151">TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="c87ef-151">TCP 50,000-59,999</span></span></p></td>
<td><p><span data-ttu-id="c87ef-152">TCP 443</span><span class="sxs-lookup"><span data-stu-id="c87ef-152">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c87ef-153">A/V Edge 서비스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c87ef-153">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="c87ef-154">이상</span><span class="sxs-lookup"><span data-stu-id="c87ef-154">Any</span></span></p></td>
<td><p><span data-ttu-id="c87ef-155">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="c87ef-155">UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="c87ef-156">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="c87ef-156">UDP 3478</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c87ef-157">이상</span><span class="sxs-lookup"><span data-stu-id="c87ef-157">Any</span></span></p></td>
<td><p><span data-ttu-id="c87ef-158">A/V Edge 서비스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c87ef-158">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="c87ef-159">이상</span><span class="sxs-lookup"><span data-stu-id="c87ef-159">Any</span></span></p></td>
<td><p><span data-ttu-id="c87ef-160">TCP 443</span><span class="sxs-lookup"><span data-stu-id="c87ef-160">TCP 443</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c87ef-161">이상</span><span class="sxs-lookup"><span data-stu-id="c87ef-161">Any</span></span></p></td>
<td><p><span data-ttu-id="c87ef-162">A/V Edge 서비스 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c87ef-162">A/V Edge service interface</span></span></p></td>
<td><p><span data-ttu-id="c87ef-163">이상</span><span class="sxs-lookup"><span data-stu-id="c87ef-163">Any</span></span></p></td>
<td><p><span data-ttu-id="c87ef-164">UDP 3478</span><span class="sxs-lookup"><span data-stu-id="c87ef-164">UDP 3478</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <span data-ttu-id="c87ef-165">Microsoft Office 통신 서버 2007에는 약간 다른 구성이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-165">Microsoft Office Communications Server 2007 requires a slightly different configuration.</span></span> <span data-ttu-id="c87ef-166">50000-59999의 TCP 및 UDP 포트 범위는 인바운드와 아웃 바운드로 열려 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-166">The TCP and UDP port range of 50,000-59,999 must be open inbound and outbound.</span></span> <span data-ttu-id="c87ef-167">이 요구 사항은 Office Communicator 2007에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-167">This requirement is only for Office Communicator 2007.</span></span> <span data-ttu-id="c87ef-168">Office Communications Server 2007 R2, Lync Server 2010 및 Lync Server 2013에만 TCP 범위 50000-59999 open outbound이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-168">Office Communications Server 2007 R2, Lync Server 2010 and Lync Server 2013 only require TCP range 50,000-59,999 open outbound.</span></span>



</div>

</div>

<div>

## <a name="nat-requirements-for-the-edge-service"></a><span data-ttu-id="c87ef-169">Edge 서비스에 대 한 NAT 요구 사항</span><span class="sxs-lookup"><span data-stu-id="c87ef-169">NAT requirements for the Edge service</span></span>

<span data-ttu-id="c87ef-170">Edge 서비스에 대해 라우팅할 수 없는 개인 IP 주소를 구성 하도록 선택 하는 경우 다음 NAT 요구 사항이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-170">The following NAT requirements apply if you choose to configure non-routable private IP addresses for the Edge service:</span></span>

  - <span data-ttu-id="c87ef-171">NAT는 DNS 로드 밸런싱 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-171">NAT can only be used with DNS load-balancing.</span></span> <span data-ttu-id="c87ef-172">NAT는 HLB (하드웨어 부하 분산) Edge 토폴로지에서는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-172">NAT is not supported with a hardware load balancing (HLB) Edge topology.</span></span>

  - <span data-ttu-id="c87ef-173">NAT는 외부에 지 인터페이스 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-173">NAT can only be used on the external Edge interface.</span></span> <span data-ttu-id="c87ef-174">NAT는 내부에 지 인터페이스에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-174">NAT is not supported on the internal Edge interface.</span></span>

  - <span data-ttu-id="c87ef-175">NAT는 들어오고 나가는 트래픽에 대해 대칭적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-175">NAT must be symmetric for incoming and outgoing traffic.</span></span>
    
  - <span data-ttu-id="c87ef-176">인터넷의 트래픽에 대해 NAT는 A/V에 지 서비스의 NAT 사용 공용 IP 주소에서 외부 IP 주소로 대상 IP 주소를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-176">For traffic from the Internet, NAT must change the destination IP address from the NAT-enabled public IP address of the A/V Edge service to its external IP address.</span></span> <span data-ttu-id="c87ef-177">원본 IP 주소는 그대로 유지 되어야 하며, A/V Edge 서비스에서 최적의 미디어 경로를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-177">The source IP address must remain intact, so that the A/V Edge service can find the optimal media path.</span></span>
  
  <span data-ttu-id="c87ef-178">예를 들어 아래 그림의 인바운드 방향에서 공용 IP 주소 131.107.155.30 외부 (개인) IP 주소 10.45.16.10로 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-178">For example, in the inbound direction in the figure below, the public IP address 131.107.155.30 was changed to the external (private) IP address 10.45.16.10.</span></span> <span data-ttu-id="c87ef-179">원본 IP 주소가 변경 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-179">The source IP address remained unchanged.</span></span>
  
  - <span data-ttu-id="c87ef-180">A/V Edge 서비스에서 인터넷으로 전송 하는 경우 NAT는 A/V Edge 서비스의 외부 IP 주소에서 NAT 사용 공용 IP 주소로 원본 IP 주소를 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-180">For traffic from the A/V Edge service to the Internet, NAT must change the source IP address from the external IP address of the A/V Edge service to the NAT-enabled public IP address.</span></span>

<span data-ttu-id="c87ef-181">예를 들어 아래 그림의 아웃 바운드 방향에서 외부 (개인) IP 주소 10.45.16.10 공용 IP 주소 131.107.155.30로 변경 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-181">For example, in the outbound direction in the figure below, the external (private) IP address 10.45.16.10 was changed to the public IP address 131.107.155.30.</span></span>

<span data-ttu-id="c87ef-182">**아래 그림은 NAT에서 인바운드 트래픽 및 아웃 바운드 트래픽의 원본 IP 주소에 대 한 대상 IP 주소를 변경 하는 방법을 보여 줍니다.**</span><span class="sxs-lookup"><span data-stu-id="c87ef-182">**The figure below shows how NAT changes the destination IP address for inbound traffic and the source IP Address for outbound traffic.**</span></span>

<span data-ttu-id="c87ef-183">![대상/원본 IP 주소 변경](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "대상/원본 IP 주소 변경")</span><span class="sxs-lookup"><span data-stu-id="c87ef-183">![Changing destination/source IP addresses](images/Gg425882.0fee7ec5-4cb8-4aff-9164-e7fbab73336d(OCS.15).jpg "Changing destination/source IP addresses")</span></span>

<span data-ttu-id="c87ef-184">주요 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-184">The key points are:</span></span>

  - <span data-ttu-id="c87ef-185">A/V Edge 서비스를 실행 하는 서버에 대 한 인바운드 트래픽 인 경우 원본 IP 주소는 변경 되지 않지만 대상 IP 주소는 131.107.155.30에서 10.45.16.10의 변환 된 IP 주소로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-185">Traffic that is inbound to the server running the A/V Edge service, the source IP address does not change but the destination IP address changes from 131.107.155.30 to the translated IP address of 10.45.16.10.</span></span>

  - <span data-ttu-id="c87ef-186">A/V Edge 서비스를 실행 하는 서버에서 워크스테이션으로 다시 보내는 트래픽 인 경우 원본 IP 주소는 서버의 공용 IP 주소에서 A/V Edge 서비스를 실행 하는 서버의 공용 IP 주소로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-186">Traffic that is outbound from the server running the A/V Edge service back to the workstation, the source IP address changes from the server’s public IP address to the public IP address of the server running the A/V Edge service.</span></span> <span data-ttu-id="c87ef-187">대상 IP는 워크스테이션의 공용 IP 주소를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-187">The destination IP remains the workstation’s public IP address.</span></span> <span data-ttu-id="c87ef-188">패킷이 첫 번째 NAT 디바이스 아웃 바운드로 나간 후에는 NAT 장치의 규칙이 A/V Edge 서비스 외부 인터페이스 IP 주소 (10.45.16.10)를 실행 하는 서버의 원본 IP 주소를 해당 공용 IP 주소 (131.107.155.30)로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="c87ef-188">After the packet leaves the first NAT device outbound, the rule on the NAT device changes the source IP address of the server running the A/V Edge service external interface IP address (10.45.16.10) to its public IP address (131.107.155.30).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

