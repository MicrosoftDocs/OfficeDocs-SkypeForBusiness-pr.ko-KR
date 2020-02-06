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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole에는 노드에 할당 된 명시적 역할이 포함 됩니다.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813366"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="94155-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="94155-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="94155-104">tblPrincipalRole에는 노드에 할당 된 명시적 역할이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="94155-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="94155-105">**열**</span><span class="sxs-lookup"><span data-stu-id="94155-105">**Columns**</span></span>

|<span data-ttu-id="94155-106">**열**</span><span class="sxs-lookup"><span data-stu-id="94155-106">**Column**</span></span>|<span data-ttu-id="94155-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="94155-107">**Type**</span></span>|<span data-ttu-id="94155-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="94155-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="94155-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="94155-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="94155-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="94155-110">int, not null</span></span>  <br/> |<span data-ttu-id="94155-111">역할이 적용 되는 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="94155-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="94155-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="94155-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="94155-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="94155-113">int, not null</span></span>  <br/> |<span data-ttu-id="94155-114">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="94155-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="94155-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="94155-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="94155-116">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="94155-116">int, not null</span></span>  <br/> |<span data-ttu-id="94155-117">역할 유형 ID (tblRoleType)입니다.</span><span class="sxs-lookup"><span data-stu-id="94155-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="94155-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="94155-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="94155-119">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="94155-119">int, not null</span></span>  <br/> |<span data-ttu-id="94155-120">이 항목을 마지막으로 업데이트 한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="94155-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="94155-121">**핵심**</span><span class="sxs-lookup"><span data-stu-id="94155-121">**Keys**</span></span>

|<span data-ttu-id="94155-122">**열**</span><span class="sxs-lookup"><span data-stu-id="94155-122">**Column**</span></span>|<span data-ttu-id="94155-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="94155-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="94155-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span><span class="sxs-lookup"><span data-stu-id="94155-124">\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\></span></span>  <br/> |<span data-ttu-id="94155-125">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="94155-125">Primary key.</span></span>  <br/> |
|<span data-ttu-id="94155-126">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="94155-126">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="94155-127">NodeID 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="94155-127">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="94155-128">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="94155-128">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="94155-129">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="94155-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="94155-130">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="94155-130">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="94155-131">TblRoleType의 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="94155-131">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

