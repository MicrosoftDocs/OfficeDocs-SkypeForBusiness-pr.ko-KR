---
title: 'Lync Server 2013: 응답 그룹 사용 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 649fb55f6c7b698986c4c31057b3a0a8f1b00a76
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511625"
---
# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="be070-102">Lync Server 2013의 응답 그룹 사용 보고서</span><span class="sxs-lookup"><span data-stu-id="be070-102">Response Group Usage Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="be070-103">_**마지막으로 수정 된 항목:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="be070-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="be070-104">응답 그룹 응용 프로그램을 사용 하면 Microsoft Lync Server 2013에서 전화를 건 번호를 기반으로 통화에 응답 하 고 경로를 지정할 수 있으며, 선택적으로 발신자의 질문에 대 한 응답을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be070-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="be070-105">일반적으로 응답 그룹 통화는 개별 사람에 게 라우팅되지 않고 대신 에이전트 그룹 이라고 하는 사용자의 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="be070-106">예를 들어 사용자가 지원 센터 번호로 전화를 걸 경우 Lync Server 2013는 해당 통화를 처음 사용할 수 있는 지원 센터 에이전트로 자동으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be070-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="be070-107">또는 Lync Server에서 일련의 질문을 할 수 있습니다 (하드웨어 문제가 있는 경우 1 번 누름).</span><span class="sxs-lookup"><span data-stu-id="be070-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="be070-108">소프트웨어 문제가 있는 경우 2를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="be070-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="be070-109">네트워크에 문제가 있는 경우 3을 누릅니다. ") 를 선택한 다음 해당 질문에 대 한 답변에 따라 가장 적합 한 지원 센터 에이전트로 통화를 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="be070-110">응답 그룹 사용 보고서에서는 모든 응답 그룹 워크플로에서 수신한 전화 통화 수에 대한 자세한 정보를 제공하며, 해당 통화를 제공된 통화, 응답한 통화, 중단된 통화 등의 보다 한정된 범주로 구분하여 해당 정보도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-110">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="be070-111">응답 그룹 사용 보고서를 사용할 때는 다음과 같은 보고된 통화 유형 간의 차이를 파악해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-111">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="be070-p102">**받은 통화**. 응답 그룹 응용 프로그램의 모든 인스턴스에서 수신된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p102">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="be070-114">**성공한 통화**.</span><span class="sxs-lookup"><span data-stu-id="be070-114">**Successful calls**.</span></span> <span data-ttu-id="be070-115">응답 그룹 응용 프로그램에 의해 선택 된 총 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="be070-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="be070-p104">**제공된 통화**. 응답 그룹 에이전트로 전송된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p104">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="be070-p105">**응답한 통화**. 응답 그룹 에이전트가 실제로 받은 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p105">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="be070-p106">**중단된 통화 비율**. 응답 그룹 응용 프로그램에서 수신되었지만 에이전트가 받지 않은 통화의 비율입니다. 이 값은 수신된 통화에서 응답한 통화를 빼고 이 값을 수신된 통화 수로 나눠서 계산됩니다. 예를 들어 수신된 통화가 10건이고 응답한 통화가 7건인 경우 10에서 7을 빼면 응답하지 않은 통화는 3건이 됩니다. 이 값을 다시 10으로 나누면 중단된 통화 비율이 30%로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p106">**Percentage of abandoned calls**. Percentage of calls that were received by the Response Group application but were never answered by an agent. This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls. For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="be070-p107">**전송된 통화**. 큐 시간 초과 또는 큐 오버플로로 인해 전송된 총 응답 그룹 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p107">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="be070-p108">응답 그룹 사용 보고서를 확인할 때 이러한 통화 유형의 정의가 잘 생각나지 않으면 적절한 통화 유형 레이블 위에 마우스를 놓으면 됩니다. 그러면 통화 유형의 간단한 설명을 제공하는 도구 설명이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p108">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label. A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="be070-p109">응답 그룹 사용 보고서에서는 워크플로 URI(해당 워크플로와 연결된 SIP 주소)로 필터링할 수 있습니다. 그러나 워크플로 URI는 보고서 자체에 실제로 표시되지는 않습니다. 가장 많은 통화에 응답하는 워크플로, 전송된 통화 수가 가장 많은 워크플로 등을 확인하려면 해당하는 메트릭을 클릭하여 지정된 기간에 대한 응답 그룹 통화 목록 보고서를 엽니다. 이 보고서에는 워크플로 URI가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p109">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow). However, workflow URIs do not actually appear on the report itself. If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period. That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="be070-133">응답 그룹 사용 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="be070-133">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="be070-134">응답 그룹 사용 보고서는 모니터링 보고서 홈 페이지에서 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-134">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="be070-135">다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 응답 그룹 통화 목록 보고서](lync-server-2013-response-group-call-list-report.md) 로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be070-135">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="be070-136">받은 통화</span><span class="sxs-lookup"><span data-stu-id="be070-136">Received calls</span></span>

  - <span data-ttu-id="be070-137">성공한 통화</span><span class="sxs-lookup"><span data-stu-id="be070-137">Successful calls</span></span>

  - <span data-ttu-id="be070-138">제공된 통화</span><span class="sxs-lookup"><span data-stu-id="be070-138">Offered calls</span></span>

  - <span data-ttu-id="be070-139">응답한 통화</span><span class="sxs-lookup"><span data-stu-id="be070-139">Answered calls</span></span>

  - <span data-ttu-id="be070-140">전송된 통화</span><span class="sxs-lookup"><span data-stu-id="be070-140">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="be070-141">응답 그룹 사용 보고서를 가장 효율적으로 활용</span><span class="sxs-lookup"><span data-stu-id="be070-141">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="be070-142">널리 알려져 있지는 않지만 응답 그룹 사용 보고서에서 유용한 기능 중 하나는 단일 응답 그룹 워크플로에 대해 사용 현황 정보를 검색하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="be070-142">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="be070-143">기본적으로 응답 그룹 워크플로는 사용자가 특정 전화 번호로 전화를 걸 때 Lync Server가 수행 하는 작업을 결정 하는 지침 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="be070-143">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="be070-144">따라서 각 워크플로는 한 전화 번호에만 고유하게 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-144">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="be070-145">누군가 그 번호로 전화를 걸면 워크플로에 따라 해당 전화의 처리 방법이 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-145">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="be070-146">예를 들어 워크플로에서 발신자에게 추가 정보를 입력하라는 일련의 IVR(대화형 음성 응답) 질문("하드웨어 지원을 받으려면 1번을, 소프트웨어 지원을 받으려면 2번을 누르십시오.")으로 전화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be070-146">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="be070-147">또는 에이전트가 통화에 응답할 수 있을 때까지 워크플로에서 통화를 큐에 배치하고 발신자를 통화 대기 상태로 유지할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be070-147">Press 2 for software support.").</span></span> <span data-ttu-id="be070-148">에이전트가 전화를 받을 수 있는 상태인지도 워크플로에서 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-148">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="be070-149">워크플로는 업무 시간(에이전트가 전화를 받을 수 있는 요일과 시간)과 휴일(에이전트가 전화를 받을 수 없는 날짜)을 구성하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-149">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="be070-150">응답 그룹 응용 프로그램에 속하는 전화 번호로 전화를 걸 때마다 실제로는 응답 그룹 워크플로로 전화를 걸게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-150">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="be070-p112">워크플로 URI는 응답 그룹 사용 보고서에 표시되지는 않지만 단일 워크플로에 대한 사용 통계를 확인할 수 있으며, 해당 정보는 매우 유용한 경우가 많습니다. 예를 들어 최근에 새 광고 캠페인을 시작했는데 사용자들이 해당 제품에 대한 문의 전화를 거는지를 확인하려는 경우를 가정해 보겠습니다. 이 경우 응답 그룹 워크플로를 광고 캠페인에 지정된 전화 번호와 연결하면 해당 번호로 전화를 거는 사람(있는 경우)의 수를 쉽게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p112">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful. For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product. If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="be070-154">이와 비슷한 방식을 사용하여 내부 지원 센터 또는 고객 서비스 부서에서 처리하는 통화 수도 측정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be070-154">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="be070-155">특정 워크플로에 대한 사용 통계를 검토하려면 워크플로 URI 상자에 워크플로 URI를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-155">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="be070-156">물론 앞에서 언급한 대로 워크플로 URI, 즉 워크플로와 연결된 SIP 주소는 보고서에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="be070-156">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="be070-157">따라서 다른 방법으로 워크플로의 URI를 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-157">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="be070-158">이 작업을 수행 하는 한 가지 방법은 Windows PowerShell 및 Lync Server 관리 셸을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="be070-158">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="be070-159">예를 들어 다음 명령은 모든 응답 그룹 워크플로의 URI를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-159">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="be070-160">이 명령을 실행하면 다음과 같은 데이터가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-160">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="be070-161">다음 명령은 New Ad Campaign이라는 단일 워크플로에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-161">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="be070-162">필터</span><span class="sxs-lookup"><span data-stu-id="be070-162">Filters</span></span>

<span data-ttu-id="be070-p114">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 예를 들어 응답 그룹 사용 보고서에서는 모든 응답 그룹 워크플로에 대한 데이터 또는 개별 워크플로에 대한 데이터를 볼 수 있습니다. 또한 데이터의 그룹 지정 방식도 선택할 수 있습니다. 이 경우 사용은 시간, 일, 주 및 월별로 그룹이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p114">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow. You can also choose how data should be grouped. In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="be070-167">다음 표에서는 응답 그룹 사용 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be070-167">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="be070-168">응답 그룹 사용 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="be070-168">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be070-169">이름</span><span class="sxs-lookup"><span data-stu-id="be070-169">Name</span></span></th>
<th><span data-ttu-id="be070-170">설명</span><span class="sxs-lookup"><span data-stu-id="be070-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be070-171"><strong>시작</strong></span><span class="sxs-lookup"><span data-stu-id="be070-171"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-p115">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p115">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="be070-174">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="be070-174">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="be070-p116">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p116">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="be070-177">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="be070-177">7/7/2012</span></span></p>
<p><span data-ttu-id="be070-178">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be070-178">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="be070-179">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="be070-179">7/3/2012</span></span></p>
<p><span data-ttu-id="be070-180">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-180">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be070-181"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="be070-181"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-p117">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p117">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="be070-184">7/7/2012 1:00 PM</span><span class="sxs-lookup"><span data-stu-id="be070-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="be070-p118">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p118">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="be070-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="be070-187">7/7/2012</span></span></p>
<p><span data-ttu-id="be070-188">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="be070-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="be070-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="be070-189">7/3/2012</span></span></p>
<p><span data-ttu-id="be070-190">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be070-191"><strong>간격당</strong></span><span class="sxs-lookup"><span data-stu-id="be070-191"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-p119">시간 간격입니다. 다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p119">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="be070-194">시간별(최대 25시간 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="be070-194">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="be070-195">일별(최대 31일 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="be070-195">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="be070-196">주별(최대 12주 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="be070-196">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="be070-197">월별(최대 12개월 표시 가능)</span><span class="sxs-lookup"><span data-stu-id="be070-197">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="be070-p120">시작 및 종료 날짜가 선택한 간격에 허용되는 최대 값 수를 초과하면 시작 날짜로부터 최대 값 수만 표시됩니다. 예를 들어 일별 간격을 선택하는 경우 시작 날짜가 2012/8/7이고 종료 날짜가 2012/9/28이면 2012/8/7 오전 12:00부터 2012/9/7 오전 12:00까지 총 31일의 데이터만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p120">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be070-200"><strong>워크플로 URI</strong></span><span class="sxs-lookup"><span data-stu-id="be070-200"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-p121">반환되는 데이터를 지정된 응답 그룹 워크플로로 제한할 수 있습니다. 이 필터를 사용하려면 워크플로 SIP 주소를 입력합니다. 예:</span><span class="sxs-lookup"><span data-stu-id="be070-p121">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span></p>
<p><span data-ttu-id="be070-204">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="be070-204">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="be070-205">메트릭</span><span class="sxs-lookup"><span data-stu-id="be070-205">Metrics</span></span>

<span data-ttu-id="be070-206">다음 표에서는 응답 그룹 사용 보고서에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be070-206">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="be070-207">응답 그룹 사용 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="be070-207">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="be070-208">이름</span><span class="sxs-lookup"><span data-stu-id="be070-208">Name</span></span></th>
<th><span data-ttu-id="be070-209">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="be070-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="be070-210">설명</span><span class="sxs-lookup"><span data-stu-id="be070-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="be070-211"><strong>매시간</strong></span><span class="sxs-lookup"><span data-stu-id="be070-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="be070-212"><strong>매일</strong></span><span class="sxs-lookup"><span data-stu-id="be070-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="be070-213"><strong>매주</strong></span><span class="sxs-lookup"><span data-stu-id="be070-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="be070-214"><strong>월간</strong></span><span class="sxs-lookup"><span data-stu-id="be070-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-215">아니요</span><span class="sxs-lookup"><span data-stu-id="be070-215">No</span></span></p></td>
<td><p><span data-ttu-id="be070-p122">선택한 시간 간격을 나타냅니다. 적용 가능한 경우 제공된 시간 간격을 클릭하여 해당 간격에 대한 세부 정보를 볼 수 있습니다. 예를 들어 일별 간격을 사용 중이고 2012/7/7을 클릭하면 해당 날짜의 사용자 등록 활동에 대한 시간별 세부 내역을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p122">Indicates the selected time interval. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be070-219"><strong>받은 통화</strong></span><span class="sxs-lookup"><span data-stu-id="be070-219"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-220">아니요</span><span class="sxs-lookup"><span data-stu-id="be070-220">No</span></span></p></td>
<td><p><span data-ttu-id="be070-p123">응답 그룹 응용 프로그램의 모든 인스턴스에서 수신된 총 통화 수입니다. 이 항목을 클릭하면 보고서에 선택한 시간 기간에 대한 응답 그룹 통화 목록 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p123">Total number of calls received by all instances of the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be070-223"><strong>성공한 통화</strong></span><span class="sxs-lookup"><span data-stu-id="be070-223"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-224">아니요</span><span class="sxs-lookup"><span data-stu-id="be070-224">No</span></span></p></td>
<td><p><span data-ttu-id="be070-p124">응답 그룹 응용 프로그램에서 받은 총 통화 수입니다. 이 항목을 클릭하면 보고서에 선택한 시간 기간에 대한 응답 그룹 통화 목록 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p124">Total number of calls that were picked up the Response Group application. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be070-227"><strong>제공된 통화</strong></span><span class="sxs-lookup"><span data-stu-id="be070-227"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-228">아니요</span><span class="sxs-lookup"><span data-stu-id="be070-228">No</span></span></p></td>
<td><p><span data-ttu-id="be070-p125">응답 그룹 에이전트로 전송된 총 통화 수입니다. 이 항목을 클릭하면 보고서에 선택한 시간 기간에 대한 응답 그룹 통화 목록 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p125">Total number of calls that were transferred to a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be070-231"><strong>응답한 통화</strong></span><span class="sxs-lookup"><span data-stu-id="be070-231"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-232">아니요</span><span class="sxs-lookup"><span data-stu-id="be070-232">No</span></span></p></td>
<td><p><span data-ttu-id="be070-p126">응답 그룹 에이전트가 실제로 받은 총 통화 수입니다. 이 항목을 클릭하면 보고서에 선택한 시간 기간에 대한 응답 그룹 통화 목록 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p126">Total number of calls that were actually answered by a Response Group agent. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be070-235"><strong>중단된 통화 비율</strong></span><span class="sxs-lookup"><span data-stu-id="be070-235"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-236">아니요</span><span class="sxs-lookup"><span data-stu-id="be070-236">No</span></span></p></td>
<td><p><span data-ttu-id="be070-p127">응답 그룹 에이전트에서 수신되었지만 에이전트가 받지 않은 총 통화 수입니다. 이 값은 수신된 통화에서 응답한 통화를 빼고 이 값을 수신된 통화 수로 나눠서 계산됩니다. 예를 들어 수신된 통화가 10건이고 받은 통화가 7건이면 10에서 7을 빼서 받지 않은 통화는 3건이 됩니다. 이 값을 다시 10으로 나누면 중단된 통화 비율이 30%로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p127">Total number of calls that were received by the Response Group application but were never answered by an agent. This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls. For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls. That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="be070-241"><strong>에이전트별 평균 통화 시간(분)</strong></span><span class="sxs-lookup"><span data-stu-id="be070-241"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-242">아니요</span><span class="sxs-lookup"><span data-stu-id="be070-242">No</span></span></p></td>
<td><p><span data-ttu-id="be070-243">응답 그룹 에이전트가 한 통화에 대해 소비한 평균 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="be070-243">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="be070-244"><strong>전송된 통화</strong></span><span class="sxs-lookup"><span data-stu-id="be070-244"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="be070-245">아니요</span><span class="sxs-lookup"><span data-stu-id="be070-245">No</span></span></p></td>
<td><p><span data-ttu-id="be070-p128">큐 시간 초과 또는 큐 오버플로로 인해 전송된 총 응답 그룹 통화 수입니다. 이 항목을 클릭하면 보고서에 선택한 시간 기간에 대한 응답 그룹 통화 목록 보고서가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="be070-p128">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow. When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

