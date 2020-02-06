---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 사용자가 포함 되어 있습니다.
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813576"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="e7bc8-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="e7bc8-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="e7bc8-104">tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 사용자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="e7bc8-105">**열**</span><span class="sxs-lookup"><span data-stu-id="e7bc8-105">**Columns**</span></span>

|<span data-ttu-id="e7bc8-106">**열**</span><span class="sxs-lookup"><span data-stu-id="e7bc8-106">**Column**</span></span>|<span data-ttu-id="e7bc8-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="e7bc8-107">**Type**</span></span>|<span data-ttu-id="e7bc8-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="e7bc8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e7bc8-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e7bc8-109">prinID</span></span>  <br/> |<span data-ttu-id="e7bc8-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="e7bc8-110">int, not null</span></span>  <br/> |<span data-ttu-id="e7bc8-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e7bc8-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="e7bc8-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="e7bc8-113">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e7bc8-113">bit, not null</span></span>  <br/> |<span data-ttu-id="e7bc8-114">Principal 소속을 새로 고쳐야 하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="e7bc8-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="e7bc8-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="e7bc8-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e7bc8-116">bit, not null</span></span>  <br/> |<span data-ttu-id="e7bc8-117">Principal 특성을 새로 고쳐야 하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="e7bc8-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="e7bc8-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="e7bc8-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e7bc8-119">bit, not null</span></span>  <br/> |<span data-ttu-id="e7bc8-120">보안 주체가 삭제 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="e7bc8-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="e7bc8-121">tryCount</span></span>  <br/> |<span data-ttu-id="e7bc8-122">int</span><span class="sxs-lookup"><span data-stu-id="e7bc8-122">int</span></span>  <br/> |<span data-ttu-id="e7bc8-123">지금까지 발생 한 AD DS에서 보안 주체의 새로 고침 시도 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="e7bc8-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="e7bc8-124">lastTry</span></span>  <br/> |<span data-ttu-id="e7bc8-125">dmtf</span><span class="sxs-lookup"><span data-stu-id="e7bc8-125">datetime</span></span>  <br/> |<span data-ttu-id="e7bc8-126">주 사용자를 새로 고치기 위한 최신 시도의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="e7bc8-127">아직 새로 고침이 시도 되지 않은 경우 null이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="e7bc8-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="e7bc8-128">nextTry</span></span>  <br/> |<span data-ttu-id="e7bc8-129">dmtf</span><span class="sxs-lookup"><span data-stu-id="e7bc8-129">datetime</span></span>  <br/> |<span data-ttu-id="e7bc8-130">예정 된 다음 새로 고침에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="e7bc8-131">추가 새로 고침이 예약 되지 않은 경우 null이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="e7bc8-132">**핵심**</span><span class="sxs-lookup"><span data-stu-id="e7bc8-132">**Keys**</span></span>

|<span data-ttu-id="e7bc8-133">**열**</span><span class="sxs-lookup"><span data-stu-id="e7bc8-133">**Column**</span></span>|<span data-ttu-id="e7bc8-134">**설명**</span><span class="sxs-lookup"><span data-stu-id="e7bc8-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e7bc8-135">prinID</span><span class="sxs-lookup"><span data-stu-id="e7bc8-135">prinID</span></span>  <br/> |<span data-ttu-id="e7bc8-136">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e7bc8-137">prinID</span><span class="sxs-lookup"><span data-stu-id="e7bc8-137">prinID</span></span>  <br/> |<span data-ttu-id="e7bc8-138">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e7bc8-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

