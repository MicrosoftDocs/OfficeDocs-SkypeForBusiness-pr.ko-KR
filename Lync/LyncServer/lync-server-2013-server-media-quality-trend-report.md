---
title: 'Lync Server 2013: 서버 미디어 품질 추세 보고서'
description: 'Lync Server 2013: 서버 미디어 품질 추세 보고서'
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
ms.openlocfilehash: e7ac2482b967aab230c5522c2b6a76e10ced28e7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578141"
---
# <a name="server-media-quality-trend-report-in-lync-server-2013"></a><span data-ttu-id="307d9-103">Lync Server 2013의 서버 미디어 품질 추세 보고서</span><span class="sxs-lookup"><span data-stu-id="307d9-103">Server Media Quality Trend Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="307d9-104">_**마지막으로 수정 된 항목:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="307d9-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="307d9-p101">서버 미디어 품질 추세 보고서는 통화량, 불량 통화율, 패킷 손실 및 지터와 같은 QoE(체감 품질) 메트릭으로 최대 5개 서버를 그래픽적으로 비교할 수 있는 방법을 제공합니다. 이를 통해 성능 품질이 낮은 서버, 활용률이 낮은 서버, 초과 사용되는 서버 등을 쉽게 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p101">The Server Media Quality Trend Report provides a way for you to graphically compare up to 5 servers on Quality of Experience metrics such as call volume, poor call percentage, packet loss, and jitter. This makes it easier to do such things as identify servers that are performing poorly, identify servers that are underutilized, or identify servers that are being overused.</span></span>

<div>

## <a name="accessing-the-server-media-quality-trend-report"></a><span data-ttu-id="307d9-107">서버 미디어 품질 추세 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="307d9-107">Accessing the Server Media Quality Trend Report</span></span>

<span data-ttu-id="307d9-108">서버 미디어 품질 추세 보고서는 다음 보고서 중 하나에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-108">The Server Media Quality Trend Report can be accessed from either one of the following report:</span></span>

  - <span data-ttu-id="307d9-109">[Lync server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) (추세 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="307d9-109">[Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) (by clicking the Trend metric)</span></span>

  - <span data-ttu-id="307d9-110">[Lync server 2013의 통화 정보 보고서](lync-server-2013-call-detail-report.md) (A/V에 지 서버 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="307d9-110">[Call Detail Report in Lync Server 2013](lync-server-2013-call-detail-report.md) (by clicking the A/V edge server metric.</span></span> <span data-ttu-id="307d9-111">발신자 또는 수신자가 서버인 경우 끝점 이름을 클릭하여 서버 품질 미디어 추세 보고서에 연결할 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="307d9-111">If the caller or callee is a server, you can also reach the Server Quality Media Trend Report by clicking the endpoint name.)</span></span>

</div>

<div>

## <a name="making-the-best-use-of-server-media-quality-trend-report"></a><span data-ttu-id="307d9-112">서버 미디어 품질 추세 보고서 활용</span><span class="sxs-lookup"><span data-stu-id="307d9-112">Making the Best Use of Server Media Quality Trend Report</span></span>

<span data-ttu-id="307d9-113">특정 서버에 대 한 [Lync server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) 에서 추세 메트릭을 클릭 하면 서버 미디어 품질 추세 보고서가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-113">When you click the Trend metric on the [Server Performance Report in Lync Server 2013](lync-server-2013-server-performance-report.md) for a specific server, the Server Media Quality Trend Report will open.</span></span> <span data-ttu-id="307d9-114">그러나 해당 보고서의 빈 인스턴스만 표시 됩니다. 서버 성능 보고서에서 선택한 서버가 화면에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-114">However, you will see only a blank instance of that report; the server you selected on the Server Performance Report will not be displayed onscreen.</span></span> <span data-ttu-id="307d9-115">대신 서버 드롭다운에서 해당 서버를 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-115">Instead, you will need to select that server from the Servers dropdown.</span></span> <span data-ttu-id="307d9-116">서버 드롭다운에서 모두 선택 옵션이 포함 되어 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-116">Note, too that the Servers dropdown includes a Select All option.</span></span> <span data-ttu-id="307d9-117">서버 수가 5 개를 넘으면이 옵션이 작동 하지 않습니다. 서버 미디어 품질 추세 보고서에는 한 번에 최대 5 대의 서버 데이터만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-117">This option will not work if you have more than 5 servers; the Server Media Quality Trend Report can only display data for a maximum of 5 servers at a time.</span></span>

<span data-ttu-id="307d9-118">서버 미디어 품질 추세 보고서에 표시 되는 그래프에는 통화 량 및 불량 통화 율 레이블이 지정 된 점수가 hotlinks. 그래프에서 점을 클릭 하면 [Lync Server 2013의 통화 목록 보고서](lync-server-2013-call-list-report.md) 인스턴스가 지정 된 기간 동안 총 통화 (또는 불량 통화)를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-118">On the graphs displayed by the Server Media Quality Trend Report, the points labeled Call Volume and Poor Call Percentage are hotlinks; clicking a point on the graph will open an instance of the [Call List Report in Lync Server 2013](lync-server-2013-call-list-report.md) showing the total calls (or poor calls) for the specified time period.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="307d9-119">필터</span><span class="sxs-lookup"><span data-stu-id="307d9-119">Filters</span></span>

<span data-ttu-id="307d9-p104">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 서버 미디어 품질 추세 보고서에 사용할 수 있는 필터 목록을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p104">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-filters"></a><span data-ttu-id="307d9-122">서버 미디어 품질 추세 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="307d9-122">Server Media Quality Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="307d9-123">이름</span><span class="sxs-lookup"><span data-stu-id="307d9-123">Name</span></span></th>
<th><span data-ttu-id="307d9-124">설명</span><span class="sxs-lookup"><span data-stu-id="307d9-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="307d9-125"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-125"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-p105">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p105">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="307d9-128">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="307d9-128">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="307d9-p106">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p106">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="307d9-131">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="307d9-131">7/7/2012</span></span></p>
<p><span data-ttu-id="307d9-132">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-132">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="307d9-133">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="307d9-133">7/3/2012</span></span></p>
<p><span data-ttu-id="307d9-134">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-134">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="307d9-135"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-135"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-p107">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p107">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="307d9-138">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="307d9-138">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="307d9-p108">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p108">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="307d9-141">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="307d9-141">7/7/2012</span></span></p>
<p><span data-ttu-id="307d9-142">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-142">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="307d9-143">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="307d9-143">7/3/2012</span></span></p>
<p><span data-ttu-id="307d9-144">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-144">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="307d9-145"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-145"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-p109">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p109">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="307d9-148">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="307d9-148">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="307d9-149">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="307d9-149">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="307d9-150">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="307d9-150">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="307d9-p110">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p110">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 8/7/2012 and an end date of 9/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="307d9-153"><strong>서버 유형</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-153"><strong>Server type</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-p111">통화에 포함된 서버 유형입니다. 허용되는 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p111">Type of server involved in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="307d9-156">중재 서버</span><span class="sxs-lookup"><span data-stu-id="307d9-156">Mediation Server</span></span></p></li>
<li><p><span data-ttu-id="307d9-157">A/V 회의 서버</span><span class="sxs-lookup"><span data-stu-id="307d9-157">A/V Conferencing Server</span></span></p></li>
<li><p><span data-ttu-id="307d9-158">A/V 에지 서버</span><span class="sxs-lookup"><span data-stu-id="307d9-158">A/V Edge Server</span></span></p></li>
<li><p><span data-ttu-id="307d9-159">게이트웨이(중재 서버)</span><span class="sxs-lookup"><span data-stu-id="307d9-159">Gateway (Mediation Server)</span></span></p></li>
<li><p><span data-ttu-id="307d9-160">게이트웨이(중재 서버 바이패스)</span><span class="sxs-lookup"><span data-stu-id="307d9-160">Gateway (Mediation Server Bypass)</span></span></p></li>
<li><p><span data-ttu-id="307d9-161">AS 회의 서버</span><span class="sxs-lookup"><span data-stu-id="307d9-161">AS Conferencing Server</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="307d9-162"><strong>서버</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-162"><strong>Servers</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-p112">세션에 포함된 서버 이름입니다. 이 드롭다운 목록은 서버 유형 필터 값에 따라 자동으로 채워집니다. 보고서를 컴파일할 때는 최대 5개의 서버를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p112">Name of the server involved in the session; this dropdown list is automatically populated for you based on the value of the Server type filter. You can select up to 5 different servers when compiling a report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="307d9-165"><strong>액세스 유형</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-165"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-p113">참가자가 내부 네트워크 또는 외부 네트워크에 로그온되었는지 여부를 나타냅니다. 허용된 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p113">Indicates whether the participant was logged on to the internal network or from the external network. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="307d9-168">모든</span><span class="sxs-lookup"><span data-stu-id="307d9-168">[All]</span></span></p></li>
<li><p><span data-ttu-id="307d9-169">내부</span><span class="sxs-lookup"><span data-stu-id="307d9-169">Internal</span></span></p></li>
<li><p><span data-ttu-id="307d9-170">외부</span><span class="sxs-lookup"><span data-stu-id="307d9-170">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="307d9-171"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-171"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-p114">참가자가 연결된 네트워크 유형을 나타냅니다. 허용된 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p114">Indicates the type of network the participant was connected to. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="307d9-174">모든</span><span class="sxs-lookup"><span data-stu-id="307d9-174">[All]</span></span></p></li>
<li><p><span data-ttu-id="307d9-175">유선</span><span class="sxs-lookup"><span data-stu-id="307d9-175">Wired</span></span></p></li>
<li><p><span data-ttu-id="307d9-176">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="307d9-176">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="307d9-177"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-177"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-p115">세션 중 외부 참가자가 VPN(가상 사설망) 연결을 사용 중이었는지를 나타냅니다. 허용된 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p115">Indicates whether an external participant was using a virtual private network (VPN) connection during the session. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="307d9-180">모든</span><span class="sxs-lookup"><span data-stu-id="307d9-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="307d9-181">VPN</span><span class="sxs-lookup"><span data-stu-id="307d9-181">VPN</span></span></p></li>
<li><p><span data-ttu-id="307d9-182">비 VPN</span><span class="sxs-lookup"><span data-stu-id="307d9-182">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="307d9-183">메트릭</span><span class="sxs-lookup"><span data-stu-id="307d9-183">Metrics</span></span>

<span data-ttu-id="307d9-184">다음 표에서는 서버 미디어 품질 추세 보고서에 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-184">The following table lists the information provided in the Server Media Quality Trend Report.</span></span>

### <a name="server-media-quality-trend-report-metrics"></a><span data-ttu-id="307d9-185">서버 미디어 품질 추세 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="307d9-185">Server Media Quality Trend Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="307d9-186">이름</span><span class="sxs-lookup"><span data-stu-id="307d9-186">Name</span></span></th>
<th><span data-ttu-id="307d9-187">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="307d9-187">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="307d9-188">설명</span><span class="sxs-lookup"><span data-stu-id="307d9-188">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="307d9-189"><strong>통화량</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-189"><strong>Call volume</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-190">아니요</span><span class="sxs-lookup"><span data-stu-id="307d9-190">No</span></span></p></td>
<td><p><span data-ttu-id="307d9-191">총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-191">Total number of calls.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="307d9-192"><strong>저하(MOS)</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-192"><strong>Degradation (MOS)</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-193">아니요</span><span class="sxs-lookup"><span data-stu-id="307d9-193">No</span></span></p></td>
<td><p><span data-ttu-id="307d9-194">통화 중에 발생 하는 평균 MOS (평균 옵션 점수) 성능 저하입니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-194">Average amount of MOS (mean option score) degradation experienced during a call.</span></span> <span data-ttu-id="307d9-195">성능 저하 값의 범위는 0.0 개에서 높은 5.0 까지입니다. 값이 0.5 이하인 경우 허용 되는 저하를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-195">Degradation values can range from a low of 0.0 to a high of 5.0; a value of 0.5 or less represents acceptable degradation.</span></span> <span data-ttu-id="307d9-196">현재까지 평균 평가점은 사용자가 1부터 5까지 통화 품질에 대한 점수를 스스로 매기게 하여 계산되었습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-196">Historically, mean options scores were calculated by having users rate the quality of a call on a scale of 1-to-5.</span></span> <span data-ttu-id="307d9-197">Lync Server에서는 사용자가 통화를 평가 하는 방법을 예측 하기 위한 알고리즘 집합을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-197">Lync Server uses a set of algorithms to predict how users would have rated a call.</span></span></p>
<p><span data-ttu-id="307d9-p117">정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버 또는 끝점의 과부하 등의 경우에는 저하 값이 높게 나타날 수 있습니다. 저하 값이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p117">High degradation values can be caused by congestion; lack of bandwidth; wireless congestion or interference, or an overloaded media server or endpoint. High degradation results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="307d9-200"><strong>불량 통화율</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-200"><strong>Poor call percentage</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-201">아니요</span><span class="sxs-lookup"><span data-stu-id="307d9-201">No</span></span></p></td>
<td><p><span data-ttu-id="307d9-p118">불량으로 분류된 총 통화 수입니다. 불량 통화는 측정된 메트릭 중 적어도 하나 이상이 허용 값을 초과하는 모든 통화입니다(예: 지터가 과도하게 발생한 통화).</span><span class="sxs-lookup"><span data-stu-id="307d9-p118">The total number of calls classified as poor. A poor call is any call which at least one of the measured metrics exceeded the allowed value (for example, a call that experienced excessive jitter).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="307d9-204"><strong>왕복(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-204"><strong>Round trip (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-205">아니요</span><span class="sxs-lookup"><span data-stu-id="307d9-205">No</span></span></p></td>
<td><p><span data-ttu-id="307d9-p119">RTP(실시간 전송 프로토콜) 패킷이 다른 끝점으로 이동한 후 다시 돌아오는 데 걸리는 평균 시간(밀리초)입니다. 적정 품질의 왕복 시간은 약 200밀리초 미만 정도로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p119">Average amount of time (in milliseconds) required for a Real-Time Transport Protocol packet to travel to one endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="307d9-p120">국제 통화 라우팅, 잘못된 라우팅 구성 또는 미디어 서버 과부하 등으로 인해 왕복 값이 높게 발생할 수 있습니다. 왕복 시간이 높으면 양방향 실시간 오디오 대화가 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p120">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="307d9-210"><strong>패킷 손실</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-210"><strong>Packet loss</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-211">아니요</span><span class="sxs-lookup"><span data-stu-id="307d9-211">No</span></span></p></td>
<td><p><span data-ttu-id="307d9-p121">RTP(Real-time Transport Protocol) 패킷 손실의 평균 비율입니다. (패킷 손실은 RTP 패킷, 인터넷을 통한 오디오 및 비디오 전송을 위해 사용되는 프로토콜인 RTP 패킷이 해당 목적지에 도달하지 못했을 때 발생합니다.) 정체 현상, 대역폭 부족, 무선 통화 정체 또는 간섭, 미디어 서버의 과부하 등의 경우에는 손실률이 높게 나타날 수 있습니다. 패킷 손실률이 높으면 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p121">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="307d9-215"><strong>지터(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-215"><strong>Jitter (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-216">아니요</span><span class="sxs-lookup"><span data-stu-id="307d9-216">No</span></span></p></td>
<td><p><span data-ttu-id="307d9-217">RTP 패킷 도착 시간 사이에 발견된 평균 지터입니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-217">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="307d9-218">(지터는 통화의 shakiness을 측정 한 것 &quot; &quot; 입니다.) 높은 지터 값은 일반적으로 혼잡 또는 오버 로드 된 미디어 서버로 인해 발생 하며 오디오가 왜곡 되거나 손실 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-218">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="307d9-219"><strong>힐러 숨김 비율</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-219"><strong>Healer concealed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-220">아니요</span><span class="sxs-lookup"><span data-stu-id="307d9-220">No</span></span></p></td>
<td><p><span data-ttu-id="307d9-p123">총 오디오 샘플 수에 대한 숨겨진 평균 오디오 샘플 비율입니다. (숨겨진 오디오 샘플은 손실된 네트워크 패킷으로 인해 발생하는 갑작스러운 전환을 매끄럽게 조정하기 위해 사용되는 기술입니다.) 값이 높으면 패킷 손실이나 지터로 인해 적용된 손실 숨김 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p123">Average ratio of concealed audio samples to the total to the total number of samples. (A concealed audio sample is a technique used to smooth out the abrupt transition that would usually be caused by dropped network packets.) High values indicate significant levels of loss concealment applied caused by packet loss or jitter, and results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="307d9-223"><strong>힐러 늘임 비율</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-223"><strong>Healer stretched ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-224">아니요</span><span class="sxs-lookup"><span data-stu-id="307d9-224">No</span></span></p></td>
<td><p><span data-ttu-id="307d9-p124">총 오디오 샘플 수에 대한 늘어진 평균 오디오 샘플 비율입니다. (늘어진 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 연장되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 늘림 수준이 높음을 의미하며 이로 인해 오디오가 왜곡되거나 끊깁니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p124">Average ratio of stretched audio samples to the total to the total number of samples. (Stretched audio is audio that has been expanded to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample stretching caused by jitter, and result in audio sounding robotic or distorted.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="307d9-227"><strong>힐러 압축 비율</strong></span><span class="sxs-lookup"><span data-stu-id="307d9-227"><strong>Healer compressed ratio</strong></span></span></p></td>
<td><p><span data-ttu-id="307d9-228">아니요</span><span class="sxs-lookup"><span data-stu-id="307d9-228">No</span></span></p></td>
<td><p><span data-ttu-id="307d9-p125">총 샘플 수에 대한 압축된 평균 오디오 샘플 비율입니다. (압축된 오디오는 손실된 네트워크 패킷이 감지되었을 때 통화 품질을 유지하기 위해 압축되는 오디오입니다.) 값이 높으면 지터로 인해 샘플 압축 수준이 높음을 의미하며 이로 인해 오디오가 빠르게 들리거나 왜곡됩니다.</span><span class="sxs-lookup"><span data-stu-id="307d9-p125">Average ratio of compressed audio samples to the total number of samples. (Compressed audio is audio that has been compressed to help maintain call quality when a dropped network packet has been detected.) High values indicate significant levels of sample compression caused by jitter, and result in audio sounding accelerated or distorted.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

