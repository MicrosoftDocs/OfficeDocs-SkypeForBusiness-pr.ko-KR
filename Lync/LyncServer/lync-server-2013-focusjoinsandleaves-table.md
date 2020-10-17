---
title: 'Lync Server 2013: FocusJoinsAndLeaves 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9f7691a008dae1fc822b6632a60f5324bb4e80fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500835"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="e0d68-102">Lync Server 2013의 FocusJoinsAndLeaves 테이블</span><span class="sxs-lookup"><span data-stu-id="e0d68-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0d68-103">_**마지막으로 수정 된 항목:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e0d68-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e0d68-104">이 테이블의 각 레코드에는 한 회의에 대 한 사용자의 참가 및 탈퇴 정보에 대 한 CDR 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="e0d68-105">사용자가 회의에 참가 하 고 나갈 때마다이 테이블에는 각 회의가 하나씩 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0d68-106">열</span><span class="sxs-lookup"><span data-stu-id="e0d68-106">Column</span></span></th>
<th><span data-ttu-id="e0d68-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="e0d68-107">Data Type</span></span></th>
<th><span data-ttu-id="e0d68-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="e0d68-108">Key/Index</span></span></th>
<th><span data-ttu-id="e0d68-109">세부 정보</span><span class="sxs-lookup"><span data-stu-id="e0d68-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0d68-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e0d68-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e0d68-112">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e0d68-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0d68-113">전화 회의 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-113">Time of conference instance.</span></span> <span data-ttu-id="e0d68-114">이를 <strong>Sessionidseq</strong> 와 함께 사용 하 여 전화 회의 인스턴스를 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e0d68-115">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0d68-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0d68-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-117">int</span><span class="sxs-lookup"><span data-stu-id="e0d68-117">int</span></span></p></td>
<td><p><span data-ttu-id="e0d68-118">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e0d68-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0d68-119">전화 회의 인스턴스를 식별 하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="e0d68-120"><strong>Sessionidtime</strong> 과 함께 회의 인스턴스를 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="e0d68-121">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 회의 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e0d68-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0d68-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-123">datetime</span><span class="sxs-lookup"><span data-stu-id="e0d68-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="e0d68-124">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e0d68-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0d68-125">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-125">Time of session request.</span></span> <span data-ttu-id="e0d68-126"><strong>SessionIdSeq</strong>와 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e0d68-127">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0d68-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0d68-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-129">int</span><span class="sxs-lookup"><span data-stu-id="e0d68-129">int</span></span></p></td>
<td><p><span data-ttu-id="e0d68-130">Primary, Foreign</span><span class="sxs-lookup"><span data-stu-id="e0d68-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0d68-131">세션을 식별하기 위한 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-131">ID number to identify the session.</span></span> <span data-ttu-id="e0d68-132"><strong>SessionIdTime</strong>과 함께 세션을 고유하게 식별하기 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="e0d68-133">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 Dialogs 표</a> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e0d68-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0d68-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-135">int</span><span class="sxs-lookup"><span data-stu-id="e0d68-135">int</span></span></p></td>
<td><p><span data-ttu-id="e0d68-136">외부</span><span class="sxs-lookup"><span data-stu-id="e0d68-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0d68-137">이 사용자를 식별 하는 고유한 번호로, <a href="lync-server-2013-users-table.md">Lync Server 2013의 Users 테이블</a>에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0d68-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-139">int</span><span class="sxs-lookup"><span data-stu-id="e0d68-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0d68-140">사용자가 동시에 여러 컴퓨터 또는 장치에 로그온 되어 있는 경우 <strong>UserInstance</strong> 을 사용 하 여 사용자/장치 조합을 고유 하 게 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0d68-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-142">비트만</span><span class="sxs-lookup"><span data-stu-id="e0d68-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e0d68-143">사용자가 내부 로부터 로그온 되었는지 여부입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0d68-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-145">int</span><span class="sxs-lookup"><span data-stu-id="e0d68-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e0d68-146">회의에서 발표자 또는 참석자와 같은이 사용자의 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0d68-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-148">datetime</span><span class="sxs-lookup"><span data-stu-id="e0d68-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e0d68-149">이 사용자가 회의에 참가 하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0d68-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-151">datetime</span><span class="sxs-lookup"><span data-stu-id="e0d68-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e0d68-152">이 사용자가 회의에서 나간 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0d68-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-154">int</span><span class="sxs-lookup"><span data-stu-id="e0d68-154">int</span></span></p></td>
<td><p><span data-ttu-id="e0d68-155">외부</span><span class="sxs-lookup"><span data-stu-id="e0d68-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e0d68-156"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블로</a>참조 되는 사용자 클라이언트 소프트웨어의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0d68-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e0d68-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e0d68-158">고유</span><span class="sxs-lookup"><span data-stu-id="e0d68-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e0d68-159">전화 회의에 사용 된 끝점의 GUID (Globally unique identifier)입니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="e0d68-160">이 필드는 Microsoft Lync Server 2013에 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e0d68-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

