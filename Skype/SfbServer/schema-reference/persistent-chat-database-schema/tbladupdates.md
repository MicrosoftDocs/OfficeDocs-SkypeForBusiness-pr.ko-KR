---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리 하지 않은 Active Directory 도메인 서비스 변경 내용이 포함 되어 있습니다.
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814686"
---
# <a name="tbladupdates"></a><span data-ttu-id="79f21-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="79f21-103">tblADUpdates</span></span>
 
<span data-ttu-id="79f21-104">tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리 하지 않은 Active Directory 도메인 서비스 변경 내용이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79f21-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="79f21-105">**열**</span><span class="sxs-lookup"><span data-stu-id="79f21-105">**Columns**</span></span>

|<span data-ttu-id="79f21-106">**열**</span><span class="sxs-lookup"><span data-stu-id="79f21-106">**Column**</span></span>|<span data-ttu-id="79f21-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="79f21-107">**Type**</span></span>|<span data-ttu-id="79f21-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="79f21-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="79f21-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="79f21-109">prinGuid</span></span>  <br/> |<span data-ttu-id="79f21-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="79f21-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="79f21-111">변경 된 개체의 Principal GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="79f21-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="79f21-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="79f21-112">prinADPath</span></span>  <br/> |<span data-ttu-id="79f21-113">nvarchar (384), null 아님</span><span class="sxs-lookup"><span data-stu-id="79f21-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="79f21-114">개체의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="79f21-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="79f21-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="79f21-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="79f21-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="79f21-116">bit, not null</span></span>  <br/> |<span data-ttu-id="79f21-117">개체의 특성이 하나 이상 변경 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="79f21-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="79f21-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="79f21-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="79f21-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="79f21-119">bit, not null</span></span>  <br/> |<span data-ttu-id="79f21-120">구성원 자격이 변경 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="79f21-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="79f21-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="79f21-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="79f21-122">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="79f21-122">bit, not null</span></span>  <br/> |<span data-ttu-id="79f21-123">사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="79f21-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="79f21-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="79f21-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="79f21-125">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="79f21-125">bit, not null</span></span>  <br/> |<span data-ttu-id="79f21-126">개체가 삭제 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="79f21-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="79f21-127">lastUpdated 됨</span><span class="sxs-lookup"><span data-stu-id="79f21-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="79f21-128">datetime, null 아님</span><span class="sxs-lookup"><span data-stu-id="79f21-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="79f21-129">행이 삽입 된 시간의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="79f21-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

