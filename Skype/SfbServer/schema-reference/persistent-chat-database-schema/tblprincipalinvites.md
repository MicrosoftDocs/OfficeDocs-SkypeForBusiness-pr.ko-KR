---
title: tblPrincipalInvites
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
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites는 자동 초대를 사용 하는 모든 노드에 대해 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.
ms.openlocfilehash: dfa41ec5715c7c5255b26fcdb32561e74c4f08df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814186"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="aee99-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="aee99-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="aee99-104">tblPrincipalInvites는 자동 초대를 사용 하는 모든 노드에 대해 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="aee99-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="aee99-105">**열**</span><span class="sxs-lookup"><span data-stu-id="aee99-105">**Columns**</span></span>

|<span data-ttu-id="aee99-106">**열**</span><span class="sxs-lookup"><span data-stu-id="aee99-106">**Column**</span></span>|<span data-ttu-id="aee99-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="aee99-107">**Type**</span></span>|<span data-ttu-id="aee99-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="aee99-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aee99-109">prinID</span><span class="sxs-lookup"><span data-stu-id="aee99-109">prinID</span></span>  <br/> |<span data-ttu-id="aee99-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="aee99-110">int, not null</span></span>  <br/> |<span data-ttu-id="aee99-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="aee99-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="aee99-112">invID</span><span class="sxs-lookup"><span data-stu-id="aee99-112">invID</span></span>  <br/> |<span data-ttu-id="aee99-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="aee99-113">int, not null</span></span>  <br/> |<span data-ttu-id="aee99-114">TblLastInviteId 테이블에서 생성 된 고유 순차 번호 (주체 ID 당)입니다.</span><span class="sxs-lookup"><span data-stu-id="aee99-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="aee99-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="aee99-115">nodeID</span></span>  <br/> |<span data-ttu-id="aee99-116">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="aee99-116">int, not null</span></span>  <br/> |<span data-ttu-id="aee99-117">노드 ID (대화방에만 해당).</span><span class="sxs-lookup"><span data-stu-id="aee99-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="aee99-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="aee99-118">createdOn</span></span>  <br/> |<span data-ttu-id="aee99-119">datetime, null 아님</span><span class="sxs-lookup"><span data-stu-id="aee99-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="aee99-120">생성 시간.</span><span class="sxs-lookup"><span data-stu-id="aee99-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="aee99-121">**핵심**</span><span class="sxs-lookup"><span data-stu-id="aee99-121">**Keys**</span></span>

|<span data-ttu-id="aee99-122">**열**</span><span class="sxs-lookup"><span data-stu-id="aee99-122">**Column**</span></span>|<span data-ttu-id="aee99-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="aee99-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="aee99-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="aee99-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="aee99-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="aee99-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="aee99-126">prinID</span><span class="sxs-lookup"><span data-stu-id="aee99-126">prinID</span></span>  <br/> |<span data-ttu-id="aee99-127">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="aee99-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="aee99-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="aee99-128">nodeID</span></span>  <br/> |<span data-ttu-id="aee99-129">NodeID 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="aee99-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

