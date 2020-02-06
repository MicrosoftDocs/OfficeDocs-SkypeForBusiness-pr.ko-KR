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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId에는 각 사용자에 대해 생성 된 마지막 초대 ID (및 tblPrincipalInvites 테이블에 사용 됨)가 포함 되어 있습니다.
ms.openlocfilehash: 17d1b725da034f79f8efc9ff9071c36430efde7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814576"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="56e9a-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="56e9a-103">tblLastInviteId</span></span>
 
<span data-ttu-id="56e9a-104">tblLastInviteId에는 각 사용자에 대해 생성 된 마지막 초대 ID (및 tblPrincipalInvites 테이블에 사용 됨)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="56e9a-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="56e9a-105">**열**</span><span class="sxs-lookup"><span data-stu-id="56e9a-105">**Columns**</span></span>

|<span data-ttu-id="56e9a-106">**열**</span><span class="sxs-lookup"><span data-stu-id="56e9a-106">**Column**</span></span>|<span data-ttu-id="56e9a-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="56e9a-107">**Type**</span></span>|<span data-ttu-id="56e9a-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="56e9a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="56e9a-109">prinID</span><span class="sxs-lookup"><span data-stu-id="56e9a-109">prinID</span></span>  <br/> |<span data-ttu-id="56e9a-110">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="56e9a-110">int, not null</span></span>  <br/> |<span data-ttu-id="56e9a-111">Principal ID.</span><span class="sxs-lookup"><span data-stu-id="56e9a-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="56e9a-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="56e9a-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="56e9a-113">int, null 아님</span><span class="sxs-lookup"><span data-stu-id="56e9a-113">int, not null</span></span>  <br/> |<span data-ttu-id="56e9a-114">마지막으로 사용한 초대 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="56e9a-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="56e9a-115">**핵심**</span><span class="sxs-lookup"><span data-stu-id="56e9a-115">**Keys**</span></span>

|<span data-ttu-id="56e9a-116">**열**</span><span class="sxs-lookup"><span data-stu-id="56e9a-116">**Column**</span></span>|<span data-ttu-id="56e9a-117">**설명**</span><span class="sxs-lookup"><span data-stu-id="56e9a-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56e9a-118">prinID</span><span class="sxs-lookup"><span data-stu-id="56e9a-118">prinID</span></span>  <br/> |<span data-ttu-id="56e9a-119">기본 키입니다.</span><span class="sxs-lookup"><span data-stu-id="56e9a-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="56e9a-120">prinID</span><span class="sxs-lookup"><span data-stu-id="56e9a-120">prinID</span></span>  <br/> |<span data-ttu-id="56e9a-121">TblPrincipal 테이블에 조회를 포함 하는 외래 키입니다.</span><span class="sxs-lookup"><span data-stu-id="56e9a-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="56e9a-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="56e9a-122">See also</span></span>

[<span data-ttu-id="56e9a-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="56e9a-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
