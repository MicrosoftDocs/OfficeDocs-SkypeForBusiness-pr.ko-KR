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
ms.openlocfilehash: 812ce68c84f86250fd25cc646bbcd5faddf0e566
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="key-health-indicators-in-lync-server-2013"></a><span data-ttu-id="21d1d-102">Lync Server 2013의 주요 상태 표시기</span><span class="sxs-lookup"><span data-stu-id="21d1d-102">Key Health Indicators in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21d1d-103">_**마지막으로 수정한 주제:** 2014-02-10_</span><span class="sxs-lookup"><span data-stu-id="21d1d-103">_**Topic Last Modified:** 2014-02-10_</span></span>

<span data-ttu-id="21d1d-104">이 문서는 다운로드 센터에서 다운로드할 수 있는 [정상적인 Lync server 포스터를 유지 관리 하는 주요 상태 표시기](http://go.microsoft.com/fwlink/?linkid=391838) 와 함께 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-104">This article is a companion to the [Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers](http://go.microsoft.com/fwlink/?linkid=391838) poster, which you can download from the Download Center.</span></span>

<span data-ttu-id="21d1d-105">![KHI 데이터를 사용하는 문제 해결에 대해 설명하는 포스터](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "KHI 데이터를 사용하는 문제 해결에 대해 설명하는 포스터")</span><span class="sxs-lookup"><span data-stu-id="21d1d-105">![Poster describing troubleshooting using KHI data](images/Dn594589.b6fe82bd-d70f-4c1f-a812-b615ac5fa7d7(OCS.15).jpg "Poster describing troubleshooting using KHI data")</span></span>

<span data-ttu-id="21d1d-106">이 포스터를 사용 하 여 키 상태 표시기 (KHIs), 사용자 환경 문제 발생을 목표로 하는 임계값을 갖는 성능 카운터에 대해 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-106">You can use this poster to learn about Key Health Indicators (KHIs), performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="21d1d-107">KHI 데이터 수집은 일반적으로 Lync 사용자에 게 고품질 오디오 환경을 제공 하는 데 초점을 맞춘 CQM (통화 품질 방법론)를 구현 하기 위한 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-107">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="21d1d-108">CQM를 사용 하는 방법에 대 한 질문이 있는 경우 cqmfeedback@microsoft.com에 질문을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-108">If you have questions about how to use CQM, you can submit your questions to cqmfeedback@microsoft.com.</span></span>

<span data-ttu-id="21d1d-109">포스터는 다음 영역에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-109">The poster explains the following areas:</span></span>

  - <span data-ttu-id="21d1d-110">주요 상태 지표는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="21d1d-110">What are Key Health Indicators?</span></span>

  - <span data-ttu-id="21d1d-111">KHI 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="21d1d-111">To Collect KHI Data</span></span>

  - <span data-ttu-id="21d1d-112">모든 서버 역할의 업데이트 관리 흐름</span><span class="sxs-lookup"><span data-stu-id="21d1d-112">Remediation Flow for all Server Roles</span></span>

  - <span data-ttu-id="21d1d-113">용어가</span><span class="sxs-lookup"><span data-stu-id="21d1d-113">Glossary</span></span>

  - <span data-ttu-id="21d1d-114">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="21d1d-114">Front-end Servers</span></span>

  - <span data-ttu-id="21d1d-115">백 엔드 SQL Server</span><span class="sxs-lookup"><span data-stu-id="21d1d-115">Backend SQL Servers</span></span>

  - <span data-ttu-id="21d1d-116">중재 서버</span><span class="sxs-lookup"><span data-stu-id="21d1d-116">Mediation Servers</span></span>

  - <span data-ttu-id="21d1d-117">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="21d1d-117">Edge Servers</span></span>

<span id="WhatIs"></span>

<div>

## <a name="what-are-key-health-indicators"></a><span data-ttu-id="21d1d-118">주요 상태 지표는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="21d1d-118">What are Key Health Indicators?</span></span>

<span data-ttu-id="21d1d-119">주요 상태 표시기는 사용자 환경 문제 노출을 목표로 하는 임계값을 갖는 성능 카운터입니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-119">Key Health Indicators are performance counters with thresholds aimed at revealing user experience issues.</span></span> <span data-ttu-id="21d1d-120">KHI 데이터 수집은 일반적으로 Lync 사용자에 게 고품질 오디오 환경을 제공 하는 데 초점을 맞춘 CQM (통화 품질 방법론)를 구현 하기 위한 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-120">Gathering KHI data is usually the first step to implementing the Call Quality Methodology (CQM), which is focused on ensuring a quality audio experience for Lync users.</span></span>

<span data-ttu-id="21d1d-121">KHIs는 표준 Lync 모니터링 솔루션 (예: System Center Operations Manager, 종합 트랜잭션, 모니터링 서버) 외에는 이러한 솔루션 대신 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-121">KHIs are used in addition to standard Lync Monitoring Solutions (e.g. System Center Operations Manager, Synthetic Transactions, Monitoring Server) and not instead of those solutions.</span></span>

<span data-ttu-id="21d1d-122">KHI 성능 카운터를 수집 하 고 네트워크 가이드와 함께 KHI 스프레드시트를 채워 Lync 배포의 서버 상태를 확인 하는 데 도움이 되는 성과 기록표를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-122">Collect the KHI performance counters and populate the KHI spreadsheet accompanying the Networking Guide to produce a scorecard that will help you determine the server health of a Lync deployment.</span></span> <span data-ttu-id="21d1d-123">채워진 후에는 환경을 복구 하는 과정을 안내 하 고 다른 관련자에 대 한 추가적인 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-123">Once populated, it guides you in repairing the environment and gives additional insight to other stakeholders.</span></span> <span data-ttu-id="21d1d-124">월 단위로 KHIs를 평가 하 고 모든 배포의 진행 중인 운영 프로세스에 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-124">Evaluate KHIs on a monthly basis and incorporate them into any deployment’s ongoing operational processes.</span></span>

<span data-ttu-id="21d1d-125">[Lync Server 네트워킹 가이드](http://go.microsoft.com/fwlink/p/?linkid=390677) 를 다운로드 하 여 모든 khis의 전체 목록을 확인 하 고 관련 스프레드시트를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-125">Download the [Lync Server Networking Guide](http://go.microsoft.com/fwlink/p/?linkid=390677) to see the full list of KHIs and to get the related spreadsheets.</span></span>

</div>

<span id="ToCollect"></span>

<div>

## <a name="to-collect-khi-data"></a><span data-ttu-id="21d1d-126">KHI 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="21d1d-126">To Collect KHI Data</span></span>

1.  <span data-ttu-id="21d1d-127">각 Lync Server의 Lync Server 네트워킹 가이드에 포함 된 KHI 스크립트를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-127">Run the KHI script included with the Lync Server Networking Guide on each Lync Server.</span></span> <span data-ttu-id="21d1d-128">이렇게 하면 성능 모니터 내부에 데이터 수집기가 생성 되 고 KHI의 이름을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-128">This will create a Data Collector inside of Performance Monitor and name it KHI.</span></span> <span data-ttu-id="21d1d-129">기본적으로 데이터는 15 초 마다 폴링됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-129">By default, data will be polled every 15 seconds.</span></span>

2.  <span data-ttu-id="21d1d-130">회사의 영업일 시작 전에 각 Lync 서버로 이동 하 여 KHI 데이터 수집기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-130">Before the start of your company's business day, go to each Lync Server and start the KHI Data Collector.</span></span>

3.  <span data-ttu-id="21d1d-131">이 날이 끝날 때 KHI 데이터 수집기를 중지 하 고 데이터를 중앙 위치에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-131">At the end of that day, stop the KHI Data Collector and copy the data to a central location.</span></span>

4.  <span data-ttu-id="21d1d-132">성능 모니터를 사용 하 여 Lync Server 네트워킹 가이드 다운로드에 포함 된 KHI 스프레드시트를 입력 한 후 추천 대상과 결과를 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-132">After using Performance Monitor to fill in the KHI spreadsheet included with the Lync Server Networking Guide download, compare the results to the recommended targets.</span></span>

</div>

<span id="Remidiation"></span>

<div>

## <a name="remediation-flow-for-all-server-roles"></a><span data-ttu-id="21d1d-133">모든 서버 역할의 업데이트 관리 흐름</span><span class="sxs-lookup"><span data-stu-id="21d1d-133">Remediation Flow for all Server Roles</span></span>

<span data-ttu-id="21d1d-134">Lync 구현의 각 서버에 대해 서버의 구성 요소 상태와 시스템 성능이 원하는 수준 이상 인지 확인 하는 것부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-134">For each server in your Lync implementation, begin by verifying that the server’s component health and system performance is at or above the desired level.</span></span> <span data-ttu-id="21d1d-135">그 이후에는 전체 Lync 구현에서 서버의 역할과 관련 된 표시기를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-135">Only after that should you look at the indicators relating to the server’s role in the overall Lync implementation.</span></span>

<span data-ttu-id="21d1d-136">먼저 모든 서버에 대 한 KHI 성능 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-136">Begin by collecting KHI Performance Data for all servers.</span></span> <span data-ttu-id="21d1d-137">각 시스템 역할 (이 문서의 뒷부분에 설명 된 세부 정보)에 대해 기본 시스템 구성 요소가 권장 대상에 맞는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-137">For each of the system roles (details discussed later in this document) determine whether the basic system components meet the recommended targets.</span></span> <span data-ttu-id="21d1d-138">그렇지 않은 경우 시스템 성능을 재구성 한 다음 KHI 데이터를 다시 수집 하 고 Lync 구현에서 서버의 역할에 대 한 메트릭을 확인 하기 전에 시스템 상태를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-138">If they do not, remediate the system performance then re-collect KHI data and ensure system health before looking at the metrics specific to the server’s role in the Lync implementation.</span></span> <span data-ttu-id="21d1d-139">모든 역할의 구성 요소 상태는 다음과 같이 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-139">Component health for all roles is defined as:</span></span>

  - <span data-ttu-id="21d1d-140">CPU 이용률 \< 80%</span><span class="sxs-lookup"><span data-stu-id="21d1d-140">CPU Utilization \< 80%</span></span>

  - <span data-ttu-id="21d1d-141">평균 디스크 쓰기 \< 10 밀리초</span><span class="sxs-lookup"><span data-stu-id="21d1d-141">Avg. Disk Write \< 10 ms</span></span>

  - <span data-ttu-id="21d1d-142">평균 디스크 읽기 \< 10 밀리초</span><span class="sxs-lookup"><span data-stu-id="21d1d-142">Avg. Disk Read \< 10 ms</span></span>

  - <span data-ttu-id="21d1d-143">사용 가능한 \>메모리 20% 시스템 총 MB</span><span class="sxs-lookup"><span data-stu-id="21d1d-143">Available memory \>20% System Total MB</span></span>

  - <span data-ttu-id="21d1d-144">네트워크 대기열 길이 \< 2</span><span class="sxs-lookup"><span data-stu-id="21d1d-144">Network Queue Length \< 2</span></span>

  - <span data-ttu-id="21d1d-145">버림 패킷 (in/out) = 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-145">Discarded Packets (in / out) = 0</span></span>

</div>

<span id="Glossary"></span>

<div>

## <a name="glossary"></a><span data-ttu-id="21d1d-146">용어가</span><span class="sxs-lookup"><span data-stu-id="21d1d-146">Glossary</span></span>

<span data-ttu-id="21d1d-147">이 포스터에 사용 되는 용어와 머리글자어는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-147">The following terms and acronyms are used in this poster:</span></span>

<span data-ttu-id="21d1d-148">MCU = Application 공유 다중 소수점 제어 단위</span><span class="sxs-lookup"><span data-stu-id="21d1d-148">AS MCU = Application Sharing Multi-point Control Unit</span></span>

<span data-ttu-id="21d1d-149">AV MCU = 오디오/비디오 MCU</span><span class="sxs-lookup"><span data-stu-id="21d1d-149">AV MCU = Audio/Video MCU</span></span>

<span data-ttu-id="21d1d-150">IM MCU = 인스턴트 메시지 MCU</span><span class="sxs-lookup"><span data-stu-id="21d1d-150">IM MCU = Instant Messaging MCU</span></span>

<span data-ttu-id="21d1d-151">통합 커뮤니케이션 웹 API</span><span class="sxs-lookup"><span data-stu-id="21d1d-151">UCWA = Unified Communications Web API</span></span>

<span data-ttu-id="21d1d-152">AV 가장자리 = Edge를 통한 오디오/비디오의 트래버스</span><span class="sxs-lookup"><span data-stu-id="21d1d-152">AV Edge = Traversal of audio/video via edge</span></span>

<span data-ttu-id="21d1d-153">AV 인증 = 오디오/비디오 인증</span><span class="sxs-lookup"><span data-stu-id="21d1d-153">AV Auth = Audio/Video Authentication</span></span>

<span data-ttu-id="21d1d-154">SIP 스택 = Lync의 코어 SIP 구현을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-154">SIP Stack = Contains Lync’s core SIP implementation</span></span>

<span data-ttu-id="21d1d-155">데이터 프록시 = edge 회의에 사용 됨</span><span class="sxs-lookup"><span data-stu-id="21d1d-155">Data Proxy = Used for edge conferencing</span></span>

<span data-ttu-id="21d1d-156">LySS = Lync 저장소 서비스</span><span class="sxs-lookup"><span data-stu-id="21d1d-156">LySS = Lync Storage Service</span></span>

</div>

<span id="Front"></span>

<div>

## <a name="front-end-servers"></a><span data-ttu-id="21d1d-157">프런트 엔드 서버</span><span class="sxs-lookup"><span data-stu-id="21d1d-157">Front-end Servers</span></span>

<span data-ttu-id="21d1d-158">다음과 같은 권장 KHI는 기본 구성 요소 상태 외에도 프런트 엔드 서버에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-158">The following recommended KHI targets are specific to front-end servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21d1d-159">기능 영역</span><span class="sxs-lookup"><span data-stu-id="21d1d-159">Functional area</span></span></th>
<th><span data-ttu-id="21d1d-160">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="21d1d-160">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21d1d-161">AS/AV/메신저 MCU</span><span class="sxs-lookup"><span data-stu-id="21d1d-161">AS/AV/IM MCU</span></span></p></td>
<td><p><span data-ttu-id="21d1d-162">MCU 상태 &lt;2</span><span class="sxs-lookup"><span data-stu-id="21d1d-162">MCU Health State &lt;2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21d1d-163">웹 구성 요소</span><span class="sxs-lookup"><span data-stu-id="21d1d-163">Web Components</span></span></p></td>
<td><p><span data-ttu-id="21d1d-164">메일 그룹 확장 광고 시간 &lt;제한 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-164">Distribution List expansion AD timeouts &lt;0</span></span></p>
<p><span data-ttu-id="21d1d-165">ABWQ 오류 = 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-165">ABWQ failures = 0</span></span></p>
<p><span data-ttu-id="21d1d-166">LIS 오류 = 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-166">LIS failures = 0</span></span></p>
<p><span data-ttu-id="21d1d-167">인증 오류 &lt; 1/초</span><span class="sxs-lookup"><span data-stu-id="21d1d-167">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="21d1d-168">ASP.NET v4 요청이 거부 됨 = 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-168">ASP.NET v4 Requests Rejected = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21d1d-169">SIP 스택</span><span class="sxs-lookup"><span data-stu-id="21d1d-169">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="21d1d-170">평균 수신 메시지 처리 &lt; 1 초</span><span class="sxs-lookup"><span data-stu-id="21d1d-170">Avg. Incoming Message Processing &lt; 1 sec</span></span></p>
<p><span data-ttu-id="21d1d-171">수신 응답 손실 &lt; 됨 1/초 수신 요청이 &lt; 1 초/초로 삭제 됨</span><span class="sxs-lookup"><span data-stu-id="21d1d-171">Incoming Responses Dropped &lt; 1/sec Incoming Requests Dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="21d1d-172">대기열 지연 &lt; 100 ms</span><span class="sxs-lookup"><span data-stu-id="21d1d-172">Queue Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="21d1d-173">프로시저를 &lt; 통해 대기 시간 100 ms</span><span class="sxs-lookup"><span data-stu-id="21d1d-173">Sproc Latency &lt; 100 ms</span></span></p>
<p><span data-ttu-id="21d1d-174">제한 되는 요청 = 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-174">Throttled Requests = 0</span></span></p>
<p><span data-ttu-id="21d1d-175">인증 오류 &lt; 1/초</span><span class="sxs-lookup"><span data-stu-id="21d1d-175">Authentication Errors &lt; 1/sec</span></span></p>
<p><span data-ttu-id="21d1d-176">받는 메시지가 시간 초과 &lt; 됨 2</span><span class="sxs-lookup"><span data-stu-id="21d1d-176">Incoming Messages Timed Out &lt; 2</span></span></p>
<p><span data-ttu-id="21d1d-177">평균 수신 메시지 대기 &lt; 1 초</span><span class="sxs-lookup"><span data-stu-id="21d1d-177">Avg. Incoming Message Hold &lt; 1 sec</span></span></p>
<p><span data-ttu-id="21d1d-178">흐름 제어 연결 &lt; 2</span><span class="sxs-lookup"><span data-stu-id="21d1d-178">Flow Controlled Connections &lt; 2</span></span></p>
<p><span data-ttu-id="21d1d-179">평균 아웃 대기열 지연 &lt; 2 초</span><span class="sxs-lookup"><span data-stu-id="21d1d-179">Avg. Out Queue Delay &lt; 2 sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21d1d-180">LySS</span><span class="sxs-lookup"><span data-stu-id="21d1d-180">LySS</span></span></p></td>
<td><p><span data-ttu-id="21d1d-181">저장소 서비스 DB &lt; 80에서 사용 된 공간의%</span><span class="sxs-lookup"><span data-stu-id="21d1d-181">% of space used by Storage Service DB &lt; 80</span></span></p>
<p><span data-ttu-id="21d1d-182">#복제 복제 실패 횟수 = 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-182"># of replica replication failures = 0</span></span></p>
<p><span data-ttu-id="21d1d-183">#데이터 손실 이벤트의 개수 = 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-183"># of data loss events = 0</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21d1d-184">TEST.SQL</span><span class="sxs-lookup"><span data-stu-id="21d1d-184">SQL</span></span></p></td>
<td><p><span data-ttu-id="21d1d-185">페이지 수명 예상 &gt; 300 초입니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-185">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="21d1d-186">일괄 처리 요청/ &lt; 초 2500</span><span class="sxs-lookup"><span data-stu-id="21d1d-186">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="BackEnd"></span>

<div>

## <a name="backend-sql-servers"></a><span data-ttu-id="21d1d-187">백 엔드 SQL Server</span><span class="sxs-lookup"><span data-stu-id="21d1d-187">Backend SQL Servers</span></span>

<span data-ttu-id="21d1d-188">다음과 같은 권장 KHI는 기본 구성 요소 상태 외에 SQL server에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-188">The following recommended KHI targets are specific to SQL servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21d1d-189">기능 영역</span><span class="sxs-lookup"><span data-stu-id="21d1d-189">Functional area</span></span></th>
<th><span data-ttu-id="21d1d-190">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="21d1d-190">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21d1d-191">TEST.SQL</span><span class="sxs-lookup"><span data-stu-id="21d1d-191">SQL</span></span></p></td>
<td><p><span data-ttu-id="21d1d-192">페이지 수명 예상 &gt; 300 초입니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-192">Page life expectancy &gt; 300 Sec.</span></span></p>
<p><span data-ttu-id="21d1d-193">일괄 처리 요청/ &lt; 초 2500</span><span class="sxs-lookup"><span data-stu-id="21d1d-193">Batch requests / sec &lt; 2500</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Mediation"></span>

<div>

## <a name="mediation-servers"></a><span data-ttu-id="21d1d-194">중재 서버</span><span class="sxs-lookup"><span data-stu-id="21d1d-194">Mediation Servers</span></span>

<span data-ttu-id="21d1d-195">다음과 같은 권장 KHI는 기본 구성 요소 상태 외에 중재 서버에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-195">The following recommended KHI targets are specific to mediation servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21d1d-196">기능 영역</span><span class="sxs-lookup"><span data-stu-id="21d1d-196">Functional area</span></span></th>
<th><span data-ttu-id="21d1d-197">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="21d1d-197">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21d1d-198">중재 서버 서비스</span><span class="sxs-lookup"><span data-stu-id="21d1d-198">Mediation Server Service</span></span></p></td>
<td><p><span data-ttu-id="21d1d-199">로드 통화 실패 인덱스 = 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-199">Load Call Failure Index = 0</span></span></p>
<p><span data-ttu-id="21d1d-200">프록시 &lt;10 때문에 실패 한 통화</span><span class="sxs-lookup"><span data-stu-id="21d1d-200">Failed Calls due to Proxy &lt;10</span></span></p>
<p><span data-ttu-id="21d1d-201">게이트웨이 &lt;10으로 인 한 통화 실패</span><span class="sxs-lookup"><span data-stu-id="21d1d-201">Failed Calls due to Gateway &lt;10</span></span></p>
<p><span data-ttu-id="21d1d-202">통화 (in 또는 out)가 거부 됨 = 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-202">Calls (in or out) rejected = 0</span></span></p>
<p><span data-ttu-id="21d1d-203">미디어 후보자 누락 = 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-203">Media Candidates missing = 0</span></span></p>
<p><span data-ttu-id="21d1d-204">미디어 연결 검사 실패 = 0</span><span class="sxs-lookup"><span data-stu-id="21d1d-204">Media Connectivity Check Failures = 0</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span id="Edge"></span>

<div>

## <a name="edge-servers"></a><span data-ttu-id="21d1d-205">Edge 서버</span><span class="sxs-lookup"><span data-stu-id="21d1d-205">Edge Servers</span></span>

<span data-ttu-id="21d1d-206">다음과 같은 권장 KHI는 기본 구성 요소 상태 외에도 edge 서버에만 해당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21d1d-206">The following recommended KHI targets are specific to edge servers in addition to basic component health:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="21d1d-207">기능 영역</span><span class="sxs-lookup"><span data-stu-id="21d1d-207">Functional area</span></span></th>
<th><span data-ttu-id="21d1d-208">대상 메트릭</span><span class="sxs-lookup"><span data-stu-id="21d1d-208">Target Metrics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="21d1d-209">AV 인증</span><span class="sxs-lookup"><span data-stu-id="21d1d-209">AV Auth</span></span></p></td>
<td><p><span data-ttu-id="21d1d-210">잘못 된 &lt; 요청 20/초</span><span class="sxs-lookup"><span data-stu-id="21d1d-210">Bad Requests &lt; 20/sec</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21d1d-211">AV 가장자리</span><span class="sxs-lookup"><span data-stu-id="21d1d-211">AV Edge</span></span></p></td>
<td><p><span data-ttu-id="21d1d-212">인증. 실패 &lt;20/초</span><span class="sxs-lookup"><span data-stu-id="21d1d-212">Auth. Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="21d1d-213">할당 실패 &lt;20/초</span><span class="sxs-lookup"><span data-stu-id="21d1d-213">Allocation Failures &lt;20/sec</span></span></p>
<p><span data-ttu-id="21d1d-214">패킷 300 &lt;/초 손실 됨</span><span class="sxs-lookup"><span data-stu-id="21d1d-214">Packets Dropped &lt;300/sec</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="21d1d-215">데이터 프록시</span><span class="sxs-lookup"><span data-stu-id="21d1d-215">Data Proxy</span></span></p></td>
<td><p><span data-ttu-id="21d1d-216">제한 서버 연결 &lt; 3</span><span class="sxs-lookup"><span data-stu-id="21d1d-216">Throttled Server connections &lt; 3</span></span></p>
<p><span data-ttu-id="21d1d-217">시스템의 스로틀 &lt;1</span><span class="sxs-lookup"><span data-stu-id="21d1d-217">System is Throttling &lt;1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="21d1d-218">SIP 스택</span><span class="sxs-lookup"><span data-stu-id="21d1d-218">SIP Stack</span></span></p></td>
<td><p><span data-ttu-id="21d1d-219">연결에 극한이 &lt; 생략 된 경우 1</span><span class="sxs-lookup"><span data-stu-id="21d1d-219">Connections over limit dropped &lt; 1</span></span></p>
<p><span data-ttu-id="21d1d-220">전송 시간 초과 &lt;10</span><span class="sxs-lookup"><span data-stu-id="21d1d-220">Sends timed out &lt;10</span></span></p>
<p><span data-ttu-id="21d1d-221">흐름 제어 연결 &lt;100</span><span class="sxs-lookup"><span data-stu-id="21d1d-221">Flow Controlled Connections &lt;100</span></span></p>
<p><span data-ttu-id="21d1d-222">수신 요청이 1 &lt; /초로 삭제 됨</span><span class="sxs-lookup"><span data-stu-id="21d1d-222">Incoming requests dropped &lt; 1/sec</span></span></p>
<p><span data-ttu-id="21d1d-223">평균 메시지 처리 &lt; 3 초</span><span class="sxs-lookup"><span data-stu-id="21d1d-223">Avg. Message Processing &lt; 3 sec</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21d1d-224">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21d1d-224">See Also</span></span>


[<span data-ttu-id="21d1d-225">Lync Server 네트워킹 가이드</span><span class="sxs-lookup"><span data-stu-id="21d1d-225">Lync Server Networking Guide</span></span>](http://go.microsoft.com/fwlink/p/?linkid=390677)  
[<span data-ttu-id="21d1d-226">주요 상태 표시기: 정상적인 Lync 서버를 유지 관리 하기 위한 토대</span><span class="sxs-lookup"><span data-stu-id="21d1d-226">Key Health Indicators: The Foundation for Maintaining Healthy Lync Servers</span></span>](http://go.microsoft.com/fwlink/?linkid=391838)  
[<span data-ttu-id="21d1d-227">Lync 통화 음질 방법</span><span class="sxs-lookup"><span data-stu-id="21d1d-227">Lync Call Quality Methodology</span></span>](http://go.microsoft.com/fwlink/?linkid=391841)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

