---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: tblPrincipalRole 테이블에는 노드에 할당된 명시적 역할이 포함됩니다.
ms.openlocfilehash: 13c9c25db9ba1dbe281947468bbd834e80417899
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831558"
---
# <a name="tblprincipalrole"></a><span data-ttu-id="8ad4b-103">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="8ad4b-103">tblPrincipalRole</span></span>
 
<span data-ttu-id="8ad4b-104">tblPrincipalRole 테이블에는 노드에 할당된 명시적 역할이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ad4b-104">tblPrincipalRole contains explicit roles assigned to nodes.</span></span>
  
<span data-ttu-id="8ad4b-105">**열**</span><span class="sxs-lookup"><span data-stu-id="8ad4b-105">**Columns**</span></span>

|<span data-ttu-id="8ad4b-106">**열**</span><span class="sxs-lookup"><span data-stu-id="8ad4b-106">**Column**</span></span>|<span data-ttu-id="8ad4b-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="8ad4b-107">**Type**</span></span>|<span data-ttu-id="8ad4b-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="8ad4b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8ad4b-109">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="8ad4b-109">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="8ad4b-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="8ad4b-110">int, not null</span></span>  <br/> |<span data-ttu-id="8ad4b-111">해당 역할이 적용되는 노드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad4b-111">Node ID that the role applies to.</span></span>  <br/> |
|<span data-ttu-id="8ad4b-112">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="8ad4b-112">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="8ad4b-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="8ad4b-113">int, not null</span></span>  <br/> |<span data-ttu-id="8ad4b-114">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad4b-114">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="8ad4b-115">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="8ad4b-115">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="8ad4b-116">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="8ad4b-116">int, not null</span></span>  <br/> |<span data-ttu-id="8ad4b-117">역할 유형 ID(tblRoleType)입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad4b-117">Role type ID (from tblRoleType).</span></span>  <br/> |
|<span data-ttu-id="8ad4b-118">prinRoleUpdatedBy</span><span class="sxs-lookup"><span data-stu-id="8ad4b-118">prinRoleUpdatedBy</span></span>  <br/> |<span data-ttu-id="8ad4b-119">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="8ad4b-119">int, not null</span></span>  <br/> |<span data-ttu-id="8ad4b-120">이 항목을 마지막으로 업데이트한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad4b-120">ID of the principal that last updated this entry.</span></span>  <br/> |
   
<span data-ttu-id="8ad4b-121">**키**</span><span class="sxs-lookup"><span data-stu-id="8ad4b-121">**Keys**</span></span>

|<span data-ttu-id="8ad4b-122">**열**</span><span class="sxs-lookup"><span data-stu-id="8ad4b-122">**Column**</span></span>|<span data-ttu-id="8ad4b-123">**설명**</span><span class="sxs-lookup"><span data-stu-id="8ad4b-123">**Description**</span></span>|
|:-----|:-----|
|\<prinRoleNodeID, prinRolePrinID, prinRoleTypeID\>  <br/> |<span data-ttu-id="8ad4b-124">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad4b-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8ad4b-125">prinRoleNodeID</span><span class="sxs-lookup"><span data-stu-id="8ad4b-125">prinRoleNodeID</span></span>  <br/> |<span data-ttu-id="8ad4b-126">tblNode.nodeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad4b-126">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
|<span data-ttu-id="8ad4b-127">prinRolePrinID</span><span class="sxs-lookup"><span data-stu-id="8ad4b-127">prinRolePrinID</span></span>  <br/> |<span data-ttu-id="8ad4b-128">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad4b-128">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="8ad4b-129">prinRoleTypeID</span><span class="sxs-lookup"><span data-stu-id="8ad4b-129">prinRoleTypeID</span></span>  <br/> |<span data-ttu-id="8ad4b-130">tblRoleType.rtypeID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="8ad4b-130">Foreign key with lookup in tblRoleType.rtypeID table.</span></span>  <br/> |
   

