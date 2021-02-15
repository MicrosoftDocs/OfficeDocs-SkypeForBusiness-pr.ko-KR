---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 계정이 포함되어 있습니다.
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831548"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="14980-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="14980-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="14980-104">tblPrincipalMeta에는 Active Directory 도메인 서비스에서 새로 고쳐야 하는 계정이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14980-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="14980-105">**열**</span><span class="sxs-lookup"><span data-stu-id="14980-105">**Columns**</span></span>

|<span data-ttu-id="14980-106">**열**</span><span class="sxs-lookup"><span data-stu-id="14980-106">**Column**</span></span>|<span data-ttu-id="14980-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="14980-107">**Type**</span></span>|<span data-ttu-id="14980-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="14980-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="14980-109">prinID</span><span class="sxs-lookup"><span data-stu-id="14980-109">prinID</span></span>  <br/> |<span data-ttu-id="14980-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="14980-110">int, not null</span></span>  <br/> |<span data-ttu-id="14980-111">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="14980-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="14980-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="14980-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="14980-113">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="14980-113">bit, not null</span></span>  <br/> |<span data-ttu-id="14980-114">사용자 회원 정보를 새로 고쳐야 하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="14980-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="14980-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="14980-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="14980-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="14980-116">bit, not null</span></span>  <br/> |<span data-ttu-id="14980-117">사용자 특성을 새로 고쳐야 하는 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="14980-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="14980-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="14980-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="14980-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="14980-119">bit, not null</span></span>  <br/> |<span data-ttu-id="14980-120">사용자가 삭제된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="14980-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="14980-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="14980-121">tryCount</span></span>  <br/> |<span data-ttu-id="14980-122">int</span><span class="sxs-lookup"><span data-stu-id="14980-122">int</span></span>  <br/> |<span data-ttu-id="14980-123">지금까지 AD DS에서 사용자를 새로 고치려는 시도가 발생한 횟수입니다.</span><span class="sxs-lookup"><span data-stu-id="14980-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="14980-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="14980-124">lastTry</span></span>  <br/> |<span data-ttu-id="14980-125">datetime</span><span class="sxs-lookup"><span data-stu-id="14980-125">datetime</span></span>  <br/> |<span data-ttu-id="14980-p101">사용자를 새로 고치려는 가장 최근 시도의 타임스탬프입니다. 새로 고침이 아직 시도되지 않은 경우 Null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14980-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="14980-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="14980-128">nextTry</span></span>  <br/> |<span data-ttu-id="14980-129">datetime</span><span class="sxs-lookup"><span data-stu-id="14980-129">datetime</span></span>  <br/> |<span data-ttu-id="14980-p102">다음 예약된 새로 고침의 타임스탬프입니다. 이후 새로 고침이 예약되지 않은 경우 Null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="14980-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="14980-132">**키**</span><span class="sxs-lookup"><span data-stu-id="14980-132">**Keys**</span></span>

|<span data-ttu-id="14980-133">**열**</span><span class="sxs-lookup"><span data-stu-id="14980-133">**Column**</span></span>|<span data-ttu-id="14980-134">**설명**</span><span class="sxs-lookup"><span data-stu-id="14980-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="14980-135">prinID</span><span class="sxs-lookup"><span data-stu-id="14980-135">prinID</span></span>  <br/> |<span data-ttu-id="14980-136">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="14980-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="14980-137">prinID</span><span class="sxs-lookup"><span data-stu-id="14980-137">prinID</span></span>  <br/> |<span data-ttu-id="14980-138">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="14980-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

