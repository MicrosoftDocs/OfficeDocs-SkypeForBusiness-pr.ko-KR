---
title: 'Lync Server 2013: McuJoinsAndLeaves 테이블'
description: 'Lync Server 2013: McuJoinsAndLeaves 테이블'
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
ms.openlocfilehash: ee7d9473892ac357dcefd80b0d52382c5dd7d930
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556504"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="e0100-103">Lync Server 2013의 McuJoinsAndLeaves 테이블</span><span class="sxs-lookup"><span data-stu-id="e0100-103">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0100-104">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e0100-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e0100-105">이 테이블의 각 레코드에는 사용자 참가 또는 나가기 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-105">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="e0100-106">예를 들어 사용자가 웹 회의 및 오디오/비디오 요소를 포함 하는 회의에 참가 하는 경우 해당 사용자의 웹 회의 참가에 대해 하나의 레코드가 생성 되 고 사용자의 오디오/비디오 회의 참가에 대 한 다른 레코드가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-106">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0100-107">열</span><span class="sxs-lookup"><span data-stu-id="e0100-107">Column</span></span></th>
<th><span data-ttu-id="e0100-108">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e0100-108">Data Type</span></span></th>
<th><span data-ttu-id="e0100-109">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="e0100-109">Key/Index</span></span></th>
<th><span data-ttu-id="e0100-110">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e0100-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0100-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0100-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0100-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e0100-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e0100-113">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e0100-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0100-114">전화 회의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-114">Time of conference instance.</span></span> <span data-ttu-id="e0100-115">이를 <strong>Sessionidseq</strong> 와 함께 사용 하 여 전화 회의 인스턴스를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e0100-116">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0100-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0100-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e0100-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e0100-118">int</span><span class="sxs-lookup"><span data-stu-id="e0100-118">int</span></span></p></td>
<td><p><span data-ttu-id="e0100-119">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e0100-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0100-120">전화 회의 인스턴스를 식별 하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="e0100-121"><strong>Sessionidtime</strong> 과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e0100-122">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0100-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0100-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e0100-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0100-124">int</span><span class="sxs-lookup"><span data-stu-id="e0100-124">int</span></span></p></td>
<td><p><span data-ttu-id="e0100-125">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e0100-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0100-126">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-126">Unique number identifying this user.</span></span> <span data-ttu-id="e0100-127">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0100-127">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0100-128"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e0100-128"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e0100-129">int</span><span class="sxs-lookup"><span data-stu-id="e0100-129">int</span></span></p></td>
<td><p><span data-ttu-id="e0100-130">Primary</span><span class="sxs-lookup"><span data-stu-id="e0100-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="e0100-131">사용자가 한 번에 여러 컴퓨터 또는 장치에 로그온 되어 있는 경우 McuUserInstance는 사용자/장치 조합을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-131">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0100-132"><strong>Is고 Mpstn</strong></span><span class="sxs-lookup"><span data-stu-id="e0100-132"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="e0100-133">비트만</span><span class="sxs-lookup"><span data-stu-id="e0100-133">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e0100-134">사용자가 PSTN에서 가입 하 고 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-134">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0100-135"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="e0100-135"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0100-136">int</span><span class="sxs-lookup"><span data-stu-id="e0100-136">int</span></span></p></td>
<td><p><span data-ttu-id="e0100-137">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e0100-137">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0100-138">이 회의 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-138">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="e0100-139">자세한 내용은 <a href="lync-server-2013-mcus-table.md">Lync Server 2013의 Mcus 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0100-139">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0100-140"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0100-140"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0100-141">datetime</span><span class="sxs-lookup"><span data-stu-id="e0100-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="e0100-142">외부</span><span class="sxs-lookup"><span data-stu-id="e0100-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0100-143">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-143">Time of session request.</span></span> <span data-ttu-id="e0100-144"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e0100-145">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0100-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0100-146"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e0100-146"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e0100-147">int</span><span class="sxs-lookup"><span data-stu-id="e0100-147">int</span></span></p></td>
<td><p><span data-ttu-id="e0100-148">외부</span><span class="sxs-lookup"><span data-stu-id="e0100-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0100-149">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-149">ID number to identify the session.</span></span> <span data-ttu-id="e0100-150"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e0100-151">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0100-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0100-152"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0100-152"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0100-153">datetime</span><span class="sxs-lookup"><span data-stu-id="e0100-153">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e0100-154">이 사용자가이 회의 서버에 참가 하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-154">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0100-155"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0100-155"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0100-156">datetime</span><span class="sxs-lookup"><span data-stu-id="e0100-156">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e0100-157">이 사용자가이 회의 서버를 떠나는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-157">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0100-158"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="e0100-158"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0100-159">int</span><span class="sxs-lookup"><span data-stu-id="e0100-159">int</span></span></p></td>
<td><p><span data-ttu-id="e0100-160">외부</span><span class="sxs-lookup"><span data-stu-id="e0100-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0100-161">회의에서 클라이언트 소프트웨어를 사용 하는 경우의 버전 번호를 지정 하는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-161">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="e0100-162">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0100-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="e0100-163">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0100-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

