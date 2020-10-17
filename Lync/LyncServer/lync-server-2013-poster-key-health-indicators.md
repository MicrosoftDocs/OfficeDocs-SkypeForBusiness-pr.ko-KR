---
title: 'Lync Server 2013: 포스터: 주요 상태 표시기'
description: 'Lync Server 2013: 포스터: 주요 상태 표시기'
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
ms.openlocfilehash: 9962d1764d5d2c664bb8415261344d9b48c81149
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566344"
---
# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="01383-103">Lync Server 2013의 주요 상태 지표</span><span class="sxs-lookup"><span data-stu-id="01383-103">Key Health Indicators in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01383-104">_**마지막으로 수정 된 항목:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="01383-104">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="01383-105">이 문서는 다운로드 센터에서 다운로드할 수 있는 [정상적인 Lync server 포스터를 유지 관리 하는 주요 상태 표시기](https://go.microsoft.com/fwlink/?linkid=391838) 와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01383-105">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](https://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="01383-106">![KHI 데이터를 사용한 문제 해결에 대해 설명 하는 포스터](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "KHI 데이터를 사용한 문제 해결에 대해 설명 하는 포스터")</span><span class="sxs-lookup"><span data-stu-id="01383-106">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="01383-107">이 포스터를 사용 하 여 사용자 환경 문제 노출을 위해 임계값을 갖는 성능 카운터, 키 상태 지표 (KHIs)에 대해 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01383-107">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="01383-108">CQM (통화 품질 방법론)를 구현 하는 첫 번째 단계로 서 KHI 데이터를 수집 하는 것이 일반적으로 Lync 사용자에 게 고품질 오디오 환경을 제공 하는 데 집중 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01383-108">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="01383-109">CQM을 사용 하는 방법에 대 한 질문이 있는 경우 cqmfeedback@microsoft.com에 게 질문을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01383-109">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="01383-110">포스터는 다음 영역에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-110">The poster explains the following areas:</span></span>

  - <span data-ttu-id="01383-111">주요 상태 지표는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="01383-111">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="01383-112">KHI 데이터를 수집 하려면</span><span class="sxs-lookup"><span data-stu-id="01383-112">To Collect KHI Data</span></span>

  - <span data-ttu-id="01383-113">모든 서버 역할에 대 한 업데이트 관리 흐름</span><span class="sxs-lookup"><span data-stu-id="01383-113">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="01383-114">용어</span><span class="sxs-lookup"><span data-stu-id="01383-114">Glossary</span></span>

  - <span data-ttu-id="01383-115">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="01383-115">Front-end Servers</span></span>

  - <span data-ttu-id="01383-116">백 엔드 SQL 서버</span><span class="sxs-lookup"><span data-stu-id="01383-116">Backend SQL Servers</span></span>

  - <span data-ttu-id="01383-117">중재 서버</span><span class="sxs-lookup"><span data-stu-id="01383-117">Mediation Servers</span></span>

  - <span data-ttu-id="01383-118">에지 서버</span><span class="sxs-lookup"><span data-stu-id="01383-118">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="01383-119">주요 상태 지표는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="01383-119">What are Key Health Indicators?</span></span>

<span data-ttu-id="01383-120">주요 상태 표시기는 사용자 환경 문제 노출을 위한 임계값을 갖는 성능 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="01383-120">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="01383-121">CQM (통화 품질 방법론)를 구현 하는 첫 번째 단계로 서 KHI 데이터를 수집 하는 것이 일반적으로 Lync 사용자에 게 고품질 오디오 환경을 제공 하는 데 집중 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01383-121">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="01383-122">KHIs 솔루션이 아닌 표준 Lync 모니터링 솔루션 (예: System Center Operations Manager, 가상 트랜잭션, 모니터링 서버)과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01383-122">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="01383-123">KHI 성능 카운터를 수집 하 고 네트워킹 가이드와 함께 KHI 스프레드시트를 채워서 Lync 배포의 서버 상태를 결정 하는 데 도움이 되는 성과 기록표를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-123">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="01383-124">채워진 후에는 환경을 복구 하 고 다른 관련자에 대 한 추가 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-124">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="01383-125">매달 KHIs를 평가 하 고이를 모든 배포의 진행 중인 운영 프로세스에 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-125">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="01383-126">[Lync Server 네트워킹 가이드](https://go.microsoft.com/fwlink/p/?linkid=390677) 를 다운로드 하 여 khis의 전체 목록을 확인 하 고 관련 스프레드시트를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01383-126">Download the [Lync Server Networking Guide](https://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="01383-127">KHI 데이터를 수집 하려면</span><span class="sxs-lookup"><span data-stu-id="01383-127">To Collect KHI Data</span></span>

1.  <span data-ttu-id="01383-128">각 Lync Server에서 Lync Server 네트워킹 가이드에 포함 된 KHI 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-128">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="01383-129">그러면 성능 모니터 내부에 데이터 수집기가 생성 되 고 이름이 KHI로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="01383-129">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="01383-130">기본적으로 데이터는 15 초 마다 폴링됩니다.</span><span class="sxs-lookup"><span data-stu-id="01383-130">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="01383-131">회사 영업일을 시작 하기 전에 각 Lync Server로 이동 하 여 KHI Data 수집기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-131">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="01383-132">해당 요일이 끝나면 KHI 데이터 수집기를 중지 하 고 중앙 위치에 데이터를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-132">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="01383-133">성능 모니터를 사용 하 여 Lync Server 네트워킹 가이드 다운로드에 포함 된 KHI 스프레드시트를 채운 후에는 결과를 권장 대상에 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-133">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="01383-134">모든 서버 역할에 대 한 업데이트 관리 흐름</span><span class="sxs-lookup"><span data-stu-id="01383-134">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="01383-135">Lync 구현의 각 서버에 대해 서버 구성 요소 상태와 시스템 성능이 원하는 수준 이상 인지 확인 하는 것부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-135">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="01383-136">그 후에는 전체 Lync 구현에서 서버의 역할과 관련 된 표시기를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-136">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="01383-137">먼저 모든 서버에 대해 KHI 성능 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-137">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="01383-138">각 시스템 역할 (이 문서의 뒷부분에서 설명 하는 세부 정보)에 대해 기본 시스템 구성 요소가 권장 대상을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-138">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="01383-139">그렇지 않으면 시스템 성능을 교정 하 고, KHI 데이터를 다시 수집 하 고, 시스템 상태를 확인 한 후에는 Lync 구현에서 서버의 역할에 해당 하는 메트릭을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01383-139">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="01383-140">모든 역할에 대 한 구성 요소 상태는 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01383-140">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="01383-141">CPU 사용률 \< 80%</span><span class="sxs-lookup"><span data-stu-id="01383-141">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="01383-142">평균 디스크 쓰기 \< 10 밀리초</span><span class="sxs-lookup"><span data-stu-id="01383-142">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="01383-143">평균 디스크 읽기 \< 10 밀리초</span><span class="sxs-lookup"><span data-stu-id="01383-143">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="01383-144">사용 가능한 메모리 \> 20% 시스템 총 MB</span><span class="sxs-lookup"><span data-stu-id="01383-144">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="01383-145">네트워크 큐 길이 \< 2</span><span class="sxs-lookup"><span data-stu-id="01383-145">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="01383-146">삭제 되는 패킷 (입출력) = 0</span><span class="sxs-lookup"><span data-stu-id="01383-146">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="01383-147">용어</span><span class="sxs-lookup"><span data-stu-id="01383-147">Glossary</span></span>

<span data-ttu-id="01383-148">이 포스터에는 다음과 같은 용어와 머리글자어가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01383-148">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="01383-149">MCU = 응용 프로그램 공유 다중 소수점 제어 장치</span><span class="sxs-lookup"><span data-stu-id="01383-149">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="01383-150">AV MCU = 오디오/비디오 MCU</span><span class="sxs-lookup"><span data-stu-id="01383-150">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="01383-151">IM MCU = 인스턴트 메시징 MCU</span><span class="sxs-lookup"><span data-stu-id="01383-151">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="01383-152">C u i = 통합 커뮤니케이션 웹 API</span><span class="sxs-lookup"><span data-stu-id="01383-152">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="01383-153">AV에 지 = Edge를 통한 오디오/비디오 통과</span><span class="sxs-lookup"><span data-stu-id="01383-153">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="01383-154">AV 인증 = 오디오/비디오 인증</span><span class="sxs-lookup"><span data-stu-id="01383-154">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="01383-155">SIP 스택 = Lync의 코어 SIP 구현을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="01383-155">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="01383-156">데이터 프록시 = edge 회의에 사용 됨</span><span class="sxs-lookup"><span data-stu-id="01383-156">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="01383-157">LySS = Lync Storage Service</span><span class="sxs-lookup"><span data-stu-id="01383-157">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="01383-158">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="01383-158">Front-end Servers</span></span>

<span data-ttu-id="01383-159">다음 권장 되는 KHI는 기본 구성 요소 상태 외에 프런트 엔드 서버와 관련 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="01383-159">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01383-160">기능 영역</span><span class="sxs-lookup"><span data-stu-id="01383-160">Functional area</span></span></th>
<th><span data-ttu-id="01383-161">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="01383-161">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01383-162">/AV/IM MCU</span><span class="sxs-lookup"><span data-stu-id="01383-162">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="01383-163">MCU 상태 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="01383-163">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01383-164">Web Components</span><span class="sxs-lookup"><span data-stu-id="01383-164">Web Components</span></span></p></td>
<td><p><span data-ttu-id="01383-165">메일 그룹 확장 AD 시간 제한 &lt; 0</span><span class="sxs-lookup"><span data-stu-id="01383-165">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="01383-166">ABWQ 실패 = 0</span><span class="sxs-lookup"><span data-stu-id="01383-166">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="01383-167">LIS 오류 = 0</span><span class="sxs-lookup"><span data-stu-id="01383-167">LIS failures = 0</span></span></p>
<p><span data-ttu-id="01383-168">인증 오류 &lt; 1/초</span><span class="sxs-lookup"><span data-stu-id="01383-168">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="01383-169">거부 된 ASP.NET v4 요청 = 0</span><span class="sxs-lookup"><span data-stu-id="01383-169">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01383-170">SIP 스택</span><span class="sxs-lookup"><span data-stu-id="01383-170">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="01383-171">평균 수신 메시지 처리 &lt; 1 초</span><span class="sxs-lookup"><span data-stu-id="01383-171">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="01383-172">들어오는 응답 삭제 &lt; 1/초당 들어오는 요청 &lt; 1/초 손실 됨</span><span class="sxs-lookup"><span data-stu-id="01383-172">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="01383-173">큐 대기 시간 &lt; 100 밀리초</span><span class="sxs-lookup"><span data-stu-id="01383-173">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="01383-174">프로시저에 대 한 대기 시간 &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="01383-174">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="01383-175">제한 된 요청 = 0</span><span class="sxs-lookup"><span data-stu-id="01383-175">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="01383-176">인증 오류 &lt; 1/초</span><span class="sxs-lookup"><span data-stu-id="01383-176">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="01383-177">들어오는 메시지 시간 초과 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="01383-177">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="01383-178">평균 받는 메시지 보류 &lt; 1 초</span><span class="sxs-lookup"><span data-stu-id="01383-178">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="01383-179">흐름 제어 연결 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="01383-179">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="01383-180">평균 출력 큐 지연 &lt; 2 초</span><span class="sxs-lookup"><span data-stu-id="01383-180">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01383-181">LySS</span><span class="sxs-lookup"><span data-stu-id="01383-181">LySS</span></span></p></td>
<td><p><span data-ttu-id="01383-182">Storage Service DB 80에서 사용 되는 공간의% &lt;</span><span class="sxs-lookup"><span data-stu-id="01383-182">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="01383-183"># 복제본 복제 실패 횟수 = 0</span><span class="sxs-lookup"><span data-stu-id="01383-183"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="01383-184"># 데이터 손실 이벤트의 개수 = 0</span><span class="sxs-lookup"><span data-stu-id="01383-184"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01383-185">SQL</span><span class="sxs-lookup"><span data-stu-id="01383-185">SQL</span></span></p></td>
<td><p><span data-ttu-id="01383-186">페이지 수명 예상 &gt; 300 초</span><span class="sxs-lookup"><span data-stu-id="01383-186">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="01383-187">일괄 처리 요청/초 &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="01383-187">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="01383-188">백 엔드 SQL 서버</span><span class="sxs-lookup"><span data-stu-id="01383-188">Backend SQL Servers</span></span>

<span data-ttu-id="01383-189">다음 권장 되는 KHI는 기본 구성 요소 상태 외에 SQL server에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01383-189">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01383-190">기능 영역</span><span class="sxs-lookup"><span data-stu-id="01383-190">Functional area</span></span></th>
<th><span data-ttu-id="01383-191">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="01383-191">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01383-192">SQL</span><span class="sxs-lookup"><span data-stu-id="01383-192">SQL</span></span></p></td>
<td><p><span data-ttu-id="01383-193">페이지 수명 예상 &gt; 300 초</span><span class="sxs-lookup"><span data-stu-id="01383-193">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="01383-194">일괄 처리 요청/초 &lt; 2500</span><span class="sxs-lookup"><span data-stu-id="01383-194">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="01383-195">중재 서버</span><span class="sxs-lookup"><span data-stu-id="01383-195">Mediation Servers</span></span>

<span data-ttu-id="01383-196">다음 권장 KHI는 기본 구성 요소 상태 외에 중재 서버에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01383-196">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01383-197">기능 영역</span><span class="sxs-lookup"><span data-stu-id="01383-197">Functional area</span></span></th>
<th><span data-ttu-id="01383-198">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="01383-198">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01383-199">중재 서버 서비스</span><span class="sxs-lookup"><span data-stu-id="01383-199">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="01383-200">로드 통화 실패 인덱스 = 0</span><span class="sxs-lookup"><span data-stu-id="01383-200">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="01383-201">프록시 10로 인 한 실패 한 통화 &lt;</span><span class="sxs-lookup"><span data-stu-id="01383-201">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="01383-202">게이트웨이 10으로 인 한 실패 한 통화 &lt;</span><span class="sxs-lookup"><span data-stu-id="01383-202">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="01383-203">거부 된 통화 (로그인 또는 아웃) = 0</span><span class="sxs-lookup"><span data-stu-id="01383-203">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="01383-204">누락 된 미디어 후보 = 0</span><span class="sxs-lookup"><span data-stu-id="01383-204">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="01383-205">미디어 연결 검사 실패 = 0</span><span class="sxs-lookup"><span data-stu-id="01383-205">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="01383-206">에지 서버</span><span class="sxs-lookup"><span data-stu-id="01383-206">Edge Servers</span></span>

<span data-ttu-id="01383-207">다음 권장 KHI는 기본 구성 요소 상태 외에도에 지 서버에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="01383-207">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="01383-208">기능 영역</span><span class="sxs-lookup"><span data-stu-id="01383-208">Functional area</span></span></th>
<th><span data-ttu-id="01383-209">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="01383-209">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="01383-210">AV 인증</span><span class="sxs-lookup"><span data-stu-id="01383-210">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="01383-211">잘못 된 요청 &lt; 20/초</span><span class="sxs-lookup"><span data-stu-id="01383-211">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01383-212">AV에 지</span><span class="sxs-lookup"><span data-stu-id="01383-212">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="01383-213">인증 실패 &lt; 20/초</span><span class="sxs-lookup"><span data-stu-id="01383-213">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="01383-214">할당 실패 &lt; 20/초</span><span class="sxs-lookup"><span data-stu-id="01383-214">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="01383-215">패킷 &lt; 300/초 손실 됨</span><span class="sxs-lookup"><span data-stu-id="01383-215">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="01383-216">데이터 프록시</span><span class="sxs-lookup"><span data-stu-id="01383-216">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="01383-217">제한 된 서버 연결 &lt; 3</span><span class="sxs-lookup"><span data-stu-id="01383-217">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="01383-218">시스템이 조절 &lt; 1</span><span class="sxs-lookup"><span data-stu-id="01383-218">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="01383-219">SIP 스택</span><span class="sxs-lookup"><span data-stu-id="01383-219">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="01383-220">제한을 초과 하는 연결 삭제 &lt; 1</span><span class="sxs-lookup"><span data-stu-id="01383-220">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="01383-221">전송 시간 초과 &lt; 10</span><span class="sxs-lookup"><span data-stu-id="01383-221">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="01383-222">흐름 제어 연결 &lt; 100</span><span class="sxs-lookup"><span data-stu-id="01383-222">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="01383-223">들어오는 요청 &lt; 1/초 손실</span><span class="sxs-lookup"><span data-stu-id="01383-223">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="01383-224">평균 메시지 처리 &lt; 3 초</span><span class="sxs-lookup"><span data-stu-id="01383-224">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="01383-225">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01383-225">See Also</span></span>


[<span data-ttu-id="01383-226">Lync Server 네트워킹 가이드</span><span class="sxs-lookup"><span data-stu-id="01383-226">Lync Server Networking Guide</span></span>](https://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="01383-227">주요 상태 지표: 정상 Lync Server를 유지 관리 하기 위한 기본 사항</span><span class="sxs-lookup"><span data-stu-id="01383-227">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](https://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="01383-228">Lync 통화 품질 방법론</span><span class="sxs-lookup"><span data-stu-id="01383-228">Lync Call Quality Methodology</span></span>](https://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

