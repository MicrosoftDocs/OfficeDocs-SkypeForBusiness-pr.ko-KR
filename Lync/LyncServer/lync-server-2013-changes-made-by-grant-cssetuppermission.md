---
title: 'Lync Server 2013: 권한 부여-CsSetupPermission에의 한 변경 내용'
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
ms.openlocfilehash: 9d82b896f1d6d1da1184bfa61d7352c9b4803a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742358"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="b288b-102">Lync Server 2013의 허용-Cssetupsetuppermission에의 한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="b288b-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b288b-103">_**마지막으로 수정한 주제:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="b288b-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="b288b-104">설치를 위임 하려면 특정 Active Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 유니버설 그룹에 대 한 사용 권한을 부여 하 여 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원이 지정 된 사용자의 Lync Server 2013을 설치할 수 있도록 합니다. 도메인 관리자 그룹의 구성원이 되지 않고 도메인</span><span class="sxs-lookup"><span data-stu-id="b288b-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="b288b-105">**부여-CsSetupPermission** cmdlet은 다음 표에 지정 된 대로 OU에 대 한 RTCUniversalServerAdmins 그룹 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="b288b-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="b288b-106">OU의 개체에 부여 된 사용 권한</span><span class="sxs-lookup"><span data-stu-id="b288b-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b288b-107">사용 권한은 다음에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b288b-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="b288b-108">부여 된 사용 권한은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b288b-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b288b-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="b288b-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="b288b-110">특별 액세스:</span><span class="sxs-lookup"><span data-stu-id="b288b-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b288b-111">ServicePrincipalName 읽기</span><span class="sxs-lookup"><span data-stu-id="b288b-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="b288b-112">ServicePrincipalName 쓰기</span><span class="sxs-lookup"><span data-stu-id="b288b-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="b288b-113">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="b288b-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="b288b-114">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="b288b-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b288b-115">하위 항목 serviceConnectionPoint 개체</span><span class="sxs-lookup"><span data-stu-id="b288b-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="b288b-116">특별 액세스:</span><span class="sxs-lookup"><span data-stu-id="b288b-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b288b-117">읽기 권한</span><span class="sxs-lookup"><span data-stu-id="b288b-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="b288b-118">쓰기 권한</span><span class="sxs-lookup"><span data-stu-id="b288b-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="b288b-119">하위 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="b288b-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="b288b-120">하위 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="b288b-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="b288b-121">내용 목록</span><span class="sxs-lookup"><span data-stu-id="b288b-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="b288b-122">쓰기 속성</span><span class="sxs-lookup"><span data-stu-id="b288b-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="b288b-123">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="b288b-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="b288b-124">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="b288b-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b288b-125">하위 항목 msRTCSIP-서버 개체</span><span class="sxs-lookup"><span data-stu-id="b288b-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="b288b-126">특별 액세스:</span><span class="sxs-lookup"><span data-stu-id="b288b-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b288b-127">쓰기 속성</span><span class="sxs-lookup"><span data-stu-id="b288b-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="b288b-128">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="b288b-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="b288b-129">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="b288b-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b288b-130">하위 msRTCSIP-WebComponents 개체</span><span class="sxs-lookup"><span data-stu-id="b288b-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="b288b-131">특별 액세스:</span><span class="sxs-lookup"><span data-stu-id="b288b-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b288b-132">쓰기 속성</span><span class="sxs-lookup"><span data-stu-id="b288b-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="b288b-133">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="b288b-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="b288b-134">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="b288b-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b288b-135">하위 항목 msRTCSIP-MCU 개체</span><span class="sxs-lookup"><span data-stu-id="b288b-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="b288b-136">특별 액세스:</span><span class="sxs-lookup"><span data-stu-id="b288b-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b288b-137">쓰기 속성</span><span class="sxs-lookup"><span data-stu-id="b288b-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="b288b-138">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="b288b-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="b288b-139">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="b288b-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b288b-140">하위 항목 msRTCSIP-MediationServer 개체</span><span class="sxs-lookup"><span data-stu-id="b288b-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="b288b-141">특별 액세스:</span><span class="sxs-lookup"><span data-stu-id="b288b-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b288b-142">쓰기 속성</span><span class="sxs-lookup"><span data-stu-id="b288b-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="b288b-143">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="b288b-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="b288b-144">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="b288b-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b288b-145">하위 항목 msRTCSIP-ApplicationServer 개체</span><span class="sxs-lookup"><span data-stu-id="b288b-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="b288b-146">특별 액세스:</span><span class="sxs-lookup"><span data-stu-id="b288b-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b288b-147">쓰기 속성</span><span class="sxs-lookup"><span data-stu-id="b288b-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="b288b-148">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="b288b-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="b288b-149">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="b288b-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b288b-150">하위 msRTCSIP-ConnectionPoint 개체</span><span class="sxs-lookup"><span data-stu-id="b288b-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="b288b-151">특별 액세스:</span><span class="sxs-lookup"><span data-stu-id="b288b-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="b288b-152">쓰기 속성</span><span class="sxs-lookup"><span data-stu-id="b288b-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="b288b-153">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="b288b-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="b288b-154">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="b288b-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b288b-155">하위 컴퓨터 개체</span><span class="sxs-lookup"><span data-stu-id="b288b-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="b288b-156">ServiceConnectionPoint에 대 한 특수 액세스:</span><span class="sxs-lookup"><span data-stu-id="b288b-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="b288b-157">자식 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="b288b-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="b288b-158">자식 개체 삭제</span><span class="sxs-lookup"><span data-stu-id="b288b-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="b288b-159">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="b288b-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="b288b-160">공개 정보에 대 한 특별 액세스:</span><span class="sxs-lookup"><span data-stu-id="b288b-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="b288b-161">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="b288b-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="b288b-162">DNS 호스트 이름에 대 한 특수 액세스:</span><span class="sxs-lookup"><span data-stu-id="b288b-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="b288b-163">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="b288b-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

