---
title: 'Lync Server 2013: tblPrincipalType'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblPrincipalType
ms:assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558633(v=OCS.15)
ms:contentKeyID: 48183787
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 725d097e1e2e75b6430974a4f133cb5fa4130346
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblprincipaltype-in-lync-server-2013"></a><span data-ttu-id="71b11-102">Lync Server 2013의 tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="71b11-102">tblPrincipalType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71b11-103">_**마지막으로 수정한 주제:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="71b11-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="71b11-104">tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류 하는 principal 형식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>

### <a name="columns"></a><span data-ttu-id="71b11-105">열</span><span class="sxs-lookup"><span data-stu-id="71b11-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71b11-106">열</span><span class="sxs-lookup"><span data-stu-id="71b11-106">Column</span></span></th>
<th><span data-ttu-id="71b11-107">유형</span><span class="sxs-lookup"><span data-stu-id="71b11-107">Type</span></span></th>
<th><span data-ttu-id="71b11-108">설명</span><span class="sxs-lookup"><span data-stu-id="71b11-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71b11-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="71b11-109">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="71b11-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="71b11-110">smallint, not null</span></span></p></td>
<td><p><span data-ttu-id="71b11-111">Principal type ID.</span><span class="sxs-lookup"><span data-stu-id="71b11-111">Principal type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b11-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="71b11-112">ptypeDesc</span></span></p></td>
<td><p><span data-ttu-id="71b11-113">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="71b11-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="71b11-114">형식에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-114">Description of the type.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b11-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="71b11-115">ptypeIsSystemUser</span></span></p></td>
<td><p><span data-ttu-id="71b11-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="71b11-116">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="71b11-117">내부 용도에 사용 되는 주체에 해당 하는 형식인 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-117">True if the type corresponds to the principals that are used for internal purposes.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b11-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="71b11-118">ptypeIsUser</span></span></p></td>
<td><p><span data-ttu-id="71b11-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="71b11-119">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="71b11-120">형식이 사용자 형식인 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-120">True if the type is a user type.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="71b11-121">키</span><span class="sxs-lookup"><span data-stu-id="71b11-121">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71b11-122">열</span><span class="sxs-lookup"><span data-stu-id="71b11-122">Column</span></span></th>
<th><span data-ttu-id="71b11-123">설명</span><span class="sxs-lookup"><span data-stu-id="71b11-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71b11-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="71b11-124">ptypeID</span></span></p></td>
<td><p><span data-ttu-id="71b11-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-125">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="principal-values"></a><span data-ttu-id="71b11-126">Principal 값</span><span class="sxs-lookup"><span data-stu-id="71b11-126">Principal Values</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71b11-127">I</span><span class="sxs-lookup"><span data-stu-id="71b11-127">ID</span></span></th>
<th><span data-ttu-id="71b11-128">역할</span><span class="sxs-lookup"><span data-stu-id="71b11-128">Role</span></span></th>
<th><span data-ttu-id="71b11-129">설명</span><span class="sxs-lookup"><span data-stu-id="71b11-129">Description</span></span></th>
<th><span data-ttu-id="71b11-130">사용자</span><span class="sxs-lookup"><span data-stu-id="71b11-130">User</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71b11-131">1</span><span class="sxs-lookup"><span data-stu-id="71b11-131">1</span></span></p></td>
<td><p><span data-ttu-id="71b11-132">이상</span><span class="sxs-lookup"><span data-stu-id="71b11-132">Any</span></span></p></td>
<td><p><span data-ttu-id="71b11-133">알려진 형식이 없는 일반 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-133">Generic principal with no known type.</span></span> <span data-ttu-id="71b11-134">TblPrincipal 테이블에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-134">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b11-135">2</span><span class="sxs-lookup"><span data-stu-id="71b11-135">2</span></span></p></td>
<td><p><span data-ttu-id="71b11-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="71b11-136">AnyUser</span></span></p></td>
<td><p><span data-ttu-id="71b11-137">사용자 유형의 일반 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-137">Generic principal of user type.</span></span> <span data-ttu-id="71b11-138">TblPrincipal 테이블에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-138">Not used in tblPrincipal table.</span></span></p></td>
<td><p><span data-ttu-id="71b11-139">예</span><span class="sxs-lookup"><span data-stu-id="71b11-139">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b11-140">3</span><span class="sxs-lookup"><span data-stu-id="71b11-140">3</span></span></p></td>
<td><p><span data-ttu-id="71b11-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="71b11-141">AnyGroup</span></span></p></td>
<td><p><span data-ttu-id="71b11-142">그룹 의미가 있는 일반 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-142">Generic principal with group semantic.</span></span> <span data-ttu-id="71b11-143">TblPrincipal 테이블에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-143">Not used in tblPrincipal table.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b11-144">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="71b11-144">4</span></span></p></td>
<td><p><span data-ttu-id="71b11-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="71b11-145">SystemUser</span></span></p></td>
<td><p><span data-ttu-id="71b11-146">영구 채팅 서버에서 내부적으로 사용 하는 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-146">Principal used internally by Persistent Chat Server.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b11-147">5mb</span><span class="sxs-lookup"><span data-stu-id="71b11-147">5</span></span></p></td>
<td><p><span data-ttu-id="71b11-148">사용자</span><span class="sxs-lookup"><span data-stu-id="71b11-148">User</span></span></p></td>
<td><p><span data-ttu-id="71b11-149">일반 사용자.</span><span class="sxs-lookup"><span data-stu-id="71b11-149">Regular user.</span></span></p></td>
<td><p><span data-ttu-id="71b11-150">예</span><span class="sxs-lookup"><span data-stu-id="71b11-150">Yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b11-151">20cm(8</span><span class="sxs-lookup"><span data-stu-id="71b11-151">8</span></span></p></td>
<td><p><span data-ttu-id="71b11-152">DC</span><span class="sxs-lookup"><span data-stu-id="71b11-152">DC</span></span></p></td>
<td><p><span data-ttu-id="71b11-153">Active Directory 도메인 서비스 도메인 컨트롤러.</span><span class="sxs-lookup"><span data-stu-id="71b11-153">Active Directory Domain Services domain controller.</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71b11-154">되었는지</span><span class="sxs-lookup"><span data-stu-id="71b11-154">9</span></span></p></td>
<td><p><span data-ttu-id="71b11-155">그룹과</span><span class="sxs-lookup"><span data-stu-id="71b11-155">Group</span></span></p></td>
<td><p><span data-ttu-id="71b11-156">Active Directory 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="71b11-156">Active Directory security group.</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71b11-157">1천만</span><span class="sxs-lookup"><span data-stu-id="71b11-157">10</span></span></p></td>
<td><p><span data-ttu-id="71b11-158">폴더</span><span class="sxs-lookup"><span data-stu-id="71b11-158">Folder</span></span></p></td>
<td><p><span data-ttu-id="71b11-159">Active Directory 컨테이너 또는 조직 구성 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="71b11-159">Active Directory container or organizational unit.</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


<div>

## <a name="see-also"></a><span data-ttu-id="71b11-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71b11-160">See Also</span></span>


[<span data-ttu-id="71b11-161">Lync Server 2013의 tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="71b11-161">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

