---
title: 'Lync Server 2013: 피어 투 피어 세션 세부 정보 보고서'
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
ms.openlocfilehash: bff140db52a98e0b442ca65bbbb8b148282c5755
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-session-detail-report-in-lync-server-2013"></a><span data-ttu-id="09eb1-102">Lync Server 2013의 피어 투 피어 세션 세부 정보 보고서</span><span class="sxs-lookup"><span data-stu-id="09eb1-102">Peer-to-Peer Session Detail Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09eb1-103">_**마지막으로 수정한 주제:** 2012-06-06_</span><span class="sxs-lookup"><span data-stu-id="09eb1-103">_**Topic Last Modified:** 2012-06-06_</span></span>

<span data-ttu-id="09eb1-104">피어 투 피어 세션 정보 보고서는 피어 투 피어 세션에 대 한 자세한 정보를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-104">The Peer-to-Peer Session Detail Report returns detailed information about a peer-to-peer session.</span></span> <span data-ttu-id="09eb1-105">예를 들어 메신저 대화를 선택 하면 보고서에서 세션의 두 사용자 각각에 게 보낸 메시지 수를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-105">For example, if you select an instant messaging session, the report will tell you the number of messages sent by each of the two users in the session.</span></span>

<div>

## <a name="accessing-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="09eb1-106">피어 투 피어 세션 세부 정보 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="09eb1-106">Accessing the Peer-to-Peer Session Detail Report</span></span>

<span data-ttu-id="09eb1-107">피어 투 피어 세션 세부 정보 보고서는 다음 보고서 중 하나에서 액세스할 수 있습니다 (모두 모니터링 보고서 홈 페이지에서 액세스할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="09eb1-107">The Peer-to-Peer Session Detail Report can be accessed from any of the following reports (all of which can be accessed from the Monitoring Reports home page):</span></span>

  - <span data-ttu-id="09eb1-108">IP 전화 인벤토리 보고서</span><span class="sxs-lookup"><span data-stu-id="09eb1-108">IP Phone Inventory Report</span></span>

  - <span data-ttu-id="09eb1-109">사용자 활동 보고서</span><span class="sxs-lookup"><span data-stu-id="09eb1-109">User Activity Report</span></span>

  - <span data-ttu-id="09eb1-110">통화 허용 제어 보고서</span><span class="sxs-lookup"><span data-stu-id="09eb1-110">Call Admission Control Report</span></span>

  - <span data-ttu-id="09eb1-111">오류 목록 보고서</span><span class="sxs-lookup"><span data-stu-id="09eb1-111">Failure List Report</span></span>

<span data-ttu-id="09eb1-112">피어 투 피어 세션 세부 정보 보고서 내에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 [Lync Server 2013에서 진단 보고서](lync-server-2013-diagnostic-report.md) 에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-112">From within the Peer-to-Peer Session Detail Report you can access the [Diagnostic Report in Lync Server 2013](lync-server-2013-diagnostic-report.md) by clicking the Diagnostic Report (Details) metric.</span></span> <span data-ttu-id="09eb1-113">다음 두 가지 메트릭 중 하나를 클릭 하 여 상위 오류 보고서에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-113">You can also access the Top Failures Report by clicking either of these two metrics:</span></span>

  - <span data-ttu-id="09eb1-114">응답</span><span class="sxs-lookup"><span data-stu-id="09eb1-114">Response</span></span>

  - <span data-ttu-id="09eb1-115">진단 ID</span><span class="sxs-lookup"><span data-stu-id="09eb1-115">Diagnostic ID</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a><span data-ttu-id="09eb1-116">피어 투 피어 세션 세부 정보 보고서를 최대한 활용 하기</span><span class="sxs-lookup"><span data-stu-id="09eb1-116">Making the Best Use of the Peer-to-Peer session Detail Report</span></span>

<span data-ttu-id="09eb1-117">피어 투 피어 세션 세부 정보 보고서에는 다 수의 메트릭이 포함 되어 있으며,이 중 상당수는 시스템 관리자에 게 익숙하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-117">The Peer-to-Peer Session Detail Report includes a large number of metrics, many of which might not be familiar to system administrators.</span></span> <span data-ttu-id="09eb1-118">그러나 종종 미터법 레이블을 마우스로 눌러 해당 메트릭의 간략 한 설명을 제공 하는 도구 설명을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-118">Often-times, however, you can view a tooltip that offers a brief description of that metric simply by holding your mouse over the metric label.</span></span>

<span data-ttu-id="09eb1-119">지정 된 보고서에 표시 되는 실제 메트릭은 선택한 피어 투 피어 세션의 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-119">Note that the actual metrics shown on a given report will depend on the type of peer-to-peer session you selected.</span></span> <span data-ttu-id="09eb1-120">오디오/비디오 세션은 인스턴트 메시지 세션 보다 다른 메트릭 집합을 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-120">An audio/video session will report a different set of metrics than an instant messaging session.</span></span>

<span data-ttu-id="09eb1-121">이러한 값에 대 한 설명을 얻으려면 응답 코드 및 진단 ID 메트릭스 위에 마우스를 놓고 있어야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-121">You can also hold your mouse over the Response code and Diagnostic ID metrics in order to obtain a description of those values:</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="09eb1-122">필터가</span><span class="sxs-lookup"><span data-stu-id="09eb1-122">Filters</span></span>

<span data-ttu-id="09eb1-123">없음.</span><span class="sxs-lookup"><span data-stu-id="09eb1-123">None.</span></span> <span data-ttu-id="09eb1-124">피어 투 피어 세션 세부 정보 보고서를 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-124">You cannot filter the Peer-to-Peer Session Detail Report.</span></span>

</div>

<div>

## <a name="session-information-metrics"></a><span data-ttu-id="09eb1-125">세션 정보 메트릭</span><span class="sxs-lookup"><span data-stu-id="09eb1-125">Session Information Metrics</span></span>

<span data-ttu-id="09eb1-126">다음 표에는 각 세션에 대 한 피어 투 피어 세션 세부 정보 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-126">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session.</span></span>

### <a name="session-information-metrics"></a><span data-ttu-id="09eb1-127">세션 정보 메트릭</span><span class="sxs-lookup"><span data-stu-id="09eb1-127">Session Information Metrics</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09eb1-128">이름</span><span class="sxs-lookup"><span data-stu-id="09eb1-128">Name</span></span></th>
<th><span data-ttu-id="09eb1-129">설명</span><span class="sxs-lookup"><span data-stu-id="09eb1-129">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-130"><strong>풀 FQDN</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-130"><strong>Pool FQDN</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-131">세션과 관련 된 등록자 풀 또는 Edge 서버의 FQDN (정규화 된 도메인 이름)입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-131">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-132"><strong>초대 시간</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-132"><strong>Invite time</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-133">세션 초대를 원래 보낸 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-133">Date and time the session invitation was originally sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-134"><strong>응답 시간</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-134"><strong>Response time</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-135">초대 수락을 받은 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-135">Date and time that the invitation acceptance was received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-136"><strong>사용자의</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-136"><strong>From user</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-137">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-137">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-138"><strong>사용자 에이전트에서</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-138"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-139">세션을 시작한 사용자의 끝점에 사용 되는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-139">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-140"><strong>사용자의 내부용입니다.</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-140"><strong>Is From user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-141">세션을 시작한 사용자가 내부 네트워크에 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-141">Indicates whether the user who initiated the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-142"><strong>일반 전화기와 통합 된 사용자 인 경우</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-142"><strong>Is From user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-143">세션을 시작한 사용자가 사용 하는 끝점이 해당 데스크톱 전화기와 통합 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-143">Indicates whether the endpoint used by the user who initiated the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-144"><strong>세션 우선 순위</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-144"><strong>Session Priority</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-145">세션에 할당 된 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-145">Priority assigned to the session.</span></span> <span data-ttu-id="09eb1-146">유효한 우선 순위: 알 수 없음 비 긴급 크기로 받기 및 비상.</span><span class="sxs-lookup"><span data-stu-id="09eb1-146">Valid priorities are: Unknown; Non-Urgent; Normal; Urgent; and Emergency.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-147"><strong>응답 코드</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-147"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-148">세션이 실패 했을 때 전송 된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-148">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-149"><strong>프론트 엔드</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-149"><strong>Front end</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-150">회의에 사용 되는 프런트 엔드 서버의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-150">Name of the Front End Server used in the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-151"><strong>캡처 시간</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-151"><strong>Capture time</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-152">세션 정보가 기록 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-152">Date and time that the session information was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-153"><strong>종료 시간</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-153"><strong>End time</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-154">세션이 종료 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-154">Date and time the session ended.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-155"><strong>사용자에 게</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-155"><strong>To user</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-156">세션에 초대 된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-156">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-157"><strong>사용자 에이전트에</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-157"><strong>To user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-158">세션에 초대 된 사용자의 끝점에서 사용 하는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-158">Software used by the endpoint of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-159"><strong>사용자 내부용</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-159"><strong>Is To user internal</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-160">세션에 초대 된 사용자가 내부 네트워크에 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-160">Indicates whether the user who was invited to the session was logged on to the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-161"><strong>일반 전화기와 사용자 통합</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-161"><strong>Is To user integrated with desk phone</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-162">세션에 초대 된 사용자가 사용 하는 끝점이 해당 데스크톱 전화기와 통합 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-162">Indicates whether the endpoint used by the user who was invited to the session is integrated with his or her desktop phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-163"><strong>다시 시도 세션</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-163"><strong>Is retried session</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-164">세션이 이전에 실패 한 세션을 다시 시도 하려고 하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-164">Indicates whether the session is an attempt to retry a session that previously failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-165"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-165"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-166">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-166">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span> <span data-ttu-id="09eb1-167">ID 번호 위에 마우스를 놓으면 해당 ID에 대 한 추가 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-167">Hold the mouse over the ID number to view additional information about that ID.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-modalities"></a><span data-ttu-id="09eb1-168">형식을에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="09eb1-168">Metrics for Modalities</span></span>

<span data-ttu-id="09eb1-169">다음 표에는 각 세션에 대 한 피어 투 피어 세션 세부 정보 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-169">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each session modality.</span></span>

### <a name="metrics-for-modalities"></a><span data-ttu-id="09eb1-170">형식을에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="09eb1-170">Metrics for Modalities</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09eb1-171">이름</span><span class="sxs-lookup"><span data-stu-id="09eb1-171">Name</span></span></th>
<th><span data-ttu-id="09eb1-172">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="09eb1-172">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="09eb1-173">설명</span><span class="sxs-lookup"><span data-stu-id="09eb1-173">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-174"><strong>형식을</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-174"><strong>Modalities</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-175">아니요</span><span class="sxs-lookup"><span data-stu-id="09eb1-175">No</span></span></p></td>
<td><p><span data-ttu-id="09eb1-176">세션에 사용 되는 형식을.</span><span class="sxs-lookup"><span data-stu-id="09eb1-176">Modalities used in the session.</span></span> <span data-ttu-id="09eb1-177">예를 들어 인스턴트 메시지 (IM) 또는 파일 전송</span><span class="sxs-lookup"><span data-stu-id="09eb1-177">For example, instant messaging (IM) or file transfer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-178"><strong>사용자 메시지</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-178"><strong>From user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-179">아니요</span><span class="sxs-lookup"><span data-stu-id="09eb1-179">No</span></span></p></td>
<td><p><span data-ttu-id="09eb1-180">세션을 시작한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-180">Number of messages sent by the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-181"><strong>사용자 메시지</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-181"><strong>To user messages</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-182">아니요</span><span class="sxs-lookup"><span data-stu-id="09eb1-182">No</span></span></p></td>
<td><p><span data-ttu-id="09eb1-183">세션에 참가 하도록 초대 된 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-183">Number of messages sent by the user who was invited to join the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="09eb1-184">진단 보고서에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="09eb1-184">Metrics for Diagnostic Reports</span></span>

<span data-ttu-id="09eb1-185">다음 표에는 각 진단 보고서에 대 한 피어 투 피어 세션 세부 정보 보고서에 제공 되는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-185">The following table lists the information provided in the Peer-to-Peer Session Detail Report for each diagnostic report.</span></span>

### <a name="metrics-for-diagnostic-reports"></a><span data-ttu-id="09eb1-186">진단 보고서에 대 한 메트릭</span><span class="sxs-lookup"><span data-stu-id="09eb1-186">Metrics for Diagnostic Reports</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="09eb1-187">이름</span><span class="sxs-lookup"><span data-stu-id="09eb1-187">Name</span></span></th>
<th><span data-ttu-id="09eb1-188">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="09eb1-188">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="09eb1-189">설명</span><span class="sxs-lookup"><span data-stu-id="09eb1-189">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-190"><strong>도</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-190"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-191">아니요</span><span class="sxs-lookup"><span data-stu-id="09eb1-191">No</span></span></p></td>
<td><p><span data-ttu-id="09eb1-192">이 항목을 클릭 하면 보고서에는 세션에 대 한 진단 보고서가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-192">When you click this item, the report shows the Diagnostic Report for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-193"><strong>보고서 시간</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-193"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-194">아니요</span><span class="sxs-lookup"><span data-stu-id="09eb1-194">No</span></span></p></td>
<td><p><span data-ttu-id="09eb1-195">보고서가 기록 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-195">Date and time the report was recorded.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-196"><strong>요청당</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-196"><strong>Request</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-197">아니요</span><span class="sxs-lookup"><span data-stu-id="09eb1-197">No</span></span></p></td>
<td><p><span data-ttu-id="09eb1-198">SIP 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-198">SIP request type.</span></span> <span data-ttu-id="09eb1-199">예를 들어 초대 또는 BYE.</span><span class="sxs-lookup"><span data-stu-id="09eb1-199">For example, INVITE or BYE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-200"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-200"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-201">아니요</span><span class="sxs-lookup"><span data-stu-id="09eb1-201">No</span></span></p></td>
<td><p><span data-ttu-id="09eb1-202">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-202">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="09eb1-203"><strong>콘텐츠 형식</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-203"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-204">아니요</span><span class="sxs-lookup"><span data-stu-id="09eb1-204">No</span></span></p></td>
<td><p><span data-ttu-id="09eb1-205">회의에 사용 되는 미디어 콘텐츠의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-205">Type of media content used in the conference.</span></span> <span data-ttu-id="09eb1-206">예를 들어 공용 콘텐츠 형식은 Application/sdp입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-206">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="09eb1-207">SDP (세션 설명 프로토콜)는 세션 공지 사항, 세션 초대 및 다른 형식의 멀티미디어 세션 초기화에 사용 되는 표준 인터넷 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-207">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="09eb1-208"><strong>보고 한 사람</strong></span><span class="sxs-lookup"><span data-stu-id="09eb1-208"><strong>Reported by</strong></span></span></p></td>
<td><p><span data-ttu-id="09eb1-209">아니요</span><span class="sxs-lookup"><span data-stu-id="09eb1-209">No</span></span></p></td>
<td><p><span data-ttu-id="09eb1-210">컴퓨터 (즉, 클라이언트 또는 서버)에서 문제를 보고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="09eb1-210">Computer (that is, client or server) that reported the problem.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

