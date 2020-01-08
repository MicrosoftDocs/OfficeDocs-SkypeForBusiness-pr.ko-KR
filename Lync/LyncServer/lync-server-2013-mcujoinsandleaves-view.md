---
title: 'Lync Server 2013: McuJoinsAndLeaves view'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7592879a1c6c6cc6bbcac54fd843046b69acee83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="86701-102">Lync Server 2013의 McuJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="86701-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="86701-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="86701-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="86701-104">McuJoinsAndLeaves 보기는 사용자가 1 회의 서버에 대 한 정보를 참가 및 탈퇴 하는 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="86701-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="86701-105">이 보기의 각 레코드에는 사용자 참가 또는 종료 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86701-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="86701-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="86701-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="86701-107">열</span><span class="sxs-lookup"><span data-stu-id="86701-107">Column</span></span></th>
<th><span data-ttu-id="86701-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="86701-108">Data Type</span></span></th>
<th><span data-ttu-id="86701-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="86701-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="86701-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="86701-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="86701-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="86701-112">컨퍼런스 인스턴스 시간.</span><span class="sxs-lookup"><span data-stu-id="86701-112">Time of conference instance.</span></span> <span data-ttu-id="86701-113">회의 인스턴스를 고유 하 게 식별 하기 위해 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86701-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="86701-114">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86701-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86701-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="86701-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-116">int</span><span class="sxs-lookup"><span data-stu-id="86701-116">int</span></span></p></td>
<td><p><span data-ttu-id="86701-117">회의 인스턴스를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="86701-118">회의 인스턴스를 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86701-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="86701-119">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86701-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86701-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="86701-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86701-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86701-122">사용자가 연결 된 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86701-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="86701-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86701-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86701-125">사용자가 연결 된 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="86701-126">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86701-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86701-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="86701-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="86701-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="86701-129">회의 서버 참여/종료 정보를 캡처한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86701-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="86701-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86701-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86701-132">회의 서버 참여/종료 정보를 캡처한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="86701-133">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86701-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86701-134"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="86701-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86701-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86701-136">회의 서버 참여/종료 정보를 캡처한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="86701-137">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86701-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86701-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="86701-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="86701-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="86701-140">회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86701-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="86701-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-142">int</span><span class="sxs-lookup"><span data-stu-id="86701-142">int</span></span></p></td>
<td><p><span data-ttu-id="86701-143">회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="86701-144">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86701-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86701-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="86701-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="86701-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="86701-147">회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트 범주의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86701-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="86701-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-149">int</span><span class="sxs-lookup"><span data-stu-id="86701-149">int</span></span></p></td>
<td><p><span data-ttu-id="86701-150">여러 장치에 동시에 로그온 한 사용자의 사용자/장치 조합을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="86701-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86701-151"><strong>Isuser찡그린 Mpstn</strong></span><span class="sxs-lookup"><span data-stu-id="86701-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-152">다소</span><span class="sxs-lookup"><span data-stu-id="86701-152">bit</span></span></p></td>
<td><p><span data-ttu-id="86701-153">사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86701-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="86701-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-155">dmtf</span><span class="sxs-lookup"><span data-stu-id="86701-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="86701-156">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-156">Time of session request.</span></span> <span data-ttu-id="86701-157">세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86701-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="86701-158">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86701-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86701-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="86701-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-160">int</span><span class="sxs-lookup"><span data-stu-id="86701-160">int</span></span></p></td>
<td><p><span data-ttu-id="86701-161">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-161">ID number to identify the session.</span></span> <span data-ttu-id="86701-162">세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86701-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="86701-163">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="86701-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86701-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="86701-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="86701-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="86701-166">세션의 SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="86701-167">형식은 대화 상자, from 태그, to 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="86701-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="86701-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-169">dmtf</span><span class="sxs-lookup"><span data-stu-id="86701-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="86701-170">사용자가 회의 서버에 참가 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="86701-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="86701-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="86701-172">dmtf</span><span class="sxs-lookup"><span data-stu-id="86701-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="86701-173">사용자가 회의 서버를 남겨진 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="86701-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

