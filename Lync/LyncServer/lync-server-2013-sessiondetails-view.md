---
title: 'Lync Server 2013: SessionDetails 보기'
description: 'Lync Server 2013: SessionDetails 보기입니다.'
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
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573244"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="74066-103">Lync Server 2013의 SessionDetails 보기</span><span class="sxs-lookup"><span data-stu-id="74066-103">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74066-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="74066-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="74066-105">SessionDetails 보기에는 피어 투 피어 세션에 대 한 정보, 즉 VoIP-VoIP 전화 통화, 두 사용자의 IM 세션 또는 기타 세션 유형이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="74066-105">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="74066-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="74066-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="74066-107">열</span><span class="sxs-lookup"><span data-stu-id="74066-107">Column</span></span></th>
<th><span data-ttu-id="74066-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="74066-108">Data Type</span></span></th>
<th><span data-ttu-id="74066-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="74066-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="74066-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="74066-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-111">datetime</span><span class="sxs-lookup"><span data-stu-id="74066-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="74066-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-112">Time of session request.</span></span> <span data-ttu-id="74066-113">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74066-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="74066-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 테이블의 대화 상자 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74066-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="74066-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-116">int</span><span class="sxs-lookup"><span data-stu-id="74066-116">int</span></span></p></td>
<td><p><span data-ttu-id="74066-117">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-117">ID number to identify the session.</span></span> <span data-ttu-id="74066-118">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="74066-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="74066-119">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74066-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="74066-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-121">datetime</span><span class="sxs-lookup"><span data-stu-id="74066-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="74066-122">첫 번째 INVITE 요청의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-122">Time of the first INVITE request.</span></span> <span data-ttu-id="74066-123">이 필드는 일반적으로 세션의 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="74066-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="74066-124">INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="74066-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="74066-125">이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="74066-125">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="74066-126">INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="74066-126">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-127"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="74066-127"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74066-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74066-129">세션을 시작한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-129">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-130"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="74066-130"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-131">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74066-131">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74066-132">세션에 참가 한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-132">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-133"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="74066-133"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-135">세션을 시작한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-135">Type of URI of the user who started the session.</span></span> <span data-ttu-id="74066-136">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74066-136">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="74066-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-138">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-139">세션에 참가 한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-139">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="74066-140">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74066-140">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-141"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="74066-141"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74066-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74066-143">세션을 시작한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-143">Tenant of the user who started the session.</span></span> <span data-ttu-id="74066-144">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74066-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-145"><strong>ToTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="74066-145"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-147">세션에 참가 한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-147">The tenant of the user who joined the session.</span></span> <span data-ttu-id="74066-148">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74066-148">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-149"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="74066-149"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-150">고유</span><span class="sxs-lookup"><span data-stu-id="74066-150">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="74066-151">세션을 시작한 사용자의 끝점에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-151">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-152"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="74066-152"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-153">고유</span><span class="sxs-lookup"><span data-stu-id="74066-153">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="74066-154">세션에 참가 한 사용자의 끝점에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-154">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-155"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="74066-155"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-156">datetime</span><span class="sxs-lookup"><span data-stu-id="74066-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="74066-157">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-157">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-158"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="74066-158"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-159">int</span><span class="sxs-lookup"><span data-stu-id="74066-159">int</span></span></p></td>
<td><p><span data-ttu-id="74066-160">세션을 시작한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-160">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-161"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="74066-161"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-162">int</span><span class="sxs-lookup"><span data-stu-id="74066-162">int</span></span></p></td>
<td><p><span data-ttu-id="74066-163">세션에 참가 한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-163">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-164"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="74066-164"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-165">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-166">세션을 시작한 사용자가 사용 하는 클라이언트의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-166">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-167"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="74066-167"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-168">int</span><span class="sxs-lookup"><span data-stu-id="74066-168">int</span></span></p></td>
<td><p><span data-ttu-id="74066-169">세션을 시작한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-169">Client used by the user who started the session.</span></span> <span data-ttu-id="74066-170">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74066-170">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-171"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="74066-171"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="74066-172">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="74066-173">세션을 시작한 사용자가 사용 하는 클라이언트의 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-173">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-174"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="74066-174"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-175">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-175">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-176">세션에 참가 한 사용자가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-176">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-177"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="74066-177"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-178">int</span><span class="sxs-lookup"><span data-stu-id="74066-178">int</span></span></p></td>
<td><p><span data-ttu-id="74066-179">세션에 참가 한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-179">Client used by the user who joined the session.</span></span> <span data-ttu-id="74066-180">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74066-180">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-181"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="74066-181"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-182">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="74066-182">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="74066-183">세션에 참가 한 사용자가 사용 하는 클라이언트의 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-183">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-184"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="74066-184"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-185">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74066-185">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74066-186">세션 대상 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-186">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-187"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="74066-187"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-188">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74066-188">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74066-189">세션에 대 한 대상 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-189">Type of URI of the target user for the session.</span></span> <span data-ttu-id="74066-190">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74066-190">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-191"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="74066-191"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74066-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74066-193">세션을 대신 시작한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-193">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-194"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="74066-194"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-196">세션을 대신 시작한 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-196">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="74066-197">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74066-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-198"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="74066-198"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-200">세션을 대신 시작한 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-200">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="74066-201">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74066-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-202"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="74066-202"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-203">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="74066-203">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="74066-204">세션을 참조한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-204">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-205"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="74066-205"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-206">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-206">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-207">세션을 참조한 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-207">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="74066-208">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74066-208">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-209"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="74066-209"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-210">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-210">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-211">세션을 참조한 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-211">Tenant of the user who referred the session.</span></span> <span data-ttu-id="74066-212">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="74066-212">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-213"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="74066-213"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-214">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="74066-214">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="74066-215">SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-215">SIP dialog ID.</span></span> <span data-ttu-id="74066-216">형식:</span><span class="sxs-lookup"><span data-stu-id="74066-216">The format is:</span></span></p>
<p><span data-ttu-id="74066-217">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="74066-217">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-218"><strong>관계</strong></span><span class="sxs-lookup"><span data-stu-id="74066-218"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-219">고유</span><span class="sxs-lookup"><span data-stu-id="74066-219">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="74066-220">여러 세션을 상호 연결 하는 데 사용 되는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-220">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-221"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="74066-221"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-222">datetime</span><span class="sxs-lookup"><span data-stu-id="74066-222">datetime</span></span></p></td>
<td><p><span data-ttu-id="74066-223">세션으로 교체 된 대화의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-223">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="74066-224">ReplaceDialogIdSeq와 함께 사용 되어 세션으로 대체 되는 대화를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="74066-224">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="74066-225">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74066-225">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-226"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="74066-226"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-227">int</span><span class="sxs-lookup"><span data-stu-id="74066-227">int</span></span></p></td>
<td><p><span data-ttu-id="74066-228">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-228">ID number to identify the session.</span></span> <span data-ttu-id="74066-229">ReplaceDialogIdTime와 함께 사용 되어 세션으로 대체 되는 대화를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="74066-229">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="74066-230">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74066-230">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-231"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="74066-231"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-232">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="74066-232">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="74066-233">세션이 교체하는 SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-233">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="74066-234">형식:</span><span class="sxs-lookup"><span data-stu-id="74066-234">The format is:</span></span></p>
<p><span data-ttu-id="74066-235">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="74066-235">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-236"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="74066-236"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-237">datetime</span><span class="sxs-lookup"><span data-stu-id="74066-237">datetime</span></span></p></td>
<td><p><span data-ttu-id="74066-p120">첫 번째 INVITE 메시지에 대한 응답 시간입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="74066-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-241"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="74066-241"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-242">int</span><span class="sxs-lookup"><span data-stu-id="74066-242">int</span></span></p></td>
<td><p><span data-ttu-id="74066-p121">세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="74066-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-246"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="74066-246"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-247">int</span><span class="sxs-lookup"><span data-stu-id="74066-247">int</span></span></p></td>
<td><p><span data-ttu-id="74066-248">SIP 헤더에서 캡처된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-248">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-249"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="74066-249"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-251">세션의 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-251">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-252"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="74066-252"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-254">세션에 대해 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-254">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-255"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="74066-255"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-257">세션에 대해 데이터를 캡처한 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-257">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-258"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="74066-258"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-260">세션을 시작한 사용자가 사용 하는에 지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-260">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-261"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="74066-261"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-262">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-262">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-263">세션을 시작한 사용자가 사용 하는에 지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-263">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-264"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="74066-264"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-265">비트만</span><span class="sxs-lookup"><span data-stu-id="74066-265">bit</span></span></p></td>
<td><p><span data-ttu-id="74066-266">세션을 시작한 사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74066-266">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-267"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="74066-267"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-268">비트만</span><span class="sxs-lookup"><span data-stu-id="74066-268">bit</span></span></p></td>
<td><p><span data-ttu-id="74066-269">세션에 참가 한 사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74066-269">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-270"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="74066-270"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-271">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="74066-271">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="74066-272">세션의 통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-272">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-273"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="74066-273"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-274">smallint</span><span class="sxs-lookup"><span data-stu-id="74066-274">smallint</span></span></p></td>
<td><p><span data-ttu-id="74066-275">세션을 시작한 사용자의 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74066-275">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="74066-276">허용된 특성 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="74066-276">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="74066-277">0x01 - 데스크톱 전화와 통합됨</span><span class="sxs-lookup"><span data-stu-id="74066-277">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-278"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="74066-278"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-279">smallint</span><span class="sxs-lookup"><span data-stu-id="74066-279">smallint</span></span></p></td>
<td><p><span data-ttu-id="74066-280">세션을 시작한 사용자의 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="74066-280">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="74066-281">허용된 특성 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="74066-281">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="74066-282">0x01 - 데스크톱 전화와 통합됨</span><span class="sxs-lookup"><span data-stu-id="74066-282">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="74066-283"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="74066-283"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-284">smallint</span><span class="sxs-lookup"><span data-stu-id="74066-284">smallint</span></span></p></td>
<td><p><span data-ttu-id="74066-p124">통화 특성을 나타냅니다. 허용된 특성 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="74066-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="74066-287">0x01 - 다시 시도된 세션</span><span class="sxs-lookup"><span data-stu-id="74066-287">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="74066-288">0x02-응답 그룹을 대신 하 여 에이전트가 수행한 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-288">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="74066-289"><strong>위치</strong></span><span class="sxs-lookup"><span data-stu-id="74066-289"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="74066-290">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="74066-290">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="74066-291">응급 통화의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="74066-291">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

