---
title: 'Lync Server 2013: P2P 요약 하위 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffa28f05ae8059244f53575c01f02551cbaffc95
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140041"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="a1bf8-102">Lync Server 2013의 P2P 요약 하위 보고서</span><span class="sxs-lookup"><span data-stu-id="a1bf8-102">P2P Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1bf8-103">_**마지막으로 수정 된 항목:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a1bf8-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a1bf8-104">P2P 요약 하위 보고서는 실패한 피어 투 피어 통신 세션에 대한 전체 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="a1bf8-105">필터</span><span class="sxs-lookup"><span data-stu-id="a1bf8-105">Filters</span></span>

<span data-ttu-id="a1bf8-p101">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에는 P2P 요약 하위 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-p101">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="a1bf8-108">P2P 요약 하위 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="a1bf8-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1bf8-109">이름</span><span class="sxs-lookup"><span data-stu-id="a1bf8-109">Name</span></span></th>
<th><span data-ttu-id="a1bf8-110">설명</span><span class="sxs-lookup"><span data-stu-id="a1bf8-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1bf8-111"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="a1bf8-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a1bf8-p102">시간 범위의 시작 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜와 시간을 모두 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-p102">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a1bf8-114">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a1bf8-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a1bf8-p103">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-p103">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a1bf8-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a1bf8-117">7/7/2012</span></span></p>
<p><span data-ttu-id="a1bf8-118">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a1bf8-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a1bf8-119">7/3/2012</span></span></p>
<p><span data-ttu-id="a1bf8-120">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1bf8-121"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="a1bf8-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a1bf8-p104">시간 범위의 종료 날짜 및 시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-p104">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a1bf8-124">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="a1bf8-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a1bf8-p105">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-p105">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a1bf8-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a1bf8-127">7/7/2012</span></span></p>
<p><span data-ttu-id="a1bf8-128">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a1bf8-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a1bf8-129">7/3/2012</span></span></p>
<p><span data-ttu-id="a1bf8-130">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1bf8-131"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="a1bf8-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a1bf8-p106">등록자 풀 또는 에지 서버의 FQDN(정규화된 도메인 이름)입니다. 개별 풀을 선택하거나 <strong>[모두]</strong>를 클릭하여 모든 풀에 대한 데이터를 봅니다. 이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-p106">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server. You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools. This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a1bf8-135">선별한</span><span class="sxs-lookup"><span data-stu-id="a1bf8-135">Metrics</span></span>

<span data-ttu-id="a1bf8-136">다음 표에는 P2P 요약 하위 보고서에 제공된 정보가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="a1bf8-137">P2P 요약 하위 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="a1bf8-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1bf8-138">이름</span><span class="sxs-lookup"><span data-stu-id="a1bf8-138">Name</span></span></th>
<th><span data-ttu-id="a1bf8-139">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="a1bf8-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a1bf8-140">설명</span><span class="sxs-lookup"><span data-stu-id="a1bf8-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1bf8-141"><strong>총 세션</strong></span><span class="sxs-lookup"><span data-stu-id="a1bf8-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a1bf8-142">아니요</span><span class="sxs-lookup"><span data-stu-id="a1bf8-142">No</span></span></p></td>
<td><p><span data-ttu-id="a1bf8-143">성공한 세션, 실패한 세션(예상 오류 및 예기치 않은 오류 모두) 및 분류되지 않은 세션을 포함한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1bf8-144"><strong>실패율</strong></span><span class="sxs-lookup"><span data-stu-id="a1bf8-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="a1bf8-145">아니요</span><span class="sxs-lookup"><span data-stu-id="a1bf8-145">No</span></span></p></td>
<td><p><span data-ttu-id="a1bf8-146">실패한 피어 투 피어 세션의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1bf8-147"><strong>형식별 세션(Sessions by Modality)</strong></span><span class="sxs-lookup"><span data-stu-id="a1bf8-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="a1bf8-148">아니요</span><span class="sxs-lookup"><span data-stu-id="a1bf8-148">No</span></span></p></td>
<td><p><span data-ttu-id="a1bf8-149">형식(예: 인스턴트 메시징)별로 그룹화된 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1bf8-150"><strong>형식별 실패율(Failure rate by modality)</strong></span><span class="sxs-lookup"><span data-stu-id="a1bf8-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="a1bf8-151">아니요</span><span class="sxs-lookup"><span data-stu-id="a1bf8-151">No</span></span></p></td>
<td><p><span data-ttu-id="a1bf8-152">형식(예: 인스턴트 메시징)별로 그룹화된 총 실패 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a1bf8-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

