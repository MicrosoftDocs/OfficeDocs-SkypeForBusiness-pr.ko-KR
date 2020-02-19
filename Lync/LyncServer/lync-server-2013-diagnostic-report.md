---
title: 'Lync Server 2013: 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57d62e5938fd2d3b3d6966410a99e2f2e106325f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="d8207-102">Lync Server 2013의 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="d8207-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d8207-103">_**마지막으로 수정 된 항목:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="d8207-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="d8207-104">진단 보고서에서는 실패한 세션에 대한 진단 및 문제 해결 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="d8207-105">이 정보에는 세션이 실패할 때 보고된 진단 ID와 진단 헤더가 모두 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="d8207-106">진단 ID는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)이며, 진단 헤더는 진단 ID에 대해 함께 표시할 설명을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="d8207-107">또한 이 보고서에는 보고 구성 요소에서 인식된 유용한 문제 해결 정보가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="d8207-108">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-108">For example:</span></span>

  - <span data-ttu-id="d8207-p102">오류를 일으킨 PSTN 게이트웨이에서 제공되는 이유 코드. PSTN 네트워크에서 발신 전화에 실패하면 ISUP(ISDN User Part) 이유 코드가 자동으로 생성됩니다. 예를 들어 PSTN 게이트웨이에서 전화를 완료하는 데 사용 가능한 회로 또는 채널이 없음을 나타내는 이유 코드 34를 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-p102">The cause code provided by the PSTN gateway that generated the failure. When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated. For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="d8207-112">연결 오류를 해결하기 위한 피어 FQDN, 포트 및 Winsock 오류</span><span class="sxs-lookup"><span data-stu-id="d8207-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="d8207-p103">DNS 확인 오류를 해결하기 위한 조회 대상 이름. DNS 확인은 클라이언트가 네임 서버에 연결하여 지정된 장치 이름에 해당하는 IP 주소를 요청할 때마다 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-p103">Names being looked up for DNS resolution failures. DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="d8207-115">진단 보고서 액세스</span><span class="sxs-lookup"><span data-stu-id="d8207-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="d8207-116">[Lync Server 2013의 피어 투 피어 세션 정보 보고서](lync-server-2013-peer-to-peer-session-detail-report.md) 또는 전화 회의 정보 보고서에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 진단 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="d8207-117">필터</span><span class="sxs-lookup"><span data-stu-id="d8207-117">Filters</span></span>

<span data-ttu-id="d8207-p104">없음. 진단 보고서는 필터링할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-p104">None. You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="d8207-120">선별한</span><span class="sxs-lookup"><span data-stu-id="d8207-120">Metrics</span></span>

<span data-ttu-id="d8207-121">다음 표에서는 각 세션에 대해 진단 보고서에 제공된 정보를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="d8207-122">진단 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="d8207-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d8207-123">이름</span><span class="sxs-lookup"><span data-stu-id="d8207-123">Name</span></span></th>
<th><span data-ttu-id="d8207-124">이 항목에 대한 정렬 가능 여부</span><span class="sxs-lookup"><span data-stu-id="d8207-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="d8207-125">설명</span><span class="sxs-lookup"><span data-stu-id="d8207-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d8207-126"><strong>보고 시간</strong></span><span class="sxs-lookup"><span data-stu-id="d8207-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="d8207-127">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-127">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-128">보고서가 기록된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8207-129"><strong>응답 코드</strong></span><span class="sxs-lookup"><span data-stu-id="d8207-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="d8207-130">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-130">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-131">세션이 실패했을 때 전송된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8207-132"><strong>요청 유형</strong></span><span class="sxs-lookup"><span data-stu-id="d8207-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="d8207-133">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-133">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-p105">실패한 SIP 요청 유형입니다. 예: INVITE, BYE 또는 SERVICE</span><span class="sxs-lookup"><span data-stu-id="d8207-p105">SIP request type that failed. For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8207-136"><strong>원본</strong></span><span class="sxs-lookup"><span data-stu-id="d8207-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="d8207-137">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-137">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-138">오류 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8207-139"><strong>보낸 사용자 URI</strong></span><span class="sxs-lookup"><span data-stu-id="d8207-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="d8207-140">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-140">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-141">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8207-142"><strong>출처 사용자 에이전트</strong></span><span class="sxs-lookup"><span data-stu-id="d8207-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="d8207-143">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-143">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-144">세션을 시작한 사용자의 끝점에 사용된 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8207-145"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="d8207-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="d8207-146">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-146">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-147">오류 문제를 해결할 때 종종 유용한 정보를 제공하는 SIP 메시지에 연결된 고유 식별자(ms-diagnostics 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8207-148"><strong>콘텐츠 형식</strong></span><span class="sxs-lookup"><span data-stu-id="d8207-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="d8207-149">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-149">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-p106">실패한 미디어 콘텐츠 형식입니다. 예를 들어 공통 콘텐츠 형식은 Application/sdp입니다. SDP(Session Description Protocol)는 세션 알림, 세션 초대 및 멀티 미디어 세션 초대의 다른 형식에 사용된 표준 인터넷 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-p106">Type of media content that failed. For example, a common content type is Application/sdp. Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8207-153"><strong>응용 프로그램</strong></span><span class="sxs-lookup"><span data-stu-id="d8207-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="d8207-154">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-154">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-155">오류와 관련된 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8207-156"><strong>대상 사용자 URI</strong></span><span class="sxs-lookup"><span data-stu-id="d8207-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="d8207-157">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-157">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-158">세션에 초대된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d8207-159">전화 회의 참가 시간(밀리초)</span><span class="sxs-lookup"><span data-stu-id="d8207-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="d8207-160">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-160">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-161">사용자가 전화 회의에 참가하기까지 소요된 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d8207-162"><strong>진단 헤더</strong></span><span class="sxs-lookup"><span data-stu-id="d8207-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="d8207-163">아니요</span><span class="sxs-lookup"><span data-stu-id="d8207-163">No</span></span></p></td>
<td><p><span data-ttu-id="d8207-164">진단 ID 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d8207-165">진단 오류 목록은 [Ms-진단 헤더 페이지](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d8207-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](http://msdn.microsoft.com/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

