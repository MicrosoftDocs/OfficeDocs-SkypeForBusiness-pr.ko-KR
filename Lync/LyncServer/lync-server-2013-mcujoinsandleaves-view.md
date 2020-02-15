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
ms.openlocfilehash: 9eae65a6f19e0eb73098ed5990d6881d0129b34e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="1ff6f-102">Lync Server 2013의 McuJoinsAndLeaves 보기</span><span class="sxs-lookup"><span data-stu-id="1ff6f-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ff6f-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1ff6f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1ff6f-104">McuJoinsAndLeaves 보기에는 사용자에 대 한 정보를 저장 하 고 회의 서버 한 대에 대 한 정보를 탈퇴 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="1ff6f-105">이 보기의 각 레코드에는 사용자 참가 또는 나가기 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="1ff6f-106">이 보기는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ff6f-107">열</span><span class="sxs-lookup"><span data-stu-id="1ff6f-107">Column</span></span></th>
<th><span data-ttu-id="1ff6f-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="1ff6f-108">Data Type</span></span></th>
<th><span data-ttu-id="1ff6f-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="1ff6f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ff6f-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="1ff6f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-112">전화 회의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-112">Time of conference instance.</span></span> <span data-ttu-id="1ff6f-113">이를 SessionIdSeq와 함께 사용 하 여 전화 회의 인스턴스를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="1ff6f-114">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff6f-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-116">int</span><span class="sxs-lookup"><span data-stu-id="1ff6f-116">int</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-117">전화 회의 인스턴스를 식별 하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="1ff6f-118">SessionIdTime과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="1ff6f-119">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff6f-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ff6f-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-122">사용자가 연결 된 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff6f-123"><strong>M메이 urit3</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ff6f-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-125">사용자가 연결 된 회의 서버의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="1ff6f-126">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff6f-127"><strong>변수와 useruri</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="1ff6f-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-129">회의 서버 참가/나가기 정보가 캡처된 사용자의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff6f-130"><strong>Userurit<</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ff6f-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-132">회의 서버 참가/나가기 정보가 캡처된 사용자의 URI 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="1ff6f-133">자세한 내용은 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013의 UriTypes 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff6f-134"><strong>UserTenant 넌 트</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-135">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ff6f-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-136">회의 서버 참가/탈퇴 정보를 캡처한 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="1ff6f-137">자세한 내용은 <a href="lync-server-2013-tenants-table.md">Lync Server 2013의 테 넌 트 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff6f-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-139">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ff6f-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-140">회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff6f-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-142">int</span><span class="sxs-lookup"><span data-stu-id="1ff6f-142">int</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-143">회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="1ff6f-144">자세한 내용은 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013의 Useragentdef 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff6f-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="1ff6f-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-147">회의 서버 참가/탈퇴 정보를 캡처한 사용자가 사용 하는 클라이언트의 범주 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff6f-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-149">int</span><span class="sxs-lookup"><span data-stu-id="1ff6f-149">int</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-150">여러 장치에 동시에 로그온 한 사용자의 사용자/장치 조합을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff6f-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-152">비트만</span><span class="sxs-lookup"><span data-stu-id="1ff6f-152">bit</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-153">사용자가 내부 사용자 인지 여부를 나타내는 비트입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff6f-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-155">datetime</span><span class="sxs-lookup"><span data-stu-id="1ff6f-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-156">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-156">Time of session request.</span></span> <span data-ttu-id="1ff6f-157">SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="1ff6f-158">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff6f-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-160">int</span><span class="sxs-lookup"><span data-stu-id="1ff6f-160">int</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-161">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-161">ID number to identify the session.</span></span> <span data-ttu-id="1ff6f-162">SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="1ff6f-163">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff6f-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="1ff6f-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-166">세션의 SIP 대화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="1ff6f-167">형식은 dialog, from-tag; to 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ff6f-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-169">datetime</span><span class="sxs-lookup"><span data-stu-id="1ff6f-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-170">사용자가 회의 서버에 참가 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ff6f-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ff6f-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ff6f-172">datetime</span><span class="sxs-lookup"><span data-stu-id="1ff6f-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ff6f-173">사용자가 회의 서버를 떠난 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="1ff6f-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

