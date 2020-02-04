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
ms.openlocfilehash: 4365e5bbfe92168047165adf6504333e1c34fab6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765266"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="8fef3-102">Lync Server 2013의 FocusJoinsAndLeaves 테이블</span><span class="sxs-lookup"><span data-stu-id="8fef3-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8fef3-103">_**마지막으로 수정한 주제:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8fef3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8fef3-104">이 테이블의 각 레코드에는 한 회의에 대 한 사용자의 참가 및 탈퇴 정보에 대 한 CDR 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="8fef3-105">각 회의는 사용자가 회의에 참가 하 고 떠날 때마다이 테이블에 하나의 레코드로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8fef3-106">열</span><span class="sxs-lookup"><span data-stu-id="8fef3-106">Column</span></span></th>
<th><span data-ttu-id="8fef3-107">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8fef3-107">Data Type</span></span></th>
<th><span data-ttu-id="8fef3-108">키/인덱스</span><span class="sxs-lookup"><span data-stu-id="8fef3-108">Key/Index</span></span></th>
<th><span data-ttu-id="8fef3-109">세부적인</span><span class="sxs-lookup"><span data-stu-id="8fef3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8fef3-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-111">dmtf</span><span class="sxs-lookup"><span data-stu-id="8fef3-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8fef3-112">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="8fef3-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fef3-113">컨퍼런스 인스턴스 시간.</span><span class="sxs-lookup"><span data-stu-id="8fef3-113">Time of conference instance.</span></span> <span data-ttu-id="8fef3-114">회의 인스턴스를 고유 하 게 식별 하기 위해 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="8fef3-115">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fef3-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fef3-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-117">int</span><span class="sxs-lookup"><span data-stu-id="8fef3-117">int</span></span></p></td>
<td><p><span data-ttu-id="8fef3-118">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="8fef3-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fef3-119">회의 인스턴스를 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="8fef3-120">회의 인스턴스를 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="8fef3-121">자세한 내용은 <a href="lync-server-2013-conferences-table.md">Lync Server 2013의 컨퍼런스 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fef3-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fef3-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-123">dmtf</span><span class="sxs-lookup"><span data-stu-id="8fef3-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="8fef3-124">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="8fef3-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fef3-125">세션 요청 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-125">Time of session request.</span></span> <span data-ttu-id="8fef3-126">세션을 고유 하 게 식별 하는 <strong>Sessionidseq</strong> 와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8fef3-127">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fef3-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fef3-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-129">int</span><span class="sxs-lookup"><span data-stu-id="8fef3-129">int</span></span></p></td>
<td><p><span data-ttu-id="8fef3-130">기본, 외래</span><span class="sxs-lookup"><span data-stu-id="8fef3-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fef3-131">세션을 식별 하는 ID 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-131">ID number to identify the session.</span></span> <span data-ttu-id="8fef3-132">세션을 고유 하 게 식별 하는 <strong>Sessionidtime</strong> 과 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8fef3-133">자세한 내용은 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013의 대화 상자 표</a> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8fef3-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fef3-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-135">int</span><span class="sxs-lookup"><span data-stu-id="8fef3-135">int</span></span></p></td>
<td><p><span data-ttu-id="8fef3-136">외부</span><span class="sxs-lookup"><span data-stu-id="8fef3-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fef3-137"><a href="lync-server-2013-users-table.md">Lync Server 2013의 사용자 테이블</a>에서 참조 된이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fef3-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-139">int</span><span class="sxs-lookup"><span data-stu-id="8fef3-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8fef3-140">사용자가 동시에 여러 컴퓨터 또는 장치에 로그온 한 경우 <strong>UserInstance</strong> 는 사용자/장치 조합을 고유 하 게 식별 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fef3-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-142">다소</span><span class="sxs-lookup"><span data-stu-id="8fef3-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8fef3-143">사용자가 내부에서 로그온 했는지 여부</span><span class="sxs-lookup"><span data-stu-id="8fef3-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fef3-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-145">int</span><span class="sxs-lookup"><span data-stu-id="8fef3-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8fef3-146">발표자 또는 참석자와 같이 회의에서이 사용자의 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fef3-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-148">dmtf</span><span class="sxs-lookup"><span data-stu-id="8fef3-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8fef3-149">이 사용자가 회의에 참가 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fef3-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-151">dmtf</span><span class="sxs-lookup"><span data-stu-id="8fef3-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8fef3-152">이 사용자가 회의를 떠난 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8fef3-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-154">int</span><span class="sxs-lookup"><span data-stu-id="8fef3-154">int</span></span></p></td>
<td><p><span data-ttu-id="8fef3-155">외부</span><span class="sxs-lookup"><span data-stu-id="8fef3-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8fef3-156"><a href="lync-server-2013-clientversions-table.md">Lync Server 2013의 Clientversions 테이블로</a>참조 되는 사용자 클라이언트 소프트웨어의 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8fef3-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="8fef3-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="8fef3-158">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="8fef3-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8fef3-159">회의에 사용 되는 끝점의 전역 고유 식별자 (GUID)입니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="8fef3-160">이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8fef3-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

