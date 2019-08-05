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
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 사용자가 포함 되어 있습니다.
ms.openlocfilehash: 9cff5b2515613ac3540d82e545862bf4fdb58b94
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196609"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="6512d-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="6512d-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="6512d-104">tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 사용자가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6512d-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="6512d-105">**열**</span><span class="sxs-lookup"><span data-stu-id="6512d-105">**Columns**</span></span>

|<span data-ttu-id="6512d-106">**열**</span><span class="sxs-lookup"><span data-stu-id="6512d-106">**Column**</span></span>|<span data-ttu-id="6512d-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="6512d-107">**Type**</span></span>|<span data-ttu-id="6512d-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="6512d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6512d-109">prinID</span><span class="sxs-lookup"><span data-stu-id="6512d-109">prinID</span></span>  <br/> |<span data-ttu-id="6512d-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="6512d-110">int, not null</span></span>  <br/> |<span data-ttu-id="6512d-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="6512d-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="6512d-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="6512d-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="6512d-113">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="6512d-113">bit, not null</span></span>  <br/> |<span data-ttu-id="6512d-114">Principal 소속을 새로 고쳐야 하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="6512d-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="6512d-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="6512d-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="6512d-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="6512d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="6512d-117">Principal 특성을 새로 고쳐야 하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="6512d-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="6512d-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="6512d-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="6512d-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="6512d-119">bit, not null</span></span>  <br/> |<span data-ttu-id="6512d-120">보안 주체가 삭제 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="6512d-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="6512d-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="6512d-121">tryCount</span></span>  <br/> |<span data-ttu-id="6512d-122">int</span><span class="sxs-lookup"><span data-stu-id="6512d-122">int</span></span>  <br/> |<span data-ttu-id="6512d-123">지금까지 발생 한 AD DS에서 보안 주체의 새로 고침 시도 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="6512d-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="6512d-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="6512d-124">lastTry</span></span>  <br/> |<span data-ttu-id="6512d-125">dmtf</span><span class="sxs-lookup"><span data-stu-id="6512d-125">datetime</span></span>  <br/> |<span data-ttu-id="6512d-126">주 사용자를 새로 고치기 위한 최신 시도의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="6512d-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="6512d-127">아직 새로 고침이 시도 되지 않은 경우 null이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6512d-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="6512d-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="6512d-128">nextTry</span></span>  <br/> |<span data-ttu-id="6512d-129">dmtf</span><span class="sxs-lookup"><span data-stu-id="6512d-129">datetime</span></span>  <br/> |<span data-ttu-id="6512d-130">예정 된 다음 새로 고침에 대 한 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="6512d-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="6512d-131">추가 새로 고침이 예약 되지 않은 경우 null이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6512d-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="6512d-132">**핵심**</span><span class="sxs-lookup"><span data-stu-id="6512d-132">**Keys**</span></span>

|<span data-ttu-id="6512d-133">**열**</span><span class="sxs-lookup"><span data-stu-id="6512d-133">**Column**</span></span>|<span data-ttu-id="6512d-134">**설명**</span><span class="sxs-lookup"><span data-stu-id="6512d-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6512d-135">prinID</span><span class="sxs-lookup"><span data-stu-id="6512d-135">prinID</span></span>  <br/> |<span data-ttu-id="6512d-136">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="6512d-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6512d-137">prinID</span><span class="sxs-lookup"><span data-stu-id="6512d-137">prinID</span></span>  <br/> |<span data-ttu-id="6512d-138">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="6512d-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

