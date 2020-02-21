---
title: 'Lync Server 2013: 부여-CsOUPermission에서 변경한 내용'
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
ms.openlocfilehash: 6143310797c7372a30665cd380d7fb07340ebaf9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="8ec4d-102">Lync Server 2013의 부여-CsOUPermission에서 변경한 내용</span><span class="sxs-lookup"><span data-stu-id="8ec4d-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ec4d-103">_**마지막으로 수정 된 항목:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="8ec4d-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="8ec4d-104">Lync Server 2013 관리를 위임 하기 위해 포리스트 준비로 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 아닌 Ou에 액세스할 수 있도록 지정 된 Ou (조직 구성 단위)에 사용 권한을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec4d-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="8ec4d-105">**Grant-CsOuPermission** cmdlet을 사용하면 다음 표에 지정된 대로 지정한 OU의 개체에 대한 사용 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ec4d-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="8ec4d-106">User 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8ec4d-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="8ec4d-107">OU의 User 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec4d-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="8ec4d-108">User 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ec4d-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ec4d-109">Group</span><span class="sxs-lookup"><span data-stu-id="8ec4d-109">Group</span></span></th>
<th><span data-ttu-id="8ec4d-110">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ec4d-110">Permission</span></span></th>
<th><span data-ttu-id="8ec4d-111">적용 대상</span><span class="sxs-lookup"><span data-stu-id="8ec4d-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="8ec4d-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-113">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="8ec4d-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-114">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ec4d-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-116">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8ec4d-116">List contents</span></span></p>
<p><span data-ttu-id="8ec4d-117">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-117">Read all properties</span></span></p>
<p><span data-ttu-id="8ec4d-118">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-119">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-121">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8ec4d-121">List contents</span></span></p>
<p><span data-ttu-id="8ec4d-122">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-122">Read all properties</span></span></p>
<p><span data-ttu-id="8ec4d-123">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-124">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ec4d-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-126">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-127">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-128">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-129">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="8ec4d-130">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-130">Read General-Information</span></span></p>
<p><span data-ttu-id="8ec4d-131">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-132">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="8ec4d-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8ec4d-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-134">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-135">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="8ec4d-136">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-137">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-138">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-139">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="8ec4d-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="8ec4d-140">Computer 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8ec4d-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="8ec4d-141">OU의 Computer 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec4d-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="8ec4d-142">Computer 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ec4d-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ec4d-143">Group</span><span class="sxs-lookup"><span data-stu-id="8ec4d-143">Group</span></span></th>
<th><span data-ttu-id="8ec4d-144">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ec4d-144">Permission</span></span></th>
<th><span data-ttu-id="8ec4d-145">적용 대상</span><span class="sxs-lookup"><span data-stu-id="8ec4d-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="8ec4d-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-147">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="8ec4d-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-148">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ec4d-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-150">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8ec4d-150">List contents</span></span></p>
<p><span data-ttu-id="8ec4d-151">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-151">Read all properties</span></span></p>
<p><span data-ttu-id="8ec4d-152">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-153">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-155">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8ec4d-155">List contents</span></span></p>
<p><span data-ttu-id="8ec4d-156">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-156">Read all properties</span></span></p>
<p><span data-ttu-id="8ec4d-157">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-158">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ec4d-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-160">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="8ec4d-161">Validated-DNS-Host-Name 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-162">하위 Computer 개체</span><span class="sxs-lookup"><span data-stu-id="8ec4d-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8ec4d-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-164">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="8ec4d-165">Validated-DNS-Host-Name 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-166">하위 Computer 개체</span><span class="sxs-lookup"><span data-stu-id="8ec4d-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="8ec4d-167">Contact 또는 AppContact 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8ec4d-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="8ec4d-168">OU의 Contact 또는 AppContact 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec4d-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="8ec4d-169">Contact 또는 AppContact 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ec4d-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ec4d-170">Group</span><span class="sxs-lookup"><span data-stu-id="8ec4d-170">Group</span></span></th>
<th><span data-ttu-id="8ec4d-171">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ec4d-171">Permission</span></span></th>
<th><span data-ttu-id="8ec4d-172">적용 대상</span><span class="sxs-lookup"><span data-stu-id="8ec4d-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="8ec4d-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-174">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="8ec4d-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-175">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ec4d-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-177">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8ec4d-177">List contents</span></span></p>
<p><span data-ttu-id="8ec4d-178">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-178">Read all properties</span></span></p>
<p><span data-ttu-id="8ec4d-179">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-180">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-182">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8ec4d-182">List contents</span></span></p>
<p><span data-ttu-id="8ec4d-183">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-183">Read all properties</span></span></p>
<p><span data-ttu-id="8ec4d-184">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-185">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ec4d-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-187">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-188">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-189">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-190">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="8ec4d-191">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-191">Read General-Information</span></span></p>
<p><span data-ttu-id="8ec4d-192">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="8ec4d-193">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-194">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="8ec4d-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8ec4d-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-196">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-197">otherIpPhone 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="8ec4d-198">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-198">Write displayName</span></span></p>
<p><span data-ttu-id="8ec4d-199">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-199">Write description</span></span></p>
<p><span data-ttu-id="8ec4d-200">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="8ec4d-201">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="8ec4d-202">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-203">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-204">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-205">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="8ec4d-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="8ec4d-206">Device 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8ec4d-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="8ec4d-207">OU의 Device 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec4d-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="8ec4d-208">Device 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ec4d-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ec4d-209">Group</span><span class="sxs-lookup"><span data-stu-id="8ec4d-209">Group</span></span></th>
<th><span data-ttu-id="8ec4d-210">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ec4d-210">Permission</span></span></th>
<th><span data-ttu-id="8ec4d-211">적용 대상</span><span class="sxs-lookup"><span data-stu-id="8ec4d-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="8ec4d-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-213">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="8ec4d-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-214">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ec4d-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-216">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8ec4d-216">List contents</span></span></p>
<p><span data-ttu-id="8ec4d-217">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-217">Read all properties</span></span></p>
<p><span data-ttu-id="8ec4d-218">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-219">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-221">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8ec4d-221">List contents</span></span></p>
<p><span data-ttu-id="8ec4d-222">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-222">Read all properties</span></span></p>
<p><span data-ttu-id="8ec4d-223">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-224">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ec4d-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-226">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-227">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-228">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-229">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="8ec4d-230">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="8ec4d-231">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-231">Read General-Information</span></span></p>
<p><span data-ttu-id="8ec4d-232">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-233">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="8ec4d-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8ec4d-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-235">자식 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-235">Create child</span></span></p>
<p><span data-ttu-id="8ec4d-236">자식 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="8ec4d-236">Delete child</span></span></p>
<p><span data-ttu-id="8ec4d-237">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="8ec4d-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-238">담당자</span><span class="sxs-lookup"><span data-stu-id="8ec4d-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ec4d-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8ec4d-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-240">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-240">Write displayName</span></span></p>
<p><span data-ttu-id="8ec4d-241">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-241">Write description</span></span></p>
<p><span data-ttu-id="8ec4d-242">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-243">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="8ec4d-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8ec4d-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-245">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-246">otherIpPhone 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="8ec4d-247">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-247">Write displayName</span></span></p>
<p><span data-ttu-id="8ec4d-248">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-248">Write description</span></span></p>
<p><span data-ttu-id="8ec4d-249">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="8ec4d-250">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="8ec4d-251">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-252">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-253">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-254">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="8ec4d-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="8ec4d-255">InetOrgPerson 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8ec4d-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="8ec4d-256">OU의 InetOrgPerson 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="8ec4d-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="8ec4d-257">InetOrgPerson 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ec4d-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8ec4d-258">Group</span><span class="sxs-lookup"><span data-stu-id="8ec4d-258">Group</span></span></th>
<th><span data-ttu-id="8ec4d-259">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8ec4d-259">Permission</span></span></th>
<th><span data-ttu-id="8ec4d-260">적용 대상</span><span class="sxs-lookup"><span data-stu-id="8ec4d-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="8ec4d-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-262">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="8ec4d-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-263">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ec4d-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-265">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8ec4d-265">List contents</span></span></p>
<p><span data-ttu-id="8ec4d-266">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-266">Read all properties</span></span></p>
<p><span data-ttu-id="8ec4d-267">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-268">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-270">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8ec4d-270">List contents</span></span></p>
<p><span data-ttu-id="8ec4d-271">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-271">Read all properties</span></span></p>
<p><span data-ttu-id="8ec4d-272">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-273">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8ec4d-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8ec4d-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8ec4d-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-275">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-276">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-277">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-278">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="8ec4d-279">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="8ec4d-280">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-280">Read General-Information</span></span></p>
<p><span data-ttu-id="8ec4d-281">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-282">하위 inetOrgPerson 개체</span><span class="sxs-lookup"><span data-stu-id="8ec4d-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8ec4d-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8ec4d-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-284">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-285">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-286">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8ec4d-287">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="8ec4d-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8ec4d-288">하위 inetOrgPerson 개체</span><span class="sxs-lookup"><span data-stu-id="8ec4d-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

