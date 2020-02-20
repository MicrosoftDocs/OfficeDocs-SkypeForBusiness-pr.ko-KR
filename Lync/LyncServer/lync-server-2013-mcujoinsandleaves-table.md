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
ms.openlocfilehash: 138fe5f989fb11986c3db6e134fa7f975a95c96e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="66415-102">Lync Server 2013의 McuJoinsAndLeaves 테이블</span><span class="sxs-lookup"><span data-stu-id="66415-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66415-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="66415-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="66415-104">이 테이블의 각 레코드에는 사용자 참가 또는 나가기 및 회의 서버의 한 조합에 대 한 통화 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="66415-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="66415-105">예를 들어 사용자가 웹 회의 및 오디오/비디오 요소를 포함 하는 회의에 참가 하는 경우 해당 사용자의 웹 회의 참가에 대해 하나의 레코드가 생성 되 고 사용자의 오디오/비디오 회의 참가에 대 한 다른 레코드가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66415-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66415-106">열</span><span class="sxs-lookup"><span data-stu-id="66415-106">Column</span></span></th>
<th><span data-ttu-id="66415-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="66415-107">Data Type</span></span></th>
<th><span data-ttu-id="66415-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="66415-108">Key/Index</span></span></th>
<th><span data-ttu-id="66415-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="66415-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66415-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="66415-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66415-111">datetime</span><span class="sxs-lookup"><span data-stu-id="66415-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="66415-112">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="66415-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66415-113">전화 회의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="66415-113">Time of conference instance.</span></span> <span data-ttu-id="66415-114">이를 <strong>Sessionidseq</strong> 와 함께 사용 하 여 전화 회의 인스턴스를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="66415-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="66415-115">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66415-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66415-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="66415-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="66415-117">int</span><span class="sxs-lookup"><span data-stu-id="66415-117">int</span></span></p></td>
<td><p><span data-ttu-id="66415-118">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="66415-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66415-119">전화 회의 인스턴스를 식별 하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="66415-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="66415-120"><strong>Sessionidtime</strong> 과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="66415-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="66415-121">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66415-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66415-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="66415-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="66415-123">int</span><span class="sxs-lookup"><span data-stu-id="66415-123">int</span></span></p></td>
<td><p><span data-ttu-id="66415-124">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="66415-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66415-125">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="66415-125">Unique number identifying this user.</span></span> <span data-ttu-id="66415-126">자세한 내용은 <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="66415-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66415-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="66415-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="66415-128">int</span><span class="sxs-lookup"><span data-stu-id="66415-128">int</span></span></p></td>
<td><p><span data-ttu-id="66415-129">Primary</span><span class="sxs-lookup"><span data-stu-id="66415-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="66415-130">사용자가 한 번에 여러 컴퓨터 또는 장치에 로그온 되어 있는 경우 McuUserInstance는 사용자/장치 조합을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="66415-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66415-131"><strong>Is고 Mpstn</strong></span><span class="sxs-lookup"><span data-stu-id="66415-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="66415-132">비트만</span><span class="sxs-lookup"><span data-stu-id="66415-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66415-133">사용자가 PSTN에서 가입 하 고 있는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="66415-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66415-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="66415-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="66415-135">int</span><span class="sxs-lookup"><span data-stu-id="66415-135">int</span></span></p></td>
<td><p><span data-ttu-id="66415-136">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="66415-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66415-137">이 회의 서버를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="66415-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="66415-138">자세한 내용은 <a href="lync-server-2013-mcus-table.md">Lync Server 2013의 Mcus 테이블</a> 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="66415-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66415-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="66415-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66415-140">datetime</span><span class="sxs-lookup"><span data-stu-id="66415-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="66415-141">외부</span><span class="sxs-lookup"><span data-stu-id="66415-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66415-142">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="66415-142">Time of session request.</span></span> <span data-ttu-id="66415-143"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66415-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="66415-144">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="66415-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66415-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="66415-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="66415-146">int</span><span class="sxs-lookup"><span data-stu-id="66415-146">int</span></span></p></td>
<td><p><span data-ttu-id="66415-147">외부</span><span class="sxs-lookup"><span data-stu-id="66415-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66415-148">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="66415-148">ID number to identify the session.</span></span> <span data-ttu-id="66415-149"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="66415-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="66415-150">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="66415-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66415-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="66415-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66415-152">datetime</span><span class="sxs-lookup"><span data-stu-id="66415-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66415-153">이 사용자가이 회의 서버에 참가 하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="66415-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66415-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="66415-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66415-155">datetime</span><span class="sxs-lookup"><span data-stu-id="66415-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="66415-156">이 사용자가이 회의 서버를 떠나는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="66415-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66415-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="66415-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="66415-158">int</span><span class="sxs-lookup"><span data-stu-id="66415-158">int</span></span></p></td>
<td><p><span data-ttu-id="66415-159">외부</span><span class="sxs-lookup"><span data-stu-id="66415-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="66415-160">회의에서 클라이언트 소프트웨어를 사용 하는 경우의 버전 번호를 지정 하는 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="66415-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="66415-161">자세한 내용은 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013에서 Clientversions 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66415-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="66415-162">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="66415-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

