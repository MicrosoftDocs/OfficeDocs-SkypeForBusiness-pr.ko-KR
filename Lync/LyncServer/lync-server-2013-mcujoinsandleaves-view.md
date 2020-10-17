---
title: 'Lync Server 2013: McuJoinsAndLeaves 보기'
description: 'Lync Server 2013: McuJoinsAndLeaves 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f2f51c340d5bd4824a6e8eff1a0da172a758c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556494"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="342d7-103">Lync Server 2013의 McuJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="342d7-103">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="342d7-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="342d7-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="342d7-105">McuJoinsAndLeaves 보기에는 사용자에 대 한 정보를 저장 하 고 회의 서버 한 대에 대 한 정보를 탈퇴 합니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-105">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="342d7-106">이 보기의 각 레코드에는 사용자 참가 또는 나가기 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-106">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="342d7-107">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="342d7-108">열</span><span class="sxs-lookup"><span data-stu-id="342d7-108">Column</span></span></th>
<th><span data-ttu-id="342d7-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="342d7-109">Data Type</span></span></th>
<th><span data-ttu-id="342d7-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="342d7-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="342d7-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="342d7-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="342d7-113">전화 회의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-113">Time of conference instance.</span></span> <span data-ttu-id="342d7-114">이를 SessionIdSeq와 함께 사용 하 여 전화 회의 인스턴스를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="342d7-115">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="342d7-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342d7-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-117">int</span><span class="sxs-lookup"><span data-stu-id="342d7-117">int</span></span></p></td>
<td><p><span data-ttu-id="342d7-118">전화 회의 인스턴스를 식별 하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="342d7-119">SessionIdTime과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="342d7-120">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="342d7-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342d7-121"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-121"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="342d7-122">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="342d7-123">사용자가 연결 된 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-123">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342d7-124"><strong>M메이 urit3</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-124"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="342d7-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="342d7-126">사용자가 연결 된 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-126">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="342d7-127">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="342d7-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342d7-128"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-128"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-129">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="342d7-129">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="342d7-130">회의 서버 참가/나가기 정보가 캡처된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-130">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342d7-131"><strong>Userurit<</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-131"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="342d7-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="342d7-133">회의 서버 참가/나가기 정보가 캡처된 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-133">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="342d7-134">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="342d7-134">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342d7-135"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-135"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="342d7-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="342d7-137">회의 서버 참가/탈퇴 정보를 캡처한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-137">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="342d7-138">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="342d7-138">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342d7-139"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-139"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="342d7-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="342d7-141">회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-141">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342d7-142"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-142"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-143">int</span><span class="sxs-lookup"><span data-stu-id="342d7-143">int</span></span></p></td>
<td><p><span data-ttu-id="342d7-144">회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-144">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="342d7-145">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="342d7-145">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342d7-146"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-146"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-147">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="342d7-147">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="342d7-148">회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트의 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-148">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342d7-149"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-149"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-150">int</span><span class="sxs-lookup"><span data-stu-id="342d7-150">int</span></span></p></td>
<td><p><span data-ttu-id="342d7-151">여러 장치에 동시에 로그온 한 사용자의 사용자/장치 조합을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-151">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342d7-152"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-152"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-153">비트만</span><span class="sxs-lookup"><span data-stu-id="342d7-153">bit</span></span></p></td>
<td><p><span data-ttu-id="342d7-154">사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-154">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342d7-155"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-155"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-156">datetime</span><span class="sxs-lookup"><span data-stu-id="342d7-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="342d7-157">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-157">Time of session request.</span></span> <span data-ttu-id="342d7-158">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-158">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="342d7-159">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="342d7-159">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342d7-160"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-160"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-161">int</span><span class="sxs-lookup"><span data-stu-id="342d7-161">int</span></span></p></td>
<td><p><span data-ttu-id="342d7-162">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-162">ID number to identify the session.</span></span> <span data-ttu-id="342d7-163">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-163">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="342d7-164">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="342d7-164">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342d7-165"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-165"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-166">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="342d7-166">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="342d7-167">세션의 SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-167">SIP dialog ID of the session.</span></span> <span data-ttu-id="342d7-168">형식은 dialog, from-tag; to 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-168">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="342d7-169"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-169"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-170">datetime</span><span class="sxs-lookup"><span data-stu-id="342d7-170">datetime</span></span></p></td>
<td><p><span data-ttu-id="342d7-171">사용자가 회의 서버에 참가 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-171">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="342d7-172"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="342d7-172"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="342d7-173">datetime</span><span class="sxs-lookup"><span data-stu-id="342d7-173">datetime</span></span></p></td>
<td><p><span data-ttu-id="342d7-174">사용자가 회의 서버를 떠난 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="342d7-174">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

