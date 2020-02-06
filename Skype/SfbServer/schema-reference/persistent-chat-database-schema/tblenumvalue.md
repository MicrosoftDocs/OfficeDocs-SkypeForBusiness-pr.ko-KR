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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue는 노드 테이블에 사용 되는 특성의 Visibility 및 Behavior 값을 포함 하는 하드 코드 된 테이블입니다.
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814606"
---
# <a name="tblenumvalue"></a><span data-ttu-id="1584c-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="1584c-103">tblEnumValue</span></span>
 
<span data-ttu-id="1584c-104">tblEnumValue는 노드 테이블에 사용 되는 특성의 Visibility 및 Behavior 값을 포함 하는 하드 코드 된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="1584c-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="1584c-105">**열**</span><span class="sxs-lookup"><span data-stu-id="1584c-105">**Columns**</span></span>

|<span data-ttu-id="1584c-106">**열**</span><span class="sxs-lookup"><span data-stu-id="1584c-106">**Column**</span></span>|<span data-ttu-id="1584c-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="1584c-107">**Type**</span></span>|<span data-ttu-id="1584c-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="1584c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1584c-109">고 대 Eid</span><span class="sxs-lookup"><span data-stu-id="1584c-109">valueID</span></span>  <br/> |<span data-ttu-id="1584c-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="1584c-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="1584c-111">값의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1584c-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="1584c-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="1584c-112">attributeID</span></span>  <br/> |<span data-ttu-id="1584c-113">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="1584c-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="1584c-114">특성의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1584c-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="1584c-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="1584c-115">attributeValue</span></span>  <br/> |<span data-ttu-id="1584c-116">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="1584c-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="1584c-117">값의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1584c-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="1584c-118">**핵심**</span><span class="sxs-lookup"><span data-stu-id="1584c-118">**Keys**</span></span>

|<span data-ttu-id="1584c-119">**열**</span><span class="sxs-lookup"><span data-stu-id="1584c-119">**Column**</span></span>|<span data-ttu-id="1584c-120">**설명**</span><span class="sxs-lookup"><span data-stu-id="1584c-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1584c-121">고 대 Eid</span><span class="sxs-lookup"><span data-stu-id="1584c-121">valueID</span></span>  <br/> |<span data-ttu-id="1584c-122">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1584c-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1584c-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="1584c-123">attributeID</span></span>  <br/> |<span data-ttu-id="1584c-124">TblEnumAttribute의 조회가 포함 되어 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="1584c-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="1584c-125">**테이블 값**</span><span class="sxs-lookup"><span data-stu-id="1584c-125">**Table Values**</span></span>

|<span data-ttu-id="1584c-126">**고 대 Eid**</span><span class="sxs-lookup"><span data-stu-id="1584c-126">**valueID**</span></span>|<span data-ttu-id="1584c-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="1584c-127">**attributeID**</span></span>|<span data-ttu-id="1584c-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="1584c-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1584c-129">2</span><span class="sxs-lookup"><span data-stu-id="1584c-129">2</span></span>  <br/> |<span data-ttu-id="1584c-130">1</span><span class="sxs-lookup"><span data-stu-id="1584c-130">1</span></span>  <br/> |<span data-ttu-id="1584c-131">개인용</span><span class="sxs-lookup"><span data-stu-id="1584c-131">private</span></span>  <br/> |
|<span data-ttu-id="1584c-132">3</span><span class="sxs-lookup"><span data-stu-id="1584c-132">3</span></span>  <br/> |<span data-ttu-id="1584c-133">1</span><span class="sxs-lookup"><span data-stu-id="1584c-133">1</span></span>  <br/> |<span data-ttu-id="1584c-134">범위도</span><span class="sxs-lookup"><span data-stu-id="1584c-134">scope</span></span>  <br/> |
|<span data-ttu-id="1584c-135">4(tcp/ipv4)</span><span class="sxs-lookup"><span data-stu-id="1584c-135">4</span></span>  <br/> |<span data-ttu-id="1584c-136">2</span><span class="sxs-lookup"><span data-stu-id="1584c-136">2</span></span>  <br/> |<span data-ttu-id="1584c-137">크기로</span><span class="sxs-lookup"><span data-stu-id="1584c-137">normal</span></span>  <br/> |
|<span data-ttu-id="1584c-138">5mb</span><span class="sxs-lookup"><span data-stu-id="1584c-138">5</span></span>  <br/> |<span data-ttu-id="1584c-139">2</span><span class="sxs-lookup"><span data-stu-id="1584c-139">2</span></span>  <br/> |<span data-ttu-id="1584c-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="1584c-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="1584c-141">26</span><span class="sxs-lookup"><span data-stu-id="1584c-141">6</span></span>  <br/> |<span data-ttu-id="1584c-142">1</span><span class="sxs-lookup"><span data-stu-id="1584c-142">1</span></span>  <br/> |<span data-ttu-id="1584c-143">열면</span><span class="sxs-lookup"><span data-stu-id="1584c-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="1584c-144">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1584c-144">See also</span></span>

[<span data-ttu-id="1584c-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="1584c-145">tblNode</span></span>](tblnode.md)
