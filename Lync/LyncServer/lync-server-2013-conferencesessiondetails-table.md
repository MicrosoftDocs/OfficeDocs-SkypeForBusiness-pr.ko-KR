---
title: 'Lync Server 2013: ConferenceSessionDetails 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c5aaa3ec022be18ad54cc8a24b8410c23faf799
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="dd9ba-102">Lync Server 2013의 ConferenceSessionDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="dd9ba-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd9ba-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="dd9ba-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="dd9ba-104">각 레코드는 하나의 회의 세션을 나타내며,이는 포커스가 있는 세션 또는 특정 회의 서버 세션 중 하나가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd9ba-105">열</span><span class="sxs-lookup"><span data-stu-id="dd9ba-105">Column</span></span></th>
<th><span data-ttu-id="dd9ba-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="dd9ba-106">Data Type</span></span></th>
<th><span data-ttu-id="dd9ba-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="dd9ba-107">Key/Index</span></span></th>
<th><span data-ttu-id="dd9ba-108">세부적인</span><span class="sxs-lookup"><span data-stu-id="dd9ba-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-110">Dmtf</span><span class="sxs-lookup"><span data-stu-id="dd9ba-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-111">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="dd9ba-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-112">세션 요청 시간 회의 세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="dd9ba-113">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-115">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-115">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-116">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="dd9ba-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-117">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-117">ID number to identify the session.</span></span> <span data-ttu-id="dd9ba-118">회의 세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="dd9ba-119">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-121">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-121">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-122">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-123">이 세션과 관련 된 포커스 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="dd9ba-124">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="dd9ba-125">이 URI는 포커스 기반 전화 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-126"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-127">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="dd9ba-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-128">되풀이 회의의 인스턴스를 구별 하는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="dd9ba-129">각 되풀이 회의 인스턴스에는 동일한 ConferenceURI 있지만 다른 지 인 인스턴스 값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="dd9ba-130">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-132">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-132">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-133">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-134">이 세션과 관련 된 회의 서버 컨퍼런스 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="dd9ba-135">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="dd9ba-136">이 URI는 회의 서버 기반 전화 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="dd9ba-137">포커스 회의 세션의 경우이 열은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-139">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-139">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-140">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-141">회의 세션의 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-141">ID of one user in the conference session.</span></span> <span data-ttu-id="dd9ba-142">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-144">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="dd9ba-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-145">끝점의 인스턴스를 식별 하는 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="dd9ba-146">예를 들어 한 사용자가 동일한 계정을 사용 하 여 다른 컴퓨터에 로그온 하는 경우 각 컴퓨터에는 서로 다른 끝점 ID가 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-148">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-148">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-149">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-150">호출자가 대신 하는 사용자의 ID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="dd9ba-151">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-153">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-153">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-154">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-155">통화를 참조 하는 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="dd9ba-156">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-158">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-158">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-159">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-160">컨퍼런스 사용자가 클라이언트 버전을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-160">Client version used by the conference user.</span></span> <span data-ttu-id="dd9ba-161">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-162"><strong>해당 클라이언트</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-163">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-163">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-164">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-165">회의 서버에서 사용 하는 클라이언트 버전.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-165">Client version used by the conference server.</span></span> <span data-ttu-id="dd9ba-166">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-168">dmtf</span><span class="sxs-lookup"><span data-stu-id="dd9ba-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-169">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-170">현재 세션으로 대체 된 대화 상자를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="dd9ba-171">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-173">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-173">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-174">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-175">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-175">ID number to identify the session.</span></span> <span data-ttu-id="dd9ba-176"><strong>ReplacesDialogIdTime</strong> 와 함께 사용 하 여이 세션으로 대체 되는 세션을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="dd9ba-177">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-179">다소</span><span class="sxs-lookup"><span data-stu-id="dd9ba-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-180">회의 서버에서 세션을 시작 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-181"><strong>Isen이상 By참여 서버</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-182">다소</span><span class="sxs-lookup"><span data-stu-id="dd9ba-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-183">회의 서버에서 세션을 종료 했음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-185">다소</span><span class="sxs-lookup"><span data-stu-id="dd9ba-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-186">사용자가 내부에서 로그온 되었는지 여부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-188">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-189">세션 초대에 대 한 SIP (세션 초기화 프로토콜) 응답 코드</span><span class="sxs-lookup"><span data-stu-id="dd9ba-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="dd9ba-190">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dd9ba-191">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-193">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-194">SIP 헤더에서 진단 ID를 캡처 했습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-196">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-196">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-197">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-198">이 세션에 사용 되는 프런트 엔드 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="dd9ba-199">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 서버 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-201">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-201">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-202">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-203">세션이 캡처된 풀의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="dd9ba-204">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-206">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-206">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-207">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-208">통화에서 사용 중인 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="dd9ba-209">자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013의 Mediationservers 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-211">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-211">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-212">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-213">통화에서 사용 중인 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="dd9ba-213">The gateway the call is using.</span></span> <span data-ttu-id="dd9ba-214">자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-216">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-216">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-217">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-218">통화에서 사용 중인 Edge 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-218">The Edge Server the call is using.</span></span> <span data-ttu-id="dd9ba-219">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-221">int</span><span class="sxs-lookup"><span data-stu-id="dd9ba-221">int</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-222">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-223">세션에 사용 되는 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-223">Content type used in the session.</span></span> <span data-ttu-id="dd9ba-224">자세한 내용은 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 Contenttypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-226">dmtf</span><span class="sxs-lookup"><span data-stu-id="dd9ba-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-227">첫 번째 초대 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-227">The time of the first INVITE request.</span></span> <span data-ttu-id="dd9ba-228">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dd9ba-229">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-231">dmtf</span><span class="sxs-lookup"><span data-stu-id="dd9ba-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-232">첫 번째 SIP 응답의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="dd9ba-233">일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="dd9ba-234">초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-236">dmtf</span><span class="sxs-lookup"><span data-stu-id="dd9ba-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-237">세션이 종료 된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="dd9ba-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-240">외부</span><span class="sxs-lookup"><span data-stu-id="dd9ba-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dd9ba-241"><a href="lync-server-2013-uritypes-table.md">Lync Server 2013에서 UriTypes 테이블</a>의 MCU URI 유형 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="dd9ba-242">이 필드는 쿼리 성능을 개선 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="dd9ba-243">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9ba-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-245">smallint</span><span class="sxs-lookup"><span data-stu-id="dd9ba-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-246">사용자 특성을 나타내는 비트 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="dd9ba-247">다음과 같은 특성 정의가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="dd9ba-248">데스크톱 전화번호와 통합-1</span><span class="sxs-lookup"><span data-stu-id="dd9ba-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9ba-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="dd9ba-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9ba-250">smallint</span><span class="sxs-lookup"><span data-stu-id="dd9ba-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dd9ba-251">통화 특성을 나타내는 비트 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-251">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="dd9ba-252">다음과 같은 특성 정의가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-252">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="dd9ba-253">다시 시도 된 세션-1</span><span class="sxs-lookup"><span data-stu-id="dd9ba-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dd9ba-254">\*대부분의 세션에서 SessionIdSeq에는 값 1이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="dd9ba-255">정확히 동시에 여러 세션을 시작 하는 경우 1에 대 한 SessionIdSeq는 1이 되 고 다른 하나는 2가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dd9ba-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

