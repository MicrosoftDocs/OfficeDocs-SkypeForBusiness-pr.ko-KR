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
ms.openlocfilehash: 3f7a143a0812b19a840c7eb339e80611720a08b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="9ef06-102">Lync Server 2013의 SessionDetails 보기</span><span class="sxs-lookup"><span data-stu-id="9ef06-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9ef06-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9ef06-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9ef06-104">SessionDetails view에는 피어 투 피어 세션에 대 한 정보, 즉 VoIP 전화 통화, 두 사용자의 IM 세션 또는 기타 유형의 세션이 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="9ef06-105">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9ef06-106">열</span><span class="sxs-lookup"><span data-stu-id="9ef06-106">Column</span></span></th>
<th><span data-ttu-id="9ef06-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9ef06-107">Data Type</span></span></th>
<th><span data-ttu-id="9ef06-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="9ef06-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-110">datetime</span><span class="sxs-lookup"><span data-stu-id="9ef06-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9ef06-111">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-111">Time of session request.</span></span> <span data-ttu-id="9ef06-112">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="9ef06-113">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 테이블의 대화 상자 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ef06-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-115">int</span><span class="sxs-lookup"><span data-stu-id="9ef06-115">int</span></span></p></td>
<td><p><span data-ttu-id="9ef06-116">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-116">ID number to identify the session.</span></span> <span data-ttu-id="9ef06-117">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="9ef06-118">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ef06-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-120">datetime</span><span class="sxs-lookup"><span data-stu-id="9ef06-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="9ef06-121">첫 번째 INVITE 요청의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-121">Time of the first INVITE request.</span></span> <span data-ttu-id="9ef06-122">이 필드는 일반적으로 세션의 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9ef06-123">INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="9ef06-124">이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9ef06-125">INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9ef06-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-128">세션을 시작한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9ef06-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-131">세션에 참가 한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-133">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-134">세션을 시작한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="9ef06-135">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ef06-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-138">세션에 참가 한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="9ef06-139">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ef06-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9ef06-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-142">세션을 시작한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="9ef06-143">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ef06-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-144"><strong>ToTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-145">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-146">세션에 참가 한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="9ef06-147">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ef06-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-149">고유</span><span class="sxs-lookup"><span data-stu-id="9ef06-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9ef06-150">세션을 시작한 사용자의 끝점에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-152">고유</span><span class="sxs-lookup"><span data-stu-id="9ef06-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9ef06-153">세션에 참가 한 사용자의 끝점에 대 한 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-155">datetime</span><span class="sxs-lookup"><span data-stu-id="9ef06-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="9ef06-156">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-158">int</span><span class="sxs-lookup"><span data-stu-id="9ef06-158">int</span></span></p></td>
<td><p><span data-ttu-id="9ef06-159">세션을 시작한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-161">int</span><span class="sxs-lookup"><span data-stu-id="9ef06-161">int</span></span></p></td>
<td><p><span data-ttu-id="9ef06-162">세션에 참가 한 사용자가 보낸 메시지 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-164">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-165">세션을 시작한 사용자가 사용 하는 클라이언트의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-167">int</span><span class="sxs-lookup"><span data-stu-id="9ef06-167">int</span></span></p></td>
<td><p><span data-ttu-id="9ef06-168">세션을 시작한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-168">Client used by the user who started the session.</span></span> <span data-ttu-id="9ef06-169">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ef06-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9ef06-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-172">세션을 시작한 사용자가 사용 하는 클라이언트의 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-175">세션에 참가 한 사용자가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-177">int</span><span class="sxs-lookup"><span data-stu-id="9ef06-177">int</span></span></p></td>
<td><p><span data-ttu-id="9ef06-178">세션에 참가 한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="9ef06-179">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ef06-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9ef06-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-182">세션에 참가 한 사용자가 사용 하는 클라이언트의 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9ef06-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-185">세션 대상 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9ef06-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-188">세션에 대 한 대상 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="9ef06-189">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ef06-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9ef06-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-192">세션을 대신 시작한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-195">세션을 대신 시작한 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="9ef06-196">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ef06-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-199">세션을 대신 시작한 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="9ef06-200">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ef06-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9ef06-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-203">세션을 참조한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-205">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-206">세션을 참조한 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="9ef06-207">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ef06-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-209">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-210">세션을 참조한 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="9ef06-211">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9ef06-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="9ef06-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-214">SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-214">SIP dialog ID.</span></span> <span data-ttu-id="9ef06-215">형식:</span><span class="sxs-lookup"><span data-stu-id="9ef06-215">The format is:</span></span></p>
<p><span data-ttu-id="9ef06-216">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="9ef06-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-217"><strong>관계</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-218">고유</span><span class="sxs-lookup"><span data-stu-id="9ef06-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9ef06-219">여러 세션을 상호 연결 하는 데 사용 되는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-221">datetime</span><span class="sxs-lookup"><span data-stu-id="9ef06-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="9ef06-222">세션으로 교체 된 대화의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="9ef06-223">ReplaceDialogIdSeq와 함께 사용 되어 세션으로 대체 되는 대화를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="9ef06-224">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ef06-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-226">int</span><span class="sxs-lookup"><span data-stu-id="9ef06-226">int</span></span></p></td>
<td><p><span data-ttu-id="9ef06-227">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-227">ID number to identify the session.</span></span> <span data-ttu-id="9ef06-228">ReplaceDialogIdTime와 함께 사용 되어 세션으로 대체 되는 대화를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="9ef06-229">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="9ef06-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="9ef06-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-232">세션이 교체하는 SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="9ef06-233">형식:</span><span class="sxs-lookup"><span data-stu-id="9ef06-233">The format is:</span></span></p>
<p><span data-ttu-id="9ef06-234">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="9ef06-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-236">datetime</span><span class="sxs-lookup"><span data-stu-id="9ef06-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="9ef06-p120">첫 번째 INVITE 메시지에 대한 응답 시간입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-241">int</span><span class="sxs-lookup"><span data-stu-id="9ef06-241">int</span></span></p></td>
<td><p><span data-ttu-id="9ef06-p121">세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-246">int</span><span class="sxs-lookup"><span data-stu-id="9ef06-246">int</span></span></p></td>
<td><p><span data-ttu-id="9ef06-247">SIP 헤더에서 캡처된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-249">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-250">세션의 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-251"><strong>프런트</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-252">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-253">세션에 대해 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-254"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-255">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-256">세션에 대해 데이터를 캡처한 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-258">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-259">세션을 시작한 사용자가 사용 하는에 지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-261">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-262">세션을 시작한 사용자가 사용 하는에 지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-264">비트만</span><span class="sxs-lookup"><span data-stu-id="9ef06-264">bit</span></span></p></td>
<td><p><span data-ttu-id="9ef06-265">세션을 시작한 사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-267">비트만</span><span class="sxs-lookup"><span data-stu-id="9ef06-267">bit</span></span></p></td>
<td><p><span data-ttu-id="9ef06-268">세션에 참가 한 사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-270">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9ef06-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-271">세션의 통화 우선 순위입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-273">smallint</span><span class="sxs-lookup"><span data-stu-id="9ef06-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="9ef06-274">세션을 시작한 사용자의 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="9ef06-275">허용된 특성 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9ef06-276">0x01 - 데스크톱 전화와 통합됨</span><span class="sxs-lookup"><span data-stu-id="9ef06-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-278">smallint</span><span class="sxs-lookup"><span data-stu-id="9ef06-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="9ef06-279">세션을 시작한 사용자의 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="9ef06-280">허용된 특성 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9ef06-281">0x01 - 데스크톱 전화와 통합됨</span><span class="sxs-lookup"><span data-stu-id="9ef06-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9ef06-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-283">smallint</span><span class="sxs-lookup"><span data-stu-id="9ef06-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="9ef06-p124">통화 특성을 나타냅니다. 허용된 특성 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9ef06-286">0x01 - 다시 시도된 세션</span><span class="sxs-lookup"><span data-stu-id="9ef06-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="9ef06-287">0x02-응답 그룹을 대신 하 여 에이전트가 수행한 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9ef06-288"><strong>위치</strong></span><span class="sxs-lookup"><span data-stu-id="9ef06-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="9ef06-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9ef06-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9ef06-290">응급 통화의 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="9ef06-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

