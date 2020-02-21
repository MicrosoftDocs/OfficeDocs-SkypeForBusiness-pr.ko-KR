---
title: 'Lync Server 2013: ErrorReport 보기'
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
ms.openlocfilehash: e635cd289f0224a7f8d4106cecc3d8b047e9bb92
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207535"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="03fe5-102">Lync Server 2013의 ErrorReport 보기</span><span class="sxs-lookup"><span data-stu-id="03fe5-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03fe5-103">_**마지막으로 수정 된 항목:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="03fe5-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="03fe5-104">ErrorReport 보기에는 보고된 오류에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="03fe5-105">각 레코드는 발생한 한 가지 오류를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-105">Each record is one error occurrence.</span></span> <span data-ttu-id="03fe5-106">오류는 프런트 엔드 서버에서 실행하는 CDR 에이전트로 캡처되거나 클라이언트로 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="03fe5-107">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="03fe5-108">열</span><span class="sxs-lookup"><span data-stu-id="03fe5-108">Column</span></span></th>
<th><span data-ttu-id="03fe5-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="03fe5-109">Data Type</span></span></th>
<th><span data-ttu-id="03fe5-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="03fe5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="03fe5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="03fe5-p102">오류가 발생한 시간입니다. ErrorReportSeq와 함께 오류를 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-116">int</span><span class="sxs-lookup"><span data-stu-id="03fe5-116">int</span></span></p></td>
<td><p><span data-ttu-id="03fe5-p103">오류를 식별하기 위한 ID 번호입니다. ErrorTime과 함께 오류를 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-120">int</span><span class="sxs-lookup"><span data-stu-id="03fe5-120">int</span></span></p></td>
<td><p><span data-ttu-id="03fe5-121">오류 보고서의 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="03fe5-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-124">오류가 유발된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="03fe5-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-127">오류가 유발된 사용자의 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="03fe5-128">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="03fe5-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="03fe5-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-131">오류가 유발된 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="03fe5-132">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03fe5-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="03fe5-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-135">오류 보고서의 대상인 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="03fe5-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-p106">오류 보고서의 대상인 사용자의 URI 형식입니다. 자세한 내용은 UriTypes Table을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="03fe5-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-140"><strong>ToTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="03fe5-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-142">오류 보고서의 대상인 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="03fe5-143">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03fe5-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="03fe5-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-146">오류 보고서의 대상인 회의의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="03fe5-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-149">오류 보고서의 대상인 회의의 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="03fe5-150">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="03fe5-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-152">datetime</span><span class="sxs-lookup"><span data-stu-id="03fe5-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="03fe5-153">오류 보고서를 시작한 세션 요청의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="03fe5-154">SessionIdSeq과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="03fe5-155">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="03fe5-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-157">int</span><span class="sxs-lookup"><span data-stu-id="03fe5-157">int</span></span></p></td>
<td><p><span data-ttu-id="03fe5-158">오류 보고서를 시작한 세션 요청을 식별하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="03fe5-159">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="03fe5-160">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="03fe5-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="03fe5-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-p111">오류가 유발된 세션의 SIP 대화 ID입니다. 형식:</span><span class="sxs-lookup"><span data-stu-id="03fe5-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="03fe5-165">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="03fe5-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="03fe5-166">이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="03fe5-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="03fe5-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-168"><strong>Microsoft.rtc.management.writableconfig.policy.clientversion.clientversion</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="03fe5-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-170">오류를 유발한 사용자가 사용하는 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-172">int</span><span class="sxs-lookup"><span data-stu-id="03fe5-172">int</span></span></p></td>
<td><p><span data-ttu-id="03fe5-173">오류를 유발한 사용자가 사용한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="03fe5-174">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03fe5-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="03fe5-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-177">오류를 유발한 사용자가 사용한 클라이언트 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-178"><strong>원본</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="03fe5-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-180">오류를 유발한 서버 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</span><span class="sxs-lookup"><span data-stu-id="03fe5-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-181"><strong>응용 프로그램</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-182">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="03fe5-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-183">오류를 유발한 응용 프로그램 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).</span><span class="sxs-lookup"><span data-stu-id="03fe5-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-185">int</span><span class="sxs-lookup"><span data-stu-id="03fe5-185">int</span></span></p></td>
<td><p><span data-ttu-id="03fe5-186">오류 보고서를 포함하는 SIP 메시지 세션에 대한 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="03fe5-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-189">실패한 요청 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="03fe5-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-192">실패한 요청의 콘텐츠 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="03fe5-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-195">세션 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-195">Type of session.</span></span> <span data-ttu-id="03fe5-196">자세한 내용은 <a href="lync-server-2013-calltype-table.md">Lync Server 2013의 Calltype table</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="03fe5-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-198">고유</span><span class="sxs-lookup"><span data-stu-id="03fe5-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="03fe5-199">회의에 포함된 서로 다른 구성 요소의 참가 시간 정보와 연결된 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-200"><strong>SetupTime 시간</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-201">int</span><span class="sxs-lookup"><span data-stu-id="03fe5-201">int</span></span></p></td>
<td><p><span data-ttu-id="03fe5-202">회의에 참가하는 특정 구성 요소에 필요한 시간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-204">비트만</span><span class="sxs-lookup"><span data-stu-id="03fe5-204">bit</span></span></p></td>
<td><p><span data-ttu-id="03fe5-205">프런트 엔드 서버에서 실행하는 CDR 에이전트에 의해 캡처되었는지, 아니면 클라이언트에 의해 전송되었는지를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-206"><strong>플래그가</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-207">smallint</span><span class="sxs-lookup"><span data-stu-id="03fe5-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="03fe5-208">나중에 사용하도록 예약됩니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="03fe5-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="03fe5-211">오류에 대한 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="03fe5-212"><strong>프런트</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-213">varchar</span><span class="sxs-lookup"><span data-stu-id="03fe5-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="03fe5-214">보고서를 전송한 프런트 엔드 서버의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="03fe5-215"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="03fe5-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="03fe5-216">varchar</span><span class="sxs-lookup"><span data-stu-id="03fe5-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="03fe5-217">보고서를 전송한 프런트 엔드 서버가 포함 된 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="03fe5-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

