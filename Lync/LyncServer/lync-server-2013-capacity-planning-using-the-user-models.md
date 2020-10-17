---
title: 사용자 모델을 사용 하는 Lync Server 2013 용량 계획
description: Lync Server 2013에서는 사용자 모델을 사용 하 여 용량을 계획 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b710f7ec88dd75c872d704f2169fa2f161fc186
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544414"
---
# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="fd750-103">사용자 모델을 사용 하는 Lync Server 2013에 대 한 용량 계획</span><span class="sxs-lookup"><span data-stu-id="fd750-103">Capacity planning for Lync Server 2013 using the user models</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd750-104">_**마지막으로 수정 된 항목:** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="fd750-104">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="fd750-105">이 섹션에서는 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)에 설명 된 사용에 따라 해당 사이트의 사용자 수에 대해 사이트에서 필요한 서버 수에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-105">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="fd750-106">테스트를 거친 하드웨어 플랫폼</span><span class="sxs-lookup"><span data-stu-id="fd750-106">Tested Hardware Platform</span></span>

<span data-ttu-id="fd750-107">이 섹션의 모든 성능 결과 및 배포 권장 사항은 다음 표에 설명 된 하드웨어를 실행 하는 서버에 대 한 성능 테스트를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-107">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="fd750-108">비슷한 하드웨어를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-108">We recommend that you use similar hardware.</span></span> <span data-ttu-id="fd750-109">덜 강력한 하드웨어를 사용 하는 경우에는 기능에 문제가 있거나 성능이 저하 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-109">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="fd750-110">이러한 하드웨어 권장 사항은 이전 버전의 Lync Server 보다 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-110">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="fd750-111">성능 테스트에 사용 되는 하드웨어</span><span class="sxs-lookup"><span data-stu-id="fd750-111">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd750-112">하드웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fd750-112">Hardware component</span></span></th>
<th><span data-ttu-id="fd750-113">권장</span><span class="sxs-lookup"><span data-stu-id="fd750-113">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd750-114">CPU</span><span class="sxs-lookup"><span data-stu-id="fd750-114">CPU</span></span></p></td>
<td><p><span data-ttu-id="fd750-115">64비트 이중 프로세서, 6중 코어, 2.26GHz 이상</span><span class="sxs-lookup"><span data-stu-id="fd750-115">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="fd750-116">Lync Server 서버 역할에는 Intel Itanium 프로세서가 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-116">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd750-117">메모리</span><span class="sxs-lookup"><span data-stu-id="fd750-117">Memory</span></span></p></td>
<td><p><span data-ttu-id="fd750-118">32GB</span><span class="sxs-lookup"><span data-stu-id="fd750-118">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd750-119">공간이</span><span class="sxs-lookup"><span data-stu-id="fd750-119">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fd750-120">72 GB 이상의 사용 가능한 디스크 공간이 있는 1만-RPM 하드 디스크 드라이브 8 개 이상</span><span class="sxs-lookup"><span data-stu-id="fd750-120">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="fd750-121">이 중 두 개는 RAID 1을 사용하고 6개는 RAID 10을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-121">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="fd750-122">- 사용자나</span><span class="sxs-lookup"><span data-stu-id="fd750-122">- OR -</span></span></p></li>
<li><p><span data-ttu-id="fd750-123">8개의 10,000 RPM 기계식 디스크 드라이브와 유사한 성능을 제공하는 SDD(반도체 드라이브)</span><span class="sxs-lookup"><span data-stu-id="fd750-123">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd750-124">네트워크</span><span class="sxs-lookup"><span data-stu-id="fd750-124">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fd750-125">1개의 이중 포트 네트워크 어댑터, 1Gbps 이상(2개 권장, 단일 MAC 주소와 단일 IP 주소를 사용하여 팀으로 구성해야 함)</span><span class="sxs-lookup"><span data-stu-id="fd750-125">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="fd750-126">결과 요약</span><span class="sxs-lookup"><span data-stu-id="fd750-126">Summary of Results</span></span>

<span data-ttu-id="fd750-127">다음 표에는 이러한 권장 사항이 요약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-127">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd750-128">서버 역할</span><span class="sxs-lookup"><span data-stu-id="fd750-128">Server role</span></span></th>
<th><span data-ttu-id="fd750-129">지원 되는 최대 사용자 수</span><span class="sxs-lookup"><span data-stu-id="fd750-129">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd750-130">12 개의 프런트 엔드 서버와 하나의 백 엔드 서버 또는 미러링된 백 엔드 서버 쌍의 프런트 엔드 풀</span><span class="sxs-lookup"><span data-stu-id="fd750-130">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="fd750-131">8만 사용자가 동시에 로그인 하 고 50%에 해당 하는 MPOP (여러 지점)을 포함 40 하 여 모바일이 아닌 인스턴스를 표시 하 고, 총 152000 끝점에 대 한 모바일 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-131">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd750-132">A/V 회의</span><span class="sxs-lookup"><span data-stu-id="fd750-132">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="fd750-133">프런트 엔드 풀에서 제공 하는 A/V 회의 서비스는 최대 회의 크기인 250 명의 사용자만을 지원 하 고 한 번에 실행 되는 이러한 대규모 회의만 있으면 서 풀의 회의를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-133">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="fd750-134">또한 대규모 회의를 호스트 하기 위해 두 개의 프런트 엔드 서버를 포함 하는 별도의 프런트 엔드 풀을 배포 하 여 250와 1000 사용자 간의 대규모 회의를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-134">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="fd750-135">자세한 내용은 <A href="lync-server-2013-supporting-large-meetings.md">Lync Server 2013을 사용 하 여 대규모 모임 지원</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd750-135">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd750-136">1 개의에 지 서버</span><span class="sxs-lookup"><span data-stu-id="fd750-136">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="fd750-137">12000 동시 원격 사용자</span><span class="sxs-lookup"><span data-stu-id="fd750-137">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd750-138">디렉터 1 개</span><span class="sxs-lookup"><span data-stu-id="fd750-138">One Director</span></span></p></td>
<td><p><span data-ttu-id="fd750-139">12000 동시 원격 사용자</span><span class="sxs-lookup"><span data-stu-id="fd750-139">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd750-140">모니터링 및 보관</span><span class="sxs-lookup"><span data-stu-id="fd750-140">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="fd750-141">Lync Server 2013에서는 모니터링 및 보관 프런트 엔드 서비스가 별도의 서버 역할이 아닌 각 프런트 엔드 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-141">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="fd750-142">각 모니터링 및 보관은 여전히 자체 데이터베이스 저장소를 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-142">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="fd750-143">Exchange 2013도 실행 하는 경우 전용 SQL 데이터베이스가 아닌 Exchange에 보관 데이터를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-143">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd750-144">중재 서버 1 개</span><span class="sxs-lookup"><span data-stu-id="fd750-144">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fd750-145">프런트 엔드 서버를 사용 하는 중재 서버 배치 된 풀의 모든 프런트 엔드 서버에서 실행 되며 풀의 사용자에 게 충분 한 용량을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-145">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="fd750-146">독립 실행형 중재 서버에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 "중재 서버" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd750-146">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd750-147">Standard Edition 서버 1 대</span><span class="sxs-lookup"><span data-stu-id="fd750-147">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="fd750-148">Standard Edition 서버를 사용 하 여 사용자를 호스트 하는 경우 항상 <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013에서 고가용성 및 재해 복구 계획</a>의 권장 사항을 사용 하 여 두 서버를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-148">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="fd750-149">쌍의 각 서버에서 최대 2500 명의 사용자를 호스팅할 수 있으며, 한 서버가 실패 하면 장애 조치 (failover) 시나리오에서 나머지 서버가 5000 사용자를 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-149">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="fd750-150">배포에 많은 양의 오디오 또는 비디오 트래픽이 포함 되는 경우 서버에 대해 서버 성능에 2500 명 넘게 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-150">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="fd750-151">이 경우 Standard Edition 서버를 더 추가 하거나 Lync Server Enterprise Edition으로 이동 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-151">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="fd750-152">Front End Server(프런트 엔드 서버)</span><span class="sxs-lookup"><span data-stu-id="fd750-152">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd750-153">스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-153">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="fd750-154">프런트 엔드 풀에서는 풀에 있는 모든 서버에 대해 하이퍼스레딩을 사용 하도록 설정 하 고 서버 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 하 고 풀에 있는 모든 6660 사용자에 대해 프런트 엔드 서버를 하나씩 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-154">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="fd750-155">풀의 모든 서버에서 하이퍼스레딩을 사용 하는 경우 한 프런트 엔드 풀의 최대 사용자 수는 8만입니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-155">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="fd750-156">사이트에 사용자가 8만 명 이상인 경우 프런트 엔드 풀을 두 개 이상 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-156">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="fd750-157">프런트 엔드 풀의 사용자 수를 고려해 야 하는 경우이 프런트 엔드 풀과 연결 된 지점에 있는 Sba (survivable Branch 기기 및 Sba (survivable 분기 서버에 있는 사용자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-157">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="fd750-158">활성 서버를 사용할 수 없으면 해당 연결이 풀의 다른 서버로 자동 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-158">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="fd750-159">예를 들어 사용자가 5 명이 고 프런트 엔드 서버가 다섯 대 3만 있는 경우 한 서버를 사용할 수 없는 경우 6000 사용자의 연결을 다른 4 개의 서버로 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-159">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="fd750-160">나머지 4 개의 서버에는 각각 7500 명의 사용자가 있으므로 권장 되는 것 보다 더 큰 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-160">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="fd750-161">예를 들어, 3만 사용자에 대해 6 개의 프런트 엔드 서버를 시작한 후 그 중 하나를 사용할 수 없게 되 면 총 5000 명의 사용자가 나머지 5 대 서버로 이동 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-161">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="fd750-162">이러한 5 개의 서버는 각 호스트 6000 사용자를 권장 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-162">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="fd750-163">프런트 엔드 풀의 최대 사용자 수는 8만입니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-163">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="fd750-164">풀의 최대 프런트 엔드 서버 수는 12입니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-164">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="fd750-165">8만 명의 사용자가 포함 된 프런트 엔드 풀의 경우 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 따르는 일반적인 배포에서 12 개의 프런트 엔드 서버는 성능에 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-165">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="fd750-166">재해 복구 장애 조치 (failover)를 지원 하도록 설계 4만 된 배포에서는 각 풀이 두 개의 쌍으로 된 프런트 엔드 풀 각각에 호스트 될 수 있는데,이 경우 각 풀에는 두 풀의 사용자를 둘 다 포함할 프런트 엔드 서버가 충분 한 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-166">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="fd750-167">특정 프런트 엔드 풀에서 양호한 성능을 사용 하 여 지원 되는 사용자 수는 다음과 같은 이유로 인해 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-167">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="fd750-168">프런트 엔드 서버에 대 한 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-168">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="fd750-169">조직의 사용량은 훨씬 더 많은 회의 트래픽 등 사용자 모델과 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-169">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fd750-170">Lync Server 2013에서는 현재 상태 데이터베이스가 백 엔드 서버에서 호스트 되는 Lync Server 2010와는 달리 프런트 엔드 서버에 호스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-170">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="fd750-171">즉, 프런트 엔드 서버에서 호스팅하는 사용자 수에 관계 없이 프런트 엔드 서버의 디스크 성능 및 용량을이 섹션의 앞부분과 <A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 용 서버 하드웨어 플랫폼</A>의 권장 사항에 따라 노출 해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-171">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="fd750-172">다음 표에서는 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)에 정의 된 대로 사용자 모델에 따라 IM 및 현재 상태에 대 한 평균 대역폭을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-172">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd750-173">사용자 당 평균 대역폭</span><span class="sxs-lookup"><span data-stu-id="fd750-173">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="fd750-174">6660 명의 사용자가 있는 프런트 엔드 서버당 대역폭 요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd750-174">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd750-175">1.3 Kpbs</span><span class="sxs-lookup"><span data-stu-id="fd750-175">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="fd750-176">13mbps</span><span class="sxs-lookup"><span data-stu-id="fd750-176">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fd750-177">프런트 엔드 서버에서 공동 위치 A/V 회의 및 중재 서버 기능의 미디어 성능을 개선 하려면 프런트 엔드 서버의 네트워크 어댑터에 대해 수신측 확장 (RSS)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-177">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="fd750-178">RSS를 사용 하면 서버의 여러 프로세서에서 들어오는 패킷을 병렬로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-178">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="fd750-179">자세한 내용은의 "Windows Server 2008에서 수신측 확장 향상 기능"을 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd750-179">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="fd750-180">RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd750-180">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="fd750-181">회의 최대값</span><span class="sxs-lookup"><span data-stu-id="fd750-181">Conferencing Maximums</span></span>

<span data-ttu-id="fd750-182">사용자 모델에서 풀 사용자의 5%가 언제 든 지 회의에 참석할 수 있는 경우 한 번에 8만 명의 사용자에 게 4000 명의 사용자가 회의에 참가 하는 것을 겪을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-182">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="fd750-183">이러한 회의는 미디어 (일부 IM 전용, 오디오를 포함 하는 일부 IM, 일부 오디오/비디오 등)와 참가자 수를 혼합 하 여 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-183">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="fd750-184">실제로 허용 되는 실제 회의 수에 대 한 제한은 없으며 실제 사용 방법에 따라 실제 성능이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-184">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="fd750-185">예를 들어 조직에서 사용자 모델에 포함 된 것 보다 많은 혼합 모드를 사용 하는 경우에는이 문서의 권장 사항 보다 더 많은 프런트 엔드 서버 또는 A/V 회의 서버를 배포 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-185">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="fd750-186">사용자 모델의 가정에 대 한 자세한 내용은 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd750-186">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="fd750-187">사용자가 호스트 하는 일반 Lync Server 2013 프런트 엔드 풀에서 호스트 하는 지원 되는 최대 회의 크기는 250 참가자입니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-187">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="fd750-188">250-사용자 회의가 진행 되는 동안에도 풀은 여전히 다른 회의를 지원 하며,이 경우 풀 사용자의 총 5%가 동시 회의에 참가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-188">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="fd750-189">예를 들어 12 프런트 엔드 서버 및 8만 사용자의 그룹에서 250 사용자 회의가 발생 하는 동안 Lync Server에서는 더 작은 회의에 참가 하는 3750을 다른 사용자에 게 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-189">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="fd750-190">프런트 엔드 풀 또는 Standard Edition server에 있는 사용자 수에 관계 없이 Lync Server는 250-사용자 회의를 호스트 하는 동일한 풀이나 서버에서 더 작은 회의에 참가 하는 최소 125의 다른 사용자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-190">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="fd750-191">250과 1000 사용자 간의 전화 회의를 사용 하도록 설정 하려면 이러한 전화 회의를 호스트 하는 경우에만 별도의 프런트 엔드 풀을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-191">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="fd750-192">이 프런트 엔드 풀은 사용자를 호스팅하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-192">This Front End pool will not host any users.</span></span> <span data-ttu-id="fd750-193">자세한 내용은 [Lync Server 2013을 사용 하 여 대규모 모임 지원](lync-server-2013-supporting-large-meetings.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd750-193">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="fd750-194">조직에서 사용자 모델에 사용 되는 것 보다 많은 혼합 모드를 사용 하는 경우에는이 문서의 권장 사항 보다 더 많은 프런트 엔드 서버를 배포 해야 할 수 있습니다 (최대 크기 제한인 12).</span><span class="sxs-lookup"><span data-stu-id="fd750-194">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="fd750-195">사용자 모델의 가정에 대 한 자세한 내용은 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fd750-195">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="fd750-196">에지 서버</span><span class="sxs-lookup"><span data-stu-id="fd750-196">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd750-197">스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-197">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="fd750-198">사이트에 동시에 액세스 하는 12000 원격 사용자 마다 하나의에 지 서버를 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-198">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="fd750-199">최소한 고가용성을 위해 두 개의에 지 서버를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-199">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="fd750-200">이러한 권장 사항은에 지 서버에 대 한 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-200">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="fd750-201">에 지 서버에 대 한 사용자 수를 고려해 야 하는 경우이 사이트의 프런트 엔드 풀에 연결 된 지점에 있는 Sba (survivable Branch 기기 및 Sba (survivable 분기 서버에 홈 사용자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-201">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd750-202">에 지 서버에서 A/V 회의에 지 서비스의 성능을 향상 시키려면에 지 서버의 네트워크 어댑터에 대해 수신측 확장 (RSS)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-202">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="fd750-203">RSS를 사용 하면 서버의 여러 프로세서에서 들어오는 패킷을 병렬로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-203">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="fd750-204">자세한 내용은의 "Windows Server 2008에서 수신측 확장 향상 기능"을 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd750-204">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="fd750-205">RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd750-205">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="fd750-206">Director</span><span class="sxs-lookup"><span data-stu-id="fd750-206">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd750-207">스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-207">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="fd750-208">디렉터 서버 역할을 배포 하는 경우에는 사이트에 동시에 액세스할 모든 12000 원격 사용자에 대해 하나의 디렉터를 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-208">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="fd750-209">최소한 고가용성을 위한 두 개의 디렉터를 권장 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-209">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="fd750-210">이러한 권장 사항은에 지 서버에 대 한 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)의 권장 사항을 충족 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-210">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="fd750-211">디렉터에 대 한 사용자 수를 고려 하는 경우이 사이트의 프런트 엔드 풀에 연결 된 지점에 있는 Sba (survivable Branch 기기 및 Sba (survivable 분기 서버에 홈 사용자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-211">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="fd750-212">중재 서버</span><span class="sxs-lookup"><span data-stu-id="fd750-212">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fd750-213">스트레치 된 풀은이 서버 역할에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-213">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="fd750-214">중재 서버와 프런트 엔드 서버를 함께 배치할 경우에는 풀의 모든 프런트 엔드 서버에서 중재 서버가 실행 되며 풀의 사용자에 게 충분 한 용량을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-214">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="fd750-215">독립 실행형 중재 서버 풀을 배포 하는 경우 배포할 중재 서버 수는 중재 서버에 사용 되는 하드웨어, VoIP 사용자 수, 각 중재 서버 풀에서 제어 하는 게이트웨이 피어 수, 이러한 게이트웨이를 통한 통화 시간 트래픽 및 중재 서버를 우회 하는 미디어의 호출 비율을 비롯 한 다양 한 요인에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-215">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="fd750-216">다음 표에는 중재 서버에 대 한 하드웨어가 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md) 의 요구 사항을 충족 하 고 하이퍼스레딩을 사용 하도록 설정 되어 있다고 가정 하 고 중재 서버가 처리할 수 있는 동시 통화의 수에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-216">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="fd750-217">중재 서버 확장성에 대 한 자세한 내용은 lync server [2013의 중재 서버에 대](lync-server-2013-deployment-guidelines-for-mediation-server.md)한 [음성 사용량 및 2013 트래픽 예상](lync-server-2013-estimating-voice-usage-and-traffic.md) 및 배포 지침을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd750-217">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="fd750-218">다음 표에는 [Lync Server 2013의 사용자 모델](lync-server-2013-user-models.md)에 요약 된 사용 용도가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-218">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="fd750-219">독립 실행형 중재 서버 용량: 70% 내부 사용자, 바이패스 없는 통화 용량을 가진 30%의 외부 사용자 (중재 서버에서 수행 하는 미디어 코드 변환)</span><span class="sxs-lookup"><span data-stu-id="fd750-219">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd750-220">서버 하드웨어</span><span class="sxs-lookup"><span data-stu-id="fd750-220">Server hardware</span></span></th>
<th><span data-ttu-id="fd750-221">최대 통화 수</span><span class="sxs-lookup"><span data-stu-id="fd750-221">Maximum number of calls</span></span></th>
<th><span data-ttu-id="fd750-222">최대 T1 회선 수</span><span class="sxs-lookup"><span data-stu-id="fd750-222">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="fd750-223">최대 E1 줄 수</span><span class="sxs-lookup"><span data-stu-id="fd750-223">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd750-224">이중 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU ( <strong>하이퍼 스레딩 사용 안 함</strong>), 32 GB 메모리 및 이중 포트 네트워크 어댑터 카드 1 개</span><span class="sxs-lookup"><span data-stu-id="fd750-224">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="fd750-225">1100</span><span class="sxs-lookup"><span data-stu-id="fd750-225">1100</span></span></p></td>
<td><p><span data-ttu-id="fd750-226">46</span><span class="sxs-lookup"><span data-stu-id="fd750-226">46</span></span></p></td>
<td><p><span data-ttu-id="fd750-227">35</span><span class="sxs-lookup"><span data-stu-id="fd750-227">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd750-228">이중 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU (32 GB 메모리 및 1 개의 이중 포트 네트워크 어댑터 카드 포함)</span><span class="sxs-lookup"><span data-stu-id="fd750-228">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="fd750-229">1500</span><span class="sxs-lookup"><span data-stu-id="fd750-229">1500</span></span></p></td>
<td><p><span data-ttu-id="fd750-230">63</span><span class="sxs-lookup"><span data-stu-id="fd750-230">63</span></span></p></td>
<td><p><span data-ttu-id="fd750-231">47</span><span class="sxs-lookup"><span data-stu-id="fd750-231">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fd750-232">메모리가 32 인 서버는 성능 테스트에 사용 되었지만, 16gb 메모리를 가진 서버는 독립 실행형 중재 서버에 대해 지원 되며이 표에 표시 된 성능을 충분히 제공 하기에 충분 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-232">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="fd750-233">중재 서버 용량 (중재 서버 배치 된 with 프런트 엔드 서버) 70% 내부 사용자, 30% 외부 사용자, 바이패스 통화 용량 (중재 서버에서 수행 하는 미디어 처리)</span><span class="sxs-lookup"><span data-stu-id="fd750-233">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd750-234">서버 하드웨어</span><span class="sxs-lookup"><span data-stu-id="fd750-234">Server hardware</span></span></th>
<th><span data-ttu-id="fd750-235">최대 통화 수</span><span class="sxs-lookup"><span data-stu-id="fd750-235">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd750-236">이중 프로세서, 16 진수 코어, 2.26 GHz 하이퍼 스레드 CPU (32 GB 메모리 및 2 개의 1GB 네트워크 어댑터 카드 포함)</span><span class="sxs-lookup"><span data-stu-id="fd750-236">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="fd750-237">150</span><span class="sxs-lookup"><span data-stu-id="fd750-237">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fd750-238">프런트 엔드 6600 서버는 음성 통화에 필요한 트랜스 코딩 외에도,이 값은 독립 실행형 중재 서버의 숫자 보다 훨씬 더 작습니다 (이 경우에는,).</span><span class="sxs-lookup"><span data-stu-id="fd750-238">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="fd750-239">중재 서버의 성능을 향상 시키려면 중재 서버의 네트워크 어댑터에 대해 수신측 확장 (RSS)을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-239">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="fd750-240">RSS를 사용 하면 서버의 여러 프로세서에서 들어오는 패킷을 병렬로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-240">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="fd750-241">자세한 내용은의 "Windows Server 2008에서 수신측 확장 향상 기능"을 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A> 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd750-241">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="fd750-242">RSS를 사용 하도록 설정 하는 방법에 대 한 자세한 내용은 네트워크 어댑터 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd750-242">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="fd750-243">백 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="fd750-243">Back End Server</span></span>

<span data-ttu-id="fd750-244">Lync Server 2013에서는 현재 상태 데이터베이스가 백 엔드 서버가 아닌 프런트 엔드 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-244">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="fd750-245">이로 인해 프런트 엔드 서버의 하드웨어 요구 사항에 해당 하는 Lync Server 2013의 각 백 엔드 서버에 대 한 요구 사항이 훨씬 더 간단해졌습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-245">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="fd750-246">이는 백 엔드 서버가 25 개 디스크를 사용 하는 것 보다 훨씬 높은 등급이 필요한 Lync Server 2010와는 대조적입니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-246">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="fd750-247">그러나 백 엔드 서버의 작업량은 여전히이 섹션의 앞부분과 [Lync server 2013 용 서버 하드웨어 플랫폼](lync-server-2013-server-hardware-platforms.md)에서 설명한 하드웨어 권장 사항을 충족 시 키 지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-247">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="fd750-248">백 엔드 서버의 고가용성을 제공 하려면 서버 미러링을 배포 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-248">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="fd750-249">자세한 내용은 [Lync server 2013에서 백 엔드 서버 고가용성](lync-server-2013-back-end-server-high-availability.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fd750-249">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="fd750-250">모니터링 및 보관</span><span class="sxs-lookup"><span data-stu-id="fd750-250">Monitoring and Archiving</span></span>

<span data-ttu-id="fd750-251">Lync Server 2013에서 모니터링 또는 보관을 배포 하는 경우 이러한 서비스의 프런트 엔드 기능은 별도의 서버 역할이 아닌 프런트 엔드 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-251">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="fd750-252">모니터링 및 보관 각 각각은 백 엔드 저장소와는 별도로 자체 데이터베이스 저장소를 그대로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-252">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="fd750-253">또는 Exchange 2013이 배포 된 경우 전용 SQL 저장소가 아닌 Exchange에 인스턴트 메시지 보관 데이터를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-253">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="fd750-254">다음 표에는 데이터 모니터링 및 보관에 대 한 일별 사용자 당 필요한 데이터베이스 저장소의 양이 대략적으로 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-254">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


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
<td><p><span data-ttu-id="fd750-255"><strong>CDR (모니터링)</strong></span><span class="sxs-lookup"><span data-stu-id="fd750-255"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="fd750-256"><strong>QoE (모니터링)</strong></span><span class="sxs-lookup"><span data-stu-id="fd750-256"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="fd750-257"><strong>보관</strong></span><span class="sxs-lookup"><span data-stu-id="fd750-257"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd750-258">사용자 당 하루에 필요한 디스크 공간</span><span class="sxs-lookup"><span data-stu-id="fd750-258">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="fd750-259">49</span><span class="sxs-lookup"><span data-stu-id="fd750-259">49 KB</span></span></p></td>
<td><p><span data-ttu-id="fd750-260">28kb(</span><span class="sxs-lookup"><span data-stu-id="fd750-260">28 KB</span></span></p></td>
<td><p><span data-ttu-id="fd750-261">57</span><span class="sxs-lookup"><span data-stu-id="fd750-261">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd750-262">Microsoft는 성능 테스트 중에 모니터링 및 보관을 위해 데이터베이스 서버에 대해 다음 표의 하드웨어를 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-262">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="fd750-263">테스트에서는 각각 8만 사용자를 포함 하는 두 프런트 엔드 풀의 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd750-263">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="fd750-264">모니터링 및 보관 성능 테스트에 사용 되는 하드웨어</span><span class="sxs-lookup"><span data-stu-id="fd750-264">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd750-265">하드웨어 구성 요소</span><span class="sxs-lookup"><span data-stu-id="fd750-265">Hardware component</span></span></th>
<th><span data-ttu-id="fd750-266">권장</span><span class="sxs-lookup"><span data-stu-id="fd750-266">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd750-267">CPU</span><span class="sxs-lookup"><span data-stu-id="fd750-267">CPU</span></span></p></td>
<td><p><span data-ttu-id="fd750-268">64비트 이중 프로세서, 6중 코어, 2.26GHz 이상</span><span class="sxs-lookup"><span data-stu-id="fd750-268">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd750-269">메모리</span><span class="sxs-lookup"><span data-stu-id="fd750-269">Memory</span></span></p></td>
<td><p><span data-ttu-id="fd750-270">48 기가바이트 (GB)</span><span class="sxs-lookup"><span data-stu-id="fd750-270">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd750-271">공간이</span><span class="sxs-lookup"><span data-stu-id="fd750-271">Disk</span></span></p></td>
<td><p><span data-ttu-id="fd750-272">25 1만-RPM 다음 구성을 사용 하 여 각 디스크에 300 GB의 하드 디스크 드라이브</span><span class="sxs-lookup"><span data-stu-id="fd750-272">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
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
<td><p><span data-ttu-id="fd750-273"><strong>드라이브</strong></span><span class="sxs-lookup"><span data-stu-id="fd750-273"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="fd750-274"><strong>RAID 구성</strong></span><span class="sxs-lookup"><span data-stu-id="fd750-274"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fd750-275"><strong>디스크 수</strong></span><span class="sxs-lookup"><span data-stu-id="fd750-275"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd750-276">CDR, QoE 및 보관 데이터베이스 데이터 파일 (단일 드라이브)</span><span class="sxs-lookup"><span data-stu-id="fd750-276">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="fd750-277">1 + 0</span><span class="sxs-lookup"><span data-stu-id="fd750-277">1+0</span></span></p></td>
<td><p><span data-ttu-id="fd750-278">16 </span><span class="sxs-lookup"><span data-stu-id="fd750-278">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd750-279">CDR 데이터베이스 로그 파일</span><span class="sxs-lookup"><span data-stu-id="fd750-279">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="fd750-280">1 </span><span class="sxs-lookup"><span data-stu-id="fd750-280">1</span></span></p></td>
<td><p><span data-ttu-id="fd750-281">2</span><span class="sxs-lookup"><span data-stu-id="fd750-281">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd750-282">QoE 데이터베이스 로그 파일</span><span class="sxs-lookup"><span data-stu-id="fd750-282">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="fd750-283">1 </span><span class="sxs-lookup"><span data-stu-id="fd750-283">1</span></span></p></td>
<td><p><span data-ttu-id="fd750-284">2</span><span class="sxs-lookup"><span data-stu-id="fd750-284">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd750-285">보관 데이터베이스 로그 파일</span><span class="sxs-lookup"><span data-stu-id="fd750-285">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="fd750-286">1 </span><span class="sxs-lookup"><span data-stu-id="fd750-286">1</span></span></p></td>
<td><p><span data-ttu-id="fd750-287">2</span><span class="sxs-lookup"><span data-stu-id="fd750-287">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd750-288">네트워크</span><span class="sxs-lookup"><span data-stu-id="fd750-288">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="fd750-289">1개의 이중 포트 네트워크 어댑터, 1Gbps 이상(2개 권장, 단일 MAC 주소와 단일 IP 주소를 사용하여 팀으로 구성해야 함)</span><span class="sxs-lookup"><span data-stu-id="fd750-289">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fd750-290">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="fd750-290">In This Section</span></span>

  - [<span data-ttu-id="fd750-291">Lync Server 2013의 음성 사용량 및 트래픽 예상</span><span class="sxs-lookup"><span data-stu-id="fd750-291">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="fd750-292">Lync Server 2013의 중재 서버 배포 지침</span><span class="sxs-lookup"><span data-stu-id="fd750-292">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

