---
title: 'Lync Server 2013: 전화 회의 요약 하위 보고서'
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
ms.openlocfilehash: ddbbe3fc546010e78ee7df6aa8afb083e594ea14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502325"
---
# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="ec4b6-102">Lync Server 2013의 전화 회의 요약 하위 보고서</span><span class="sxs-lookup"><span data-stu-id="ec4b6-102">Conference Summary Subreport in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec4b6-103">_**마지막으로 수정 된 항목:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="ec4b6-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="ec4b6-p101">전화 회의 요약 하위 보고서에서는 실패한 전화 회의 세션에 대한 전반적인 정보를 제공합니다. 이와 같은 실패한 세션은 세션 유형(회의 센터 세션 및 MCU 세션)별로 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-p101">The Conference Summary Subreport provides an overall view of failed conference sessions. These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="ec4b6-106">필터</span><span class="sxs-lookup"><span data-stu-id="ec4b6-106">Filters</span></span>

<span data-ttu-id="ec4b6-p102">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 전화 회의 요약 하위 보고서에 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-p102">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="ec4b6-109">전화 회의 요약 하위 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="ec4b6-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec4b6-110">이름</span><span class="sxs-lookup"><span data-stu-id="ec4b6-110">Name</span></span></th>
<th><span data-ttu-id="ec4b6-111">설명</span><span class="sxs-lookup"><span data-stu-id="ec4b6-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec4b6-112"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="ec4b6-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="ec4b6-p103">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-p103">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="ec4b6-115">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ec4b6-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ec4b6-p104">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-p104">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ec4b6-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ec4b6-118">7/7/2012</span></span></p>
<p><span data-ttu-id="ec4b6-119">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ec4b6-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ec4b6-120">7/3/2012</span></span></p>
<p><span data-ttu-id="ec4b6-121">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec4b6-122"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="ec4b6-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="ec4b6-p105">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-p105">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="ec4b6-125">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="ec4b6-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="ec4b6-p106">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-p106">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="ec4b6-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="ec4b6-128">7/7/2012</span></span></p>
<p><span data-ttu-id="ec4b6-129">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="ec4b6-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="ec4b6-130">7/3/2012</span></span></p>
<p><span data-ttu-id="ec4b6-131">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec4b6-132"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="ec4b6-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ec4b6-p107">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-p107">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ec4b6-136">메트릭</span><span class="sxs-lookup"><span data-stu-id="ec4b6-136">Metrics</span></span>

<span data-ttu-id="ec4b6-137">다음 표에서는 전화 회의 요약 하위 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="ec4b6-138">전화 회의 요약 하위 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="ec4b6-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec4b6-139">이름</span><span class="sxs-lookup"><span data-stu-id="ec4b6-139">Name</span></span></th>
<th><span data-ttu-id="ec4b6-140">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="ec4b6-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ec4b6-141">설명</span><span class="sxs-lookup"><span data-stu-id="ec4b6-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec4b6-142"><strong>총 전화 회의</strong></span><span class="sxs-lookup"><span data-stu-id="ec4b6-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="ec4b6-143">아니요</span><span class="sxs-lookup"><span data-stu-id="ec4b6-143">No</span></span></p></td>
<td><p><span data-ttu-id="ec4b6-144">진행된 총 전화 회의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec4b6-145"><strong>총 전화 회의 세션</strong></span><span class="sxs-lookup"><span data-stu-id="ec4b6-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ec4b6-146">아니요</span><span class="sxs-lookup"><span data-stu-id="ec4b6-146">No</span></span></p></td>
<td><p><span data-ttu-id="ec4b6-p108">총 전화 회의 세션 수입니다. 전화 회의 하나에 여러 세션이 포함될 수 있습니다. 예를 들어 하나의 전화 회의가 회의 센터 세션과 MCU 세션을 둘 다 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-p108">Total number of conference sessions. A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec4b6-149"><strong>전체 세션 실패율</strong></span><span class="sxs-lookup"><span data-stu-id="ec4b6-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="ec4b6-150">아니요</span><span class="sxs-lookup"><span data-stu-id="ec4b6-150">No</span></span></p></td>
<td><p><span data-ttu-id="ec4b6-151">실패한 모든 전화 회의의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec4b6-152"><strong>회의 센터 세션</strong></span><span class="sxs-lookup"><span data-stu-id="ec4b6-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="ec4b6-153">아니요</span><span class="sxs-lookup"><span data-stu-id="ec4b6-153">No</span></span></p></td>
<td><p><span data-ttu-id="ec4b6-154">회의 센터 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec4b6-155"><strong>회의 센터 실패율</strong></span><span class="sxs-lookup"><span data-stu-id="ec4b6-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="ec4b6-156">아니요</span><span class="sxs-lookup"><span data-stu-id="ec4b6-156">No</span></span></p></td>
<td><p><span data-ttu-id="ec4b6-157">실패한 회의 센터 세션의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec4b6-158">MCU 세션</span><span class="sxs-lookup"><span data-stu-id="ec4b6-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="ec4b6-159">아니요</span><span class="sxs-lookup"><span data-stu-id="ec4b6-159">No</span></span></p></td>
<td><p><span data-ttu-id="ec4b6-160">MCU 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec4b6-161"><strong>MCU 실패율</strong></span><span class="sxs-lookup"><span data-stu-id="ec4b6-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="ec4b6-162">아니요</span><span class="sxs-lookup"><span data-stu-id="ec4b6-162">No</span></span></p></td>
<td><p><span data-ttu-id="ec4b6-163">실패한 MCU 세션의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec4b6-164"><strong>형식별 MCU 세션</strong></span><span class="sxs-lookup"><span data-stu-id="ec4b6-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="ec4b6-165">아니요</span><span class="sxs-lookup"><span data-stu-id="ec4b6-165">No</span></span></p></td>
<td><p><span data-ttu-id="ec4b6-166">형식별(예: IM 회의)로 그룹화된 MCU 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec4b6-167"><strong>형식별 실패율</strong></span><span class="sxs-lookup"><span data-stu-id="ec4b6-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="ec4b6-168">아니요</span><span class="sxs-lookup"><span data-stu-id="ec4b6-168">No</span></span></p></td>
<td><p><span data-ttu-id="ec4b6-169">형식별(예: IM 회의)로 그룹화된 실패한 MCU 세션의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4b6-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

