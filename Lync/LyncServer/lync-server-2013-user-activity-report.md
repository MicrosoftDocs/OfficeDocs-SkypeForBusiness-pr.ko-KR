---
title: 'Lync Server 2013: 사용자 활동 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36001aaf38dc39d0bb4eb7524e41c616b0a1c160
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530235"
---
# <a name="user-activity-report-in-lync-server-2013"></a><span data-ttu-id="0cb0a-102">Lync Server 2013의 사용자 활동 보고서</span><span class="sxs-lookup"><span data-stu-id="0cb0a-102">User Activity Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0cb0a-103">_**마지막으로 수정 된 항목:** 2015-02-27_</span><span class="sxs-lookup"><span data-stu-id="0cb0a-103">_**Topic Last Modified:** 2015-02-27_</span></span>

<span data-ttu-id="0cb0a-p101">사용자 활동 보고서에서는 지정된 기간 동안 사용자가 수행한 피어 투 피어 및 회의 세션의 자세한 목록을 제공합니다. 대부분의 모니터링 보고서와 달리 사용자 활동 보고서에서는 각 전화가 개별 사용자와 연결됩니다. 예를 들어 피어 투 피어 세션은 전화를 시작한 사람(보낸 사용자)과 해당 전화를 거는 대상(대상 사용자)의 SIP URI를 지정합니다. 전화 회의에 대해 정보를 확장하면 모든 전화 회의 참가자 및 참가자들이 해당 전화 회의에 대해 보유한 역할의 목록이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p101">The User Activity Report provides a detailed list of the peer-to-peer and conferencing sessions carried out by your users in a given time period. Unlike many of the Monitoring Reports, the User Activity Report ties each call to individual users. For example, peer-to-peer sessions specify the SIP URIs of the person who initiated the call (the From user) and the person who was being called (the To user). If you expand the information for a conference, you'll see a list of all the conference participants and the role they held for that conference.</span></span>

<span data-ttu-id="0cb0a-p102">사용자 활동 보고서는 "지원 센터" 보고서라고도 합니다. 이 보고서는 지원 센터 담당자가 특정 사용자에 대한 세션 정보를 검색하는 데 사용하는 경우가 많기 때문입니다. 사용자 URI 접두사 상자에 사용자의 SIP URI만 입력하면 개별 사용자가 걸거나 받은 전화를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p102">The User Activity Report is sometimes referred to as the "help desk" report. That's because the report is often used by help desk personnel to retrieve session information for a specific user. You can filter for calls made to or made by an individual user simply by typing the user's SIP URI in the User URI prefix box.</span></span>

<span data-ttu-id="0cb0a-111">이렇게 하면 사용자 활동 보고서에서 SIP URI가 지정 된 문자열로 시작 하는 모든 사용자에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-111">If you do this, the User Activity Report will return information for any user whose SIP URI begins with the specified string.</span></span> <span data-ttu-id="0cb0a-112">예를 들어 URI 상자에 **ken** 를 입력 하면 사용자 활동 보고서가 **ken**를 찾습니다. Myer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0cb0a-112">For example, if you type **ken** in the URI box, the User Activity Report will locate **Ken**.Myer@litwareinc.com.</span></span> <span data-ttu-id="0cb0a-113">그러나 다음과 같은 사용자도 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-113">However, it will also locate these users:</span></span>

  - <span data-ttu-id="0cb0a-114">**ken**azi@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0cb0a-114">**ken**azi@litwareinc.com</span></span>

  - <span data-ttu-id="0cb0a-115">**ken**burg@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0cb0a-115">**ken**burg@litwareinc.com</span></span>

  - <span data-ttu-id="0cb0a-116">**Ken** Sanchez@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0cb0a-116">**Ken**.Sanchez@litwareinc.com</span></span>

  - <span data-ttu-id="0cb0a-117">**Ken**nedy@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0cb0a-117">**Ken**nedy@litwareinc.com</span></span>

<span data-ttu-id="0cb0a-118">Ken Myer에 대 한 정보만 반환 되도록 하려면 검색 상자에 전체 URI (Ken.Myer@litwareinc.com)를 입력 하 고, 조직의 다른 사용자 로부터 고유 하 게 구별할 수 있도록 Ken의 URI 형식을 충분히 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-118">To ensure that information only for Ken Myer is returned, either type his full URI (Ken.Myer@litwareinc.com) in the search box or at least enough type of Ken’s URI to uniquely distinguish him from other users in your organization.</span></span> <span data-ttu-id="0cb0a-119">예제:</span><span class="sxs-lookup"><span data-stu-id="0cb0a-119">For example:</span></span>

<span data-ttu-id="0cb0a-120">Ken.my</span><span class="sxs-lookup"><span data-stu-id="0cb0a-120">Ken.my</span></span>

<div>

## <a name="to-access-the-user-activity-report"></a><span data-ttu-id="0cb0a-121">사용자 활동 보고서에 액세스하려면</span><span class="sxs-lookup"><span data-stu-id="0cb0a-121">To access the user activity report</span></span>

<span data-ttu-id="0cb0a-122">사용자 활동 보고서는 모니터링 보고서 홈 페이지에서 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-122">The User Activity Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="0cb0a-123">[Lync Server 2013의 IP 전화 인벤토리 보고서](lync-server-2013-ip-phone-inventory-report.md)에서 사용자 URI 메트릭을 클릭 하 여 사용자 활동 보고서에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-123">You can also reach the User Activity Report by clicking the User URI metric on the [IP Phone Inventory Report in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).</span></span> <span data-ttu-id="0cb0a-124">사용자 활동 보고서 내에서 전화 회의에 대해 전화 회의 URI를 클릭하면 전화 회의 정보 보고서로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-124">From within the User Activity Report, clicking the Conference URI (for a conference) takes you to the Conference Detail Report.</span></span> <span data-ttu-id="0cb0a-125">마찬가지로 피어 투 피어 통화에 대 한 세부 정보 메트릭을 클릭 하면 [Lync Server 2013의 피어 투 피어 세션 정보 보고서](lync-server-2013-peer-to-peer-session-detail-report.md)로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-125">Similarly, clicking the Detail metric for a peer-to-peer call takes you to the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a><span data-ttu-id="0cb0a-126">사용자 활동 보고서를 가장 효율적으로 활용</span><span class="sxs-lookup"><span data-stu-id="0cb0a-126">Making the best use of the user activity report</span></span>

<span data-ttu-id="0cb0a-127">사용자 활동 보고서에는 유용한 정보가 많지만 이러한 정보를 찾기가 어려운 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-127">Although there is a lot of good information in the User Activity Report, that information can sometimes be difficult to locate.</span></span> <span data-ttu-id="0cb0a-128">예를 들어 지정 된 기간 동안 조직에서 수행 되는 모든 사용자 활동은 사용자 활동 보고서에 포함 됩니다. 즉, 보고서 내에서 실제로 Microsoft Lync Server 2013를 어떤 식으로든 사용 하는 사용자에 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-128">For example, all the user activity that takes place in your organization during a specified period is included in the User Activity Report; that means that, buried, within the report is information about which users actually used Microsoft Lync Server 2013 in some way.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0cb0a-129">기술적으로는 일부 사용자 작업이 기록 되지 않은 될 수 있습니다. Lync Server에서는 모든 전화 통화에 대 한 정보를 유지 하는 동안 데이터베이스에 기록 되는 통화에 대 한 정보 없이 통화를 했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-129">Technically, it’s possible that some user activity might go unrecorded: while Lync Server strives to keep information about all phone calls it's possible that a call could have been made without the information about that call being written to the database.</span></span> <span data-ttu-id="0cb0a-130">Lync Server는 매우 정확 하지만 Lync Server 2013를 사용 하는 방법을 완벽 하 게 확인할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-130">Lync Server is designed to give an extremely accurate but not necessarily perfect look at how Lync Server 2013 is being used.</span></span> <span data-ttu-id="0cb0a-131">(모든 통화의 100%가 기록 될 수 없다는 사실은 Lync Server 모니터링을 대금 청구 시스템으로 사용 하지 않아야 하는 이유에 대해 설명 합니다.)</span><span class="sxs-lookup"><span data-stu-id="0cb0a-131">(The fact that there is no guarantee that 100% of all calls are recorded explains why Lync Server monitoring should not be used as a billing system.)</span></span><BR><span data-ttu-id="0cb0a-p108">둘째로, 모니터링 보고서에서는 레코드를 1,000개까지만 표시할 수 있습니다. 따라서 사용자 활동의 양과 작업 기간에 따라서는 쿼리가 데이터베이스에 실제로 저장되어 있는 모든 데이터를 반환하지는 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p108">Second, a Monitoring Report report can only display, at most, 1,000 records. Depending on the amount of user activity you have, and depending on the time period you are working with, that means your query might not return all the data actually stored in the database.</span></span>



</div>

  - <span data-ttu-id="0cb0a-134">해당 기간 동안 실제로 시스템을 사용한 사용자</span><span class="sxs-lookup"><span data-stu-id="0cb0a-134">Which users actually used the system during this time period?</span></span>

  - <span data-ttu-id="0cb0a-135">해당 기간 동안 가장 많은 활동을 한 사용자</span><span class="sxs-lookup"><span data-stu-id="0cb0a-135">Which of my users were the most active during this time period?</span></span>

  - <span data-ttu-id="0cb0a-136">전화 통화를 가장 많이 한 사용자 및 가장 많은 인스턴트 메시징 세션에 참가한 사용자</span><span class="sxs-lookup"><span data-stu-id="0cb0a-136">Are the users who make the most phone calls also the users who participate in the most instant messaging sessions?</span></span>

<span data-ttu-id="0cb0a-137">이러한 정보를 확인하려면 모니터링 보고서에서 검색된 데이터를 Excel 스프레드시트로 내보내면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-137">If you need to answer questions like this, you can export the data retrieved by the Monitoring Reports to an Excel spreadsheet.</span></span> <span data-ttu-id="0cb0a-138">그런 다음 해당 스프레드시트 및/또는 쉼표로 구분된 값 파일을 사용하여 사용자 활동 보고서에서 가능한 방식으로 데이터를 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-138">You then use that spreadsheet and/or a comma-separated values file to analyze the data in ways that the User Activity Report.</span></span> <span data-ttu-id="0cb0a-139">예를 들어 보고서 데이터를 Excel로 내보낸 다음 쉼표로 구분된 값 파일로 내보냈다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-139">For example, suppose you have exported the report data to Excel and then to a comma-separated values file.</span></span> <span data-ttu-id="0cb0a-140">이때에서 데이터를 가져올 수 있습니다. CSV 파일을 Windows PowerShell로 실행 하는 것과 유사한 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-140">At that point, you can import the data from the .CSV file to Windows PowerShell by using a command similar to this:</span></span>

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

<span data-ttu-id="0cb0a-141">데이터를 가져온 후에는 간단한 Windows PowerShell 명령을 사용 하 여 질문에 대 한 답을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-141">After the data has been imported you can then use simple Windows PowerShell commands to help answer your questions.</span></span> <span data-ttu-id="0cb0a-142">예를 들어 다음 명령은 하나 이상의 세션에서 "시작 사용자" 역할을 한 고유 사용자의 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-142">For example, this command returns a list of unique users who served as the "From user" in at least one session:</span></span>

    $x | Group-Object "From user" | Select Name | Sort-Object Name

<span data-ttu-id="0cb0a-143">즉, 다음과 같은 결과가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-143">In other words:</span></span>

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

<span data-ttu-id="0cb0a-144">다음 명령은 사용자가 참가한 총 세션 수를 기준으로 고유 사용자 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-144">This command lists the unique users (based on the total number of sessions that they participated in:</span></span>

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="0cb0a-145">이 명령을 실행하면 다음과 같은 데이터가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-145">That returns data similar to this:</span></span>

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

<span data-ttu-id="0cb0a-146">다음 명령은 형식으로 오디오를 포함한 세션만 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-146">This command limits the reported sessions to those that included audio as a modality:</span></span>

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

<span data-ttu-id="0cb0a-147">보고서에 표시되는 진단 ID 위에 마우스를 놓으면 해당 ID에 대해 설명하는 도구 설명이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-147">If you hold your mouse over any Diagnostic ID shown on the report, a tooltip will appear describing that ID.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="0cb0a-148">필터</span><span class="sxs-lookup"><span data-stu-id="0cb0a-148">Filters</span></span>

<span data-ttu-id="0cb0a-p111">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 사용자 활동 보고서에서는 활동 유형과 같은 항목(즉, 피어 투 피어 세션 또는 회의 세션) 또는 사용자의 SIP 주소(한 사용자의 활동 보기 허용)에 따라 반환된 데이터를 필터링할 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 사용은 시간, 일, 주 및 월별로 그룹이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p111">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the User Activity Report enables you to filter the returned data based on such things as activity type (that is, peer-to-peer sessions or conferencing sessions) or by the user's SIP address (allowing you to view the activities for one user). You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="0cb0a-153">다음 표에서는 사용자 활동 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-153">The following table lists the filters that you can use with the User Activity Report.</span></span>

### <a name="user-activity-report-filters"></a><span data-ttu-id="0cb0a-154">사용자 활동 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="0cb0a-154">User activity report filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cb0a-155">이름</span><span class="sxs-lookup"><span data-stu-id="0cb0a-155">Name</span></span></th>
<th><span data-ttu-id="0cb0a-156">설명</span><span class="sxs-lookup"><span data-stu-id="0cb0a-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-157"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-157"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-p112">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p112">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="0cb0a-160">2012/7/17 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="0cb0a-160">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0cb0a-p113">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p113">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0cb0a-163">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0cb0a-163">7/17/12012</span></span></p>
<p><span data-ttu-id="0cb0a-164">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-164">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0cb0a-165">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0cb0a-165">7/13/2012</span></span></p>
<p><span data-ttu-id="0cb0a-166">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-166">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-167"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-167"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-p114">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p114">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="0cb0a-170">2012/7/17 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="0cb0a-170">7/17/12012 1:00 PM</span></span></p>
<p><span data-ttu-id="0cb0a-p115">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p115">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="0cb0a-173">7/17/12012</span><span class="sxs-lookup"><span data-stu-id="0cb0a-173">7/17/12012</span></span></p>
<p><span data-ttu-id="0cb0a-174">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-174">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="0cb0a-175">7/13/2012</span><span class="sxs-lookup"><span data-stu-id="0cb0a-175">7/13/2012</span></span></p>
<p><span data-ttu-id="0cb0a-176">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-176">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-177"><strong>활동 유형</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-177"><strong>Activity type</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-p116">활동 유형입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p116">Type of activity. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0cb0a-180">모든</span><span class="sxs-lookup"><span data-stu-id="0cb0a-180">[All]</span></span></p></li>
<li><p><span data-ttu-id="0cb0a-181">피어-투-피어</span><span class="sxs-lookup"><span data-stu-id="0cb0a-181">Peer-to-peer</span></span></p></li>
<li><p><span data-ttu-id="0cb0a-182">회의</span><span class="sxs-lookup"><span data-stu-id="0cb0a-182">Conference</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-183"><strong>형식</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-183"><strong>Modality</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-184">사용할 수 있는 형식은 활동 유형 선택에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-184">The Modality available to you varies depending on the select Activity Type.</span></span> <span data-ttu-id="0cb0a-185">활동 유형이 피어 투 피어 인 경우 IM을 선택할 수 있습니다. 파일 전송; 응용 프로그램 공유, 음 또는 비디오를 기본값으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-185">If the Activity Type is Peer-to-Peer, you can select IM; File Transfer; Application Sharing; Voice; or Video as the modality.</span></span></p>
<p><span data-ttu-id="0cb0a-186">활동 유형이 전화 회의 이면 IM 전화 회의를 선택할 수 있습니다. 웹 회의 응용 프로그램 공유, 음성/화상 회의 또는 전화 통신 회의</span><span class="sxs-lookup"><span data-stu-id="0cb0a-186">If the Activity Type is Conference, you can select IM Phone conference; Web conference; Application Sharing; Voice/Video conference; or Telephony conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-187"><strong>세션 범주</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-187"><strong>Session category</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-p118">문제가 있는 활동이 성공 또는 실패했는지를 나타냅니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p118">Indicates whether the activity in question succeeded or failed. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="0cb0a-190">모든</span><span class="sxs-lookup"><span data-stu-id="0cb0a-190">[All]</span></span></p></li>
<li><p><span data-ttu-id="0cb0a-191">Success</span><span class="sxs-lookup"><span data-stu-id="0cb0a-191">Success</span></span></p></li>
<li><p><span data-ttu-id="0cb0a-192">예상 오류</span><span class="sxs-lookup"><span data-stu-id="0cb0a-192">Expected failure</span></span></p></li>
<li><p><span data-ttu-id="0cb0a-193">예기치 않은 오류</span><span class="sxs-lookup"><span data-stu-id="0cb0a-193">Unexpected failure</span></span></p></li>
</ul>
<p><span data-ttu-id="0cb0a-194">예상 되는 &quot; 오류는 발생할 것으로 예상 되는 오류입니다 &quot; . 예를 들어 사용자가 자신의 상태를 방해 금지로 설정 하면 해당 사용자에 게 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-194">An &quot;expected failure&quot; is a failure that is expected to happen; for example, if a user has set his or her status to Do Not Disturb you would expect any call to that user to fail.</span></span> <span data-ttu-id="0cb0a-195">예기치 않은 오류가 발생 하는 것 &quot; &quot; 은 정상적인 시스템이 아닌 것 처럼 보이는 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-195">An &quot;unexpected failure&quot; is a failure that occurs in what would appear to be an otherwise healthy system.</span></span> <span data-ttu-id="0cb0a-196">예를 들어 발신자가 보류 상태일 때는 통화가 종료되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-196">For example, a call should not be terminated if the caller is placed on hold.</span></span> <span data-ttu-id="0cb0a-197">하지만 통화가 종료되면 바로 예기치 않은 오류로 플래그 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-197">If that occurs, that would be flagged as an unexpected failure.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-198"><strong>사용자 URI 접두사</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-p120">사용자의 SIP 주소입니다. 사용자 Ken Myer에 대한 레코드만 보려면 Ken Myer의 SIP 주소를 입력해야 합니다. 예:</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p120">SIP address for the user. To view records only for the user Ken Myer you need to enter Ken Myer's SIP address. For example:</span></span></p>
<p><span data-ttu-id="0cb0a-202">sip:kenmyer@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="0cb0a-202">sip:kenmyer@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="0cb0a-203">피어 투 피어 세션에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="0cb0a-203">Metrics for peer-to-peer sessions</span></span>

<span data-ttu-id="0cb0a-204">다음 표에서는 피어 투 피어 세션(즉, 참가자가 두 명뿐인 세션)에 대해 사용자 활동 보고서에 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-204">The following table lists the information provided in the User Activity Report for peer-to-peer sessions (that is, sessions involving just two participants).</span></span>

### <a name="metrics-for-peer-to-peer-sessions"></a><span data-ttu-id="0cb0a-205">피어 투 피어 세션에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="0cb0a-205">Metrics for peer-to-peer sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cb0a-206">이름</span><span class="sxs-lookup"><span data-stu-id="0cb0a-206">Name</span></span></th>
<th><span data-ttu-id="0cb0a-207">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="0cb0a-207">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0cb0a-208">설명</span><span class="sxs-lookup"><span data-stu-id="0cb0a-208">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-209"><strong>자세한 정보</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-209"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-210">아니요</span><span class="sxs-lookup"><span data-stu-id="0cb0a-210">No</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-211">이 항목을 클릭하면 보고서에 선택한 세션에 대한 피어 투 피어 세션 세부 정보 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-211">When you click this item, the report shows you the Peer-to-Peer Session Detail Report for the selected session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-212"><strong>시작 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-212"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-213">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-214">피어 투 피어 세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-214">SIP address of the user who initiated the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-215"><strong>대상 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-215"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-216">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-216">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-217">피어 투 피어 세션에 참가한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-217">SIP address of the user who joined the peer-to-peer session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-218"><strong>형식</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-218"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-219">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-219">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-p121">세션에 사용된 통신 유형입니다. 예: IM, 오디오 또는 파일 전송.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p121">Type of communication used in the session. For example, IM, audio, or file transfer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-222"><strong>초대 시간</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-222"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-223">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-224">피어 투 피어 세션에 참가하라는 최초 초대가 전송된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-224">Date and time the initial invitation to join the peer-to-peer session was sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-225"><strong>응답 시간</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-225"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-226">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-227">&quot; &quot; 사용자가 세션 초대를 수락한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-227">Date and time that the &quot;To&quot; user accepted the session invitation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-228"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-228"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-229">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-230">피어 투 피어 세션이 종료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-230">Date and time the peer-to-peer session ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-231"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-231"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-232">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-232">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-p122">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. 진단 헤더는 선택 사항이며(이러한 헤더를 포함하지 않는 SIP 세션도 가능함) 진단 ID는 일부 유형의 문제가 발생한 세션에 대해서만 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p122">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="0cb0a-235">회의 세션에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="0cb0a-235">Metrics for conferencing sessions</span></span>

<span data-ttu-id="0cb0a-236">다음 표에서는 회의 세션(즉, 참가자가 세 명 이상인 세션)에 대해 사용자 활동 보고서에 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-236">The following table lists the information provided in the User Activity Report for conferencing sessions (that is, sessions involving three or more participants).</span></span>

### <a name="metrics-for-conferencing-sessions"></a><span data-ttu-id="0cb0a-237">회의 세션에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="0cb0a-237">Metrics for conferencing sessions</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cb0a-238">이름</span><span class="sxs-lookup"><span data-stu-id="0cb0a-238">Name</span></span></th>
<th><span data-ttu-id="0cb0a-239">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="0cb0a-239">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0cb0a-240">설명</span><span class="sxs-lookup"><span data-stu-id="0cb0a-240">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-241"><strong>전화 회의 URI</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-241"><strong>Conference URI</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-242">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-242">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-243">고유한 회의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-243">Unique conference identifier.</span></span> <span data-ttu-id="0cb0a-244">이 항목을 클릭하면 보고서에 선택한 세션에 대한 회의 세부 정보 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-244">When you click this item, the report shows you the Conference Detail Report for the selected session.</span></span> <span data-ttu-id="0cb0a-245">이 항목을 확장하면 보고서에 회의 참가자에 대한 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-245">When you expand this item, the report shows you information about the conference participants.</span></span> <span data-ttu-id="0cb0a-246">자세한 내용은 &quot; 이 항목 뒷부분에 나오는 회의 참가자를 위한 메트릭 섹션을 참조 하십시오 &quot; .</span><span class="sxs-lookup"><span data-stu-id="0cb0a-246">For details, see the &quot;Metrics for Conference Participants&quot; section later in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-247"><strong>구성 도우미</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-247"><strong>Organizer</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-248">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-248">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-249">회의를 구성한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-249">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-250"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-251">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-251">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-252">회의에 사용된 에지 서버(있는 경우)의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-252">Name of the Edge Server (if any) used in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-253"><strong>시작 시간</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-253"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-254">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-254">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-255">회의가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-255">Date and time that the conference began.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-256"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-256"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-257">예</span><span class="sxs-lookup"><span data-stu-id="0cb0a-257">Yes</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-258">회의가 종료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-258">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a><span data-ttu-id="0cb0a-259">회의 참가자에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="0cb0a-259">Metrics for conference participants</span></span>

<span data-ttu-id="0cb0a-260">다음 표에서는 회의의 각 참가자에 대해 제공되는 사용자 활동 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-260">The following table lists the information provided in the User Activity Report provides for each participant in a conference.</span></span>

### <a name="metrics-for-conference-participants"></a><span data-ttu-id="0cb0a-261">회의 참가자에 대한 메트릭</span><span class="sxs-lookup"><span data-stu-id="0cb0a-261">Metrics for conference participants</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0cb0a-262">이름</span><span class="sxs-lookup"><span data-stu-id="0cb0a-262">Name</span></span></th>
<th><span data-ttu-id="0cb0a-263">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="0cb0a-263">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="0cb0a-264">설명</span><span class="sxs-lookup"><span data-stu-id="0cb0a-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-265"><strong>역할</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-265"><strong>Role</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-266">아니요</span><span class="sxs-lookup"><span data-stu-id="0cb0a-266">No</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-267">사용자에 대한 회의 역할(예: 발표자)입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-267">Conference role (for example, Presenter) for the user.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-268"><strong>조직</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-268"><strong>Participant</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-269">아니요</span><span class="sxs-lookup"><span data-stu-id="0cb0a-269">No</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-270">사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-270">SIP address of the user.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-271"><strong>연결</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-271"><strong>Connectivity</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-272">아니요</span><span class="sxs-lookup"><span data-stu-id="0cb0a-272">No</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-273">네트워크 연결 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-273">Network connection type.</span></span> <span data-ttu-id="0cb0a-274">예를 들어 내부 연결의 경우 &quot; &quot; 또는 &quot; &quot; 전화 접속 사용자에 대해 PSTN을 사용 하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-274">For example &quot;From Internal&quot; for internal connection or &quot;From PSTN&quot; for dial-in users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-275"><strong>참가 시간</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-275"><strong>Join time</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-276">아니요</span><span class="sxs-lookup"><span data-stu-id="0cb0a-276">No</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-277">사용자가 회의에 참가한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-277">Date and time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0cb0a-278"><strong>나간 시간</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-278"><strong>Leave time</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-279">아니요</span><span class="sxs-lookup"><span data-stu-id="0cb0a-279">No</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-280">사용자가 회의에서 나간 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-280">Date and time that the user left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0cb0a-281"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="0cb0a-281"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="0cb0a-282">아니요</span><span class="sxs-lookup"><span data-stu-id="0cb0a-282">No</span></span></p></td>
<td><p><span data-ttu-id="0cb0a-p125">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다. 진단 헤더는 선택 사항이며(이러한 헤더를 포함하지 않는 SIP 세션도 가능함) 진단 ID는 일부 유형의 문제가 발생한 세션에 대해서만 보고됩니다.</span><span class="sxs-lookup"><span data-stu-id="0cb0a-p125">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors. Diagnostics headers are optional (it is possible to have SIP sessions that do not include these headers), and diagnostic IDs are reported only for sessions that experienced problems of some kind.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

