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
ms.openlocfilehash: dfad0cf4b8b863cd19d4d4113241477de1a50aaf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="8c77c-102">Lync Server 2013의 부여-CsOUPermission에서 변경한 내용</span><span class="sxs-lookup"><span data-stu-id="8c77c-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c77c-103">_**마지막으로 수정 된 항목:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="8c77c-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="8c77c-104">Lync Server 2013 관리를 위임 하기 위해 포리스트 준비로 만든 RTC 유니버설 그룹의 구성원이 Domain Admins 그룹의 구성원이 아닌 Ou에 액세스할 수 있도록 지정 된 Ou (조직 구성 단위)에 사용 권한을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c77c-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="8c77c-105">**Grant-CsOuPermission** cmdlet을 사용하면 다음 표에 지정된 대로 지정한 OU의 개체에 대한 사용 권한이 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c77c-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="8c77c-106">User 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8c77c-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="8c77c-107">OU의 User 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="8c77c-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="8c77c-108">User 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c77c-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c77c-109">Group</span><span class="sxs-lookup"><span data-stu-id="8c77c-109">Group</span></span></th>
<th><span data-ttu-id="8c77c-110">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c77c-110">Permission</span></span></th>
<th><span data-ttu-id="8c77c-111">적용 대상</span><span class="sxs-lookup"><span data-stu-id="8c77c-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="8c77c-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8c77c-113">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="8c77c-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8c77c-114">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c77c-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-116">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8c77c-116">List contents</span></span></p>
<p><span data-ttu-id="8c77c-117">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-117">Read all properties</span></span></p>
<p><span data-ttu-id="8c77c-118">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-119">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-121">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8c77c-121">List contents</span></span></p>
<p><span data-ttu-id="8c77c-122">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-122">Read all properties</span></span></p>
<p><span data-ttu-id="8c77c-123">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-124">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c77c-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-126">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-127">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-128">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-129">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c77c-130">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-130">Read General-Information</span></span></p>
<p><span data-ttu-id="8c77c-131">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-132">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="8c77c-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c77c-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c77c-134">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-135">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="8c77c-136">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-137">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-138">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8c77c-139">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="8c77c-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="8c77c-140">Computer 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8c77c-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="8c77c-141">OU의 Computer 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="8c77c-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="8c77c-142">Computer 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c77c-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c77c-143">Group</span><span class="sxs-lookup"><span data-stu-id="8c77c-143">Group</span></span></th>
<th><span data-ttu-id="8c77c-144">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c77c-144">Permission</span></span></th>
<th><span data-ttu-id="8c77c-145">적용 대상</span><span class="sxs-lookup"><span data-stu-id="8c77c-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="8c77c-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8c77c-147">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="8c77c-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8c77c-148">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c77c-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-150">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8c77c-150">List contents</span></span></p>
<p><span data-ttu-id="8c77c-151">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-151">Read all properties</span></span></p>
<p><span data-ttu-id="8c77c-152">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-153">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-155">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8c77c-155">List contents</span></span></p>
<p><span data-ttu-id="8c77c-156">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-156">Read all properties</span></span></p>
<p><span data-ttu-id="8c77c-157">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-158">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c77c-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-160">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c77c-161">Validated-DNS-Host-Name 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="8c77c-162">하위 Computer 개체</span><span class="sxs-lookup"><span data-stu-id="8c77c-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c77c-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c77c-164">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c77c-165">Validated-DNS-Host-Name 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="8c77c-166">하위 Computer 개체</span><span class="sxs-lookup"><span data-stu-id="8c77c-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="8c77c-167">Contact 또는 AppContact 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8c77c-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="8c77c-168">OU의 Contact 또는 AppContact 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="8c77c-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="8c77c-169">Contact 또는 AppContact 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c77c-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c77c-170">Group</span><span class="sxs-lookup"><span data-stu-id="8c77c-170">Group</span></span></th>
<th><span data-ttu-id="8c77c-171">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c77c-171">Permission</span></span></th>
<th><span data-ttu-id="8c77c-172">적용 대상</span><span class="sxs-lookup"><span data-stu-id="8c77c-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="8c77c-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8c77c-174">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="8c77c-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8c77c-175">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c77c-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-177">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8c77c-177">List contents</span></span></p>
<p><span data-ttu-id="8c77c-178">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-178">Read all properties</span></span></p>
<p><span data-ttu-id="8c77c-179">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-180">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-182">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8c77c-182">List contents</span></span></p>
<p><span data-ttu-id="8c77c-183">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-183">Read all properties</span></span></p>
<p><span data-ttu-id="8c77c-184">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-185">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c77c-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-187">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-188">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-189">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-190">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c77c-191">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-191">Read General-Information</span></span></p>
<p><span data-ttu-id="8c77c-192">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="8c77c-193">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-194">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="8c77c-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c77c-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c77c-196">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-197">otherIpPhone 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="8c77c-198">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-198">Write displayName</span></span></p>
<p><span data-ttu-id="8c77c-199">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-199">Write description</span></span></p>
<p><span data-ttu-id="8c77c-200">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="8c77c-201">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="8c77c-202">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-203">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-204">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8c77c-205">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="8c77c-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="8c77c-206">Device 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8c77c-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="8c77c-207">OU의 Device 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="8c77c-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="8c77c-208">Device 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c77c-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c77c-209">Group</span><span class="sxs-lookup"><span data-stu-id="8c77c-209">Group</span></span></th>
<th><span data-ttu-id="8c77c-210">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c77c-210">Permission</span></span></th>
<th><span data-ttu-id="8c77c-211">적용 대상</span><span class="sxs-lookup"><span data-stu-id="8c77c-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="8c77c-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8c77c-213">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="8c77c-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8c77c-214">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c77c-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-216">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8c77c-216">List contents</span></span></p>
<p><span data-ttu-id="8c77c-217">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-217">Read all properties</span></span></p>
<p><span data-ttu-id="8c77c-218">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-219">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-221">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8c77c-221">List contents</span></span></p>
<p><span data-ttu-id="8c77c-222">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-222">Read all properties</span></span></p>
<p><span data-ttu-id="8c77c-223">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-224">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c77c-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-226">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-227">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-228">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-229">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c77c-230">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="8c77c-231">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-231">Read General-Information</span></span></p>
<p><span data-ttu-id="8c77c-232">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-233">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="8c77c-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c77c-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c77c-235">자식 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="8c77c-235">Create child</span></span></p>
<p><span data-ttu-id="8c77c-236">자식 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="8c77c-236">Delete child</span></span></p>
<p><span data-ttu-id="8c77c-237">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="8c77c-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="8c77c-238">담당자</span><span class="sxs-lookup"><span data-stu-id="8c77c-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c77c-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c77c-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c77c-240">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-240">Write displayName</span></span></p>
<p><span data-ttu-id="8c77c-241">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-241">Write description</span></span></p>
<p><span data-ttu-id="8c77c-242">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="8c77c-243">하위 User 개체</span><span class="sxs-lookup"><span data-stu-id="8c77c-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c77c-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c77c-245">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-246">otherIpPhone 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="8c77c-247">displayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-247">Write displayName</span></span></p>
<p><span data-ttu-id="8c77c-248">description 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-248">Write description</span></span></p>
<p><span data-ttu-id="8c77c-249">telephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="8c77c-250">msExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="8c77c-251">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-252">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-253">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8c77c-254">하위 Contact 개체</span><span class="sxs-lookup"><span data-stu-id="8c77c-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="8c77c-255">InetOrgPerson 개체에 대한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="8c77c-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="8c77c-256">OU의 InetOrgPerson 개체에 대해 **Grant-CsOuPermission** cmdlet을 실행하면 다음 표에 나타난 것처럼 그룹이 사용 권한을 부여받습니다.</span><span class="sxs-lookup"><span data-stu-id="8c77c-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="8c77c-257">InetOrgPerson 개체에 대해 부여되는 사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c77c-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8c77c-258">Group</span><span class="sxs-lookup"><span data-stu-id="8c77c-258">Group</span></span></th>
<th><span data-ttu-id="8c77c-259">사용 권한</span><span class="sxs-lookup"><span data-stu-id="8c77c-259">Permission</span></span></th>
<th><span data-ttu-id="8c77c-260">적용 대상</span><span class="sxs-lookup"><span data-stu-id="8c77c-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="8c77c-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="8c77c-262">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="8c77c-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="8c77c-263">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c77c-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-265">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8c77c-265">List contents</span></span></p>
<p><span data-ttu-id="8c77c-266">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-266">Read all properties</span></span></p>
<p><span data-ttu-id="8c77c-267">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-268">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-270">콘텐츠 나열</span><span class="sxs-lookup"><span data-stu-id="8c77c-270">List contents</span></span></p>
<p><span data-ttu-id="8c77c-271">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-271">Read all properties</span></span></p>
<p><span data-ttu-id="8c77c-272">사용 권한 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-273">이 개체만</span><span class="sxs-lookup"><span data-stu-id="8c77c-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8c77c-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="8c77c-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="8c77c-275">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-276">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-277">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-278">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="8c77c-279">공용 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="8c77c-280">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-280">Read General-Information</span></span></p>
<p><span data-ttu-id="8c77c-281">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="8c77c-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="8c77c-282">하위 inetOrgPerson 개체</span><span class="sxs-lookup"><span data-stu-id="8c77c-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8c77c-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="8c77c-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="8c77c-284">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-285">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-286">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="8c77c-287">proxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="8c77c-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="8c77c-288">하위 inetOrgPerson 개체</span><span class="sxs-lookup"><span data-stu-id="8c77c-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

