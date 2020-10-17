---
title: 'Lync Server 2013: ConferenceSessionDetails 보기'
description: 'Lync Server 2013: ConferenceSessionDetails 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c62f020413efecdbc0f909618256ccc7308d4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566774"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="e807f-103">Lync Server 2013의 ConferenceSessionDetails 보기</span><span class="sxs-lookup"><span data-stu-id="e807f-103">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e807f-104">_**마지막으로 수정 된 항목:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="e807f-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e807f-105">ConferenceSessionDetails 보기에는 단체 세션에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-105">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="e807f-106">각 레코드는 Focus를 가진 세션이거나, 특정 회의 서버를 가진 세션일 수 있는 하나의 회의 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-106">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="e807f-107">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e807f-108">열</span><span class="sxs-lookup"><span data-stu-id="e807f-108">Column</span></span></th>
<th><span data-ttu-id="e807f-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e807f-109">Data Type</span></span></th>
<th><span data-ttu-id="e807f-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e807f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e807f-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e807f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e807f-113">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-113">Time of session request.</span></span> <span data-ttu-id="e807f-114">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-114">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e807f-115">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e807f-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-117">int</span><span class="sxs-lookup"><span data-stu-id="e807f-117">int</span></span></p></td>
<td><p><span data-ttu-id="e807f-118">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-118">ID number to identify the session.</span></span> <span data-ttu-id="e807f-119">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-119">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e807f-120">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e807f-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-121"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-121"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e807f-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="e807f-p104">첫 번째 INVITE 요청의 시간입니다. 이 필드는 일반적으로 세션의 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 필드에 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-126"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-126"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e807f-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e807f-128">회의의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-128">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-129"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-129"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-131">회의 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-131">Type of conference URI.</span></span> <span data-ttu-id="e807f-132">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e807f-132">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-133"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-133"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-134">고유</span><span class="sxs-lookup"><span data-stu-id="e807f-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e807f-p106">반복해서 수행되는 회의를 구분하는 식별자입니다. 반복되는 각 회의 인스턴스는 동일한 ConferenceURI를 갖지만 ConfInstance 값이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-137"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-137"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-138">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e807f-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e807f-139">회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-139">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-140"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-140"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-141">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-142">회의 서버 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-142">Type of conferencing server URI.</span></span> <span data-ttu-id="e807f-143">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e807f-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-144"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-144"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e807f-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e807f-146">세션에 관련된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-146">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-147"><strong>Userurit<</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-147"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-148">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-149">세션에 속하는 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-149">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="e807f-150">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e807f-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-151"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-151"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-152">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-153">세션에 속하는 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-153">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="e807f-154">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e807f-154">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-155"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-155"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-156">고유</span><span class="sxs-lookup"><span data-stu-id="e807f-156">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e807f-157">세션에 속하는 사용자의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-157">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-158"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-158"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-159">datetime</span><span class="sxs-lookup"><span data-stu-id="e807f-159">datetime</span></span></p></td>
<td><p><span data-ttu-id="e807f-160">세션의 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-160">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-161"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-161"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-162">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-163">회의 서버의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-163">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-164"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-164"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-165">int</span><span class="sxs-lookup"><span data-stu-id="e807f-165">int</span></span></p></td>
<td><p><span data-ttu-id="e807f-166">회의 서버의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-166">Type of conference server.</span></span> <span data-ttu-id="e807f-167">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e807f-167">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-168"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-168"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-169">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e807f-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e807f-170">회의 서버 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-170">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-171"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-171"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-172">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-172">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-173">세션에 참가한 사용자가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-173">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-174"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-174"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-175">int</span><span class="sxs-lookup"><span data-stu-id="e807f-175">int</span></span></p></td>
<td><p><span data-ttu-id="e807f-176">세션에 참가한 사용자가 사용한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-176">Client used by the user who participated in the session.</span></span> <span data-ttu-id="e807f-177">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e807f-177">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-178"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-178"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-179">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="e807f-179">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e807f-180">세션에 속하는 사용자가 사용한 클라이언트의 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-180">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-181"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-181"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-182">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e807f-182">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e807f-183">세션을 대신 시작한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-183">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-184"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-184"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-185">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-185">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-186">세션을 대신 시작한 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-186">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="e807f-187">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e807f-187">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-188"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-188"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-189">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-189">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-190">세션을 대신 시작한 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-190">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="e807f-191">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e807f-191">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-192"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-192"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-193">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e807f-193">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e807f-194">세션을 참조한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-194">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-195"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-195"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-196">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-196">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-197">세션을 참조한 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-197">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="e807f-198">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e807f-198">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-199"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-199"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-200">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-200">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-201">세션을 참조한 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-201">Tenant of the user who referred the session.</span></span> <span data-ttu-id="e807f-202">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e807f-202">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-203"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-203"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-204">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="e807f-204">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="e807f-p116">SIP 대화 ID입니다. 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="e807f-207">:d ialog; from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="e807f-207">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-208"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-208"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-209">datetime</span><span class="sxs-lookup"><span data-stu-id="e807f-209">datetime</span></span></p></td>
<td><p><span data-ttu-id="e807f-210">현재 세션으로 교체된 대화를 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-210">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="e807f-211">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e807f-211">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-212"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-212"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-213">int</span><span class="sxs-lookup"><span data-stu-id="e807f-213">int</span></span></p></td>
<td><p><span data-ttu-id="e807f-214">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-214">ID number to identify the session.</span></span> <span data-ttu-id="e807f-215">ReplaceDialogIdTime과 함께 이 세션으로 교체된 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-215">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="e807f-216">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e807f-216">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-217"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-217"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-218">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="e807f-218">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e807f-p119">세션이 교체하는 SIP 대화 ID입니다. 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="e807f-221">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="e807f-221">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-222"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-222"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-223">비트만</span><span class="sxs-lookup"><span data-stu-id="e807f-223">bit</span></span></p></td>
<td><p><span data-ttu-id="e807f-224">세션이 회의 서버에서 시작되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-224">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-225"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-225"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-226">비트만</span><span class="sxs-lookup"><span data-stu-id="e807f-226">bit</span></span></p></td>
<td><p><span data-ttu-id="e807f-227">세션이 회의 서버에서 종료되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-227">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-228"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-228"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-229">비트만</span><span class="sxs-lookup"><span data-stu-id="e807f-229">bit</span></span></p></td>
<td><p><span data-ttu-id="e807f-230">사용자가 내부 네트워크에서 로그온했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-230">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-232">datetime</span><span class="sxs-lookup"><span data-stu-id="e807f-232">datetime</span></span></p></td>
<td><p><span data-ttu-id="e807f-p120">첫 번째 INVITE 메시지에 대한 응답 시간입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-236"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-236"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-237">int</span><span class="sxs-lookup"><span data-stu-id="e807f-237">int</span></span></p></td>
<td><p><span data-ttu-id="e807f-p121">세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-241"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-241"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-242">int</span><span class="sxs-lookup"><span data-stu-id="e807f-242">int</span></span></p></td>
<td><p><span data-ttu-id="e807f-243">세션 SIP 헤더에서 캡처된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-243">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-244"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-244"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-245">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-245">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-246">세션의 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-246">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-247"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-247"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-248">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-248">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-249">세션에 대해 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-249">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-250"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-251">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-251">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-252">세션에 대해 데이터를 캡처한 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-252">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-253"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-253"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-254">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-254">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-255">세션에 참가한 사용자가 사용한 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-255">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-256"><strong>게이트웨이</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-256"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-257">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-257">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-258">세션에 참가한 사용자가 사용한 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-258">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-259"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-259"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-260">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="e807f-260">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e807f-261">세션에 참가한 사용자가 사용한 에지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-261">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e807f-262"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-262"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-263">smallint</span><span class="sxs-lookup"><span data-stu-id="e807f-263">smallint</span></span></p></td>
<td><p><span data-ttu-id="e807f-p122">세션에 참가한 사용자의 특성을 나타냅니다. 허용된 특성 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="e807f-266">0x01 - 데스크톱 전화와 통합됨</span><span class="sxs-lookup"><span data-stu-id="e807f-266">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e807f-267"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e807f-267"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e807f-268">smallint</span><span class="sxs-lookup"><span data-stu-id="e807f-268">smallint</span></span></p></td>
<td><p><span data-ttu-id="e807f-p123">통화 특성을 나타냅니다. 허용된 특성 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e807f-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="e807f-271">0x01 - 다시 시도된 세션0</span><span class="sxs-lookup"><span data-stu-id="e807f-271">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="e807f-272">x02 - 응답 그룹을 대신하여 에이전트가 시작한 통화</span><span class="sxs-lookup"><span data-stu-id="e807f-272">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

