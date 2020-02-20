---
title: 'Lync Server 2013: tblPrincipal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipal
ms:assetid: 79a24502-b4ce-41f0-8979-8caddf535338
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558667(v=OCS.15)
ms:contentKeyID: 48184571
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4894cc1e27ce2692f0afee57fafd0025cbafebc8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="0fe8d-102">Lync Server 2013의 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="0fe8d-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0fe8d-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="0fe8d-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="0fe8d-104">tblPrincipal에는 사용자, 폴더 및 그룹을 비롯한 모든 참가자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="0fe8d-105">단</span><span class="sxs-lookup"><span data-stu-id="0fe8d-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0fe8d-106">열</span><span class="sxs-lookup"><span data-stu-id="0fe8d-106">Column</span></span></th>
<th><span data-ttu-id="0fe8d-107">형식</span><span class="sxs-lookup"><span data-stu-id="0fe8d-107">Type</span></span></th>
<th><span data-ttu-id="0fe8d-108">설명</span><span class="sxs-lookup"><span data-stu-id="0fe8d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0fe8d-109">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="0fe8d-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0fe8d-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-111">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fe8d-112">Principal.pringuid</span><span class="sxs-lookup"><span data-stu-id="0fe8d-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-113">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0fe8d-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-114">사용자 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-114">Principal GUID.</span></span> <span data-ttu-id="0fe8d-115">이는 해당 의미가 Active Directory 도메인 서비스 공간에 대 한 것 이므로 대체 기본 키로 광범위 하 게 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="0fe8d-116">캐시된 사용자의 GUID는 해당하는 Active Directory 개체 GUID와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fe8d-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="0fe8d-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-118">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="0fe8d-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-p102">계정 URI입니다. SIP 구성표는 사용자에 대해 사용되고 ma-grp는 거의 모든 다른 항목들에 대해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-p102">Principal URI. The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fe8d-121">prinName</span><span class="sxs-lookup"><span data-stu-id="0fe8d-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-122">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0fe8d-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-p103">회사 이름입니다. 사용자 유형에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-p103">Common name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fe8d-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="0fe8d-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-126">Nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0fe8d-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-p104">표시 이름입니다. 사용자 유형에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-p104">Display name. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fe8d-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="0fe8d-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0fe8d-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-p105">회사 이름입니다. 사용자 유형에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-p105">Company name. Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fe8d-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="0fe8d-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0fe8d-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-p106">전자 메일입니다. 사용자 유형에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-p106">Email. Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fe8d-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="0fe8d-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-138">nvarchar(384)</span><span class="sxs-lookup"><span data-stu-id="0fe8d-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-p107">계정이 캐시된 버전인 Active Directory 개체의 도메인 이름입니다. Active Directory가 아닌 개체 유형의 경우 Null일 수 있습니다(예: 시스템 사용자).</span><span class="sxs-lookup"><span data-stu-id="0fe8d-p107">Domain name of the Active Directory object that the principal is a cached version of. Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fe8d-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="0fe8d-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-142">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="0fe8d-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-p108">사용자의 UPN(Universal Principal Name)입니다. 사용자 유형에서만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-p108">User’s user principal name (UPN). Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fe8d-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="0fe8d-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-146">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0fe8d-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="0fe8d-147">0: 계정이 활성입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="0fe8d-148">1: 사용자의 SIP 기능이 사용하지 않도록 설정되었기 때문에 계정이 사용하지 않도록 설정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="0fe8d-149">2: 연결된 AD 개체가 삭제되었기 때문에 계정이 삭제되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fe8d-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="0fe8d-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-151">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0fe8d-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-152">계정 유형(tblPrincipalType 테이블)입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fe8d-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="0fe8d-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-154">임계값</span><span class="sxs-lookup"><span data-stu-id="0fe8d-154">Int</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-155">보안 주체에 대 한 Lync 풀 할당입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fe8d-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="0fe8d-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-157">임계값</span><span class="sxs-lookup"><span data-stu-id="0fe8d-157">Int</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-158">사용자에 대 한 영구 채팅 서버 정책 값 (tag type policy가 있는 경우)</span><span class="sxs-lookup"><span data-stu-id="0fe8d-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fe8d-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="0fe8d-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-160">int</span><span class="sxs-lookup"><span data-stu-id="0fe8d-160">int</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-161">작성자의 사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fe8d-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="0fe8d-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-163">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0fe8d-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-164">만든 시간에 대한 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fe8d-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="0fe8d-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-166">int</span><span class="sxs-lookup"><span data-stu-id="0fe8d-166">int</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-167">이 항목을 마지막으로 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0fe8d-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="0fe8d-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-169">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0fe8d-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-170">마지막 업데이트에 대한 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fe8d-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="0fe8d-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-172">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0fe8d-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-173">사용자에 대한 마지막 Active Directory 동기화 새로 고침의 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="0fe8d-174">키</span><span class="sxs-lookup"><span data-stu-id="0fe8d-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0fe8d-175">열</span><span class="sxs-lookup"><span data-stu-id="0fe8d-175">Column</span></span></th>
<th><span data-ttu-id="0fe8d-176">설명</span><span class="sxs-lookup"><span data-stu-id="0fe8d-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0fe8d-177">Tblprincipal.prinid</span><span class="sxs-lookup"><span data-stu-id="0fe8d-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-178">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0fe8d-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="0fe8d-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="0fe8d-180">tblPrincipalType.ptypeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0fe8d-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

