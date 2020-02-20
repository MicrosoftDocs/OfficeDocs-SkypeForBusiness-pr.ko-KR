---
title: 'Lync Server 2013: McuJoinsAndLeaves 보기'
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
ms.openlocfilehash: a217ddc3ef362c99e5cb7686594e5f9068ce4970
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="dbafa-102">Lync Server 2013의 McuJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="dbafa-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbafa-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dbafa-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dbafa-104">McuJoinsAndLeaves 보기에는 사용자에 대 한 정보를 저장 하 고 회의 서버 한 대에 대 한 정보를 탈퇴 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="dbafa-105">이 보기의 각 레코드에는 사용자 참가 또는 나가기 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="dbafa-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbafa-107">열</span><span class="sxs-lookup"><span data-stu-id="dbafa-107">Column</span></span></th>
<th><span data-ttu-id="dbafa-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="dbafa-108">Data Type</span></span></th>
<th><span data-ttu-id="dbafa-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="dbafa-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbafa-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-111">datetime</span><span class="sxs-lookup"><span data-stu-id="dbafa-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="dbafa-112">전화 회의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-112">Time of conference instance.</span></span> <span data-ttu-id="dbafa-113">이를 SessionIdSeq와 함께 사용 하 여 전화 회의 인스턴스를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="dbafa-114">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbafa-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbafa-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-116">int</span><span class="sxs-lookup"><span data-stu-id="dbafa-116">int</span></span></p></td>
<td><p><span data-ttu-id="dbafa-117">전화 회의 인스턴스를 식별 하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="dbafa-118">SessionIdTime과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="dbafa-119">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbafa-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbafa-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dbafa-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dbafa-122">사용자가 연결 된 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbafa-123"><strong>M메이 urit3</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dbafa-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dbafa-125">사용자가 연결 된 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="dbafa-126">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbafa-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbafa-127"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dbafa-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dbafa-129">회의 서버 참가/나가기 정보가 캡처된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbafa-130"><strong>Userurit<</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dbafa-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dbafa-132">회의 서버 참가/나가기 정보가 캡처된 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="dbafa-133">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbafa-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbafa-134"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dbafa-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dbafa-136">회의 서버 참가/탈퇴 정보를 캡처한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="dbafa-137">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbafa-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbafa-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dbafa-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dbafa-140">회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbafa-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-142">int</span><span class="sxs-lookup"><span data-stu-id="dbafa-142">int</span></span></p></td>
<td><p><span data-ttu-id="dbafa-143">회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="dbafa-144">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbafa-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbafa-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="dbafa-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="dbafa-147">회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트의 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbafa-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-149">int</span><span class="sxs-lookup"><span data-stu-id="dbafa-149">int</span></span></p></td>
<td><p><span data-ttu-id="dbafa-150">여러 장치에 동시에 로그온 한 사용자의 사용자/장치 조합을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbafa-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-152">비트만</span><span class="sxs-lookup"><span data-stu-id="dbafa-152">bit</span></span></p></td>
<td><p><span data-ttu-id="dbafa-153">사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbafa-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-155">datetime</span><span class="sxs-lookup"><span data-stu-id="dbafa-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="dbafa-156">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-156">Time of session request.</span></span> <span data-ttu-id="dbafa-157">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="dbafa-158">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbafa-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbafa-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-160">int</span><span class="sxs-lookup"><span data-stu-id="dbafa-160">int</span></span></p></td>
<td><p><span data-ttu-id="dbafa-161">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-161">ID number to identify the session.</span></span> <span data-ttu-id="dbafa-162">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="dbafa-163">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbafa-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbafa-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="dbafa-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="dbafa-166">세션의 SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="dbafa-167">형식은 dialog, from-tag; to 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbafa-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-169">datetime</span><span class="sxs-lookup"><span data-stu-id="dbafa-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="dbafa-170">사용자가 회의 서버에 참가 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbafa-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="dbafa-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dbafa-172">datetime</span><span class="sxs-lookup"><span data-stu-id="dbafa-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="dbafa-173">사용자가 회의 서버를 떠난 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="dbafa-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

