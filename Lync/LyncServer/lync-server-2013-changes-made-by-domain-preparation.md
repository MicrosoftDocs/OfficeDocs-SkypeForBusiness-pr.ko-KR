---
title: 'Lync Server 2013: 도메인 준비로 인 한 변경 내용'
description: 'Lync Server 2013: 도메인 준비로 인 한 변경'
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
ms.openlocfilehash: 26400bd1c72c6ae3b8dc1f2d2d8f6c6906b80595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543694"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="6503a-103">Lync Server 2013에서 도메인 준비로 인 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="6503a-103">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6503a-104">_**마지막으로 수정 된 항목:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="6503a-104">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="6503a-p101">다음 표에는 도메인 준비가 도메인 루트에 대해 만든 ACE(액세스 제어 항목)가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="6503a-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="6503a-107">도메인 루트에 추가된 ACE</span><span class="sxs-lookup"><span data-stu-id="6503a-107">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="6503a-108">ACE</span><span class="sxs-lookup"><span data-stu-id="6503a-108">ACE</span></span></th>
<th><span data-ttu-id="6503a-109">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="6503a-109">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="6503a-110">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="6503a-110">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="6503a-111">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="6503a-111">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="6503a-112">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="6503a-112">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="6503a-113">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="6503a-113">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6503a-114">컨테이너 읽기(상속되지 않음)</span><span class="sxs-lookup"><span data-stu-id="6503a-114">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="6503a-115"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-116"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-116"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-117">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-117">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-118">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-118">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-119">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-119">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6503a-120">사용자 PropertySet User-Account-Restrictions 읽기</span><span class="sxs-lookup"><span data-stu-id="6503a-120">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="6503a-121"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-121"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-122">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-122">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-123">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-123">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-124">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-124">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-125">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-125">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6503a-126">사용자 PropertySet Personal-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="6503a-126">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="6503a-127"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-127"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-128">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-128">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-129">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-129">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-130">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-130">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-131">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-131">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6503a-132">사용자 PropertySet General-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="6503a-132">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="6503a-133"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-133"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-134">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-134">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-135">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-135">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-136">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-136">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-137">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-137">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6503a-138">사용자 PropertySet Public-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="6503a-138">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="6503a-139"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-139"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-140">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-140">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-141">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-141">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-142">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-142">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-143">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-143">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6503a-144">사용자 PropertySet RTCUserSearchProperty-Set 읽기</span><span class="sxs-lookup"><span data-stu-id="6503a-144">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="6503a-145"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-145"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-146">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-146">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-147">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-147">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-148">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-148">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-149"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-149"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6503a-150">사용자 PropertySet RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="6503a-150">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="6503a-151"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-151"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-152">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-152">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-153">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-153">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-154">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-154">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-155">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-155">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6503a-156">사용자 Property Proxy-Addresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="6503a-156">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="6503a-157">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-157">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-158">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-158">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-159"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-159"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-160">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-160">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-161">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-161">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6503a-162">사용자 PropertySet RTCUserSearchProperty-Set 쓰기</span><span class="sxs-lookup"><span data-stu-id="6503a-162">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="6503a-163">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-163">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-164">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-164">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-165"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-165"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-166">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-166">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-167">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-167">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6503a-168">사용자 PropertySet RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="6503a-168">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="6503a-169">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-169">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-170">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-170">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-171"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-171"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-172">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-172">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-173">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-173">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6503a-174">모든 Active Directory 개체의 PropertySet DS-Replication-Get-Changes 읽기</span><span class="sxs-lookup"><span data-stu-id="6503a-174">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="6503a-175">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-175">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-176">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-176">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-177">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-177">No</span></span></p></td>
<td><p><span data-ttu-id="6503a-178"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-178"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-179">아니요</span><span class="sxs-lookup"><span data-stu-id="6503a-179">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6503a-p102">다음 표에는 도메인 준비가 세 개의 기본 제공 컨테이너인 사용자, 컴퓨터 및 도메인 컨트롤러에 만드는 ACE가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="6503a-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="6503a-182">기본 제공 컨테이너에 추가 된 Ace</span><span class="sxs-lookup"><span data-stu-id="6503a-182">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6503a-183">ACE</span><span class="sxs-lookup"><span data-stu-id="6503a-183">ACE</span></span></th>
<th><span data-ttu-id="6503a-184">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="6503a-184">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="6503a-185">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="6503a-185">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6503a-186">컨테이너 읽기(상속되지 않음)</span><span class="sxs-lookup"><span data-stu-id="6503a-186">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="6503a-187"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-187"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="6503a-188"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="6503a-188"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

