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
ms.openlocfilehash: 26f825a33eeb90817685c1694a5c6579110ffcd6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="location-trend-report-in-lync-server-2013"></a><span data-ttu-id="df662-102">Lync Server 2013의 위치 추세 보고서</span><span class="sxs-lookup"><span data-stu-id="df662-102">Location Trend Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="df662-103">_**마지막으로 수정한 주제:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="df662-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="df662-104">위치 추세 보고서는 네트워크 위치에 대 한 통화 품질 추세 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="df662-104">The Location Trend Report provides call quality trend information for network locations.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="df662-105">필터가</span><span class="sxs-lookup"><span data-stu-id="df662-105">Filters</span></span>

<span data-ttu-id="df662-106">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df662-106">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="df662-107">예를 들어 위치 추세 보고서를 사용 하면 액세스 형식 (즉, 간격 액세스와 외부 액세스) 또는 유선/무선 네트워크 연결을 통해 반환 된 데이터를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df662-107">For example, the Location Trend Report enables you to filter the returned data by such things as access type (that is, interval access vs. external access) or by wired/wireless network connection.</span></span> <span data-ttu-id="df662-108">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df662-108">You can also choose how data should be grouped.</span></span> <span data-ttu-id="df662-109">이 경우 통화는 시간, 일 또는 주별로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df662-109">In this case, calls are grouped by hour, day, or week.</span></span>

<span data-ttu-id="df662-110">다음 표에는 위치 추세 보고서와 함께 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df662-110">The following table lists the filters that you can use with the Location Trend Report.</span></span>

### <a name="location-trend-report-filters"></a><span data-ttu-id="df662-111">위치 추세 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="df662-111">Location Trend Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="df662-112">이름</span><span class="sxs-lookup"><span data-stu-id="df662-112">Name</span></span></th>
<th><span data-ttu-id="df662-113">설명</span><span class="sxs-lookup"><span data-stu-id="df662-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="df662-114"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="df662-114"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="df662-115">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="df662-115">Start date/time for the time range.</span></span> <span data-ttu-id="df662-116">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="df662-116">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="df662-117">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="df662-117">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="df662-118">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df662-118">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="df662-119">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="df662-119">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="df662-120">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="df662-120">7/7/2012</span></span></p>
<p><span data-ttu-id="df662-121">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="df662-121">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="df662-122">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="df662-122">7/3/2012</span></span></p>
<p><span data-ttu-id="df662-123">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df662-123">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df662-124"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="df662-124"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="df662-125">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="df662-125">End date/time for the time range.</span></span> <span data-ttu-id="df662-126">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="df662-126">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="df662-127">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="df662-127">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="df662-128">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df662-128">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="df662-129">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="df662-129">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="df662-130">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="df662-130">7/7/2012</span></span></p>
<p><span data-ttu-id="df662-131">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="df662-131">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="df662-132">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="df662-132">7/3/2012</span></span></p>
<p><span data-ttu-id="df662-133">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="df662-133">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df662-134"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="df662-134"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="df662-135">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="df662-135">Time interval.</span></span> <span data-ttu-id="df662-136">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="df662-136">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="df662-137">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="df662-137">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="df662-138">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="df662-138">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="df662-139">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="df662-139">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="df662-140">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="df662-140">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="df662-141">예를 들어 시작 날짜가 1/1/2011이 고 종료 날짜가 2/28/2011 인 일일 간격을 선택 하는 경우에는 8/1/2011 12:00 AM ~ 9/1/2011 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="df662-141">For example, if you select the Daily interval with a start date of 1/1/2011 and an end date of 2/28/2011, data is displayed for the days 8/1/2011 12:00 AM to 9/1/2011 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df662-142"><strong>Access 형식</strong></span><span class="sxs-lookup"><span data-stu-id="df662-142"><strong>Access type</strong></span></span></p></td>
<td><p><span data-ttu-id="df662-143">전화를 걸 때 클라이언트가 내부 네트워크 또는 외부 네트워크에 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df662-143">Indicates whether the client was logged on to the internal network or the external network when the call was placed.</span></span> <span data-ttu-id="df662-144">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="df662-144">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="df662-145">모든</span><span class="sxs-lookup"><span data-stu-id="df662-145">[All]</span></span></p></li>
<li><p><span data-ttu-id="df662-146">내부용</span><span class="sxs-lookup"><span data-stu-id="df662-146">Internal</span></span></p></li>
<li><p><span data-ttu-id="df662-147">내부</span><span class="sxs-lookup"><span data-stu-id="df662-147">External</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="df662-148"><strong>네트워크 유형</strong></span><span class="sxs-lookup"><span data-stu-id="df662-148"><strong>Network type</strong></span></span></p></td>
<td><p><span data-ttu-id="df662-149">전화를 걸 때 클라이언트가 연결 된 네트워크의 유형을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df662-149">Indicates the type of network the client was connected to when the call was placed.</span></span> <span data-ttu-id="df662-150">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="df662-150">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="df662-151">모든</span><span class="sxs-lookup"><span data-stu-id="df662-151">[All]</span></span></p></li>
<li><p><span data-ttu-id="df662-152">유</span><span class="sxs-lookup"><span data-stu-id="df662-152">Wired</span></span></p></li>
<li><p><span data-ttu-id="df662-153">Wireless-n</span><span class="sxs-lookup"><span data-stu-id="df662-153">Wireless</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="df662-154"><strong>VPN</strong></span><span class="sxs-lookup"><span data-stu-id="df662-154"><strong>VPN</strong></span></span></p></td>
<td><p><span data-ttu-id="df662-155">통화를 했을 때 외부 클라이언트가 VPN (가상 사설망) 연결을 사용 중인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="df662-155">Indicates whether an external client was using a virtual private network (VPN) connection when the call was placed.</span></span> <span data-ttu-id="df662-156">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="df662-156">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="df662-157">모든</span><span class="sxs-lookup"><span data-stu-id="df662-157">[All]</span></span></p></li>
<li><p><span data-ttu-id="df662-158">VPN</span><span class="sxs-lookup"><span data-stu-id="df662-158">VPN</span></span></p></li>
<li><p><span data-ttu-id="df662-159">비 VPN</span><span class="sxs-lookup"><span data-stu-id="df662-159">Non-VPN</span></span></p></li>
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

