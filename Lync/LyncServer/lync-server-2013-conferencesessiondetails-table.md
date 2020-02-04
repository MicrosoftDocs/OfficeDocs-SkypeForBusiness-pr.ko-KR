---
title: 'Lync Server 2013: ConferenceSessionDetails 테이블'
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
ms.openlocfilehash: 61da586f3ecaf215b3bb636a80141ba8aaa19f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="9397f-102">Lync Server 2013의 ConferenceSessionDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="9397f-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9397f-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="9397f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="9397f-104">각 레코드는 하나의 회의 세션을 나타내며,이는 포커스가 있는 세션 또는 특정 회의 서버 세션 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9397f-105">열</span><span class="sxs-lookup"><span data-stu-id="9397f-105">Column</span></span></th>
<th><span data-ttu-id="9397f-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="9397f-106">Data Type</span></span></th>
<th><span data-ttu-id="9397f-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="9397f-107">Key/Index</span></span></th>
<th><span data-ttu-id="9397f-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="9397f-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9397f-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-110">Dmtf</span><span class="sxs-lookup"><span data-stu-id="9397f-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="9397f-111">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="9397f-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-112">세션 요청 시간 회의 세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="9397f-113">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-115">int</span><span class="sxs-lookup"><span data-stu-id="9397f-115">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-116">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="9397f-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-117">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-117">ID number to identify the session.</span></span> <span data-ttu-id="9397f-118">회의 세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="9397f-119">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-121">int</span><span class="sxs-lookup"><span data-stu-id="9397f-121">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-122">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-123">이 세션과 관련 된 포커스 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="9397f-124">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="9397f-125">이 URI는 포커스 기반 전화 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-126"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-127">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="9397f-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-128">되풀이 회의의 인스턴스를 구별 하는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="9397f-129">각 되풀이 회의 인스턴스에는 동일한 ConferenceURI 있지만 다른 지 인 인스턴스 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="9397f-130">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-132">int</span><span class="sxs-lookup"><span data-stu-id="9397f-132">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-133">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-134">이 세션과 관련 된 회의 서버 컨퍼런스 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="9397f-135">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="9397f-136">이 URI는 회의 서버 기반 전화 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="9397f-137">포커스 회의 세션의 경우이 열은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-139">int</span><span class="sxs-lookup"><span data-stu-id="9397f-139">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-140">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-141">회의 세션의 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-141">ID of one user in the conference session.</span></span> <span data-ttu-id="9397f-142">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-144">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9397f-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-145">끝점의 인스턴스를 식별 하는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="9397f-146">예를 들어 한 사용자가 동일한 계정을 사용 하 여 다른 컴퓨터에 로그온 하는 경우 각 컴퓨터에는 서로 다른 끝점 ID가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-148">int</span><span class="sxs-lookup"><span data-stu-id="9397f-148">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-149">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-150">호출자가 대신 하는 사용자의 ID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="9397f-151">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-153">int</span><span class="sxs-lookup"><span data-stu-id="9397f-153">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-154">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-155">통화를 참조 하는 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="9397f-156">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-158">int</span><span class="sxs-lookup"><span data-stu-id="9397f-158">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-159">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-160">컨퍼런스 사용자가 클라이언트 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-160">Client version used by the conference user.</span></span> <span data-ttu-id="9397f-161">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-162"><strong>해당 클라이언트</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-163">int</span><span class="sxs-lookup"><span data-stu-id="9397f-163">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-164">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-165">회의 서버에서 사용 하는 클라이언트 버전.</span><span class="sxs-lookup"><span data-stu-id="9397f-165">Client version used by the conference server.</span></span> <span data-ttu-id="9397f-166">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-168">dmtf</span><span class="sxs-lookup"><span data-stu-id="9397f-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="9397f-169">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-170">현재 세션으로 대체 된 대화 상자를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="9397f-171">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-173">int</span><span class="sxs-lookup"><span data-stu-id="9397f-173">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-174">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-175">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-175">ID number to identify the session.</span></span> <span data-ttu-id="9397f-176"><strong>ReplacesDialogIdTime</strong> 와 함께 사용 하 여이 세션으로 대체 되는 세션을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="9397f-177">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-179">다소</span><span class="sxs-lookup"><span data-stu-id="9397f-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-180">회의 서버에서 세션을 시작 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-181"><strong>Isen이상 By참여 서버</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-182">다소</span><span class="sxs-lookup"><span data-stu-id="9397f-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-183">회의 서버에서 세션을 종료 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-185">다소</span><span class="sxs-lookup"><span data-stu-id="9397f-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-186">사용자가 내부에서 로그온 되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="9397f-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-188">int</span><span class="sxs-lookup"><span data-stu-id="9397f-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-189">세션 초대에 대 한 SIP (세션 초기화 프로토콜) 응답 코드</span><span class="sxs-lookup"><span data-stu-id="9397f-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="9397f-190">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9397f-191">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-193">int</span><span class="sxs-lookup"><span data-stu-id="9397f-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-194">SIP 헤더에서 진단 ID를 캡처 했습니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-196">int</span><span class="sxs-lookup"><span data-stu-id="9397f-196">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-197">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-198">이 세션에 사용 되는 프런트 엔드 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="9397f-199">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 서버 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-201">int</span><span class="sxs-lookup"><span data-stu-id="9397f-201">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-202">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-203">세션이 캡처된 풀의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="9397f-204">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-206">int</span><span class="sxs-lookup"><span data-stu-id="9397f-206">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-207">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-208">통화에서 사용 중인 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="9397f-209">자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 Mediationservers 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-211">int</span><span class="sxs-lookup"><span data-stu-id="9397f-211">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-212">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-213">통화에서 사용 중인 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="9397f-213">The gateway the call is using.</span></span> <span data-ttu-id="9397f-214">자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-216">int</span><span class="sxs-lookup"><span data-stu-id="9397f-216">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-217">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-218">통화에서 사용 중인 Edge 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-218">The Edge Server the call is using.</span></span> <span data-ttu-id="9397f-219">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-221">int</span><span class="sxs-lookup"><span data-stu-id="9397f-221">int</span></span></p></td>
<td><p><span data-ttu-id="9397f-222">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-223">세션에 사용 되는 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-223">Content type used in the session.</span></span> <span data-ttu-id="9397f-224">자세한 내용은 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 Contenttypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9397f-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-226">dmtf</span><span class="sxs-lookup"><span data-stu-id="9397f-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-227">첫 번째 초대 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-227">The time of the first INVITE request.</span></span> <span data-ttu-id="9397f-228">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9397f-229">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-231">dmtf</span><span class="sxs-lookup"><span data-stu-id="9397f-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-232">첫 번째 SIP 응답의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="9397f-233">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9397f-234">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-236">dmtf</span><span class="sxs-lookup"><span data-stu-id="9397f-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-237">세션이 종료 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="9397f-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9397f-240">외부</span><span class="sxs-lookup"><span data-stu-id="9397f-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="9397f-241"><a href="lync-server-2013-uritypes-table.md">Lync Server 2013에서 UriTypes 테이블</a>의 MCU URI 유형 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="9397f-242">이 필드는 쿼리 성능을 개선 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="9397f-243">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9397f-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-245">smallint</span><span class="sxs-lookup"><span data-stu-id="9397f-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-246">사용자 특성을 나타내는 비트 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="9397f-247">다음과 같은 특성 정의가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="9397f-248">데스크톱 전화번호와 통합-1</span><span class="sxs-lookup"><span data-stu-id="9397f-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9397f-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9397f-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9397f-250">smallint</span><span class="sxs-lookup"><span data-stu-id="9397f-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9397f-251">통화 특성을 나타내는 비트 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-251">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="9397f-252">다음과 같은 특성 정의가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-252">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="9397f-253">다시 시도 된 세션-1</span><span class="sxs-lookup"><span data-stu-id="9397f-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="9397f-254">\*대부분의 세션에서 SessionIdSeq에는 값 1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="9397f-255">정확히 동시에 여러 세션을 시작 하는 경우 1에 대 한 SessionIdSeq는 1이 되 고 다른 하나는 2가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9397f-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

