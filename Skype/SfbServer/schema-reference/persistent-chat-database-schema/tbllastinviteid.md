---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId에는 각 사용자에 대해 생성 된 마지막 초대 ID (및 tblPrincipalInvites 테이블에 사용 됨)가 포함 되어 있습니다.
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196625"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="e31b8-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="e31b8-103">tblLastInviteId</span></span>
 
<span data-ttu-id="e31b8-104">tblLastInviteId에는 각 사용자에 대해 생성 된 마지막 초대 ID (및 tblPrincipalInvites 테이블에 사용 됨)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e31b8-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="e31b8-105">**열**</span><span class="sxs-lookup"><span data-stu-id="e31b8-105">**Columns**</span></span>

|<span data-ttu-id="e31b8-106">**열**</span><span class="sxs-lookup"><span data-stu-id="e31b8-106">**Column**</span></span>|<span data-ttu-id="e31b8-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="e31b8-107">**Type**</span></span>|<span data-ttu-id="e31b8-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="e31b8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e31b8-109">prinID</span><span class="sxs-lookup"><span data-stu-id="e31b8-109">prinID</span></span>  <br/> |<span data-ttu-id="e31b8-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="e31b8-110">int, not null</span></span>  <br/> |<span data-ttu-id="e31b8-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="e31b8-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e31b8-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="e31b8-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="e31b8-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="e31b8-113">int, not null</span></span>  <br/> |<span data-ttu-id="e31b8-114">마지막으로 사용한 초대 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e31b8-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="e31b8-115">**핵심**</span><span class="sxs-lookup"><span data-stu-id="e31b8-115">**Keys**</span></span>

|<span data-ttu-id="e31b8-116">**열**</span><span class="sxs-lookup"><span data-stu-id="e31b8-116">**Column**</span></span>|<span data-ttu-id="e31b8-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="e31b8-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e31b8-118">prinID</span><span class="sxs-lookup"><span data-stu-id="e31b8-118">prinID</span></span>  <br/> |<span data-ttu-id="e31b8-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e31b8-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e31b8-120">prinID</span><span class="sxs-lookup"><span data-stu-id="e31b8-120">prinID</span></span>  <br/> |<span data-ttu-id="e31b8-121">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="e31b8-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e31b8-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e31b8-122">See also</span></span>

[<span data-ttu-id="e31b8-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="e31b8-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
