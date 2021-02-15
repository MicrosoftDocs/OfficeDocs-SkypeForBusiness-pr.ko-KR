---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal에는 노드에 지정된 범위가 포함됩니다.
ms.openlocfilehash: efda792ab6f6c6cc7b188a9dffdaa7c324b24797
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831518"
---
# <a name="tblscopeprincipal"></a><span data-ttu-id="b96b4-103">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="b96b4-103">tblScopePrincipal</span></span>
 
<span data-ttu-id="b96b4-104">tblScopePrincipal에는 노드에 지정된 범위가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b96b4-104">tblScopePrincipal contains scopes assigned to nodes.</span></span>
  
<span data-ttu-id="b96b4-105">**열**</span><span class="sxs-lookup"><span data-stu-id="b96b4-105">**Columns**</span></span>

|<span data-ttu-id="b96b4-106">**열**</span><span class="sxs-lookup"><span data-stu-id="b96b4-106">**Column**</span></span>|<span data-ttu-id="b96b4-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="b96b4-107">**Type**</span></span>|<span data-ttu-id="b96b4-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="b96b4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b96b4-109">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b96b4-109">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b96b4-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="b96b4-110">int, not null</span></span>  <br/> |<span data-ttu-id="b96b4-111">해당 범위가 적용되는 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b96b4-111">Node ID that the scope applies to.</span></span>  <br/> |
|<span data-ttu-id="b96b4-112">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b96b4-112">scopePrinID</span></span>  <br/> |<span data-ttu-id="b96b4-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="b96b4-113">int, not null</span></span>  <br/> |<span data-ttu-id="b96b4-114">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b96b4-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b96b4-115">scopeIsDenied</span><span class="sxs-lookup"><span data-stu-id="b96b4-115">scopeIsDenied</span></span>  <br/> |<span data-ttu-id="b96b4-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="b96b4-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b96b4-117">범위 유형이 Deny인 경우 True이고 Allow이면 False입니다.</span><span class="sxs-lookup"><span data-stu-id="b96b4-117">True if type of scope is Deny; False if Allow.</span></span>  <br/> |
|<span data-ttu-id="b96b4-118">scopeUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="b96b4-118">scopeUpdatedBy</span></span>  <br/> |<span data-ttu-id="b96b4-119">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="b96b4-119">int, not null</span></span>  <br/> |<span data-ttu-id="b96b4-120">이 항목을 마지막으로 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="b96b4-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="b96b4-121">**키**</span><span class="sxs-lookup"><span data-stu-id="b96b4-121">**Keys**</span></span>

|<span data-ttu-id="b96b4-122">**열**</span><span class="sxs-lookup"><span data-stu-id="b96b4-122">**Column**</span></span>|<span data-ttu-id="b96b4-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="b96b4-123">**Description**</span></span>|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |<span data-ttu-id="b96b4-124">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b96b4-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b96b4-125">scopeNodeID</span><span class="sxs-lookup"><span data-stu-id="b96b4-125">scopeNodeID</span></span>  <br/> |<span data-ttu-id="b96b4-126">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b96b4-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="b96b4-127">scopePrinID</span><span class="sxs-lookup"><span data-stu-id="b96b4-127">scopePrinID</span></span>  <br/> |<span data-ttu-id="b96b4-128">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="b96b4-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

