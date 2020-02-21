---
title: 'Lync Server 2013: FocusJoinsAndLeaves 보기'
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
ms.openlocfilehash: 9e97346929851bec53ab228988d72fb4813316d2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="29192-102">Lync Server 2013의 FocusJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="29192-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29192-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="29192-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="29192-104">FocusJoinsAndLeaves 보기에는 한 회의의 참가 및 탈퇴 정보에 대 한 정보가 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29192-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="29192-105">각 회의는 사용자가 회의에 참가 하 고 나갈 때마다 기록 되는 레코드로이 보기로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29192-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="29192-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="29192-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29192-107">열</span><span class="sxs-lookup"><span data-stu-id="29192-107">Column</span></span></th>
<th><span data-ttu-id="29192-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="29192-108">Data Type</span></span></th>
<th><span data-ttu-id="29192-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="29192-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29192-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="29192-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-111">datetime</span><span class="sxs-lookup"><span data-stu-id="29192-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="29192-112">전화 회의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-112">Time of conference instance.</span></span> <span data-ttu-id="29192-113">이를 SessionIdSeq와 함께 사용 하 여 전화 회의 인스턴스를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="29192-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="29192-114">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29192-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29192-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="29192-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-116">int</span><span class="sxs-lookup"><span data-stu-id="29192-116">int</span></span></p></td>
<td><p><span data-ttu-id="29192-117">전화 회의 인스턴스를 식별 하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="29192-118">SessionIdTime과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29192-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="29192-119">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29192-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29192-120"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="29192-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="29192-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="29192-122">전화 회의 참가/나가기 정보가 캡처된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29192-123"><strong>Userurit<</strong></span><span class="sxs-lookup"><span data-stu-id="29192-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29192-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29192-125">전화 회의 참가/나가기 정보가 캡처된 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="29192-126">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="29192-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29192-127"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="29192-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29192-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29192-129">전화 회의 참가/나가기 정보가 캡처된 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="29192-130">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="29192-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29192-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="29192-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-132">고유</span><span class="sxs-lookup"><span data-stu-id="29192-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="29192-133">전화 회의 참가/나가기 정보가 캡처된 사용자의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29192-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="29192-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29192-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29192-136">전화 회의 참가/나가기 정보가 캡처된 사용자가 사용 하는 클라이언트의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29192-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="29192-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-138">int</span><span class="sxs-lookup"><span data-stu-id="29192-138">int</span></span></p></td>
<td><p><span data-ttu-id="29192-139">전화 회의 참가/나가기 정보가 캡처된 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="29192-140">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 테이블을</a> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="29192-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29192-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="29192-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="29192-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="29192-143">전화 회의 참가/나가기 정보가 캡처된 사용자가 사용 하는 클라이언트의 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29192-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="29192-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-145">int</span><span class="sxs-lookup"><span data-stu-id="29192-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29192-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="29192-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-147">비트만</span><span class="sxs-lookup"><span data-stu-id="29192-147">bit</span></span></p></td>
<td><p><span data-ttu-id="29192-148">사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29192-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="29192-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-150">datetime</span><span class="sxs-lookup"><span data-stu-id="29192-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="29192-151">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-151">Time of session request.</span></span> <span data-ttu-id="29192-152">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="29192-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="29192-153">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="29192-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29192-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="29192-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-155">int</span><span class="sxs-lookup"><span data-stu-id="29192-155">int</span></span></p></td>
<td><p><span data-ttu-id="29192-156">사용자가 동시에 여러 컴퓨터 또는 장치에 로그온 되어 있는 경우 UserInstance을 사용 하 여 사용자/장치 조합을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="29192-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29192-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="29192-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="29192-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="29192-159">세션의 SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="29192-160">형식은 dialog, from-tag; to 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29192-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="29192-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-162">datetime</span><span class="sxs-lookup"><span data-stu-id="29192-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="29192-163">사용자가 회의에 참가 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29192-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="29192-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-165">datetime</span><span class="sxs-lookup"><span data-stu-id="29192-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="29192-166">사용자가 회의에서 나간 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29192-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="29192-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="29192-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="29192-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="29192-169">회의에서 발표자 또는 참석자와 같은 사용자의 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="29192-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

