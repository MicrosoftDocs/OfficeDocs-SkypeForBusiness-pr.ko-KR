---
title: tblPrincipalRole
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole에는 노드에 할당 된 명시적 역할이 포함 됩니다.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196607"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="e39ca-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="e39ca-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="e39ca-104">tblPrincipalRole에는 노드에 할당 된 명시적 역할이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e39ca-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="e39ca-105">**열**</span><span class="sxs-lookup"><span data-stu-id="e39ca-105">**Columns**</span></span>

|<span data-ttu-id="e39ca-106">**열**</span><span class="sxs-lookup"><span data-stu-id="e39ca-106">**Column**</span></span>|<span data-ttu-id="e39ca-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="e39ca-107">**Type**</span></span>|<span data-ttu-id="e39ca-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="e39ca-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e39ca-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="e39ca-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="e39ca-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="e39ca-110">int, not null</span></span>  <br/> |<span data-ttu-id="e39ca-111">역할이 적용 되는 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e39ca-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="e39ca-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="e39ca-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="e39ca-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="e39ca-113">int, not null</span></span>  <br/> |<span data-ttu-id="e39ca-114">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="e39ca-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e39ca-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="e39ca-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="e39ca-116">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="e39ca-116">int, not null</span></span>  <br/> |<span data-ttu-id="e39ca-117">역할 유형 ID (tblRoleType)입니다.</span><span class="sxs-lookup"><span data-stu-id="e39ca-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="e39ca-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="e39ca-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="e39ca-119">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="e39ca-119">int, not null</span></span>  <br/> |<span data-ttu-id="e39ca-120">이 항목을 마지막으로 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e39ca-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="e39ca-121">**핵심**</span><span class="sxs-lookup"><span data-stu-id="e39ca-121">**Keys**</span></span>

|<span data-ttu-id="e39ca-122">**열**</span><span class="sxs-lookup"><span data-stu-id="e39ca-122">**Column**</span></span>|<span data-ttu-id="e39ca-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="e39ca-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e39ca-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="e39ca-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="e39ca-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e39ca-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e39ca-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="e39ca-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="e39ca-127">NodeID 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e39ca-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="e39ca-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="e39ca-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="e39ca-129">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e39ca-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="e39ca-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="e39ca-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="e39ca-131">TblRoleType의 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e39ca-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

