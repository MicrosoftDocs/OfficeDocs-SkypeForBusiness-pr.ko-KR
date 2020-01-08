---
title: 'Lync Server 2013: SessionDetails 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="2b219-102">Lync Server 2013의 SessionDetails 보기</span><span class="sxs-lookup"><span data-stu-id="2b219-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b219-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="2b219-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="2b219-104">SessionDetails view는 피어 투 피어 세션에 대 한 정보를 저장 하는데,이는 VoIP 전화 통화, 2-파티 IM 세션 또는 기타 세션 유형이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="2b219-105">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b219-106">열</span><span class="sxs-lookup"><span data-stu-id="2b219-106">Column</span></span></th>
<th><span data-ttu-id="2b219-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="2b219-107">Data Type</span></span></th>
<th><span data-ttu-id="2b219-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="2b219-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b219-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-110">dmtf</span><span class="sxs-lookup"><span data-stu-id="2b219-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b219-111">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-111">Time of session request.</span></span> <span data-ttu-id="2b219-112">세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="2b219-113">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 테이블의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-115">int</span><span class="sxs-lookup"><span data-stu-id="2b219-115">int</span></span></p></td>
<td><p><span data-ttu-id="2b219-116">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-116">ID number to identify the session.</span></span> <span data-ttu-id="2b219-117">세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="2b219-118">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-120">dmtf</span><span class="sxs-lookup"><span data-stu-id="2b219-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b219-121">첫 번째 초대 요청의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-121">Time of the first INVITE request.</span></span> <span data-ttu-id="2b219-122">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="2b219-123">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="2b219-124">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="2b219-125">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b219-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b219-128">세션을 시작한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b219-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b219-131">세션에 참가 한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-132"><strong>Fromurit</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-134">세션을 시작한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="2b219-135">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-138">세션에 참가 한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="2b219-139">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b219-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b219-142">세션을 시작한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="2b219-143">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-144"><strong>ToTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-146">세션에 참가 한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="2b219-147">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="2b219-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2b219-150">세션을 시작한 사용자의 끝점에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="2b219-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2b219-153">세션에 참가 한 사용자의 끝점에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-155">dmtf</span><span class="sxs-lookup"><span data-stu-id="2b219-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b219-156">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-158">int</span><span class="sxs-lookup"><span data-stu-id="2b219-158">int</span></span></p></td>
<td><p><span data-ttu-id="2b219-159">세션을 시작한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-161">int</span><span class="sxs-lookup"><span data-stu-id="2b219-161">int</span></span></p></td>
<td><p><span data-ttu-id="2b219-162">세션에 참가 한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-165">세션을 시작한 사용자가 사용 하는 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-167">int</span><span class="sxs-lookup"><span data-stu-id="2b219-167">int</span></span></p></td>
<td><p><span data-ttu-id="2b219-168">세션을 시작한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-168">Client used by the user who started the session.</span></span> <span data-ttu-id="2b219-169">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2b219-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="2b219-172">세션을 시작한 사용자가 사용 하는 클라이언트 범주의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-175">세션에 참가 한 사용자가 사용 하는 클라이언트 버전</span><span class="sxs-lookup"><span data-stu-id="2b219-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-177">int</span><span class="sxs-lookup"><span data-stu-id="2b219-177">int</span></span></p></td>
<td><p><span data-ttu-id="2b219-178">세션에 참가 한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="2b219-179">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2b219-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="2b219-182">세션에 참가 한 사용자가 사용 하는 클라이언트 범주의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b219-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b219-185">세션의 대상 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b219-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b219-188">세션에 대 한 대상 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="2b219-189">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b219-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b219-192">해당 세션이 시작 된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-195">세션이 시작 된 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="2b219-196">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-199">세션이 시작 된 사용자를 대신해 서의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="2b219-200">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2b219-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2b219-203">세션을 참조 한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-206">세션을 참조 한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="2b219-207">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-210">세션을 참조 한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="2b219-211">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="2b219-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="2b219-214">SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-214">SIP dialog ID.</span></span> <span data-ttu-id="2b219-215">형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-215">The format is:</span></span></p>
<p><span data-ttu-id="2b219-216">대화 상자; from 태그; 태그</span><span class="sxs-lookup"><span data-stu-id="2b219-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-217"><strong>Legredir</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="2b219-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2b219-219">여러 세션의 연관성을 위해 사용 되는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-221">dmtf</span><span class="sxs-lookup"><span data-stu-id="2b219-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b219-222">세션으로 대체 된 대화의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="2b219-223">ReplaceDialogIdSeq와 함께 사용 하 여 세션으로 대체 되는 대화를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="2b219-224">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-226">int</span><span class="sxs-lookup"><span data-stu-id="2b219-226">int</span></span></p></td>
<td><p><span data-ttu-id="2b219-227">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-227">ID number to identify the session.</span></span> <span data-ttu-id="2b219-228">ReplaceDialogIdTime와 함께 사용 하 여 세션으로 대체 되는 대화를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="2b219-229">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b219-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="2b219-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="2b219-232">세션에서 대체 하는 SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="2b219-233">형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-233">The format is:</span></span></p>
<p><span data-ttu-id="2b219-234">대화 상자; from 태그; 태그</span><span class="sxs-lookup"><span data-stu-id="2b219-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-236">dmtf</span><span class="sxs-lookup"><span data-stu-id="2b219-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="2b219-237">첫 번째 초대 메시지에 대 한 응답 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="2b219-238">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="2b219-239">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-241">int</span><span class="sxs-lookup"><span data-stu-id="2b219-241">int</span></span></p></td>
<td><p><span data-ttu-id="2b219-242">세션 초대에 대 한 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="2b219-243">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="2b219-244">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-246">int</span><span class="sxs-lookup"><span data-stu-id="2b219-246">int</span></span></p></td>
<td><p><span data-ttu-id="2b219-247">SIP 헤더에서 진단 ID를 캡처 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-250">세션의 콘텐츠 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-253">세션에 대 한 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-254"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-256">세션에 대 한 데이터를 캡처한 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-259">세션을 시작한 사용자가 사용 하는 Edge 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-262">세션을 시작한 사용자가 사용 하는 Edge 서버의 FQDN</span><span class="sxs-lookup"><span data-stu-id="2b219-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-264">다소</span><span class="sxs-lookup"><span data-stu-id="2b219-264">bit</span></span></p></td>
<td><p><span data-ttu-id="2b219-265">세션을 시작한 사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-267">다소</span><span class="sxs-lookup"><span data-stu-id="2b219-267">bit</span></span></p></td>
<td><p><span data-ttu-id="2b219-268">세션에 참가 한 사용자가 내부 네트워크에서 로그온 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="2b219-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2b219-271">세션의 호출 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-273">smallint</span><span class="sxs-lookup"><span data-stu-id="2b219-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="2b219-274">세션을 시작한 사용자의 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="2b219-275">다음과 같은 특성 정의가 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="2b219-276">0x01-데스크톱 전화와 통합</span><span class="sxs-lookup"><span data-stu-id="2b219-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-278">smallint</span><span class="sxs-lookup"><span data-stu-id="2b219-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="2b219-279">세션을 시작한 사용자의 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="2b219-280">다음과 같은 특성 정의가 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="2b219-281">0x01-데스크톱 전화와 통합</span><span class="sxs-lookup"><span data-stu-id="2b219-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b219-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-283">smallint</span><span class="sxs-lookup"><span data-stu-id="2b219-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="2b219-284">통화 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-284">Indicates the call attributes.</span></span> <span data-ttu-id="2b219-285">다음과 같은 특성 정의가 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="2b219-286">0x01-재시도 하는 세션</span><span class="sxs-lookup"><span data-stu-id="2b219-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="2b219-287">0x02-응답 그룹을 대신 하 여 상담원이 수행한 A 통화</span><span class="sxs-lookup"><span data-stu-id="2b219-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b219-288"><strong>위치</strong></span><span class="sxs-lookup"><span data-stu-id="2b219-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="2b219-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="2b219-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="2b219-290">비상 전화의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="2b219-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

