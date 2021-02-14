---
title: tblEnumValue
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
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue는 Node 테이블에 사용된 특성의 표시 및 동작 값이 포함된 하드코드된 테이블입니다.
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816028"
---
# <a name="tblenumvalue"></a><span data-ttu-id="a11a3-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="a11a3-103">tblEnumValue</span></span>
 
<span data-ttu-id="a11a3-104">tblEnumValue는 Node 테이블에 사용된 특성의 표시 및 동작 값이 포함된 하드코드된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="a11a3-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="a11a3-105">**열**</span><span class="sxs-lookup"><span data-stu-id="a11a3-105">**Columns**</span></span>

|<span data-ttu-id="a11a3-106">**열**</span><span class="sxs-lookup"><span data-stu-id="a11a3-106">**Column**</span></span>|<span data-ttu-id="a11a3-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="a11a3-107">**Type**</span></span>|<span data-ttu-id="a11a3-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="a11a3-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a11a3-109">valueID</span><span class="sxs-lookup"><span data-stu-id="a11a3-109">valueID</span></span>  <br/> |<span data-ttu-id="a11a3-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="a11a3-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="a11a3-111">값의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a11a3-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="a11a3-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="a11a3-112">attributeID</span></span>  <br/> |<span data-ttu-id="a11a3-113">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="a11a3-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="a11a3-114">특성의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a11a3-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="a11a3-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="a11a3-115">attributeValue</span></span>  <br/> |<span data-ttu-id="a11a3-116">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="a11a3-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="a11a3-117">값의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a11a3-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="a11a3-118">**키**</span><span class="sxs-lookup"><span data-stu-id="a11a3-118">**Keys**</span></span>

|<span data-ttu-id="a11a3-119">**열**</span><span class="sxs-lookup"><span data-stu-id="a11a3-119">**Column**</span></span>|<span data-ttu-id="a11a3-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="a11a3-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a11a3-121">valueID</span><span class="sxs-lookup"><span data-stu-id="a11a3-121">valueID</span></span>  <br/> |<span data-ttu-id="a11a3-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="a11a3-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a11a3-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="a11a3-123">attributeID</span></span>  <br/> |<span data-ttu-id="a11a3-124">tblEnumAttribute.attributeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="a11a3-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="a11a3-125">**테이블 값**</span><span class="sxs-lookup"><span data-stu-id="a11a3-125">**Table Values**</span></span>

|<span data-ttu-id="a11a3-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="a11a3-126">**valueID**</span></span>|<span data-ttu-id="a11a3-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="a11a3-127">**attributeID**</span></span>|<span data-ttu-id="a11a3-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="a11a3-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a11a3-129">2 </span><span class="sxs-lookup"><span data-stu-id="a11a3-129">2</span></span>  <br/> |<span data-ttu-id="a11a3-130">1 </span><span class="sxs-lookup"><span data-stu-id="a11a3-130">1</span></span>  <br/> |<span data-ttu-id="a11a3-131">private</span><span class="sxs-lookup"><span data-stu-id="a11a3-131">private</span></span>  <br/> |
|<span data-ttu-id="a11a3-132">3 </span><span class="sxs-lookup"><span data-stu-id="a11a3-132">3</span></span>  <br/> |<span data-ttu-id="a11a3-133">1 </span><span class="sxs-lookup"><span data-stu-id="a11a3-133">1</span></span>  <br/> |<span data-ttu-id="a11a3-134">범위</span><span class="sxs-lookup"><span data-stu-id="a11a3-134">scope</span></span>  <br/> |
|<span data-ttu-id="a11a3-135">4 </span><span class="sxs-lookup"><span data-stu-id="a11a3-135">4</span></span>  <br/> |<span data-ttu-id="a11a3-136">2 </span><span class="sxs-lookup"><span data-stu-id="a11a3-136">2</span></span>  <br/> |<span data-ttu-id="a11a3-137">normal</span><span class="sxs-lookup"><span data-stu-id="a11a3-137">normal</span></span>  <br/> |
|<span data-ttu-id="a11a3-138">5 </span><span class="sxs-lookup"><span data-stu-id="a11a3-138">5</span></span>  <br/> |<span data-ttu-id="a11a3-139">2 </span><span class="sxs-lookup"><span data-stu-id="a11a3-139">2</span></span>  <br/> |<span data-ttu-id="a11a3-140">강당</span><span class="sxs-lookup"><span data-stu-id="a11a3-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="a11a3-141">6 </span><span class="sxs-lookup"><span data-stu-id="a11a3-141">6</span></span>  <br/> |<span data-ttu-id="a11a3-142">1 </span><span class="sxs-lookup"><span data-stu-id="a11a3-142">1</span></span>  <br/> |<span data-ttu-id="a11a3-143">open</span><span class="sxs-lookup"><span data-stu-id="a11a3-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="a11a3-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a11a3-144">See also</span></span>

[<span data-ttu-id="a11a3-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="a11a3-145">tblNode</span></span>](tblnode.md)
