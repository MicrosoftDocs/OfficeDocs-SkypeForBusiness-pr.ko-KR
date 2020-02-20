---
title: 'Lync Server 2013: 부여-CsSetupPermission을 통해 변경한 내용'
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
ms.openlocfilehash: 12c9431e413428080f72d34510cdb3879e26e7cf
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-cssetuppermission-in-lync-server-2013"></a><span data-ttu-id="7fef8-102">Lync Server 2013의 부여-CsSetupPermission에서 수행한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="7fef8-102">Changes made by Grant-CsSetupPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fef8-103">_**마지막으로 수정 된 항목:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="7fef8-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="7fef8-104">설치를 위임 하려면 특정 Active Directory OU (조직 구성 단위)에 대 한 RTCUniversalServerAdmins 유니버설 그룹에 사용 권한을 부여 하 여 해당 OU에 있는 RTCUniversalServerAdmins 그룹의 구성원이 지정 된에 Lync Server 2013을 설치할 수 있도록 합니다. domain Admins 그룹의 구성원이 아닌 도메인</span><span class="sxs-lookup"><span data-stu-id="7fef8-104">To delegate setup, you can grant permissions to the RTCUniversalServerAdmins universal group for a specific Active Directory organizational unit (OU), enabling members of the RTCUniversalServerAdmins group in that OU to install Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="7fef8-105">**Grant-CsSetupPermission** cmdlet을 실행하면 다음 표에 지정된 것과 같이 OU의 RTCUniversalServerAdmins 그룹에 사용 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fef8-105">The **Grant-CsSetupPermission** cmdlet grants the RTCUniversalServerAdmins group permissions on an OU, as specified in the following table:</span></span>

### <a name="permissions-granted-to-objects-in-the-ou"></a><span data-ttu-id="7fef8-106">OU의 개체에 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="7fef8-106">Permissions granted to Objects in the OU</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7fef8-107">사용 권한의 적용 대상</span><span class="sxs-lookup"><span data-stu-id="7fef8-107">Permissions apply to:</span></span></th>
<th><span data-ttu-id="7fef8-108">부여받는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="7fef8-108">Permissions granted are:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7fef8-109">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7fef8-109">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="7fef8-110">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="7fef8-110">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fef8-111">servicePrincipalName 읽기</span><span class="sxs-lookup"><span data-stu-id="7fef8-111">Read servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="7fef8-112">servicePrincipalName 쓰기</span><span class="sxs-lookup"><span data-stu-id="7fef8-112">Write servicePrincipalName</span></span></p></li>
<li><p><span data-ttu-id="7fef8-113">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="7fef8-113">Delete tree</span></span></p></li>
<li><p><span data-ttu-id="7fef8-114">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="7fef8-114">Replicating directory changes</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fef8-115">하위 serviceConnectionPoint 개체</span><span class="sxs-lookup"><span data-stu-id="7fef8-115">Descendant serviceConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="7fef8-116">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="7fef8-116">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fef8-117">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="7fef8-117">Read permissions</span></span></p></li>
<li><p><span data-ttu-id="7fef8-118">사용 권한 쓰기</span><span class="sxs-lookup"><span data-stu-id="7fef8-118">Write permissions</span></span></p></li>
<li><p><span data-ttu-id="7fef8-119">자식 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="7fef8-119">Create child</span></span></p></li>
<li><p><span data-ttu-id="7fef8-120">자식 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="7fef8-120">Delete child</span></span></p></li>
<li><p><span data-ttu-id="7fef8-121">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="7fef8-121">List contents</span></span></p></li>
<li><p><span data-ttu-id="7fef8-122">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="7fef8-122">Write property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-123">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="7fef8-123">Read property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-124">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="7fef8-124">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fef8-125">하위 msRTCSIP-Server 개체</span><span class="sxs-lookup"><span data-stu-id="7fef8-125">Descendant msRTCSIP-Server objects</span></span></p></td>
<td><p><span data-ttu-id="7fef8-126">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="7fef8-126">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fef8-127">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="7fef8-127">Write property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-128">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="7fef8-128">Read property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-129">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="7fef8-129">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fef8-130">하위 msRTCSIP-WebComponents 개체</span><span class="sxs-lookup"><span data-stu-id="7fef8-130">Descendant msRTCSIP-WebComponents objects</span></span></p></td>
<td><p><span data-ttu-id="7fef8-131">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="7fef8-131">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fef8-132">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="7fef8-132">Write property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-133">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="7fef8-133">Read property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-134">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="7fef8-134">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fef8-135">하위 msRTCSIP-MCU 개체</span><span class="sxs-lookup"><span data-stu-id="7fef8-135">Descendant msRTCSIP-MCU objects</span></span></p></td>
<td><p><span data-ttu-id="7fef8-136">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="7fef8-136">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fef8-137">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="7fef8-137">Write property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-138">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="7fef8-138">Read property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-139">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="7fef8-139">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fef8-140">하위 msRTCSIP-MediationServer 개체</span><span class="sxs-lookup"><span data-stu-id="7fef8-140">Descendant msRTCSIP-MediationServer objects</span></span></p></td>
<td><p><span data-ttu-id="7fef8-141">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="7fef8-141">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fef8-142">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="7fef8-142">Write property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-143">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="7fef8-143">Read property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-144">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="7fef8-144">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fef8-145">하위 msRTCSIP-ApplicationServer 개체</span><span class="sxs-lookup"><span data-stu-id="7fef8-145">Descendant msRTCSIP-ApplicationServer objects</span></span></p></td>
<td><p><span data-ttu-id="7fef8-146">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="7fef8-146">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fef8-147">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="7fef8-147">Write property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-148">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="7fef8-148">Read property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-149">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="7fef8-149">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7fef8-150">하위 msRTCSIP-ConnectionPoint 개체</span><span class="sxs-lookup"><span data-stu-id="7fef8-150">Descendant msRTCSIP-ConnectionPoint objects</span></span></p></td>
<td><p><span data-ttu-id="7fef8-151">특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="7fef8-151">Special access:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fef8-152">속성 쓰기</span><span class="sxs-lookup"><span data-stu-id="7fef8-152">Write property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-153">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="7fef8-153">Read property</span></span></p></li>
<li><p><span data-ttu-id="7fef8-154">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="7fef8-154">Delete tree</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7fef8-155">하위 Computer 개체</span><span class="sxs-lookup"><span data-stu-id="7fef8-155">Descendant Computer objects</span></span></p></td>
<td><p><span data-ttu-id="7fef8-156">serviceConnectionPoint에 대한 특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="7fef8-156">Special access for serviceConnectionPoint:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fef8-157">자식 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="7fef8-157">Create child objects</span></span></p></li>
<li><p><span data-ttu-id="7fef8-158">자식 개체 삭제</span><span class="sxs-lookup"><span data-stu-id="7fef8-158">Delete child objects</span></span></p></li>
<li><p><span data-ttu-id="7fef8-159">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="7fef8-159">Delete tree</span></span></p></li>
</ul>
<p><span data-ttu-id="7fef8-160">공개 정보에 대한 특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="7fef8-160">Special access for public information:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fef8-161">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="7fef8-161">Read property</span></span></p></li>
</ul>
<p><span data-ttu-id="7fef8-162">DNS 호스트 이름에 대한 특수 액세스 권한:</span><span class="sxs-lookup"><span data-stu-id="7fef8-162">Special access for DNS host name:</span></span></p>
<ul>
<li><p><span data-ttu-id="7fef8-163">속성 읽기</span><span class="sxs-lookup"><span data-stu-id="7fef8-163">Read property</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

