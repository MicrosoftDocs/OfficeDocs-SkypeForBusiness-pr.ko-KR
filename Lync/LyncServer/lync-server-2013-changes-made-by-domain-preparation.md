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
ms.openlocfilehash: 74fe383cf773e1cdfa645a3f8513167fd7472958
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181421"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="bf97f-102">Lync Server 2013에서 도메인 준비로 인 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="bf97f-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bf97f-103">_**마지막으로 수정 된 항목:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="bf97f-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="bf97f-p101">다음 표에는 도메인 준비가 도메인 루트에 대해 만든 ACE(액세스 제어 항목)가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf97f-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="bf97f-106">도메인 루트에 추가된 ACE</span><span class="sxs-lookup"><span data-stu-id="bf97f-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="bf97f-107">ACE</span><span class="sxs-lookup"><span data-stu-id="bf97f-107">ACE</span></span></th>
<th><span data-ttu-id="bf97f-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="bf97f-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="bf97f-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="bf97f-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="bf97f-110">RTCUniversal UserAdmins</span><span class="sxs-lookup"><span data-stu-id="bf97f-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="bf97f-111">RTCHSUniversal-서비스</span><span class="sxs-lookup"><span data-stu-id="bf97f-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="bf97f-112">인증 된 사용자</span><span class="sxs-lookup"><span data-stu-id="bf97f-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf97f-113">컨테이너 읽기(상속되지 않음)</span><span class="sxs-lookup"><span data-stu-id="bf97f-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="bf97f-114"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-115"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-116">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-116">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-117">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-117">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-118">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf97f-119">사용자 PropertySet User-Account-Restrictions 읽기</span><span class="sxs-lookup"><span data-stu-id="bf97f-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="bf97f-120"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-121">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-121">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-122">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-122">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-123">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-123">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-124">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf97f-125">사용자 PropertySet Personal-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="bf97f-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="bf97f-126"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-127">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-127">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-128">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-128">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-129">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-129">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-130">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf97f-131">사용자 PropertySet General-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="bf97f-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="bf97f-132"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-133">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-133">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-134">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-134">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-135">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-135">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-136">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf97f-137">사용자 PropertySet Public-Information 읽기</span><span class="sxs-lookup"><span data-stu-id="bf97f-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="bf97f-138"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-139">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-139">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-140">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-140">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-141">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-141">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-142">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf97f-143">사용자 PropertySet RTCUserSearchProperty-Set 읽기</span><span class="sxs-lookup"><span data-stu-id="bf97f-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="bf97f-144"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-145">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-145">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-146">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-146">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-147">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-147">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-148"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf97f-149">사용자 PropertySet RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="bf97f-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="bf97f-150"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-151">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-151">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-152">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-152">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-153">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-153">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-154">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf97f-155">사용자 Property Proxy-Addresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="bf97f-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="bf97f-156">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-156">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-157">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-157">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-158"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-159">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-159">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-160">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf97f-161">사용자 PropertySet RTCUserSearchProperty-Set 쓰기</span><span class="sxs-lookup"><span data-stu-id="bf97f-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="bf97f-162">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-162">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-163">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-163">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-164"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-165">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-165">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-166">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bf97f-167">사용자 PropertySet RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="bf97f-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="bf97f-168">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-168">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-169">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-169">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-170"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-171">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-171">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-172">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bf97f-173">모든 Active Directory 개체의 PropertySet DS-Replication-Get-Changes 읽기</span><span class="sxs-lookup"><span data-stu-id="bf97f-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="bf97f-174">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-174">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-175">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-175">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-176">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-176">No</span></span></p></td>
<td><p><span data-ttu-id="bf97f-177"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-178">아니요</span><span class="sxs-lookup"><span data-stu-id="bf97f-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bf97f-p102">다음 표에는 도메인 준비가 세 개의 기본 제공 컨테이너인 사용자, 컴퓨터 및 도메인 컨트롤러에 만드는 ACE가 나열되어 있습니다. 다른 언급이 없는 경우 모든 ACE는 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf97f-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="bf97f-181">기본 제공 컨테이너에 추가 된 Ace</span><span class="sxs-lookup"><span data-stu-id="bf97f-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bf97f-182">ACE</span><span class="sxs-lookup"><span data-stu-id="bf97f-182">ACE</span></span></th>
<th><span data-ttu-id="bf97f-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="bf97f-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="bf97f-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="bf97f-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bf97f-185">컨테이너 읽기(상속되지 않음)</span><span class="sxs-lookup"><span data-stu-id="bf97f-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="bf97f-186"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="bf97f-187"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="bf97f-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

