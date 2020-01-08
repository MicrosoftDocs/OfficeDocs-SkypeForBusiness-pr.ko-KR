---
title: 'Lync Server 2013: 진단 보고서'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Diagnostic Report
ms:assetid: b389dbd9-f2e8-4184-93d0-2e504796ac16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615445(v=OCS.15)
ms:contentKeyID: 48185159
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b314bccb0c1df539598e17ffc8ca12b30287b8eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="diagnostic-report-in-lync-server-2013"></a><span data-ttu-id="25ccf-102">Lync Server 2013의 진단 보고서</span><span class="sxs-lookup"><span data-stu-id="25ccf-102">Diagnostic Report in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25ccf-103">_**마지막으로 수정한 주제:** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="25ccf-103">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="25ccf-104">진단 보고서는 실패 한 세션에 대 한 진단 및 문제 해결 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-104">The Diagnostic Report provides diagnostic and troubleshooting information for a failed session.</span></span> <span data-ttu-id="25ccf-105">이 정보에는 진단 ID와 세션에 실패 했을 때 보고 된 진단 헤더가 모두 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-105">This information includes both the Diagnostic ID and the Diagnostic header that were reported when the session failed.</span></span> <span data-ttu-id="25ccf-106">진단 ID는 SIP 메시지에 연결 되는 고유 식별자 (ms-진단 헤더 형식) 이며 진단 헤더는 진단 ID에 대해 함께 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-106">The Diagnostic ID is a unique identifier (in the form of an ms-diagnostics header) that gets attached to a SIP message, while the Diagnostic header provides an accompanying description for the Diagnostic ID.</span></span> <span data-ttu-id="25ccf-107">보고 구성 요소에서 인식 하는 중요 한 문제 해결 세부 정보를 보고서에 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-107">The report might also contain valuable troubleshooting details that are known by the reporting component.</span></span> <span data-ttu-id="25ccf-108">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-108">For example:</span></span>

  - <span data-ttu-id="25ccf-109">오류를 생성 한 PSTN 게이트웨이에서 제공 하는 원인 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-109">The cause code provided by the PSTN gateway that generated the failure.</span></span> <span data-ttu-id="25ccf-110">PSTN 네트워크에서 발신 통화가 실패 하면, ISDN 사용자 파트 (ISUP)가 자동으로 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-110">When an outgoing call fails on the PSTN network, an ISDN User Part (ISUP) cause code is automatically generated.</span></span> <span data-ttu-id="25ccf-111">예를 들어 PSTN 게이트웨이에서는 통화를 완료 하는 데 사용할 수 있는 회로 또는 채널이 없음을 나타내기 위해 코드 34를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-111">For example, a PSTN gateway might send cause code 34 to indicate that no circuit or channel was available for completing the call.</span></span>

  - <span data-ttu-id="25ccf-112">연결 오류에 대 한 피어 FQDN, 포트 및 Winsock 오류.</span><span class="sxs-lookup"><span data-stu-id="25ccf-112">Peer FQDN, port, and Winsock errors for connectivity failures.</span></span>

  - <span data-ttu-id="25ccf-113">DNS 확인 실패를 조회 하는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-113">Names being looked up for DNS resolution failures.</span></span> <span data-ttu-id="25ccf-114">DNS 확인은 클라이언트가 이름 서버에 접속 하 고 지정 된 디바이스 이름에 해당 하는 IP 주소를 요청 하는 경우에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-114">DNS resolution takes place any time a client contacts a name server and requests the IP address that corresponds to specified device name.</span></span>

<div>

## <a name="accessing-the-diagnostic-report"></a><span data-ttu-id="25ccf-115">진단 보고서에 액세스</span><span class="sxs-lookup"><span data-stu-id="25ccf-115">Accessing the Diagnostic Report</span></span>

<span data-ttu-id="25ccf-116">[Lync Server 2013의 피어 투 피어 세션 세부 정보 보고서](lync-server-2013-peer-to-peer-session-detail-report.md) 또는 회의 정보 보고서에서 진단 보고서 (세부 정보) 메트릭을 클릭 하 여 진단 보고서에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-116">The Diagnostic Report can be accessed by clicking the Diagnostic Report (Detail) metric on either the [Peer-to-Peer Session Detail Report in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md) or the Conference Detail Report.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="25ccf-117">필터가</span><span class="sxs-lookup"><span data-stu-id="25ccf-117">Filters</span></span>

<span data-ttu-id="25ccf-118">없음.</span><span class="sxs-lookup"><span data-stu-id="25ccf-118">None.</span></span> <span data-ttu-id="25ccf-119">진단 보고서는 필터링 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-119">You cannot filter the Diagnostic Report.</span></span>

</div>

<div>

## <a name="metrics"></a><span data-ttu-id="25ccf-120">매트릭스</span><span class="sxs-lookup"><span data-stu-id="25ccf-120">Metrics</span></span>

<span data-ttu-id="25ccf-121">다음 표에는 진단 보고서에서 각 세션에 대해 제공 하는 정보가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-121">The following table lists the information provided in the Diagnostic Report for each session.</span></span>

### <a name="diagnostic-report-metrics"></a><span data-ttu-id="25ccf-122">진단 보고서 메트릭</span><span class="sxs-lookup"><span data-stu-id="25ccf-122">Diagnostic Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="25ccf-123">이름</span><span class="sxs-lookup"><span data-stu-id="25ccf-123">Name</span></span></th>
<th><span data-ttu-id="25ccf-124">이 항목을 정렬할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="25ccf-124">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="25ccf-125">설명</span><span class="sxs-lookup"><span data-stu-id="25ccf-125">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="25ccf-126"><strong>보고서 시간</strong></span><span class="sxs-lookup"><span data-stu-id="25ccf-126"><strong>Report time</strong></span></span></p></td>
<td><p><span data-ttu-id="25ccf-127">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-127">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-128">보고서가 기록 된 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-128">Date and time that the report was recorded.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25ccf-129"><strong>응답 코드</strong></span><span class="sxs-lookup"><span data-stu-id="25ccf-129"><strong>Response code</strong></span></span></p></td>
<td><p><span data-ttu-id="25ccf-130">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-130">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-131">세션이 실패 했을 때 전송 된 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-131">SIP response code sent when the session failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25ccf-132"><strong>요청 형식</strong></span><span class="sxs-lookup"><span data-stu-id="25ccf-132"><strong>Request type</strong></span></span></p></td>
<td><p><span data-ttu-id="25ccf-133">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-133">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-134">실패 한 SIP 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-134">SIP request type that failed.</span></span> <span data-ttu-id="25ccf-135">예를 들어 초대, BYE, 서비스 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-135">For example, INVITE, BYE, or SERVICE.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25ccf-136"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="25ccf-136"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="25ccf-137">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-137">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-138">오류의 원본입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-138">Source of the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25ccf-139"><strong>사용자 URI에서</strong></span><span class="sxs-lookup"><span data-stu-id="25ccf-139"><strong>From user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="25ccf-140">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-140">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-141">세션을 시작한 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-141">SIP address of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25ccf-142"><strong>사용자 에이전트에서</strong></span><span class="sxs-lookup"><span data-stu-id="25ccf-142"><strong>From user agent</strong></span></span></p></td>
<td><p><span data-ttu-id="25ccf-143">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-143">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-144">세션을 시작한 사용자의 끝점에 사용 되는 소프트웨어입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-144">Software used by the endpoint of the user who initiated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25ccf-145"><strong>진단 ID</strong></span><span class="sxs-lookup"><span data-stu-id="25ccf-145"><strong>Diagnostic ID</strong></span></span></p></td>
<td><p><span data-ttu-id="25ccf-146">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-146">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-147">오류 문제 해결에 유용한 정보를 자주 제공 하는 SIP 메시지에 첨부 된 고유 식별자 (ms-진단 헤더 형식)입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-147">Unique identifier (in the form of an ms-diagnostics header) attached to a SIP message that often provides information useful in troubleshooting errors.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25ccf-148"><strong>콘텐츠 형식</strong></span><span class="sxs-lookup"><span data-stu-id="25ccf-148"><strong>Content type</strong></span></span></p></td>
<td><p><span data-ttu-id="25ccf-149">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-149">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-150">실패 한 미디어 콘텐츠의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-150">Type of media content that failed.</span></span> <span data-ttu-id="25ccf-151">예를 들어 공용 콘텐츠 형식은 Application/sdp입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-151">For example, a common content type is Application/sdp.</span></span> <span data-ttu-id="25ccf-152">SDP (세션 설명 프로토콜)는 세션 공지 사항, 세션 초대 및 다른 형식의 멀티미디어 세션 초기화에 사용 되는 표준 인터넷 프로토콜입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-152">Session Description Protocol (SDP) is a standard Internet protocol used for session announcements, session invitations, and other forms of multimedia session initiation.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25ccf-153"><strong>응용 프로그램</strong></span><span class="sxs-lookup"><span data-stu-id="25ccf-153"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="25ccf-154">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-154">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-155">오류와 관련 된 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="25ccf-155">Application involved in the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25ccf-156"><strong>사용자 URI로</strong></span><span class="sxs-lookup"><span data-stu-id="25ccf-156"><strong>To user URI</strong></span></span></p></td>
<td><p><span data-ttu-id="25ccf-157">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-157">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-158">세션에 초대 된 사용자의 SIP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-158">SIP address of the user who was invited to the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="25ccf-159">컨퍼런스 참가 시간 (ms)</span><span class="sxs-lookup"><span data-stu-id="25ccf-159">Conference join times (ms)</span></span></p></td>
<td><p><span data-ttu-id="25ccf-160">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-160">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-161">사용자가 회의에 참가 하는 데 걸린 시간 (밀리초 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-161">Amount of time (in milliseconds) it took for the user to join the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="25ccf-162"><strong>진단 헤더</strong></span><span class="sxs-lookup"><span data-stu-id="25ccf-162"><strong>Diagnostic header</strong></span></span></p></td>
<td><p><span data-ttu-id="25ccf-163">아니요</span><span class="sxs-lookup"><span data-stu-id="25ccf-163">No</span></span></p></td>
<td><p><span data-ttu-id="25ccf-164">진단 ID 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-164">Diagnostic ID description.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="25ccf-165">진단 오류 목록은 [Ms-진단 헤더 페이지](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25ccf-165">A list of diagnostic errors can be found on the [Ms-Diagnostics Header page](http://msdn.microsoft.com/en-us/library/gg132446\(v=office.12\).aspx).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

