---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId에는 각 사용자에 대해 생성(및 tblPrincipalInvites 테이블에서 사용)된 마지막 초대 ID가 포함됩니다.
ms.openlocfilehash: 9d5ec67a4f5c3db8558c58834582d489fde00ab6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815968"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="e29fd-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="e29fd-103">tblLastInviteId</span></span>
 
<span data-ttu-id="e29fd-104">tblLastInviteId에는 각 사용자에 대해 생성(및 tblPrincipalInvites 테이블에서 사용)된 마지막 초대 ID가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e29fd-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="e29fd-105">**열**</span><span class="sxs-lookup"><span data-stu-id="e29fd-105">**Columns**</span></span>

|<span data-ttu-id="e29fd-106">**열**</span><span class="sxs-lookup"><span data-stu-id="e29fd-106">**Column**</span></span>|<span data-ttu-id="e29fd-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="e29fd-107">**Type**</span></span>|<span data-ttu-id="e29fd-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="e29fd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e29fd-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e29fd-109">prinID</span></span>  <br/> |<span data-ttu-id="e29fd-110">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e29fd-110">int, not null</span></span>  <br/> |<span data-ttu-id="e29fd-111">사용자 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e29fd-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e29fd-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="e29fd-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="e29fd-113">int, null이 아님</span><span class="sxs-lookup"><span data-stu-id="e29fd-113">int, not null</span></span>  <br/> |<span data-ttu-id="e29fd-114">마지막으로 초대 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e29fd-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="e29fd-115">**키**</span><span class="sxs-lookup"><span data-stu-id="e29fd-115">**Keys**</span></span>

|<span data-ttu-id="e29fd-116">**열**</span><span class="sxs-lookup"><span data-stu-id="e29fd-116">**Column**</span></span>|<span data-ttu-id="e29fd-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="e29fd-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e29fd-118">prinID</span><span class="sxs-lookup"><span data-stu-id="e29fd-118">prinID</span></span>  <br/> |<span data-ttu-id="e29fd-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e29fd-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e29fd-120">prinID</span><span class="sxs-lookup"><span data-stu-id="e29fd-120">prinID</span></span>  <br/> |<span data-ttu-id="e29fd-121">tblPrincipal.prinID 테이블에서 조회 기능이 있는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e29fd-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e29fd-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e29fd-122">See also</span></span>

[<span data-ttu-id="e29fd-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="e29fd-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
