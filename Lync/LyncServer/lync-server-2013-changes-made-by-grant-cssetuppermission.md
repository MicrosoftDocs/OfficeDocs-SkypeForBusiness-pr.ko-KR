---
title: 'Lync Server 2013: Grant-CsSetupPermission에서 변경한 내용'
description: 'Lync Server 2013: 부여-CsSetupPermission을 통해 변경한 내용입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsSetupPermission
ms:assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205250(v=OCS.15)
ms:contentKeyID: 48185360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2a9156c977c993dd32e38fc6816bd08d3f65c1f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543604"
---
# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="353e0-103">Lync Server 2013의 Grant-CsSetupPermission에의 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="353e0-103">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="353e0-104">_**마지막으로 수정 된 항목:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="353e0-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="353e0-105">설치를 위임 하려면 특정 Active Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 유니버설 그룹에 사용 권한을 부여 하 여 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원이 Domain Admins 그룹의 구성원이 아닌 지정 된 도메인에 Lync Server 2013을 설치할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-105">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="353e0-106">**Grant-CsSetupPermission** cmdlet을 실행하면 다음 표에 지정된 것과 같이 OU의 RTCUniversalServerAdmins 그룹에 사용 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e0-106">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="353e0-107">OU의 개체에 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="353e0-107">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="353e0-108">사용 권한의 적용 대상</span><span class="sxs-lookup"><span data-stu-id="353e0-108">Permissions apply to:</span></span></th>
<th><span data-ttu-id="353e0-109">부여받는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="353e0-109">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="353e0-110">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="353e0-110">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="353e0-111">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="353e0-111">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="353e0-112">servicePrincipalName 읽기</span><span class="sxs-lookup"><span data-stu-id="353e0-112">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="353e0-113">servicePrincipalName 쓰기</span><span class="sxs-lookup"><span data-stu-id="353e0-113">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="353e0-114">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="353e0-114">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="353e0-115">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="353e0-115">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="353e0-116">하위 serviceConnectionPoint 개체</span><span class="sxs-lookup"><span data-stu-id="353e0-116">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="353e0-117">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="353e0-117">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="353e0-118">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="353e0-118">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="353e0-119">사용 권한 쓰기</span><span class="sxs-lookup"><span data-stu-id="353e0-119">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="353e0-120">자식 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="353e0-120">Create child</span></span></p></li>
<li><p><span data-ttu-id="353e0-121">자식 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="353e0-121">Delete child</span></span></p></li>
<li><p><span data-ttu-id="353e0-122">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="353e0-122">List contents</span></span></p></li>
<li><p><span data-ttu-id="353e0-123">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="353e0-123">Write property</span></span></p></li>
<li><p><span data-ttu-id="353e0-124">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="353e0-124">Read property</span></span></p></li>
<li><p><span data-ttu-id="353e0-125">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="353e0-125">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="353e0-126">하위 msRTCSIP-Server 개체</span><span class="sxs-lookup"><span data-stu-id="353e0-126">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="353e0-127">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="353e0-127">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="353e0-128">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="353e0-128">Write property</span></span></p></li>
<li><p><span data-ttu-id="353e0-129">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="353e0-129">Read property</span></span></p></li>
<li><p><span data-ttu-id="353e0-130">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="353e0-130">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="353e0-131">하위 msRTCSIP-WebComponents 개체</span><span class="sxs-lookup"><span data-stu-id="353e0-131">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="353e0-132">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="353e0-132">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="353e0-133">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="353e0-133">Write property</span></span></p></li>
<li><p><span data-ttu-id="353e0-134">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="353e0-134">Read property</span></span></p></li>
<li><p><span data-ttu-id="353e0-135">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="353e0-135">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="353e0-136">하위 msRTCSIP-MCU 개체</span><span class="sxs-lookup"><span data-stu-id="353e0-136">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="353e0-137">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="353e0-137">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="353e0-138">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="353e0-138">Write property</span></span></p></li>
<li><p><span data-ttu-id="353e0-139">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="353e0-139">Read property</span></span></p></li>
<li><p><span data-ttu-id="353e0-140">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="353e0-140">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="353e0-141">하위 msRTCSIP-MediationServer 개체</span><span class="sxs-lookup"><span data-stu-id="353e0-141">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="353e0-142">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="353e0-142">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="353e0-143">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="353e0-143">Write property</span></span></p></li>
<li><p><span data-ttu-id="353e0-144">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="353e0-144">Read property</span></span></p></li>
<li><p><span data-ttu-id="353e0-145">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="353e0-145">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="353e0-146">하위 msRTCSIP-ApplicationServer 개체</span><span class="sxs-lookup"><span data-stu-id="353e0-146">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="353e0-147">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="353e0-147">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="353e0-148">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="353e0-148">Write property</span></span></p></li>
<li><p><span data-ttu-id="353e0-149">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="353e0-149">Read property</span></span></p></li>
<li><p><span data-ttu-id="353e0-150">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="353e0-150">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="353e0-151">하위 msRTCSIP-ConnectionPoint 개체</span><span class="sxs-lookup"><span data-stu-id="353e0-151">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="353e0-152">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="353e0-152">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="353e0-153">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="353e0-153">Write property</span></span></p></li>
<li><p><span data-ttu-id="353e0-154">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="353e0-154">Read property</span></span></p></li>
<li><p><span data-ttu-id="353e0-155">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="353e0-155">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="353e0-156">하위 Computer 개체</span><span class="sxs-lookup"><span data-stu-id="353e0-156">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="353e0-157">serviceConnectionPoint에 대한 특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="353e0-157">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="353e0-158">자식 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="353e0-158">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="353e0-159">자식 개체 삭제</span><span class="sxs-lookup"><span data-stu-id="353e0-159">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="353e0-160">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="353e0-160">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="353e0-161">공개 정보에 대한 특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="353e0-161">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="353e0-162">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="353e0-162">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="353e0-163">DNS 호스트 이름에 대한 특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="353e0-163">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="353e0-164">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="353e0-164">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

