---
title: 'Lync Server 2013: ErrorReport 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c2a0b85e905bc7e00488c667a242965e169872b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="4e4a7-102">Lync Server 2013의 ErrorReport 테이블</span><span class="sxs-lookup"><span data-stu-id="4e4a7-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e4a7-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4e4a7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4e4a7-104">ErrorReport 테이블에는 발생 한 오류에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="4e4a7-105">각 레코드는 발생한 한 가지 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-105">Each record is one error occurrence.</span></span> <span data-ttu-id="4e4a7-106">오류는 프런트 엔드 서버에서 실행하는 CDR 에이전트로 캡처되거나 클라이언트로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4e4a7-107">열</span><span class="sxs-lookup"><span data-stu-id="4e4a7-107">Column</span></span></th>
<th><span data-ttu-id="4e4a7-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4e4a7-108">Data Type</span></span></th>
<th><span data-ttu-id="4e4a7-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="4e4a7-109">Key/Index</span></span></th>
<th><span data-ttu-id="4e4a7-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4e4a7-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4e4a7-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4e4a7-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4e4a7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-114">오류가 발생 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e4a7-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-116">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-116">int</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-117">Primary</span><span class="sxs-lookup"><span data-stu-id="4e4a7-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-118">오류 보고서를 식별 하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-118">ID number to identify the error report.</span></span> <span data-ttu-id="4e4a7-119">오류 보고서를 고유 하 게 식별 하기 위해 <strong>Errortime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e4a7-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-121">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-121">int</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-122">외부</span><span class="sxs-lookup"><span data-stu-id="4e4a7-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-123">오류 유형의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-123">Unique ID of the error type.</span></span> <span data-ttu-id="4e4a7-124">자세한 내용은 <a href="lync-server-2013-errordef-table.md">Lync Server 2013의 Errordef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e4a7-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-126">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-126">int</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-127">외부</span><span class="sxs-lookup"><span data-stu-id="4e4a7-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-128">오류를 일으킨 요청을 시작한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="4e4a7-129">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e4a7-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-131">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-131">int</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-132">외부</span><span class="sxs-lookup"><span data-stu-id="4e4a7-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-133">오류를 일으킨 요청에 대 한 대상 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="4e4a7-134">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e4a7-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-136">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-136">int</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-137">외부</span><span class="sxs-lookup"><span data-stu-id="4e4a7-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-138">오류와 관련 된 전화 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-138">Conference URI related to the error.</span></span> <span data-ttu-id="4e4a7-139">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="4e4a7-140">일반적으로 ConferenceUriId가 null이 아닌 경우에는 FromUserId 또는 ToUserId가 null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e4a7-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-142">datetime</span><span class="sxs-lookup"><span data-stu-id="4e4a7-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-143">외부</span><span class="sxs-lookup"><span data-stu-id="4e4a7-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-144"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4e4a7-145">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e4a7-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-147">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-147">int</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-148">외부</span><span class="sxs-lookup"><span data-stu-id="4e4a7-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-149">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-149">ID number to identify the session.</span></span> <span data-ttu-id="4e4a7-150"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4e4a7-151">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e4a7-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-153">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-153">int</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-154">외부</span><span class="sxs-lookup"><span data-stu-id="4e4a7-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-155">오류 보고서를 보낸 서버 (보고서가 서버 구성 요소에서 전송 되 고 있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="4e4a7-156">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="4e4a7-157">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e4a7-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-159">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-159">int</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-160">외부</span><span class="sxs-lookup"><span data-stu-id="4e4a7-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-161">오류 보고서를 보낸 서버 (보고서가 서버 구성 요소에서 전송 되 고 있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="4e4a7-162">자세한 내용은 <a href="lync-server-2013-application-table.md">Lync Server 2013의 Application table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="4e4a7-163">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e4a7-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-165">이미지나</span><span class="sxs-lookup"><span data-stu-id="4e4a7-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4e4a7-166">오류에 대 한 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-166">More information about the error.</span></span></p>
<p><span data-ttu-id="4e4a7-167">이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e4a7-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-169">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-169">int</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-170">외부</span><span class="sxs-lookup"><span data-stu-id="4e4a7-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-171">오류 보고서를 전송 하는 끝점의 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="4e4a7-172">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e4a7-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-174">비트만</span><span class="sxs-lookup"><span data-stu-id="4e4a7-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e4a7-175">프런트 엔드 서버에서 실행 중이거나 클라이언트에서 보낸 CDR 에이전트에 의해 캡처된 오류 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e4a7-176"><strong>플래그가</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-177">smallint</span><span class="sxs-lookup"><span data-stu-id="4e4a7-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e4a7-178">나중에 사용하도록 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e4a7-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-180">고유</span><span class="sxs-lookup"><span data-stu-id="4e4a7-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e4a7-181">회의에 포함된 서로 다른 구성 요소의 참가 시간 정보와 연결된 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="4e4a7-182">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e4a7-183"><strong>SessionSetupTime 시간</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-184">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4e4a7-185">회의에 참가하는 특정 구성 요소에 필요한 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="4e4a7-186">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4e4a7-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-188">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-188">int</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-189">외부</span><span class="sxs-lookup"><span data-stu-id="4e4a7-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-190">오류 보고서를 생성 한 서버의 fqdn (정규화 된 도메인 이름)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4e4a7-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="4e4a7-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="4e4a7-192">int</span><span class="sxs-lookup"><span data-stu-id="4e4a7-192">int</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-193">외부</span><span class="sxs-lookup"><span data-stu-id="4e4a7-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4e4a7-194">오류 보고서가 생성 된 풀의 정규화 된 도메인 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4e4a7-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

