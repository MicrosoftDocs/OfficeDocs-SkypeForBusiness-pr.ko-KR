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
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites는 자동 초대를 사용 하는 모든 노드에 대해 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.
ms.openlocfilehash: 21344cfc34ce046a1dffdf7cd3ee9557da20a7ef
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196615"
---
# <a name="tblprincipalinvites"></a><span data-ttu-id="c9600-103">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c9600-103">tblPrincipalInvites</span></span>
 
<span data-ttu-id="c9600-104">tblPrincipalInvites는 자동 초대를 사용 하는 모든 노드에 대해 프로 비전 된 모든 사용자에 대 한 초대를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9600-104">tblPrincipalInvites contains invitations for all provisioned users for all nodes with auto-invite on.</span></span>
  
<span data-ttu-id="c9600-105">**열**</span><span class="sxs-lookup"><span data-stu-id="c9600-105">**Columns**</span></span>

|<span data-ttu-id="c9600-106">**열**</span><span class="sxs-lookup"><span data-stu-id="c9600-106">**Column**</span></span>|<span data-ttu-id="c9600-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="c9600-107">**Type**</span></span>|<span data-ttu-id="c9600-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="c9600-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9600-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c9600-109">prinID</span></span>  <br/> |<span data-ttu-id="c9600-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="c9600-110">int, not null</span></span>  <br/> |<span data-ttu-id="c9600-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="c9600-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c9600-112">invID</span><span class="sxs-lookup"><span data-stu-id="c9600-112">invID</span></span>  <br/> |<span data-ttu-id="c9600-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="c9600-113">int, not null</span></span>  <br/> |<span data-ttu-id="c9600-114">TblLastInviteId 테이블에서 생성 된 고유 순차 번호 (주체 ID 당)입니다.</span><span class="sxs-lookup"><span data-stu-id="c9600-114">Unique sequential number (per principal ID) generated from tblLastInviteId table.</span></span>  <br/> |
|<span data-ttu-id="c9600-115">nodeID</span><span class="sxs-lookup"><span data-stu-id="c9600-115">nodeID</span></span>  <br/> |<span data-ttu-id="c9600-116">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="c9600-116">int, not null</span></span>  <br/> |<span data-ttu-id="c9600-117">노드 ID (대화방에만 해당).</span><span class="sxs-lookup"><span data-stu-id="c9600-117">Node ID (chat room only).</span></span>  <br/> |
|<span data-ttu-id="c9600-118">createdOn</span><span class="sxs-lookup"><span data-stu-id="c9600-118">createdOn</span></span>  <br/> |<span data-ttu-id="c9600-119">datetime, null 아님</span><span class="sxs-lookup"><span data-stu-id="c9600-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="c9600-120">생성 시간.</span><span class="sxs-lookup"><span data-stu-id="c9600-120">Time of creation.</span></span>  <br/> |
   
<span data-ttu-id="c9600-121">**핵심**</span><span class="sxs-lookup"><span data-stu-id="c9600-121">**Keys**</span></span>

|<span data-ttu-id="c9600-122">**열**</span><span class="sxs-lookup"><span data-stu-id="c9600-122">**Column**</span></span>|<span data-ttu-id="c9600-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="c9600-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9600-124">\<prinID, nodeID\></span><span class="sxs-lookup"><span data-stu-id="c9600-124">\<prinID, nodeID\></span></span>  <br/> |<span data-ttu-id="c9600-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c9600-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c9600-126">prinID</span><span class="sxs-lookup"><span data-stu-id="c9600-126">prinID</span></span>  <br/> |<span data-ttu-id="c9600-127">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c9600-127">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="c9600-128">nodeID</span><span class="sxs-lookup"><span data-stu-id="c9600-128">nodeID</span></span>  <br/> |<span data-ttu-id="c9600-129">NodeID 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c9600-129">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   

