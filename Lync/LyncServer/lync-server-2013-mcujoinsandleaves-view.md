---
title: 'Lync Server 2013: McuJoinsAndLeaves view'
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
ms.openlocfilehash: d339df5b3b591cbf67376c36c5e0e4261c390851
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="5656b-102">Lync Server 2013의 McuJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="5656b-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5656b-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5656b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5656b-104">McuJoinsAndLeaves 보기는 사용자가 1 회의 서버에 대 한 정보를 참가 및 탈퇴 하는 정보를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="5656b-105">이 보기의 각 레코드에는 사용자 참가 또는 종료 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="5656b-106">이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5656b-107">열</span><span class="sxs-lookup"><span data-stu-id="5656b-107">Column</span></span></th>
<th><span data-ttu-id="5656b-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="5656b-108">Data Type</span></span></th>
<th><span data-ttu-id="5656b-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="5656b-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5656b-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="5656b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="5656b-112">컨퍼런스 인스턴스 시간.</span><span class="sxs-lookup"><span data-stu-id="5656b-112">Time of conference instance.</span></span> <span data-ttu-id="5656b-113">회의 인스턴스를 고유 하 게 식별 하기 위해 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="5656b-114">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5656b-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5656b-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-116">int</span><span class="sxs-lookup"><span data-stu-id="5656b-116">int</span></span></p></td>
<td><p><span data-ttu-id="5656b-117">회의 인스턴스를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="5656b-118">회의 인스턴스를 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="5656b-119">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5656b-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5656b-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5656b-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5656b-122">사용자가 연결 된 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5656b-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5656b-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5656b-125">사용자가 연결 된 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="5656b-126">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5656b-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5656b-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="5656b-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5656b-129">회의 서버 참여/종료 정보를 캡처한 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5656b-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5656b-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5656b-132">회의 서버 참여/종료 정보를 캡처한 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="5656b-133">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5656b-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5656b-134"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5656b-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5656b-136">회의 서버 참여/종료 정보를 캡처한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="5656b-137">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5656b-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5656b-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="5656b-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5656b-140">회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5656b-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-142">int</span><span class="sxs-lookup"><span data-stu-id="5656b-142">int</span></span></p></td>
<td><p><span data-ttu-id="5656b-143">회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="5656b-144">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013에서 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5656b-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5656b-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="5656b-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5656b-147">회의 서버 참여/종료 정보를 캡처한 사용자가 사용 하는 클라이언트 범주의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5656b-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-149">int</span><span class="sxs-lookup"><span data-stu-id="5656b-149">int</span></span></p></td>
<td><p><span data-ttu-id="5656b-150">여러 장치에 동시에 로그온 한 사용자의 사용자/장치 조합을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5656b-151"><strong>Isuser찡그린 Mpstn</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-152">다소</span><span class="sxs-lookup"><span data-stu-id="5656b-152">bit</span></span></p></td>
<td><p><span data-ttu-id="5656b-153">사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5656b-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-155">dmtf</span><span class="sxs-lookup"><span data-stu-id="5656b-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="5656b-156">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-156">Time of session request.</span></span> <span data-ttu-id="5656b-157">세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5656b-158">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5656b-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5656b-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-160">int</span><span class="sxs-lookup"><span data-stu-id="5656b-160">int</span></span></p></td>
<td><p><span data-ttu-id="5656b-161">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-161">ID number to identify the session.</span></span> <span data-ttu-id="5656b-162">세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5656b-163">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5656b-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5656b-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="5656b-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="5656b-166">세션의 SIP 대화 상자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="5656b-167">형식은 대화 상자, from 태그, to 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5656b-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-169">dmtf</span><span class="sxs-lookup"><span data-stu-id="5656b-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="5656b-170">사용자가 회의 서버에 참가 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5656b-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="5656b-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5656b-172">dmtf</span><span class="sxs-lookup"><span data-stu-id="5656b-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="5656b-173">사용자가 회의 서버를 남겨진 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="5656b-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

