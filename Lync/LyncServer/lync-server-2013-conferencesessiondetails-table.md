---
title: 'Lync Server 2013: ConferenceSessionDetails 테이블'
description: 'Lync Server 2013: ConferenceSessionDetails 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566784"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="3aa2a-103">Lync Server 2013의 ConferenceSessionDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="3aa2a-103">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3aa2a-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3aa2a-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3aa2a-105">각 레코드는 Focus를 가진 세션이거나, 특정 회의 서버를 가진 세션일 수 있는 하나의 회의 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3aa2a-106">열</span><span class="sxs-lookup"><span data-stu-id="3aa2a-106">Column</span></span></th>
<th><span data-ttu-id="3aa2a-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3aa2a-107">Data Type</span></span></th>
<th><span data-ttu-id="3aa2a-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="3aa2a-108">Key/Index</span></span></th>
<th><span data-ttu-id="3aa2a-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="3aa2a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-111">Datetime</span><span class="sxs-lookup"><span data-stu-id="3aa2a-111">Datetime</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-112">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="3aa2a-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-113">세션 요청 시간 <strong>Sessionidseq</strong> 와 함께 사용 되어 회의 세션을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-113">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="3aa2a-114">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-116">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-116">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-117">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="3aa2a-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-118">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-118">ID number to identify the session.</span></span> <span data-ttu-id="3aa2a-119">회의 세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="3aa2a-120">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-121"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-121"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-122">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-122">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-123">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-124">이 세션과 관련된 회의 센터 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-124">Focus conference URI related to this session.</span></span> <span data-ttu-id="3aa2a-125">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-125">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="3aa2a-126">이 URI는 회의 센터 기반 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-126">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-127"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-128">고유</span><span class="sxs-lookup"><span data-stu-id="3aa2a-128">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-129">되풀이 회의 인스턴스 간에 구별하기 위한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-129">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="3aa2a-130">각 되풀이 회의 인스턴스는 ConferenceURI 값이 같지만 ConfInstance 값은 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-130">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="3aa2a-131">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-131">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-132"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-132"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-133">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-133">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-134">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-134">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-135">이 세션과 관련된 회의 서버 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-135">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="3aa2a-136">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-136">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="3aa2a-137">이 URI는 회의 서버 기반 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-137">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="3aa2a-138">회의 센터 회의 세션의 경우 이 열은 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-138">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-139"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-139"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-140">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-140">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-141">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-142">회의 세션에 있는 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-142">ID of one user in the conference session.</span></span> <span data-ttu-id="3aa2a-143">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-144"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-144"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-145">고유</span><span class="sxs-lookup"><span data-stu-id="3aa2a-145">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-p107">끝점 인스턴스를 식별하기 위한 GUID입니다. 예를 들어 한 사용자가 동일 계정을 사용하여 여러 컴퓨터에 로그온하면 각 컴퓨터가 서로 다른 끝점 ID를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-148"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-148"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-149">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-149">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-150">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-151">발신자가 역할을 대신 수행하고 있는 원래 사용자의 ID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-151">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="3aa2a-152">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-152">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-153"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-153"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-154">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-154">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-155">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-156">통화를 참조한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-156">ID of the user by who the call is referred.</span></span> <span data-ttu-id="3aa2a-157">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-158"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-158"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-159">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-159">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-160">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-161">회의 사용자가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-161">Client version used by the conference user.</span></span> <span data-ttu-id="3aa2a-162">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-163"><strong>에이 Client합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-163"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-164">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-164">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-165">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-166">회의 서버가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-166">Client version used by the conference server.</span></span> <span data-ttu-id="3aa2a-167">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-167">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-168"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-168"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-169">datetime</span><span class="sxs-lookup"><span data-stu-id="3aa2a-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-170">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-171">현재 세션으로 교체된 대화를 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-171">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="3aa2a-172">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-172">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-173"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-173"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-174">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-174">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-175">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-175">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-176">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-176">ID number to identify the session.</span></span> <span data-ttu-id="3aa2a-177"><strong>ReplacesDialogIdTime</strong>과 함께 이 세션으로 교체된 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-177">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="3aa2a-178">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-178">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-179"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-179"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-180">비트만</span><span class="sxs-lookup"><span data-stu-id="3aa2a-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-181">세션이 회의 서버에서 시작되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-181">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-182"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-182"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-183">비트만</span><span class="sxs-lookup"><span data-stu-id="3aa2a-183">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-184">세션이 회의 서버에서 종료되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-184">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-185"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-185"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-186">비트만</span><span class="sxs-lookup"><span data-stu-id="3aa2a-186">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-187">사용자가 내부로부터 로그온되었는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-187">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-188"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-188"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-189">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-189">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-190">세션 초대에 대한 SIP(Session Initiation Protocol) 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-190">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="3aa2a-191">이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-191">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="3aa2a-192">INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-192">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-193"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-193"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-194">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-194">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-195">SIP 헤더에서 캡처된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-195">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-196"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-196"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-197">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-197">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-198">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-199">이 세션에 사용된 프런트 엔드 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-199">ID of the front-end server used for this session.</span></span> <span data-ttu-id="3aa2a-200">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-200">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-201"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-201"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-202">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-202">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-203">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-203">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-204">세션이 캡처된 풀의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-204">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="3aa2a-205">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-205">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-206"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-206"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-207">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-207">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-208">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-208">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-209">통화를 사용 중인 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-209">The Mediation Server the call is using.</span></span> <span data-ttu-id="3aa2a-210">자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013에서 Mediationservers 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-210">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-211"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-211"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-212">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-212">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-213">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-213">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-214">통화를 사용 중인 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-214">The gateway the call is using.</span></span> <span data-ttu-id="3aa2a-215">자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-215">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-216"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-216"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-217">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-217">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-218">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-219">통화를 사용 중인 에지 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-219">The Edge Server the call is using.</span></span> <span data-ttu-id="3aa2a-220">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-220">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-221"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-221"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-222">int</span><span class="sxs-lookup"><span data-stu-id="3aa2a-222">int</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-223">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-223">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-224">세션에 사용된 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-224">Content type used in the session.</span></span> <span data-ttu-id="3aa2a-225">자세한 내용은 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 Contenttypes 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-225">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-226"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-226"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-227">datetime</span><span class="sxs-lookup"><span data-stu-id="3aa2a-227">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-p121">첫 번째 INVITE 요청 시간입니다. 이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 이 필드가 첫 번째 해당 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜와 시간으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-232">datetime</span><span class="sxs-lookup"><span data-stu-id="3aa2a-232">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-233">첫 번째 SIP RESPONSE 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-233">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="3aa2a-234">이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-234">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="3aa2a-235">INVITE 메시지가 없으면 이 필드가 첫 번째 해당 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜와 시간으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-235">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-236"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-236"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-237">datetime</span><span class="sxs-lookup"><span data-stu-id="3aa2a-237">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-238">세션이 종료된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-238">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-239"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-239"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-240">tinyint</span><span class="sxs-lookup"><span data-stu-id="3aa2a-240">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-241">외부</span><span class="sxs-lookup"><span data-stu-id="3aa2a-241">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3aa2a-242"><a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a>에 있는 MCU URI 유형 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-242">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="3aa2a-243">이 필드는 쿼리 성능을 높이기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-243">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="3aa2a-244">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-244">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aa2a-245"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-245"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-246">smallint</span><span class="sxs-lookup"><span data-stu-id="3aa2a-246">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-p124">사용자 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="3aa2a-249">일반 전화기와 통합됨 - 1</span><span class="sxs-lookup"><span data-stu-id="3aa2a-249">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aa2a-250"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="3aa2a-250"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="3aa2a-251">smallint</span><span class="sxs-lookup"><span data-stu-id="3aa2a-251">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3aa2a-p125">통화 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="3aa2a-254">다시 시도된 세션 - 1</span><span class="sxs-lookup"><span data-stu-id="3aa2a-254">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3aa2a-255">\* 대부분의 세션에서 SessionIdSeq는 값 1을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-255">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="3aa2a-256">여러 세션이 정확히 동시에 시작될 경우 한 세션에 대한 SessionIdSeq가 1이 되고 다른 세션에 대해서는 2, 3, 4의 순서로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="3aa2a-256">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

