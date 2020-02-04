---
title: 'Lync Server 2013: SessionDetails 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fabf7ae963240f6a2b14ac8c3db272e0cb06091c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="9fb42-102">Lync Server 2013의 SessionDetails 보기</span><span class="sxs-lookup"><span data-stu-id="9fb42-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9fb42-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9fb42-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9fb42-104">SessionDetails view는 피어 투 피어 세션에 대 한 정보를 저장 하는데,이는 VoIP 전화 통화, 2-파티 IM 세션 또는 기타 세션 유형이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="9fb42-105">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9fb42-106">열</span><span class="sxs-lookup"><span data-stu-id="9fb42-106">Column</span></span></th>
<th><span data-ttu-id="9fb42-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9fb42-107">Data Type</span></span></th>
<th><span data-ttu-id="9fb42-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="9fb42-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="9fb42-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9fb42-111">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-111">Time of session request.</span></span> <span data-ttu-id="9fb42-112">세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="9fb42-113">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 테이블의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-115">int</span><span class="sxs-lookup"><span data-stu-id="9fb42-115">int</span></span></p></td>
<td><p><span data-ttu-id="9fb42-116">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-116">ID number to identify the session.</span></span> <span data-ttu-id="9fb42-117">세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="9fb42-118">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-120">dmtf</span><span class="sxs-lookup"><span data-stu-id="9fb42-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="9fb42-121">첫 번째 초대 요청의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-121">Time of the first INVITE request.</span></span> <span data-ttu-id="9fb42-122">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9fb42-123">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="9fb42-124">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9fb42-125">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb42-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-128">세션을 시작한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb42-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-131">세션에 참가 한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-132"><strong>Fromurit</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-134">세션을 시작한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="9fb42-135">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-138">세션에 참가 한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="9fb42-139">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb42-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-142">세션을 시작한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="9fb42-143">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-144"><strong>ToTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-146">세션에 참가 한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="9fb42-147">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9fb42-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9fb42-150">세션을 시작한 사용자의 끝점에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9fb42-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9fb42-153">세션에 참가 한 사용자의 끝점에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-155">dmtf</span><span class="sxs-lookup"><span data-stu-id="9fb42-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="9fb42-156">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-158">int</span><span class="sxs-lookup"><span data-stu-id="9fb42-158">int</span></span></p></td>
<td><p><span data-ttu-id="9fb42-159">세션을 시작한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-161">int</span><span class="sxs-lookup"><span data-stu-id="9fb42-161">int</span></span></p></td>
<td><p><span data-ttu-id="9fb42-162">세션에 참가 한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-165">세션을 시작한 사용자가 사용 하는 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-167">int</span><span class="sxs-lookup"><span data-stu-id="9fb42-167">int</span></span></p></td>
<td><p><span data-ttu-id="9fb42-168">세션을 시작한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-168">Client used by the user who started the session.</span></span> <span data-ttu-id="9fb42-169">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9fb42-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-172">세션을 시작한 사용자가 사용 하는 클라이언트 범주의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-175">세션에 참가 한 사용자가 사용 하는 클라이언트 버전</span><span class="sxs-lookup"><span data-stu-id="9fb42-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-177">int</span><span class="sxs-lookup"><span data-stu-id="9fb42-177">int</span></span></p></td>
<td><p><span data-ttu-id="9fb42-178">세션에 참가 한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="9fb42-179">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9fb42-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-182">세션에 참가 한 사용자가 사용 하는 클라이언트 범주의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb42-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-185">세션의 대상 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb42-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-188">세션에 대 한 대상 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="9fb42-189">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb42-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-192">해당 세션이 시작 된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-195">세션이 시작 된 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="9fb42-196">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-199">세션이 시작 된 사용자를 대신해 서의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="9fb42-200">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9fb42-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-203">세션을 참조 한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-206">세션을 참조 한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="9fb42-207">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-210">세션을 참조 한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="9fb42-211">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="9fb42-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-214">SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-214">SIP dialog ID.</span></span> <span data-ttu-id="9fb42-215">형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-215">The format is:</span></span></p>
<p><span data-ttu-id="9fb42-216">대화 상자; from 태그; 태그</span><span class="sxs-lookup"><span data-stu-id="9fb42-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-217"><strong>Legredir</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9fb42-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9fb42-219">여러 세션의 연관성을 위해 사용 되는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-221">dmtf</span><span class="sxs-lookup"><span data-stu-id="9fb42-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="9fb42-222">세션으로 대체 된 대화의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="9fb42-223">ReplaceDialogIdSeq와 함께 사용 하 여 세션으로 대체 되는 대화를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="9fb42-224">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-226">int</span><span class="sxs-lookup"><span data-stu-id="9fb42-226">int</span></span></p></td>
<td><p><span data-ttu-id="9fb42-227">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-227">ID number to identify the session.</span></span> <span data-ttu-id="9fb42-228">ReplaceDialogIdTime와 함께 사용 하 여 세션으로 대체 되는 대화를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="9fb42-229">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb42-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="9fb42-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-232">세션에서 대체 하는 SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="9fb42-233">형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-233">The format is:</span></span></p>
<p><span data-ttu-id="9fb42-234">대화 상자; from 태그; 태그</span><span class="sxs-lookup"><span data-stu-id="9fb42-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-236">dmtf</span><span class="sxs-lookup"><span data-stu-id="9fb42-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="9fb42-237">첫 번째 초대 메시지에 대 한 응답 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="9fb42-238">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9fb42-239">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-241">int</span><span class="sxs-lookup"><span data-stu-id="9fb42-241">int</span></span></p></td>
<td><p><span data-ttu-id="9fb42-242">세션 초대에 대 한 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="9fb42-243">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9fb42-244">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-246">int</span><span class="sxs-lookup"><span data-stu-id="9fb42-246">int</span></span></p></td>
<td><p><span data-ttu-id="9fb42-247">SIP 헤더에서 진단 ID를 캡처 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-250">세션의 콘텐츠 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-253">세션에 대 한 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-254"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-256">세션에 대 한 데이터를 캡처한 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-259">세션을 시작한 사용자가 사용 하는 Edge 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-262">세션을 시작한 사용자가 사용 하는 Edge 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="9fb42-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-264">다소</span><span class="sxs-lookup"><span data-stu-id="9fb42-264">bit</span></span></p></td>
<td><p><span data-ttu-id="9fb42-265">세션을 시작한 사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-267">다소</span><span class="sxs-lookup"><span data-stu-id="9fb42-267">bit</span></span></p></td>
<td><p><span data-ttu-id="9fb42-268">세션에 참가 한 사용자가 내부 네트워크에서 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9fb42-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-271">세션의 호출 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-273">smallint</span><span class="sxs-lookup"><span data-stu-id="9fb42-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="9fb42-274">세션을 시작한 사용자의 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="9fb42-275">다음과 같은 특성 정의가 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9fb42-276">0x01-데스크톱 전화와 통합</span><span class="sxs-lookup"><span data-stu-id="9fb42-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-278">smallint</span><span class="sxs-lookup"><span data-stu-id="9fb42-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="9fb42-279">세션을 시작한 사용자의 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="9fb42-280">다음과 같은 특성 정의가 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9fb42-281">0x01-데스크톱 전화와 통합</span><span class="sxs-lookup"><span data-stu-id="9fb42-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9fb42-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-283">smallint</span><span class="sxs-lookup"><span data-stu-id="9fb42-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="9fb42-284">통화 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-284">Indicates the call attributes.</span></span> <span data-ttu-id="9fb42-285">다음과 같은 특성 정의가 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9fb42-286">0x01-재시도 하는 세션</span><span class="sxs-lookup"><span data-stu-id="9fb42-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="9fb42-287">0x02-응답 그룹을 대신 하 여 상담원이 수행한 A 통화</span><span class="sxs-lookup"><span data-stu-id="9fb42-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9fb42-288"><strong>위치</strong></span><span class="sxs-lookup"><span data-stu-id="9fb42-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="9fb42-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9fb42-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9fb42-290">비상 전화의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb42-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

