---
title: 'Lync Server 2013: 컨퍼런스 요약 하위 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Summary Subreport
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204779(v=OCS.15)
ms:contentKeyID: 48183742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b87ea9648404f495f487a639a3b11900f91dcda4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="48bd5-102">Lync Server 2013의 컨퍼런스 요약 하위 보고서</span><span class="sxs-lookup"><span data-stu-id="48bd5-102">Conference Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48bd5-103">_**마지막으로 수정한 주제:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="48bd5-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="48bd5-104">회의 요약 하위 보고서는 실패 한 회의 세션의 전체적인 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-104">The Conference Summary Subreport provides an overall view of failed conference sessions.</span></span> <span data-ttu-id="48bd5-105">이러한 실패 한 세션은 세션 유형: 포커스 세션 및 MCU 세션으로 더욱 세분화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-105">These failed sessions are further broken down by session type: Focus sessions and MCU sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="48bd5-106">필터가</span><span class="sxs-lookup"><span data-stu-id="48bd5-106">Filters</span></span>

<span data-ttu-id="48bd5-107">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-107">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="48bd5-108">다음 표에는 회의 요약 하위 보고서와 함께 사용할 수 있는 필터가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-108">The following table lists the filters that you can use with the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-filters"></a><span data-ttu-id="48bd5-109">컨퍼런스 요약 하위 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="48bd5-109">Conference Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48bd5-110">이름</span><span class="sxs-lookup"><span data-stu-id="48bd5-110">Name</span></span></th>
<th><span data-ttu-id="48bd5-111">설명</span><span class="sxs-lookup"><span data-stu-id="48bd5-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48bd5-112"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="48bd5-112"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="48bd5-113">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-113">Start date/time for the time range.</span></span> <span data-ttu-id="48bd5-114">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-114">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="48bd5-115">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="48bd5-115">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="48bd5-116">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="48bd5-117">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-117">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="48bd5-118">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="48bd5-118">7/7/2012</span></span></p>
<p><span data-ttu-id="48bd5-119">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="48bd5-119">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="48bd5-120">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="48bd5-120">7/3/2012</span></span></p>
<p><span data-ttu-id="48bd5-121">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-121">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48bd5-122"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="48bd5-122"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="48bd5-123">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-123">End date/time for the time range.</span></span> <span data-ttu-id="48bd5-124">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-124">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="48bd5-125">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="48bd5-125">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="48bd5-126">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-126">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="48bd5-127">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-127">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="48bd5-128">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="48bd5-128">7/7/2012</span></span></p>
<p><span data-ttu-id="48bd5-129">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="48bd5-129">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="48bd5-130">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="48bd5-130">7/3/2012</span></span></p>
<p><span data-ttu-id="48bd5-131">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-131">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48bd5-132"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="48bd5-132"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="48bd5-133">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-133">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="48bd5-134">개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-134">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="48bd5-135">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-135">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="48bd5-136">매트릭스</span><span class="sxs-lookup"><span data-stu-id="48bd5-136">Metrics</span></span>

<span data-ttu-id="48bd5-137">다음 표에는 회의 요약 하위 보고서에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-137">The following table lists the information provided in the Conference Summary Subreport.</span></span>

### <a name="conference-summary-subreport-metrics"></a><span data-ttu-id="48bd5-138">컨퍼런스 요약 하위 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="48bd5-138">Conference Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48bd5-139">이름</span><span class="sxs-lookup"><span data-stu-id="48bd5-139">Name</span></span></th>
<th><span data-ttu-id="48bd5-140">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="48bd5-140">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="48bd5-141">설명</span><span class="sxs-lookup"><span data-stu-id="48bd5-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48bd5-142"><strong>총 컨퍼런스</strong></span><span class="sxs-lookup"><span data-stu-id="48bd5-142"><strong>Total conferences</strong></span></span></p></td>
<td><p><span data-ttu-id="48bd5-143">아니요</span><span class="sxs-lookup"><span data-stu-id="48bd5-143">No</span></span></p></td>
<td><p><span data-ttu-id="48bd5-144">보유 한 총 컨퍼런스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-144">Total number of conferences held.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48bd5-145"><strong>총 회의 세션</strong></span><span class="sxs-lookup"><span data-stu-id="48bd5-145"><strong>Total conference sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="48bd5-146">아니요</span><span class="sxs-lookup"><span data-stu-id="48bd5-146">No</span></span></p></td>
<td><p><span data-ttu-id="48bd5-147">회의 세션의 총 수입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-147">Total number of conference sessions.</span></span> <span data-ttu-id="48bd5-148">단일 회의는 여러 세션을 가질 수 있습니다. 예를 들어 컨퍼런스에는 포커스 세션과 MCU 세션이 모두 포함 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-148">A single conference can have multiple sessions; for example, a conference might include both a Focus session and an MCU session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48bd5-149"><strong>전체 세션 실패 율</strong></span><span class="sxs-lookup"><span data-stu-id="48bd5-149"><strong>Overall session failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="48bd5-150">아니요</span><span class="sxs-lookup"><span data-stu-id="48bd5-150">No</span></span></p></td>
<td><p><span data-ttu-id="48bd5-151">실패 한 모든 컨퍼런스의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-151">Percentage of all conferences that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48bd5-152"><strong>포커스 세션</strong></span><span class="sxs-lookup"><span data-stu-id="48bd5-152"><strong>Focus sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="48bd5-153">아니요</span><span class="sxs-lookup"><span data-stu-id="48bd5-153">No</span></span></p></td>
<td><p><span data-ttu-id="48bd5-154">총 포커스 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-154">Total number of Focus sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48bd5-155"><strong>초점 고장 속도</strong></span><span class="sxs-lookup"><span data-stu-id="48bd5-155"><strong>Focus failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="48bd5-156">아니요</span><span class="sxs-lookup"><span data-stu-id="48bd5-156">No</span></span></p></td>
<td><p><span data-ttu-id="48bd5-157">실패 한 포커스 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-157">Percentage of Focus sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48bd5-158">MCU 세션</span><span class="sxs-lookup"><span data-stu-id="48bd5-158">MCU sessions</span></span></p></td>
<td><p><span data-ttu-id="48bd5-159">아니요</span><span class="sxs-lookup"><span data-stu-id="48bd5-159">No</span></span></p></td>
<td><p><span data-ttu-id="48bd5-160">총 MCU 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-160">Total number of MCU sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48bd5-161"><strong>MCU 실패 율</strong></span><span class="sxs-lookup"><span data-stu-id="48bd5-161"><strong>MCU failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="48bd5-162">아니요</span><span class="sxs-lookup"><span data-stu-id="48bd5-162">No</span></span></p></td>
<td><p><span data-ttu-id="48bd5-163">실패 한 MCU 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-163">Percentage of MCU sessions that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48bd5-164"><strong>모달에의 한 MCU 세션</strong></span><span class="sxs-lookup"><span data-stu-id="48bd5-164"><strong>MCU sessions by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="48bd5-165">아니요</span><span class="sxs-lookup"><span data-stu-id="48bd5-165">No</span></span></p></td>
<td><p><span data-ttu-id="48bd5-166">형식 (예: IM 회의)으로 그룹화 된 총 MCU 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="48bd5-166">Total number of MCU sessions, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48bd5-167"><strong>모달의 실패 비율</strong></span><span class="sxs-lookup"><span data-stu-id="48bd5-167"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="48bd5-168">아니요</span><span class="sxs-lookup"><span data-stu-id="48bd5-168">No</span></span></p></td>
<td><p><span data-ttu-id="48bd5-169">실패 한 MCU 세션의 백분율 (예: IM 회의)</span><span class="sxs-lookup"><span data-stu-id="48bd5-169">Percentage of MCU sessions that failed, grouped by modality (for example, IM conferencing).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

