---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute는 노드 테이블에 사용 되는 Visibility 및 Behavior 특성을 포함 하는 하드 코드 된 테이블입니다.
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196631"
---
# <a name="tblenumattribute"></a><span data-ttu-id="b88b7-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="b88b7-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="b88b7-104">tblEnumAttribute는 노드 테이블에 사용 되는 Visibility 및 Behavior 특성을 포함 하는 하드 코드 된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="b88b7-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="b88b7-105">**열**</span><span class="sxs-lookup"><span data-stu-id="b88b7-105">**Columns**</span></span>

|<span data-ttu-id="b88b7-106">**열**</span><span class="sxs-lookup"><span data-stu-id="b88b7-106">**Column**</span></span>|<span data-ttu-id="b88b7-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="b88b7-107">**Type**</span></span>|<span data-ttu-id="b88b7-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="b88b7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b88b7-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="b88b7-109">attributeID</span></span>  <br/> |<span data-ttu-id="b88b7-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="b88b7-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b88b7-111">특성의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b88b7-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="b88b7-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="b88b7-112">attributeName</span></span>  <br/> |<span data-ttu-id="b88b7-113">nvarchar (256), null 아님</span><span class="sxs-lookup"><span data-stu-id="b88b7-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b88b7-114">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b88b7-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="b88b7-115">**키**</span><span class="sxs-lookup"><span data-stu-id="b88b7-115">**Key**</span></span>

|<span data-ttu-id="b88b7-116">**열**</span><span class="sxs-lookup"><span data-stu-id="b88b7-116">**Column**</span></span>|<span data-ttu-id="b88b7-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="b88b7-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b88b7-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="b88b7-118">attributeID</span></span>  <br/> |<span data-ttu-id="b88b7-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b88b7-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="b88b7-120">**테이블 값**</span><span class="sxs-lookup"><span data-stu-id="b88b7-120">**Table Values**</span></span>

|<span data-ttu-id="b88b7-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="b88b7-121">**attributeID**</span></span>|<span data-ttu-id="b88b7-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="b88b7-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b88b7-123">raid-1</span><span class="sxs-lookup"><span data-stu-id="b88b7-123">1</span></span>  <br/> |<span data-ttu-id="b88b7-124">시도가.</span><span class="sxs-lookup"><span data-stu-id="b88b7-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="b88b7-125">2</span><span class="sxs-lookup"><span data-stu-id="b88b7-125">2</span></span>  <br/> |<span data-ttu-id="b88b7-126">결과가.</span><span class="sxs-lookup"><span data-stu-id="b88b7-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b88b7-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b88b7-127">See also</span></span>

[<span data-ttu-id="b88b7-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="b88b7-128">tblNode</span></span>](tblnode.md)
