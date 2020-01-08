---
title: 'Lync Server 2013: FocusJoinsAndLeaves view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1302bf744b0954d00eae4f4cc27454b2889745
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="5a8d6-102">Lync Server 2013의 FocusJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="5a8d6-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a8d6-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5a8d6-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5a8d6-104">FocusJoinsAndLeaves 보기는 한 회의에 대 한 참가 및 탈퇴 정보에 대 한 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="5a8d6-105">각 회의는 사용자가 회의에 참가 하 고 떠날 때마다 기록 하는 레코드를 기준으로이 보기로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="5a8d6-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5a8d6-107">열</span><span class="sxs-lookup"><span data-stu-id="5a8d6-107">Column</span></span></th>
<th><span data-ttu-id="5a8d6-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5a8d6-108">Data Type</span></span></th>
<th><span data-ttu-id="5a8d6-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="5a8d6-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5a8d6-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="5a8d6-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-112">컨퍼런스 인스턴스 시간.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-112">Time of conference instance.</span></span> <span data-ttu-id="5a8d6-113">회의 인스턴스를 고유 하 게 식별 하기 위해 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="5a8d6-114">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d6-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-116">int</span><span class="sxs-lookup"><span data-stu-id="5a8d6-116">int</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-117">회의 인스턴스를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="5a8d6-118">회의 인스턴스를 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="5a8d6-119">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d6-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5a8d6-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-122">회의 참가/정보 남기기를 캡처한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d6-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5a8d6-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-125">회의 참가/정보 남기기를 캡처한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="5a8d6-126">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d6-127"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-128">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5a8d6-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-129">회의 참가/정보 남기기를 캡처한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="5a8d6-130">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d6-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-132">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5a8d6-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-133">회의 참가/종료 정보가 캡처 된 사용자의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d6-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5a8d6-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-136">회의 참가/정보 남기기를 캡처한 사용자가 사용 하는 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d6-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-138">int</span><span class="sxs-lookup"><span data-stu-id="5a8d6-138">int</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-139">회의 참가/정보 남기기를 캡처한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="5a8d6-140">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d6-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5a8d6-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-143">회의 참가/정보 남기기를 캡처한 사용자가 사용 하는 클라이언트 범주의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d6-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-145">int</span><span class="sxs-lookup"><span data-stu-id="5a8d6-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d6-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-147">다소</span><span class="sxs-lookup"><span data-stu-id="5a8d6-147">bit</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-148">사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d6-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-150">dmtf</span><span class="sxs-lookup"><span data-stu-id="5a8d6-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-151">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-151">Time of session request.</span></span> <span data-ttu-id="5a8d6-152">세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5a8d6-153">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d6-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-155">int</span><span class="sxs-lookup"><span data-stu-id="5a8d6-155">int</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-156">사용자가 동시에 여러 컴퓨터 또는 장치에 로그온 한 경우 UserInstance는 사용자/장치 조합을 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d6-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="5a8d6-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-159">세션의 SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="5a8d6-160">형식은 대화 상자, from 태그, to 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d6-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-162">dmtf</span><span class="sxs-lookup"><span data-stu-id="5a8d6-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-163">사용자가 회의에 참가 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5a8d6-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-165">dmtf</span><span class="sxs-lookup"><span data-stu-id="5a8d6-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-166">사용자가 회의를 남겨진 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5a8d6-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5a8d6-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="5a8d6-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="5a8d6-168">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5a8d6-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5a8d6-169">회의에서 사용자의 역할 (예: 발표자 또는 참석자)</span><span class="sxs-lookup"><span data-stu-id="5a8d6-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

