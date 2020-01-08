---
title: 사용자 모델을 사용 하 여 Lync Server 2013 용량 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b7db58e8c6f3e84f95a51ddd393ddca5ec18091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979724"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="97985-102">사용자 모델을 사용 하 여 Lync Server 2013에 대 한 용량 계획</span><span class="sxs-lookup"><span data-stu-id="97985-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97985-103">_**마지막으로 수정한 주제:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="97985-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="97985-104">이 섹션에서는 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)에서 설명한 사용에 따라 사이트에 필요한 서버 수 (해당 사이트의 사용자 수)에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="97985-105">테스트를 거친 하드웨어 플랫폼</span><span class="sxs-lookup"><span data-stu-id="97985-105">Tested Hardware Platform</span></span>

<span data-ttu-id="97985-106">이 섹션의 모든 성능 결과 및 배포 권장 사항은 다음 표에 설명 된 하드웨어를 실행 하는 서버에 대 한 성능 테스트를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="97985-107">비슷한 하드웨어를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="97985-108">덜 강력한 하드웨어를 사용 하는 경우 기능에 문제가 있거나 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="97985-109">이러한 하드웨어 권장 사항은 이전 버전의 Lync Server 보다 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="97985-110">성능 테스트에 사용 되는 하드웨어</span><span class="sxs-lookup"><span data-stu-id="97985-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97985-111">하드웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="97985-111">Hardware component</span></span></th>
<th><span data-ttu-id="97985-112">권장</span><span class="sxs-lookup"><span data-stu-id="97985-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97985-113">%</span><span class="sxs-lookup"><span data-stu-id="97985-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="97985-114">64 비트 듀얼 프로세서, 16 진수 코어, 2.26 ghz 이상</span><span class="sxs-lookup"><span data-stu-id="97985-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="97985-115">인텔 아이테니엄 프로세서는 Lync Server 서버 역할에 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97985-116">Memory</span><span class="sxs-lookup"><span data-stu-id="97985-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="97985-117">32 기가바이트 (GB)</span><span class="sxs-lookup"><span data-stu-id="97985-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97985-118">공간</span><span class="sxs-lookup"><span data-stu-id="97985-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97985-119">최소 72 GB의 사용 가능한 디스크 공간을 갖춘 8 대 이상의 1만-RPM 하드 디스크 드라이브.</span><span class="sxs-lookup"><span data-stu-id="97985-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="97985-120">두 개의 디스크에서 RAID 1을 사용 하 고 6 개는 RAID 10을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="97985-121">-또는</span><span class="sxs-lookup"><span data-stu-id="97985-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="97985-122">8 1만-RPM 기계 디스크 드라이브와 유사한 성능을 제공 하는 Ssd (고체 스테이트 드라이브).</span><span class="sxs-lookup"><span data-stu-id="97985-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97985-123">네트워크</span><span class="sxs-lookup"><span data-stu-id="97985-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97985-124">1 Gbps 이상의 듀얼 포트 네트워크 어댑터 (2 권장, 단일 MAC 주소 및 단일 IP 주소를 사용 하는 팀이 필요 함)</span><span class="sxs-lookup"><span data-stu-id="97985-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="97985-125">결과 요약</span><span class="sxs-lookup"><span data-stu-id="97985-125">Summary of Results</span></span>

<span data-ttu-id="97985-126">다음 표에는 이러한 권장 사항이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97985-127">서버 역할</span><span class="sxs-lookup"><span data-stu-id="97985-127">Server role</span></span></th>
<th><span data-ttu-id="97985-128">지원 되는 최대 사용자 수</span><span class="sxs-lookup"><span data-stu-id="97985-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97985-129">12 개의 프런트 엔드 서버와 1 백 엔드 서버 또는 미러 백 엔드 서버 쌍이 있는 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="97985-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="97985-130">8만 고유 사용자에 게 동시에 로그인 하 고 50%의 여러 지점 (MPOP)이 비 모바일 인스턴스를 표시 하 고, 사용자의 40%가 총 152000 끝점에 대해 이동성을 사용 하도록 설정 했습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97985-131">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="97985-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="97985-132">프런트 엔드 풀에서 제공 하는 A/V 회의 서비스는 최대 컨퍼런스 크기인 250 사용자로 간주 되는 풀의 컨퍼런스와 한 번에 실행 되는 이러한 대량 컨퍼런스만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="97985-133">또한, 대형 회의를 호스트할 프런트 엔드 서버 두 대와 별도의 프런트 엔드 풀을 배포 하 여 250와 1000 사용자 간에 대규모 회의를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="97985-134">자세한 내용은 <A href="lync-server-2013-supporting-large-meetings.md">Lync Server 2013를 사용 하 여 대형 모임 지원을</A>참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97985-135">1에 지 서버</span><span class="sxs-lookup"><span data-stu-id="97985-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="97985-136">12000 동시 원격 사용자</span><span class="sxs-lookup"><span data-stu-id="97985-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97985-137">디렉터 1 개</span><span class="sxs-lookup"><span data-stu-id="97985-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="97985-138">12000 동시 원격 사용자</span><span class="sxs-lookup"><span data-stu-id="97985-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97985-139">모니터링 및 보관</span><span class="sxs-lookup"><span data-stu-id="97985-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="97985-140">Lync Server 2013에서는 이제 각 프런트 엔드 서버에서 별도의 서버 역할이 아니라 모니터링 및 보관 프런트 엔드 서비스를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="97985-141">각 모니터링 및 보관에는 여전히 자체 데이터베이스 저장소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="97985-142">Exchange 2013를 실행 하는 경우 전용 SQL 데이터베이스가 아닌 Exchange에 보관 데이터를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97985-143">하나의 중재 서버</span><span class="sxs-lookup"><span data-stu-id="97985-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="97985-144">프런트 엔드 서버를 사용 하는 중재 서버 collocated 풀의 모든 프런트 엔드 서버에서 실행 되며 풀의 사용자에 게 충분 한 용량을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="97985-145">독립 실행형 중재 서버의 경우이 항목의 뒷부분에 나오는 "중재 서버" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97985-146">1 개 표준 버전 서버</span><span class="sxs-lookup"><span data-stu-id="97985-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="97985-147">스탠더드 버전 서버를 사용 하 여 사용자를 호스트 하는 경우, <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013에서 고가용성 및 재해 복구 계획</a>의 권장 사항을 사용 하는 두 서버를 항상 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="97985-148">쌍의 각 서버는 최대 2500 사용자를 호스트할 수 있으며, 한 서버가 실패 하는 경우 나머지 서버는 장애 조치 시나리오에서 5000 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="97985-149">배포에 상당한 양의 오디오 또는 비디오 소통량이 포함 되어 있는 경우 서버에 2500 사용자가 넘는 경우 서버의 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="97985-150">이 경우에는 표준 버전 서버를 추가 하거나 Lync Server Enterprise Edition으로 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="97985-151">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="97985-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97985-152">스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="97985-153">프런트 엔드 풀에서 풀의 모든 서버에 대 한 하이퍼 스레드를 사용 하도록 설정 하 고 서버 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 하 여 풀에 있는 모든 6660 사용자에 대해 프런트 엔드 서버를 하나씩 보유 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="97985-154">풀의 모든 서버에서 하이퍼 스레드를 사용 하는 경우 한 프런트 엔드 풀의 최대 사용자 수는 8만입니다.</span><span class="sxs-lookup"><span data-stu-id="97985-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="97985-155">사이트에 8만 명 이상의 사용자가 있는 경우 두 개 이상의 프런트 엔드 풀을 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="97985-156">프런트 엔드 풀의 사용자 수를 고려 하는 경우이 프론트 엔드 풀과 연결 된 지점에서 Survivable Branch 기기 및 Survivable Branch 서버에 속한 사용자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="97985-157">활성 서버를 사용할 수 없는 경우 해당 연결이 자동으로 풀의 다른 서버로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97985-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="97985-158">예를 들어 3만 사용자와 다섯 개의 프런트 엔드 서버가 있는 경우 서버를 사용할 수 없는 경우에는 6000 사용자의 연결을 다른 4 개의 서버로 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="97985-159">나머지 4 대의 서버에는 각각 7500 사용자가 있으며 권장 보다 더 큽니다.</span><span class="sxs-lookup"><span data-stu-id="97985-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="97985-160">3만 사용자를 위해 6 개의 프런트 엔드 서버로 시작 하 고 그 이후에 한 번만 사용할 수 있게 되 면 총 5000 사용자가 나머지 5 대 서버로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="97985-161">이 다섯 개의 서버는 각각 호스트 6000 사용자 이며 권장 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="97985-162">프런트 엔드 풀의 최대 사용자 수는 8만입니다.</span><span class="sxs-lookup"><span data-stu-id="97985-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="97985-163">풀의 최대 프런트 엔드 서버 수는 12 개입니다.</span><span class="sxs-lookup"><span data-stu-id="97985-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="97985-164">8만 사용자가 있는 프런트 엔드 풀의 경우, [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 따르는 일반적인 배포의 12 개의 프런트 엔드 서버는 성능에 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="97985-165">재해 복구 장애 조치 (failover)를 지원 하도록 설계 된 배포 4만는 두 개의 쌍으로 이루어진 각 프런트 엔드 풀에 호스트 될 수 있으며, 각 풀의 사용자에 게 하나의 풀을 사용할 수 있는 충분 한 프런트 엔드 서버가 있는 것으로 가정 합니다. (으)로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="97985-166">특정 프런트 엔드 풀에의 한 좋은 성능으로 지원 되는 사용자 수는 다음과 같은 이유로 이러한 번호와 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="97985-167">프런트 엔드 서버용 하드웨어가 [Lync server 2013의 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)에 대 한 권장 사항을 충족 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="97985-168">조직의 사용이 훨씬 더 많은 회의 트래픽과 같은 사용자 모델과 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="97985-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="97985-169">Lync Server 2013에서 현재 상태 데이터베이스는 백 엔드 서버에서 호스트 되는 Lync Server 2010와는 달리 프런트 엔드 서버에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="97985-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="97985-170">이는 프런트 엔드 서버에서 호스트 되는 사용자 수에 관계 없이 프런트 엔드 서버의 디스크 성능 및 용량이이 섹션의 앞부분에 나열 된 권장 사항 및 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013의 서버 하드웨어 플랫폼</A>에서 노출 되지 않아야 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="97985-171">다음 표에서는 [Lync Server 2013의 사용자](lync-server-2013-user-models.md)모델에 정의 된 대로 사용자 모델에 따라 IM 및 현재 상태에 대 한 평균 대역폭을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97985-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97985-172">사용자 당 평균 대역폭</span><span class="sxs-lookup"><span data-stu-id="97985-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="97985-173">6660 사용자가 있는 프런트 엔드 서버 당 대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="97985-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97985-174">1.3 Kpbs</span><span class="sxs-lookup"><span data-stu-id="97985-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="97985-175">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="97985-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="97985-176">프런트 엔드 서버에서 배치 된 A/V 회의 및 조정 서버 기능의 미디어 성능을 개선 하려면 프런트 엔드 서버의 네트워크 어댑터에서 수신측 배율 (RSS)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="97985-177">RSS를 사용 하면 서버의 여러 프로세서가 들어오는 패킷을 병렬로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="97985-178">자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>"Windows Server 2008에서 수신측 배율 향상 기능"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="97985-179">RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="97985-180">회의 최대값</span><span class="sxs-lookup"><span data-stu-id="97985-180">Conferencing Maximums</span></span>

<span data-ttu-id="97985-181">풀의 사용자 5%가 한 번에 회의에 있을 수 있는 사용자 모델의 경우, 8만 사용자 풀은 한 번에 회의에 4000 사용자를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="97985-182">이러한 회의는 미디어 (일부 IM 전용, 오디오가 있는 일부 메신저, 일부 오디오/비디오 등)와 참가자 수를 혼합 하 여 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="97985-183">실제 회의 수에는 제한이 없으며 실제 사용량에 따라 실제 성능이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97985-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="97985-184">예를 들어 조직에 사용자 모델에 포함 된 것 보다 더 많은 혼합 모드 회의가 있는 경우이 문서의 권장 사항 보다 더 많은 프런트 엔드 서버 또는 A/V 회의 서버를 배포 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="97985-185">사용자 모델의 가정에 대 한 자세한 내용은 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="97985-186">사용자를 호스트 하는 일반 Lync Server 2013 프런트 엔드 풀에서 호스트 하는 지원 되는 최대 컨퍼런스 크기 250입니다.</span><span class="sxs-lookup"><span data-stu-id="97985-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="97985-187">250 사용자 회의가 진행 되는 동안에도 풀 사용자의 총 5%가 동시에 진행 되는 것을 비롯 한 다른 컨퍼런스도 여전히 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97985-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="97985-188">예를 들어 12 프런트 엔드 서버와 8만 사용자의 풀에서 250 사용자 회의가 발생 하는 동안에는 Lync Server가 소규모 회의에 참여 하는 3750 다른 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="97985-189">Lync Server는 프런트 엔드 풀 또는 Standard Edition server에 속한 사용자 수와 관계 없이 250-사용자 회의를 호스트 하는 동일한 풀이나 서버에서 작은 회의에 참여 하는 최소 125의 다른 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="97985-190">250와 1000 사용자 간에 회의를 설정 하려면 해당 회의를 호스팅하기 위해 별도의 프런트 엔드 풀을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="97985-191">이 프런트 엔드 풀은 사용자를 호스팅하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="97985-192">자세한 내용은 [Lync Server 2013를 사용 하 여 대형 모임 지원을](lync-server-2013-supporting-large-meetings.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="97985-193">조직에 사용자 모델에 사용 되는 것 보다 더 많은 혼합 모드 회의가 있는 경우이 문서의 권장 사항 보다 더 많은 프런트 엔드 서버를 배포 해야 할 수 있습니다 (최대 12fes).</span><span class="sxs-lookup"><span data-stu-id="97985-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="97985-194">사용자 모델의 가정에 대 한 자세한 내용은 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="97985-195">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="97985-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97985-196">스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="97985-197">사이트에 동시에 액세스 하는 모든 12000 원격 사용자에 대해 하나의 Edge 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="97985-198">최소한 고가용성을 위해 두 개의 Edge 서버를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="97985-199">이러한 권장 사항은 Edge 서버의 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="97985-200">Edge 서버의 사용자 수를 고려 하는 경우이 사이트의 프런트 엔드 풀과 연결 된 지점에서 Survivable Branch 기기 및 Survivable Branch 서버에 속한 사용자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97985-201">Edge 서버에서 A/V 회의에 대 한 서비스의 성능을 향상 시키려면 Edge 서버의 네트워크 어댑터에서 수신측 배율 (RSS)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="97985-202">RSS를 사용 하면 서버의 여러 프로세서가 들어오는 패킷을 병렬로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="97985-203">자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>"Windows Server 2008에서 수신측 배율 향상 기능"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="97985-204">RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="97985-205">Director</span><span class="sxs-lookup"><span data-stu-id="97985-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97985-206">스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="97985-207">디렉터 서버 역할을 배포 하는 경우 사이트에 동시에 액세스 하는 모든 12000 원격 사용자에 대해 하나의 디렉터를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="97985-208">최소한 고가용성을 위해 2 개의 디렉터를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="97985-209">이러한 권장 사항은 Edge 서버의 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="97985-210">디렉터에 대 한 사용자 수를 고려 하는 경우이 사이트의 프런트 엔드 풀에 연결 된 지점에서 Survivable Branch 기기 및 Survivable Branch 서버에 속한 사용자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="97985-211">중재 서버</span><span class="sxs-lookup"><span data-stu-id="97985-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="97985-212">스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="97985-213">프런트 엔드 서버를 사용 하는 중재 서버를 collocate 풀의 모든 프런트 엔드 서버에서 중재 서버가 실행 되며 풀의 사용자에 게 충분 한 용량을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="97985-214">독립 실행형 중재 서버 풀을 배포 하는 경우에는 조정 서버에 사용 되는 하드웨어, 보유 한 VoIP 사용자 수, 각 중재 서버 풀에 있는 게이트웨이 피어 수를 비롯 한 다양 한 요인에 따라 배포할 중재 서버 수가 달라 집니다. 해당 게이트웨이를 통해 사용 하는 시간 트래픽 및 중재 서버를 우회 하는 미디어로의 통화 백분율이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97985-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="97985-215">다음 표에서는 중재 서버에 대 한 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 의 요구 사항을 충족 하 고 하이퍼 스레드를 사용 하도록 설정 되어 있다고 가정 하 여 중재 서버가 처리할 수 있는 동시 호출 횟수에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="97985-216">중재 서버 확장성에 대 한 자세한 내용은 [lync server 2013의 중재 서버에 대 한](lync-server-2013-deployment-guidelines-for-mediation-server.md) [lync Server 2013 및 배포 지침에 대 한 음성 사용량 및 트래픽 예측](lync-server-2013-estimating-voice-usage-and-traffic.md) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="97985-217">다음 표에는 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)에 요약 된 사용 방법이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="97985-218">독립 실행형 중재 서버 용량: 70% 내부 사용자, 우회 되지 않는 외부 사용자 30% (중재 서버에서 수행 하는 미디어 코드 변환)</span><span class="sxs-lookup"><span data-stu-id="97985-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97985-219">서버 하드웨어</span><span class="sxs-lookup"><span data-stu-id="97985-219">Server hardware</span></span></th>
<th><span data-ttu-id="97985-220">최대 통화 수</span><span class="sxs-lookup"><span data-stu-id="97985-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="97985-221">최대 T1 회선 수</span><span class="sxs-lookup"><span data-stu-id="97985-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="97985-222">최대 E1 선 수</span><span class="sxs-lookup"><span data-stu-id="97985-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97985-223">듀얼 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU (32 GB 메모리와 듀얼 포트 네트워크 어댑터 카드)를 사용 하 여 <strong>하이퍼 스레딩 기능을 사용할 수 없습니다</strong>.</span><span class="sxs-lookup"><span data-stu-id="97985-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="97985-224">1100</span><span class="sxs-lookup"><span data-stu-id="97985-224">1100</span></span></p></td>
<td><p><span data-ttu-id="97985-225">46</span><span class="sxs-lookup"><span data-stu-id="97985-225">46</span></span></p></td>
<td><p><span data-ttu-id="97985-226">35</span><span class="sxs-lookup"><span data-stu-id="97985-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97985-227">듀얼 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU, 32 GB 메모리 및 1 개의 듀얼 포트 네트워크 어댑터 카드.</span><span class="sxs-lookup"><span data-stu-id="97985-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="97985-228">1500</span><span class="sxs-lookup"><span data-stu-id="97985-228">1500</span></span></p></td>
<td><p><span data-ttu-id="97985-229">63</span><span class="sxs-lookup"><span data-stu-id="97985-229">63</span></span></p></td>
<td><p><span data-ttu-id="97985-230">47</span><span class="sxs-lookup"><span data-stu-id="97985-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="97985-231">32 GB의 메모리가 있는 서버는 성능 테스트에 사용 되지만, 16 GB 메모리가 있는 서버는 독립 실행형 중재 서버에 대해 지원 되며이 표에 표시 된 성능을 제공 하기에 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="97985-232">서버 용량 조정 (프런트 엔드 서버를 사용 하는 중재 서버 Collocated) 70% 내부 사용자, 30% 외부 사용자, 바이패스 되지 않은 통화 용량 (중재 서버에서 수행 하는 미디어 처리)</span><span class="sxs-lookup"><span data-stu-id="97985-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97985-233">서버 하드웨어</span><span class="sxs-lookup"><span data-stu-id="97985-233">Server hardware</span></span></th>
<th><span data-ttu-id="97985-234">최대 통화 수</span><span class="sxs-lookup"><span data-stu-id="97985-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97985-235">32 GB 메모리 및 2 개의 1GB 네트워크 어댑터 카드가 있는 듀얼 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU.</span><span class="sxs-lookup"><span data-stu-id="97985-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="97985-236">150</span><span class="sxs-lookup"><span data-stu-id="97985-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="97985-237">프런트 엔드 서버는 해당 사용자에 게 있는 6600 사용자에 대 한 다른 기능 및 기능을 처리 해야 하 고 음성 통화에 필요한 코드 변환 외에도이 숫자가 독립 실행형 중재 서버의 숫자 보다 훨씬 작습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="97985-238">중재 서버의 성능을 향상 시키려면 중재 서버의 네트워크 어댑터에서 수신측 배율 (RSS)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="97985-239">RSS를 사용 하면 서버의 여러 프로세서가 들어오는 패킷을 병렬로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="97985-240">자세한 내용은에서 <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>"Windows Server 2008에서 수신측 배율 향상 기능"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="97985-241">RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="97985-242">백 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="97985-242">Back End Server</span></span>

<span data-ttu-id="97985-243">Lync Server 2013에서 현재 상태 데이터베이스는 백 엔드 서버 대신 프런트 엔드 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="97985-244">이로 인해 프런트 엔드 서버의 하드웨어 요구 사항에 해당 하는 Lync Server 2013의 각 백 엔드 서버에 대 한 요구 사항이 훨씬 더 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="97985-245">백 엔드 서버가 25 개 디스크를 사용 하 여 훨씬 더 높은 성적 서버 여야 하는 Lync Server 2010와 비교해 보세요.</span><span class="sxs-lookup"><span data-stu-id="97985-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="97985-246">그러나 백 엔드 서버의 작업 부하는 여전히이 섹션의 앞에 나열 된 하드웨어 권장 사항과 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)에서 수행 하지 않도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97985-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="97985-247">백 엔드 서버의 가용성을 높이기 위해 서버 미러링을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="97985-248">자세한 내용은 [Lync server 2013에서 백 엔드 서버의](lync-server-2013-back-end-server-high-availability.md)고가용성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="97985-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="97985-249">모니터링 및 보관</span><span class="sxs-lookup"><span data-stu-id="97985-249">Monitoring and Archiving</span></span>

<span data-ttu-id="97985-250">Lync Server 2013에서 모니터링 또는 보관을 배포 하는 경우 이러한 서비스의 프런트 엔드 기능은 별도의 서버 역할 대신 프런트 엔드 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97985-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="97985-251">각 모니터링 및 보관은 백 엔드 저장소와는 별도로 자체 데이터베이스 저장소를 계속 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="97985-252">또는 Exchange 2013을 배포한 경우 전용 SQL 저장소 대신 Exchange에 인스턴트 메시지 보관 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="97985-253">다음 표에는 데이터 모니터링 및 아카이빙에 대해 일일 사용자 당 얼마나 많은 데이터베이스 저장소가 필요한가 표시 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="97985-254"><strong>CDR (모니터링)</strong></span><span class="sxs-lookup"><span data-stu-id="97985-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="97985-255"><strong>체감 품질 (모니터링)</strong></span><span class="sxs-lookup"><span data-stu-id="97985-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="97985-256"><strong>보관</strong></span><span class="sxs-lookup"><span data-stu-id="97985-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97985-257">일일 사용자 당 필요한 디스크 공간</span><span class="sxs-lookup"><span data-stu-id="97985-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="97985-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="97985-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="97985-259">28KB</span><span class="sxs-lookup"><span data-stu-id="97985-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="97985-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="97985-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="97985-261">Microsoft는 성능 테스트 중에 모니터링 및 보관을 위해 데이터베이스 서버에 대해 다음 표의 하드웨어를 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="97985-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="97985-262">테스트는 각각 8만 사용자를 포함 하는 두 개의 프런트 엔드 풀의 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="97985-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="97985-263">모니터링 및 보관 성능 테스트에 사용 되는 하드웨어</span><span class="sxs-lookup"><span data-stu-id="97985-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97985-264">하드웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="97985-264">Hardware component</span></span></th>
<th><span data-ttu-id="97985-265">권장</span><span class="sxs-lookup"><span data-stu-id="97985-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97985-266">%</span><span class="sxs-lookup"><span data-stu-id="97985-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="97985-267">64 비트 듀얼 프로세서, 16 진수 코어, 2.26 ghz 이상</span><span class="sxs-lookup"><span data-stu-id="97985-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97985-268">Memory</span><span class="sxs-lookup"><span data-stu-id="97985-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="97985-269">48 기가바이트 (GB)</span><span class="sxs-lookup"><span data-stu-id="97985-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97985-270">공간</span><span class="sxs-lookup"><span data-stu-id="97985-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="97985-271">25 1만-RPM 하드 디스크 드라이브, 각 디스크에 300 GB, 다음 구성</span><span class="sxs-lookup"><span data-stu-id="97985-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97985-272"><strong>구동</strong></span><span class="sxs-lookup"><span data-stu-id="97985-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="97985-273"><strong>RAID 구성</strong></span><span class="sxs-lookup"><span data-stu-id="97985-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="97985-274"><strong>디스크 수</strong></span><span class="sxs-lookup"><span data-stu-id="97985-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97985-275">CDR, 체감 품질, 데이터베이스 데이터 파일을 단일 드라이브에 보관</span><span class="sxs-lookup"><span data-stu-id="97985-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="97985-276">1 + 0</span><span class="sxs-lookup"><span data-stu-id="97985-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="97985-277">16</span><span class="sxs-lookup"><span data-stu-id="97985-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97985-278">CDR 데이터베이스 로그 파일</span><span class="sxs-lookup"><span data-stu-id="97985-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="97985-279">1</span><span class="sxs-lookup"><span data-stu-id="97985-279">1</span></span></p></td>
<td><p><span data-ttu-id="97985-280">2</span><span class="sxs-lookup"><span data-stu-id="97985-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97985-281">체감 품질 데이터베이스 로그 파일</span><span class="sxs-lookup"><span data-stu-id="97985-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="97985-282">1</span><span class="sxs-lookup"><span data-stu-id="97985-282">1</span></span></p></td>
<td><p><span data-ttu-id="97985-283">2</span><span class="sxs-lookup"><span data-stu-id="97985-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97985-284">데이터베이스 로그 파일 보관</span><span class="sxs-lookup"><span data-stu-id="97985-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="97985-285">1</span><span class="sxs-lookup"><span data-stu-id="97985-285">1</span></span></p></td>
<td><p><span data-ttu-id="97985-286">2</span><span class="sxs-lookup"><span data-stu-id="97985-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97985-287">네트워크</span><span class="sxs-lookup"><span data-stu-id="97985-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="97985-288">1 Gbps 이상의 듀얼 포트 네트워크 어댑터 (2 권장, 단일 MAC 주소 및 단일 IP 주소를 사용 하는 팀이 필요 함)</span><span class="sxs-lookup"><span data-stu-id="97985-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="97985-289">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="97985-289">In This Section</span></span>

  - [<span data-ttu-id="97985-290">Lync Server 2013의 음성 사용량 및 트래픽 예상</span><span class="sxs-lookup"><span data-stu-id="97985-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="97985-291">Lync Server 2013의 중재 서버 배포 지침</span><span class="sxs-lookup"><span data-stu-id="97985-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

