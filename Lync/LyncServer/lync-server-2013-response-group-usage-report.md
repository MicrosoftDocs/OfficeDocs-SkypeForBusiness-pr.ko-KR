---
title: 'Lync Server 2013: 응답 그룹 사용 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9334fea5bded88b4f2453f46a0848819743766d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-usage-report-in-lync-server-2013"></a><span data-ttu-id="3c0bd-102">Lync Server 2013의 응답 그룹 사용 보고서</span><span class="sxs-lookup"><span data-stu-id="3c0bd-102">Response Group Usage Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c0bd-103">_**마지막으로 수정한 주제:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="3c0bd-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="3c0bd-104">응답 그룹 응용 프로그램은 Microsoft Lync Server 2013에서 전화를 걸고, 선택적으로 발신자의 질문에 대 한 회신에 대 한 응답 및 라우팅 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-104">The Response Group application provides a way for Microsoft Lync Server 2013 to answer and route phone calls based on the number that was dialed and, optionally, on the caller's responses to a series of questions.</span></span> <span data-ttu-id="3c0bd-105">일반적으로 응답 그룹 통화는 개인 사람에 게 라우팅되지 않지만, 대신 상담원 그룹 이라고 하는 사용자의 팀으로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-105">Typically, Response Group calls are not routed to an individual person but, instead, are routed to a team of people referred to as an agent group.</span></span> <span data-ttu-id="3c0bd-106">예를 들어 사용자가 지원 센터 번호로 전화를 걸 경우 Lync Server 2013는 해당 통화를 사용 가능한 첫 번째 지원 센터 에이전트로 자동으로 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-106">For example, if someone calls the phone number for your help desk, Lync Server 2013 can automatically route that call to the first available help desk agent.</span></span> <span data-ttu-id="3c0bd-107">또는 Lync Server가 일련의 질문을 할 수 있습니다 (하드웨어 문제가 있는 경우 1 번 누름).</span><span class="sxs-lookup"><span data-stu-id="3c0bd-107">Alternatively, Lync Server could ask a series of questions ("Press 1 if you are having hardware problems.</span></span> <span data-ttu-id="3c0bd-108">소프트웨어 문제가 있는 경우 2를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-108">Press 2 if you are having software problems.</span></span> <span data-ttu-id="3c0bd-109">네트워크 문제가 발생 하는 경우 3을 누릅니다. ") 그런 다음 해당 질문에 대 한 답변을 기준으로 가장 적절 한 지원 센터 상담원에 게 통화를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-109">Press 3 if you are having network problems.") and then route the call to the most appropriate help desk agent based on the answer to those questions.</span></span>

<span data-ttu-id="3c0bd-110">응답 그룹 사용 보고서는 모든 응답 그룹 워크플로에서 받은 전화 통화 수에 대 한 자세한 정보를 제공 하 고, 해당 통화는 제공 되는 통화, 응답 통화, 중단 된 통화 등의 더 많은 유한 범주로 분류 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-110">The Response Group Usage Report provides a detailed look at the number of phone calls received by all your Response Group workflows, then breaks those calls down into more finite categories such as Offered calls, Answered calls, and Abandoned calls.</span></span>

<span data-ttu-id="3c0bd-111">응답 그룹 사용 보고서를 사용 하 여 작업 하는 열쇠는 보고 된 통화 유형의 차이점을 이해 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-111">The key to working with the Response Group Usage Report is to understand the difference between the reported call types:</span></span>

  - <span data-ttu-id="3c0bd-112">**전화 받음**.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-112">**Received calls**.</span></span> <span data-ttu-id="3c0bd-113">응답 그룹 응용 프로그램의 모든 인스턴스에서 받은 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-113">Total number of calls received by all instances of the Response Group application.</span></span>

  - <span data-ttu-id="3c0bd-114">**통화 했습니다**.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-114">**Successful calls**.</span></span> <span data-ttu-id="3c0bd-115">응답 그룹 응용 프로그램이 선택한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-115">Total number of calls that were picked up by the Response Group application.</span></span>

  - <span data-ttu-id="3c0bd-116">**제공**되는 통화.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-116">**Offered calls**.</span></span> <span data-ttu-id="3c0bd-117">응답 그룹 에이전트로 전송 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-117">Total number of calls that were transferred to a Response Group agent.</span></span>

  - <span data-ttu-id="3c0bd-118">**통화 응답**.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-118">**Answered calls**.</span></span> <span data-ttu-id="3c0bd-119">응답 그룹 에이전트에서 실제로 응답 한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-119">Total number of calls that were actually answered by a Response Group agent.</span></span>

  - <span data-ttu-id="3c0bd-120">**중단 된 통화의 백분율**입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-120">**Percentage of abandoned calls**.</span></span> <span data-ttu-id="3c0bd-121">응답 그룹 응용 프로그램에서 받았지만 에이전트에서 응답 하지 않은 통화의 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-121">Percentage of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="3c0bd-122">이 값은 수신 전화에서 응답 한 전화를 뺀 다음 해당 값을 수신 된 통화 수로 나누는 방법으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-122">This value is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of Received calls.</span></span> <span data-ttu-id="3c0bd-123">예를 들어 10 개의 통화를 받고 7 개가 응답 한 경우에는 3 개의 응답 하지 않은 통화를 종료 하 고 10에서 7을 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-123">For example, if you received 10 calls and 7 were answered, you would subtract 7 from 10, leaving 3 unanswered calls.</span></span> <span data-ttu-id="3c0bd-124">이 값을 10으로 나누면 30%의 통화 백분율이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-124">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span>

  - <span data-ttu-id="3c0bd-125">**통화를 전송**했습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-125">**Transferred calls**.</span></span> <span data-ttu-id="3c0bd-126">큐 시간 제한 또는 큐 오버플로 때문에 전송 된 총 응답 그룹 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-126">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span>

<span data-ttu-id="3c0bd-127">응답 그룹 사용 보고서를 보고 있는 경우 이러한 호출 형식에 대 한 정의를 잊어버린 경우 적절 한 콜 형식 레이블 위에 마우스를 놓고 놓기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-127">If you are looking at the Response Group Usage Report and can't remember the definition for any of these call types, simply hold your mouse over the appropriate call type label.</span></span> <span data-ttu-id="3c0bd-128">통화 유형에 대 한 간략 한 설명을 제공 하는 도구 설명이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-128">A tooltip will appear that offers a brief description of the call type.</span></span>

<span data-ttu-id="3c0bd-129">응답 그룹 사용 보고서를 사용 하면 워크플로 URI (해당 워크플로와 연결 된 SIP 주소)를 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-129">The Response Group Usage Report allows you to filter on a workflow URI (the SIP address associated with that workflow).</span></span> <span data-ttu-id="3c0bd-130">그러나 워크플로 Uri는 보고서 자체에 실제로 나타나지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-130">However, workflow URIs do not actually appear on the report itself.</span></span> <span data-ttu-id="3c0bd-131">가장 많은 통화에 응답 하는 워크플로 또는 가장 많이 전송 되는 전화를 받은 워크플로 등의 항목을 알고 싶은 경우 적절 한 메트릭을 클릭 하 여 해당 기간에 대 한 응답 그룹 통화 목록 보고서를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-131">If you would like to know things such as which workflows are answering the most calls or which workflows are experiencing the most transferred calls, click the appropriate metric to open the Response Group Call List Report for that given time period.</span></span> <span data-ttu-id="3c0bd-132">해당 보고서에 워크플로 Uri가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-132">That reports does list the workflow URIs.</span></span>

<div>

## <a name="accessing-the-response-group-usage-report"></a><span data-ttu-id="3c0bd-133">응답 그룹 사용 현황 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="3c0bd-133">Accessing the Response Group Usage Report</span></span>

<span data-ttu-id="3c0bd-134">응답 그룹 사용 보고서는 모니터링 보고서 홈 페이지에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-134">The Response Group Usage Report is accessed from the Monitoring Reports home page.</span></span> <span data-ttu-id="3c0bd-135">다음 메트릭 중 하나를 클릭 하 여 [Lync Server 2013의 응답 그룹 통화 목록 보고서](lync-server-2013-response-group-call-list-report.md) 로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-135">You can drill down to the [Response Group Call List Report in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) by clicking any of the following metrics:</span></span>

  - <span data-ttu-id="3c0bd-136">수신 전화</span><span class="sxs-lookup"><span data-stu-id="3c0bd-136">Received calls</span></span>

  - <span data-ttu-id="3c0bd-137">성공한 통화</span><span class="sxs-lookup"><span data-stu-id="3c0bd-137">Successful calls</span></span>

  - <span data-ttu-id="3c0bd-138">제공 되는 통화</span><span class="sxs-lookup"><span data-stu-id="3c0bd-138">Offered calls</span></span>

  - <span data-ttu-id="3c0bd-139">응답 한 전화</span><span class="sxs-lookup"><span data-stu-id="3c0bd-139">Answered calls</span></span>

  - <span data-ttu-id="3c0bd-140">통화 전송</span><span class="sxs-lookup"><span data-stu-id="3c0bd-140">Transferred calls</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a><span data-ttu-id="3c0bd-141">응답 그룹 사용 현황 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="3c0bd-141">Making the Best Use of the Response Group Usage Report</span></span>

<span data-ttu-id="3c0bd-142">응답 그룹의 사용 현황 보고서에 대 한 사용 정보를 검색 하는 기능에 대 한 보다 흥미로운 방법 중 하나가 바로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-142">One of the more interesting uses of the Response Group Usage Report might not be readily apparent: the ability to retrieve usage information for a single Response Group workflow.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="3c0bd-143">응답 그룹 워크플로는 사용자가 특정 전화 번호로 전화를 걸 때의 Lync Server의 기능을 결정 하는 지침 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-143">A Response Group workflow is basically a set of instructions that determines what Lync Server does when a user dials a particular phone number.</span></span> <span data-ttu-id="3c0bd-144">이 끝까지 각 워크플로는 전화 번호와 고유 하 게 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-144">To that end, each workflow is uniquely associated with a phone number.</span></span> <span data-ttu-id="3c0bd-145">다른 사용자가 해당 번호를 호출 하는 경우 워크플로는 호출 처리 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-145">When someone calls that number, the workflow determines how the call will be handled.</span></span> <span data-ttu-id="3c0bd-146">예를 들어 워크플로는 호출자에 게 추가 정보를 입력 하 라는 메시지가 표시 되는 IVR (대화형 음성 응답) 질문으로 경로를 지정할 수 있습니다 ("하드웨어 지원의 경우 1을 누름.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-146">For example, the workflow might cause the call to be routed to a series of interactive voice response (IVR) questions that prompt the caller to enter additional information ("Press 1 for hardware support.</span></span> <span data-ttu-id="3c0bd-147">소프트웨어 지원을 보려면 2를 누릅니다. ").</span><span class="sxs-lookup"><span data-stu-id="3c0bd-147">Press 2 for software support.").</span></span> <span data-ttu-id="3c0bd-148">또는 워크플로가 통화에 응답 하는 데 사용 될 때까지 호출자가 대기 상태로 전환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-148">Alternatively, the workflow might cause the call to be placed in a queue , with the caller put on hold until an agent is available to answer the call.</span></span> <span data-ttu-id="3c0bd-149">전화를 받기 위한 에이전트의 사용 가능성 또한 워크플로를 사용 하 여 비즈니스 시간 (일주일의 요일 및 상담원이 전화를 받을 수 있는 시간) 및 휴일 (워크플로가 응답을 사용할 수 없는 경우 일)을 구성할 수 있습니다. 통화).</span><span class="sxs-lookup"><span data-stu-id="3c0bd-149">The availability of agents to answer calls is also dictated by the workflow: workflows are used to configure both business hours (the days of the week and the times of day when agents are available to answer calls) and holidays (days when no agents are available to answer calls).</span></span> <span data-ttu-id="3c0bd-150">응답 그룹 응용 프로그램에 속하는 전화 번호로 전화를 걸 때마다 기본적으로 응답 그룹 워크플로를 호출 하 게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-150">Any time you dial a phone number that belongs to the Response Group application you are essentially calling a Response Group workflow.</span></span>



</div>

<span data-ttu-id="3c0bd-151">응답 그룹 사용 보고서에는 워크플로 Uri가 표시 되지 않지만 종종 매우 유용한 단일 워크플로에 대 한 사용 현황 통계를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-151">Although workflow URIs do not appear in the Response Group Usage Report, it's still possible to view the usage statistics for a single workflow, something that is often extremely useful.</span></span> <span data-ttu-id="3c0bd-152">예를 들어 최근에 새 광고 캠페인을 unveiled 사용자가 해당 제품에 대 한 질문에 전화를 거는 지 여부를 알고 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-152">For example, suppose you recently unveiled a new ad campaign and are curious to know whether people are calling in to ask about that product.</span></span> <span data-ttu-id="3c0bd-153">광고 캠페인에 제공 된 전화 번호와 함께 응답 그룹 워크플로를 연결한 경우 해당 번호로 전화를 거는 사용자가 얼마나 되는지 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-153">If you have associated a Response Group workflow with the phone number given in the ad campaign, you can easily check to see how many people (if any) are calling that number.</span></span>

<span data-ttu-id="3c0bd-154">또한 유사한 방법을 사용 하 여 내부 헬프 데스크 또는 고객 서비스 부서로 처리 되는 통화 수를 측정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-154">You might also use a similar approach to gauge the number of calls being handled by your internal help desk or your customer service department.</span></span>

<span data-ttu-id="3c0bd-155">특정 워크플로에 대 한 사용 현황 통계를 검토 하려면 워크플로 URI 상자에 워크플로 URI를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-155">To review usage statistics for a particular workflow, enter the workflow URI in the Workflow URI box.</span></span> <span data-ttu-id="3c0bd-156">참고로, 워크플로 Uri (워크플로와 연결 된 SIP 주소)는 보고서에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-156">Of course, as noted, workflow URIs (the SIP address associated with a workflow) do not appear on the report.</span></span> <span data-ttu-id="3c0bd-157">즉, 워크플로의 URI를 확인 하는 다른 방법을 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-157">That means you need to find some other way to determine the URI of a workflow.</span></span> <span data-ttu-id="3c0bd-158">이 작업을 수행 하는 한 가지 방법은 Windows PowerShell 및 Lync Server Management Shell을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-158">One way to do this is to use Windows PowerShell and the Lync Server Management Shell.</span></span> <span data-ttu-id="3c0bd-159">예를 들어이 명령은 모든 응답 그룹 워크플로에 대 한 Uri를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-159">For example, this command returns the URIs for all your Response Group workflows:</span></span>

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

<span data-ttu-id="3c0bd-160">이는 다음과 같은 데이터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-160">That will return data similar to this:</span></span>

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

<span data-ttu-id="3c0bd-161">이 명령은 이름 새 광고 캠페인이 있는 단일 워크플로에 대 한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-161">This command returns information for a single workflow, the one with the name New Ad Campaign:</span></span>

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a><span data-ttu-id="3c0bd-162">필터가</span><span class="sxs-lookup"><span data-stu-id="3c0bd-162">Filters</span></span>

<span data-ttu-id="3c0bd-163">필터를 통해 더욱 세밀 하 게 대상 지정 된 데이터 집합을 반환 하거나 반환 된 데이터를 다양 한 방식으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-163">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="3c0bd-164">예를 들어 응답 그룹 사용 현황 보고서를 통해 모든 응답 그룹 워크플로에 대 한 데이터를 보거나 개별 워크플로에 대 한 데이터를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-164">For example, the Response Group Usage Report enables you to view data for all your Response Group workflows or to view data for an individual workflow.</span></span> <span data-ttu-id="3c0bd-165">데이터 그룹화 방법을 선택할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-165">You can also choose how data should be grouped.</span></span> <span data-ttu-id="3c0bd-166">이 경우 사용량은 시간, 일, 주 또는 월로 그룹화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-166">In this case, usages are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="3c0bd-167">다음 표에는 응답 그룹 사용 보고서와 함께 사용할 수 있는 필터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-167">The following table lists the filters that you can use with the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-filters"></a><span data-ttu-id="3c0bd-168">응답 그룹 사용 현황 보고서 필터</span><span class="sxs-lookup"><span data-stu-id="3c0bd-168">Response Group Usage Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c0bd-169">이름</span><span class="sxs-lookup"><span data-stu-id="3c0bd-169">Name</span></span></th>
<th><span data-ttu-id="3c0bd-170">설명</span><span class="sxs-lookup"><span data-stu-id="3c0bd-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c0bd-171"><strong>보낸 사람</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-171"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-172">시간 범위의 시작 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-172">Start date/time for the time range.</span></span> <span data-ttu-id="3c0bd-173">시간별로 데이터를 보려면 시작 날짜와 시간을 모두 다음과 같이 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-173">To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="3c0bd-174">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="3c0bd-174">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3c0bd-175">시작 시간을 입력 하지 않으면 지정한 날짜에 오전 12:00부터 보고서가 자동으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-175">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day.</span></span> <span data-ttu-id="3c0bd-176">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-176">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3c0bd-177">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3c0bd-177">7/7/2012</span></span></p>
<p><span data-ttu-id="3c0bd-178">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="3c0bd-178">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3c0bd-179">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3c0bd-179">7/3/2012</span></span></p>
<p><span data-ttu-id="3c0bd-180">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-180">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c0bd-181"><strong>받는 사람</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-181"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-182">시간 범위의 종료 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-182">End date/time for the time range.</span></span> <span data-ttu-id="3c0bd-183">시간별로 데이터를 보려면 다음과 같이 종료 날짜와 시간을 모두 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-183">To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="3c0bd-184">오후 7/7/2012 1:00</span><span class="sxs-lookup"><span data-stu-id="3c0bd-184">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="3c0bd-185">종료 시간을 입력 하지 않으면 지정한 날짜에 12:00 오전에 보고서가 자동으로 종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-185">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day.</span></span> <span data-ttu-id="3c0bd-186">날짜별로 데이터를 보려면 날짜만 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-186">To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="3c0bd-187">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="3c0bd-187">7/7/2012</span></span></p>
<p><span data-ttu-id="3c0bd-188">주별 또는 월별로 보려면 보려는 주 또는 월의 어디에 나 날짜를 입력 합니다 (주 또는 월의 첫 번째 요일을 입력할 필요는 없음).</span><span class="sxs-lookup"><span data-stu-id="3c0bd-188">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="3c0bd-189">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="3c0bd-189">7/3/2012</span></span></p>
<p><span data-ttu-id="3c0bd-190">주는 항상 일요일 ~ 토요일을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-190">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c0bd-191"><strong>간격만</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-191"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-192">시간 간격.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-192">Time interval.</span></span> <span data-ttu-id="3c0bd-193">다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-193">Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="3c0bd-194">매시간 (최대 25 시간 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="3c0bd-194">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3c0bd-195">매일 (최대 31 일이 표시 될 수 있음)</span><span class="sxs-lookup"><span data-stu-id="3c0bd-195">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3c0bd-196">주간 (최대 12 주를 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="3c0bd-196">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="3c0bd-197">월간 (최대 12 개월을 표시할 수 있음)</span><span class="sxs-lookup"><span data-stu-id="3c0bd-197">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="3c0bd-198">시작 및 끝 날짜가 선택한 기간에 허용 되는 최대 값을 초과 하는 경우에는 시작 날짜부터 시작 하 여 최대 값만 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-198">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) is displayed.</span></span> <span data-ttu-id="3c0bd-199">예를 들어 시작 날짜가 7/7/2012이 고 종료 날짜가 2/28/2012 인 일일 간격을 선택 하는 경우에는 8/7/2012 12:00 AM ~ 9/7/2012 12:00 AM (즉, 총 31 일 "의 데이터)에 대 한 데이터가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-199">For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c0bd-200"><strong>워크플로 URI</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-200"><strong>Workflow URI</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-201">반환 되는 데이터를 지정 된 응답 그룹 워크플로로 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-201">Enables you to limit the returned data to the specified Response Group workflow.</span></span> <span data-ttu-id="3c0bd-202">이 필터를 사용 하려면 워크플로 SIP 주소를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-202">To use this filter, enter the Workflow SIP address.</span></span> <span data-ttu-id="3c0bd-203">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-203">For example:</span></span></p>
<p><span data-ttu-id="3c0bd-204">sip:helpdesk@litwareinc.com</span><span class="sxs-lookup"><span data-stu-id="3c0bd-204">sip:helpdesk@litwareinc.com</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="3c0bd-205">매트릭스</span><span class="sxs-lookup"><span data-stu-id="3c0bd-205">Metrics</span></span>

<span data-ttu-id="3c0bd-206">다음 표에는 응답 그룹 사용 보고서에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-206">The following table lists the information provided in the Response Group Usage Report.</span></span>

### <a name="response-group-usage-report-metrics"></a><span data-ttu-id="3c0bd-207">응답 그룹 사용 현황 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="3c0bd-207">Response Group Usage Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c0bd-208">이름</span><span class="sxs-lookup"><span data-stu-id="3c0bd-208">Name</span></span></th>
<th><span data-ttu-id="3c0bd-209">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="3c0bd-209">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="3c0bd-210">설명</span><span class="sxs-lookup"><span data-stu-id="3c0bd-210">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c0bd-211"><strong>마다</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-211"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="3c0bd-212"><strong>Daily</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-212"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="3c0bd-213"><strong>매주</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-213"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="3c0bd-214"><strong>월간</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-214"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-215">아니요</span><span class="sxs-lookup"><span data-stu-id="3c0bd-215">No</span></span></p></td>
<td><p><span data-ttu-id="3c0bd-216">선택한 시간 간격을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-216">Indicates the selected time interval.</span></span> <span data-ttu-id="3c0bd-217">해당 되는 경우 지정 된 시간 간격을 클릭 하 여 해당 간격에 대 한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-217">Where applicable, you can click a given time interval to view detailed information for that interval.</span></span> <span data-ttu-id="3c0bd-218">예를 들어 일일 기간을 사용 하는 경우 7/7/2012을 클릭 하면 해당 날짜에 대 한 사용자 등록 작업을 시간별로 분류 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-218">For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c0bd-219"><strong>수신 전화</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-219"><strong>Received calls</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-220">아니요</span><span class="sxs-lookup"><span data-stu-id="3c0bd-220">No</span></span></p></td>
<td><p><span data-ttu-id="3c0bd-221">응답 그룹 응용 프로그램의 모든 인스턴스에서 받은 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-221">Total number of calls received by all instances of the Response Group application.</span></span> <span data-ttu-id="3c0bd-222">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 응답 그룹 통화 목록 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-222">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c0bd-223"><strong>성공한 통화</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-223"><strong>Successful calls</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-224">아니요</span><span class="sxs-lookup"><span data-stu-id="3c0bd-224">No</span></span></p></td>
<td><p><span data-ttu-id="3c0bd-225">응답 그룹 응용 프로그램을 선택한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-225">Total number of calls that were picked up the Response Group application.</span></span> <span data-ttu-id="3c0bd-226">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 응답 그룹 통화 목록 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-226">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c0bd-227"><strong>제공 되는 통화</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-227"><strong>Offered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-228">아니요</span><span class="sxs-lookup"><span data-stu-id="3c0bd-228">No</span></span></p></td>
<td><p><span data-ttu-id="3c0bd-229">응답 그룹 에이전트로 전송 된 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-229">Total number of calls that were transferred to a Response Group agent.</span></span> <span data-ttu-id="3c0bd-230">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 응답 그룹 통화 목록 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-230">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c0bd-231"><strong>응답 한 전화</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-231"><strong>Answered calls</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-232">아니요</span><span class="sxs-lookup"><span data-stu-id="3c0bd-232">No</span></span></p></td>
<td><p><span data-ttu-id="3c0bd-233">응답 그룹 에이전트에서 실제로 응답 한 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-233">Total number of calls that were actually answered by a Response Group agent.</span></span> <span data-ttu-id="3c0bd-234">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 응답 그룹 통화 목록 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-234">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c0bd-235"><strong>중단 된 통화 비율</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-235"><strong>Percentage of abandoned calls</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-236">아니요</span><span class="sxs-lookup"><span data-stu-id="3c0bd-236">No</span></span></p></td>
<td><p><span data-ttu-id="3c0bd-237">응답 그룹 응용 프로그램에서 받았지만 에이전트에서 응답 하지 않은 총 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-237">Total number of calls that were received by the Response Group application but were never answered by an agent.</span></span> <span data-ttu-id="3c0bd-238">이는 수신 전화에서 응답 한 전화를 뺀 다음 해당 값을 수신 된 통화 수로 나누는 방법으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-238">This is calculated by subtracting the Answered calls from the Received calls, and then dividing that value by the number of received calls.</span></span> <span data-ttu-id="3c0bd-239">예를 들어 10 개의 수신 통화가 있고 7 개에 응답 한 경우 10에서 7을 빼서 응답 하지 않은 세 개의 통화를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-239">For example, if you have 10 received calls and seven were answered, you would subtract seven from 10, leaving three unanswered calls.</span></span> <span data-ttu-id="3c0bd-240">이 값을 10으로 나누면 30%의 통화 백분율이 중단 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-240">That value would then be divided by 10, giving you an abandoned call percentage of 30%.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c0bd-241"><strong>에이전트 별 평균 통화 시간 (분)</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-241"><strong>Average call minutes by agent</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-242">아니요</span><span class="sxs-lookup"><span data-stu-id="3c0bd-242">No</span></span></p></td>
<td><p><span data-ttu-id="3c0bd-243">응답 그룹 에이전트가 통화에 소요한 평균 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-243">Average amount of time a Response Group agent spent on a call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c0bd-244"><strong>통화 전송</strong></span><span class="sxs-lookup"><span data-stu-id="3c0bd-244"><strong>Transferred calls</strong></span></span></p></td>
<td><p><span data-ttu-id="3c0bd-245">아니요</span><span class="sxs-lookup"><span data-stu-id="3c0bd-245">No</span></span></p></td>
<td><p><span data-ttu-id="3c0bd-246">큐 시간 제한 또는 큐 오버플로 때문에 전송 된 총 응답 그룹 통화 수입니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-246">Total number of Response Group calls that were transferred because of a queue timeout or queue overflow.</span></span> <span data-ttu-id="3c0bd-247">이 항목을 클릭 하면 보고서에 선택한 기간에 대 한 응답 그룹 통화 목록 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c0bd-247">When you click this item, the report shows you the Response Group Call List report for the selected time period.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

