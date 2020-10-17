---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60fa841f7f88e0da2c428ae68c5007fb79e6c69d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536325"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="c4eb0-102">Lync Server 2013의 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="c4eb0-102">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c4eb0-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="c4eb0-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="c4eb0-104">tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류하기 위한 사용자 유형이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="c4eb0-105">단</span><span class="sxs-lookup"><span data-stu-id="c4eb0-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4eb0-106">열</span><span class="sxs-lookup"><span data-stu-id="c4eb0-106">Column</span></span></th>
<th><span data-ttu-id="c4eb0-107">유형</span><span class="sxs-lookup"><span data-stu-id="c4eb0-107">Type</span></span></th>
<th><span data-ttu-id="c4eb0-108">설명</span><span class="sxs-lookup"><span data-stu-id="c4eb0-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4eb0-109">Tblprincipaltype.ptypeid</span><span class="sxs-lookup"><span data-stu-id="c4eb0-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="c4eb0-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-111">사용자 유형 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4eb0-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="c4eb0-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-113">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="c4eb0-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-114">유형에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4eb0-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="c4eb0-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="c4eb0-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-117">유형이 내부 용도로 사용되는 사용자에 해당하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4eb0-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="c4eb0-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="c4eb0-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-120">유형이 사용자 유형인 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="c4eb0-121">키</span><span class="sxs-lookup"><span data-stu-id="c4eb0-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4eb0-122">열</span><span class="sxs-lookup"><span data-stu-id="c4eb0-122">Column</span></span></th>
<th><span data-ttu-id="c4eb0-123">설명</span><span class="sxs-lookup"><span data-stu-id="c4eb0-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4eb0-124">Tblprincipaltype.ptypeid</span><span class="sxs-lookup"><span data-stu-id="c4eb0-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="c4eb0-126">사용자 값</span><span class="sxs-lookup"><span data-stu-id="c4eb0-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c4eb0-127">ID</span><span class="sxs-lookup"><span data-stu-id="c4eb0-127">ID</span></span></th>
<th><span data-ttu-id="c4eb0-128">역할</span><span class="sxs-lookup"><span data-stu-id="c4eb0-128">Role</span></span></th>
<th><span data-ttu-id="c4eb0-129">설명</span><span class="sxs-lookup"><span data-stu-id="c4eb0-129">Description</span></span></th>
<th><span data-ttu-id="c4eb0-130">사용자</span><span class="sxs-lookup"><span data-stu-id="c4eb0-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c4eb0-131">1 </span><span class="sxs-lookup"><span data-stu-id="c4eb0-131">1</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-132">모두</span><span class="sxs-lookup"><span data-stu-id="c4eb0-132">Any</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-p101">유형이 알려지지 않은 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4eb0-135">2</span><span class="sxs-lookup"><span data-stu-id="c4eb0-135">2</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="c4eb0-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-p102">사용자 유형의 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-139">예</span><span class="sxs-lookup"><span data-stu-id="c4eb0-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4eb0-140">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="c4eb0-140">3</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="c4eb0-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-p103">그룹 체계를 포함하는 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4eb0-144">4 </span><span class="sxs-lookup"><span data-stu-id="c4eb0-144">4</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="c4eb0-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-146">영구 채팅 서버에서 내부적으로 사용 되는 보안 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4eb0-147">5 </span><span class="sxs-lookup"><span data-stu-id="c4eb0-147">5</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-148">사용자</span><span class="sxs-lookup"><span data-stu-id="c4eb0-148">User</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-149">일반 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-150">예</span><span class="sxs-lookup"><span data-stu-id="c4eb0-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4eb0-151">8 </span><span class="sxs-lookup"><span data-stu-id="c4eb0-151">8</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-152">AD</span><span class="sxs-lookup"><span data-stu-id="c4eb0-152">DC</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-153">Active Directory 도메인 서비스 도메인 컨트롤러입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c4eb0-154">9 </span><span class="sxs-lookup"><span data-stu-id="c4eb0-154">9</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-155">그룹</span><span class="sxs-lookup"><span data-stu-id="c4eb0-155">Group</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-156">Active Directory 보안 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c4eb0-157">10  </span><span class="sxs-lookup"><span data-stu-id="c4eb0-157">10</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-158">편지함</span><span class="sxs-lookup"><span data-stu-id="c4eb0-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="c4eb0-159">Active Directory 컨테이너 또는 조직 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="c4eb0-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="c4eb0-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c4eb0-160">See Also</span></span>


[<span data-ttu-id="c4eb0-161">Lync Server 2013의 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="c4eb0-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

