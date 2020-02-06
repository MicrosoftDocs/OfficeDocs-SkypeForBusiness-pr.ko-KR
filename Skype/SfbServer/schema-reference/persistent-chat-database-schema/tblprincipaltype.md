---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류 하는 principal 형식이 포함 되어 있습니다.
ms.openlocfilehash: 1aacfdf34689bebc2c7e012c926731ae1f4a8349
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812936"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="75866-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="75866-103">tblPrincipalType</span></span>
 
<span data-ttu-id="75866-104">tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류 하는 principal 형식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75866-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="75866-105">**열**</span><span class="sxs-lookup"><span data-stu-id="75866-105">**Columns**</span></span>

|<span data-ttu-id="75866-106">**열**</span><span class="sxs-lookup"><span data-stu-id="75866-106">**Column**</span></span>|<span data-ttu-id="75866-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="75866-107">**Type**</span></span>|<span data-ttu-id="75866-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="75866-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="75866-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="75866-109">ptypeID</span></span>  <br/> |<span data-ttu-id="75866-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="75866-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="75866-111">Principal type ID.</span><span class="sxs-lookup"><span data-stu-id="75866-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="75866-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="75866-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="75866-113">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="75866-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="75866-114">형식에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="75866-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="75866-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="75866-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="75866-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="75866-116">bit, not null</span></span>  <br/> |<span data-ttu-id="75866-117">내부 용도에 사용 되는 주체에 해당 하는 형식인 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="75866-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="75866-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="75866-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="75866-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="75866-119">bit, not null</span></span>  <br/> |<span data-ttu-id="75866-120">형식이 사용자 형식인 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="75866-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="75866-121">**키**</span><span class="sxs-lookup"><span data-stu-id="75866-121">**Key**</span></span>

|<span data-ttu-id="75866-122">**열**</span><span class="sxs-lookup"><span data-stu-id="75866-122">**Column**</span></span>|<span data-ttu-id="75866-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="75866-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="75866-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="75866-124">ptypeID</span></span>  <br/> |<span data-ttu-id="75866-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="75866-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="75866-126">**Principal 값**</span><span class="sxs-lookup"><span data-stu-id="75866-126">**Principal Values**</span></span>

|<span data-ttu-id="75866-127">**I**</span><span class="sxs-lookup"><span data-stu-id="75866-127">**ID**</span></span>|<span data-ttu-id="75866-128">**역할인**</span><span class="sxs-lookup"><span data-stu-id="75866-128">**Role**</span></span>|<span data-ttu-id="75866-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="75866-129">**Description**</span></span>|<span data-ttu-id="75866-130">**사용자**</span><span class="sxs-lookup"><span data-stu-id="75866-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="75866-131">1</span><span class="sxs-lookup"><span data-stu-id="75866-131">1</span></span>  <br/> |<span data-ttu-id="75866-132">이상</span><span class="sxs-lookup"><span data-stu-id="75866-132">Any</span></span>  <br/> |<span data-ttu-id="75866-133">알려진 형식이 없는 일반 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="75866-133">Generic principal with no known type.</span></span> <span data-ttu-id="75866-134">TblPrincipal 테이블에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75866-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="75866-135">2</span><span class="sxs-lookup"><span data-stu-id="75866-135">2</span></span>  <br/> |<span data-ttu-id="75866-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="75866-136">AnyUser</span></span>  <br/> |<span data-ttu-id="75866-137">사용자 유형의 일반 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="75866-137">Generic principal of user type.</span></span> <span data-ttu-id="75866-138">TblPrincipal 테이블에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75866-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="75866-139">예</span><span class="sxs-lookup"><span data-stu-id="75866-139">Yes</span></span>  <br/> |
|<span data-ttu-id="75866-140">3</span><span class="sxs-lookup"><span data-stu-id="75866-140">3</span></span>  <br/> |<span data-ttu-id="75866-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="75866-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="75866-142">그룹 의미가 있는 일반 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="75866-142">Generic principal with group semantic.</span></span> <span data-ttu-id="75866-143">TblPrincipal 테이블에서 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75866-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="75866-144">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="75866-144">4</span></span>  <br/> |<span data-ttu-id="75866-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="75866-145">SystemUser</span></span>  <br/> |<span data-ttu-id="75866-146">영구 채팅 서버에서 내부적으로 사용 하는 주체입니다.</span><span class="sxs-lookup"><span data-stu-id="75866-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="75866-147">5mb</span><span class="sxs-lookup"><span data-stu-id="75866-147">5</span></span>  <br/> |<span data-ttu-id="75866-148">사용자</span><span class="sxs-lookup"><span data-stu-id="75866-148">User</span></span>  <br/> |<span data-ttu-id="75866-149">일반 사용자.</span><span class="sxs-lookup"><span data-stu-id="75866-149">Regular user.</span></span>  <br/> |<span data-ttu-id="75866-150">예</span><span class="sxs-lookup"><span data-stu-id="75866-150">Yes</span></span>  <br/> |
|<span data-ttu-id="75866-151">20cm(8</span><span class="sxs-lookup"><span data-stu-id="75866-151">8</span></span>  <br/> |<span data-ttu-id="75866-152">DC</span><span class="sxs-lookup"><span data-stu-id="75866-152">DC</span></span>  <br/> |<span data-ttu-id="75866-153">Active Directory 도메인 서비스 도메인 컨트롤러.</span><span class="sxs-lookup"><span data-stu-id="75866-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="75866-154">되었는지</span><span class="sxs-lookup"><span data-stu-id="75866-154">9</span></span>  <br/> |<span data-ttu-id="75866-155">그룹과</span><span class="sxs-lookup"><span data-stu-id="75866-155">Group</span></span>  <br/> |<span data-ttu-id="75866-156">Active Directory 보안 그룹</span><span class="sxs-lookup"><span data-stu-id="75866-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="75866-157">1천만</span><span class="sxs-lookup"><span data-stu-id="75866-157">10</span></span>  <br/> |<span data-ttu-id="75866-158">폴더</span><span class="sxs-lookup"><span data-stu-id="75866-158">Folder</span></span>  <br/> |<span data-ttu-id="75866-159">Active Directory 컨테이너 또는 조직 구성 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="75866-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="75866-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="75866-160">See also</span></span>

[<span data-ttu-id="75866-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="75866-161">tblPrincipal</span></span>](tblprincipal.md)
