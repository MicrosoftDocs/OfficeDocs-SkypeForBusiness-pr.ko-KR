---
title: 'Lync Server 2013: 도메인 준비에의 한 변경 사항'
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
ms.openlocfilehash: cbdd1fa1fbb5bd7a396e17f478326a9e4dd700f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="3b073-102">Lync Server 2013에서 도메인 준비에의 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="3b073-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3b073-103">_**마지막으로 수정한 주제:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="3b073-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="3b073-104">다음 표에는 도메인 준비에서 도메인 루트에 만드는 Ace (액세스 제어 항목)가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b073-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="3b073-105">다른 언급이 없는 한 모든 Ace는 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b073-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="3b073-106">도메인 루트에 추가 된 Ace</span><span class="sxs-lookup"><span data-stu-id="3b073-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="3b073-107">ACE</span><span class="sxs-lookup"><span data-stu-id="3b073-107">ACE</span></span></th>
<th><span data-ttu-id="3b073-108">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="3b073-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="3b073-109">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="3b073-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="3b073-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="3b073-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="3b073-111">RTCHSUniversal 서비스</span><span class="sxs-lookup"><span data-stu-id="3b073-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="3b073-112">인증 된 사용자</span><span class="sxs-lookup"><span data-stu-id="3b073-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b073-113">컨테이너 읽기 (상속 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="3b073-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="3b073-114"><strong>'</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-115"><strong>'</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-116">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-116">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-117">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-117">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-118">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b073-119">사용자 PropertySet 사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="3b073-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3b073-120"><strong>'</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-121">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-121">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-122">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-122">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-123">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-123">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-124">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b073-125">사용자 PropertySet 개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="3b073-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="3b073-126"><strong>'</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-127">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-127">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-128">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-128">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-129">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-129">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-130">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b073-131">사용자 PropertySet 일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="3b073-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="3b073-132"><strong>'</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-133">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-133">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-134">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-134">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-135">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-135">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-136">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b073-137">사용자 PropertySet 공개 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="3b073-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="3b073-138"><strong>'</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-139">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-139">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-140">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-140">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-141">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-141">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-142">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b073-143">PropertySet 사용자 읽기 RTCUserSearchProperty-설정</span><span class="sxs-lookup"><span data-stu-id="3b073-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="3b073-144"><strong>'</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-145">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-145">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-146">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-146">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-147">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-147">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-148"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b073-149">사용자 PropertySet RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="3b073-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="3b073-150"><strong>'</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-151">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-151">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-152">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-152">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-153">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-153">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-154">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b073-155">사용자 속성 프록시-주소 쓰기</span><span class="sxs-lookup"><span data-stu-id="3b073-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="3b073-156">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-156">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-157">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-157">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-158"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-159">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-159">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-160">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b073-161">PropertySet 사용자 쓰기 RTCUserSearchProperty-설정</span><span class="sxs-lookup"><span data-stu-id="3b073-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="3b073-162">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-162">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-163">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-163">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-164"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-165">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-165">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-166">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3b073-167">사용자 PropertySet RTCPropertySet에 쓰기</span><span class="sxs-lookup"><span data-stu-id="3b073-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="3b073-168">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-168">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-169">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-169">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-170"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-171">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-171">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-172">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3b073-173">PropertySet 읽기-모든 Active Directory 개체의 가져오기-복제-변경</span><span class="sxs-lookup"><span data-stu-id="3b073-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="3b073-174">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-174">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-175">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-175">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-176">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-176">No</span></span></p></td>
<td><p><span data-ttu-id="3b073-177"><strong>예</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-178">아니요</span><span class="sxs-lookup"><span data-stu-id="3b073-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3b073-179">다음 표에는 세 가지 기본 제공 컨테이너 (사용자, 컴퓨터 및 도메인 컨트롤러)에서 도메인 준비가 만드는 Ace가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b073-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="3b073-180">다른 언급이 없는 한 모든 Ace는 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b073-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="3b073-181">기본 제공 컨테이너에 Ace가 추가 됨</span><span class="sxs-lookup"><span data-stu-id="3b073-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3b073-182">ACE</span><span class="sxs-lookup"><span data-stu-id="3b073-182">ACE</span></span></th>
<th><span data-ttu-id="3b073-183">RTCUniversal-UserReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="3b073-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="3b073-184">RTCUniversal-ServerReadOnly-Group</span><span class="sxs-lookup"><span data-stu-id="3b073-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3b073-185">컨테이너 읽기 (상속 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="3b073-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="3b073-186"><strong>'</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3b073-187"><strong>'</strong></span><span class="sxs-lookup"><span data-stu-id="3b073-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

