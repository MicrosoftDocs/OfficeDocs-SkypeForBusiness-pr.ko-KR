---
title: 'Lync Server 2013: ErrorReport view'
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
ms.openlocfilehash: a72b2f12c00248095b99198182b8c71bb945bfa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="b9b84-102">Lync Server 2013의 ErrorReport 보기</span><span class="sxs-lookup"><span data-stu-id="b9b84-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9b84-103">_**마지막으로 수정한 주제:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="b9b84-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="b9b84-104">ErrorReport 보기는 보고 된 오류에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="b9b84-105">각 레코드는 오류 발생 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-105">Each record is one error occurrence.</span></span> <span data-ttu-id="b9b84-106">이 오류는 프런트 엔드 서버에서 실행 되는 CDR 에이전트에서 또는 클라이언트에서 전송 된에 의해 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="b9b84-107">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b9b84-108">열</span><span class="sxs-lookup"><span data-stu-id="b9b84-108">Column</span></span></th>
<th><span data-ttu-id="b9b84-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b9b84-109">Data Type</span></span></th>
<th><span data-ttu-id="b9b84-110">세부적인</span><span class="sxs-lookup"><span data-stu-id="b9b84-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-112">dmtf</span><span class="sxs-lookup"><span data-stu-id="b9b84-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b9b84-113">오류가 발생 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-113">Time of error occurred.</span></span> <span data-ttu-id="b9b84-114">오류를 고유 하 게 식별 하는 ErrorReportSeq와 함께 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-116">int</span><span class="sxs-lookup"><span data-stu-id="b9b84-116">int</span></span></p></td>
<td><p><span data-ttu-id="b9b84-117">오류를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-117">ID number to identify the error.</span></span> <span data-ttu-id="b9b84-118">오류를 고유 하 게 식별 하는 ErrorTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-120">int</span><span class="sxs-lookup"><span data-stu-id="b9b84-120">int</span></span></p></td>
<td><p><span data-ttu-id="b9b84-121">오류 보고서의 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b9b84-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-124">오류를 발생 시킨 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-125"><strong>Fromurit</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9b84-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-127">오류를 발생 시킨 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="b9b84-128">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9b84-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9b84-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-131">오류를 발생 시킨 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="b9b84-132">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9b84-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b9b84-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-135">오류 보고서를 대상으로 하는 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9b84-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-138">오류 보고서를 대상으로 하는 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="b9b84-139">자세한 내용은 UriTypes 테이블을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9b84-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-140"><strong>ToTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9b84-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-142">오류 보고서를 대상으로 하는 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="b9b84-143">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9b84-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b9b84-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-146">오류 보고서의 대상인 컨퍼런스의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9b84-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-149">오류 보고서의 대상에 해당 하는 회의의 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="b9b84-150">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9b84-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-152">dmtf</span><span class="sxs-lookup"><span data-stu-id="b9b84-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="b9b84-153">오류 보고를 시작 하는 세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="b9b84-154">세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b9b84-155">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9b84-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-157">int</span><span class="sxs-lookup"><span data-stu-id="b9b84-157">int</span></span></p></td>
<td><p><span data-ttu-id="b9b84-158">오류 보고서를 시작 하는 세션 요청을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="b9b84-159">세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="b9b84-160">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9b84-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="b9b84-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-163">오류를 발생 시킨 세션의 SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="b9b84-164">형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-164">The format is:</span></span></p>
<p><span data-ttu-id="b9b84-165">대화 상자; from 태그; 태그</span><span class="sxs-lookup"><span data-stu-id="b9b84-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="b9b84-166">이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="b9b84-167">캐스트 (cast (max) as varchar (max))</span><span class="sxs-lookup"><span data-stu-id="b9b84-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9b84-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-170">오류를 발생 시킨 사용자가 사용 하는 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-172">int</span><span class="sxs-lookup"><span data-stu-id="b9b84-172">int</span></span></p></td>
<td><p><span data-ttu-id="b9b84-173">오류를 발생 시킨 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="b9b84-174">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9b84-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b9b84-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-177">오류를 발생 시킨 사용자가 사용 하는 클라이언트 범주의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-178"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9b84-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-180">오류를 발생 시킨 서버의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).</span><span class="sxs-lookup"><span data-stu-id="b9b84-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-181"><strong>응용 프로그램</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-182">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9b84-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-183">오류를 발생 시킨 응용 프로그램의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).</span><span class="sxs-lookup"><span data-stu-id="b9b84-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-185">int</span><span class="sxs-lookup"><span data-stu-id="b9b84-185">int</span></span></p></td>
<td><p><span data-ttu-id="b9b84-186">오류 보고서를 포함 하는 SIP 메시지의 세션에 대 한 SIP 응답 코드</span><span class="sxs-lookup"><span data-stu-id="b9b84-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="b9b84-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-189">실패 한 요청의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="b9b84-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-192">실패 한 요청의 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b9b84-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-195">세션의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-195">Type of session.</span></span> <span data-ttu-id="b9b84-196">자세한 내용은 <a href="lync-server-2013-calltype-table.md">Lync Server 2013의 Calltype 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b9b84-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-198">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="b9b84-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b9b84-199">고유한 식별자는 회의에 관련 된 다양 한 구성 요소에 대 한 조인 시간 정보를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-200"><strong>SetupTime 시간</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-201">int</span><span class="sxs-lookup"><span data-stu-id="b9b84-201">int</span></span></p></td>
<td><p><span data-ttu-id="b9b84-202">특정 구성 요소가 컨퍼런스에 참가 하는 데 필요한 시간 (밀리초 단위)입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-204">다소</span><span class="sxs-lookup"><span data-stu-id="b9b84-204">bit</span></span></p></td>
<td><p><span data-ttu-id="b9b84-205">프런트 엔드 서버에서 실행 중이거나 클라이언트가 보낸 CDR 에이전트에 의해 오류 보고서가 캡처 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-206"><strong>플래그</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-207">smallint</span><span class="sxs-lookup"><span data-stu-id="b9b84-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="b9b84-208">나중에 사용 하기 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="b9b84-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b9b84-211">오류에 대 한 추가 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b9b84-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-213">varchar</span><span class="sxs-lookup"><span data-stu-id="b9b84-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="b9b84-214">보고서를 제출한 프런트 엔드 서버의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b9b84-215"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="b9b84-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="b9b84-216">varchar</span><span class="sxs-lookup"><span data-stu-id="b9b84-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="b9b84-217">보고서를 제출한 프런트 엔드 서버를 포함 하는 풀의 정규화 된 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b9b84-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

