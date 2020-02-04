---
title: 'Lync Server 2013: 서버 미디어 품질 추세 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Media Quality Trend Report
ms:assetid: 8a51fd13-1487-4632-b5ec-f7ae2abe8ed4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205071(v=OCS.15)
ms:contentKeyID: 48184760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4efb7e2f29c1da75a81f4df4ec586c396d77d3d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="d24fb-102">Lync Server 2013의 서버 미디어 품질 추세 보고서</span><span class="sxs-lookup"><span data-stu-id="d24fb-102">Server Media Quality Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d24fb-103">_**마지막으로 수정한 주제:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="d24fb-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="d24fb-104">서버 미디어 품질 추세 보고서에서는 통화 볼륨, 잘못 된 통화 비율, 패킷 손실 및 지터와 같은 경력 지표에 따라 최대 5 대의 서버를 그래픽으로 비교할 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-104">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter.</span></span> <span data-ttu-id="d24fb-105">이렇게 하면 성능이 좋지 않은 서버를 식별 하거나, 사용률이 낮은 서버를 식별 하거나, 과도 하는 서버를 식별 하는 등의 작업을 쉽게 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-105">This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="d24fb-106">서버 미디어 품질 추세 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="d24fb-106">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="d24fb-107">서버 미디어 품질 추세 보고서는 다음 보고서 중 하나에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-107">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="d24fb-108">[Lync server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) (추세 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="d24fb-108">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="d24fb-109">[Lync server 2013의 통화 세부 정보 보고서](lync-server-2013-call-detail-report.md) (A/V edge 서버 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="d24fb-109">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="d24fb-110">호출자 또는 호출 수신자가 서버인 경우 끝점 이름을 클릭 하 여 서버 품질 미디어 추세 보고서에 도달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-110">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="d24fb-111">서버 미디어 품질 추세 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="d24fb-111">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="d24fb-112">특정 서버에 대 한 [Lync server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) 에서 추세 메트릭을 클릭 하면 서버 미디어 품질 추세 보고서가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-112">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="d24fb-113">그러나 해당 보고서의 빈 인스턴스만 표시 됩니다. 서버 성능 보고서에서 선택한 서버는 화면에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-113">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="d24fb-114">대신 서버 드롭다운에서 해당 서버를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-114">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="d24fb-115">서버 드롭다운에서 모두 선택 옵션이 포함 되어 있는 것을 참고 하세요.</span><span class="sxs-lookup"><span data-stu-id="d24fb-115">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="d24fb-116">서버를 5 개 이상 보유 한 경우에는이 옵션이 작동 하지 않습니다. 서버 미디어 품질 추세 보고서는 한 번에 최대 5 대의 서버에 대 한 데이터만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-116">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="d24fb-117">서버 미디어 품질 추세 보고서에 표시 되는 그래프에서 통화 볼륨 및 잘못 된 통화 백분율 이라는 레이블이 붙은 포인트는 hotlinks입니다. 그래프의 점을 클릭 하면 [Lync Server 2013에서](lync-server-2013-call-list-report.md) 지정 된 기간 동안 발생 한 총 통화 (또는 잘못 된 통화)를 보여 주는 통화 목록 보고서의 인스턴스가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-117">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d24fb-118">필터가</span><span class="sxs-lookup"><span data-stu-id="d24fb-118">Filters</span></span>

<span data-ttu-id="d24fb-119">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-119">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="d24fb-120">다음 표에는 서버 미디어 품질 추세 보고서와 함께 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-120">The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="d24fb-121">서버 미디어 품질 추세 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="d24fb-121">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d24fb-122">이름</span><span class="sxs-lookup"><span data-stu-id="d24fb-122">Name</span></span></th>
<th><span data-ttu-id="d24fb-123">설명</span><span class="sxs-lookup"><span data-stu-id="d24fb-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d24fb-124"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-124"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-125">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-125">Start date/time for the time range.</span></span> <span data-ttu-id="d24fb-126">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-126">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="d24fb-127">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="d24fb-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d24fb-128">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-128">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d24fb-129">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-129">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d24fb-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d24fb-130">7/7/2012</span></span></p>
<p><span data-ttu-id="d24fb-131">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="d24fb-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d24fb-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d24fb-132">7/3/2012</span></span></p>
<p><span data-ttu-id="d24fb-133">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d24fb-134"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-134"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-135">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-135">End date/time for the time range.</span></span> <span data-ttu-id="d24fb-136">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-136">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="d24fb-137">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="d24fb-137">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="d24fb-138">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-138">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="d24fb-139">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-139">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="d24fb-140">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="d24fb-140">7/7/2012</span></span></p>
<p><span data-ttu-id="d24fb-141">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="d24fb-141">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="d24fb-142">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="d24fb-142">7/3/2012</span></span></p>
<p><span data-ttu-id="d24fb-143">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-143">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d24fb-144"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-144"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-145">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="d24fb-145">Time interval.</span></span> <span data-ttu-id="d24fb-146">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-146">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="d24fb-147">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d24fb-147">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d24fb-148">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d24fb-148">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="d24fb-149">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="d24fb-149">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="d24fb-150">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-150">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="d24fb-151">예를 들어 시작 날짜가 8/7/2012이 고 종료 날짜가 9/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-151">For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d24fb-152"><strong>서버 유형</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-152"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-153">통화와 관련 된 서버의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-153">Type of server involved in the call.</span></span> <span data-ttu-id="d24fb-154">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-154">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="d24fb-155">중재 서버</span><span class="sxs-lookup"><span data-stu-id="d24fb-155">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="d24fb-156">A/V 회의 서버</span><span class="sxs-lookup"><span data-stu-id="d24fb-156">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="d24fb-157">A/V에 지 서버</span><span class="sxs-lookup"><span data-stu-id="d24fb-157">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="d24fb-158">게이트웨이 (중재 서버)</span><span class="sxs-lookup"><span data-stu-id="d24fb-158">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="d24fb-159">게이트웨이 (중재 서버 무시)</span><span class="sxs-lookup"><span data-stu-id="d24fb-159">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="d24fb-160">회의 서버로</span><span class="sxs-lookup"><span data-stu-id="d24fb-160">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d24fb-161"><strong>서버</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-161"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-162">세션과 관련 된 서버의 이름입니다. 이 드롭다운 목록은 서버 유형 필터 값에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-162">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter.</span></span> <span data-ttu-id="d24fb-163">보고서를 컴파일할 때 최대 5 개의 다른 서버를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-163">You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d24fb-164"><strong>Access 형식</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-164"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-165">참가자가 내부 네트워크에 로그인 되었는지 외부 네트워크에 로그온 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-165">Indicates whether the participant was logged on to the internal network or from the external network.</span></span> <span data-ttu-id="d24fb-166">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-166">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="d24fb-167">모든</span><span class="sxs-lookup"><span data-stu-id="d24fb-167">[All]</span></span></p></li>
<li><p><span data-ttu-id="d24fb-168">내부용</span><span class="sxs-lookup"><span data-stu-id="d24fb-168">Internal</span></span></p></li>
<li><p><span data-ttu-id="d24fb-169">내부</span><span class="sxs-lookup"><span data-stu-id="d24fb-169">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d24fb-170"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-170"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-171">참가자가 연결 된 네트워크 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-171">Indicates the type of network the participant was connected to.</span></span> <span data-ttu-id="d24fb-172">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-172">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="d24fb-173">모든</span><span class="sxs-lookup"><span data-stu-id="d24fb-173">[All]</span></span></p></li>
<li><p><span data-ttu-id="d24fb-174">유</span><span class="sxs-lookup"><span data-stu-id="d24fb-174">Wired</span></span></p></li>
<li><p><span data-ttu-id="d24fb-175">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="d24fb-175">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d24fb-176"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-176"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-177">외부 참가자가 세션 중에 VPN (가상 사설망) 연결을 사용 하 고 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-177">Indicates whether an external participant was using a virtual private network (VPN) connection during the session.</span></span> <span data-ttu-id="d24fb-178">사용 가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-178">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="d24fb-179">모든</span><span class="sxs-lookup"><span data-stu-id="d24fb-179">[All]</span></span></p></li>
<li><p><span data-ttu-id="d24fb-180">VPN</span><span class="sxs-lookup"><span data-stu-id="d24fb-180">VPN</span></span></p></li>
<li><p><span data-ttu-id="d24fb-181">비 VPN</span><span class="sxs-lookup"><span data-stu-id="d24fb-181">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d24fb-182">매트릭스</span><span class="sxs-lookup"><span data-stu-id="d24fb-182">Metrics</span></span>

<span data-ttu-id="d24fb-183">다음 표에는 서버 미디어 품질 추세 보고서에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-183">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="d24fb-184">서버 미디어 품질 추세 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="d24fb-184">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d24fb-185">이름</span><span class="sxs-lookup"><span data-stu-id="d24fb-185">Name</span></span></th>
<th><span data-ttu-id="d24fb-186">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="d24fb-186">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d24fb-187">설명</span><span class="sxs-lookup"><span data-stu-id="d24fb-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d24fb-188"><strong>통화 볼륨</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-188"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-189">아니요</span><span class="sxs-lookup"><span data-stu-id="d24fb-189">No</span></span></p></td>
<td><p><span data-ttu-id="d24fb-190">총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-190">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d24fb-191"><strong>성능 저하 (SPECIALIST)</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-191"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-192">아니요</span><span class="sxs-lookup"><span data-stu-id="d24fb-192">No</span></span></p></td>
<td><p><span data-ttu-id="d24fb-193">통화 중에 발생 한 평균 SPECIALIST (평균 옵션 점수)의 감소 금액입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-193">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="d24fb-194">성능 저하 값의 범위는 0.0 ~ 5.0 ~ 높음이 하입니다. 0.5 이하의 값은 허용 되는 저하를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-194">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="d24fb-195">지금까지 평균 옵션 점수는 사용자가 1 ~ 5의 배율로 통화 품질을 평가할 수 있도록 하 여 계산 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-195">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="d24fb-196">Lync Server는 사용자가 통화를 평가 하는 방법을 예측 하는 알고리즘 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-196">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="d24fb-197">높은 성능 저하 값은 정체로 인해 발생할 수 있습니다. 대역폭 부족, 무선 혼잡 또는 간섭 또는 오버 로드 된 미디어 서버 또는 끝점.</span><span class="sxs-lookup"><span data-stu-id="d24fb-197">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint.</span></span> <span data-ttu-id="d24fb-198">품질이 높으면 오디오가 왜곡 되거나 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-198">High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d24fb-199"><strong>통화 불량 백분율</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-199"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-200">아니요</span><span class="sxs-lookup"><span data-stu-id="d24fb-200">No</span></span></p></td>
<td><p><span data-ttu-id="d24fb-201">불량으로 분류 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-201">The total number of calls classified as poor.</span></span> <span data-ttu-id="d24fb-202">잘못 된 통화는 측정 된 메트릭 중 적어도 하나가 허용 된 값 (예: 과도 한 지터)을 초과한 모든 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-202">A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d24fb-203"><strong>왕복 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-203"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-204">아니요</span><span class="sxs-lookup"><span data-stu-id="d24fb-204">No</span></span></p></td>
<td><p><span data-ttu-id="d24fb-205">실시간 전송 프로토콜 패킷이 한 종점으로 이동 하는 데 필요한 평균 시간 (밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-205">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back.</span></span> <span data-ttu-id="d24fb-206">200 밀리초 이하의 왕복 시간은 허용 되는 품질로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-206">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="d24fb-207">높은 라운드트립 값은 국제 통화 라우팅으로 인해 발생할 수 있습니다. 라우팅 구성이 잘못 되었습니다. 또는 오버 로드 된 미디어 서버.</span><span class="sxs-lookup"><span data-stu-id="d24fb-207">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="d24fb-208">왕복 시간이 높으면 양방향 실시간 음성 대화에서 문제가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-208">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d24fb-209"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-209"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-210">아니요</span><span class="sxs-lookup"><span data-stu-id="d24fb-210">No</span></span></p></td>
<td><p><span data-ttu-id="d24fb-211">RTP (실시간 전송 프로토콜) 패킷 손실의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-211">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="d24fb-212">(패킷 손실은 RTP 패킷, 인터넷에서 오디오 및 비디오를 전송 하는 데 사용 되는 프로토콜인 해당 목적지에 도달 하지 못한 경우에 발생 합니다.) 일반적으로 정체 때문에 손실률이 높습니다. 대역폭 부족, 무선 정체 또는 간섭. 또는 오버 로드 된 미디어 서버.</span><span class="sxs-lookup"><span data-stu-id="d24fb-212">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="d24fb-213">패킷 손실은 일반적으로 오디오의 왜곡 또는 분실을 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-213">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d24fb-214"><strong>지터 (ms)</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-214"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-215">아니요</span><span class="sxs-lookup"><span data-stu-id="d24fb-215">No</span></span></p></td>
<td><p><span data-ttu-id="d24fb-216">RTP 패킷 도착 간에 감지 된 평균 지터.</span><span class="sxs-lookup"><span data-stu-id="d24fb-216">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="d24fb-217">(지터는 통화의 &quot;shakiness&quot; 을 측정 하는 척도입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오를 왜곡 하거나 손실 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-217">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d24fb-218"><strong>Healer 숨겨진 비율</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-218"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-219">아니요</span><span class="sxs-lookup"><span data-stu-id="d24fb-219">No</span></span></p></td>
<td><p><span data-ttu-id="d24fb-220">총 샘플 수에 대 한 총 숨겨진 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-220">Average ratio of concealed audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="d24fb-221">(숨겨진 오디오 샘플은 일반적으로 손실 된 네트워크 패킷으로 인해 발생 하는 갑작스런 전환을 매끄럽게 하는 데 사용 되는 기술입니다.) 값이 높으면 패킷 손실률 또는 지터로 인해 적용 되는 손실 concealment의 상당 부분이 왜곡 되거나 손실 되는 결과를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-221">(A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d24fb-222"><strong>Healer 늘이기 비율</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-222"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-223">아니요</span><span class="sxs-lookup"><span data-stu-id="d24fb-223">No</span></span></p></td>
<td><p><span data-ttu-id="d24fb-224">총 샘플 수에 대 한 총 스트레치 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-224">Average ratio of stretched audio samples to the total to the total number of samples.</span></span> <span data-ttu-id="d24fb-225">(늘인 오디오는 손실 된 네트워크 패킷이 감지 될 때 통화 품질을 유지 하기 위해 확장 되어 있는 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 스트레치의 상당 수준을 나타내고, 오디오는 로보틱 또는 왜곡 될 때 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-225">(Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d24fb-226"><strong>Healer 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="d24fb-226"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="d24fb-227">아니요</span><span class="sxs-lookup"><span data-stu-id="d24fb-227">No</span></span></p></td>
<td><p><span data-ttu-id="d24fb-228">총 샘플 수에 대 한 압축 된 오디오 샘플의 평균 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-228">Average ratio of compressed audio samples to the total number of samples.</span></span> <span data-ttu-id="d24fb-229">(압축 오디오는 손실 된 네트워크 패킷이 감지 되었을 때 통화 품질을 유지 하기 위해 압축 된 오디오입니다.) 값이 높으면 지터로 인해 발생 하는 샘플 압축의 상당 부분이 표시 되 고 오디오의 가속 또는 왜곡이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d24fb-229">(Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

