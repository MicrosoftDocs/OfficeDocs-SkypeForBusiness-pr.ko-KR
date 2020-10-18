---
title: 'Lync Server 2013: FocusJoinsAndLeaves 보기'
description: 'Lync Server 2013: FocusJoinsAndLeaves 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6f68c44461e378e9ebedce1305ee6b384a7a8a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577454"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="b3e20-103">Lync Server 2013의 FocusJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="b3e20-103">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3e20-104">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="b3e20-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="b3e20-105">FocusJoinsAndLeaves 보기에는 한 회의의 참가 및 탈퇴 정보에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-105">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="b3e20-106">각 회의는 사용자가 회의에 참가 하 고 나갈 때마다 기록 되는 레코드로이 보기로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-106">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="b3e20-107">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3e20-108">열</span><span class="sxs-lookup"><span data-stu-id="b3e20-108">Column</span></span></th>
<th><span data-ttu-id="b3e20-109">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="b3e20-109">Data Type</span></span></th>
<th><span data-ttu-id="b3e20-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="b3e20-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3e20-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b3e20-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3e20-113">전화 회의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-113">Time of conference instance.</span></span> <span data-ttu-id="b3e20-114">이를 SessionIdSeq와 함께 사용 하 여 전화 회의 인스턴스를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="b3e20-115">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3e20-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3e20-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-117">int</span><span class="sxs-lookup"><span data-stu-id="b3e20-117">int</span></span></p></td>
<td><p><span data-ttu-id="b3e20-118">전화 회의 인스턴스를 식별 하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="b3e20-119">SessionIdTime과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="b3e20-120">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3e20-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3e20-121"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-121"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-122">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="b3e20-122">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b3e20-123">전화 회의 참가/나가기 정보가 캡처된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-123">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3e20-124"><strong>Userurit<</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-124"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3e20-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3e20-126">전화 회의 참가/나가기 정보가 캡처된 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-126">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="b3e20-127">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3e20-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3e20-128"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-128"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3e20-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3e20-130">전화 회의 참가/나가기 정보가 캡처된 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-130">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="b3e20-131">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3e20-131">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3e20-132"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-132"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-133">고유</span><span class="sxs-lookup"><span data-stu-id="b3e20-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="b3e20-134">전화 회의 참가/나가기 정보가 캡처된 사용자의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-134">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3e20-135"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-135"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-136">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3e20-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3e20-137">전화 회의 참가/나가기 정보가 캡처된 사용자가 사용 하는 클라이언트의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-137">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3e20-138"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-138"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-139">int</span><span class="sxs-lookup"><span data-stu-id="b3e20-139">int</span></span></p></td>
<td><p><span data-ttu-id="b3e20-140">전화 회의 참가/나가기 정보가 캡처된 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-140">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="b3e20-141">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 테이블을</a> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3e20-141">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3e20-142"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-142"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-143">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b3e20-143">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="b3e20-144">전화 회의 참가/나가기 정보가 캡처된 사용자가 사용 하는 클라이언트의 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-144">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3e20-145"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-145"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-146">int</span><span class="sxs-lookup"><span data-stu-id="b3e20-146">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3e20-147"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-147"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-148">비트만</span><span class="sxs-lookup"><span data-stu-id="b3e20-148">bit</span></span></p></td>
<td><p><span data-ttu-id="b3e20-149">사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-149">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3e20-150"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-150"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-151">datetime</span><span class="sxs-lookup"><span data-stu-id="b3e20-151">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3e20-152">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-152">Time of session request.</span></span> <span data-ttu-id="b3e20-153">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-153">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="b3e20-154">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b3e20-154">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3e20-155"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-155"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-156">int</span><span class="sxs-lookup"><span data-stu-id="b3e20-156">int</span></span></p></td>
<td><p><span data-ttu-id="b3e20-157">사용자가 동시에 여러 컴퓨터 또는 장치에 로그온 되어 있는 경우 UserInstance을 사용 하 여 사용자/장치 조합을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-157">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3e20-158"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-158"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-159">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="b3e20-159">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="b3e20-160">세션의 SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-160">SIP dialog ID of the session.</span></span> <span data-ttu-id="b3e20-161">형식은 dialog, from-tag; to 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-161">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3e20-162"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-162"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-163">datetime</span><span class="sxs-lookup"><span data-stu-id="b3e20-163">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3e20-164">사용자가 회의에 참가 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-164">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3e20-165"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-165"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-166">datetime</span><span class="sxs-lookup"><span data-stu-id="b3e20-166">datetime</span></span></p></td>
<td><p><span data-ttu-id="b3e20-167">사용자가 회의에서 나간 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-167">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3e20-168"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="b3e20-168"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="b3e20-169">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3e20-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3e20-170">회의에서 발표자 또는 참석자와 같은 사용자의 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="b3e20-170">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

