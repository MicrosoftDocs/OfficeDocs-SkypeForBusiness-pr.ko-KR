---
title: 'Lync Server 2013: 위치 추세 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Location Trend Report
ms:assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204941(v=OCS.15)
ms:contentKeyID: 48184280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df3896704565a617ae4f50cfcc9afee29f5f098e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513775"
---
# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="cbfce-102">Lync Server 2013의 위치 추세 보고서</span><span class="sxs-lookup"><span data-stu-id="cbfce-102">Location Trend Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbfce-103">_**마지막으로 수정 된 항목:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="cbfce-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="cbfce-104">위치 추세 보고서는 네트워크 위치에 대한 통화 품질 추세 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="cbfce-105">필터</span><span class="sxs-lookup"><span data-stu-id="cbfce-105">Filters</span></span>

<span data-ttu-id="cbfce-p101">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 위치 추세 보고서에서는 액세스 유형(즉, 내부 액세스와 외부 액세스) 또는 유선/무선 네트워크 연결 등의 조건에 따라 반환되는 데이터를 필터링할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 통화는 시간, 일 또는 주별로 그룹이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-p101">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection. You can also choose how data should be grouped. In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="cbfce-110">다음 표에서는 위치 추세 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="cbfce-111">위치 추세 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="cbfce-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cbfce-112">이름</span><span class="sxs-lookup"><span data-stu-id="cbfce-112">Name</span></span></th>
<th><span data-ttu-id="cbfce-113">설명</span><span class="sxs-lookup"><span data-stu-id="cbfce-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cbfce-114"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="cbfce-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="cbfce-p102">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-p102">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="cbfce-117">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cbfce-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cbfce-p103">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cbfce-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cbfce-120">7/7/2012</span></span></p>
<p><span data-ttu-id="cbfce-121">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cbfce-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cbfce-122">7/3/2012</span></span></p>
<p><span data-ttu-id="cbfce-123">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbfce-124"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="cbfce-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="cbfce-p104">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-p104">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="cbfce-127">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cbfce-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cbfce-p105">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cbfce-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cbfce-130">7/7/2012</span></span></p>
<p><span data-ttu-id="cbfce-131">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cbfce-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cbfce-132">7/3/2012</span></span></p>
<p><span data-ttu-id="cbfce-133">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbfce-134"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="cbfce-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="cbfce-p106">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-p106">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbfce-137">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="cbfce-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="cbfce-138">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="cbfce-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="cbfce-139">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="cbfce-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="cbfce-p107">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값을 초과하면 시작 날짜로부터 최대한의 값 숫자만 표시됩니다. 예를 들어 일별 간격을 선택하고 시작 날짜가 1/1/2011이고 종료 날짜가 2/28/2011인 경우 8/1/2011 12:00 AM부터 9/1/2011 12:00 AM까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-p107">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbfce-142"><strong>액세스 유형</strong></span><span class="sxs-lookup"><span data-stu-id="cbfce-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="cbfce-p108">통화가 시도되었을 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온되어 있는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-p108">Indicates whether the client was logged on to the internal network or the external network when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbfce-145">모든</span><span class="sxs-lookup"><span data-stu-id="cbfce-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="cbfce-146">내부</span><span class="sxs-lookup"><span data-stu-id="cbfce-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="cbfce-147">외부</span><span class="sxs-lookup"><span data-stu-id="cbfce-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cbfce-148"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="cbfce-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="cbfce-p109">통화가 시도되었을 때 클라이언트가 연결된 네트워크의 유형을 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-p109">Indicates the type of network the client was connected to when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbfce-151">모든</span><span class="sxs-lookup"><span data-stu-id="cbfce-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="cbfce-152">유선</span><span class="sxs-lookup"><span data-stu-id="cbfce-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="cbfce-153">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="cbfce-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cbfce-154"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="cbfce-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="cbfce-p110">통화가 시도되었을 때 외부 클라이언트가 VPN(가상 사설망) 연결을 사용 중이었는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cbfce-p110">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="cbfce-157">모든</span><span class="sxs-lookup"><span data-stu-id="cbfce-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="cbfce-158">VPN</span><span class="sxs-lookup"><span data-stu-id="cbfce-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="cbfce-159">비 VPN</span><span class="sxs-lookup"><span data-stu-id="cbfce-159">Non-VPN</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

