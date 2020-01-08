---
title: 'Lync Server 2013: FocusJoinsAndLeaves 테이블'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ead6fc2ce79f7ab1206476ee420bd2ba5a7711f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="6d243-102">Lync Server 2013의 FocusJoinsAndLeaves 테이블</span><span class="sxs-lookup"><span data-stu-id="6d243-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d243-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="6d243-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="6d243-104">이 테이블의 각 레코드에는 한 회의에 대 한 사용자의 참가 및 탈퇴 정보에 대 한 CDR 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="6d243-105">각 회의는 사용자가 회의에 참가 하 고 떠날 때마다이 테이블에 하나의 레코드로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d243-106">열</span><span class="sxs-lookup"><span data-stu-id="6d243-106">Column</span></span></th>
<th><span data-ttu-id="6d243-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6d243-107">Data Type</span></span></th>
<th><span data-ttu-id="6d243-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="6d243-108">Key/Index</span></span></th>
<th><span data-ttu-id="6d243-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="6d243-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d243-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="6d243-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="6d243-112">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="6d243-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d243-113">컨퍼런스 인스턴스 시간.</span><span class="sxs-lookup"><span data-stu-id="6d243-113">Time of conference instance.</span></span> <span data-ttu-id="6d243-114">회의 인스턴스를 고유 하 게 식별 하기 위해 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="6d243-115">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d243-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d243-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-117">int</span><span class="sxs-lookup"><span data-stu-id="6d243-117">int</span></span></p></td>
<td><p><span data-ttu-id="6d243-118">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="6d243-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d243-119">회의 인스턴스를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="6d243-120">회의 인스턴스를 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="6d243-121">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d243-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d243-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-123">dmtf</span><span class="sxs-lookup"><span data-stu-id="6d243-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="6d243-124">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="6d243-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d243-125">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-125">Time of session request.</span></span> <span data-ttu-id="6d243-126">세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6d243-127">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d243-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d243-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-129">int</span><span class="sxs-lookup"><span data-stu-id="6d243-129">int</span></span></p></td>
<td><p><span data-ttu-id="6d243-130">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="6d243-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d243-131">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-131">ID number to identify the session.</span></span> <span data-ttu-id="6d243-132">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="6d243-133">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d243-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d243-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-135">int</span><span class="sxs-lookup"><span data-stu-id="6d243-135">int</span></span></p></td>
<td><p><span data-ttu-id="6d243-136">외부</span><span class="sxs-lookup"><span data-stu-id="6d243-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d243-137"><a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a>에서 참조 된이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d243-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-139">int</span><span class="sxs-lookup"><span data-stu-id="6d243-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d243-140">사용자가 동시에 여러 컴퓨터 또는 장치에 로그온 한 경우 <strong>UserInstance</strong> 는 사용자/장치 조합을 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d243-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-142">다소</span><span class="sxs-lookup"><span data-stu-id="6d243-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d243-143">사용자가 내부에서 로그온 했는지 여부</span><span class="sxs-lookup"><span data-stu-id="6d243-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d243-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-145">int</span><span class="sxs-lookup"><span data-stu-id="6d243-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d243-146">발표자 또는 참석자와 같이 회의에서이 사용자의 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d243-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-148">dmtf</span><span class="sxs-lookup"><span data-stu-id="6d243-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d243-149">이 사용자가 회의에 참가 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d243-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-151">dmtf</span><span class="sxs-lookup"><span data-stu-id="6d243-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="6d243-152">이 사용자가 회의를 떠난 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d243-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-154">int</span><span class="sxs-lookup"><span data-stu-id="6d243-154">int</span></span></p></td>
<td><p><span data-ttu-id="6d243-155">외부</span><span class="sxs-lookup"><span data-stu-id="6d243-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="6d243-156"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블로</a>참조 되는 사용자 클라이언트 소프트웨어의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d243-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="6d243-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="6d243-158">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="6d243-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6d243-159">회의에 사용 되는 끝점의 전역 고유 식별자 (GUID)입니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="6d243-160">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d243-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

