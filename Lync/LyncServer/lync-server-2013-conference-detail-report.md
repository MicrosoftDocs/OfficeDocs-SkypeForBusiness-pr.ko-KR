---
title: 'Lync Server 2013: 컨퍼런스 세부 정보 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Detail Report
ms:assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204728(v=OCS.15)
ms:contentKeyID: 48183565
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac598c3f85211ad97f2d6266b74b6c524d76d006
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983867"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-detail-report-in-lync-server-2013"></a><span data-ttu-id="76a8d-102">Lync Server 2013의 회의 세부 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="76a8d-102">Conference Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="76a8d-103">_**마지막으로 수정한 주제:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="76a8d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="76a8d-104">회의 정보 보고서는 회의에 참가 한 모든 사용자에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-104">The Conference Detail Report provides detailed information about all the users who participated in a conference.</span></span> <span data-ttu-id="76a8d-105">예를 들어 사용자가 회의에 참가 한 날짜 및 시간과 사용자가 회의를 남긴 날짜 및 시간, 해당 사용자를 회의에 연결 하는 데 사용 된 끝점의 사용자 에이전트 등의 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-105">For example, you can see such information as the date and time that a user joined the conference, the date and time that the user left the conference, and the user agent of the endpoint that was used to connect that user to the conference.</span></span> <span data-ttu-id="76a8d-106">각 회의에서 사용자의 역할에 대 한 정보를 볼 수도 있습니다 (예: 발표자 또는 참석자).</span><span class="sxs-lookup"><span data-stu-id="76a8d-106">You can also see information the user's role in each conference (for example, Presenter or Attendee).</span></span> <span data-ttu-id="76a8d-107">가장 중요 한 점은 회의를 성공적으로 참가 하 고 완료 하는 사용자와 회의를 성공적으로 참가 및 완료할 수 없었던 사용자를 빠르게 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-107">Perhaps most important, you get quickly see which users successfully join and complete the conference, and which users were not able to successfully join and complete the conference.</span></span>

<div>

## <a name="accessing-the-conference-detail-report"></a><span data-ttu-id="76a8d-108">회의 세부 정보 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="76a8d-108">Accessing the Conference Detail Report</span></span>

<span data-ttu-id="76a8d-109">회의 세부 정보 보고서는 다음 보고서에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-109">The Conference Detail Report can be accessed from the following reports:</span></span>

  - <span data-ttu-id="76a8d-110">[Lync Server 2013의 통화 허용 제어 보고서](lync-server-2013-call-admission-control-report.md) (컨퍼런스에 대 한 세부 정보 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="76a8d-110">The [Call Admission Control Report in Lync Server 2013](lync-server-2013-call-admission-control-report.md) (by clicking the Detail metric for a conference)</span></span>

  - <span data-ttu-id="76a8d-111">[Lync Server 2013의 실패 목록 보고서](lync-server-2013-failure-list-report.md) (회의 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="76a8d-111">The [Failure List Report in Lync Server 2013](lync-server-2013-failure-list-report.md) (by clicking the Conference metric)</span></span>

  - <span data-ttu-id="76a8d-112">[Lync Server 2013의 사용자 활동 보고서](lync-server-2013-user-activity-report.md) (컨퍼런스 URI 메트릭 클릭)</span><span class="sxs-lookup"><span data-stu-id="76a8d-112">The [User Activity Report in Lync Server 2013](lync-server-2013-user-activity-report.md) (by clicking the Conference URI metric)</span></span>

<span data-ttu-id="76a8d-113">회의 정보 보고서에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 [Lync Server 2013에서 진단 보고서](lync-server-2013-diagnostic-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-113">From the Conference Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Detail) metric.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="76a8d-114">필터가</span><span class="sxs-lookup"><span data-stu-id="76a8d-114">Filters</span></span>

<span data-ttu-id="76a8d-115">없음.</span><span class="sxs-lookup"><span data-stu-id="76a8d-115">None.</span></span> <span data-ttu-id="76a8d-116">회의 세부 정보 보고서에서 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-116">You cannot filter on the Conference Detail Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="76a8d-117">매트릭스</span><span class="sxs-lookup"><span data-stu-id="76a8d-117">Metrics</span></span>

<span data-ttu-id="76a8d-118">다음 표에는 회의 세부 정보 보고서의 컨퍼런스 Information 섹션에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-118">The following table lists the information provided in the Conference Information section of the Conference Detail Report.</span></span>

### <a name="conference-information-metrics"></a><span data-ttu-id="76a8d-119">컨퍼런스 정보 메트릭</span><span class="sxs-lookup"><span data-stu-id="76a8d-119">Conference Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76a8d-120">이름</span><span class="sxs-lookup"><span data-stu-id="76a8d-120">Name</span></span></th>
<th><span data-ttu-id="76a8d-121">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="76a8d-121">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="76a8d-122">설명</span><span class="sxs-lookup"><span data-stu-id="76a8d-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76a8d-123"><strong>컨퍼런스 URI</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-123"><strong>Conference URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-124">회의에 할당 된 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-124">URI assigned to the conference.</span></span> <span data-ttu-id="76a8d-125">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-125">For example:</span></span></p>
<p><span data-ttu-id="76a8d-126">sip: kmyer@litwareinc gruu, 불투명 = 앱: 회의: 포커스: id: drg2y8v4</span><span class="sxs-lookup"><span data-stu-id="76a8d-126">sip:kmyer@litwareinc.com;gruu;opaque=app:conf:focus:id:drg2y8v4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76a8d-127"><strong>풀 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-127"><strong>Pool FQDN</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-128">세션에 포함 된 레지스트라 풀 또는 Edge 서버의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-128">Fully-qualified domain name of the Registrar pool or Edge Server involved in a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76a8d-129"><strong>시작 시간</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-129"><strong>Start time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-130">회의가 시작 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-130">Date and time that the conference started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76a8d-131"><strong>구성 도우미</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-131"><strong>Organizer</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-132">회의를 구성한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-132">SIP address of the user who organized the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76a8d-133"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-133"><strong>End time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-134">회의가 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-134">Date and time that the conference ended.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="76a8d-135">다음 표에는 회의 세부 정보 보고서의 회의 참여 섹션에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-135">The following table lists the information provided in the Conference Participation Section of the Conference Detail Report.</span></span>

### <a name="conference-participation-metrics"></a><span data-ttu-id="76a8d-136">회의 참여 메트릭</span><span class="sxs-lookup"><span data-stu-id="76a8d-136">Conference Participation Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76a8d-137">이름</span><span class="sxs-lookup"><span data-stu-id="76a8d-137">Name</span></span></th>
<th><span data-ttu-id="76a8d-138">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="76a8d-138">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="76a8d-139">설명</span><span class="sxs-lookup"><span data-stu-id="76a8d-139">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76a8d-140"><strong>사용자</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-140"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-141">회의에 참가 한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-141">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76a8d-142"><strong>역할인</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-142"><strong>Role</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-143">회의 참가자가 재생 한 역할 (예: 발표자)입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-143">Role (for example, Presenter) played by the conference participant.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76a8d-144"><strong>연결성</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-144"><strong>Connectivity</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-145">참가자의 네트워크 연결 (일반적으로 내부 또는 외부에서)</span><span class="sxs-lookup"><span data-stu-id="76a8d-145">Network connectivity (typically From Internal or From External) for the participant.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76a8d-146">참가 시간</span><span class="sxs-lookup"><span data-stu-id="76a8d-146">Join time</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-147">참가자가 회의에 참가 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-147">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76a8d-148"><strong>휴가 시간</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-148"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-149">참가자가 회의를 남겨진 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-149">Date and time that the participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76a8d-150"><strong>사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-150"><strong>User agent</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-151">참가자의 끝점에 사용 되는 소프트웨어의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-151">Identifier for the software used by the participant’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76a8d-152"><strong>진단 보고서</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-152"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-153">진단 및 문제 해결 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-153">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="76a8d-154">실패 한 세션에 대 한 SIP 응답 코드, 진단 헤더, 컨퍼런스 참가 시간, 진단 Id 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-154">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="76a8d-155">다음 표에는 회의 세부 정보 보고서의 컨퍼런스 형식을 섹션에서 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-155">The following table lists the information provided in the Conference Modalities section of the Conference Detail Report.</span></span>

### <a name="conference-modalities-metrics"></a><span data-ttu-id="76a8d-156">컨퍼런스 형식을 메트릭</span><span class="sxs-lookup"><span data-stu-id="76a8d-156">Conference Modalities Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="76a8d-157">이름</span><span class="sxs-lookup"><span data-stu-id="76a8d-157">Name</span></span></th>
<th><span data-ttu-id="76a8d-158">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="76a8d-158">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="76a8d-159">설명</span><span class="sxs-lookup"><span data-stu-id="76a8d-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="76a8d-160"><strong>사용자</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-160"><strong>User</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-161">회의에 참가 한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-161">SIP address of the user who participated in the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76a8d-162"><strong>참가 시간</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-162"><strong>Join time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-163">참가자가 회의에 참가 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-163">Date and time that the participant joined the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76a8d-164"><strong>휴가 시간</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-164"><strong>Leave time</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-165">참가자가 회의를 남겨진 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-165">Date and time that a participant left the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="76a8d-166"><strong>회의 서버 URI</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-166"><strong>Conferencing server URI</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-167">회의에 사용 되는 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-167">URI for the Conferencing server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="76a8d-168"><strong>진단 보고서</strong></span><span class="sxs-lookup"><span data-stu-id="76a8d-168"><strong>Diagnostic reports</strong></span></span></p></td>
<td></td>
<td><p><span data-ttu-id="76a8d-169">진단 및 문제 해결 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-169">Provides diagnostic and troubleshooting information.</span></span> <span data-ttu-id="76a8d-170">실패 한 세션에 대 한 SIP 응답 코드, 진단 헤더, 컨퍼런스 참가 시간, 진단 Id 등이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="76a8d-170">Including SIP response codes, diagnostic headers, conference join times, and diagnostic IDs for failed sessions.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

