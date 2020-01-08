---
title: 'Lync Server 2013: P2P 요약 하위 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: P2P Summary Subreport
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205416(v=OCS.15)
ms:contentKeyID: 48185950
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7199d9571adfb90b6f848f8f46474fd14813bc76
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="p2p-summary-subreport-in-lync-server-2013"></a><span data-ttu-id="a8cb1-102">Lync Server 2013의 P2P 요약 하위 보고서</span><span class="sxs-lookup"><span data-stu-id="a8cb1-102">P2P Summary Subreport in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a8cb1-103">_**마지막으로 수정한 주제:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="a8cb1-103">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="a8cb1-104">P2P 요약 하위 보고서는 실패 한 피어 투 피어 통신 세션에 대 한 전체적인 보기를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-104">The P2P Summary Subreport provides an overall view of your failed peer-to-peer communication sessions.</span></span>

<div>

## <a name="filters"></a><span data-ttu-id="a8cb1-105">필터가</span><span class="sxs-lookup"><span data-stu-id="a8cb1-105">Filters</span></span>

<span data-ttu-id="a8cb1-106">필터는 더욱 세밀 하 게 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-106">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="a8cb1-107">다음 표에는 P2P 요약 하위 보고서에 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-107">The following table lists the filters that you can use with the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-filters"></a><span data-ttu-id="a8cb1-108">P2P 요약 하위 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="a8cb1-108">P2P Summary Subreport Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8cb1-109">이름</span><span class="sxs-lookup"><span data-stu-id="a8cb1-109">Name</span></span></th>
<th><span data-ttu-id="a8cb1-110">설명</span><span class="sxs-lookup"><span data-stu-id="a8cb1-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8cb1-111"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="a8cb1-111"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="a8cb1-112">시간 범위에 대 한 시작 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-112">Start date and time for the time range.</span></span> <span data-ttu-id="a8cb1-113">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-113">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="a8cb1-114">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="a8cb1-114">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a8cb1-115">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="a8cb1-116">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-116">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a8cb1-117">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a8cb1-117">7/7/2012</span></span></p>
<p><span data-ttu-id="a8cb1-118">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="a8cb1-118">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a8cb1-119">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a8cb1-119">7/3/2012</span></span></p>
<p><span data-ttu-id="a8cb1-120">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-120">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8cb1-121"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="a8cb1-121"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="a8cb1-122">시간 범위의 종료 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-122">End date and time for the time range.</span></span> <span data-ttu-id="a8cb1-123">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-123">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="a8cb1-124">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="a8cb1-124">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="a8cb1-125">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-125">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="a8cb1-126">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-126">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="a8cb1-127">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="a8cb1-127">7/7/2012</span></span></p>
<p><span data-ttu-id="a8cb1-128">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="a8cb1-128">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="a8cb1-129">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="a8cb1-129">7/3/2012</span></span></p>
<p><span data-ttu-id="a8cb1-130">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-130">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8cb1-131"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="a8cb1-131"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="a8cb1-132">등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="a8cb1-133">개별 풀을 선택 하거나 <strong>[모두]</strong> 를 클릭 하 여 모든 풀에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-133">You can either select an individual pool or click <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="a8cb1-134">이 드롭다운 목록은 데이터베이스의 레코드에 따라 자동으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-134">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="a8cb1-135">매트릭스</span><span class="sxs-lookup"><span data-stu-id="a8cb1-135">Metrics</span></span>

<span data-ttu-id="a8cb1-136">다음 표에는 P2P 요약 하위 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-136">The following table lists the information provided in the P2P Summary Subreport.</span></span>

### <a name="p2p-summary-subreport-metrics"></a><span data-ttu-id="a8cb1-137">P2P 요약 하위 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="a8cb1-137">P2P Summary Subreport Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a8cb1-138">이름</span><span class="sxs-lookup"><span data-stu-id="a8cb1-138">Name</span></span></th>
<th><span data-ttu-id="a8cb1-139">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="a8cb1-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="a8cb1-140">설명</span><span class="sxs-lookup"><span data-stu-id="a8cb1-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a8cb1-141"><strong>총 세션</strong></span><span class="sxs-lookup"><span data-stu-id="a8cb1-141"><strong>Total sessions</strong></span></span></p></td>
<td><p><span data-ttu-id="a8cb1-142">아니요</span><span class="sxs-lookup"><span data-stu-id="a8cb1-142">No</span></span></p></td>
<td><p><span data-ttu-id="a8cb1-143">성공한 세션, 실패 한 세션 (예상 되는 실패 및 예기치 못한 실패), 범주화 되지 않은 세션 등의 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-143">Total number of sessions, including successful sessions, failed sessions (both expected failures and unexpected failures), and uncategorized sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8cb1-144"><strong>실패 율</strong></span><span class="sxs-lookup"><span data-stu-id="a8cb1-144"><strong>Failure rate</strong></span></span></p></td>
<td><p><span data-ttu-id="a8cb1-145">아니요</span><span class="sxs-lookup"><span data-stu-id="a8cb1-145">No</span></span></p></td>
<td><p><span data-ttu-id="a8cb1-146">실패 한 피어 투 피어 세션의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-146">Percentage of peer-to-peer sessions that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a8cb1-147"><strong>모달의 세션</strong></span><span class="sxs-lookup"><span data-stu-id="a8cb1-147"><strong>Sessions by Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="a8cb1-148">아니요</span><span class="sxs-lookup"><span data-stu-id="a8cb1-148">No</span></span></p></td>
<td><p><span data-ttu-id="a8cb1-149">모달 (예: 인스턴트 메시지)에 의해 그룹화 된 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-149">Total number of sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a8cb1-150"><strong>모달의 실패 비율</strong></span><span class="sxs-lookup"><span data-stu-id="a8cb1-150"><strong>Failure rate by modality</strong></span></span></p></td>
<td><p><span data-ttu-id="a8cb1-151">아니요</span><span class="sxs-lookup"><span data-stu-id="a8cb1-151">No</span></span></p></td>
<td><p><span data-ttu-id="a8cb1-152">모달 (예: 인스턴트 메시지)로 그룹화 된 실패 한 총 세션 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a8cb1-152">Total number of failed sessions grouped by modality (for example, instant messaging).</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

