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
ms.openlocfilehash: 25de9273fb6e153bb154bf0062edd96cb67bbac2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipal-in-lync-server-2013"></a><span data-ttu-id="10cfb-102">Lync Server 2013의 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="10cfb-102">tblPrincipal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10cfb-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="10cfb-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="10cfb-104">tblPrincipal 사용자, 폴더 및 그룹을 비롯 한 모든 사용자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-104">tblPrincipal contains all principals, including users, folders, and groups.</span></span>

### <a name="columns"></a><span data-ttu-id="10cfb-105">열</span><span class="sxs-lookup"><span data-stu-id="10cfb-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10cfb-106">열</span><span class="sxs-lookup"><span data-stu-id="10cfb-106">Column</span></span></th>
<th><span data-ttu-id="10cfb-107">유형</span><span class="sxs-lookup"><span data-stu-id="10cfb-107">Type</span></span></th>
<th><span data-ttu-id="10cfb-108">설명</span><span class="sxs-lookup"><span data-stu-id="10cfb-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10cfb-109">prinID</span><span class="sxs-lookup"><span data-stu-id="10cfb-109">prinID</span></span></p></td>
<td><p><span data-ttu-id="10cfb-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="10cfb-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="10cfb-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="10cfb-111">Principal ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cfb-112">prinGuid</span><span class="sxs-lookup"><span data-stu-id="10cfb-112">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="10cfb-113">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="10cfb-113">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="10cfb-114">Principal GUID.</span><span class="sxs-lookup"><span data-stu-id="10cfb-114">Principal GUID.</span></span> <span data-ttu-id="10cfb-115">이는 해당 의미가 Active Directory 도메인 서비스 공간으로 교차 되므로 대체 기본 키로 광범위 하 게 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-115">This is broadly used as an alternate primary key because its meaning crosses over into the Active Directory Domain Services space.</span></span> <span data-ttu-id="10cfb-116">(캐시 된 보안 주체의 GUID는 해당 Active Directory 개체 GUID와 같습니다.)</span><span class="sxs-lookup"><span data-stu-id="10cfb-116">(The GUID for a cached principal is equal to the corresponding Active Directory object GUID.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cfb-117">prinUri</span><span class="sxs-lookup"><span data-stu-id="10cfb-117">prinUri</span></span></p></td>
<td><p><span data-ttu-id="10cfb-118">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="10cfb-118">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="10cfb-119">Principal URI.</span><span class="sxs-lookup"><span data-stu-id="10cfb-119">Principal URI.</span></span> <span data-ttu-id="10cfb-120">SIP 스키마는 사용자에 게 사용 되며 ma는 거의 모든 내용에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-120">The SIP scheme is used for users, and ma-grp is used for almost everything else.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cfb-121">prinName</span><span class="sxs-lookup"><span data-stu-id="10cfb-121">prinName</span></span></p></td>
<td><p><span data-ttu-id="10cfb-122">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10cfb-122">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="10cfb-123">일반 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-123">Common name.</span></span> <span data-ttu-id="10cfb-124">사용자 유형별로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-124">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cfb-125">prinDisplayName</span><span class="sxs-lookup"><span data-stu-id="10cfb-125">prinDisplayName</span></span></p></td>
<td><p><span data-ttu-id="10cfb-126">Nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10cfb-126">Nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="10cfb-127">표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-127">Display name.</span></span> <span data-ttu-id="10cfb-128">사용자 유형별로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-128">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cfb-129">prinCompanyName</span><span class="sxs-lookup"><span data-stu-id="10cfb-129">prinCompanyName</span></span></p></td>
<td><p><span data-ttu-id="10cfb-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10cfb-130">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="10cfb-131">회사 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-131">Company name.</span></span> <span data-ttu-id="10cfb-132">사용자 유형별로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-132">Used only by user types.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cfb-133">prinEmail</span><span class="sxs-lookup"><span data-stu-id="10cfb-133">prinEmail</span></span></p></td>
<td><p><span data-ttu-id="10cfb-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10cfb-134">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="10cfb-135">메일 주소.</span><span class="sxs-lookup"><span data-stu-id="10cfb-135">Email.</span></span> <span data-ttu-id="10cfb-136">사용자 유형별로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-136">Used only by user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cfb-137">prinADPath</span><span class="sxs-lookup"><span data-stu-id="10cfb-137">prinADPath</span></span></p></td>
<td><p><span data-ttu-id="10cfb-138">nvarchar (384)</span><span class="sxs-lookup"><span data-stu-id="10cfb-138">nvarchar (384)</span></span></p></td>
<td><p><span data-ttu-id="10cfb-139">주체가 캐시 된 버전인 Active Directory 개체의 도메인 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-139">Domain name of the Active Directory object that the principal is a cached version of.</span></span> <span data-ttu-id="10cfb-140">Active Directory 개체 (예: 시스템 사용자)가 아닌 형식의 경우 Null이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-140">Can be Null for types that are not Active Directory objects (such as system users).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cfb-141">prinADUserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="10cfb-141">prinADUserPrincipalName</span></span></p></td>
<td><p><span data-ttu-id="10cfb-142">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="10cfb-142">nvarchar (256)</span></span></p></td>
<td><p><span data-ttu-id="10cfb-143">사용자의 UPN (사용자 계정 이름).</span><span class="sxs-lookup"><span data-stu-id="10cfb-143">User’s user principal name (UPN).</span></span> <span data-ttu-id="10cfb-144">일반 사용자 형식 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-144">Used only by regular user types.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cfb-145">prinDisabled</span><span class="sxs-lookup"><span data-stu-id="10cfb-145">prinDisabled</span></span></p></td>
<td><p><span data-ttu-id="10cfb-146">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="10cfb-146">smallint, not null</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="10cfb-147">0: 주체가 활성 상태입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-147">0: Principal is active.</span></span></p></li>
<li><p><span data-ttu-id="10cfb-148">1: 사용자의 SIP 접근 권한 값을 사용할 수 없기 때문에 Principal을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-148">1: Principal is disabled because user’s SIP capabilities are disabled.</span></span></p></li>
<li><p><span data-ttu-id="10cfb-149">2: 연결 된 광고 개체가 삭제 되어 주체가 삭제 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-149">2: Principal is deleted because associated AD object has been deleted.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cfb-150">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="10cfb-150">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="10cfb-151">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="10cfb-151">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="10cfb-152">Principal type (tblPrincipalType 테이블에서)</span><span class="sxs-lookup"><span data-stu-id="10cfb-152">Principal type (from tblPrincipalType table).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cfb-153">prinPoolID</span><span class="sxs-lookup"><span data-stu-id="10cfb-153">prinPoolID</span></span></p></td>
<td><p><span data-ttu-id="10cfb-154">Int</span><span class="sxs-lookup"><span data-stu-id="10cfb-154">Int</span></span></p></td>
<td><p><span data-ttu-id="10cfb-155">주도자에 대 한 Lync 풀 할당입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-155">Lync pool assignment for the principal.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cfb-156">prinPolicyID</span><span class="sxs-lookup"><span data-stu-id="10cfb-156">prinPolicyID</span></span></p></td>
<td><p><span data-ttu-id="10cfb-157">Int</span><span class="sxs-lookup"><span data-stu-id="10cfb-157">Int</span></span></p></td>
<td><p><span data-ttu-id="10cfb-158">태그 유형 정책이 있는 경우 사용자에 대 한 영구 채팅 서버 정책 값</span><span class="sxs-lookup"><span data-stu-id="10cfb-158">Persistent Chat Server policy value for user, if tag type policy is present.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cfb-159">prinAddedBy</span><span class="sxs-lookup"><span data-stu-id="10cfb-159">prinAddedBy</span></span></p></td>
<td><p><span data-ttu-id="10cfb-160">int</span><span class="sxs-lookup"><span data-stu-id="10cfb-160">int</span></span></p></td>
<td><p><span data-ttu-id="10cfb-161">작성자의 사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-161">Principal ID of the creator.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cfb-162">prinAddedOn</span><span class="sxs-lookup"><span data-stu-id="10cfb-162">prinAddedOn</span></span></p></td>
<td><p><span data-ttu-id="10cfb-163">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="10cfb-163">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="10cfb-164">만든 시간에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-164">Time stamp for the creation time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cfb-165">prinUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="10cfb-165">prinUpdatedBy</span></span></p></td>
<td><p><span data-ttu-id="10cfb-166">int</span><span class="sxs-lookup"><span data-stu-id="10cfb-166">int</span></span></p></td>
<td><p><span data-ttu-id="10cfb-167">이를 마지막으로 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-167">ID of the principal that last updated this.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10cfb-168">prinUpdatedOn</span><span class="sxs-lookup"><span data-stu-id="10cfb-168">prinUpdatedOn</span></span></p></td>
<td><p><span data-ttu-id="10cfb-169">bigint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="10cfb-169">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="10cfb-170">마지막 업데이트에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-170">Time stamp for the last update.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cfb-171">prinVerifiedOn</span><span class="sxs-lookup"><span data-stu-id="10cfb-171">prinVerifiedOn</span></span></p></td>
<td><p><span data-ttu-id="10cfb-172">datetime, null 아님</span><span class="sxs-lookup"><span data-stu-id="10cfb-172">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="10cfb-173">주도자에 대 한 마지막 Active Directory 동기화 새로 고침의 날짜 및 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-173">Date and time of the last Active Directory Sync refresh for the principal.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="10cfb-174">핵심</span><span class="sxs-lookup"><span data-stu-id="10cfb-174">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10cfb-175">열</span><span class="sxs-lookup"><span data-stu-id="10cfb-175">Column</span></span></th>
<th><span data-ttu-id="10cfb-176">설명</span><span class="sxs-lookup"><span data-stu-id="10cfb-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10cfb-177">prinID</span><span class="sxs-lookup"><span data-stu-id="10cfb-177">prinID</span></span></p></td>
<td><p><span data-ttu-id="10cfb-178">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-178">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10cfb-179">prinTypeID</span><span class="sxs-lookup"><span data-stu-id="10cfb-179">prinTypeID</span></span></p></td>
<td><p><span data-ttu-id="10cfb-180">TblPrincipalType에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="10cfb-180">Foreign key with lookup in tblPrincipalType.ptypeID table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

