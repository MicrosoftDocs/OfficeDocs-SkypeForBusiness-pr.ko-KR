---
title: 'Lync Server 2013: 전화 회의 요약 하위 보고서'
description: 'Lync Server 2013: 전화 회의 요약 하위 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0612ce1adb8a6b0fdea5e3bf70b88346f7c08044
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550694"
---
# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="cb4eb-103">Lync Server 2013의 전화 회의 요약 하위 보고서</span><span class="sxs-lookup"><span data-stu-id="cb4eb-103">Conference Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb4eb-104">_**마지막으로 수정 된 항목:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="cb4eb-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="cb4eb-p101">전화 회의 요약 하위 보고서에서는 실패한 전화 회의 세션에 대한 전반적인 정보를 제공합니다. 이와 같은 실패한 세션은 세션 유형(회의 센터 세션 및 MCU 세션)별로 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="cb4eb-107">필터</span><span class="sxs-lookup"><span data-stu-id="cb4eb-107">Filters</span></span>

<span data-ttu-id="cb4eb-p102">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 전화 회의 요약 하위 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="cb4eb-110">전화 회의 요약 하위 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="cb4eb-110">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb4eb-111">이름</span><span class="sxs-lookup"><span data-stu-id="cb4eb-111">Name</span></span></th>
<th><span data-ttu-id="cb4eb-112">설명</span><span class="sxs-lookup"><span data-stu-id="cb4eb-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb4eb-113"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="cb4eb-113"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="cb4eb-p103">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="cb4eb-116">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cb4eb-116">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cb4eb-p104">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cb4eb-119">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cb4eb-119">7/7/2012</span></span></p>
<p><span data-ttu-id="cb4eb-120">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-120">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cb4eb-121">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cb4eb-121">7/3/2012</span></span></p>
<p><span data-ttu-id="cb4eb-122">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-122">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb4eb-123"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="cb4eb-123"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="cb4eb-p105">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="cb4eb-126">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="cb4eb-126">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="cb4eb-p106">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="cb4eb-129">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="cb4eb-129">7/7/2012</span></span></p>
<p><span data-ttu-id="cb4eb-130">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-130">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="cb4eb-131">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="cb4eb-131">7/3/2012</span></span></p>
<p><span data-ttu-id="cb4eb-132">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-132">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb4eb-133"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="cb4eb-133"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="cb4eb-p107">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="cb4eb-137">메트릭</span><span class="sxs-lookup"><span data-stu-id="cb4eb-137">Metrics</span></span>

<span data-ttu-id="cb4eb-138">다음 표에서는 전화 회의 요약 하위 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-138">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="cb4eb-139">전화 회의 요약 하위 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="cb4eb-139">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cb4eb-140">이름</span><span class="sxs-lookup"><span data-stu-id="cb4eb-140">Name</span></span></th>
<th><span data-ttu-id="cb4eb-141">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="cb4eb-141">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="cb4eb-142">설명</span><span class="sxs-lookup"><span data-stu-id="cb4eb-142">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cb4eb-143"><strong>총 전화 회의</strong></span><span class="sxs-lookup"><span data-stu-id="cb4eb-143"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="cb4eb-144">아니요</span><span class="sxs-lookup"><span data-stu-id="cb4eb-144">No</span></span></p></td>
<td><p><span data-ttu-id="cb4eb-145">진행된 총 전화 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-145">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb4eb-146"><strong>총 전화 회의 세션</strong></span><span class="sxs-lookup"><span data-stu-id="cb4eb-146"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cb4eb-147">아니요</span><span class="sxs-lookup"><span data-stu-id="cb4eb-147">No</span></span></p></td>
<td><p><span data-ttu-id="cb4eb-p108">총 전화 회의 세션 수입니다. 전화 회의 하나에 여러 세션이 포함될 수 있습니다. 예를 들어 하나의 전화 회의가 회의 센터 세션과 MCU 세션을 둘 다 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb4eb-150"><strong>전체 세션 실패율</strong></span><span class="sxs-lookup"><span data-stu-id="cb4eb-150"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="cb4eb-151">아니요</span><span class="sxs-lookup"><span data-stu-id="cb4eb-151">No</span></span></p></td>
<td><p><span data-ttu-id="cb4eb-152">실패한 모든 전화 회의의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-152">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb4eb-153"><strong>회의 센터 세션</strong></span><span class="sxs-lookup"><span data-stu-id="cb4eb-153"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="cb4eb-154">아니요</span><span class="sxs-lookup"><span data-stu-id="cb4eb-154">No</span></span></p></td>
<td><p><span data-ttu-id="cb4eb-155">회의 센터 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-155">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb4eb-156"><strong>회의 센터 실패율</strong></span><span class="sxs-lookup"><span data-stu-id="cb4eb-156"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="cb4eb-157">아니요</span><span class="sxs-lookup"><span data-stu-id="cb4eb-157">No</span></span></p></td>
<td><p><span data-ttu-id="cb4eb-158">실패한 회의 센터 세션의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-158">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb4eb-159">MCU 세션</span><span class="sxs-lookup"><span data-stu-id="cb4eb-159">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="cb4eb-160">아니요</span><span class="sxs-lookup"><span data-stu-id="cb4eb-160">No</span></span></p></td>
<td><p><span data-ttu-id="cb4eb-161">MCU 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-161">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb4eb-162"><strong>MCU 실패율</strong></span><span class="sxs-lookup"><span data-stu-id="cb4eb-162"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="cb4eb-163">아니요</span><span class="sxs-lookup"><span data-stu-id="cb4eb-163">No</span></span></p></td>
<td><p><span data-ttu-id="cb4eb-164">실패한 MCU 세션의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-164">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cb4eb-165"><strong>형식별 MCU 세션</strong></span><span class="sxs-lookup"><span data-stu-id="cb4eb-165"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="cb4eb-166">아니요</span><span class="sxs-lookup"><span data-stu-id="cb4eb-166">No</span></span></p></td>
<td><p><span data-ttu-id="cb4eb-167">형식별(예: IM 회의)로 그룹화된 MCU 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-167">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cb4eb-168"><strong>형식별 실패율</strong></span><span class="sxs-lookup"><span data-stu-id="cb4eb-168"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="cb4eb-169">아니요</span><span class="sxs-lookup"><span data-stu-id="cb4eb-169">No</span></span></p></td>
<td><p><span data-ttu-id="cb4eb-170">형식별(예: IM 회의)로 그룹화된 실패한 MCU 세션의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="cb4eb-170">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

