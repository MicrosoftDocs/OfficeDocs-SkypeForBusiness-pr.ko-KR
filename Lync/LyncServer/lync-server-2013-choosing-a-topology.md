---
title: 'Lync Server 2013: 토폴로지 선택'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9f59648d845f37c7cf6d92c471b81a29415753
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="4eec2-102">Lync Server 2013에서 토폴로지 선택</span><span class="sxs-lookup"><span data-stu-id="4eec2-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="4eec2-103">_**마지막으로 수정한 주제:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="4eec2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="4eec2-104">토폴로지를 선택 하면 다음과 같은 지원 되는 토폴로지 옵션 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4eec2-105">다른 언급이 없는 한, Microsoft Lync Server 2010에 대 한 경험이 있는 경우 여기에 나와 있는 지침이 대부분 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="4eec2-106">Lync Server 2013의 개인 IP 주소 및 NAT 사용 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="4eec2-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="4eec2-107">Lync Server 2013의 공용 IP 주소의 단일 통합 에지</span><span class="sxs-lookup"><span data-stu-id="4eec2-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="4eec2-108">Lync Server 2013의 조정된 통합 에지, NAT 사용 개인 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="4eec2-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="4eec2-109">Lync Server 2013의 조정된 통합 에지, 공용 IP 주소의 DNS 부하 분산</span><span class="sxs-lookup"><span data-stu-id="4eec2-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="4eec2-110">Lync Server 2013의 하드웨어 부하 분산 장치를 사용하는 조정된 통합 에지</span><span class="sxs-lookup"><span data-stu-id="4eec2-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="4eec2-111">내부 에지 인터페이스와 외부 에지 인터페이스는 같은 유형의 부하 분산을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-111">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="4eec2-112">즉, 한 에지 인터페이스에서는 DNS 부하 분산을 사용하고 다른 에지 인터페이스에서는 하드웨어 부하 분산을 사용할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-112">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="4eec2-113">다음 표에서는 지원 되는 Microsoft Lync Server 2013 토폴로지에서 사용할 수 있는 기능을 요약 하 여 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="4eec2-114">열 머리글은 해당 Edge 구성 옵션에 대해 사용할 수 있는 기능을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="4eec2-115">크기가 조정 된 가장자리 (DNS 부하 분산) 옵션을 사용 하는 경우 높은 가용성을 지원할 수 있으며, 외부 인터페이스에 지정 된 라우팅 불가능 한 개인 IP 주소 또는 라우팅 가능한 공용 IP 주소를 사용 하 여 비용을 줄일 수 있습니다. 하드웨어 로드 균형 조정기는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="4eec2-116">DNS 부하 분산에서 지원 되는 Edge 장애 조치 시나리오는 Lync에서 Lync를 사용 하는 지점간 세션, Lync 회의 세션, Lync-PSTN 세션 및 Office 365입니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="4eec2-117">DNS 부하 분산에 도움이 되지 않는 Edge 장애 조치 시나리오는 원격 사용자의 Exchange UM (통합 메시징), Exchange 2010 SP1 이전 버전, 공용 인스턴트 메시징 (IM) 연결, Office Communications을 실행 하는 서버와의 페더레이션 등의 장애 조치입니다. Server.</span><span class="sxs-lookup"><span data-stu-id="4eec2-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="4eec2-118">Edge 서버 토폴로지 옵션 요약</span><span class="sxs-lookup"><span data-stu-id="4eec2-118">Summary of Edge Server Topology Options</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4eec2-119">토폴로지</span><span class="sxs-lookup"><span data-stu-id="4eec2-119">Topology</span></span></th>
<th><span data-ttu-id="4eec2-120">고가용성</span><span class="sxs-lookup"><span data-stu-id="4eec2-120">High availability</span></span></th>
<th><span data-ttu-id="4eec2-121">Edge 풀의 외부에 지 서버에 필요한 추가 DNS 레코드</span><span class="sxs-lookup"><span data-stu-id="4eec2-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="4eec2-122">Lync에서 Lync 용 세션에 대 한 Edge 장애 조치</span><span class="sxs-lookup"><span data-stu-id="4eec2-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="4eec2-123">Lync to Lync EUM/PIC/OCS 페더레이션 세션에 대 한 Edge 장애 조치</span><span class="sxs-lookup"><span data-stu-id="4eec2-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eec2-124">NAT를 사용 하 여 단일 쪽</span><span class="sxs-lookup"><span data-stu-id="4eec2-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="4eec2-125">아니요</span><span class="sxs-lookup"><span data-stu-id="4eec2-125">No</span></span></p></td>
<td><p><span data-ttu-id="4eec2-126">아니요</span><span class="sxs-lookup"><span data-stu-id="4eec2-126">No</span></span></p></td>
<td><p><span data-ttu-id="4eec2-127">아니요</span><span class="sxs-lookup"><span data-stu-id="4eec2-127">No</span></span></p></td>
<td><p><span data-ttu-id="4eec2-128">아니요</span><span class="sxs-lookup"><span data-stu-id="4eec2-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eec2-129">공용 IP를 사용 하는 단일 쪽</span><span class="sxs-lookup"><span data-stu-id="4eec2-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="4eec2-130">아니요</span><span class="sxs-lookup"><span data-stu-id="4eec2-130">No</span></span></p></td>
<td><p><span data-ttu-id="4eec2-131">아니요</span><span class="sxs-lookup"><span data-stu-id="4eec2-131">No</span></span></p></td>
<td><p><span data-ttu-id="4eec2-132">아니요</span><span class="sxs-lookup"><span data-stu-id="4eec2-132">No</span></span></p></td>
<td><p><span data-ttu-id="4eec2-133">아니요</span><span class="sxs-lookup"><span data-stu-id="4eec2-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eec2-134">NAT를 사용 하 여 크기가 조정 된 Edge (DNS 부하 분산)</span><span class="sxs-lookup"><span data-stu-id="4eec2-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="4eec2-135">예</span><span class="sxs-lookup"><span data-stu-id="4eec2-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="4eec2-136">예</span><span class="sxs-lookup"><span data-stu-id="4eec2-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="4eec2-137">예</span><span class="sxs-lookup"><span data-stu-id="4eec2-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eec2-138">공용 IP를 사용 하 여 크기가 조정 된 Edge (DNS 부하 분산)</span><span class="sxs-lookup"><span data-stu-id="4eec2-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="4eec2-139">예</span><span class="sxs-lookup"><span data-stu-id="4eec2-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="4eec2-140">예</span><span class="sxs-lookup"><span data-stu-id="4eec2-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="4eec2-141">예</span><span class="sxs-lookup"><span data-stu-id="4eec2-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eec2-142">확장 된 Edge 하드웨어 부하 분산)</span><span class="sxs-lookup"><span data-stu-id="4eec2-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="4eec2-143">예</span><span class="sxs-lookup"><span data-stu-id="4eec2-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="4eec2-144">없음 (VIP 당 하나의 DNS A 레코드)</span><span class="sxs-lookup"><span data-stu-id="4eec2-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="4eec2-145">예</span><span class="sxs-lookup"><span data-stu-id="4eec2-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="4eec2-146">예</span><span class="sxs-lookup"><span data-stu-id="4eec2-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4eec2-147">**\*** DNS 부하 분산에서는 공용 IM (인스턴트 메시징) 연결에 대 한 장애 조치 및 Office Communications Server를 실행 하는 서버와의 페더레이션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="4eec2-148">DNS 부하 분산을 사용 하는 exchange UM (원격 사용자) 장애 조치 (failover)에는 Exchange Server 2010 SP1 이상 버전이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="4eec2-149">단일 모서리 및 배율 조정 된 모서리 (DNS 부하 분산) 토폴로지에서 다음을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="4eec2-150">라우팅할 수 있는 공용 IP 주소</span><span class="sxs-lookup"><span data-stu-id="4eec2-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="4eec2-151">대칭적 NAT (network address translation)를 사용 하는 경우 라우팅할 수 없는 개인 IP 주소</span><span class="sxs-lookup"><span data-stu-id="4eec2-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="4eec2-152">NAT에서 공용 IP 주소 또는 개인 IP 주소를 사용 하는 경우에도 토폴로지 작성기의 구성 선택에 따라 동일한 수의 IP 주소를 사용 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="4eec2-153">각 서비스에 대 한 고유 포트를 사용 하 여 단일 IP 주소를 사용 하거나, 서비스 별로 고유한 IP 주소를 사용 하 되, 동일한 포트 (기본적으로 TCP 443)를 사용 하도록 Edge 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="4eec2-154">NAT에서 라우팅할 수 없는 개인 IP 주소를 사용 하기로 결정 한 경우:</span><span class="sxs-lookup"><span data-stu-id="4eec2-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="4eec2-155">세 개의 외부 인터페이스 모두에서 라우팅할 수 있는 개인 IP 주소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="4eec2-156">들어오고 나가는 트래픽에 대해 대칭 NAT를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="4eec2-157">크기가 조정 된 Edge (하드웨어 부하 분산) 토폴로지에서는 공용 IP 주소를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="4eec2-158">Lync Server 2013는 단일 및 배율 통합 된 Edge 서버 토폴로지에 대해 NAT (network address translation)를 수행 하는 라우터 또는 방화벽 뒤에 Access, 웹 회의 및 A/V 경계 외부 인터페이스를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="4eec2-159">모든 Edge 외부 인터페이스에 NAT를 사용 하려면 DNS 부하 분산을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-159">Using NAT for all Edge external interfaces requires the use of DNS load balancing.</span></span> <span data-ttu-id="4eec2-160">하드웨어 부하 분산 장치를 사용 하는 것과 비교해 볼 때 NAT 없이 DNS 부하 분산을 사용 하면 다음 목록에 나와 있는 것 처럼 Edge 풀에 있는 Edge 당 공용 IP 주소 수를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-160">When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="4eec2-161">Lync Server 2013 배율 조정 된 통합 된 Edge (DNS 부하 분산)에는 edge 풀의 각 Edge 서버에 대 한 세 가지 공용 IP 주소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="4eec2-162">Lync Server 2013 배율 통합 된 가장자리 (하드웨어 부하 분산)에는 부하 분산 장치 가상 IP 주소에 대 한 세 가지 공용 IP 주소 (더 많은 Edge 서버를 풀에 추가 하는 데 사용 되지 않는 한 가지) 및 다음 당 세 개의 공용 IP 주소가 필요 합니다. 풀의 Edge 서버.</span><span class="sxs-lookup"><span data-stu-id="4eec2-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="4eec2-163">확장 통합 된 가장자리에 대 한 IP 주소 요구 사항 (역할별 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="4eec2-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4eec2-164">풀 당 Edge 서버 수</span><span class="sxs-lookup"><span data-stu-id="4eec2-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="4eec2-165">필요한 IP 주소 수 Lync Server 2013 (DNS 부하 분산)</span><span class="sxs-lookup"><span data-stu-id="4eec2-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="4eec2-166">필요한 IP 주소 수 Lync Server 2013 (하드웨어 부하 분산)</span><span class="sxs-lookup"><span data-stu-id="4eec2-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eec2-167">2</span><span class="sxs-lookup"><span data-stu-id="4eec2-167">2</span></span></p></td>
<td><p><span data-ttu-id="4eec2-168">26</span><span class="sxs-lookup"><span data-stu-id="4eec2-168">6</span></span></p></td>
<td><p><span data-ttu-id="4eec2-169">3 (VIP 당 1 개) + 6</span><span class="sxs-lookup"><span data-stu-id="4eec2-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eec2-170">3</span><span class="sxs-lookup"><span data-stu-id="4eec2-170">3</span></span></p></td>
<td><p><span data-ttu-id="4eec2-171">되었는지</span><span class="sxs-lookup"><span data-stu-id="4eec2-171">9</span></span></p></td>
<td><p><span data-ttu-id="4eec2-172">3 (VIP 당 1 개) + 9</span><span class="sxs-lookup"><span data-stu-id="4eec2-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eec2-173">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="4eec2-173">4</span></span></p></td>
<td><p><span data-ttu-id="4eec2-174">까지</span><span class="sxs-lookup"><span data-stu-id="4eec2-174">12</span></span></p></td>
<td><p><span data-ttu-id="4eec2-175">3 (VIP 당 1 개) + 12</span><span class="sxs-lookup"><span data-stu-id="4eec2-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eec2-176">5mb</span><span class="sxs-lookup"><span data-stu-id="4eec2-176">5</span></span></p></td>
<td><p><span data-ttu-id="4eec2-177">~</span><span class="sxs-lookup"><span data-stu-id="4eec2-177">15</span></span></p></td>
<td><p><span data-ttu-id="4eec2-178">3 (VIP 당 1) + 15</span><span class="sxs-lookup"><span data-stu-id="4eec2-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="4eec2-179">확장 통합 된 가장자리에 대 한 IP 주소 요구 사항 (모든 역할의 단일 IP 주소)</span><span class="sxs-lookup"><span data-stu-id="4eec2-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4eec2-180">풀 당 Edge 서버 수</span><span class="sxs-lookup"><span data-stu-id="4eec2-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="4eec2-181">필요한 IP 주소 수 Lync Server 2013 (DNS 부하 분산)</span><span class="sxs-lookup"><span data-stu-id="4eec2-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="4eec2-182">필요한 IP 주소 수 Lync Server 2013 (하드웨어 부하 분산)</span><span class="sxs-lookup"><span data-stu-id="4eec2-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4eec2-183">2</span><span class="sxs-lookup"><span data-stu-id="4eec2-183">2</span></span></p></td>
<td><p><span data-ttu-id="4eec2-184">2</span><span class="sxs-lookup"><span data-stu-id="4eec2-184">2</span></span></p></td>
<td><p><span data-ttu-id="4eec2-185">1 (VIP 당 1 개) + 2</span><span class="sxs-lookup"><span data-stu-id="4eec2-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eec2-186">3</span><span class="sxs-lookup"><span data-stu-id="4eec2-186">3</span></span></p></td>
<td><p><span data-ttu-id="4eec2-187">3</span><span class="sxs-lookup"><span data-stu-id="4eec2-187">3</span></span></p></td>
<td><p><span data-ttu-id="4eec2-188">1 (VIP 당 1 개) + 3</span><span class="sxs-lookup"><span data-stu-id="4eec2-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4eec2-189">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="4eec2-189">4</span></span></p></td>
<td><p><span data-ttu-id="4eec2-190">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="4eec2-190">4</span></span></p></td>
<td><p><span data-ttu-id="4eec2-191">1 (VIP 당 1 개) + 4</span><span class="sxs-lookup"><span data-stu-id="4eec2-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4eec2-192">5mb</span><span class="sxs-lookup"><span data-stu-id="4eec2-192">5</span></span></p></td>
<td><p><span data-ttu-id="4eec2-193">5mb</span><span class="sxs-lookup"><span data-stu-id="4eec2-193">5</span></span></p></td>
<td><p><span data-ttu-id="4eec2-194">1 (VIP 당 1 개) + 5</span><span class="sxs-lookup"><span data-stu-id="4eec2-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4eec2-195">토폴로지 선택에 대 한 기본 결정 사항은 고가용성 및 부하 분산입니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-195">The primary decision points for topology selection are high availability and load balancing.</span></span> <span data-ttu-id="4eec2-196">고가용성을 위한 요구 사항은 부하 분산 결정에 영향을 미칠 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-196">The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="4eec2-197">**고가용성**   높은 가용성을 필요로 하는 경우 풀에 Edge 서버를 두 개 이상 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="4eec2-198">단일 Edge 풀은 최대 12 대의 Edge 서버를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="4eec2-199">용량이 더 필요한 경우 여러 Edge 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="4eec2-200">일반적으로 지정 된 사용자 기반의 10%는 외부 액세스가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="4eec2-201">토폴로지 작성기를 사용 하면 단일 Edge 풀에서 최대 20 개의 Edge 서버를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="4eec2-202">풀에서 테스트 되 고 지원 되는 최대 Edge 서버 수는 12 개 보다 더 많은 수를 허용 하는 토폴로지 작성기는 단일 Edge 풀에 있는 12 개 이상의 Edge 서버에 대해 암시적인 지원으로 construed 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="4eec2-203">**하드웨어 부하 분산**   경계 외부 인터페이스에 대해 공개적으로 라우팅할 수 있는 IP 주소를 사용 하는 경우 Lync Server 2013 Edge 서버의 부하 분산에 대해 하드웨어 부하 분산이 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="4eec2-204">예를 들어 다음 응용 프로그램에 대해 장애 조치가 필요한 경우에이 방법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="4eec2-205">공용 메신저 연결</span><span class="sxs-lookup"><span data-stu-id="4eec2-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="4eec2-206">Microsoft Office Communications Server 2007 또는 Microsoft Office Communications Server 2007 R2를 실행 하는 회사와의 페더레이션</span><span class="sxs-lookup"><span data-stu-id="4eec2-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="4eec2-207">Exchange 2007 UM (통합 메시징) 또는 Exchange 2010 UM에 대 한 외부 액세스</span><span class="sxs-lookup"><span data-stu-id="4eec2-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="4eec2-208">Exchange 2010 SP1 이상에 대 한 DNS 부하 분산이 Exchange UM에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="4eec2-209">이러한 세 가지 응용 프로그램은 계속 작동 하지만 DNS 부하 분산을 인식 하지 않으며 풀의 첫 번째 Edge 서버에만 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-209">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool.</span></span> <span data-ttu-id="4eec2-210">해당 서버를 사용할 수 없는 경우에는 연결에 실패 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-210">If that server is unavailable, the connection will fail.</span></span> <span data-ttu-id="4eec2-211">예를 들어 페더레이션 트래픽 로드를 처리 하기 위해 풀에 여러 Edge 서버가 배포 되는 경우 한 액세스 프록시는 다른 사용자가 유휴 상태에 있는 동안 실제로 트래픽을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-211">For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="4eec2-212">Lync Server 2010 및 Microsoft Office 365를 사용 하 여 회사와 페더레이션 하는 경우 DNS 부하 분산을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4eec2-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="4eec2-213">대부분의 페더레이션 파트너가 Office Communications Server 2007 또는 Office Communications Server 2007 R2를 사용 하는 경우 성능이 크게 저하 된다는 점에 주의 하세요.</span><span class="sxs-lookup"><span data-stu-id="4eec2-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="4eec2-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="4eec2-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

