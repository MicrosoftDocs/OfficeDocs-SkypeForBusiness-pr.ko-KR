---
title: 'Lync Server 2013: 응답 그룹 통화 목록 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group Call List Report
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615443(v=OCS.15)
ms:contentKeyID: 48184954
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf2c45167b5e5c437a3ff755115aa54d34c74a87
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-call-list-report-in-lync-server-2013"></a><span data-ttu-id="8f776-102">Lync Server 2013의 응답 그룹 통화 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="8f776-102">Response Group Call List Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f776-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="8f776-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="8f776-104">응답 그룹 응용 프로그램은 Microsoft Lync Server 2013에서 전화를 걸고, 선택적으로 발신자의 질문에 대 한 회신에 대 한 응답 및 라우팅 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="8f776-105">일반적으로 응답 그룹 통화는 개인 사람에 게 라우팅되지 않지만, 대신 상담원 그룹 이라고 하는 사용자의 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="8f776-106">예를 들어 사용자가 지원 센터 번호로 전화를 걸 경우 Lync Server 2013는 해당 통화를 사용 가능한 첫 번째 지원 센터 에이전트로 자동으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="8f776-107">또는 Lync Server가 일련의 질문을 할 수 있습니다 (하드웨어 문제가 있는 경우 1 번 누름).</span><span class="sxs-lookup"><span data-stu-id="8f776-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="8f776-108">소프트웨어 문제가 있는 경우 2를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="8f776-109">네트워크 문제가 발생 하는 경우 3을 누릅니다. ") 그런 다음 해당 질문에 대 한 답변을 기준으로 가장 적절 한 지원 센터 상담원에 게 통화를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="8f776-110">응답 그룹 통화 목록 보고서는 지정 된 기간 및 지정 된 통화 유형에 대해 이루어진 통화 모음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-110">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call.</span></span> <span data-ttu-id="8f776-111">응답 그룹 통화 목록 보고서를 열기 전에 먼저 열려 있어야 하는 Response 그룹 사용 보고서에서 다음 통화 유형을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-111">The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

  - <span data-ttu-id="8f776-112">**전화 받음**.</span><span class="sxs-lookup"><span data-stu-id="8f776-112">**Received calls**.</span></span> <span data-ttu-id="8f776-113">응답 그룹 응용 프로그램의 모든 인스턴스에서 받은 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-113">Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="8f776-114">**통화 했습니다**.</span><span class="sxs-lookup"><span data-stu-id="8f776-114">**Successful calls**.</span></span> <span data-ttu-id="8f776-115">응답 그룹 응용 프로그램이 선택한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="8f776-116">**제공**되는 통화.</span><span class="sxs-lookup"><span data-stu-id="8f776-116">**Offered calls**.</span></span> <span data-ttu-id="8f776-117">응답 그룹 에이전트로 전송 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-117">Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="8f776-118">**통화 응답**.</span><span class="sxs-lookup"><span data-stu-id="8f776-118">**Answered calls**.</span></span> <span data-ttu-id="8f776-119">응답 그룹 에이전트에서 실제로 응답 한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-119">Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="8f776-120">중단 된 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-120">Percentage of abandoned calls.</span></span> <span data-ttu-id="8f776-121">응답 그룹 응용 프로그램에서 받았지만 에이전트에서 응답 하지 않은 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="8f776-122">이 값은 수신 전화에서 응답 한 전화를 뺀 다음 해당 값을 수신 된 통화 수로 나누는 방법으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="8f776-123">예를 들어 10 개의 통화를 받고 7 개가 응답 한 경우에는 3 개의 응답 하지 않은 통화를 종료 하 고 10에서 7을 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="8f776-124">이 값을 10으로 나누면 30%의 통화 백분율이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="8f776-125">**통화를 전송**했습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-125">**Transferred calls**.</span></span> <span data-ttu-id="8f776-126">큐 시간 제한 또는 큐 오버플로 때문에 전송 된 총 응답 그룹 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-126">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<div>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="8f776-127">응답 그룹 통화 목록 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="8f776-127">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="8f776-128">응답 그룹 통화 목록 보고서에는 [Lync Server 2013의 응답 그룹 사용 보고서](lync-server-2013-response-group-usage-report.md)에 있는 다음 메트릭 중 하나를 클릭 하 여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-128">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Lync Server 2013](lync-server-2013-response-group-usage-report.md):</span></span>

  - <span data-ttu-id="8f776-129">수신 전화</span><span class="sxs-lookup"><span data-stu-id="8f776-129">Received calls</span></span>

  - <span data-ttu-id="8f776-130">성공한 통화</span><span class="sxs-lookup"><span data-stu-id="8f776-130">Successful calls</span></span>

  - <span data-ttu-id="8f776-131">제공 되는 통화</span><span class="sxs-lookup"><span data-stu-id="8f776-131">Offered calls</span></span>

  - <span data-ttu-id="8f776-132">응답 한 전화</span><span class="sxs-lookup"><span data-stu-id="8f776-132">Answered calls</span></span>

  - <span data-ttu-id="8f776-133">통화 전송</span><span class="sxs-lookup"><span data-stu-id="8f776-133">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="8f776-134">응답 그룹 통화 목록 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="8f776-134">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="8f776-135">응답 그룹 통화 목록 보고서를 사용 하 여 표시 된 데이터를 특정 응답 그룹 워크플로를 포함 하는 통화로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-135">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow.</span></span> <span data-ttu-id="8f776-136">이렇게 하려면 워크플로 uri 상자에 워크플로 URI (워크플로의 SIP 주소)를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-136">To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box.</span></span> <span data-ttu-id="8f776-137">이 작업을 수행 하기 전에 실제로 워크플로 URI 상자를 볼 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-137">Before you can do that, however, you must actually be able to see the Workflow URI box.</span></span> <span data-ttu-id="8f776-138">응답 그룹 통화 목록 보고서에 대 한 필터링 옵션을 표시 하려면 보고서 창의 왼쪽 위 부분에 있는 매개 변수 표시/숨기기 단추를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-138">To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="8f776-139">응답 그룹 통화 목록에는 해당 메트릭 중 하나 위에 마우스를 놓고 응답 코드 또는 진단 ID에 대 한 정보가 표시 되지 않는다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f776-139">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="8f776-140">추가 정보가 필요한 경우 응답 코드 및/또는 진단 ID를 기록한 다음 [Lync Server 2013의 상위 오류 보고서](lync-server-2013-top-failures-report.md)에서 해당 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-140">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Lync Server 2013](lync-server-2013-top-failures-report.md).</span></span>

<span data-ttu-id="8f776-141">"이 문제가 발생 하는 개별 워크플로가 가장 많은 호출을 받음" 등의 질문은 다음과 같이 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-141">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1.  <span data-ttu-id="8f776-142">응답 그룹 사용 현황 보고서에서 원하는 기간을 설정한 다음 받은 통화 메트릭을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-142">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric.</span></span> <span data-ttu-id="8f776-143">그러면 응답 그룹 통화 목록 보고서가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-143">That will open the Response Group Call List Report.</span></span>

2.  <span data-ttu-id="8f776-144">응답 그룹 통화 목록 보고서에 표시 된 데이터를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-144">Export the data shown on the Response Group Call List Report.</span></span> <span data-ttu-id="8f776-145">예를 들어 Microsoft Excel 형식으로 데이터를 내보낸 다음 Excel을 사용 하 여 해당 데이터를 쉼표로 구분 된 값 파일로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-145">For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3.  <span data-ttu-id="8f776-146">Windows PowerShell을 사용 하 여 분석을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-146">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="8f776-147">예를 들어 데이터를\\C: 데이터\\응답\_그룹\_통화\_목록\_보고서 .csv로 저장 한 경우 다음 명령을 사용 하 여 보고서에 나열 된 각 워크플로에 대 한 총 수신 통화 수를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-147">For example, if you have saved the data to a file named C:\\Data\\Response\_Group\_Call\_List\_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="8f776-148">이 정보는 다음과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-148">That will information similar to this:</span></span>

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

</div>

<div>

## <a name="filters"></a><span data-ttu-id="8f776-149">필터가</span><span class="sxs-lookup"><span data-stu-id="8f776-149">Filters</span></span>

<span data-ttu-id="8f776-150">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-150">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="8f776-151">다음 표에는 응답 그룹 통화 목록 보고서와 함께 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-151">The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

### <a name="response-group-call-list-report-filters"></a><span data-ttu-id="8f776-152">응답 그룹 통화 목록 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="8f776-152">Response Group Call List Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f776-153">이름</span><span class="sxs-lookup"><span data-stu-id="8f776-153">Name</span></span></th>
<th><span data-ttu-id="8f776-154">설명</span><span class="sxs-lookup"><span data-stu-id="8f776-154">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f776-155"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="8f776-155"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="8f776-156">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-156">Start date/time for the time range.</span></span> <span data-ttu-id="8f776-157">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-157">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="8f776-158">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="8f776-158">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8f776-159">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-159">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8f776-160">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-160">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8f776-161">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8f776-161">7/7/2012</span></span></p>
<p><span data-ttu-id="8f776-162">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="8f776-162">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8f776-163">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8f776-163">7/3/2012</span></span></p>
<p><span data-ttu-id="8f776-164">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-164">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f776-165"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="8f776-165"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="8f776-166">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-166">End date/time for the time range.</span></span> <span data-ttu-id="8f776-167">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-167">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="8f776-168">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="8f776-168">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="8f776-169">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-169">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="8f776-170">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-170">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="8f776-171">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="8f776-171">7/7/2012</span></span></p>
<p><span data-ttu-id="8f776-172">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="8f776-172">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="8f776-173">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="8f776-173">7/3/2012</span></span></p>
<p><span data-ttu-id="8f776-174">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-174">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f776-175"><strong>워크플로 URI</strong></span><span class="sxs-lookup"><span data-stu-id="8f776-175"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="8f776-176">반환 되는 데이터를 지정 된 응답 그룹 워크플로로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-176">Enables you to limit the returned data to the specified Response Group workflow.</span></span> <span data-ttu-id="8f776-177">이 필터를 사용 하려면 워크플로 SIP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-177">To use this filter, enter the Workflow SIP address.</span></span> <span data-ttu-id="8f776-178">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-178">For example:</span></span></p>
<p><span data-ttu-id="8f776-179">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="8f776-179">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f776-180"><strong>전화가</strong></span><span class="sxs-lookup"><span data-stu-id="8f776-180"><strong>Calls</strong></span></span></p></td>
<td><p><span data-ttu-id="8f776-181">다음 통화 유형 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-181">You can select one of the following call types:</span></span></p>
<ul>
<li><p><span data-ttu-id="8f776-182">수신 전화</span><span class="sxs-lookup"><span data-stu-id="8f776-182">Received Calls</span></span></p></li>
<li><p><span data-ttu-id="8f776-183">성공한 통화</span><span class="sxs-lookup"><span data-stu-id="8f776-183">Successful Calls</span></span></p></li>
<li><p><span data-ttu-id="8f776-184">제공 되는 통화</span><span class="sxs-lookup"><span data-stu-id="8f776-184">Offered Calls</span></span></p></li>
<li><p><span data-ttu-id="8f776-185">응답 한 전화</span><span class="sxs-lookup"><span data-stu-id="8f776-185">Answered Calls</span></span></p></li>
<li><p><span data-ttu-id="8f776-186">통화 전송</span><span class="sxs-lookup"><span data-stu-id="8f776-186">Transferred Calls</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="8f776-187">매트릭스</span><span class="sxs-lookup"><span data-stu-id="8f776-187">Metrics</span></span>

<span data-ttu-id="8f776-188">다음 표에는 응답 그룹 응용 프로그램이 받은 각 통화에 대 한 응답 그룹 통화 목록 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-188">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

### <a name="response-group-call-list-report-metrics"></a><span data-ttu-id="8f776-189">응답 그룹 통화 목록 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="8f776-189">Response Group Call List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8f776-190">이름</span><span class="sxs-lookup"><span data-stu-id="8f776-190">Name</span></span></th>
<th><span data-ttu-id="8f776-191">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="8f776-191">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="8f776-192">설명</span><span class="sxs-lookup"><span data-stu-id="8f776-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8f776-193"><strong>호출인</strong></span><span class="sxs-lookup"><span data-stu-id="8f776-193"><strong>Caller</strong></span></span></p></td>
<td><p><span data-ttu-id="8f776-194">아니요</span><span class="sxs-lookup"><span data-stu-id="8f776-194">No</span></span></p></td>
<td><p><span data-ttu-id="8f776-195">발신자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-195">SIP address of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f776-196"><strong>워크플로입니다</strong></span><span class="sxs-lookup"><span data-stu-id="8f776-196"><strong>Workflow</strong></span></span></p></td>
<td><p><span data-ttu-id="8f776-197">아니요</span><span class="sxs-lookup"><span data-stu-id="8f776-197">No</span></span></p></td>
<td><p><span data-ttu-id="8f776-198">응답 그룹 워크플로의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-198">SIP address of the Response Group workflow.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f776-199"><strong>시작 시간</strong></span><span class="sxs-lookup"><span data-stu-id="8f776-199"><strong>Start time</strong></span></span></p></td>
<td><p><span data-ttu-id="8f776-200">아니요</span><span class="sxs-lookup"><span data-stu-id="8f776-200">No</span></span></p></td>
<td><p><span data-ttu-id="8f776-201">통화가 시작 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-201">Date and time that the call started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f776-202"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="8f776-202"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="8f776-203">아니요</span><span class="sxs-lookup"><span data-stu-id="8f776-203">No</span></span></p></td>
<td><p><span data-ttu-id="8f776-204">통화가 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-204">Date and time that the call ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8f776-205"><strong>응답 코드</strong></span><span class="sxs-lookup"><span data-stu-id="8f776-205"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="8f776-206">아니요</span><span class="sxs-lookup"><span data-stu-id="8f776-206">No</span></span></p></td>
<td><p><span data-ttu-id="8f776-207">세션이 실패 했을 때 전송 된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-207">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8f776-208"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="8f776-208"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="8f776-209">아니요</span><span class="sxs-lookup"><span data-stu-id="8f776-209">No</span></span></p></td>
<td><p><span data-ttu-id="8f776-210">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="8f776-210">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

