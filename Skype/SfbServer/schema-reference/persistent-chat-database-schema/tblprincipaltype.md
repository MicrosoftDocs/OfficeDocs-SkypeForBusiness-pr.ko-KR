---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류하기 위한 사용자 유형이 포함됩니다.
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831538"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="ff82d-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="ff82d-103">tblPrincipalType</span></span>
 
<span data-ttu-id="ff82d-104">tblPrincipalType에는 tblPrincipal 테이블에 있는 항목을 분류하기 위한 사용자 유형이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="ff82d-105">**열**</span><span class="sxs-lookup"><span data-stu-id="ff82d-105">**Columns**</span></span>

|<span data-ttu-id="ff82d-106">**열**</span><span class="sxs-lookup"><span data-stu-id="ff82d-106">**Column**</span></span>|<span data-ttu-id="ff82d-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="ff82d-107">**Type**</span></span>|<span data-ttu-id="ff82d-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="ff82d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ff82d-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="ff82d-109">ptypeID</span></span>  <br/> |<span data-ttu-id="ff82d-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="ff82d-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="ff82d-111">사용자 유형 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="ff82d-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="ff82d-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="ff82d-113">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="ff82d-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="ff82d-114">유형에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="ff82d-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="ff82d-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="ff82d-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="ff82d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="ff82d-117">유형이 내부 용도로 사용되는 사용자에 해당하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="ff82d-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="ff82d-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="ff82d-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="ff82d-119">bit, not null</span></span>  <br/> |<span data-ttu-id="ff82d-120">유형이 사용자 유형인 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="ff82d-121">**키**</span><span class="sxs-lookup"><span data-stu-id="ff82d-121">**Key**</span></span>

|<span data-ttu-id="ff82d-122">**열**</span><span class="sxs-lookup"><span data-stu-id="ff82d-122">**Column**</span></span>|<span data-ttu-id="ff82d-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="ff82d-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ff82d-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="ff82d-124">ptypeID</span></span>  <br/> |<span data-ttu-id="ff82d-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="ff82d-126">**사용자 값**</span><span class="sxs-lookup"><span data-stu-id="ff82d-126">**Principal Values**</span></span>

|<span data-ttu-id="ff82d-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="ff82d-127">**ID**</span></span>|<span data-ttu-id="ff82d-128">**역할**</span><span class="sxs-lookup"><span data-stu-id="ff82d-128">**Role**</span></span>|<span data-ttu-id="ff82d-129">**설명**</span><span class="sxs-lookup"><span data-stu-id="ff82d-129">**Description**</span></span>|<span data-ttu-id="ff82d-130">**사용자**</span><span class="sxs-lookup"><span data-stu-id="ff82d-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ff82d-131">1 </span><span class="sxs-lookup"><span data-stu-id="ff82d-131">1</span></span>  <br/> |<span data-ttu-id="ff82d-132">모두</span><span class="sxs-lookup"><span data-stu-id="ff82d-132">Any</span></span>  <br/> |<span data-ttu-id="ff82d-p101">유형이 알려지지 않은 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="ff82d-135">2 </span><span class="sxs-lookup"><span data-stu-id="ff82d-135">2</span></span>  <br/> |<span data-ttu-id="ff82d-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="ff82d-136">AnyUser</span></span>  <br/> |<span data-ttu-id="ff82d-p102">사용자 유형의 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="ff82d-139">예</span><span class="sxs-lookup"><span data-stu-id="ff82d-139">Yes</span></span>  <br/> |
|<span data-ttu-id="ff82d-140">3 </span><span class="sxs-lookup"><span data-stu-id="ff82d-140">3</span></span>  <br/> |<span data-ttu-id="ff82d-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="ff82d-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="ff82d-p103">그룹 체계를 포함하는 일반 사용자입니다. tblPrincipal 테이블에서 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="ff82d-144">4 </span><span class="sxs-lookup"><span data-stu-id="ff82d-144">4</span></span>  <br/> |<span data-ttu-id="ff82d-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="ff82d-145">SystemUser</span></span>  <br/> |<span data-ttu-id="ff82d-146">영구 채팅 서버에서 내부적으로 사용되는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="ff82d-147">5 </span><span class="sxs-lookup"><span data-stu-id="ff82d-147">5</span></span>  <br/> |<span data-ttu-id="ff82d-148">사용자</span><span class="sxs-lookup"><span data-stu-id="ff82d-148">User</span></span>  <br/> |<span data-ttu-id="ff82d-149">일반 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-149">Regular user.</span></span>  <br/> |<span data-ttu-id="ff82d-150">예</span><span class="sxs-lookup"><span data-stu-id="ff82d-150">Yes</span></span>  <br/> |
|<span data-ttu-id="ff82d-151">8 </span><span class="sxs-lookup"><span data-stu-id="ff82d-151">8</span></span>  <br/> |<span data-ttu-id="ff82d-152">DC</span><span class="sxs-lookup"><span data-stu-id="ff82d-152">DC</span></span>  <br/> |<span data-ttu-id="ff82d-153">Active Directory 도메인 서비스 도메인 컨트롤러.</span><span class="sxs-lookup"><span data-stu-id="ff82d-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="ff82d-154">9 </span><span class="sxs-lookup"><span data-stu-id="ff82d-154">9</span></span>  <br/> |<span data-ttu-id="ff82d-155">그룹</span><span class="sxs-lookup"><span data-stu-id="ff82d-155">Group</span></span>  <br/> |<span data-ttu-id="ff82d-156">Active Directory 보안 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="ff82d-157">10  </span><span class="sxs-lookup"><span data-stu-id="ff82d-157">10</span></span>  <br/> |<span data-ttu-id="ff82d-158">폴더</span><span class="sxs-lookup"><span data-stu-id="ff82d-158">Folder</span></span>  <br/> |<span data-ttu-id="ff82d-159">Active Directory 컨테이너 또는 조직 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="ff82d-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="ff82d-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ff82d-160">See also</span></span>

[<span data-ttu-id="ff82d-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="ff82d-161">tblPrincipal</span></span>](tblprincipal.md)
