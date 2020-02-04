---
title: 'Lync Server 2013: Lync Server 성능 모니터링'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync Server 2013 performance
ms:assetid: 2acfd720-6120-4816-a2d4-30476bd5cd0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720910(v=OCS.15)
ms:contentKeyID: 63969592
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7859ea116e4ae63a5777e816c37893f11cf1c39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756842"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-lync-server-2013-performance"></a><span data-ttu-id="8513d-102">Lync Server 2013 성능 모니터링</span><span class="sxs-lookup"><span data-stu-id="8513d-102">Monitoring Lync Server 2013 performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8513d-103">_**마지막으로 수정한 주제:** 2014-05-15_</span><span class="sxs-lookup"><span data-stu-id="8513d-103">_**Topic Last Modified:** 2014-05-15_</span></span>

<span data-ttu-id="8513d-104">Lync Server 2013 성능은 사용자 프로필, 시스템 아키텍처, 소프트웨어, 하드웨어 구성 요소, 게이트웨이 및 전화 통신 장비, 네트워크 연결 및 성능, Windows와 같은 타사 통합 지점 등의 다양 한 요인의 영향을 받습니다. Active Directory 서비스 구성과 성능 외에도 Windows 운영 체제 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-104">Lync Server 2013 performance is affected by various factors such as user profiles, system architecture, software, hardware components, third-party integration points such as gateways and telephony equipment, network connectivity and performance, Windows Active Directory service configuration and performance in addition to the Windows operating system functionality.</span></span>

<span data-ttu-id="8513d-105">Lync Server 2013 배포의 핵심은 구현 되는 서버 소프트웨어 및 하드웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-105">At the core of a Lync Server 2013 deployments’ performance is the server software and hardware it is implemented on.</span></span> <span data-ttu-id="8513d-106">예를 들어 프런트 엔드 서버에는 예상 되는 사용자 로드 (단기)를 처리할 충분 한 하드웨어 리소스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-106">As an example, a front-end server must have sufficient hardware resources to cope with the expected (short-term) user load.</span></span> <span data-ttu-id="8513d-107">1만 사용자에 게 서비스를 제공 하는 데 필요한 각 프런트 엔드 서버를 사용 하는 경우 적절 하 게 구성 된 서버가 예상 되는 로드 요구 사항을 충족 해야 가장 적합 한 최종 사용자 환경을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-107">If a respective front-end server is required to provide services to 10 thousand users, then an adequately configured server must meet the expected load requirements to ultimately help ensure the best possible end-user experience.</span></span>

<span data-ttu-id="8513d-108">따라서 서버 성능 모니터링은 구현 된 서버 인프라에 일일 피크 로드 요구 사항에 적합 한 하드웨어 리소스가 있는지 여부를 측정 하는 데 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-108">Monitoring server performance is therefore extremely important to gauge whether the implemented server infrastructure have suitable hardware resources for the day-to-day peak-load requirements.</span></span> <span data-ttu-id="8513d-109">서버 성능을 모니터링 하면 최종 사용자 환경에 영향을 미치지 않기 위해 관리자가 정정 작업을 적용할 수 있도록 시스템 병목 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-109">Monitoring server performance helps identify system bottlenecks allowing administrators to apply corrective action before the end-user experience is affected.</span></span> <span data-ttu-id="8513d-110">성능 데이터는 장기간 용량 계획에 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-110">The performance data should be used for long-term capacity planning.</span></span>

<span data-ttu-id="8513d-111">제공 되는 모든 성능 개체 및 카운터에 대 한 자세한 내용은 [System Center Operations Manager를 통해 Lync Server 2013을 모니터링](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md)하는 데 연결 되어 있지만, 다음의 몇 가지 성능 카운터를 사용 하 여 관리자에 게 시스템 성능을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-111">While detailed information on all performance objects and counters to be observed is linked to in [Monitoring Lync Server 2013 with System Center Operations Manager](lync-server-2013-monitoring-lync-server-with-system-center-operations-manager.md), some performance counters that you should follow can provide administrators a quick view of the system performance:</span></span>

  - <span data-ttu-id="8513d-112">프런트 엔드 서버의 전반적인 시스템 상태를 추적 하기 위해 프로세서\\시간% 프로세서를 확인 하는 것이 좋은 출발점입니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-112">To track overall system health of the front-end server, a good starting point is to check Processor\\% Processor Time.</span></span> <span data-ttu-id="8513d-113">값은 항상 80% 미만 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-113">The value should always be below 80 percent.</span></span>

  - <span data-ttu-id="8513d-114">프런트 엔드 풀에서 사용 하는 백 엔드 SQL Server 데이터베이스 소프트웨어 인스턴스의 성능을 추적 하려면 다음 성능 카운터를 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-114">To track the performance of the back end SQL Server database software instance used by the Front End pool, monitor the following performance counters:</span></span>
    
    <span data-ttu-id="8513d-115">LC: USrv – 00 – DBStore\\usrv – 002 – 큐 대기 시간 (밀리초)</span><span class="sxs-lookup"><span data-stu-id="8513d-115">LC:USrv – 00 – DBStore\\Usrv – 002 – Queue Latency (msec)</span></span>
    
    <span data-ttu-id="8513d-116">LC: USrv – 00 – DBStore\\usrv – 0 04-저장 프로시저 대기 시간 (밀리초)</span><span class="sxs-lookup"><span data-stu-id="8513d-116">LC:USrv – 00 – DBStore\\Usrv – 0 04– Sproc Latency (msec)</span></span>
    
    <span data-ttu-id="8513d-117">정상 상태의 서버는 100 ms 대기 시간 \<값을 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-117">The healthy server at steady state should show \<100 ms latency values.</span></span> <span data-ttu-id="8513d-118">대기 시간에 도달 하면 프런트 엔드 서버가 백 엔드에 대 한 요청 제한 시작을 의미 하는 12 초가 될 때까지 제한 메커니즘이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-118">The throttling mechanism will engage when latency reaches 12 seconds, which means the front-end server starts throttling requests to the back end.</span></span> <span data-ttu-id="8513d-119">이 때문에 클라이언트가 503 서버 사용량이 너무 많은 오류 메시지를 수신 하는 것이 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-119">This causes clients to start to receive a 503 Server too busy error message.</span></span>

  - <span data-ttu-id="8513d-120">프런트 엔드 서버에서 처리 시간을 추적 하려면 다음 카운터를 모니터링 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-120">To track the processing time at the front-end server, monitor the following counter:</span></span>
    
    <span data-ttu-id="8513d-121">LC: SIP-07-부하 관리\\SIP-000-받는 메시지에 대 한 평균 유지 시간</span><span class="sxs-lookup"><span data-stu-id="8513d-121">LC:SIP - 07 - Load Management\\SIP - 000 - Average Holding Time For Incoming Messages</span></span>
    
    <span data-ttu-id="8513d-122">이는 프런트 엔드 서버의 처리 시간이 높을 때 시작 되는이 시간을 프런트 엔드 서버에서 사용할 수 있는 또 다른 제한 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-122">This is another throttling mechanism on the front-end servers, this time starting when the processing time on the front end is high.</span></span> <span data-ttu-id="8513d-123">평균 처리 시간이 6 초를 초과 하는 경우 서버는 제한 모드로 전환 되 고 클라이언트 연결당 해결 되지 않은 트랜잭션만 하나만 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-123">If average processing time is more than six seconds, the server goes into throttling mode and only allows one outstanding transaction per client connection.</span></span>

  - <span data-ttu-id="8513d-124">SQL 백 엔드 서버에서 메모리 문제를 추적 하려면 다음 카운터를 모니터링 하세요.</span><span class="sxs-lookup"><span data-stu-id="8513d-124">To track memory issues at SQL Back End Server, monitor the following counter:</span></span>
    
    <span data-ttu-id="8513d-125">SQL Server 버퍼 관리자\\페이지 수명 액</span><span class="sxs-lookup"><span data-stu-id="8513d-125">SQL Server Buffer Manager\\Page life expectancy</span></span>
    
    <span data-ttu-id="8513d-126">3600 초 미만인 낮은 값 (대기 시간이 긴 기록/초 및 검사점 페이지/초)이 메모리 사용량을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-126">A low value, below 3600 seconds (together with high latency writes/sec and checkpoint pages/sec) indicates memory pressure.</span></span>

<div>

## <a name="additional-counters-to-view"></a><span data-ttu-id="8513d-127">표시할 추가 카운터</span><span class="sxs-lookup"><span data-stu-id="8513d-127">Additional Counters to View</span></span>

<span data-ttu-id="8513d-128">프런트 엔드 서버의 전반적인 상태에 대 한 훌륭한 지표로 표시 되는 몇 가지 주요 카운터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-128">There are several key counters that are good indicators of overall health from the front end server.</span></span> <span data-ttu-id="8513d-129">이것은 포괄적인 목록이 아니며 근본 원인을 파악 하는 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-129">This is not a comprehensive list and is not meant to identify root cause.</span></span> <span data-ttu-id="8513d-130">이러한 카운터를 통해 서버 상태에 대 한 빠른 검사를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-130">These counters will let you perform a quick check on your server health.</span></span> <span data-ttu-id="8513d-131">풀의 각 서버에서 이러한 카운터를 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-131">We recommend verifying these counters on each of the servers in the pool.</span></span> <span data-ttu-id="8513d-132">이러한 카운터 값은 서버가 정상 상태인 경우를 이해 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-132">It is important to understand what these counter values are when your server is healthy.</span></span> <span data-ttu-id="8513d-133">기준에 따라 사용자 환경의 성능이 떨어질 때 변경 내용을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-133">A baseline is required to understand what changed when the user experience is degraded.</span></span>

<span data-ttu-id="8513d-134">프런트 엔드 서버는 시스템의 다른 곳에 있는 병목 현상으로 인해 발생할 수 있는 문제를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-134">The front-end server can indicate issues that may be caused by bottlenecks elsewhere in the system.</span></span> <span data-ttu-id="8513d-135">즉, 전체 시스템 상태를 볼 때 가장 좋은 시작 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-135">This means that it is the best place to start when looking at overall system health.</span></span>

<span data-ttu-id="8513d-136">먼저 검토 하는 두 가지 추가 카운터는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-136">Two additional counters to review first are as follows:</span></span>

<span data-ttu-id="8513d-137">LC: USrv-00-DBStore\\usrv-002-큐 대기 시간 (밀리초)</span><span class="sxs-lookup"><span data-stu-id="8513d-137">LC:USrv-00-DBStore\\Usrv-002-Queue Latency (msec)</span></span>

<span data-ttu-id="8513d-138">LC: USrv-00-DBStore\\usrv-004-저장 프로시저 대기 시간 (밀리초)</span><span class="sxs-lookup"><span data-stu-id="8513d-138">LC:USrv-00-DBStore\\Usrv-004-Sproc Latency (msec)</span></span>

<span data-ttu-id="8513d-139">Queue latency 카운터는 큐에서 백 엔드 까지의 요청이 소요 된 시간 및 처리 대기 시간을 나타내며 백 엔드가 요청을 처리 하는 데 걸리는 시간을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-139">The queue latency counter represents the time that a request spent in the queue to the back end and the Sproc latency represents the time that it took for the back end to process the request.</span></span> <span data-ttu-id="8513d-140">백 엔드의 어떠한 이유, 디스크, 메모리, 네트워크, 프로세서에 대해 문제가 발생 하는 경우 대기열 대기 시간이 더 높습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-140">If, for any reason, disk, memory, network, and processor on the back end are in trouble, the queue latency counter will be high.</span></span>

<span data-ttu-id="8513d-141">또한 프론트 엔드와 백 엔드 사이에 네트워크 대기 시간이 많은 경우 높을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-141">It can also be high if there is high network latency between the front end and the back end.</span></span> <span data-ttu-id="8513d-142">그렇다면 허용 되는 큐 대기 시간은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="8513d-142">So what is acceptable queue latency?</span></span>

<span data-ttu-id="8513d-143">12 초에 프런트 엔드 서버는 백 엔드 서버에 대 한 제한 요청을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-143">At 12 seconds, the Front End Servers start throttling requests to the Back End Servers.</span></span> <span data-ttu-id="8513d-144">이는 서버에서 서버 사용량이 많음 – 503 오류가 클라이언트에 반환 되기 시작 한다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-144">This means the servers start returning Server too busy – 503 errors to the clients.</span></span> <span data-ttu-id="8513d-145">정상 상태의 서버는 일정 한 상태에서 100 msec DBStore 대기열 대기 시간을 초과 해야 하지만, 서버가 온라인 상태로 전환 되 고 사용자가 동시에 로그인 하는 경우에는 해당 카운터가 매우 높을 수 있으며,이는 여러 번 발생 하는 것 처럼 보일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-145">A healthy server should have less than 100 msec DBStore queue latencies at steady state, but during times where the server has just come online and users are all logging in at the same time, that counter can be very high and you may even see it hit multiple seconds.</span></span>

<span data-ttu-id="8513d-146">부하 분산 구성을 사용할 수 있으며,이 경우 여러 프런트 엔드 서버를 사용 하 여 배포 된 풀과 "최소 연결 수"로 구성 된 부하 분산 장치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-146">You may have a load-balanced configuration, where you have a pool deployed with multiple front-end servers and a load balancer that is configured for "least number of connections."</span></span> <span data-ttu-id="8513d-147">이 경우 프런트 엔드 서버 중 하나가 다시 시작 되 면 해당 서버에는 다른 풀 구성원에 비해 더 적은 연결이 있으므로 다시 연결 하려는 모든 사용자가 다시 시작 된 서버를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-147">In this case, if one front-end server is restarted, then all users who attempt to reconnect will be pointed to the restarted server, because that server will have fewer connections compared to the other pool members.</span></span> <span data-ttu-id="8513d-148">이 기간 동안에는 해당 프런트 엔드 서버가 오버 로드 될 수 있지만 다른 풀 구성원은 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-148">During this time, the respective front-end server may be overloaded while the other pool members are not.</span></span>

<span data-ttu-id="8513d-149">사용자가 동시에 서버에 연결 하기 위해 경쟁 하지 않는 경우에는 시간이 경과 되는 동안 유지 관리를 수행 하 여 성능이 저하 되는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-149">We recommend that you perform maintenance during off-hours to reduce the performance affect as users will not all be competing to connect to the server at the same time.</span></span>

<span data-ttu-id="8513d-150">이전의 두 성능 카운터가 높으면 SQL 백 엔드 서버에 병목 현상이 발생할 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-150">If the previous two performance counters are high, the most likely bottleneck is the SQL Back End Server.</span></span> <span data-ttu-id="8513d-151">확인 해야 할 다음 구성 요소는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-151">The next components to confirm are as follows:</span></span>

  - <span data-ttu-id="8513d-152">SQL Server CPU가 너무 높기 때문에</span><span class="sxs-lookup"><span data-stu-id="8513d-152">Is the SQL Server CPU too high?</span></span> <span data-ttu-id="8513d-153">예를 들어, 80% 이상 입니까?</span><span class="sxs-lookup"><span data-stu-id="8513d-153">For example, is it greater than 80 percent?</span></span>

  - <span data-ttu-id="8513d-154">디스크 대기 시간이 높지 않습니까?</span><span class="sxs-lookup"><span data-stu-id="8513d-154">Is the disk latency high?</span></span>

<span data-ttu-id="8513d-155">이상적으로는 메모리에 RTC 및 RTCDYN 데이터베이스를 둘 다 사용할 수 있는 충분 한 RAM이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-155">In an ideal world, you have enough RAM to have both the RTC and RTCDYN databases in memory.</span></span> <span data-ttu-id="8513d-156">그런 다음 서버가 디스크에 액세스 하는 유일한 이유가 로그 파일에 기록 하 고 데이터베이스에 플러시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-156">Then, the only reason the server would be accessing the disk, is to write to the log files and flush to the databases.</span></span> <span data-ttu-id="8513d-157">테스트에서는 12gb의 RAM이 10만 사용자 배포에 충분 하다는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-157">Tests have shown that 12 GB of RAM is sufficient for 100 thousand user deployments.</span></span> <span data-ttu-id="8513d-158">이는 RTC 및 RTCDYN 데이터베이스 크기가 12gb 미만인 것으로 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-158">This assumes that the RTC and RTCDYN databases size totals less than 12 GB.</span></span> <span data-ttu-id="8513d-159">데이터베이스가 이보다 크면 추가 메모리가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-159">If your databases are larger than that, then you may need additional memory.</span></span>

<span data-ttu-id="8513d-160">Sql server 버퍼 관리자 페이지 수명 액 성능 카운터를 검토 하 여 SQL Server에 추가 RAM이 필요한 지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-160">You can determine whether your SQL Server requires additional RAM by reviewing the SQL Server Buffer Manager page life expectancy performance counter.</span></span> <span data-ttu-id="8513d-161">3600 보다 작은 값은 메모리 사용량을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-161">A value less than 3,600 indicates memory pressure.</span></span> <span data-ttu-id="8513d-162">또한 SQL Server에서 데이터베이스에 쓰기만 해야 하므로 메모리가 충분 한 경우에는 데이터베이스 드라이브에 읽기가 거의 안 되지 않는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-162">You should also see little to no reads on your database drive if you have sufficient memory because SQL Server should only be writing to the database.</span></span>

<span data-ttu-id="8513d-163">서버 처리 시간이 높을 경우 시작 하는 Lync Server 2013 프런트 엔드 서버에는 추가 조절 메커니즘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-163">There is an additional throttling mechanism in a Lync Server 2013 Front End Server that starts if the server processing time is high.</span></span> <span data-ttu-id="8513d-164">DBStore 대기 시간 제한은 SQL Server의 대기 시간이 높을 때만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-164">The DBStore latency throttling is only enabled if the latency to the SQL Server is high.</span></span> <span data-ttu-id="8513d-165">이러한 제한이 사용 되는 한 가지 예는 프런트 엔드 서버가 CPU에 연결 되어 있는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-165">One example in which such throttling is enabled is if the front-end server is CPU-bound.</span></span>

<span data-ttu-id="8513d-166">서버에서 평균 처리 시간 **(LC: sip-07-부하 관리\\SIP-000-받는 메시지의 경우)** 이 6 초를 초과 하면 서버는 제한 모드로 전환 되며 사용자는 클라이언트 연결당 한 가지 해결 되지 않은 트랜잭션만 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-166">If the average processing time **(LC:SIP-07-Load Management\\SIP-000-Average Holding Time For Incoming Messages)** on the server exceeds six seconds, then the server goes into throttling mode and only gives users one outstanding transaction per client connection.</span></span> <span data-ttu-id="8513d-167">처리 시간이 3 초로 떨어지면 서버가 제한 모드를 종료 하 고 사용자에 게 클라이언트 연결당 최대 20 개의 해결 되지 않은 트랜잭션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-167">Once the processing time drops to three seconds, then the server drops out of throttling mode and gives users up to 20 outstanding transactions per client connection.</span></span> <span data-ttu-id="8513d-168">특정 연결에 대 한 트랜잭션의 수가 위의 임계값을 초과할 때마다 흐름 제어로 연결 되는 것으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-168">Whenever the number of transactions on a specific connection exceeds the threshold above, the connection is marked as flow controlled.</span></span> <span data-ttu-id="8513d-169">결과적으로 서버는 해당 파일에 대 한 수신을 게시 하지 않으며 **LC: SIP-01-피어\\흐름 제어 된 연결** 카운터가 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-169">The result is the server does not post any receives on it, and the **LC:SIP-01-Peers\\Flow Controlled Connections** counter is incremented.</span></span> <span data-ttu-id="8513d-170">연결이 흐름 제어 상태에서 1 분 이상으로 유지 되는 경우 서버에서 해당 연결을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-170">If a connection stays in a flow-controlled state for more than one minute, then the server closes it.</span></span> <span data-ttu-id="8513d-171">지연 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-171">It does so lazily.</span></span> <span data-ttu-id="8513d-172">연결을 확인할 기회가 있는 경우, 연결이 너무 오랫동안 스로틀 되었는지 여부를 확인 하 고 1 분이 넘으면이를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-172">When it has an opportunity to check the connection, it determines whether it was throttled for too long and closes it if it has more than one minute.</span></span>

<span data-ttu-id="8513d-173">다음은 두 가지 스로틀 메커니즘이 며, 서버가 수행 하는 제한 사항에 대 한 요약 한 가지 성능 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-173">These are the two throttling mechanisms and there is one performance counter that summarizes what, if any, throttling the server is performing.</span></span>

<span data-ttu-id="8513d-174">**LC: SIP-04-응답\\SIP-053-로컬 503 응답/초**</span><span class="sxs-lookup"><span data-stu-id="8513d-174">**LC:SIP-04-Responses\\SIP-053-Local 503 Responses/sec**</span></span>

  - <span data-ttu-id="8513d-175">이전 카운터의 "Local" 이라는 용어는 로컬에서 생성 된 응답을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-175">The term "Local" in the previous counter refers to locally generated responses.</span></span>

  - <span data-ttu-id="8513d-176">503 코드는 서버를 사용할 수 없는 경우 (정상 서버에서 503 코드를 표시 하지 않아야 함)에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-176">The 503 code corresponds to server unavailable—where you should not see any 503 codes on a healthy server.</span></span> <span data-ttu-id="8513d-177">서버가 온라인 상태가 된 후의 기간 동안에는 일부 503 코드가 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-177">During the period after a server is just brought online, you may see some 503 codes.</span></span> <span data-ttu-id="8513d-178">모든 사용자가 다시 로그인 하 고 서버가 안정적인 상태로 반환 되는 경우 추가 503 코드가 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-178">When all of the users sign back in and the server returns to a stable state, there should no additional 503 codes.</span></span>

<span data-ttu-id="8513d-179">**LC: SIP-04-응답\\SIP-074-로컬 504 응답/초**</span><span class="sxs-lookup"><span data-stu-id="8513d-179">**LC:SIP-04-Responses\\SIP-074-Local 504 Responses/sec**</span></span>

<span data-ttu-id="8513d-180">이 성능 카운터는 다른 서버와의 연결 문제를 나타내고 연결 하는 동안 발생 한 오류를 표시 하거나 연결을 지연 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-180">This performance counter indicates connectivity issues with other servers and it can indicate failures to connect or delays in connecting.</span></span> <span data-ttu-id="8513d-181">504 오류가 표시 되는 경우 다음 성능 카운터를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-181">If you are seeing 504 errors then the following performance counter should be checked.</span></span>

<span data-ttu-id="8513d-182">**LC: SIP-01-피어\\SIP-017-해결 되지 않은 전송**</span><span class="sxs-lookup"><span data-stu-id="8513d-182">**LC:SIP-01-Peers\\SIP-017-Sends Outstanding**</span></span>

<span data-ttu-id="8513d-183">이 카운터는 나가는 대기 요청과 응답의 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-183">This counter indicates the number of outgoing queued requests and responses.</span></span> <span data-ttu-id="8513d-184">이 카운터가 높으면 해당 문제가 로컬 서버에 없을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-184">If this counter is high then the issue is most likely not on the local server.</span></span> <span data-ttu-id="8513d-185">네트워크 지연 문제가 있는 경우에는이 카운터가 높을 수 있다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8513d-185">Note that this counter can be high if there are network latency issues.</span></span> <span data-ttu-id="8513d-186">로컬 네트워크 어댑터의 문제를 나타낼 수도 있지만, 원격 서버의 문제로 인해 발생할 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-186">It could also indicate issues with the local network adapter, but is more likely caused by an issue on a remote server.</span></span> <span data-ttu-id="8513d-187">이 카운터는 통신 하려고 하는 풀이 오버 로드 되었을 때 디렉터 서버에서 높을 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-187">This counter would most likely be high on a Director server when the pool it is trying to communicate with is overloaded.</span></span> <span data-ttu-id="8513d-188">이 카운터를 사용 하는 열쇠는 합계 뿐 아니라 인스턴스를 살펴보는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8513d-188">The key with this counter is to look at the instances, not just the total.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

