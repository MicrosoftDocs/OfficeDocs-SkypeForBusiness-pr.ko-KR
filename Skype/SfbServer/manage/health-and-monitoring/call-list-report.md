---
title: 비즈니스용 Skype 서버의 응답 그룹 통화 목록 보고서
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: '요약: 비즈니스용 Skype 서버의 응답 그룹 응용 프로그램에 대해 자세히 알아보습니다.'
ms.openlocfilehash: 416a0e7b7a7aebaeae84a00c04a7ab5c4e1a5bf8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826498"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a><span data-ttu-id="94415-103">비즈니스용 Skype 서버의 응답 그룹 통화 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="94415-103">Response Group Call List Report in Skype for Business Server</span></span>

<span data-ttu-id="94415-104">**요약:** 비즈니스용 Skype 서버의 응답 그룹 응용 프로그램에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="94415-104">**Summary:** Learn about the Response Group application in Skype for Business Server.</span></span>

<span data-ttu-id="94415-105">응답 그룹 응용 프로그램을 사용하면 비즈니스용 Skype 서버가 전화를 걸었다는 번호와 여러 질문에 대한 발신자 응답에 따라 전화 통화에 응답하고 통화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94415-105">The Response Group application provides a way for Skype for Business Server to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="94415-106">일반적으로 응답 그룹 통화는 개별 사용자로 라우팅되지 않고 대신 에이전트 그룹이라고 하는 사람의 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="94415-106">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="94415-107">예를 들어 누군가 지원 센터의 전화 번호로 전화를 걸면 비즈니스용 Skype 서버는 해당 통화를 사용 가능한 첫 번째 지원 센터 에이전트로 자동으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94415-107">For example, if someone calls the phone number for your help desk, Skype for Business Server can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="94415-108">또는 비즈니스용 Skype 서버에서 일련의 질문을 할 수 있습니다("하드웨어 문제가 있는 경우 1을 누르기).</span><span class="sxs-lookup"><span data-stu-id="94415-108">Alternatively, Skype for Business Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="94415-109">소프트웨어 문제가 있는 경우 2를 누르고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94415-109">Press 2 if you are having software problems.</span></span> <span data-ttu-id="94415-110">네트워크 문제가 있는 경우 3을 누르고 있습니다.") 그런 다음 해당 질문에 대한 답변에 따라 통화를 가장 적절한 지원 센터 에이전트로 라우팅합니다.</span><span class="sxs-lookup"><span data-stu-id="94415-110">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="94415-p102">응답 그룹 통화 목록 보고서는 지정된 기간 및 지정된 통화 유형의 통화 컬렉션을 나타냅니다. 응답 그룹 통화 목록 보고서를 열기 위해 먼저 열어야 하는 응답 그룹 사용 보고서에서는 다음과 같은 통화 유형을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p102">The Response Group Call List Report represents a collection of calls made for a specified period of time and for a specified type of call. The Response Group Usage Report (which must be opened first before you can open the Response Group Call List Report) recognizes the following call types:</span></span>

- <span data-ttu-id="94415-p103">**받은 통화**. 응답 그룹 응용 프로그램의 모든 인스턴스에서 수신된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p103">**Received calls**. Total number of calls received by all instances of the Response Group application.</span></span>

- <span data-ttu-id="94415-115">**성공한 통화**.</span><span class="sxs-lookup"><span data-stu-id="94415-115">**Successful calls**.</span></span> <span data-ttu-id="94415-116">응답 그룹 응용 프로그램에서 선택된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="94415-116">Total number of calls that were picked up by the Response Group application.</span></span>

- <span data-ttu-id="94415-p105">**제공된 통화**. 응답 그룹 에이전트로 전송된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p105">**Offered calls**. Total number of calls that were transferred to a Response Group agent.</span></span>

- <span data-ttu-id="94415-p106">**응답한 통화**. 응답 그룹 에이전트가 실제로 받은 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p106">**Answered calls**. Total number of calls that were actually answered by a Response Group agent.</span></span>

- <span data-ttu-id="94415-121">**중단된 통화의 백분율입니다.**</span><span class="sxs-lookup"><span data-stu-id="94415-121">**Percentage of abandoned calls.**</span></span> <span data-ttu-id="94415-122">응답 그룹 응용 프로그램에서 수신되었지만 에이전트가 받지 않은 통화의 비율입니다.</span><span class="sxs-lookup"><span data-stu-id="94415-122">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="94415-123">이 값은 수신된 통화에서 응답한 통화를 빼고 이 값을 수신된 통화 수로 나눠서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="94415-123">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="94415-124">예를 들어 수신된 통화가 10건이고 응답한 통화가 7건인 경우 10에서 7을 빼면 응답하지 않은 통화는 3건이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94415-124">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="94415-125">이 값을 다시 10으로 나누면 중단된 통화 비율이 30%로 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="94415-125">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

- <span data-ttu-id="94415-p108">**전송된 통화**. 큐 시간 초과 또는 큐 오버플로로 인해 전송된 총 응답 그룹 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p108">**Transferred calls**. Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

## <a name="accessing-the-response-group-call-list-report"></a><span data-ttu-id="94415-128">응답 그룹 통화 목록 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="94415-128">Accessing the Response Group Call List Report</span></span>

<span data-ttu-id="94415-129">응답 그룹 통화 목록 보고서는 비즈니스용 Skype 서버의 응답 그룹 사용 보고서에 있는 다음 메트릭 중 하나를 클릭해야 [액세스할 수 있습니다.](response-group-usage-report.md)</span><span class="sxs-lookup"><span data-stu-id="94415-129">The Response Group Call List Report can only be accessed by clicking one of the following metrics found on the [Response Group Usage Report in Skype for Business Server](response-group-usage-report.md):</span></span>

- <span data-ttu-id="94415-130">받은 통화</span><span class="sxs-lookup"><span data-stu-id="94415-130">Received calls</span></span>

- <span data-ttu-id="94415-131">성공한 통화</span><span class="sxs-lookup"><span data-stu-id="94415-131">Successful calls</span></span>

- <span data-ttu-id="94415-132">제공된 통화</span><span class="sxs-lookup"><span data-stu-id="94415-132">Offered calls</span></span>

- <span data-ttu-id="94415-133">응답한 통화</span><span class="sxs-lookup"><span data-stu-id="94415-133">Answered calls</span></span>

- <span data-ttu-id="94415-134">전송된 통화</span><span class="sxs-lookup"><span data-stu-id="94415-134">Transferred calls</span></span>

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a><span data-ttu-id="94415-135">응답 그룹 통화 목록 보고서의 효과적인 활용</span><span class="sxs-lookup"><span data-stu-id="94415-135">Making the Best Use of the Response Group Call List Report</span></span>

<span data-ttu-id="94415-p109">응답 그룹 통화 목록 보고서를 사용하면 표시되는 데이터를 특정 응답 그룹 워크플로를 사용하는 통화로 제한할 수 있습니다. 이를 위해 워크플로 URI 상자에 워크플로 URI(워크플로의 SIP 주소)를 입력해야 합니다. 그러나 이렇게 하려면 실제로 워크플로 URI가 표시되어 있어야 합니다. 응답 그룹 통화 목록 보고서에 대한 필터링 옵션을 표시하려면 보고서 창 왼쪽 윗부분에 있는 매개 변수 표시/숨기기 단추를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p109">The Response Group Call List Report allows you to limit the displayed data to calls involving a particular Response Group workflow. To do that, you need to enter the workflow URI (the workflow's SIP address) in the Workflow URI box. Before you can do that, however, you must actually be able to see the Workflow URI box. To display the filtering options for the Response Group Call List Report, click the Show/Hide Parameters button in the upper left-hand portion of the report window.</span></span>

<span data-ttu-id="94415-140">응답 그룹 통화 목록에서는 응답 코드 또는 진단 ID 위에 마우스를 놓아도 이러한 메트릭에 대한 정보가 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94415-140">Note that the Response Group Call List does not display information about either the Response code or the Diagnostic ID if you hold the mouse over either of those metrics.</span></span> <span data-ttu-id="94415-141">자세한 정보가 필요한 경우 응답 코드 및/또는 진단 ID를 메모한 다음 비즈니스용 Skype 서버의 Top Failures 보고서에서 해당 값을 [검색할 수 있습니다.](top-failures-report.md)</span><span class="sxs-lookup"><span data-stu-id="94415-141">If you need more information, you might note the Response code and/or Diagnostic ID, and then search for those values in the [Top Failures Report in Skype for Business Server](top-failures-report.md).</span></span>

<span data-ttu-id="94415-142">"어떤 개별 워크플로에서 가장 많은 통화를 받았는가?"와 같은 질문에 대한 답을 확인하려면 다음과 같이 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94415-142">a question like this one: "Which individual workflow received the most calls?", you can do the following:</span></span>

1. <span data-ttu-id="94415-p111">응답 그룹 사용 보고서에서 원하는 기간을 설정한 후 받은 통화 메트릭을 클릭합니다. 그러면 응답 그룹 통화 목록 보고서가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p111">On the Response Group Usage Report, set the desired time period and then click the Received Calls metric. That will open the Response Group Call List Report.</span></span>

2. <span data-ttu-id="94415-p112">응답 그룹 통화 목록 보고서에 표시되는 데이터를 내보냅니다. 예를 들어 데이터를 Microsoft Excel 형식으로 내보낸 후에 Excel을 사용하여 해당 데이터를 쉼표로 구분된 값 파일로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p112">Export the data shown on the Response Group Call List Report. For example, you might export the data in Microsoft Excel format, and then use Excel to convert that data to a comma-separated values file.</span></span>

3. <span data-ttu-id="94415-147">Windows PowerShell을 사용하여 분석을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="94415-147">Run your analyses using Windows PowerShell.</span></span>

<span data-ttu-id="94415-148">예를 들어 데이터를 C:\Data\Response_Group_Call_List_Report.csv라는 이름의 파일에 저장한 경우 다음 명령을 사용하면 보고서에 나열된 각 워크플로의 수신된 총 통화 수가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="94415-148">For example, if you have saved the data to a file named C:\Data\Response_Group_Call_List_Report.csv, you can then use the following command to return the total number of received calls for each workflow listed in the report:</span></span>

```PowerShell
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

<span data-ttu-id="94415-149">다음과 같은 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="94415-149">That will information similar to this:</span></span>

<pre>
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
</pre>

## <a name="filters"></a><span data-ttu-id="94415-150">필터</span><span class="sxs-lookup"><span data-stu-id="94415-150">Filters</span></span>

<span data-ttu-id="94415-p113">필터를 사용하면 여러 방식으로 반환된 데이터를 보거나 보다 세부적으로 대상화된 데이터 집합을 반환할 수 있습니다. 다음 표에서는 응답 그룹 통화 목록 보고서에서 사용할 수 있는 필터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p113">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. The following table lists the filters that you can use with the Response Group Call List Report.</span></span>

<span data-ttu-id="94415-153">**응답 그룹 통화 목록 보고서 필터**</span><span class="sxs-lookup"><span data-stu-id="94415-153">**Response Group Call List Report Filters**</span></span>


| <span data-ttu-id="94415-154">**이름**</span><span class="sxs-lookup"><span data-stu-id="94415-154">**Name**</span></span>               | <span data-ttu-id="94415-155">**설명**</span><span class="sxs-lookup"><span data-stu-id="94415-155">**Description**</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="94415-156">**시작**</span><span class="sxs-lookup"><span data-stu-id="94415-156">**From**</span></span> <br/>         | <span data-ttu-id="94415-p114">시간 범위의 시작 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 시작 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p114">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span>  <br/> <span data-ttu-id="94415-159">2015/7/7 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="94415-159">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="94415-p115">시작 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시부터 시작됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p115">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="94415-162">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="94415-162">7/7/2015</span></span>  <br/> <span data-ttu-id="94415-163">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94415-163">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="94415-164">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="94415-164">7/3/2015</span></span>  <br/> <span data-ttu-id="94415-165">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="94415-165">Weeks always run from Sunday through Saturday.</span></span>  <br/> |
| <span data-ttu-id="94415-166">**To**</span><span class="sxs-lookup"><span data-stu-id="94415-166">**To**</span></span> <br/>           | <span data-ttu-id="94415-p116">시간 범위의 종료 날짜/시간입니다. 시간별 데이터를 보려면 다음과 같이 종료 날짜 및 시간을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p116">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span>  <br/> <span data-ttu-id="94415-169">2015/7/7 오후 1:00</span><span class="sxs-lookup"><span data-stu-id="94415-169">7/7/2015 1:00 PM</span></span>  <br/> <span data-ttu-id="94415-p117">종료 시간을 입력하지 않으면 보고서가 자동으로 지정된 날짜의 오전 12시에 종료됩니다. 일별 데이터를 보려면 날짜만 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94415-p117">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span>  <br/> <span data-ttu-id="94415-172">7/7/2015</span><span class="sxs-lookup"><span data-stu-id="94415-172">7/7/2015</span></span>  <br/> <span data-ttu-id="94415-173">주 또는 월별로 보려면 데이터를 보려는 해당 주 또는 월에 속하는 날짜를 입력합니다. 주 또는 월의 첫 번째 날짜를 입력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94415-173">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span>  <br/> <span data-ttu-id="94415-174">7/3/2015</span><span class="sxs-lookup"><span data-stu-id="94415-174">7/3/2015</span></span>  <br/> <span data-ttu-id="94415-175">주는 항상 일요일부터 토요일까지로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="94415-175">Weeks always run from Sunday through Saturday.</span></span>  <br/>        |
| <span data-ttu-id="94415-176">**워크플로 URI**</span><span class="sxs-lookup"><span data-stu-id="94415-176">**Workflow URI**</span></span> <br/> | <span data-ttu-id="94415-p118">반환되는 데이터를 지정된 응답 그룹 워크플로로 제한할 수 있습니다. 이 필터를 사용하려면 워크플로 SIP 주소를 입력합니다. 예:</span><span class="sxs-lookup"><span data-stu-id="94415-p118">Enables you to limit the returned data to the specified Response Group workflow. To use this filter, enter the Workflow SIP address. For example:</span></span>  <br/> <span data-ttu-id="94415-180">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="94415-180">sip:helpdesk@litwareinc.com</span></span>  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| <span data-ttu-id="94415-181">**통화**</span><span class="sxs-lookup"><span data-stu-id="94415-181">**Calls**</span></span> <br/>        | <span data-ttu-id="94415-182">다음 통화 유형 중 하나를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94415-182">You can select one of the following call types:</span></span> <br/>  <span data-ttu-id="94415-183">받은 통화</span><span class="sxs-lookup"><span data-stu-id="94415-183">Received Calls</span></span> <br/>  <span data-ttu-id="94415-184">성공한 통화</span><span class="sxs-lookup"><span data-stu-id="94415-184">Successful Calls</span></span> <br/>  <span data-ttu-id="94415-185">제공된 통화</span><span class="sxs-lookup"><span data-stu-id="94415-185">Offered Calls</span></span> <br/>  <span data-ttu-id="94415-186">응답한 통화</span><span class="sxs-lookup"><span data-stu-id="94415-186">Answered Calls</span></span> <br/>  <span data-ttu-id="94415-187">전송된 통화</span><span class="sxs-lookup"><span data-stu-id="94415-187">Transferred Calls</span></span> <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a><span data-ttu-id="94415-188">메트릭</span><span class="sxs-lookup"><span data-stu-id="94415-188">Metrics</span></span>

<span data-ttu-id="94415-189">다음 표에서는 응답 그룹 응용 프로그램에서 수신된 각 통화에 대해 응답 그룹 통화 목록 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="94415-189">The following table lists the information provided in the Response Group Call List Report for each call received by the Response Group application.</span></span>

<span data-ttu-id="94415-190">**응답 그룹 통화 목록 보고서 메트릭**</span><span class="sxs-lookup"><span data-stu-id="94415-190">**Response Group Call List Report Metrics**</span></span>

|<span data-ttu-id="94415-191">**이름**</span><span class="sxs-lookup"><span data-stu-id="94415-191">**Name**</span></span>|<span data-ttu-id="94415-192">**이 항목에 대한 정렬 가능 여부**</span><span class="sxs-lookup"><span data-stu-id="94415-192">**Can you sort on this item?**</span></span>|<span data-ttu-id="94415-193">**설명**</span><span class="sxs-lookup"><span data-stu-id="94415-193">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="94415-194">**발신자**</span><span class="sxs-lookup"><span data-stu-id="94415-194">**Caller**</span></span> <br/> |<span data-ttu-id="94415-195">아니요</span><span class="sxs-lookup"><span data-stu-id="94415-195">No</span></span>  <br/> |<span data-ttu-id="94415-196">발신자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="94415-196">SIP address of the caller.</span></span>  <br/> |
|<span data-ttu-id="94415-197">**워크플로**</span><span class="sxs-lookup"><span data-stu-id="94415-197">**Workflow**</span></span> <br/> |<span data-ttu-id="94415-198">아니요</span><span class="sxs-lookup"><span data-stu-id="94415-198">No</span></span>  <br/> |<span data-ttu-id="94415-199">응답 그룹 워크플로의 SIP 주소입니다</span><span class="sxs-lookup"><span data-stu-id="94415-199">SIP address of the Response Group workflow.</span></span>  <br/> |
|<span data-ttu-id="94415-200">**시작 시간**</span><span class="sxs-lookup"><span data-stu-id="94415-200">**Start time**</span></span> <br/> |<span data-ttu-id="94415-201">아니요</span><span class="sxs-lookup"><span data-stu-id="94415-201">No</span></span>  <br/> |<span data-ttu-id="94415-202">통화가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="94415-202">Date and time that the call started.</span></span>  <br/> |
|<span data-ttu-id="94415-203">**종료 시간**</span><span class="sxs-lookup"><span data-stu-id="94415-203">**End time**</span></span> <br/> |<span data-ttu-id="94415-204">아니요</span><span class="sxs-lookup"><span data-stu-id="94415-204">No</span></span>  <br/> |<span data-ttu-id="94415-205">통화가 종료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="94415-205">Date and time that the call ended.</span></span>  <br/> |
|<span data-ttu-id="94415-206">**응답 코드**</span><span class="sxs-lookup"><span data-stu-id="94415-206">**Response code**</span></span> <br/> |<span data-ttu-id="94415-207">아니요</span><span class="sxs-lookup"><span data-stu-id="94415-207">No</span></span>  <br/> |<span data-ttu-id="94415-208">세션이 실패했을 때 전송된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="94415-208">SIP response code sent when the session failed.</span></span>  <br/> |
|<span data-ttu-id="94415-209">**진단 ID**</span><span class="sxs-lookup"><span data-stu-id="94415-209">**Diagnostic ID**</span></span> <br/> |<span data-ttu-id="94415-210">아니요</span><span class="sxs-lookup"><span data-stu-id="94415-210">No</span></span>  <br/> |<span data-ttu-id="94415-211">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="94415-211">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span>  <br/> |


