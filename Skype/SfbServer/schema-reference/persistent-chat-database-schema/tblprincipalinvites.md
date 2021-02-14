---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites에는 자동 초대가 켜진 모든 노드에 대해 프로비전된 모든 사용자에 대한 초대가 포함됩니다.
ms.openlocfilehash: 5bbccd582442001bd2122dcbacdbe3634fcfd649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815858"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="0e980-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="0e980-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="0e980-104">tblPrincipalInvites에는 자동 초대가 켜진 모든 노드에 대해 프로비전된 모든 사용자에 대한 초대가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e980-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="0e980-105">**열**</span><span class="sxs-lookup"><span data-stu-id="0e980-105">**Columns**</span></span>

|<span data-ttu-id="0e980-106">**열**</span><span class="sxs-lookup"><span data-stu-id="0e980-106">**Column**</span></span>|<span data-ttu-id="0e980-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="0e980-107">**Type**</span></span>|<span data-ttu-id="0e980-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="0e980-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e980-109">prinID</span><span class="sxs-lookup"><span data-stu-id="0e980-109">prinID</span></span>  <br/> |<span data-ttu-id="0e980-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0e980-110">int, not null</span></span>  <br/> |<span data-ttu-id="0e980-111">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0e980-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="0e980-112">invID</span><span class="sxs-lookup"><span data-stu-id="0e980-112">invID</span></span>  <br/> |<span data-ttu-id="0e980-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0e980-113">int, not null</span></span>  <br/> |<span data-ttu-id="0e980-114">tblLastInviteId 테이블에서 생성된 고유한 일련 번호(계정 ID당 하나)입니다.</span><span class="sxs-lookup"><span data-stu-id="0e980-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="0e980-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="0e980-115">nodeID</span></span>  <br/> |<span data-ttu-id="0e980-116">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0e980-116">int, not null</span></span>  <br/> |<span data-ttu-id="0e980-117">노드 ID(대화방 전용)입니다.</span><span class="sxs-lookup"><span data-stu-id="0e980-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="0e980-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="0e980-118">createdOn</span></span>  <br/> |<span data-ttu-id="0e980-119">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="0e980-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="0e980-120">만든 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="0e980-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="0e980-121">**키**</span><span class="sxs-lookup"><span data-stu-id="0e980-121">**Keys**</span></span>

|<span data-ttu-id="0e980-122">**열**</span><span class="sxs-lookup"><span data-stu-id="0e980-122">**Column**</span></span>|<span data-ttu-id="0e980-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="0e980-123">**Description**</span></span>|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |<span data-ttu-id="0e980-124">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0e980-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0e980-125">prinID</span><span class="sxs-lookup"><span data-stu-id="0e980-125">prinID</span></span>  <br/> |<span data-ttu-id="0e980-126">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0e980-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="0e980-127">nodeID</span><span class="sxs-lookup"><span data-stu-id="0e980-127">nodeID</span></span>  <br/> |<span data-ttu-id="0e980-128">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="0e980-128">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

