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
ms.openlocfilehash: 4da3af65a20d13ce4d4f1078e5ef76cbc67f402c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="e3ed8-102">Lync Server 2013의 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="e3ed8-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3ed8-103">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="e3ed8-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="e3ed8-104">tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류하기 위한 사용자 유형이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="e3ed8-105">단</span><span class="sxs-lookup"><span data-stu-id="e3ed8-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3ed8-106">열</span><span class="sxs-lookup"><span data-stu-id="e3ed8-106">Column</span></span></th>
<th><span data-ttu-id="e3ed8-107">형식</span><span class="sxs-lookup"><span data-stu-id="e3ed8-107">Type</span></span></th>
<th><span data-ttu-id="e3ed8-108">설명</span><span class="sxs-lookup"><span data-stu-id="e3ed8-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3ed8-109">Tblprincipaltype.ptypeid</span><span class="sxs-lookup"><span data-stu-id="e3ed8-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e3ed8-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-111">사용자 유형 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3ed8-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="e3ed8-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-113">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="e3ed8-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-114">유형에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3ed8-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="e3ed8-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e3ed8-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-117">유형이 내부 용도로 사용되는 사용자에 해당하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3ed8-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="e3ed8-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e3ed8-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-120">유형이 사용자 유형인 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="e3ed8-121">키</span><span class="sxs-lookup"><span data-stu-id="e3ed8-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3ed8-122">열</span><span class="sxs-lookup"><span data-stu-id="e3ed8-122">Column</span></span></th>
<th><span data-ttu-id="e3ed8-123">설명</span><span class="sxs-lookup"><span data-stu-id="e3ed8-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3ed8-124">Tblprincipaltype.ptypeid</span><span class="sxs-lookup"><span data-stu-id="e3ed8-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="e3ed8-126">사용자 값</span><span class="sxs-lookup"><span data-stu-id="e3ed8-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3ed8-127">ID</span><span class="sxs-lookup"><span data-stu-id="e3ed8-127">ID</span></span></th>
<th><span data-ttu-id="e3ed8-128">역할</span><span class="sxs-lookup"><span data-stu-id="e3ed8-128">Role</span></span></th>
<th><span data-ttu-id="e3ed8-129">설명</span><span class="sxs-lookup"><span data-stu-id="e3ed8-129">Description</span></span></th>
<th><span data-ttu-id="e3ed8-130">사용자</span><span class="sxs-lookup"><span data-stu-id="e3ed8-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3ed8-131">1 </span><span class="sxs-lookup"><span data-stu-id="e3ed8-131">1</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-132">모두</span><span class="sxs-lookup"><span data-stu-id="e3ed8-132">Any</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-p101">유형이 알려지지 않은 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3ed8-135">2 </span><span class="sxs-lookup"><span data-stu-id="e3ed8-135">2</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="e3ed8-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-p102">사용자 유형의 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-139">예</span><span class="sxs-lookup"><span data-stu-id="e3ed8-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3ed8-140">3 </span><span class="sxs-lookup"><span data-stu-id="e3ed8-140">3</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="e3ed8-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-p103">그룹 체계를 포함하는 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3ed8-144">4 </span><span class="sxs-lookup"><span data-stu-id="e3ed8-144">4</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="e3ed8-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-146">영구 채팅 서버에서 내부적으로 사용 되는 보안 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3ed8-147">5 </span><span class="sxs-lookup"><span data-stu-id="e3ed8-147">5</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-148">사용자</span><span class="sxs-lookup"><span data-stu-id="e3ed8-148">User</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-149">일반 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-150">예</span><span class="sxs-lookup"><span data-stu-id="e3ed8-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3ed8-151">8 </span><span class="sxs-lookup"><span data-stu-id="e3ed8-151">8</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-152">AD</span><span class="sxs-lookup"><span data-stu-id="e3ed8-152">DC</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-153">Active Directory 도메인 서비스 도메인 컨트롤러입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3ed8-154">9 </span><span class="sxs-lookup"><span data-stu-id="e3ed8-154">9</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-155">Group</span><span class="sxs-lookup"><span data-stu-id="e3ed8-155">Group</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-156">Active Directory 보안 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3ed8-157">10 </span><span class="sxs-lookup"><span data-stu-id="e3ed8-157">10</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-158">편지함</span><span class="sxs-lookup"><span data-stu-id="e3ed8-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="e3ed8-159">Active Directory 컨테이너 또는 조직 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="e3ed8-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="e3ed8-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3ed8-160">See Also</span></span>


[<span data-ttu-id="e3ed8-161">Lync Server 2013의 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="e3ed8-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

