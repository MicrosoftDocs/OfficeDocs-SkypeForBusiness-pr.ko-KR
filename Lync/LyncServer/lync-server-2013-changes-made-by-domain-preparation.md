---
title: 'Lync Server 2013: 도메인 준비로 인 한 변경 내용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb693f79470e7d68a1aaf662c9ab82b8bafa5c39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="c7637-102">Lync Server 2013에서 도메인 준비로 인 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="c7637-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7637-103">_**마지막으로 수정 된 항목:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="c7637-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="c7637-p101">다음 표에는 도메인 준비가 도메인 루트에 대해 만든 ACE(액세스 제어 항목)가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7637-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="c7637-106">도메인 루트에 추가된 ACE</span><span class="sxs-lookup"><span data-stu-id="c7637-106">ACEs Added to Domain Root</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7637-107">ACE</span><span class="sxs-lookup"><span data-stu-id="c7637-107">ACE</span></span></th>
<th><span data-ttu-id="c7637-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c7637-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="c7637-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c7637-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="c7637-110">RTCUniversal UserAdmins</span><span class="sxs-lookup"><span data-stu-id="c7637-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="c7637-111">RTCHSUniversal-서비스</span><span class="sxs-lookup"><span data-stu-id="c7637-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="c7637-112">인증 된 사용자</span><span class="sxs-lookup"><span data-stu-id="c7637-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7637-113">컨테이너 읽기(상속되지 않음)</span><span class="sxs-lookup"><span data-stu-id="c7637-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c7637-114"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-115"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-116">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-116">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-117">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-117">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-118">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7637-119">사용자 PropertySet User-Account-Restrictions 읽기</span><span class="sxs-lookup"><span data-stu-id="c7637-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="c7637-120"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-121">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-121">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-122">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-122">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-123">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-123">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-124">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7637-125">사용자 PropertySet Personal-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="c7637-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="c7637-126"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-127">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-127">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-128">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-128">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-129">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-129">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-130">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7637-131">사용자 PropertySet General-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="c7637-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="c7637-132"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-133">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-133">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-134">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-134">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-135">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-135">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-136">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7637-137">사용자 PropertySet Public-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="c7637-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="c7637-138"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-139">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-139">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-140">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-140">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-141">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-141">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-142">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7637-143">사용자 PropertySet RTCUserSearchProperty-Set 읽기</span><span class="sxs-lookup"><span data-stu-id="c7637-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="c7637-144"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-145">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-145">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-146">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-146">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-147">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-147">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-148"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7637-149">사용자 PropertySet RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="c7637-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="c7637-150"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-151">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-151">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-152">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-152">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-153">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-153">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-154">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7637-155">사용자 Property Proxy-Addresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="c7637-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="c7637-156">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-156">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-157">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-157">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-158"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-159">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-159">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-160">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7637-161">사용자 PropertySet RTCUserSearchProperty-Set 쓰기</span><span class="sxs-lookup"><span data-stu-id="c7637-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="c7637-162">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-162">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-163">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-163">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-164"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-165">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-165">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-166">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7637-167">사용자 PropertySet RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="c7637-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="c7637-168">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-168">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-169">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-169">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-170"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-171">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-171">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-172">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7637-173">모든 Active Directory 개체의 PropertySet DS-Replication-Get-Changes 읽기</span><span class="sxs-lookup"><span data-stu-id="c7637-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="c7637-174">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-174">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-175">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-175">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-176">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-176">No</span></span></p></td>
<td><p><span data-ttu-id="c7637-177"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-178">아니요</span><span class="sxs-lookup"><span data-stu-id="c7637-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c7637-p102">다음 표에는 도메인 준비가 세 개의 기본 제공 컨테이너인 사용자, 컴퓨터 및 도메인 컨트롤러에 만드는 ACE가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7637-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="c7637-181">기본 제공 컨테이너에 추가 된 Ace</span><span class="sxs-lookup"><span data-stu-id="c7637-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7637-182">ACE</span><span class="sxs-lookup"><span data-stu-id="c7637-182">ACE</span></span></th>
<th><span data-ttu-id="c7637-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c7637-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="c7637-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="c7637-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7637-185">컨테이너 읽기(상속되지 않음)</span><span class="sxs-lookup"><span data-stu-id="c7637-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c7637-186"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c7637-187"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="c7637-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

