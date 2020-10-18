---
title: 'Lync Server 2013: 오류 목록 보고서'
description: 'Lync Server 2013: 오류 목록 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failure List Report
ms:assetid: b6f3a605-e0c6-461e-b17a-41d8039ace9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615446(v=OCS.15)
ms:contentKeyID: 48185194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7467144fe207ab61fd086cd35aac74779fd4f771
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575054"
---
# <a name="failure-list-report-in-lync-server-2013"></a><span data-ttu-id="ce7e9-103">Lync Server 2013의 오류 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="ce7e9-103">Failure List Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce7e9-104">_**마지막으로 수정 된 항목:** 2012-07-02_</span><span class="sxs-lookup"><span data-stu-id="ce7e9-104">_**Topic Last Modified:** 2012-07-02_</span></span>

<span data-ttu-id="ce7e9-p101">오류 목록 보고서에서는 실패한 피어 투 피어 또는 회의 세션에 참가한 개별 참가자에 대한 정보를 제공합니다. 이 정보에는 문제를 경험한 사용자의 URI와 실패와 관련된 SIP 응답 코드 및 진단 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-p101">The Failure List report provides information about the individual participants who took part in a failed peer-to-peer or conferencing session. This information includes the URI of the user who experienced the problem, as well as the SIP Response code and Diagnostic ID associated with the failure.</span></span>

<div>

## <a name="accessing-the-failure-list-report"></a><span data-ttu-id="ce7e9-107">오류 목록 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="ce7e9-107">Accessing the Failure List Report</span></span>

<span data-ttu-id="ce7e9-108">[Lync Server 2013의 실패 분포 보고서](lync-server-2013-failure-distribution-report.md)에서 다음 메트릭 중 하나를 클릭 하 여 오류 목록 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-108">The Failure List Report is accessed by clicking any of the following metrics on the [Failure Distribution Report in Lync Server 2013](lync-server-2013-failure-distribution-report.md):</span></span>

  - <span data-ttu-id="ce7e9-109">상위 진단 이유(세션)</span><span class="sxs-lookup"><span data-stu-id="ce7e9-109">Top diagnostic reasons (sessions)</span></span>

  - <span data-ttu-id="ce7e9-110">상위 형식(세션)</span><span class="sxs-lookup"><span data-stu-id="ce7e9-110">Top modalities (sessions)</span></span>

  - <span data-ttu-id="ce7e9-111">상위 풀(세션)</span><span class="sxs-lookup"><span data-stu-id="ce7e9-111">Top pools (sessions)</span></span>

  - <span data-ttu-id="ce7e9-112">상위 원본(세션)</span><span class="sxs-lookup"><span data-stu-id="ce7e9-112">Top sources (sessions)</span></span>

  - <span data-ttu-id="ce7e9-113">상위 구성 요소(세션)</span><span class="sxs-lookup"><span data-stu-id="ce7e9-113">Top components (sessions)</span></span>

  - <span data-ttu-id="ce7e9-114">상위 출처 사용자(세션)</span><span class="sxs-lookup"><span data-stu-id="ce7e9-114">Top from users (sessions)</span></span>

  - <span data-ttu-id="ce7e9-115">상위 대상 사용자(세션)</span><span class="sxs-lookup"><span data-stu-id="ce7e9-115">Top to users (sessions)</span></span>

  - <span data-ttu-id="ce7e9-116">상위 출처 사용자 에이전트(세션)</span><span class="sxs-lookup"><span data-stu-id="ce7e9-116">Top from user agents (sessions)</span></span>

<span data-ttu-id="ce7e9-117">실패 목록 보고서에서 피어 투 피어 세션에 대 한 세션 세부 정보 메트릭을 클릭 하 여 [Lync Server 2013의 피어 투 피어 세션 정보 보고서](lync-server-2013-peer-to-peer-session-detail-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-117">From the Failure List Report you can access the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) by clicking the Session detail metric for a peer-to-peer session.</span></span> <span data-ttu-id="ce7e9-118">또한 전화 회의에 대한 전화 회의 메트릭을 클릭하여 전화 회의 정보 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-118">You can also access the Conference Detail Report by clicking the Conference metric for a conference.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-failure-list-report"></a><span data-ttu-id="ce7e9-119">오류 목록 보고서의 효과적인 활용</span><span class="sxs-lookup"><span data-stu-id="ce7e9-119">Making the Best Use of the Failure List Report</span></span>

<span data-ttu-id="ce7e9-p103">오류 목록 보고서에서는 각 응답 코드 또는 각 진단 ID 위에 마우스를 놓기만 하면 해당 값에 대한 설명을 볼 수 있습니다. 예를 들어 진단 ID 7025 위에 마우스를 놓으면 도구 설명에 다음이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-p103">In the Failure List Report, you can view a description for each Response code or each Diagnostic ID simply by holding your mouse over that value. For example, if you hold your mouse over Diagnostic ID 7025 you'll see the following displayed in a tooltip:</span></span>

<span data-ttu-id="ce7e9-122">사용자를 위한 미디어를 만드는 동안 내부 서버 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-122">Internal server error creating media for user.</span></span>

<span data-ttu-id="ce7e9-123">오류 목록 보고서는 하나 이상의 실패 한 세션에 참여 한 모든 사용자의 목록을 직접 검색 하지 않으며, 오류가 발생 한 세션과 가장 자주 관련 된 사용자를 확인 하는 방법도 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-123">It's important to note that the Failure List Report does not provide a straightforward way to directly retrieve a list of all the users who participated in at least one failed session, nor does it provide a way to determine which users were most-often involved in a failed session.</span></span> <span data-ttu-id="ce7e9-124">한 가지 경우에는 실패 목록 보고서에 필터링 기능이 없습니다. 그러나 데이터를 내보낸 다음 쉼표로 구분 된 값 파일로 변환 하면 Windows PowerShell을 사용 하 여 이와 같은 질문에 대 한 답변을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-124">(For one thing, the Failure List Report has no filtering capabilities.) However, if you export the data and then convert it to a comma-separated values file, you can use Windows PowerShell to find the answers to questions like those.</span></span> <span data-ttu-id="ce7e9-125">예를 들어 데이터를에 저장 한다고 가정 합니다. C: 라는 CSV 파일이 \\ \\List.csv 데이터 오류 \_ 입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-125">For example, suppose you save the data to a .CSV file named C:\\Data\\Failure\_List.csv.</span></span> <span data-ttu-id="ce7e9-126">이 명령은 하나 이상의 실패 한 세션에 포함 된 모든 사용자를 나열 하 고 해당 파일에 저장 된 데이터를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-126">Based on the data saved in that file, this command lists all the users who were involved in at least one failed session:</span></span>

    $failures = Import-Csv -Path " C:\Data\Failure_List.csv"
    $failure |Sort-Object "From user" | Select-Object "From user" -Unique

<span data-ttu-id="ce7e9-127">그러면 다음과 같은 목록이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-127">That command will return a list similar to this:</span></span>

    From user
    ----
    Pilar.Ackerman@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    David.Ahs@litwareinc.com
    Ken.Myer@litwareinc.com

<span data-ttu-id="ce7e9-128">다음 두 명령은 각 사용자가 참가한 실패한 총 세션 수를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-128">These two commands report back the total number of failed sessions that each user was involved in:</span></span>

    $failures = Import-Csv -Path "C:\Data\Failure_List.csv"
    $failures | Group-Object "From user" | Select-Object Count, Name | Sort-Object -Property Count -Descending

<span data-ttu-id="ce7e9-129">그러면 다음과 같은 데이터가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-129">That will return data similar to this:</span></span>

    Count    Name
     -----    ----
        20    Pilar.Ackerman@litwareinc.com
        20    David.Ahs@litwareinc.com
        16    Gilead.Amosnino@litwareinc.com
        16    Ken.Myero@litwareinc.com
        14    Henrik.Jensen@litwareinc.com

</div>

<div>

## <a name="filters"></a><span data-ttu-id="ce7e9-130">필터</span><span class="sxs-lookup"><span data-stu-id="ce7e9-130">Filters</span></span>

<span data-ttu-id="ce7e9-p105">없음. 오류 목록 보고서는 필터링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-p105">None. You cannot filter the Failure List Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="ce7e9-133">메트릭</span><span class="sxs-lookup"><span data-stu-id="ce7e9-133">Metrics</span></span>

<span data-ttu-id="ce7e9-134">다음 표에서는 각 실패한 통화에 대해 오류 목록 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-134">The following table lists the information provided in the Failure List Report for each failed call.</span></span>

### <a name="failure-list-report-metrics"></a><span data-ttu-id="ce7e9-135">오류 목록 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="ce7e9-135">Failure List Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce7e9-136">이름</span><span class="sxs-lookup"><span data-stu-id="ce7e9-136">Name</span></span></th>
<th><span data-ttu-id="ce7e9-137">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="ce7e9-137">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="ce7e9-138">설명</span><span class="sxs-lookup"><span data-stu-id="ce7e9-138">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce7e9-139"><strong>보고된 시간</strong></span><span class="sxs-lookup"><span data-stu-id="ce7e9-139"><strong>Reported time</strong></span></span></p></td>
<td><p><span data-ttu-id="ce7e9-140">아니요</span><span class="sxs-lookup"><span data-stu-id="ce7e9-140">No</span></span></p></td>
<td><p><span data-ttu-id="ce7e9-141">보고서가 기록된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-141">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce7e9-142"><strong>요청이</strong></span><span class="sxs-lookup"><span data-stu-id="ce7e9-142"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="ce7e9-143">아니요</span><span class="sxs-lookup"><span data-stu-id="ce7e9-143">No</span></span></p></td>
<td><p><span data-ttu-id="ce7e9-p106">실패한 SIP 요청 유형입니다. 예: INVITE 또는 BYE</span><span class="sxs-lookup"><span data-stu-id="ce7e9-p106">SIP request type that failed. For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce7e9-146"><strong>응답 코드</strong></span><span class="sxs-lookup"><span data-stu-id="ce7e9-146"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="ce7e9-147">아니요</span><span class="sxs-lookup"><span data-stu-id="ce7e9-147">No</span></span></p></td>
<td><p><span data-ttu-id="ce7e9-148">회의가 실패했을 때 전송된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-148">SIP response code sent when the conference failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce7e9-149"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="ce7e9-149"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="ce7e9-150">아니요</span><span class="sxs-lookup"><span data-stu-id="ce7e9-150">No</span></span></p></td>
<td><p><span data-ttu-id="ce7e9-151">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-151">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce7e9-152"><strong>참가 소요 시간(밀리초)</strong></span><span class="sxs-lookup"><span data-stu-id="ce7e9-152"><strong>Join cost time (ms)</strong></span></span></p></td>
<td><p><span data-ttu-id="ce7e9-153">아니요</span><span class="sxs-lookup"><span data-stu-id="ce7e9-153">No</span></span></p></td>
<td><p><span data-ttu-id="ce7e9-154">사용자가 전화 회의에 참가하기까지 소요된 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-154">Amount of time (in milliseconds) required for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce7e9-155"><strong>시작 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="ce7e9-155"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="ce7e9-156">아니요</span><span class="sxs-lookup"><span data-stu-id="ce7e9-156">No</span></span></p></td>
<td><p><span data-ttu-id="ce7e9-157">통화를 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-157">SIP address of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce7e9-158"><strong>출처 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="ce7e9-158"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="ce7e9-159">아니요</span><span class="sxs-lookup"><span data-stu-id="ce7e9-159">No</span></span></p></td>
<td><p><span data-ttu-id="ce7e9-160">통화를 시작한 사용자의 끝점에 사용된 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-160">Software used by the endpoint of the user who initiated the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce7e9-161"><strong>대상 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="ce7e9-161"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="ce7e9-162">아니요</span><span class="sxs-lookup"><span data-stu-id="ce7e9-162">No</span></span></p></td>
<td><p><span data-ttu-id="ce7e9-163">통화를 받고 있는 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="ce7e9-163">SIP address of the user who was being called.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

