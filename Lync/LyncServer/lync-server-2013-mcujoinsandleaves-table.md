---
title: 'Lync Server 2013: McuJoinsAndLeaves 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 204906deb88a2067b7304088515b25fee2da0350
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="48893-102">Lync Server 2013의 McuJoinsAndLeaves 테이블</span><span class="sxs-lookup"><span data-stu-id="48893-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48893-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="48893-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="48893-104">이 테이블의 각 레코드에는 사용자 참가 또는 종료 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48893-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="48893-105">예를 들어 사용자가 웹 회의 및 오디오/비디오 요소를 포함 하는 회의에 참가 하는 경우 해당 사용자의 웹 회의 참가에 대해 하나의 레코드가 만들어지고 사용자의 오디오/비디오 회의 참가에 대해 다른 레코드가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="48893-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="48893-106">열</span><span class="sxs-lookup"><span data-stu-id="48893-106">Column</span></span></th>
<th><span data-ttu-id="48893-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="48893-107">Data Type</span></span></th>
<th><span data-ttu-id="48893-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="48893-108">Key/Index</span></span></th>
<th><span data-ttu-id="48893-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="48893-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="48893-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="48893-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="48893-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="48893-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="48893-112">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="48893-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="48893-113">컨퍼런스 인스턴스 시간.</span><span class="sxs-lookup"><span data-stu-id="48893-113">Time of conference instance.</span></span> <span data-ttu-id="48893-114">회의 인스턴스를 고유 하 게 식별 하기 위해 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48893-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="48893-115">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48893-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48893-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="48893-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="48893-117">int</span><span class="sxs-lookup"><span data-stu-id="48893-117">int</span></span></p></td>
<td><p><span data-ttu-id="48893-118">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="48893-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="48893-119">회의 인스턴스를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="48893-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="48893-120">회의 인스턴스를 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48893-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="48893-121">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48893-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48893-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="48893-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="48893-123">int</span><span class="sxs-lookup"><span data-stu-id="48893-123">int</span></span></p></td>
<td><p><span data-ttu-id="48893-124">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="48893-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="48893-125">이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="48893-125">Unique number identifying this user.</span></span> <span data-ttu-id="48893-126">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48893-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48893-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="48893-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="48893-128">int</span><span class="sxs-lookup"><span data-stu-id="48893-128">int</span></span></p></td>
<td><p><span data-ttu-id="48893-129">주요한</span><span class="sxs-lookup"><span data-stu-id="48893-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="48893-130">사용자가 한 번에 여러 컴퓨터 또는 장치에 로그온 한 경우 McuUserInstance는 사용자/장치 조합을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="48893-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48893-131"><strong>Is찡그린 Mpstn</strong></span><span class="sxs-lookup"><span data-stu-id="48893-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="48893-132">다소</span><span class="sxs-lookup"><span data-stu-id="48893-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="48893-133">사용자가 PSTN에서 가입 하 고 있는지 여부.</span><span class="sxs-lookup"><span data-stu-id="48893-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48893-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="48893-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="48893-135">int</span><span class="sxs-lookup"><span data-stu-id="48893-135">int</span></span></p></td>
<td><p><span data-ttu-id="48893-136">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="48893-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="48893-137">이 회의 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="48893-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="48893-138">자세한 내용은 <a href="lync-server-2013-mcus-table.md">Lync Server 2013의 Mcus 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48893-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48893-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="48893-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="48893-140">dmtf</span><span class="sxs-lookup"><span data-stu-id="48893-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="48893-141">외부</span><span class="sxs-lookup"><span data-stu-id="48893-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="48893-142">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="48893-142">Time of session request.</span></span> <span data-ttu-id="48893-143">세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48893-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="48893-144">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48893-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48893-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="48893-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="48893-146">int</span><span class="sxs-lookup"><span data-stu-id="48893-146">int</span></span></p></td>
<td><p><span data-ttu-id="48893-147">외부</span><span class="sxs-lookup"><span data-stu-id="48893-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="48893-148">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="48893-148">ID number to identify the session.</span></span> <span data-ttu-id="48893-149">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48893-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="48893-150">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48893-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48893-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="48893-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="48893-152">dmtf</span><span class="sxs-lookup"><span data-stu-id="48893-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="48893-153">이 사용자가 회의 서버에 참가 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="48893-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="48893-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="48893-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="48893-155">dmtf</span><span class="sxs-lookup"><span data-stu-id="48893-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="48893-156">이 사용자가 회의 서버를 나간 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="48893-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="48893-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="48893-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="48893-158">int</span><span class="sxs-lookup"><span data-stu-id="48893-158">int</span></span></p></td>
<td><p><span data-ttu-id="48893-159">외부</span><span class="sxs-lookup"><span data-stu-id="48893-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="48893-160">회의에서 클라이언트 소프트웨어 사용의 버전 번호를 지정 하는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="48893-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="48893-161">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블</a> 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48893-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="48893-162">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="48893-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

