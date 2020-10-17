---
title: 'Lync Server 2013: Grant-CsOUPermission에서 변경한 내용'
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
ms.openlocfilehash: 0ff916c0b4e284f9c6ce4d5dbaf9c2e196ed4bc6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529435"
---
# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="22f32-102">Lync Server 2013의 Grant-CsOUPermission에의 한 변경 사항</span><span class="sxs-lookup"><span data-stu-id="22f32-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22f32-103">_**마지막으로 수정 된 항목:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="22f32-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="22f32-104">Lync Server 2013 관리를 위임 하기 위해 포리스트 준비로 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 아닌 Ou에 액세스할 수 있도록 지정 된 Ou (조직 구성 단위)에 사용 권한을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f32-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="22f32-105">**Grant-CsOuPermission** cmdlet을 사용하면 다음 표에 지정된 대로 지정한 OU의 개체에 대한 사용 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="22f32-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="22f32-106">User 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="22f32-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="22f32-107">OU의 User 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="22f32-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="22f32-108">User 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="22f32-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22f32-109">그룹</span><span class="sxs-lookup"><span data-stu-id="22f32-109">Group</span></span></th>
<th><span data-ttu-id="22f32-110">사용 권한</span><span class="sxs-lookup"><span data-stu-id="22f32-110">Permission</span></span></th>
<th><span data-ttu-id="22f32-111">적용 대상</span><span class="sxs-lookup"><span data-stu-id="22f32-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22f32-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="22f32-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="22f32-113">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="22f32-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="22f32-114">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f32-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-116">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="22f32-116">List contents</span></span></p>
<p><span data-ttu-id="22f32-117">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-117">Read all properties</span></span></p>
<p><span data-ttu-id="22f32-118">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="22f32-119">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f32-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-121">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="22f32-121">List contents</span></span></p>
<p><span data-ttu-id="22f32-122">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-122">Read all properties</span></span></p>
<p><span data-ttu-id="22f32-123">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="22f32-124">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f32-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-126">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="22f32-127">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="22f32-128">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="22f32-129">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="22f32-130">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-130">Read General-Information</span></span></p>
<p><span data-ttu-id="22f32-131">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="22f32-132">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="22f32-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f32-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="22f32-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="22f32-134">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="22f32-135">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="22f32-136">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="22f32-137">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="22f32-138">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="22f32-139">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="22f32-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="22f32-140">Computer 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="22f32-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="22f32-141">OU의 Computer 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="22f32-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="22f32-142">Computer 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="22f32-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22f32-143">그룹</span><span class="sxs-lookup"><span data-stu-id="22f32-143">Group</span></span></th>
<th><span data-ttu-id="22f32-144">사용 권한</span><span class="sxs-lookup"><span data-stu-id="22f32-144">Permission</span></span></th>
<th><span data-ttu-id="22f32-145">적용 대상</span><span class="sxs-lookup"><span data-stu-id="22f32-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22f32-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="22f32-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="22f32-147">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="22f32-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="22f32-148">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f32-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-150">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="22f32-150">List contents</span></span></p>
<p><span data-ttu-id="22f32-151">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-151">Read all properties</span></span></p>
<p><span data-ttu-id="22f32-152">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="22f32-153">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f32-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-155">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="22f32-155">List contents</span></span></p>
<p><span data-ttu-id="22f32-156">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-156">Read all properties</span></span></p>
<p><span data-ttu-id="22f32-157">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="22f32-158">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f32-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-160">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="22f32-161">Validated-DNS-Host-Name 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="22f32-162">하위 Computer 개체</span><span class="sxs-lookup"><span data-stu-id="22f32-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f32-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="22f32-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="22f32-164">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="22f32-165">Validated-DNS-Host-Name 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="22f32-166">하위 Computer 개체</span><span class="sxs-lookup"><span data-stu-id="22f32-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="22f32-167">Contact 또는 AppContact 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="22f32-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="22f32-168">OU의 Contact 또는 AppContact 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="22f32-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="22f32-169">Contact 또는 AppContact 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="22f32-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22f32-170">그룹</span><span class="sxs-lookup"><span data-stu-id="22f32-170">Group</span></span></th>
<th><span data-ttu-id="22f32-171">사용 권한</span><span class="sxs-lookup"><span data-stu-id="22f32-171">Permission</span></span></th>
<th><span data-ttu-id="22f32-172">적용 대상</span><span class="sxs-lookup"><span data-stu-id="22f32-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22f32-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="22f32-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="22f32-174">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="22f32-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="22f32-175">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f32-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-177">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="22f32-177">List contents</span></span></p>
<p><span data-ttu-id="22f32-178">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-178">Read all properties</span></span></p>
<p><span data-ttu-id="22f32-179">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="22f32-180">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f32-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-182">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="22f32-182">List contents</span></span></p>
<p><span data-ttu-id="22f32-183">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-183">Read all properties</span></span></p>
<p><span data-ttu-id="22f32-184">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="22f32-185">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f32-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-187">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="22f32-188">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="22f32-189">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="22f32-190">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="22f32-191">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-191">Read General-Information</span></span></p>
<p><span data-ttu-id="22f32-192">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="22f32-193">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="22f32-194">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="22f32-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f32-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="22f32-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="22f32-196">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="22f32-197">otherIpPhone 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="22f32-198">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-198">Write displayName</span></span></p>
<p><span data-ttu-id="22f32-199">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-199">Write description</span></span></p>
<p><span data-ttu-id="22f32-200">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="22f32-201">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="22f32-202">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="22f32-203">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="22f32-204">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="22f32-205">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="22f32-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="22f32-206">Device 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="22f32-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="22f32-207">OU의 Device 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="22f32-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="22f32-208">Device 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="22f32-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22f32-209">그룹</span><span class="sxs-lookup"><span data-stu-id="22f32-209">Group</span></span></th>
<th><span data-ttu-id="22f32-210">사용 권한</span><span class="sxs-lookup"><span data-stu-id="22f32-210">Permission</span></span></th>
<th><span data-ttu-id="22f32-211">적용 대상</span><span class="sxs-lookup"><span data-stu-id="22f32-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22f32-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="22f32-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="22f32-213">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="22f32-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="22f32-214">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f32-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-216">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="22f32-216">List contents</span></span></p>
<p><span data-ttu-id="22f32-217">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-217">Read all properties</span></span></p>
<p><span data-ttu-id="22f32-218">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="22f32-219">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f32-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-221">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="22f32-221">List contents</span></span></p>
<p><span data-ttu-id="22f32-222">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-222">Read all properties</span></span></p>
<p><span data-ttu-id="22f32-223">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="22f32-224">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f32-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-226">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="22f32-227">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="22f32-228">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="22f32-229">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="22f32-230">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="22f32-231">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-231">Read General-Information</span></span></p>
<p><span data-ttu-id="22f32-232">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="22f32-233">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="22f32-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f32-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="22f32-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="22f32-235">자식 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="22f32-235">Create child</span></span></p>
<p><span data-ttu-id="22f32-236">자식 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="22f32-236">Delete child</span></span></p>
<p><span data-ttu-id="22f32-237">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="22f32-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="22f32-238">담당자</span><span class="sxs-lookup"><span data-stu-id="22f32-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f32-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="22f32-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="22f32-240">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-240">Write displayName</span></span></p>
<p><span data-ttu-id="22f32-241">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-241">Write description</span></span></p>
<p><span data-ttu-id="22f32-242">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="22f32-243">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="22f32-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f32-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="22f32-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="22f32-245">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="22f32-246">otherIpPhone 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="22f32-247">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-247">Write displayName</span></span></p>
<p><span data-ttu-id="22f32-248">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-248">Write description</span></span></p>
<p><span data-ttu-id="22f32-249">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="22f32-250">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="22f32-251">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="22f32-252">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="22f32-253">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="22f32-254">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="22f32-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="22f32-255">InetOrgPerson 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="22f32-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="22f32-256">OU의 InetOrgPerson 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="22f32-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="22f32-257">InetOrgPerson 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="22f32-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="22f32-258">그룹</span><span class="sxs-lookup"><span data-stu-id="22f32-258">Group</span></span></th>
<th><span data-ttu-id="22f32-259">사용 권한</span><span class="sxs-lookup"><span data-stu-id="22f32-259">Permission</span></span></th>
<th><span data-ttu-id="22f32-260">적용 대상</span><span class="sxs-lookup"><span data-stu-id="22f32-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="22f32-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="22f32-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="22f32-262">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="22f32-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="22f32-263">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f32-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-265">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="22f32-265">List contents</span></span></p>
<p><span data-ttu-id="22f32-266">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-266">Read all properties</span></span></p>
<p><span data-ttu-id="22f32-267">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="22f32-268">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f32-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-270">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="22f32-270">List contents</span></span></p>
<p><span data-ttu-id="22f32-271">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-271">Read all properties</span></span></p>
<p><span data-ttu-id="22f32-272">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="22f32-273">이 개체만</span><span class="sxs-lookup"><span data-stu-id="22f32-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="22f32-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="22f32-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="22f32-275">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="22f32-276">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="22f32-277">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="22f32-278">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="22f32-279">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="22f32-280">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-280">Read General-Information</span></span></p>
<p><span data-ttu-id="22f32-281">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="22f32-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="22f32-282">하위 inetOrgPerson 개체</span><span class="sxs-lookup"><span data-stu-id="22f32-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="22f32-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="22f32-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="22f32-284">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="22f32-285">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="22f32-286">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="22f32-287">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="22f32-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="22f32-288">하위 inetOrgPerson 개체</span><span class="sxs-lookup"><span data-stu-id="22f32-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

