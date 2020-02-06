---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal에는 노드에 할당 된 범위가 포함 됩니다.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812446"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="6fa79-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="6fa79-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="6fa79-104">tblScopePrincipal에는 노드에 할당 된 범위가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fa79-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="6fa79-105">**열**</span><span class="sxs-lookup"><span data-stu-id="6fa79-105">**Columns**</span></span>

|<span data-ttu-id="6fa79-106">**열**</span><span class="sxs-lookup"><span data-stu-id="6fa79-106">**Column**</span></span>|<span data-ttu-id="6fa79-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="6fa79-107">**Type**</span></span>|<span data-ttu-id="6fa79-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="6fa79-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6fa79-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="6fa79-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="6fa79-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="6fa79-110">int, not null</span></span>  <br/> |<span data-ttu-id="6fa79-111">범위가 적용 되는 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa79-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="6fa79-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="6fa79-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="6fa79-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="6fa79-113">int, not null</span></span>  <br/> |<span data-ttu-id="6fa79-114">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="6fa79-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="6fa79-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="6fa79-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="6fa79-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="6fa79-116">bit, not null</span></span>  <br/> |<span data-ttu-id="6fa79-117">범위 형식이 Deny 이면 True이 고, 그렇지 않으면 false입니다. 허용 하는 경우 False</span><span class="sxs-lookup"><span data-stu-id="6fa79-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="6fa79-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="6fa79-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="6fa79-119">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="6fa79-119">int, not null</span></span>  <br/> |<span data-ttu-id="6fa79-120">이 항목을 마지막으로 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa79-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="6fa79-121">**핵심**</span><span class="sxs-lookup"><span data-stu-id="6fa79-121">**Keys**</span></span>

|<span data-ttu-id="6fa79-122">**열**</span><span class="sxs-lookup"><span data-stu-id="6fa79-122">**Column**</span></span>|<span data-ttu-id="6fa79-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="6fa79-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6fa79-124">\<scopeNodeID, scopePrinID\></span><span class="sxs-lookup"><span data-stu-id="6fa79-124">\<scopeNodeID, scopePrinID\></span></span>  <br/> |<span data-ttu-id="6fa79-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa79-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6fa79-126">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="6fa79-126">scopeNodeID</span></span>  <br/> |<span data-ttu-id="6fa79-127">NodeID 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa79-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="6fa79-128">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="6fa79-128">scopePrinID</span></span>  <br/> |<span data-ttu-id="6fa79-129">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="6fa79-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

