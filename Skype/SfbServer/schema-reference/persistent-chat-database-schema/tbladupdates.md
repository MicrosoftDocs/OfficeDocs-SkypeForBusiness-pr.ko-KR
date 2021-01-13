---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리되지 않은 Active Directory 도메인 서비스 변경 내용이 포함되어 있습니다.
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821388"
---
# <a name="tbladupdates"></a><span data-ttu-id="7a2fb-103">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="7a2fb-103">tblADUpdates</span></span>
 
<span data-ttu-id="7a2fb-104">tblADUpdates에는 이후 Active Directory 동기화 단계에서 아직 처리되지 않은 Active Directory 도메인 서비스 변경 내용이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2fb-104">tblADUpdates contains Active Directory Domain Services changes that have not yet been processed by the later Active Directory Sync steps.</span></span>
  
<span data-ttu-id="7a2fb-105">**열**</span><span class="sxs-lookup"><span data-stu-id="7a2fb-105">**Columns**</span></span>

|<span data-ttu-id="7a2fb-106">**열**</span><span class="sxs-lookup"><span data-stu-id="7a2fb-106">**Column**</span></span>|<span data-ttu-id="7a2fb-107">**유형**</span><span class="sxs-lookup"><span data-stu-id="7a2fb-107">**Type**</span></span>|<span data-ttu-id="7a2fb-108">**설명**</span><span class="sxs-lookup"><span data-stu-id="7a2fb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a2fb-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="7a2fb-109">prinGuid</span></span>  <br/> |<span data-ttu-id="7a2fb-110">GUID, null이 아님</span><span class="sxs-lookup"><span data-stu-id="7a2fb-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="7a2fb-111">변경된 개체의 사용자 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2fb-111">Principal GUID of the object that changed.</span></span>  <br/> |
|<span data-ttu-id="7a2fb-112">prinADPath</span><span class="sxs-lookup"><span data-stu-id="7a2fb-112">prinADPath</span></span>  <br/> |<span data-ttu-id="7a2fb-113">nvarchar(384), null이 아님</span><span class="sxs-lookup"><span data-stu-id="7a2fb-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="7a2fb-114">개체의 고유 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2fb-114">Distinguished name of the object.</span></span>  <br/> |
|<span data-ttu-id="7a2fb-115">prinAttributesChanged</span><span class="sxs-lookup"><span data-stu-id="7a2fb-115">prinAttributesChanged</span></span>  <br/> |<span data-ttu-id="7a2fb-116">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="7a2fb-116">bit, not null</span></span>  <br/> |<span data-ttu-id="7a2fb-117">개체의 특성이 하나 이상 변경된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2fb-117">True if at least one attribute of the object changed.</span></span>  <br/> |
|<span data-ttu-id="7a2fb-118">prinMembersChanged</span><span class="sxs-lookup"><span data-stu-id="7a2fb-118">prinMembersChanged</span></span>  <br/> |<span data-ttu-id="7a2fb-119">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="7a2fb-119">bit, not null</span></span>  <br/> |<span data-ttu-id="7a2fb-120">구성원 자격이 변경된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2fb-120">True if the membership changed.</span></span>  <br/> |
|<span data-ttu-id="7a2fb-121">prinAffiliationsChanged</span><span class="sxs-lookup"><span data-stu-id="7a2fb-121">prinAffiliationsChanged</span></span>  <br/> |<span data-ttu-id="7a2fb-122">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="7a2fb-122">bit, not null</span></span>  <br/> |<span data-ttu-id="7a2fb-123">사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2fb-123">Not used.</span></span>  <br/> |
|<span data-ttu-id="7a2fb-124">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="7a2fb-124">prinDeleted</span></span>  <br/> |<span data-ttu-id="7a2fb-125">bit, null이 아님</span><span class="sxs-lookup"><span data-stu-id="7a2fb-125">bit, not null</span></span>  <br/> |<span data-ttu-id="7a2fb-126">개체가 삭제된 경우 True입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2fb-126">True if the object was deleted.</span></span>  <br/> |
|<span data-ttu-id="7a2fb-127">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="7a2fb-127">lastUpdated</span></span>  <br/> |<span data-ttu-id="7a2fb-128">datetime, null이 아님</span><span class="sxs-lookup"><span data-stu-id="7a2fb-128">datetime, not null</span></span>  <br/> |<span data-ttu-id="7a2fb-129">행이 삽입되었을 때의 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="7a2fb-129">Time stamp of when the row was inserted.</span></span>  <br/> |
   

