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
ms.openlocfilehash: 2b1eea02c41acf748674cdd7976028a51fdb367e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529505"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="99b50-102">Lync Server 2013에서 도메인 준비로 인 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="99b50-102">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99b50-103">_**마지막으로 수정 된 항목:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="99b50-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="99b50-p101">다음 표에는 도메인 준비가 도메인 루트에 대해 만든 ACE(액세스 제어 항목)가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="99b50-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="99b50-106">도메인 루트에 추가된 ACE</span><span class="sxs-lookup"><span data-stu-id="99b50-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="99b50-107">ACE</span><span class="sxs-lookup"><span data-stu-id="99b50-107">ACE</span></span></th>
<th><span data-ttu-id="99b50-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="99b50-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="99b50-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="99b50-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="99b50-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="99b50-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="99b50-111">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="99b50-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="99b50-112">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="99b50-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99b50-113">컨테이너 읽기(상속되지 않음)</span><span class="sxs-lookup"><span data-stu-id="99b50-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="99b50-114"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-115"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-116">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-116">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-117">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-117">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-118">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99b50-119">사용자 PropertySet User-Account-Restrictions 읽기</span><span class="sxs-lookup"><span data-stu-id="99b50-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="99b50-120"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-121">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-121">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-122">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-122">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-123">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-123">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-124">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99b50-125">사용자 PropertySet Personal-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="99b50-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="99b50-126"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-127">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-127">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-128">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-128">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-129">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-129">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-130">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99b50-131">사용자 PropertySet General-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="99b50-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="99b50-132"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-133">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-133">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-134">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-134">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-135">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-135">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-136">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99b50-137">사용자 PropertySet Public-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="99b50-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="99b50-138"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-139">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-139">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-140">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-140">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-141">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-141">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-142">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99b50-143">사용자 PropertySet RTCUserSearchProperty-Set 읽기</span><span class="sxs-lookup"><span data-stu-id="99b50-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="99b50-144"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-145">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-145">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-146">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-146">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-147">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-147">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-148"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99b50-149">사용자 PropertySet RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="99b50-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="99b50-150"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-151">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-151">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-152">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-152">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-153">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-153">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-154">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99b50-155">사용자 Property Proxy-Addresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="99b50-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="99b50-156">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-156">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-157">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-157">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-158"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-159">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-159">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-160">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99b50-161">사용자 PropertySet RTCUserSearchProperty-Set 쓰기</span><span class="sxs-lookup"><span data-stu-id="99b50-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="99b50-162">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-162">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-163">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-163">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-164"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-165">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-165">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-166">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="99b50-167">사용자 PropertySet RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="99b50-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="99b50-168">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-168">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-169">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-169">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-170"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-171">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-171">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-172">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="99b50-173">모든 Active Directory 개체의 PropertySet DS-Replication-Get-Changes 읽기</span><span class="sxs-lookup"><span data-stu-id="99b50-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="99b50-174">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-174">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-175">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-175">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-176">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-176">No</span></span></p></td>
<td><p><span data-ttu-id="99b50-177"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-178">아니요</span><span class="sxs-lookup"><span data-stu-id="99b50-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="99b50-p102">다음 표에는 도메인 준비가 세 개의 기본 제공 컨테이너인 사용자, 컴퓨터 및 도메인 컨트롤러에 만드는 ACE가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="99b50-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="99b50-181">기본 제공 컨테이너에 추가 된 Ace</span><span class="sxs-lookup"><span data-stu-id="99b50-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="99b50-182">ACE</span><span class="sxs-lookup"><span data-stu-id="99b50-182">ACE</span></span></th>
<th><span data-ttu-id="99b50-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="99b50-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="99b50-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="99b50-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="99b50-185">컨테이너 읽기(상속되지 않음)</span><span class="sxs-lookup"><span data-stu-id="99b50-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="99b50-186"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="99b50-187"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="99b50-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

