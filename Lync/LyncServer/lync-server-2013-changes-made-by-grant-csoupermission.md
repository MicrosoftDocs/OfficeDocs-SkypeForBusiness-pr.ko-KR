---
title: 'Lync Server 2013: 요청-CsOUPermission에의 한 변경 내용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by Grant-CsOUPermission
ms:assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205310(v=OCS.15)
ms:contentKeyID: 48185564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ce6b16dff48afeeec848024d763655695905008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-grant-csoupermission-in-lync-server-2013"></a><span data-ttu-id="a91e8-102">Lync Server 2013의 허용-CsOUPermission에의 한 변경 내용</span><span class="sxs-lookup"><span data-stu-id="a91e8-102">Changes made by Grant-CsOUPermission in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a91e8-103">_**마지막으로 수정한 주제:** 2012-06-20_</span><span class="sxs-lookup"><span data-stu-id="a91e8-103">_**Topic Last Modified:** 2012-06-20_</span></span>

<span data-ttu-id="a91e8-104">Lync Server 2013 관리를 위임 하려면 포리스트 준비로 만든 RTC 유니버설 그룹의 구성원이 도메인 관리자 그룹의 구성원이 아닌 Ou에 액세스할 수 있도록 지정 된 조직 구성 단위 (Ou)에 대 한 사용 권한을 추가 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91e8-104">To delegate Lync Server 2013 administration, you can add permissions to specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access the OUs without being members of the Domain Admins group.</span></span>

<span data-ttu-id="a91e8-105">**허용-CsOuPermission** cmdlet은 다음 표에 지정 된 대로 지정 된 OU의 개체에 대 한 사용 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="a91e8-105">The **Grant-CsOuPermission** cmdlet grants permissions to objects in the specified OU as specified in the following tables.</span></span>

<div>

## <a name="granting-permission-for-user-objects"></a><span data-ttu-id="a91e8-106">사용자 개체에 대 한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="a91e8-106">Granting Permission for User Objects</span></span>

<span data-ttu-id="a91e8-107">OU의 사용자 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하는 경우 그룹에는 다음 표에 나와 있는 것 처럼 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91e8-107">When you run the **Grant-CsOuPermission** cmdlet for User objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-user-objects"></a><span data-ttu-id="a91e8-108">사용자 개체에 부여 된 사용 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-108">Permissions Granted for User Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a91e8-109">그룹과</span><span class="sxs-lookup"><span data-stu-id="a91e8-109">Group</span></span></th>
<th><span data-ttu-id="a91e8-110">있는</span><span class="sxs-lookup"><span data-stu-id="a91e8-110">Permission</span></span></th>
<th><span data-ttu-id="a91e8-111">적용 대상</span><span class="sxs-lookup"><span data-stu-id="a91e8-111">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-112">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a91e8-112">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a91e8-113">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="a91e8-113">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="a91e8-114">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-114">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91e8-115">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-115">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-116">내용 목록</span><span class="sxs-lookup"><span data-stu-id="a91e8-116">List contents</span></span></p>
<p><span data-ttu-id="a91e8-117">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-117">Read all properties</span></span></p>
<p><span data-ttu-id="a91e8-118">읽기 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-118">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-119">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-119">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-120">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-120">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-121">내용 목록</span><span class="sxs-lookup"><span data-stu-id="a91e8-121">List contents</span></span></p>
<p><span data-ttu-id="a91e8-122">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-122">Read all properties</span></span></p>
<p><span data-ttu-id="a91e8-123">읽기 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-123">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-124">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-124">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91e8-125">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-125">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-126">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-126">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-127">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-127">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-128">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-128">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-129">공개 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-129">Read Public-Information</span></span></p>
<p><span data-ttu-id="a91e8-130">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-130">Read General-Information</span></span></p>
<p><span data-ttu-id="a91e8-131">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-131">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-132">하위 사용자 개체</span><span class="sxs-lookup"><span data-stu-id="a91e8-132">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-133">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a91e8-133">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a91e8-134">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-134">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-135">MsExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-135">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="a91e8-136">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-136">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-137">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-137">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-138">ProxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-138">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="a91e8-139">하위 사용자 개체</span><span class="sxs-lookup"><span data-stu-id="a91e8-139">Descendant User objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-computer-objects"></a><span data-ttu-id="a91e8-140">컴퓨터 개체에 대 한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="a91e8-140">Granting Permission for Computer Objects</span></span>

<span data-ttu-id="a91e8-141">OU의 컴퓨터 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하는 경우 그룹에는 다음 표에 나와 있는 것 처럼 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91e8-141">When you run the **Grant-CsOuPermission** cmdlet for Computer objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-computer-objects"></a><span data-ttu-id="a91e8-142">컴퓨터 개체에 부여 된 사용 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-142">Permissions Granted for Computer Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a91e8-143">그룹과</span><span class="sxs-lookup"><span data-stu-id="a91e8-143">Group</span></span></th>
<th><span data-ttu-id="a91e8-144">있는</span><span class="sxs-lookup"><span data-stu-id="a91e8-144">Permission</span></span></th>
<th><span data-ttu-id="a91e8-145">적용 대상</span><span class="sxs-lookup"><span data-stu-id="a91e8-145">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-146">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a91e8-146">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a91e8-147">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="a91e8-147">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="a91e8-148">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-148">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91e8-149">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-149">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-150">내용 목록</span><span class="sxs-lookup"><span data-stu-id="a91e8-150">List contents</span></span></p>
<p><span data-ttu-id="a91e8-151">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-151">Read all properties</span></span></p>
<p><span data-ttu-id="a91e8-152">읽기 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-152">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-153">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-153">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-154">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-154">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-155">내용 목록</span><span class="sxs-lookup"><span data-stu-id="a91e8-155">List contents</span></span></p>
<p><span data-ttu-id="a91e8-156">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-156">Read all properties</span></span></p>
<p><span data-ttu-id="a91e8-157">읽기 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-157">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-158">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-158">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91e8-159">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-159">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-160">공개 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-160">Read Public-Information</span></span></p>
<p><span data-ttu-id="a91e8-161">읽음 확인 됨-DNS-호스트 이름</span><span class="sxs-lookup"><span data-stu-id="a91e8-161">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="a91e8-162">하위 컴퓨터 개체</span><span class="sxs-lookup"><span data-stu-id="a91e8-162">Descendant Computer objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-163">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a91e8-163">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a91e8-164">공개 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-164">Read Public-Information</span></span></p>
<p><span data-ttu-id="a91e8-165">읽음 확인 됨-DNS-호스트 이름</span><span class="sxs-lookup"><span data-stu-id="a91e8-165">Read Validated-DNS-Host-Name</span></span></p></td>
<td><p><span data-ttu-id="a91e8-166">하위 컴퓨터 개체</span><span class="sxs-lookup"><span data-stu-id="a91e8-166">Descendant Computer objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-contact-or-appcontact-objects"></a><span data-ttu-id="a91e8-167">연락처 또는 AppContact 개체에 대 한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="a91e8-167">Granting Permission for Contact or AppContact Objects</span></span>

<span data-ttu-id="a91e8-168">OU의 Contact objects 또는 AppContact 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하면 다음 표에 표시 된 것 처럼 그룹에 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91e8-168">When you run the **Grant-CsOuPermission** cmdlet for Contact objects or AppContact objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-contact-or-appcontact-objects"></a><span data-ttu-id="a91e8-169">연락처 또는 AppContact 개체에 부여 된 사용 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-169">Permissions Granted for Contact or AppContact Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a91e8-170">그룹과</span><span class="sxs-lookup"><span data-stu-id="a91e8-170">Group</span></span></th>
<th><span data-ttu-id="a91e8-171">있는</span><span class="sxs-lookup"><span data-stu-id="a91e8-171">Permission</span></span></th>
<th><span data-ttu-id="a91e8-172">적용 대상</span><span class="sxs-lookup"><span data-stu-id="a91e8-172">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-173">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a91e8-173">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a91e8-174">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="a91e8-174">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="a91e8-175">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-175">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91e8-176">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-176">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-177">내용 목록</span><span class="sxs-lookup"><span data-stu-id="a91e8-177">List contents</span></span></p>
<p><span data-ttu-id="a91e8-178">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-178">Read all properties</span></span></p>
<p><span data-ttu-id="a91e8-179">읽기 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-179">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-180">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-180">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-181">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-181">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-182">내용 목록</span><span class="sxs-lookup"><span data-stu-id="a91e8-182">List contents</span></span></p>
<p><span data-ttu-id="a91e8-183">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-183">Read all properties</span></span></p>
<p><span data-ttu-id="a91e8-184">읽기 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-184">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-185">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-185">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91e8-186">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-186">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-187">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-187">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-188">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-188">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-189">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-189">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-190">공개 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-190">Read Public-Information</span></span></p>
<p><span data-ttu-id="a91e8-191">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-191">Read General-Information</span></span></p>
<p><span data-ttu-id="a91e8-192">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-192">Read Personal-Information</span></span></p>
<p><span data-ttu-id="a91e8-193">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-193">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-194">하위 연락처 개체</span><span class="sxs-lookup"><span data-stu-id="a91e8-194">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-195">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a91e8-195">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a91e8-196">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-196">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-197">OtherIpPhone 작성</span><span class="sxs-lookup"><span data-stu-id="a91e8-197">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="a91e8-198">DisplayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-198">Write displayName</span></span></p>
<p><span data-ttu-id="a91e8-199">설명 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-199">Write description</span></span></p>
<p><span data-ttu-id="a91e8-200">TelephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-200">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="a91e8-201">MsExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-201">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="a91e8-202">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-202">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-203">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-203">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-204">ProxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-204">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="a91e8-205">하위 연락처 개체</span><span class="sxs-lookup"><span data-stu-id="a91e8-205">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-device-objects"></a><span data-ttu-id="a91e8-206">디바이스 개체에 대 한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="a91e8-206">Granting Permission for Device Objects</span></span>

<span data-ttu-id="a91e8-207">OU의 디바이스 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하면 다음 표에 표시 된 대로 그룹에 대 한 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91e8-207">When you run the **Grant-CsOuPermission** cmdlet for Device objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-device-objects"></a><span data-ttu-id="a91e8-208">장치 개체에 부여 된 사용 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-208">Permissions Granted for Device Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a91e8-209">그룹과</span><span class="sxs-lookup"><span data-stu-id="a91e8-209">Group</span></span></th>
<th><span data-ttu-id="a91e8-210">있는</span><span class="sxs-lookup"><span data-stu-id="a91e8-210">Permission</span></span></th>
<th><span data-ttu-id="a91e8-211">적용 대상</span><span class="sxs-lookup"><span data-stu-id="a91e8-211">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-212">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a91e8-212">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a91e8-213">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="a91e8-213">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="a91e8-214">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-214">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91e8-215">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-215">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-216">내용 목록</span><span class="sxs-lookup"><span data-stu-id="a91e8-216">List contents</span></span></p>
<p><span data-ttu-id="a91e8-217">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-217">Read all properties</span></span></p>
<p><span data-ttu-id="a91e8-218">읽기 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-218">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-219">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-219">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-220">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-220">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-221">내용 목록</span><span class="sxs-lookup"><span data-stu-id="a91e8-221">List contents</span></span></p>
<p><span data-ttu-id="a91e8-222">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-222">Read all properties</span></span></p>
<p><span data-ttu-id="a91e8-223">읽기 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-223">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-224">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-224">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91e8-225">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-225">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-226">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-226">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-227">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-227">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-228">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-228">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-229">공개 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-229">Read Public-Information</span></span></p>
<p><span data-ttu-id="a91e8-230">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-230">Read Personal-Information</span></span></p>
<p><span data-ttu-id="a91e8-231">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-231">Read General-Information</span></span></p>
<p><span data-ttu-id="a91e8-232">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-232">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-233">하위 연락처 개체</span><span class="sxs-lookup"><span data-stu-id="a91e8-233">Descendant Contact objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-234">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a91e8-234">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a91e8-235">하위 항목 만들기</span><span class="sxs-lookup"><span data-stu-id="a91e8-235">Create child</span></span></p>
<p><span data-ttu-id="a91e8-236">하위 항목 삭제</span><span class="sxs-lookup"><span data-stu-id="a91e8-236">Delete child</span></span></p>
<p><span data-ttu-id="a91e8-237">트리 삭제</span><span class="sxs-lookup"><span data-stu-id="a91e8-237">Delete tree</span></span></p></td>
<td><p><span data-ttu-id="a91e8-238">Contact</span><span class="sxs-lookup"><span data-stu-id="a91e8-238">Contact</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91e8-239">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a91e8-239">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a91e8-240">DisplayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-240">Write displayName</span></span></p>
<p><span data-ttu-id="a91e8-241">설명 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-241">Write description</span></span></p>
<p><span data-ttu-id="a91e8-242">TelephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-242">Write telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="a91e8-243">하위 사용자 개체</span><span class="sxs-lookup"><span data-stu-id="a91e8-243">Descendant User objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-244">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a91e8-244">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a91e8-245">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-245">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-246">OtherIpPhone 작성</span><span class="sxs-lookup"><span data-stu-id="a91e8-246">Write otherIpPhone</span></span></p>
<p><span data-ttu-id="a91e8-247">DisplayName 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-247">Write displayName</span></span></p>
<p><span data-ttu-id="a91e8-248">설명 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-248">Write description</span></span></p>
<p><span data-ttu-id="a91e8-249">TelephoneNumber 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-249">Write telephoneNumber</span></span></p>
<p><span data-ttu-id="a91e8-250">MsExchUCVoiceMailSettings 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-250">Write msExchUCVoiceMailSettings</span></span></p>
<p><span data-ttu-id="a91e8-251">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-251">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-252">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-252">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-253">ProxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-253">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="a91e8-254">하위 연락처 개체</span><span class="sxs-lookup"><span data-stu-id="a91e8-254">Descendant Contact objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="granting-permission-for-inetorgperson-objects"></a><span data-ttu-id="a91e8-255">InetOrgPerson 개체에 대 한 사용 권한 부여</span><span class="sxs-lookup"><span data-stu-id="a91e8-255">Granting Permission for InetOrgPerson Objects</span></span>

<span data-ttu-id="a91e8-256">OU의 InetOrgPerson 개체에 대해 **허용-CsOuPermission** cmdlet을 실행 하는 경우 그룹에는 다음 표에 나와 있는 것 처럼 권한이 부여 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a91e8-256">When you run the **Grant-CsOuPermission** cmdlet for InetOrgPerson objects on an OU, groups are granted permissions as shown in the following table.</span></span>

### <a name="permissions-granted-for-inetorgperson-objects"></a><span data-ttu-id="a91e8-257">InetOrgPerson 개체에 부여 된 사용 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-257">Permissions Granted for InetOrgPerson Objects</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a91e8-258">그룹과</span><span class="sxs-lookup"><span data-stu-id="a91e8-258">Group</span></span></th>
<th><span data-ttu-id="a91e8-259">있는</span><span class="sxs-lookup"><span data-stu-id="a91e8-259">Permission</span></span></th>
<th><span data-ttu-id="a91e8-260">적용 대상</span><span class="sxs-lookup"><span data-stu-id="a91e8-260">Applies to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-261">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="a91e8-261">RTCHSUniversalServices</span></span></p></td>
<td><p><span data-ttu-id="a91e8-262">디렉터리 변경 내용 복제</span><span class="sxs-lookup"><span data-stu-id="a91e8-262">Replicating directory changes</span></span></p></td>
<td><p><span data-ttu-id="a91e8-263">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-263">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91e8-264">RTCUniversalServerReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-264">RTCUniversalServerReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-265">내용 목록</span><span class="sxs-lookup"><span data-stu-id="a91e8-265">List contents</span></span></p>
<p><span data-ttu-id="a91e8-266">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-266">Read all properties</span></span></p>
<p><span data-ttu-id="a91e8-267">읽기 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-267">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-268">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-268">This object only</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-269">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-269">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-270">내용 목록</span><span class="sxs-lookup"><span data-stu-id="a91e8-270">List contents</span></span></p>
<p><span data-ttu-id="a91e8-271">모든 속성 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-271">Read all properties</span></span></p>
<p><span data-ttu-id="a91e8-272">읽기 권한</span><span class="sxs-lookup"><span data-stu-id="a91e8-272">Read permissions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-273">이 개체만</span><span class="sxs-lookup"><span data-stu-id="a91e8-273">This object only</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a91e8-274">RTCUniversalUserReadOnlyGroup</span><span class="sxs-lookup"><span data-stu-id="a91e8-274">RTCUniversalUserReadOnlyGroup</span></span></p></td>
<td><p><span data-ttu-id="a91e8-275">RTCUserSearchPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-275">Read RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-276">RTCUserProvisioningPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-276">Read RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-277">RTCPropertySet 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-277">Read RTCPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-278">개인 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-278">Read Personal-Information</span></span></p>
<p><span data-ttu-id="a91e8-279">공개 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-279">Read Public-Information</span></span></p>
<p><span data-ttu-id="a91e8-280">일반 정보 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-280">Read General-Information</span></span></p>
<p><span data-ttu-id="a91e8-281">사용자 계정 제한 사항 읽기</span><span class="sxs-lookup"><span data-stu-id="a91e8-281">Read User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="a91e8-282">하위 항목 inetOrgPerson 개체</span><span class="sxs-lookup"><span data-stu-id="a91e8-282">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a91e8-283">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="a91e8-283">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="a91e8-284">RTCUserSearchPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-284">Write RTCUserSearchPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-285">RTCUserProvisioningPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-285">Write RTCUserProvisioningPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-286">RTCPropertySet 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-286">Write RTCPropertySet</span></span></p>
<p><span data-ttu-id="a91e8-287">ProxyAddresses 쓰기</span><span class="sxs-lookup"><span data-stu-id="a91e8-287">Write proxyAddresses</span></span></p></td>
<td><p><span data-ttu-id="a91e8-288">하위 항목 inetOrgPerson 개체</span><span class="sxs-lookup"><span data-stu-id="a91e8-288">Descendant inetOrgPerson objects</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

