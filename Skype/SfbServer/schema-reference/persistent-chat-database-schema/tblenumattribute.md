---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute는 Node 테이블에 사용된 Visibility 및 Behavior 특성이 들어 있는 하드코드된 테이블입니다.
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809718"
---
# <a name="tblenumattribute"></a><span data-ttu-id="fc74c-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="fc74c-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="fc74c-104">tblEnumAttribute는 Node 테이블에 사용된 Visibility 및 Behavior 특성이 들어 있는 하드코드된 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="fc74c-105">**열**</span><span class="sxs-lookup"><span data-stu-id="fc74c-105">**Columns**</span></span>

|<span data-ttu-id="fc74c-106">**열**</span><span class="sxs-lookup"><span data-stu-id="fc74c-106">**Column**</span></span>|<span data-ttu-id="fc74c-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="fc74c-107">**Type**</span></span>|<span data-ttu-id="fc74c-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="fc74c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fc74c-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="fc74c-109">attributeID</span></span>  <br/> |<span data-ttu-id="fc74c-110">smallint, null이 아님</span><span class="sxs-lookup"><span data-stu-id="fc74c-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="fc74c-111">특성의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="fc74c-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="fc74c-112">attributeName</span></span>  <br/> |<span data-ttu-id="fc74c-113">nvarchar(256), null이 아님</span><span class="sxs-lookup"><span data-stu-id="fc74c-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="fc74c-114">특성의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="fc74c-115">**키**</span><span class="sxs-lookup"><span data-stu-id="fc74c-115">**Key**</span></span>

|<span data-ttu-id="fc74c-116">**열**</span><span class="sxs-lookup"><span data-stu-id="fc74c-116">**Column**</span></span>|<span data-ttu-id="fc74c-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="fc74c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fc74c-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="fc74c-118">attributeID</span></span>  <br/> |<span data-ttu-id="fc74c-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="fc74c-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="fc74c-120">**테이블 값**</span><span class="sxs-lookup"><span data-stu-id="fc74c-120">**Table Values**</span></span>

|<span data-ttu-id="fc74c-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="fc74c-121">**attributeID**</span></span>|<span data-ttu-id="fc74c-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="fc74c-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fc74c-123">1 </span><span class="sxs-lookup"><span data-stu-id="fc74c-123">1</span></span>  <br/> |<span data-ttu-id="fc74c-124">가시성.</span><span class="sxs-lookup"><span data-stu-id="fc74c-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="fc74c-125">2 </span><span class="sxs-lookup"><span data-stu-id="fc74c-125">2</span></span>  <br/> |<span data-ttu-id="fc74c-126">동작.</span><span class="sxs-lookup"><span data-stu-id="fc74c-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fc74c-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fc74c-127">See also</span></span>

[<span data-ttu-id="fc74c-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="fc74c-128">tblNode</span></span>](tblnode.md)
