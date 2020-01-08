---
title: 'Lync Server 2013: 도메인 준비에의 한 변경 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b674e2c3d65aeda22838dca08ac5b016fa83359
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="b3328-102">Lync Server 2013에서 도메인 준비에의 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="b3328-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3328-103">_**마지막으로 수정한 주제:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="b3328-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="b3328-104">다음 표에는 도메인 준비에서 도메인 루트에 만드는 Ace (액세스 제어 항목)가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3328-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="b3328-105">다른 언급이 없는 한 모든 Ace는 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3328-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="b3328-106">도메인 루트에 추가 된 Ace</span><span class="sxs-lookup"><span data-stu-id="b3328-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="b3328-107">ACE</span><span class="sxs-lookup"><span data-stu-id="b3328-107">ACE</span></span></th>
<th><span data-ttu-id="b3328-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="b3328-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="b3328-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="b3328-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="b3328-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="b3328-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="b3328-111">RTCHSUniversal 서비스</span><span class="sxs-lookup"><span data-stu-id="b3328-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="b3328-112">인증 된 사용자</span><span class="sxs-lookup"><span data-stu-id="b3328-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3328-113">컨테이너 읽기 (상속 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="b3328-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="b3328-114"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-115"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-116">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-116">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-117">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-117">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-118">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3328-119">사용자 PropertySet 사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="b3328-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="b3328-120"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-121">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-121">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-122">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-122">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-123">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-123">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-124">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3328-125">사용자 PropertySet 개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="b3328-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="b3328-126"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-127">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-127">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-128">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-128">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-129">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-129">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-130">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3328-131">사용자 PropertySet 일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="b3328-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="b3328-132"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-133">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-133">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-134">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-134">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-135">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-135">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-136">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3328-137">사용자 PropertySet 공개 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="b3328-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="b3328-138"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-139">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-139">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-140">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-140">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-141">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-141">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-142">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3328-143">PropertySet 사용자 읽기 RTCUserSearchProperty-설정</span><span class="sxs-lookup"><span data-stu-id="b3328-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="b3328-144"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-145">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-145">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-146">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-146">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-147">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-147">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-148"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3328-149">사용자 PropertySet RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="b3328-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="b3328-150"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-151">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-151">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-152">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-152">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-153">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-153">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-154">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3328-155">사용자 속성 프록시-주소 쓰기</span><span class="sxs-lookup"><span data-stu-id="b3328-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="b3328-156">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-156">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-157">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-157">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-158"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-159">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-159">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-160">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3328-161">PropertySet 사용자 쓰기 RTCUserSearchProperty-설정</span><span class="sxs-lookup"><span data-stu-id="b3328-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="b3328-162">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-162">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-163">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-163">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-164"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-165">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-165">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-166">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3328-167">사용자 PropertySet RTCPropertySet에 쓰기</span><span class="sxs-lookup"><span data-stu-id="b3328-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="b3328-168">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-168">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-169">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-169">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-170"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-171">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-171">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-172">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3328-173">PropertySet 읽기-모든 Active Directory 개체의 가져오기-복제-변경</span><span class="sxs-lookup"><span data-stu-id="b3328-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="b3328-174">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-174">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-175">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-175">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-176">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-176">No</span></span></p></td>
<td><p><span data-ttu-id="b3328-177"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-178">아니요</span><span class="sxs-lookup"><span data-stu-id="b3328-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b3328-179">다음 표에는 세 가지 기본 제공 컨테이너 (사용자, 컴퓨터 및 도메인 컨트롤러)에서 도메인 준비가 만드는 Ace가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3328-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="b3328-180">다른 언급이 없는 한 모든 Ace는 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3328-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="b3328-181">기본 제공 컨테이너에 Ace가 추가 됨</span><span class="sxs-lookup"><span data-stu-id="b3328-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3328-182">ACE</span><span class="sxs-lookup"><span data-stu-id="b3328-182">ACE</span></span></th>
<th><span data-ttu-id="b3328-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="b3328-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="b3328-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="b3328-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3328-185">컨테이너 읽기 (상속 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="b3328-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="b3328-186"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="b3328-187"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="b3328-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

