---
title: 'Lync Server 2013: 응답 그룹 통화 목록 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abb3a1b13bf7357a0a2ee31180557911fc37ae0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511765"
---
# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="17ac3-102">Lync Server 2013의 응답 그룹 통화 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="17ac3-102">Response Group Call List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17ac3-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="17ac3-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="17ac3-104">응답 그룹 응용 프로그램을 사용 하면 Microsoft Lync Server 2013에서 전화를 건 번호를 기반으로 통화에 응답 하 고 경로를 지정할 수 있으며, 선택적으로 발신자의 질문에 대 한 응답을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="17ac3-105">일반적으로 응답 그룹 통화는 개별 사람에 게 라우팅되지 않고 대신 에이전트 그룹 이라고 하는 사용자의 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="17ac3-106">예를 들어 사용자가 지원 센터 번호로 전화를 걸 경우 Lync Server 2013는 해당 통화를 처음 사용할 수 있는 지원 센터 에이전트로 자동으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="17ac3-107">또는 Lync Server에서 일련의 질문을 할 수 있습니다 (하드웨어 문제가 있는 경우 1 번 누름).</span><span class="sxs-lookup"><span data-stu-id="17ac3-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="17ac3-108">소프트웨어 문제가 있는 경우 2를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="17ac3-109">네트워크에 문제가 있는 경우 3을 누릅니다. ") 를 선택한 다음 해당 질문에 대 한 답변에 따라 가장 적합 한 지원 센터 에이전트로 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="17ac3-p102">응답 그룹 통화 목록 보고서는 지정된 기간 및 지정된 통화 유형의 통화 컬렉션을 나타냅니다. 응답 그룹 통화 목록 보고서를 열기 위해 먼저 열어야 하는 응답 그룹 사용 보고서에서는 다음과 같은 통화 유형을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="17ac3-p103">**받은 통화**. 응답 그룹 응용 프로그램의 모든 인스턴스에서 수신된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="17ac3-114">**성공한 통화**.</span><span class="sxs-lookup"><span data-stu-id="17ac3-114">**Successful calls**.</span></span> <span data-ttu-id="17ac3-115">응답 그룹 응용 프로그램에 의해 선택 된 총 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="17ac3-p105">**제공된 통화**. 응답 그룹 에이전트로 전송된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="17ac3-p106">**응답한 통화**. 응답 그룹 에이전트가 실제로 받은 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="17ac3-120">중단된 통화 비율.</span><span class="sxs-lookup"><span data-stu-id="17ac3-120">Percentage of abandoned calls.</span></span> <span data-ttu-id="17ac3-121">응답 그룹 응용 프로그램에서 수신되었지만 에이전트가 받지 않은 통화의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="17ac3-122">이 값은 수신된 통화에서 응답한 통화를 빼고 이 값을 수신된 통화 수로 나눠서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="17ac3-123">예를 들어 수신된 통화가 10건이고 응답한 통화가 7건인 경우 10에서 7을 빼면 응답하지 않은 통화는 3건이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="17ac3-124">이 값을 다시 10으로 나누면 중단된 통화 비율이 30%로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="17ac3-p108">**전송된 통화**. 큐 시간 초과 또는 큐 오버플로로 인해 전송된 총 응답 그룹 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="17ac3-127">응답 그룹 통화 목록 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="17ac3-127">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="17ac3-128">응답 그룹 통화 목록 보고서는 [Lync Server 2013의 응답 그룹 사용 보고서](lync-server-2013-response-group-usage-report.md)에 있는 다음 메트릭 중 하나를 클릭 하는 방법 으로만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-128">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="17ac3-129">받은 통화</span><span class="sxs-lookup"><span data-stu-id="17ac3-129">Received calls</span></span>

  - <span data-ttu-id="17ac3-130">성공한 통화</span><span class="sxs-lookup"><span data-stu-id="17ac3-130">Successful calls</span></span>

  - <span data-ttu-id="17ac3-131">제공된 통화</span><span class="sxs-lookup"><span data-stu-id="17ac3-131">Offered calls</span></span>

  - <span data-ttu-id="17ac3-132">응답한 통화</span><span class="sxs-lookup"><span data-stu-id="17ac3-132">Answered calls</span></span>

  - <span data-ttu-id="17ac3-133">전송된 통화</span><span class="sxs-lookup"><span data-stu-id="17ac3-133">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="17ac3-134">응답 그룹 통화 목록 보고서의 효과적인 활용</span><span class="sxs-lookup"><span data-stu-id="17ac3-134">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="17ac3-p109">응답 그룹 통화 목록 보고서를 사용하면 표시되는 데이터를 특정 응답 그룹 워크플로를 사용하는 통화로 제한할 수 있습니다. 이를 위해 워크플로 URI 상자에 워크플로 URI(워크플로의 SIP 주소)를 입력해야 합니다. 그러나 이렇게 하려면 실제로 워크플로 URI가 표시되어 있어야 합니다. 응답 그룹 통화 목록 보고서에 대한 필터링 옵션을 표시하려면 보고서 창 왼쪽 윗부분에 있는 매개 변수 표시/숨기기 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="17ac3-139">응답 그룹 통화 목록에서는 응답 코드 또는 진단 ID 위에 마우스를 놓아도 이러한 메트릭에 대한 정보가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-139">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="17ac3-140">추가 정보가 필요한 경우 응답 코드 및/또는 진단 ID를 기록한 다음 [Lync Server 2013의 상위 오류 보고서](lync-server-2013-top-failures-report.md)에서 해당 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-140">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="17ac3-141">"어떤 개별 워크플로에서 가장 많은 통화를 받았는가?"와 같은 질문에 대한 답을 확인하려면 다음과 같이 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-141">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="17ac3-p111">응답 그룹 사용 보고서에서 원하는 기간을 설정한 후 받은 통화 메트릭을 클릭합니다. 그러면 응답 그룹 통화 목록 보고서가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="17ac3-p112">응답 그룹 통화 목록 보고서에 표시되는 데이터를 내보냅니다. 예를 들어 데이터를 Microsoft Excel 형식으로 내보낸 후에 Excel을 사용하여 해당 데이터를 쉼표로 구분된 값 파일로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="17ac3-146">Windows PowerShell을 사용하여 분석을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-146">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="17ac3-147">예를 들어 데이터를 C: \\ 데이터 \\ 응답 그룹 통화 목록Report.csv에 저장 한 경우 \_ \_ \_ \_ 다음 명령을 사용 하 여 보고서에 나열 된 각 워크플로의 수신 된 총 통화 수를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-147">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="17ac3-148">다음과 같은 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-148">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="17ac3-149">필터</span><span class="sxs-lookup"><span data-stu-id="17ac3-149">Filters</span></span>

<span data-ttu-id="17ac3-p113">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 응답 그룹 통화 목록 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="17ac3-152">응답 그룹 통화 목록 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="17ac3-152">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17ac3-153">이름</span><span class="sxs-lookup"><span data-stu-id="17ac3-153">Name</span></span></th>
<th><span data-ttu-id="17ac3-154">설명</span><span class="sxs-lookup"><span data-stu-id="17ac3-154">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17ac3-155"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="17ac3-155"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="17ac3-p114">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="17ac3-158">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="17ac3-158">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="17ac3-p115">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="17ac3-161">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="17ac3-161">7/7/2012</span></span></p>
<p><span data-ttu-id="17ac3-162">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-162">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="17ac3-163">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="17ac3-163">7/3/2012</span></span></p>
<p><span data-ttu-id="17ac3-164">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-164">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17ac3-165"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="17ac3-165"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="17ac3-p116">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="17ac3-168">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="17ac3-168">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="17ac3-p117">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="17ac3-171">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="17ac3-171">7/7/2012</span></span></p>
<p><span data-ttu-id="17ac3-172">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-172">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="17ac3-173">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="17ac3-173">7/3/2012</span></span></p>
<p><span data-ttu-id="17ac3-174">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-174">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17ac3-175"><strong>워크플로 URI</strong></span><span class="sxs-lookup"><span data-stu-id="17ac3-175"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="17ac3-p118">반환되는 데이터를 지정된 응답 그룹 워크플로로 제한할 수 있습니다. 이 필터를 사용하려면 워크플로 SIP 주소를 입력합니다. 예:</span><span class="sxs-lookup"><span data-stu-id="17ac3-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="17ac3-179">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="17ac3-179">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17ac3-180"><strong>착신</strong></span><span class="sxs-lookup"><span data-stu-id="17ac3-180"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="17ac3-181">다음 통화 유형 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-181">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="17ac3-182">받은 통화</span><span class="sxs-lookup"><span data-stu-id="17ac3-182">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="17ac3-183">성공한 통화</span><span class="sxs-lookup"><span data-stu-id="17ac3-183">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="17ac3-184">제공된 통화</span><span class="sxs-lookup"><span data-stu-id="17ac3-184">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="17ac3-185">응답한 통화</span><span class="sxs-lookup"><span data-stu-id="17ac3-185">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="17ac3-186">전송된 통화</span><span class="sxs-lookup"><span data-stu-id="17ac3-186">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="17ac3-187">메트릭</span><span class="sxs-lookup"><span data-stu-id="17ac3-187">Metrics</span></span>

<span data-ttu-id="17ac3-188">다음 표에서는 응답 그룹 응용 프로그램에서 수신된 각 통화에 대해 응답 그룹 통화 목록 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-188">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="17ac3-189">응답 그룹 통화 목록 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="17ac3-189">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="17ac3-190">이름</span><span class="sxs-lookup"><span data-stu-id="17ac3-190">Name</span></span></th>
<th><span data-ttu-id="17ac3-191">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="17ac3-191">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="17ac3-192">설명</span><span class="sxs-lookup"><span data-stu-id="17ac3-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="17ac3-193"><strong>최초</strong></span><span class="sxs-lookup"><span data-stu-id="17ac3-193"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="17ac3-194">아니요</span><span class="sxs-lookup"><span data-stu-id="17ac3-194">No</span></span></p></td>
<td><p><span data-ttu-id="17ac3-195">발신자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-195">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17ac3-196"><strong>워크플로</strong></span><span class="sxs-lookup"><span data-stu-id="17ac3-196"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="17ac3-197">아니요</span><span class="sxs-lookup"><span data-stu-id="17ac3-197">No</span></span></p></td>
<td><p><span data-ttu-id="17ac3-198">응답 그룹 워크플로의 SIP 주소입니다</span><span class="sxs-lookup"><span data-stu-id="17ac3-198">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17ac3-199"><strong>시작 시간</strong></span><span class="sxs-lookup"><span data-stu-id="17ac3-199"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="17ac3-200">아니요</span><span class="sxs-lookup"><span data-stu-id="17ac3-200">No</span></span></p></td>
<td><p><span data-ttu-id="17ac3-201">통화가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-201">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17ac3-202"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="17ac3-202"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="17ac3-203">아니요</span><span class="sxs-lookup"><span data-stu-id="17ac3-203">No</span></span></p></td>
<td><p><span data-ttu-id="17ac3-204">통화가 종료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-204">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="17ac3-205"><strong>응답 코드</strong></span><span class="sxs-lookup"><span data-stu-id="17ac3-205"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="17ac3-206">아니요</span><span class="sxs-lookup"><span data-stu-id="17ac3-206">No</span></span></p></td>
<td><p><span data-ttu-id="17ac3-207">세션이 실패했을 때 전송된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-207">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="17ac3-208"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="17ac3-208"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="17ac3-209">아니요</span><span class="sxs-lookup"><span data-stu-id="17ac3-209">No</span></span></p></td>
<td><p><span data-ttu-id="17ac3-210">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="17ac3-210">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

