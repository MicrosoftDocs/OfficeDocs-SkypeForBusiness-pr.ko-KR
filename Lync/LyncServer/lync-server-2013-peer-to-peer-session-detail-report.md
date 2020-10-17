---
title: 'Lync Server 2013: 피어 투 피어 세션 세부 정보 보고서'
description: 'Lync Server 2013: 피어 투 피어 세션 세부 정보 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Session Detail Report
ms:assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558659(v=OCS.15)
ms:contentKeyID: 48184416
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e712225fddabb646cc3b862f59601857a7df8eff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557284"
---
# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="e3b98-103">Lync Server 2013의 피어 투 피어 세션 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="e3b98-103">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3b98-104">_**마지막으로 수정 된 항목:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="e3b98-104">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="e3b98-105">피어 투 피어 세션 정보 보고서는 피어 투 피어 세션에 대 한 자세한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-105">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session.</span></span> <span data-ttu-id="e3b98-106">예를 들어 인스턴트 메시징 세션을 선택 하는 경우 보고서는 세션의 두 사용자가 보낸 메시지 수를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-106">For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="e3b98-107">피어 투 피어 세션 세부 정보 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="e3b98-107">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="e3b98-108">피어 투 피어 세션 세부 정보 보고서는 다음 보고서에서 액세스할 수 있습니다 (모두 모니터링 보고서 홈 페이지에서 액세스할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="e3b98-108">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="e3b98-109">IP 전화 인벤토리 보고서</span><span class="sxs-lookup"><span data-stu-id="e3b98-109">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="e3b98-110">사용자 작업 보고서</span><span class="sxs-lookup"><span data-stu-id="e3b98-110">User Activity Report</span></span>

  - <span data-ttu-id="e3b98-111">통화 허용 컨트롤 보고서</span><span class="sxs-lookup"><span data-stu-id="e3b98-111">Call Admission Control Report</span></span>

  - <span data-ttu-id="e3b98-112">오류 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="e3b98-112">Failure List Report</span></span>

<span data-ttu-id="e3b98-113">피어 투 피어 세션 세부 정보 보고서 내에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 [Lync Server 2013의 진단 보고서](lync-server-2013-diagnostic-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-113">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="e3b98-114">다음 두 메트릭 중 하나를 클릭 하 여 상위 오류 보고서에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-114">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="e3b98-115">응답</span><span class="sxs-lookup"><span data-stu-id="e3b98-115">Response</span></span>

  - <span data-ttu-id="e3b98-116">진단 ID</span><span class="sxs-lookup"><span data-stu-id="e3b98-116">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="e3b98-117">피어 투 피어 세션 세부 정보 보고서를 가장 효율적으로 활용</span><span class="sxs-lookup"><span data-stu-id="e3b98-117">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="e3b98-118">피어 투 피어 세션 정보 보고서에는 많은 수의 메트릭이 포함 되어 있는데,이는 대부분 시스템 관리자에 게 익숙한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-118">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators.</span></span> <span data-ttu-id="e3b98-119">그러나 종종 메트릭 레이블 위에 마우스를 놓으면 해당 메트릭에 대 한 간략 한 설명을 제공 하는 도구 설명을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-119">Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="e3b98-120">지정 된 보고서에 표시 되는 실제 메트릭은 선택한 피어 투 피어 세션 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-120">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected.</span></span> <span data-ttu-id="e3b98-121">오디오/비디오 세션에서는 인스턴트 메시징 세션 보다 다양 한 메트릭 집합을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-121">An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="e3b98-122">또한 응답 코드 및 진단 ID 메트릭 위로 마우스를 가져가면 해당 값에 대 한 설명을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-122">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="e3b98-123">필터</span><span class="sxs-lookup"><span data-stu-id="e3b98-123">Filters</span></span>

<span data-ttu-id="e3b98-124">없음</span><span class="sxs-lookup"><span data-stu-id="e3b98-124">None.</span></span> <span data-ttu-id="e3b98-125">피어 투 피어 세션 정보 보고서를 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-125">You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="e3b98-126">세션 정보 메트릭</span><span class="sxs-lookup"><span data-stu-id="e3b98-126">Session Information Metrics</span></span>

<span data-ttu-id="e3b98-127">다음 표에서는 각 세션에 대해 피어 투 피어 세션 정보 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-127">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="e3b98-128">세션 정보 메트릭</span><span class="sxs-lookup"><span data-stu-id="e3b98-128">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3b98-129">이름</span><span class="sxs-lookup"><span data-stu-id="e3b98-129">Name</span></span></th>
<th><span data-ttu-id="e3b98-130">설명</span><span class="sxs-lookup"><span data-stu-id="e3b98-130">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-131"><strong>풀 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-131"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-132">세션에 포함 된 등록자 풀 또는에 지 서버의 FQDN (전체 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-132">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-133"><strong>초대 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-133"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-134">세션 초대가 원래 전송 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-134">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-135"><strong>응답 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-135"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-136">초대 수락이 수신 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-136">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-137"><strong>시작 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-137"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-138">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-138">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-139"><strong>출처 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-139"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-140">세션을 시작한 사용자의 끝점에 사용된 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-140">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-141"><strong>사용자 내부 출처</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-141"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-142">세션을 시작한 사용자가 내부 네트워크에 로그온 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-142">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-143"><strong>일반 전화기와 통합 된 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-143"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-144">세션을 시작한 사용자가 사용 하는 끝점이 자신의 데스크톱 전화와 통합 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-144">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-145"><strong>세션 우선 순위</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-145"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-146">세션에 할당 된 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-146">Priority assigned to the session.</span></span> <span data-ttu-id="e3b98-147">유효한 우선 순위는 다음과 같습니다. 비 긴급; 보통인 기울여야 및 긴급</span><span class="sxs-lookup"><span data-stu-id="e3b98-147">Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-148"><strong>응답 코드</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-148"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-149">세션이 실패했을 때 전송된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-149">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-150"><strong>프런트 엔드</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-150"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-151">전화 회의에 사용 된 프런트 엔드 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-151">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-152"><strong>캡처 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-152"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-153">세션 정보가 기록 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-153">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-154"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-154"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-155">세션이 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-155">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-156"><strong>대상 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-156"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-157">세션에 초대된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-157">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-158"><strong>사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-158"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-159">세션에 초대 된 사용자의 끝점에 사용 된 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-159">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-160"><strong>사용자 내부</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-160"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-161">세션에 초대 된 사용자가 내부 네트워크에 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-161">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-162"><strong>일반 전화기와 통합 된 사용자</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-162"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-163">세션에 초대 된 사용자가 사용 하는 끝점이 자신의 데스크톱 전화와 통합 되어 있는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-163">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-164"><strong>재시도 되는 세션</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-164"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-165">세션이 이전에 실패 한 세션에 대 한 다시 시도 인지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-165">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-166"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-166"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-167">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-167">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="e3b98-168">ID 번호 위에 마우스를 놓으면 해당 ID에 대 한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-168">Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="e3b98-169">형식에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e3b98-169">Metrics for Modalities</span></span>

<span data-ttu-id="e3b98-170">다음 표에서는 각 세션 형식에 대해 피어 투 피어 세션 정보 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-170">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="e3b98-171">형식에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e3b98-171">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3b98-172">이름</span><span class="sxs-lookup"><span data-stu-id="e3b98-172">Name</span></span></th>
<th><span data-ttu-id="e3b98-173">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="e3b98-173">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e3b98-174">설명</span><span class="sxs-lookup"><span data-stu-id="e3b98-174">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-175"><strong>형식</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-175"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-176">아니요</span><span class="sxs-lookup"><span data-stu-id="e3b98-176">No</span></span></p></td>
<td><p><span data-ttu-id="e3b98-177">세션에서 사용 되는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-177">Modalities used in the session.</span></span> <span data-ttu-id="e3b98-178">IM (인스턴트 메시징) 또는 파일 전송 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-178">For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-179"><strong>사용자 메시지</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-179"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-180">아니요</span><span class="sxs-lookup"><span data-stu-id="e3b98-180">No</span></span></p></td>
<td><p><span data-ttu-id="e3b98-181">세션을 시작한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-181">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-182"><strong>사용자 메시지</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-182"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-183">아니요</span><span class="sxs-lookup"><span data-stu-id="e3b98-183">No</span></span></p></td>
<td><p><span data-ttu-id="e3b98-184">세션에 참가 하도록 초대 된 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-184">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="e3b98-185">진단 보고서에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e3b98-185">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="e3b98-186">다음 표에서는 각 진단 보고서에 대해 피어 투 피어 세션 정보 보고서에 제공 되는 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-186">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="e3b98-187">진단 보고서에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="e3b98-187">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3b98-188">이름</span><span class="sxs-lookup"><span data-stu-id="e3b98-188">Name</span></span></th>
<th><span data-ttu-id="e3b98-189">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="e3b98-189">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="e3b98-190">설명</span><span class="sxs-lookup"><span data-stu-id="e3b98-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-191"><strong>자세한 정보</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-191"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-192">아니요</span><span class="sxs-lookup"><span data-stu-id="e3b98-192">No</span></span></p></td>
<td><p><span data-ttu-id="e3b98-193">이 항목을 클릭 하면 보고서에 세션에 대 한 진단 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-193">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-194"><strong>보고 시간</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-194"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-195">아니요</span><span class="sxs-lookup"><span data-stu-id="e3b98-195">No</span></span></p></td>
<td><p><span data-ttu-id="e3b98-196">보고서가 기록된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-196">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-197"><strong>요청이</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-197"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-198">아니요</span><span class="sxs-lookup"><span data-stu-id="e3b98-198">No</span></span></p></td>
<td><p><span data-ttu-id="e3b98-199">SIP 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-199">SIP request type.</span></span> <span data-ttu-id="e3b98-200">예: INVITE 또는 BYE</span><span class="sxs-lookup"><span data-stu-id="e3b98-200">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-201"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-201"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-202">아니요</span><span class="sxs-lookup"><span data-stu-id="e3b98-202">No</span></span></p></td>
<td><p><span data-ttu-id="e3b98-203">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-203">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3b98-204"><strong>콘텐츠 형식</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-204"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-205">아니요</span><span class="sxs-lookup"><span data-stu-id="e3b98-205">No</span></span></p></td>
<td><p><span data-ttu-id="e3b98-206">전화 회의에서 사용 되는 미디어 콘텐츠 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-206">Type of media content used in the conference.</span></span> <span data-ttu-id="e3b98-207">예를 들어 공통 콘텐츠 형식은 Application/sdp입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-207">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="e3b98-208">SDP(Session Description Protocol)는 세션 알림, 세션 초대 및 멀티 미디어 세션 초대의 다른 형식에 사용된 표준 인터넷 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-208">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3b98-209"><strong>보고 한 사람</strong></span><span class="sxs-lookup"><span data-stu-id="e3b98-209"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="e3b98-210">아니요</span><span class="sxs-lookup"><span data-stu-id="e3b98-210">No</span></span></p></td>
<td><p><span data-ttu-id="e3b98-211">문제를 보고 한 컴퓨터 (즉, 클라이언트 또는 서버)입니다.</span><span class="sxs-lookup"><span data-stu-id="e3b98-211">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

