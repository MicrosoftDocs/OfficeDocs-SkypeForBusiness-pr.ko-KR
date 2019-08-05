---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue는 노드 테이블에 사용 되는 특성의 Visibility 및 Behavior 값을 포함 하는 하드 코드 된 테이블입니다.
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196630"
---
# <a name="tblenumvalue"></a><span data-ttu-id="088fc-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="088fc-103">tblEnumValue</span></span>
 
<span data-ttu-id="088fc-104">tblEnumValue는 노드 테이블에 사용 되는 특성의 Visibility 및 Behavior 값을 포함 하는 하드 코드 된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="088fc-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="088fc-105">**열**</span><span class="sxs-lookup"><span data-stu-id="088fc-105">**Columns**</span></span>

|<span data-ttu-id="088fc-106">**열**</span><span class="sxs-lookup"><span data-stu-id="088fc-106">**Column**</span></span>|<span data-ttu-id="088fc-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="088fc-107">**Type**</span></span>|<span data-ttu-id="088fc-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="088fc-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="088fc-109">고 대 Eid</span><span class="sxs-lookup"><span data-stu-id="088fc-109">valueID</span></span>  <br/> |<span data-ttu-id="088fc-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="088fc-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="088fc-111">값의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="088fc-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="088fc-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="088fc-112">attributeID</span></span>  <br/> |<span data-ttu-id="088fc-113">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="088fc-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="088fc-114">특성의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="088fc-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="088fc-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="088fc-115">attributeValue</span></span>  <br/> |<span data-ttu-id="088fc-116">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="088fc-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="088fc-117">값의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="088fc-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="088fc-118">**핵심**</span><span class="sxs-lookup"><span data-stu-id="088fc-118">**Keys**</span></span>

|<span data-ttu-id="088fc-119">**열**</span><span class="sxs-lookup"><span data-stu-id="088fc-119">**Column**</span></span>|<span data-ttu-id="088fc-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="088fc-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="088fc-121">고 대 Eid</span><span class="sxs-lookup"><span data-stu-id="088fc-121">valueID</span></span>  <br/> |<span data-ttu-id="088fc-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="088fc-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="088fc-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="088fc-123">attributeID</span></span>  <br/> |<span data-ttu-id="088fc-124">TblEnumAttribute의 조회가 포함 되어 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="088fc-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="088fc-125">**테이블 값**</span><span class="sxs-lookup"><span data-stu-id="088fc-125">**Table Values**</span></span>

|<span data-ttu-id="088fc-126">**고 대 Eid**</span><span class="sxs-lookup"><span data-stu-id="088fc-126">**valueID**</span></span>|<span data-ttu-id="088fc-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="088fc-127">**attributeID**</span></span>|<span data-ttu-id="088fc-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="088fc-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="088fc-129">2</span><span class="sxs-lookup"><span data-stu-id="088fc-129">2</span></span>  <br/> |<span data-ttu-id="088fc-130">raid-1</span><span class="sxs-lookup"><span data-stu-id="088fc-130">1</span></span>  <br/> |<span data-ttu-id="088fc-131">개인용</span><span class="sxs-lookup"><span data-stu-id="088fc-131">private</span></span>  <br/> |
|<span data-ttu-id="088fc-132">3-4</span><span class="sxs-lookup"><span data-stu-id="088fc-132">3</span></span>  <br/> |<span data-ttu-id="088fc-133">raid-1</span><span class="sxs-lookup"><span data-stu-id="088fc-133">1</span></span>  <br/> |<span data-ttu-id="088fc-134">범위도</span><span class="sxs-lookup"><span data-stu-id="088fc-134">scope</span></span>  <br/> |
|<span data-ttu-id="088fc-135">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="088fc-135">4</span></span>  <br/> |<span data-ttu-id="088fc-136">2</span><span class="sxs-lookup"><span data-stu-id="088fc-136">2</span></span>  <br/> |<span data-ttu-id="088fc-137">크기로</span><span class="sxs-lookup"><span data-stu-id="088fc-137">normal</span></span>  <br/> |
|<span data-ttu-id="088fc-138">5mb</span><span class="sxs-lookup"><span data-stu-id="088fc-138">5</span></span>  <br/> |<span data-ttu-id="088fc-139">2</span><span class="sxs-lookup"><span data-stu-id="088fc-139">2</span></span>  <br/> |<span data-ttu-id="088fc-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="088fc-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="088fc-141">26</span><span class="sxs-lookup"><span data-stu-id="088fc-141">6</span></span>  <br/> |<span data-ttu-id="088fc-142">raid-1</span><span class="sxs-lookup"><span data-stu-id="088fc-142">1</span></span>  <br/> |<span data-ttu-id="088fc-143">열면</span><span class="sxs-lookup"><span data-stu-id="088fc-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="088fc-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="088fc-144">See also</span></span>

[<span data-ttu-id="088fc-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="088fc-145">tblNode</span></span>](tblnode.md)
