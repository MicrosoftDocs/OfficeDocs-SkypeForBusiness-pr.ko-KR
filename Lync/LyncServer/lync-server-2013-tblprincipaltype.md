---
title: 'Lync Server 2013: tblPrincipalType'
description: 'Lync Server 2013: tblPrincipalType'
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
ms.openlocfilehash: ba0f607d4499b54b16d7ecf8a4e7de603e874788
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549864"
---
# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="79382-103">Lync Server 2013의 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="79382-103">tblPrincipalType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="79382-104">_**마지막으로 수정 된 항목:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="79382-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="79382-105">tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류하기 위한 사용자 유형이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="79382-105">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="79382-106">단</span><span class="sxs-lookup"><span data-stu-id="79382-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79382-107">열</span><span class="sxs-lookup"><span data-stu-id="79382-107">Column</span></span></th>
<th><span data-ttu-id="79382-108">유형</span><span class="sxs-lookup"><span data-stu-id="79382-108">Type</span></span></th>
<th><span data-ttu-id="79382-109">설명</span><span class="sxs-lookup"><span data-stu-id="79382-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79382-110">Tblprincipaltype.ptypeid</span><span class="sxs-lookup"><span data-stu-id="79382-110">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="79382-111">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="79382-111">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="79382-112">사용자 유형 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="79382-112">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79382-113">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="79382-113">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="79382-114">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="79382-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="79382-115">유형에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="79382-115">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79382-116">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="79382-116">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="79382-117">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="79382-117">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="79382-118">유형이 내부 용도로 사용되는 사용자에 해당하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="79382-118">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79382-119">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="79382-119">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="79382-120">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="79382-120">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="79382-121">유형이 사용자 유형인 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="79382-121">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="79382-122">키</span><span class="sxs-lookup"><span data-stu-id="79382-122">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79382-123">열</span><span class="sxs-lookup"><span data-stu-id="79382-123">Column</span></span></th>
<th><span data-ttu-id="79382-124">설명</span><span class="sxs-lookup"><span data-stu-id="79382-124">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79382-125">Tblprincipaltype.ptypeid</span><span class="sxs-lookup"><span data-stu-id="79382-125">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="79382-126">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="79382-126">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="79382-127">사용자 값</span><span class="sxs-lookup"><span data-stu-id="79382-127">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="79382-128">ID</span><span class="sxs-lookup"><span data-stu-id="79382-128">ID</span></span></th>
<th><span data-ttu-id="79382-129">역할</span><span class="sxs-lookup"><span data-stu-id="79382-129">Role</span></span></th>
<th><span data-ttu-id="79382-130">설명</span><span class="sxs-lookup"><span data-stu-id="79382-130">Description</span></span></th>
<th><span data-ttu-id="79382-131">사용자</span><span class="sxs-lookup"><span data-stu-id="79382-131">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="79382-132">1 </span><span class="sxs-lookup"><span data-stu-id="79382-132">1</span></span></p></td>
<td><p><span data-ttu-id="79382-133">모두</span><span class="sxs-lookup"><span data-stu-id="79382-133">Any</span></span></p></td>
<td><p><span data-ttu-id="79382-p101">유형이 알려지지 않은 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79382-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79382-136">2</span><span class="sxs-lookup"><span data-stu-id="79382-136">2</span></span></p></td>
<td><p><span data-ttu-id="79382-137">AnyUser</span><span class="sxs-lookup"><span data-stu-id="79382-137">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="79382-p102">사용자 유형의 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79382-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="79382-140">예</span><span class="sxs-lookup"><span data-stu-id="79382-140">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79382-141">3(sp3)</span><span class="sxs-lookup"><span data-stu-id="79382-141">3</span></span></p></td>
<td><p><span data-ttu-id="79382-142">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="79382-142">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="79382-p103">그룹 체계를 포함하는 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79382-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79382-145">4 </span><span class="sxs-lookup"><span data-stu-id="79382-145">4</span></span></p></td>
<td><p><span data-ttu-id="79382-146">SystemUser</span><span class="sxs-lookup"><span data-stu-id="79382-146">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="79382-147">영구 채팅 서버에서 내부적으로 사용 되는 보안 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="79382-147">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79382-148">5 </span><span class="sxs-lookup"><span data-stu-id="79382-148">5</span></span></p></td>
<td><p><span data-ttu-id="79382-149">사용자</span><span class="sxs-lookup"><span data-stu-id="79382-149">User</span></span></p></td>
<td><p><span data-ttu-id="79382-150">일반 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="79382-150">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="79382-151">예</span><span class="sxs-lookup"><span data-stu-id="79382-151">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79382-152">8 </span><span class="sxs-lookup"><span data-stu-id="79382-152">8</span></span></p></td>
<td><p><span data-ttu-id="79382-153">AD</span><span class="sxs-lookup"><span data-stu-id="79382-153">DC</span></span></p></td>
<td><p><span data-ttu-id="79382-154">Active Directory 도메인 서비스 도메인 컨트롤러입니다.</span><span class="sxs-lookup"><span data-stu-id="79382-154">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="79382-155">9 </span><span class="sxs-lookup"><span data-stu-id="79382-155">9</span></span></p></td>
<td><p><span data-ttu-id="79382-156">그룹</span><span class="sxs-lookup"><span data-stu-id="79382-156">Group</span></span></p></td>
<td><p><span data-ttu-id="79382-157">Active Directory 보안 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="79382-157">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="79382-158">10  </span><span class="sxs-lookup"><span data-stu-id="79382-158">10</span></span></p></td>
<td><p><span data-ttu-id="79382-159">편지함</span><span class="sxs-lookup"><span data-stu-id="79382-159">Folder</span></span></p></td>
<td><p><span data-ttu-id="79382-160">Active Directory 컨테이너 또는 조직 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="79382-160">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="79382-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79382-161">See Also</span></span>


[<span data-ttu-id="79382-162">Lync Server 2013의 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="79382-162">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

