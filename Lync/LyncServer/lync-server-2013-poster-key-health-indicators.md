---
title: 'Lync Server 2013: 포스터: 주요 상태 표시기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Poster: Key Health Indicators'
ms:assetid: 8367dccf-adaa-4a0b-a4ed-bc9570cc5e24
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn593599(v=OCS.15)
ms:contentKeyID: 61084873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6db6a701c98a44b042d9ee36d0a749bf6363bd2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513385"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="250fd-102">Lync Server 2013의 주요 상태 지표</span><span class="sxs-lookup"><span data-stu-id="250fd-102">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="250fd-103">_**마지막으로 수정 된 항목:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="250fd-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="250fd-104">이 문서는 다운로드 센터에서 다운로드할 수 있는 [정상적인 Lync server 포스터를 유지 관리 하는 주요 상태 표시기](https://go.microsoft.com/fwlink/?linkid=391838) 와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="250fd-105">![KHI 데이터를 사용한 문제 해결에 대해 설명 하는 포스터](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "KHI 데이터를 사용한 문제 해결에 대해 설명 하는 포스터")</span><span class="sxs-lookup"><span data-stu-id="250fd-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="250fd-106">이 포스터를 사용 하 여 사용자 환경 문제 노출을 위해 임계값을 갖는 성능 카운터, 키 상태 지표 (KHIs)에 대해 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="250fd-107">CQM (통화 품질 방법론)를 구현 하는 첫 번째 단계로 서 KHI 데이터를 수집 하는 것이 일반적으로 Lync 사용자에 게 고품질 오디오 환경을 제공 하는 데 집중 됩니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="250fd-108">CQM을 사용 하는 방법에 대 한 질문이 있는 경우 cqmfeedback@microsoft.com에 게 질문을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="250fd-109">포스터는 다음 영역에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="250fd-110">주요 상태 지표는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="250fd-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="250fd-111">KHI 데이터를 수집 하려면</span><span class="sxs-lookup"><span data-stu-id="250fd-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="250fd-112">모든 서버 역할에 대 한 업데이트 관리 흐름</span><span class="sxs-lookup"><span data-stu-id="250fd-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="250fd-113">용어</span><span class="sxs-lookup"><span data-stu-id="250fd-113">Glossary</span></span>

  - <span data-ttu-id="250fd-114">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="250fd-114">Front-end Servers</span></span>

  - <span data-ttu-id="250fd-115">백 엔드 SQL 서버</span><span class="sxs-lookup"><span data-stu-id="250fd-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="250fd-116">중재 서버</span><span class="sxs-lookup"><span data-stu-id="250fd-116">Mediation Servers</span></span>

  - <span data-ttu-id="250fd-117">에지 서버</span><span class="sxs-lookup"><span data-stu-id="250fd-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="250fd-118">주요 상태 지표는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="250fd-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="250fd-119">주요 상태 표시기는 사용자 환경 문제 노출을 위한 임계값을 갖는 성능 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="250fd-120">CQM (통화 품질 방법론)를 구현 하는 첫 번째 단계로 서 KHI 데이터를 수집 하는 것이 일반적으로 Lync 사용자에 게 고품질 오디오 환경을 제공 하는 데 집중 됩니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="250fd-121">KHIs 솔루션이 아닌 표준 Lync 모니터링 솔루션 (예: System Center Operations Manager, 가상 트랜잭션, 모니터링 서버)과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="250fd-122">KHI 성능 카운터를 수집 하 고 네트워킹 가이드와 함께 KHI 스프레드시트를 채워서 Lync 배포의 서버 상태를 결정 하는 데 도움이 되는 성과 기록표를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="250fd-123">채워진 후에는 환경을 복구 하 고 다른 관련자에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="250fd-124">매달 KHIs를 평가 하 고이를 모든 배포의 진행 중인 운영 프로세스에 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="250fd-125">[Lync Server 네트워킹 가이드](https://go.microsoft.com/fwlink/p/?linkid=390677) 를 다운로드 하 여 khis의 전체 목록을 확인 하 고 관련 스프레드시트를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-125">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="250fd-126">KHI 데이터를 수집 하려면</span><span class="sxs-lookup"><span data-stu-id="250fd-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="250fd-127">각 Lync Server에서 Lync Server 네트워킹 가이드에 포함 된 KHI 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="250fd-128">그러면 성능 모니터 내부에 데이터 수집기가 생성 되 고 이름이 KHI로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="250fd-129">기본적으로 데이터는 15 초 마다 폴링됩니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="250fd-130">회사 영업일을 시작 하기 전에 각 Lync Server로 이동 하 여 KHI Data 수집기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="250fd-131">해당 요일이 끝나면 KHI 데이터 수집기를 중지 하 고 중앙 위치에 데이터를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="250fd-132">성능 모니터를 사용 하 여 Lync Server 네트워킹 가이드 다운로드에 포함 된 KHI 스프레드시트를 채운 후에는 결과를 권장 대상에 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="250fd-133">모든 서버 역할에 대 한 업데이트 관리 흐름</span><span class="sxs-lookup"><span data-stu-id="250fd-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="250fd-134">Lync 구현의 각 서버에 대해 서버 구성 요소 상태와 시스템 성능이 원하는 수준 이상 인지 확인 하는 것부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="250fd-135">그 후에는 전체 Lync 구현에서 서버의 역할과 관련 된 표시기를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="250fd-136">먼저 모든 서버에 대해 KHI 성능 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="250fd-137">각 시스템 역할 (이 문서의 뒷부분에서 설명 하는 세부 정보)에 대해 기본 시스템 구성 요소가 권장 대상을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="250fd-138">그렇지 않으면 시스템 성능을 교정 하 고, KHI 데이터를 다시 수집 하 고, 시스템 상태를 확인 한 후에는 Lync 구현에서 서버의 역할에 해당 하는 메트릭을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="250fd-139">모든 역할에 대 한 구성 요소 상태는 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="250fd-140">CPU 사용률 \< 80%</span><span class="sxs-lookup"><span data-stu-id="250fd-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="250fd-141">평균 디스크 쓰기 \< 10 밀리초</span><span class="sxs-lookup"><span data-stu-id="250fd-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="250fd-142">평균 디스크 읽기 \< 10 밀리초</span><span class="sxs-lookup"><span data-stu-id="250fd-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="250fd-143">사용 가능한 메모리 \> 20% 시스템 총 MB</span><span class="sxs-lookup"><span data-stu-id="250fd-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="250fd-144">네트워크 큐 길이 \< 2</span><span class="sxs-lookup"><span data-stu-id="250fd-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="250fd-145">삭제 되는 패킷 (입출력) = 0</span><span class="sxs-lookup"><span data-stu-id="250fd-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="250fd-146">용어</span><span class="sxs-lookup"><span data-stu-id="250fd-146">Glossary</span></span>

<span data-ttu-id="250fd-147">이 포스터에는 다음과 같은 용어와 머리글자어가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="250fd-148">MCU = 응용 프로그램 공유 다중 소수점 제어 장치</span><span class="sxs-lookup"><span data-stu-id="250fd-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="250fd-149">AV MCU = 오디오/비디오 MCU</span><span class="sxs-lookup"><span data-stu-id="250fd-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="250fd-150">IM MCU = 인스턴트 메시징 MCU</span><span class="sxs-lookup"><span data-stu-id="250fd-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="250fd-151">C u i = 통합 커뮤니케이션 웹 API</span><span class="sxs-lookup"><span data-stu-id="250fd-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="250fd-152">AV에 지 = Edge를 통한 오디오/비디오 통과</span><span class="sxs-lookup"><span data-stu-id="250fd-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="250fd-153">AV 인증 = 오디오/비디오 인증</span><span class="sxs-lookup"><span data-stu-id="250fd-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="250fd-154">SIP 스택 = Lync의 코어 SIP 구현을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="250fd-155">데이터 프록시 = edge 회의에 사용 됨</span><span class="sxs-lookup"><span data-stu-id="250fd-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="250fd-156">LySS = Lync Storage Service</span><span class="sxs-lookup"><span data-stu-id="250fd-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="250fd-157">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="250fd-157">Front-end Servers</span></span>

<span data-ttu-id="250fd-158">다음 권장 되는 KHI는 기본 구성 요소 상태 외에 프런트 엔드 서버와 관련 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="250fd-159">기능 영역</span><span class="sxs-lookup"><span data-stu-id="250fd-159">Functional area</span></span></th>
<th><span data-ttu-id="250fd-160">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="250fd-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="250fd-161">/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="250fd-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="250fd-162">MCU 상태 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="250fd-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250fd-163">Web Components</span><span class="sxs-lookup"><span data-stu-id="250fd-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="250fd-164">메일 그룹 확장 AD 시간 제한 &lt; 0</span><span class="sxs-lookup"><span data-stu-id="250fd-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="250fd-165">ABWQ 실패 = 0</span><span class="sxs-lookup"><span data-stu-id="250fd-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="250fd-166">LIS 오류 = 0</span><span class="sxs-lookup"><span data-stu-id="250fd-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="250fd-167">인증 오류 &lt; 1/초</span><span class="sxs-lookup"><span data-stu-id="250fd-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="250fd-168">거부 된 ASP.NET v4 요청 = 0</span><span class="sxs-lookup"><span data-stu-id="250fd-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250fd-169">SIP 스택</span><span class="sxs-lookup"><span data-stu-id="250fd-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="250fd-170">평균 수신 메시지 처리 &lt; 1 초</span><span class="sxs-lookup"><span data-stu-id="250fd-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="250fd-171">들어오는 응답 삭제 &lt; 1/초당 들어오는 요청 &lt; 1/초 손실 됨</span><span class="sxs-lookup"><span data-stu-id="250fd-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="250fd-172">큐 대기 시간 &lt; 100 밀리초</span><span class="sxs-lookup"><span data-stu-id="250fd-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="250fd-173">프로시저에 대 한 대기 시간 &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="250fd-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="250fd-174">제한 된 요청 = 0</span><span class="sxs-lookup"><span data-stu-id="250fd-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="250fd-175">인증 오류 &lt; 1/초</span><span class="sxs-lookup"><span data-stu-id="250fd-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="250fd-176">들어오는 메시지 시간 초과 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="250fd-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="250fd-177">평균 받는 메시지 보류 &lt; 1 초</span><span class="sxs-lookup"><span data-stu-id="250fd-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="250fd-178">흐름 제어 연결 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="250fd-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="250fd-179">평균 출력 큐 지연 &lt; 2 초</span><span class="sxs-lookup"><span data-stu-id="250fd-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250fd-180">LySS</span><span class="sxs-lookup"><span data-stu-id="250fd-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="250fd-181">Storage Service DB 80에서 사용 되는 공간의% &lt;</span><span class="sxs-lookup"><span data-stu-id="250fd-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="250fd-182"># 복제본 복제 실패 횟수 = 0</span><span class="sxs-lookup"><span data-stu-id="250fd-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="250fd-183"># 데이터 손실 이벤트의 개수 = 0</span><span class="sxs-lookup"><span data-stu-id="250fd-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250fd-184">SQL</span><span class="sxs-lookup"><span data-stu-id="250fd-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="250fd-185">페이지 수명 예상 &gt; 300 초</span><span class="sxs-lookup"><span data-stu-id="250fd-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="250fd-186">일괄 처리 요청/초 &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="250fd-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="250fd-187">백 엔드 SQL 서버</span><span class="sxs-lookup"><span data-stu-id="250fd-187">Backend SQL Servers</span></span>

<span data-ttu-id="250fd-188">다음 권장 되는 KHI는 기본 구성 요소 상태 외에 SQL server에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="250fd-189">기능 영역</span><span class="sxs-lookup"><span data-stu-id="250fd-189">Functional area</span></span></th>
<th><span data-ttu-id="250fd-190">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="250fd-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="250fd-191">SQL</span><span class="sxs-lookup"><span data-stu-id="250fd-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="250fd-192">페이지 수명 예상 &gt; 300 초</span><span class="sxs-lookup"><span data-stu-id="250fd-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="250fd-193">일괄 처리 요청/초 &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="250fd-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="250fd-194">중재 서버</span><span class="sxs-lookup"><span data-stu-id="250fd-194">Mediation Servers</span></span>

<span data-ttu-id="250fd-195">다음 권장 KHI는 기본 구성 요소 상태 외에 중재 서버에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="250fd-196">기능 영역</span><span class="sxs-lookup"><span data-stu-id="250fd-196">Functional area</span></span></th>
<th><span data-ttu-id="250fd-197">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="250fd-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="250fd-198">중재 서버 서비스</span><span class="sxs-lookup"><span data-stu-id="250fd-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="250fd-199">로드 통화 실패 인덱스 = 0</span><span class="sxs-lookup"><span data-stu-id="250fd-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="250fd-200">프록시 10로 인 한 실패 한 통화 &lt;</span><span class="sxs-lookup"><span data-stu-id="250fd-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="250fd-201">게이트웨이 10으로 인 한 실패 한 통화 &lt;</span><span class="sxs-lookup"><span data-stu-id="250fd-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="250fd-202">거부 된 통화 (로그인 또는 아웃) = 0</span><span class="sxs-lookup"><span data-stu-id="250fd-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="250fd-203">누락 된 미디어 후보 = 0</span><span class="sxs-lookup"><span data-stu-id="250fd-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="250fd-204">미디어 연결 검사 실패 = 0</span><span class="sxs-lookup"><span data-stu-id="250fd-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="250fd-205">에지 서버</span><span class="sxs-lookup"><span data-stu-id="250fd-205">Edge Servers</span></span>

<span data-ttu-id="250fd-206">다음 권장 KHI는 기본 구성 요소 상태 외에도에 지 서버에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="250fd-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="250fd-207">기능 영역</span><span class="sxs-lookup"><span data-stu-id="250fd-207">Functional area</span></span></th>
<th><span data-ttu-id="250fd-208">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="250fd-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="250fd-209">AV 인증</span><span class="sxs-lookup"><span data-stu-id="250fd-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="250fd-210">잘못 된 요청 &lt; 20/초</span><span class="sxs-lookup"><span data-stu-id="250fd-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250fd-211">AV에 지</span><span class="sxs-lookup"><span data-stu-id="250fd-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="250fd-212">인증 실패 &lt; 20/초</span><span class="sxs-lookup"><span data-stu-id="250fd-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="250fd-213">할당 실패 &lt; 20/초</span><span class="sxs-lookup"><span data-stu-id="250fd-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="250fd-214">패킷 &lt; 300/초 손실 됨</span><span class="sxs-lookup"><span data-stu-id="250fd-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="250fd-215">데이터 프록시</span><span class="sxs-lookup"><span data-stu-id="250fd-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="250fd-216">제한 된 서버 연결 &lt; 3</span><span class="sxs-lookup"><span data-stu-id="250fd-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="250fd-217">시스템이 조절 &lt; 1</span><span class="sxs-lookup"><span data-stu-id="250fd-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="250fd-218">SIP 스택</span><span class="sxs-lookup"><span data-stu-id="250fd-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="250fd-219">제한을 초과 하는 연결 삭제 &lt; 1</span><span class="sxs-lookup"><span data-stu-id="250fd-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="250fd-220">전송 시간 초과 &lt; 10</span><span class="sxs-lookup"><span data-stu-id="250fd-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="250fd-221">흐름 제어 연결 &lt; 100</span><span class="sxs-lookup"><span data-stu-id="250fd-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="250fd-222">들어오는 요청 &lt; 1/초 손실</span><span class="sxs-lookup"><span data-stu-id="250fd-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="250fd-223">평균 메시지 처리 &lt; 3 초</span><span class="sxs-lookup"><span data-stu-id="250fd-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="250fd-224">참고 항목</span><span class="sxs-lookup"><span data-stu-id="250fd-224">See Also</span></span>


[<span data-ttu-id="250fd-225">Lync Server 네트워킹 가이드</span><span class="sxs-lookup"><span data-stu-id="250fd-225">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="250fd-226">주요 상태 지표: 정상 Lync Server를 유지 관리 하기 위한 기본 사항</span><span class="sxs-lookup"><span data-stu-id="250fd-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="250fd-227">Lync 통화 품질 방법론</span><span class="sxs-lookup"><span data-stu-id="250fd-227">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

