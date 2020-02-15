---
title: 'Lync Server 2013: ConferenceSessionDetails 보기'
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
ms.openlocfilehash: be9d3566a951ee1b65d87e423627f556254173b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="55fcf-102">Lync Server 2013의 ConferenceSessionDetails 보기</span><span class="sxs-lookup"><span data-stu-id="55fcf-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55fcf-103">_**마지막으로 수정 된 항목:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="55fcf-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="55fcf-104">ConferenceSessionDetails 보기에는 단체 세션에 대한 정보가 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="55fcf-105">각 레코드는 Focus를 가진 세션이거나, 특정 회의 서버를 가진 세션일 수 있는 하나의 회의 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="55fcf-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="55fcf-107">열</span><span class="sxs-lookup"><span data-stu-id="55fcf-107">Column</span></span></th>
<th><span data-ttu-id="55fcf-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="55fcf-108">Data Type</span></span></th>
<th><span data-ttu-id="55fcf-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="55fcf-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-111">datetime</span><span class="sxs-lookup"><span data-stu-id="55fcf-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="55fcf-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-112">Time of session request.</span></span> <span data-ttu-id="55fcf-113">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="55fcf-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fcf-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-116">int</span><span class="sxs-lookup"><span data-stu-id="55fcf-116">int</span></span></p></td>
<td><p><span data-ttu-id="55fcf-117">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-117">ID number to identify the session.</span></span> <span data-ttu-id="55fcf-118">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="55fcf-119">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fcf-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-121">datetime</span><span class="sxs-lookup"><span data-stu-id="55fcf-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="55fcf-p104">첫 번째 INVITE 요청의 시간입니다. 이 필드는 일반적으로 세션의 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 필드에 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="55fcf-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-127">회의의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-130">회의 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-130">Type of conference URI.</span></span> <span data-ttu-id="55fcf-131">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fcf-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-132"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-133">고유</span><span class="sxs-lookup"><span data-stu-id="55fcf-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="55fcf-p106">반복해서 수행되는 회의를 구분하는 식별자입니다. 반복되는 각 회의 인스턴스는 동일한 ConferenceURI를 갖지만 ConfInstance 값이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="55fcf-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-138">회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-141">회의 서버 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-141">Type of conferencing server URI.</span></span> <span data-ttu-id="55fcf-142">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fcf-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-143"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="55fcf-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-145">세션에 관련된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-146"><strong>Userurit<</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-148">세션에 속하는 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="55fcf-149">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fcf-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-150"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-152">세션에 속하는 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="55fcf-153">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55fcf-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-155">고유</span><span class="sxs-lookup"><span data-stu-id="55fcf-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="55fcf-156">세션에 속하는 사용자의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-158">datetime</span><span class="sxs-lookup"><span data-stu-id="55fcf-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="55fcf-159">세션의 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-162">회의 서버의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-164">int</span><span class="sxs-lookup"><span data-stu-id="55fcf-164">int</span></span></p></td>
<td><p><span data-ttu-id="55fcf-165">회의 서버의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-165">Type of conference server.</span></span> <span data-ttu-id="55fcf-166">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fcf-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="55fcf-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-169">회의 서버 범주입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-172">세션에 참가한 사용자가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-174">int</span><span class="sxs-lookup"><span data-stu-id="55fcf-174">int</span></span></p></td>
<td><p><span data-ttu-id="55fcf-175">세션에 참가한 사용자가 사용한 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="55fcf-176">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55fcf-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="55fcf-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-179">세션에 속하는 사용자가 사용한 클라이언트의 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="55fcf-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-182">세션을 대신 시작한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-185">세션을 대신 시작한 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="55fcf-186">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fcf-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-189">세션을 대신 시작한 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="55fcf-190">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55fcf-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="55fcf-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-193">세션을 참조한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-196">세션을 참조한 사용자 URI의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="55fcf-197">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fcf-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-200">세션을 참조한 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="55fcf-201">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55fcf-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="55fcf-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-p116">SIP 대화 ID입니다. 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="55fcf-206">:d ialog; from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="55fcf-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-208">datetime</span><span class="sxs-lookup"><span data-stu-id="55fcf-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="55fcf-209">현재 세션으로 교체된 대화를 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="55fcf-210">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fcf-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-212">int</span><span class="sxs-lookup"><span data-stu-id="55fcf-212">int</span></span></p></td>
<td><p><span data-ttu-id="55fcf-213">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-213">ID number to identify the session.</span></span> <span data-ttu-id="55fcf-214">ReplaceDialogIdTime과 함께 이 세션으로 교체된 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="55fcf-215">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="55fcf-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="55fcf-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-p119">세션이 교체하는 SIP 대화 ID입니다. 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="55fcf-220">대화 상자, from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="55fcf-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-222">비트만</span><span class="sxs-lookup"><span data-stu-id="55fcf-222">bit</span></span></p></td>
<td><p><span data-ttu-id="55fcf-223">세션이 회의 서버에서 시작되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-225">비트만</span><span class="sxs-lookup"><span data-stu-id="55fcf-225">bit</span></span></p></td>
<td><p><span data-ttu-id="55fcf-226">세션이 회의 서버에서 종료되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-228">비트만</span><span class="sxs-lookup"><span data-stu-id="55fcf-228">bit</span></span></p></td>
<td><p><span data-ttu-id="55fcf-229">사용자가 내부 네트워크에서 로그온했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-231">datetime</span><span class="sxs-lookup"><span data-stu-id="55fcf-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="55fcf-p120">첫 번째 INVITE 메시지에 대한 응답 시간입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-236">int</span><span class="sxs-lookup"><span data-stu-id="55fcf-236">int</span></span></p></td>
<td><p><span data-ttu-id="55fcf-p121">세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-241">int</span><span class="sxs-lookup"><span data-stu-id="55fcf-241">int</span></span></p></td>
<td><p><span data-ttu-id="55fcf-242">세션 SIP 헤더에서 캡처된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-245">세션의 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-246"><strong>프런트</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-248">세션에 대해 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-249"><strong>그룹</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-251">세션에 대해 데이터를 캡처한 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-254">세션에 참가한 사용자가 사용한 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-255"><strong>게이트웨이</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-257">세션에 참가한 사용자가 사용한 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="55fcf-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="55fcf-260">세션에 참가한 사용자가 사용한 에지 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="55fcf-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-262">smallint</span><span class="sxs-lookup"><span data-stu-id="55fcf-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="55fcf-p122">세션에 참가한 사용자의 특성을 나타냅니다. 허용된 특성 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="55fcf-265">0x01 - 데스크톱 전화와 통합됨</span><span class="sxs-lookup"><span data-stu-id="55fcf-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="55fcf-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="55fcf-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="55fcf-267">smallint</span><span class="sxs-lookup"><span data-stu-id="55fcf-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="55fcf-p123">통화 특성을 나타냅니다. 허용된 특성 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55fcf-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="55fcf-270">0x01 - 다시 시도된 세션0</span><span class="sxs-lookup"><span data-stu-id="55fcf-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="55fcf-271">x02 - 응답 그룹을 대신하여 에이전트가 시작한 통화</span><span class="sxs-lookup"><span data-stu-id="55fcf-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

