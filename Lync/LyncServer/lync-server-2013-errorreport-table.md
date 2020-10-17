---
title: 'Lync Server 2013: ErrorReport 테이블'
description: 'Lync Server 2013: ErrorReport 테이블'
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
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572014"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="4a52b-103">Lync Server 2013의 ErrorReport 테이블</span><span class="sxs-lookup"><span data-stu-id="4a52b-103">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a52b-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4a52b-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4a52b-105">ErrorReport 테이블에는 발생 한 오류에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-105">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="4a52b-106">각 레코드는 발생한 한 가지 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-106">Each record is one error occurrence.</span></span> <span data-ttu-id="4a52b-107">오류는 프런트 엔드 서버에서 실행하는 CDR 에이전트로 캡처되거나 클라이언트로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4a52b-108">열</span><span class="sxs-lookup"><span data-stu-id="4a52b-108">Column</span></span></th>
<th><span data-ttu-id="4a52b-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="4a52b-109">Data Type</span></span></th>
<th><span data-ttu-id="4a52b-110">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="4a52b-110">Key/Index</span></span></th>
<th><span data-ttu-id="4a52b-111">세부 정보</span><span class="sxs-lookup"><span data-stu-id="4a52b-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4a52b-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-113">datetime</span><span class="sxs-lookup"><span data-stu-id="4a52b-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="4a52b-114">Primary</span><span class="sxs-lookup"><span data-stu-id="4a52b-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="4a52b-115">오류가 발생 한 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-115">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a52b-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-117">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-117">int</span></span></p></td>
<td><p><span data-ttu-id="4a52b-118">Primary</span><span class="sxs-lookup"><span data-stu-id="4a52b-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="4a52b-119">오류 보고서를 식별 하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-119">ID number to identify the error report.</span></span> <span data-ttu-id="4a52b-120">오류 보고서를 고유 하 게 식별 하기 위해 <strong>Errortime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-120">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a52b-121"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-121"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-122">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-122">int</span></span></p></td>
<td><p><span data-ttu-id="4a52b-123">외부</span><span class="sxs-lookup"><span data-stu-id="4a52b-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a52b-124">오류 유형의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-124">Unique ID of the error type.</span></span> <span data-ttu-id="4a52b-125">자세한 내용은 <a href="lync-server-2013-errordef-table.md">Lync Server 2013의 Errordef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a52b-125">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a52b-126"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-126"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-127">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-127">int</span></span></p></td>
<td><p><span data-ttu-id="4a52b-128">외부</span><span class="sxs-lookup"><span data-stu-id="4a52b-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a52b-129">오류를 일으킨 요청을 시작한 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-129">User who originated the request that caused the error.</span></span> <span data-ttu-id="4a52b-130">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a52b-130">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a52b-131"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-131"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-132">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-132">int</span></span></p></td>
<td><p><span data-ttu-id="4a52b-133">외부</span><span class="sxs-lookup"><span data-stu-id="4a52b-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a52b-134">오류를 일으킨 요청에 대 한 대상 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-134">Destination user for the request that caused the error.</span></span> <span data-ttu-id="4a52b-135">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a52b-135">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a52b-136"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-136"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-137">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-137">int</span></span></p></td>
<td><p><span data-ttu-id="4a52b-138">외부</span><span class="sxs-lookup"><span data-stu-id="4a52b-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a52b-139">오류와 관련 된 전화 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-139">Conference URI related to the error.</span></span> <span data-ttu-id="4a52b-140">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a52b-140">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="4a52b-141">일반적으로 ConferenceUriId가 null이 아닌 경우에는 FromUserId 또는 ToUserId가 null이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-141">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a52b-142"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-142"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-143">datetime</span><span class="sxs-lookup"><span data-stu-id="4a52b-143">datetime</span></span></p></td>
<td><p><span data-ttu-id="4a52b-144">외부</span><span class="sxs-lookup"><span data-stu-id="4a52b-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a52b-145"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-145">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4a52b-146">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a52b-146">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a52b-147"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-147"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-148">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-148">int</span></span></p></td>
<td><p><span data-ttu-id="4a52b-149">외부</span><span class="sxs-lookup"><span data-stu-id="4a52b-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a52b-150">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-150">ID number to identify the session.</span></span> <span data-ttu-id="4a52b-151"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-151">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4a52b-152">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a52b-152">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a52b-153"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-153"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-154">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-154">int</span></span></p></td>
<td><p><span data-ttu-id="4a52b-155">외부</span><span class="sxs-lookup"><span data-stu-id="4a52b-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a52b-156">오류 보고서를 보낸 서버 (보고서가 서버 구성 요소에서 전송 되 고 있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-156">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="4a52b-157">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a52b-157">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="4a52b-158">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a52b-159"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-159"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-160">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-160">int</span></span></p></td>
<td><p><span data-ttu-id="4a52b-161">외부</span><span class="sxs-lookup"><span data-stu-id="4a52b-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a52b-162">오류 보고서를 보낸 서버 (보고서가 서버 구성 요소에서 전송 되 고 있는 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-162">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="4a52b-163">자세한 내용은 <a href="lync-server-2013-application-table.md">Lync Server 2013의 Application table</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="4a52b-163">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="4a52b-164">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-164">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a52b-165"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-165"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-166">이미지나</span><span class="sxs-lookup"><span data-stu-id="4a52b-166">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4a52b-167">오류에 대 한 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-167">More information about the error.</span></span></p>
<p><span data-ttu-id="4a52b-168">이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-168">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a52b-169"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-169"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-170">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-170">int</span></span></p></td>
<td><p><span data-ttu-id="4a52b-171">외부</span><span class="sxs-lookup"><span data-stu-id="4a52b-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a52b-172">오류 보고서를 전송 하는 끝점의 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-172">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="4a52b-173">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a52b-173">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a52b-174"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-174"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-175">비트만</span><span class="sxs-lookup"><span data-stu-id="4a52b-175">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4a52b-176">프런트 엔드 서버에서 실행 중이거나 클라이언트에서 보낸 CDR 에이전트에 의해 캡처된 오류 보고서입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-176">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a52b-177"><strong>플래그가</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-177"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-178">smallint</span><span class="sxs-lookup"><span data-stu-id="4a52b-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4a52b-179">나중에 사용하도록 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-179">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a52b-180"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-180"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-181">고유</span><span class="sxs-lookup"><span data-stu-id="4a52b-181">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4a52b-182">회의에 포함된 서로 다른 구성 요소의 참가 시간 정보와 연결된 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-182">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="4a52b-183">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-183">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a52b-184"><strong>SessionSetupTime 시간</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-184"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-185">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4a52b-186">회의에 참가하는 특정 구성 요소에 필요한 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-186">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="4a52b-187">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-187">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4a52b-188"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-188"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-189">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-189">int</span></span></p></td>
<td><p><span data-ttu-id="4a52b-190">외부</span><span class="sxs-lookup"><span data-stu-id="4a52b-190">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a52b-191">오류 보고서를 생성 한 서버의 fqdn (정규화 된 도메인 이름)을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-191">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4a52b-192"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="4a52b-192"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="4a52b-193">int</span><span class="sxs-lookup"><span data-stu-id="4a52b-193">int</span></span></p></td>
<td><p><span data-ttu-id="4a52b-194">외부</span><span class="sxs-lookup"><span data-stu-id="4a52b-194">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4a52b-195">오류 보고서가 생성 된 풀의 정규화 된 도메인 이름을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a52b-195">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

