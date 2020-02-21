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
ms.openlocfilehash: 3e991f6240d9c21815299a3ef169c5824cf5ef3b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="15d15-102">Lync Server 2013의 ConferenceSessionDetails 테이블</span><span class="sxs-lookup"><span data-stu-id="15d15-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15d15-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="15d15-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="15d15-104">각 레코드는 Focus를 가진 세션이거나, 특정 회의 서버를 가진 세션일 수 있는 하나의 회의 세션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="15d15-105">열</span><span class="sxs-lookup"><span data-stu-id="15d15-105">Column</span></span></th>
<th><span data-ttu-id="15d15-106">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="15d15-106">Data Type</span></span></th>
<th><span data-ttu-id="15d15-107">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="15d15-107">Key/Index</span></span></th>
<th><span data-ttu-id="15d15-108">세부 정보</span><span class="sxs-lookup"><span data-stu-id="15d15-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="15d15-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-110">Datetime</span><span class="sxs-lookup"><span data-stu-id="15d15-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="15d15-111">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="15d15-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-112">세션 요청 시간 <strong>Sessionidseq</strong> 와 함께 사용 되어 회의 세션을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="15d15-113">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-115">int</span><span class="sxs-lookup"><span data-stu-id="15d15-115">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-116">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="15d15-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-117">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-117">ID number to identify the session.</span></span> <span data-ttu-id="15d15-118">회의 세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="15d15-119">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-121">int</span><span class="sxs-lookup"><span data-stu-id="15d15-121">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-122">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-123">이 세션과 관련된 회의 센터 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="15d15-124">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="15d15-125">이 URI는 회의 센터 기반 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-126"><strong>인스턴스</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-127">고유</span><span class="sxs-lookup"><span data-stu-id="15d15-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-128">되풀이 회의 인스턴스 간에 구별하기 위한 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="15d15-129">각 되풀이 회의 인스턴스는 ConferenceURI 값이 같지만 ConfInstance 값은 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="15d15-130">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-132">int</span><span class="sxs-lookup"><span data-stu-id="15d15-132">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-133">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-134">이 세션과 관련된 회의 서버 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="15d15-135">자세한 내용은 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013의 ConferenceUris 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="15d15-136">이 URI는 회의 서버 기반 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="15d15-137">회의 센터 회의 세션의 경우 이 열은 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-139">int</span><span class="sxs-lookup"><span data-stu-id="15d15-139">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-140">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-141">회의 세션에 있는 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-141">ID of one user in the conference session.</span></span> <span data-ttu-id="15d15-142">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-144">고유</span><span class="sxs-lookup"><span data-stu-id="15d15-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-p107">끝점 인스턴스를 식별하기 위한 GUID입니다. 예를 들어 한 사용자가 동일 계정을 사용하여 여러 컴퓨터에 로그온하면 각 컴퓨터가 서로 다른 끝점 ID를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-148">int</span><span class="sxs-lookup"><span data-stu-id="15d15-148">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-149">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-150">발신자가 역할을 대신 수행하고 있는 원래 사용자의 ID를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="15d15-151">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-153">int</span><span class="sxs-lookup"><span data-stu-id="15d15-153">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-154">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-155">통화를 참조한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="15d15-156">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-158">int</span><span class="sxs-lookup"><span data-stu-id="15d15-158">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-159">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-160">회의 사용자가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-160">Client version used by the conference user.</span></span> <span data-ttu-id="15d15-161">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15d15-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-162"><strong>에이 Client합니다.</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-163">int</span><span class="sxs-lookup"><span data-stu-id="15d15-163">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-164">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-165">회의 서버가 사용한 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-165">Client version used by the conference server.</span></span> <span data-ttu-id="15d15-166">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15d15-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-168">datetime</span><span class="sxs-lookup"><span data-stu-id="15d15-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="15d15-169">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-170">현재 세션으로 교체된 대화를 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="15d15-171">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-173">int</span><span class="sxs-lookup"><span data-stu-id="15d15-173">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-174">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-175">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-175">ID number to identify the session.</span></span> <span data-ttu-id="15d15-176"><strong>ReplacesDialogIdTime</strong>과 함께 이 세션으로 교체된 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="15d15-177">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-179">비트만</span><span class="sxs-lookup"><span data-stu-id="15d15-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-180">세션이 회의 서버에서 시작되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-182">비트만</span><span class="sxs-lookup"><span data-stu-id="15d15-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-183">세션이 회의 서버에서 종료되었는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-185">비트만</span><span class="sxs-lookup"><span data-stu-id="15d15-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-186">사용자가 내부로부터 로그온되었는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-188">int</span><span class="sxs-lookup"><span data-stu-id="15d15-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-189">세션 초대에 대한 SIP(Session Initiation Protocol) 응답 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="15d15-190">이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="15d15-191">INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-193">int</span><span class="sxs-lookup"><span data-stu-id="15d15-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-194">SIP 헤더에서 캡처된 진단 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-196">int</span><span class="sxs-lookup"><span data-stu-id="15d15-196">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-197">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-198">이 세션에 사용된 프런트 엔드 서버의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="15d15-199">자세한 내용은 <a href="lync-server-2013-servers-table.md">Lync Server 2013의 Servers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-201">int</span><span class="sxs-lookup"><span data-stu-id="15d15-201">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-202">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-203">세션이 캡처된 풀의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="15d15-204">자세한 내용은 <a href="lync-server-2013-pools-table.md">Lync Server 2013의 풀 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15d15-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-206">int</span><span class="sxs-lookup"><span data-stu-id="15d15-206">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-207">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-208">통화를 사용 중인 중재 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="15d15-209">자세한 내용은 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013에서 Mediationservers 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-211">int</span><span class="sxs-lookup"><span data-stu-id="15d15-211">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-212">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-213">통화를 사용 중인 게이트웨이입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-213">The gateway the call is using.</span></span> <span data-ttu-id="15d15-214">자세한 내용은 <a href="lync-server-2013-gateways-table.md">Lync Server 2013의 게이트웨이 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-216">int</span><span class="sxs-lookup"><span data-stu-id="15d15-216">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-217">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-218">통화를 사용 중인 에지 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-218">The Edge Server the call is using.</span></span> <span data-ttu-id="15d15-219">자세한 내용은 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013의 EdgeServers 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15d15-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-221">int</span><span class="sxs-lookup"><span data-stu-id="15d15-221">int</span></span></p></td>
<td><p><span data-ttu-id="15d15-222">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-223">세션에 사용된 콘텐츠 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-223">Content type used in the session.</span></span> <span data-ttu-id="15d15-224">자세한 내용은 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013의 Contenttypes 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="15d15-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-226">datetime</span><span class="sxs-lookup"><span data-stu-id="15d15-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-p121">첫 번째 INVITE 요청 시간입니다. 이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 이 필드가 첫 번째 해당 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜와 시간으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-231">datetime</span><span class="sxs-lookup"><span data-stu-id="15d15-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-232">첫 번째 SIP RESPONSE 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="15d15-233">이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="15d15-234">INVITE 메시지가 없으면 이 필드가 첫 번째 해당 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜와 시간으로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-236">datetime</span><span class="sxs-lookup"><span data-stu-id="15d15-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-237">세션이 종료된 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="15d15-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="15d15-240">외부</span><span class="sxs-lookup"><span data-stu-id="15d15-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="15d15-241"><a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a>에 있는 MCU URI 유형 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="15d15-242">이 필드는 쿼리 성능을 높이기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="15d15-243">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="15d15-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-245">smallint</span><span class="sxs-lookup"><span data-stu-id="15d15-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-p124">사용자 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="15d15-248">일반 전화기와 통합됨 - 1</span><span class="sxs-lookup"><span data-stu-id="15d15-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="15d15-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="15d15-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="15d15-250">smallint</span><span class="sxs-lookup"><span data-stu-id="15d15-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="15d15-p125">통화 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="15d15-253">다시 시도된 세션 - 1</span><span class="sxs-lookup"><span data-stu-id="15d15-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="15d15-254">\*대부분의 세션에서 SessionIdSeq는 값 1을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="15d15-255">여러 세션이 정확히 동시에 시작될 경우 한 세션에 대한 SessionIdSeq가 1이 되고 다른 세션에 대해서는 2, 3, 4의 순서로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="15d15-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

