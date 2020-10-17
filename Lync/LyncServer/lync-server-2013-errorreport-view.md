---
title: 'Lync Server 2013: ErrorReport 보기'
description: 'Lync Server 2013: ErrorReport 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50fb0a362c71d8dfb5873157e7b1ed3d3eb680ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572044"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="cafcd-103">Lync Server 2013의 ErrorReport 보기</span><span class="sxs-lookup"><span data-stu-id="cafcd-103">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cafcd-104">_**마지막으로 수정 된 항목:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="cafcd-104">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="cafcd-105">ErrorReport 보기에는 보고된 오류에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-105">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="cafcd-106">각 레코드는 발생한 한 가지 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-106">Each record is one error occurrence.</span></span> <span data-ttu-id="cafcd-107">오류는 프런트 엔드 서버에서 실행하는 CDR 에이전트로 캡처되거나 클라이언트로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="cafcd-108">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cafcd-109">열</span><span class="sxs-lookup"><span data-stu-id="cafcd-109">Column</span></span></th>
<th><span data-ttu-id="cafcd-110">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="cafcd-110">Data Type</span></span></th>
<th><span data-ttu-id="cafcd-111">세부 정보</span><span class="sxs-lookup"><span data-stu-id="cafcd-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-113">datetime</span><span class="sxs-lookup"><span data-stu-id="cafcd-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="cafcd-p102">오류가 발생한 시간입니다. ErrorReportSeq와 함께 오류를 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-117">int</span><span class="sxs-lookup"><span data-stu-id="cafcd-117">int</span></span></p></td>
<td><p><span data-ttu-id="cafcd-p103">오류를 식별하기 위한 ID 번호입니다. ErrorTime과 함께 오류를 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-120"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-120"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-121">int</span><span class="sxs-lookup"><span data-stu-id="cafcd-121">int</span></span></p></td>
<td><p><span data-ttu-id="cafcd-122">오류 보고서의 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-122">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-123"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-123"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cafcd-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-125">오류가 유발된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-125">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-126"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-126"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cafcd-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-128">오류가 유발된 사용자의 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-128">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="cafcd-129">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cafcd-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-130"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-130"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cafcd-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-132">오류가 유발된 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-132">Tenant of the user who originated the error.</span></span> <span data-ttu-id="cafcd-133">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cafcd-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-134"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-134"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-135">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cafcd-135">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-136">오류 보고서의 대상인 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-136">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cafcd-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-p106">오류 보고서의 대상인 사용자의 URI 형식입니다. 자세한 내용은 UriTypes Table을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cafcd-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-141"><strong>ToTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-141"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cafcd-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-143">오류 보고서의 대상인 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-143">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="cafcd-144">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cafcd-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-145"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-145"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-146">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cafcd-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-147">오류 보고서의 대상인 회의의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-147">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-148"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-148"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-149">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cafcd-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-150">오류 보고서의 대상인 회의의 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-150">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="cafcd-151">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cafcd-151">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-152"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-152"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-153">datetime</span><span class="sxs-lookup"><span data-stu-id="cafcd-153">datetime</span></span></p></td>
<td><p><span data-ttu-id="cafcd-154">오류 보고서를 시작한 세션 요청의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-154">Time of session request that originated the error report.</span></span> <span data-ttu-id="cafcd-155">SessionIdSeq과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-155">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="cafcd-156">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cafcd-156">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-157"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-157"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-158">int</span><span class="sxs-lookup"><span data-stu-id="cafcd-158">int</span></span></p></td>
<td><p><span data-ttu-id="cafcd-159">오류 보고서를 시작한 세션 요청을 식별하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-159">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="cafcd-160">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-160">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="cafcd-161">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cafcd-161">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-162"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-162"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-163">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="cafcd-163">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-p111">오류가 유발된 세션의 SIP 대화 ID입니다. 형식:</span><span class="sxs-lookup"><span data-stu-id="cafcd-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="cafcd-166">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="cafcd-166">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="cafcd-167">이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="cafcd-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="cafcd-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-169"><strong>Microsoft.rtc.management.writableconfig.policy.clientversion.clientversion</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-169"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-170">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cafcd-170">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-171">오류를 유발한 사용자가 사용하는 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-171">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-172"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-172"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-173">int</span><span class="sxs-lookup"><span data-stu-id="cafcd-173">int</span></span></p></td>
<td><p><span data-ttu-id="cafcd-174">오류를 유발한 사용자가 사용한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-174">Client used by the user who originated the error.</span></span> <span data-ttu-id="cafcd-175">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cafcd-175">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-176"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-176"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-177">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="cafcd-177">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-178">오류를 유발한 사용자가 사용한 클라이언트 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-178">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-179"><strong>원본</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-179"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cafcd-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-181">오류를 유발한 서버 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</span><span class="sxs-lookup"><span data-stu-id="cafcd-181">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-182"><strong>응용 프로그램</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-182"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-183">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cafcd-183">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-184">오류를 유발한 응용 프로그램 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</span><span class="sxs-lookup"><span data-stu-id="cafcd-184">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-185"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-185"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-186">int</span><span class="sxs-lookup"><span data-stu-id="cafcd-186">int</span></span></p></td>
<td><p><span data-ttu-id="cafcd-187">오류 보고서를 포함하는 SIP 메시지 세션에 대한 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-187">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-188"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-188"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-189">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="cafcd-189">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-190">실패한 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-190">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-191"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-191"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-192">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="cafcd-192">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-193">실패한 요청의 콘텐츠 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-193">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-194"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-194"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cafcd-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-196">세션 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-196">Type of session.</span></span> <span data-ttu-id="cafcd-197">자세한 내용은 <a href="lync-server-2013-calltype-table.md">Lync Server 2013의 Calltype table</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cafcd-197">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-198"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-198"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-199">고유</span><span class="sxs-lookup"><span data-stu-id="cafcd-199">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="cafcd-200">회의에 포함된 서로 다른 구성 요소의 참가 시간 정보와 연결된 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-200">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-201"><strong>SetupTime 시간</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-201"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-202">int</span><span class="sxs-lookup"><span data-stu-id="cafcd-202">int</span></span></p></td>
<td><p><span data-ttu-id="cafcd-203">회의에 참가하는 특정 구성 요소에 필요한 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-203">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-204"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-204"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-205">비트만</span><span class="sxs-lookup"><span data-stu-id="cafcd-205">bit</span></span></p></td>
<td><p><span data-ttu-id="cafcd-206">프런트 엔드 서버에서 실행하는 CDR 에이전트에 의해 캡처되었는지, 아니면 클라이언트에 의해 전송되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-206">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-207"><strong>플래그가</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-207"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-208">smallint</span><span class="sxs-lookup"><span data-stu-id="cafcd-208">smallint</span></span></p></td>
<td><p><span data-ttu-id="cafcd-209">나중에 사용하도록 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-209">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-210"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-210"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-211">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="cafcd-211">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="cafcd-212">오류에 대한 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-212">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cafcd-213"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-213"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-214">varchar</span><span class="sxs-lookup"><span data-stu-id="cafcd-214">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="cafcd-215">보고서를 전송한 프런트 엔드 서버의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-215">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cafcd-216"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="cafcd-216"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="cafcd-217">varchar</span><span class="sxs-lookup"><span data-stu-id="cafcd-217">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="cafcd-218">보고서를 전송한 프런트 엔드 서버가 포함 된 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cafcd-218">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

