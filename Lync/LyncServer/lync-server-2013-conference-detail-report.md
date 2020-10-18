---
title: 'Lync Server 2013: 전화 회의 정보 보고서'
description: 'Lync Server 2013: 전화 회의 정보 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 07c50b545f4a9ee3308a840fc2aa5a15e617a5bd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577634"
---
# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="6f09f-103">Lync Server 2013의 전화 회의 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="6f09f-103">Conference Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f09f-104">_**마지막으로 수정 된 항목:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="6f09f-104">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="6f09f-p101">전화 회의 정보 보고서에서는 전화 회의에 참가한 모든 사용자에 대한 자세한 정보를 제공합니다. 예를 들어 사용자가 전화 회의에 참가한 날짜/시간, 사용자가 전화 회의에서 나간 날짜/시간, 그리고 해당 사용자를 전화 회의에 연결하는 데 사용된 끝점의 사용자 에이전트와 같은 정보를 확인할 수 있습니다. 각 전화 회의에서 사용자의 역할(예: 발표자, 참석자) 관련 정보도 볼 수 있습니다. 그러나 가장 중요한 기능은 전화 회의에 정상적으로 참가하여 전화 회의를 완료한 사용자가 그렇지 않은 사용자를 빠르게 확인할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-p101">The Conference Detail Report provides detailed information about all the users who participated in a conference. For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference. You can also see information the user's role in each conference (for example, Presenter or Attendee). Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="6f09f-109">전화 회의 정보 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="6f09f-109">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="6f09f-110">다음 보고서에서 전화 회의 정보 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-110">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="6f09f-111">[Lync Server 2013의 통화 허용 제어 보고서](lync-server-2013-call-admission-control-report.md) (전화 회의에 대 한 세부 정보 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="6f09f-111">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="6f09f-112">[Lync Server 2013의 오류 목록 보고서](lync-server-2013-failure-list-report.md) (전화 회의 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="6f09f-112">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="6f09f-113">[Lync Server 2013의 사용자 활동 보고서](lync-server-2013-user-activity-report.md) (전화 회의 URI 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="6f09f-113">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="6f09f-114">전화 회의 정보 보고서에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 [Lync Server 2013의 진단 보고서](lync-server-2013-diagnostic-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-114">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="6f09f-115">필터</span><span class="sxs-lookup"><span data-stu-id="6f09f-115">Filters</span></span>

<span data-ttu-id="6f09f-p102">없음. 전화 회의 정보 보고서는 필터링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-p102">None. You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="6f09f-118">메트릭</span><span class="sxs-lookup"><span data-stu-id="6f09f-118">Metrics</span></span>

<span data-ttu-id="6f09f-119">다음 표에서는 전화 회의 정보 보고서의 전화 회의 정보 섹션에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-119">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="6f09f-120">전화 회의 정보 메트릭</span><span class="sxs-lookup"><span data-stu-id="6f09f-120">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f09f-121">이름</span><span class="sxs-lookup"><span data-stu-id="6f09f-121">Name</span></span></th>
<th><span data-ttu-id="6f09f-122">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="6f09f-122">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6f09f-123">설명</span><span class="sxs-lookup"><span data-stu-id="6f09f-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f09f-124"><strong>전화 회의 URI</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-124"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-p103">전화 회의에 할당된 URI입니다. 예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-p103">URI assigned to the conference. For example:</span></span></p>
<p><span data-ttu-id="6f09f-127">sip: kmyer@litwareinc .com, gruu, 불투명 = app: 회의: focus: id: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="6f09f-127">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f09f-128"><strong>풀 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-128"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-129">세션에 포함된 등록자 풀 또는 에지 서버의 정규화된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-129">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f09f-130"><strong>시작 시간</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-130"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-131">전화 회의가 시작된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-131">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f09f-132"><strong>구성 도우미</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-132"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-133">전화 회의를 구성한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-133">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f09f-134"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-134"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-135">전화 회의가 종료된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-135">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6f09f-136">다음 표에서는 전화 회의 정보 보고서의 전화 회의 참가 섹션에서 제공되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-136">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="6f09f-137">전화 회의 참가 메트릭</span><span class="sxs-lookup"><span data-stu-id="6f09f-137">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f09f-138">이름</span><span class="sxs-lookup"><span data-stu-id="6f09f-138">Name</span></span></th>
<th><span data-ttu-id="6f09f-139">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="6f09f-139">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6f09f-140">설명</span><span class="sxs-lookup"><span data-stu-id="6f09f-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f09f-141"><strong>사용자</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-141"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-142">전화 회의에 참가한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-142">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f09f-143"><strong>역할</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-143"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-144">전화 회의 참가자가 수행하는 역할(예: 발표자)입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-144">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f09f-145"><strong>연결</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-145"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-146">참가자의 네트워크 연결(일반적으로 내부 발신 또는 외부 발신)입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-146">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f09f-147">참가 시간</span><span class="sxs-lookup"><span data-stu-id="6f09f-147">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-148">참가자가 전화 회의에 참가한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-148">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f09f-149"><strong>나간 시간</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-149"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-150">참가자가 전화 회의에서 나간 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-150">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f09f-151"><strong>사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-151"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-152">참가자의 끝점에 사용된 소프트웨어의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-152">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f09f-153"><strong>진단 보고서</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-153"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-p104">진단 및 문제 해결 정보를 제공합니다. 여기에는 실패한 세션에 대한 SIP 응답 코드, 진단 헤더, 전화 회의 참가 시간 및 진단 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-p104">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6f09f-156">다음 표에서는 전화 회의 정보 보고서의 전화 회의 형식 섹션에서 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-156">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="6f09f-157">전화 회의 형식 메트릭</span><span class="sxs-lookup"><span data-stu-id="6f09f-157">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6f09f-158">이름</span><span class="sxs-lookup"><span data-stu-id="6f09f-158">Name</span></span></th>
<th><span data-ttu-id="6f09f-159">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="6f09f-159">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="6f09f-160">설명</span><span class="sxs-lookup"><span data-stu-id="6f09f-160">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6f09f-161"><strong>사용자</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-161"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-162">전화 회의에 참가한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-162">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f09f-163"><strong>참가 시간</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-163"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-164">참가자가 전화 회의에 참가한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-164">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f09f-165"><strong>나간 시간</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-165"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-166">참가자가 전화 회의에서 나간 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-166">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6f09f-167"><strong>전화 회의 서버</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-167"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-168">전화 회의에 사용된 전화 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-168">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6f09f-169"><strong>진단 보고서</strong></span><span class="sxs-lookup"><span data-stu-id="6f09f-169"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6f09f-p105">진단 및 문제 해결 정보를 제공합니다. 여기에는 실패한 세션에 대한 SIP 응답 코드, 진단 헤더, 전화 회의 참가 시간 및 진단 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f09f-p105">Provides diagnostic and troubleshooting information. Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

