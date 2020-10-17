---
title: 'Lync Server 2013: Grant-CsOUPermission에서 변경한 내용'
description: 'Lync Server 2013: 부여-CsOUPermission을 통해 변경한 내용입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10d3db0e9dde380628690bc016e2b4bd2ec85b54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543614"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="1b7c4-103">Lync Server 2013의 Grant-CsOUPermission에의 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="1b7c4-103">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b7c4-104">_**마지막으로 수정 된 항목:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="1b7c4-104">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="1b7c4-105">Lync Server 2013 관리를 위임 하기 위해 포리스트 준비로 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 아닌 Ou에 액세스할 수 있도록 지정 된 Ou (조직 구성 단위)에 사용 권한을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7c4-105">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="1b7c4-106">**Grant-CsOuPermission** cmdlet을 사용하면 다음 표에 지정된 대로 지정한 OU의 개체에 대한 사용 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b7c4-106">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="1b7c4-107">User 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="1b7c4-107">Granting Permission for User Objects</span></span>

<span data-ttu-id="1b7c4-108">OU의 User 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7c4-108">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="1b7c4-109">User 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="1b7c4-109">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b7c4-110">그룹</span><span class="sxs-lookup"><span data-stu-id="1b7c4-110">Group</span></span></th>
<th><span data-ttu-id="1b7c4-111">사용 권한</span><span class="sxs-lookup"><span data-stu-id="1b7c4-111">Permission</span></span></th>
<th><span data-ttu-id="1b7c4-112">적용 대상</span><span class="sxs-lookup"><span data-stu-id="1b7c4-112">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-113">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1b7c4-113">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-114">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="1b7c4-114">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-115">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-115">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7c4-116">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-116">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-117">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="1b7c4-117">List contents</span></span></p>
<p><span data-ttu-id="1b7c4-118">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-118">Read all properties</span></span></p>
<p><span data-ttu-id="1b7c4-119">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-119">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-120">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-120">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-121">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-121">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-122">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="1b7c4-122">List contents</span></span></p>
<p><span data-ttu-id="1b7c4-123">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-123">Read all properties</span></span></p>
<p><span data-ttu-id="1b7c4-124">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-124">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-125">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-125">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7c4-126">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-126">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-127">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-127">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-128">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-128">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-129">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-129">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-130">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-130">Read Public-Information</span></span></p>
<p><span data-ttu-id="1b7c4-131">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-131">Read General-Information</span></span></p>
<p><span data-ttu-id="1b7c4-132">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-132">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-133">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="1b7c4-133">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1b7c4-134">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-135">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-135">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-136">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-136">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1b7c4-137">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-137">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-138">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-138">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-139">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-139">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-140">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="1b7c4-140">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="1b7c4-141">Computer 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="1b7c4-141">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="1b7c4-142">OU의 Computer 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7c4-142">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="1b7c4-143">Computer 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="1b7c4-143">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b7c4-144">그룹</span><span class="sxs-lookup"><span data-stu-id="1b7c4-144">Group</span></span></th>
<th><span data-ttu-id="1b7c4-145">사용 권한</span><span class="sxs-lookup"><span data-stu-id="1b7c4-145">Permission</span></span></th>
<th><span data-ttu-id="1b7c4-146">적용 대상</span><span class="sxs-lookup"><span data-stu-id="1b7c4-146">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-147">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1b7c4-147">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-148">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="1b7c4-148">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-149">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-149">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7c4-150">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-150">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-151">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="1b7c4-151">List contents</span></span></p>
<p><span data-ttu-id="1b7c4-152">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-152">Read all properties</span></span></p>
<p><span data-ttu-id="1b7c4-153">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-153">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-154">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-154">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-155">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-155">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-156">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="1b7c4-156">List contents</span></span></p>
<p><span data-ttu-id="1b7c4-157">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-157">Read all properties</span></span></p>
<p><span data-ttu-id="1b7c4-158">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-158">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-159">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-159">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7c4-160">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-160">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-161">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-161">Read Public-Information</span></span></p>
<p><span data-ttu-id="1b7c4-162">Validated-DNS-Host-Name 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-162">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-163">하위 Computer 개체</span><span class="sxs-lookup"><span data-stu-id="1b7c4-163">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-164">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1b7c4-164">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-165">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-165">Read Public-Information</span></span></p>
<p><span data-ttu-id="1b7c4-166">Validated-DNS-Host-Name 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-166">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-167">하위 Computer 개체</span><span class="sxs-lookup"><span data-stu-id="1b7c4-167">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="1b7c4-168">Contact 또는 AppContact 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="1b7c4-168">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="1b7c4-169">OU의 Contact 또는 AppContact 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7c4-169">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="1b7c4-170">Contact 또는 AppContact 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="1b7c4-170">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b7c4-171">그룹</span><span class="sxs-lookup"><span data-stu-id="1b7c4-171">Group</span></span></th>
<th><span data-ttu-id="1b7c4-172">사용 권한</span><span class="sxs-lookup"><span data-stu-id="1b7c4-172">Permission</span></span></th>
<th><span data-ttu-id="1b7c4-173">적용 대상</span><span class="sxs-lookup"><span data-stu-id="1b7c4-173">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-174">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1b7c4-174">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-175">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="1b7c4-175">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-176">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-176">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7c4-177">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-177">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-178">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="1b7c4-178">List contents</span></span></p>
<p><span data-ttu-id="1b7c4-179">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-179">Read all properties</span></span></p>
<p><span data-ttu-id="1b7c4-180">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-180">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-181">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-181">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-182">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-182">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-183">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="1b7c4-183">List contents</span></span></p>
<p><span data-ttu-id="1b7c4-184">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-184">Read all properties</span></span></p>
<p><span data-ttu-id="1b7c4-185">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-185">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-186">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-186">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7c4-187">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-187">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-188">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-188">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-189">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-189">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-190">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-190">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-191">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-191">Read Public-Information</span></span></p>
<p><span data-ttu-id="1b7c4-192">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-192">Read General-Information</span></span></p>
<p><span data-ttu-id="1b7c4-193">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-193">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1b7c4-194">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-194">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-195">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="1b7c4-195">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-196">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1b7c4-196">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-197">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-197">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-198">otherIpPhone 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-198">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="1b7c4-199">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-199">Write displayName</span></span></p>
<p><span data-ttu-id="1b7c4-200">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-200">Write description</span></span></p>
<p><span data-ttu-id="1b7c4-201">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-201">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="1b7c4-202">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-202">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1b7c4-203">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-203">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-204">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-204">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-205">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-205">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-206">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="1b7c4-206">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="1b7c4-207">Device 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="1b7c4-207">Granting Permission for Device Objects</span></span>

<span data-ttu-id="1b7c4-208">OU의 Device 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7c4-208">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="1b7c4-209">Device 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="1b7c4-209">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b7c4-210">그룹</span><span class="sxs-lookup"><span data-stu-id="1b7c4-210">Group</span></span></th>
<th><span data-ttu-id="1b7c4-211">사용 권한</span><span class="sxs-lookup"><span data-stu-id="1b7c4-211">Permission</span></span></th>
<th><span data-ttu-id="1b7c4-212">적용 대상</span><span class="sxs-lookup"><span data-stu-id="1b7c4-212">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-213">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1b7c4-213">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-214">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="1b7c4-214">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-215">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-215">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7c4-216">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-216">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-217">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="1b7c4-217">List contents</span></span></p>
<p><span data-ttu-id="1b7c4-218">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-218">Read all properties</span></span></p>
<p><span data-ttu-id="1b7c4-219">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-219">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-220">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-220">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-221">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-221">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-222">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="1b7c4-222">List contents</span></span></p>
<p><span data-ttu-id="1b7c4-223">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-223">Read all properties</span></span></p>
<p><span data-ttu-id="1b7c4-224">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-224">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-225">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-225">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7c4-226">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-226">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-227">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-227">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-228">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-228">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-229">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-229">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-230">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-230">Read Public-Information</span></span></p>
<p><span data-ttu-id="1b7c4-231">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-231">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1b7c4-232">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-232">Read General-Information</span></span></p>
<p><span data-ttu-id="1b7c4-233">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-233">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-234">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="1b7c4-234">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-235">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1b7c4-235">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-236">자식 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-236">Create child</span></span></p>
<p><span data-ttu-id="1b7c4-237">자식 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="1b7c4-237">Delete child</span></span></p>
<p><span data-ttu-id="1b7c4-238">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="1b7c4-238">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-239">담당자</span><span class="sxs-lookup"><span data-stu-id="1b7c4-239">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7c4-240">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1b7c4-240">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-241">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-241">Write displayName</span></span></p>
<p><span data-ttu-id="1b7c4-242">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-242">Write description</span></span></p>
<p><span data-ttu-id="1b7c4-243">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-243">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-244">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="1b7c4-244">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-245">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1b7c4-245">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-246">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-246">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-247">otherIpPhone 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-247">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="1b7c4-248">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-248">Write displayName</span></span></p>
<p><span data-ttu-id="1b7c4-249">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-249">Write description</span></span></p>
<p><span data-ttu-id="1b7c4-250">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-250">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="1b7c4-251">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-251">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="1b7c4-252">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-252">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-253">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-253">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-254">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-254">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-255">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="1b7c4-255">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="1b7c4-256">InetOrgPerson 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="1b7c4-256">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="1b7c4-257">OU의 InetOrgPerson 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="1b7c4-257">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="1b7c4-258">InetOrgPerson 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="1b7c4-258">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1b7c4-259">그룹</span><span class="sxs-lookup"><span data-stu-id="1b7c4-259">Group</span></span></th>
<th><span data-ttu-id="1b7c4-260">사용 권한</span><span class="sxs-lookup"><span data-stu-id="1b7c4-260">Permission</span></span></th>
<th><span data-ttu-id="1b7c4-261">적용 대상</span><span class="sxs-lookup"><span data-stu-id="1b7c4-261">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-262">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="1b7c4-262">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-263">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="1b7c4-263">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-264">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-264">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7c4-265">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-265">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-266">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="1b7c4-266">List contents</span></span></p>
<p><span data-ttu-id="1b7c4-267">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-267">Read all properties</span></span></p>
<p><span data-ttu-id="1b7c4-268">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-268">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-269">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-269">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-270">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-270">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-271">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="1b7c4-271">List contents</span></span></p>
<p><span data-ttu-id="1b7c4-272">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-272">Read all properties</span></span></p>
<p><span data-ttu-id="1b7c4-273">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-273">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-274">이 개체만</span><span class="sxs-lookup"><span data-stu-id="1b7c4-274">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1b7c4-275">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="1b7c4-275">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-276">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-276">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-277">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-277">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-278">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-278">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-279">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-279">Read Personal-Information</span></span></p>
<p><span data-ttu-id="1b7c4-280">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-280">Read Public-Information</span></span></p>
<p><span data-ttu-id="1b7c4-281">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-281">Read General-Information</span></span></p>
<p><span data-ttu-id="1b7c4-282">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-282">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-283">하위 inetOrgPerson 개체</span><span class="sxs-lookup"><span data-stu-id="1b7c4-283">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1b7c4-284">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="1b7c4-284">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-285">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-285">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-286">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-286">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-287">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-287">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="1b7c4-288">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="1b7c4-288">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="1b7c4-289">하위 inetOrgPerson 개체</span><span class="sxs-lookup"><span data-stu-id="1b7c4-289">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

