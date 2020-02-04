---
title: 'Lync Server 2013: ConferenceSessionDetails view'
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
ms.openlocfilehash: 46356099c3eee20794a4198720597dc4395b563f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="1dde4-102">Lync Server 2013의 ConferenceSessionDetails 보기</span><span class="sxs-lookup"><span data-stu-id="1dde4-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1dde4-103">_**마지막으로 수정한 주제:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="1dde4-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="1dde4-104">ConferenceSessionDetails 보기는 단체 세션에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="1dde4-105">각 레코드는 하나의 회의 세션을 나타내며,이는 포커스가 있는 세션 또는 특정 회의 서버 세션 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="1dde4-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1dde4-107">열</span><span class="sxs-lookup"><span data-stu-id="1dde4-107">Column</span></span></th>
<th><span data-ttu-id="1dde4-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1dde4-108">Data Type</span></span></th>
<th><span data-ttu-id="1dde4-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="1dde4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="1dde4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dde4-112">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-112">Time of session request.</span></span> <span data-ttu-id="1dde4-113">세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="1dde4-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-116">int</span><span class="sxs-lookup"><span data-stu-id="1dde4-116">int</span></span></p></td>
<td><p><span data-ttu-id="1dde4-117">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-117">ID number to identify the session.</span></span> <span data-ttu-id="1dde4-118">세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="1dde4-119">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-121">dmtf</span><span class="sxs-lookup"><span data-stu-id="1dde4-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dde4-122">첫 번째 초대 요청의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-122">Time of the first INVITE request.</span></span> <span data-ttu-id="1dde4-123">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="1dde4-124">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dde4-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-127">회의의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-130">회의 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-130">Type of conference URI.</span></span> <span data-ttu-id="1dde4-131">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-132"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="1dde4-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1dde4-134">되풀이 회의의 인스턴스를 구별 하는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="1dde4-135">각 되풀이 회의 인스턴스에는 동일한 ConferenceURI 있지만 다른 지 인 인스턴스 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dde4-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-138">회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-141">회의 서버 URI의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-141">Type of conferencing server URI.</span></span> <span data-ttu-id="1dde4-142">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dde4-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-145">세션과 관련 된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-148">세션의 일부인 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="1dde4-149">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-150"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-151">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-152">세션에 참가 하 고 있던 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="1dde4-153">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="1dde4-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1dde4-156">세션의 일부인 사용자의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-158">dmtf</span><span class="sxs-lookup"><span data-stu-id="1dde4-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dde4-159">세션 종료 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-161">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-162">컨퍼런스 서버의 버전.</span><span class="sxs-lookup"><span data-stu-id="1dde4-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-164">int</span><span class="sxs-lookup"><span data-stu-id="1dde4-164">int</span></span></p></td>
<td><p><span data-ttu-id="1dde4-165">회의 서버의 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-165">Type of conference server.</span></span> <span data-ttu-id="1dde4-166">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1dde4-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-169">회의 서버 범주.</span><span class="sxs-lookup"><span data-stu-id="1dde4-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-171">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-172">세션에 참가 한 사용자가 사용 하는 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-174">int</span><span class="sxs-lookup"><span data-stu-id="1dde4-174">int</span></span></p></td>
<td><p><span data-ttu-id="1dde4-175">세션에 참가 한 사용자가 사용 하는 클라이언트</span><span class="sxs-lookup"><span data-stu-id="1dde4-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="1dde4-176">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1dde4-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-179">세션에 참가 한 사용자가 사용 하는 클라이언트 범주의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dde4-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-182">해당 세션이 시작 된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-184">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-185">세션이 시작 된 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="1dde4-186">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-188">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-189">세션이 시작 된 사용자를 대신해 서의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="1dde4-190">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1dde4-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-193">세션을 참조 한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-196">세션을 참조 한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="1dde4-197">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-200">세션을 참조 한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="1dde4-201">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="1dde4-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-204">SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-204">SIP dialog ID.</span></span> <span data-ttu-id="1dde4-205">형식은</span><span class="sxs-lookup"><span data-stu-id="1dde4-205">The format is</span></span></p>
<p><span data-ttu-id="1dde4-206">:d ialog; from 태그; to 태그</span><span class="sxs-lookup"><span data-stu-id="1dde4-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-208">dmtf</span><span class="sxs-lookup"><span data-stu-id="1dde4-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dde4-209">현재 세션으로 대체 된 대화 상자를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="1dde4-210">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-212">int</span><span class="sxs-lookup"><span data-stu-id="1dde4-212">int</span></span></p></td>
<td><p><span data-ttu-id="1dde4-213">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-213">ID number to identify the session.</span></span> <span data-ttu-id="1dde4-214">ReplaceDialogIdTime와 함께 사용 하 여이 세션으로 대체 되는 세션을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="1dde4-215">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1dde4-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="1dde4-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-218">세션에서 대체 하는 SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="1dde4-219">의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-219">The format of the is:</span></span></p>
<p><span data-ttu-id="1dde4-220">대화 상자; from 태그; 태그</span><span class="sxs-lookup"><span data-stu-id="1dde4-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-222">다소</span><span class="sxs-lookup"><span data-stu-id="1dde4-222">bit</span></span></p></td>
<td><p><span data-ttu-id="1dde4-223">회의 서버에 의해 세션이 시작 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-224"><strong>Isen이상 By참여 서버</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-225">다소</span><span class="sxs-lookup"><span data-stu-id="1dde4-225">bit</span></span></p></td>
<td><p><span data-ttu-id="1dde4-226">회의 서버에 의해 세션이 종료 되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-228">다소</span><span class="sxs-lookup"><span data-stu-id="1dde4-228">bit</span></span></p></td>
<td><p><span data-ttu-id="1dde4-229">사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-231">dmtf</span><span class="sxs-lookup"><span data-stu-id="1dde4-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="1dde4-232">첫 번째 초대 메시지에 대 한 응답 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="1dde4-233">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="1dde4-234">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-236">int</span><span class="sxs-lookup"><span data-stu-id="1dde4-236">int</span></span></p></td>
<td><p><span data-ttu-id="1dde4-237">세션 초대에 대 한 SIP 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="1dde4-238">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="1dde4-239">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-241">int</span><span class="sxs-lookup"><span data-stu-id="1dde4-241">int</span></span></p></td>
<td><p><span data-ttu-id="1dde4-242">세션 SIP 헤더에서 진단 ID를 캡처 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-244">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-245">세션의 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-247">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-248">세션에 대 한 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-249"><strong>풀</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-250">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-251">세션에 대 한 데이터를 캡처한 풀의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-253">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-254">세션에 참가 한 사용자가 사용 하는 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-255"><strong>게이트웨이와</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-256">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-257">세션에 참가 한 사용자가 사용 하는 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="1dde4-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-259">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1dde4-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1dde4-260">세션에 참가 한 사용자가 사용 하는 Edge 서버의 FQDN입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1dde4-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-262">smallint</span><span class="sxs-lookup"><span data-stu-id="1dde4-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="1dde4-263">세션에 참가 한 사용자의 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="1dde4-264">허용 되는 특성 정의는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="1dde4-265">0x01-데스크톱 전화와 통합</span><span class="sxs-lookup"><span data-stu-id="1dde4-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1dde4-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="1dde4-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="1dde4-267">smallint</span><span class="sxs-lookup"><span data-stu-id="1dde4-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="1dde4-268">통화 특성을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-268">Indicates the call attributes.</span></span> <span data-ttu-id="1dde4-269">다음과 같은 특성 정의가 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="1dde4-270">0x01-재시도 Session0</span><span class="sxs-lookup"><span data-stu-id="1dde4-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="1dde4-271">x02-응답 그룹을 대신 하 여 상담원이 수행한 통화입니다.</span><span class="sxs-lookup"><span data-stu-id="1dde4-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

