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
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리 하지 않은 Active Directory 도메인 서비스 변경 내용이 포함 되어 있습니다.
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196646"
---
# <a name="tbladupdates"></a><span data-ttu-id="95a90-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="95a90-103">tblADUpdates</span></span>
 
<span data-ttu-id="95a90-104">tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리 하지 않은 Active Directory 도메인 서비스 변경 내용이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95a90-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="95a90-105">**열**</span><span class="sxs-lookup"><span data-stu-id="95a90-105">**Columns**</span></span>

|<span data-ttu-id="95a90-106">**열**</span><span class="sxs-lookup"><span data-stu-id="95a90-106">**Column**</span></span>|<span data-ttu-id="95a90-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="95a90-107">**Type**</span></span>|<span data-ttu-id="95a90-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="95a90-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="95a90-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="95a90-109">prinGuid</span></span>  <br/> |<span data-ttu-id="95a90-110">GUID (null 아님)</span><span class="sxs-lookup"><span data-stu-id="95a90-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="95a90-111">변경 된 개체의 Principal GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="95a90-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="95a90-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="95a90-112">prinADPath</span></span>  <br/> |<span data-ttu-id="95a90-113">nvarchar (384), null 아님</span><span class="sxs-lookup"><span data-stu-id="95a90-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="95a90-114">개체의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="95a90-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="95a90-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="95a90-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="95a90-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="95a90-116">bit, not null</span></span>  <br/> |<span data-ttu-id="95a90-117">개체의 특성이 하나 이상 변경 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="95a90-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="95a90-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="95a90-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="95a90-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="95a90-119">bit, not null</span></span>  <br/> |<span data-ttu-id="95a90-120">구성원 자격이 변경 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="95a90-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="95a90-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="95a90-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="95a90-122">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="95a90-122">bit, not null</span></span>  <br/> |<span data-ttu-id="95a90-123">사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="95a90-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="95a90-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="95a90-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="95a90-125">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="95a90-125">bit, not null</span></span>  <br/> |<span data-ttu-id="95a90-126">개체가 삭제 된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="95a90-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="95a90-127">lastUpdated 됨</span><span class="sxs-lookup"><span data-stu-id="95a90-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="95a90-128">datetime, null 아님</span><span class="sxs-lookup"><span data-stu-id="95a90-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="95a90-129">행이 삽입 된 시간의 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="95a90-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

