---
title: User 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: User 테이블은 데이터베이스에 기록된 세션에 참가한 다양한 사용자 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 한 사용자를 나타내는 것입니다.
ms.openlocfilehash: 5c84f0b947199fa497964cb1689dccc571a98d14
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800078"
---
# <a name="user-table"></a><span data-ttu-id="96a0c-104">User 테이블</span><span class="sxs-lookup"><span data-stu-id="96a0c-104">User table</span></span>
 
<span data-ttu-id="96a0c-105">User 테이블은 데이터베이스에 기록된 세션에 참가한 다양한 사용자 목록을 저장하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="96a0c-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="96a0c-106">테이블의 각 레코드는 한 사용자를 나타내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="96a0c-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="96a0c-107">**열**</span><span class="sxs-lookup"><span data-stu-id="96a0c-107">**Column**</span></span>|<span data-ttu-id="96a0c-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="96a0c-108">**Data Type**</span></span>|<span data-ttu-id="96a0c-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="96a0c-109">**Key/Index**</span></span>|<span data-ttu-id="96a0c-110">**세부 정보**</span><span class="sxs-lookup"><span data-stu-id="96a0c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="96a0c-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="96a0c-111">**UserKey**</span></span> <br/> |<span data-ttu-id="96a0c-112">int</span><span class="sxs-lookup"><span data-stu-id="96a0c-112">int</span></span>  <br/> |<span data-ttu-id="96a0c-113">Primary</span><span class="sxs-lookup"><span data-stu-id="96a0c-113">Primary</span></span>  <br/> |<span data-ttu-id="96a0c-114">이 사용자를 식별하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="96a0c-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="96a0c-115">**URI**</span><span class="sxs-lookup"><span data-stu-id="96a0c-115">**URI**</span></span> <br/> |<span data-ttu-id="96a0c-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="96a0c-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="96a0c-117">고유</span><span class="sxs-lookup"><span data-stu-id="96a0c-117">Unique</span></span>  <br/> |<span data-ttu-id="96a0c-118">URI 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="96a0c-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="96a0c-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="96a0c-119">**URIType**</span></span> <br/> |<span data-ttu-id="96a0c-120">int</span><span class="sxs-lookup"><span data-stu-id="96a0c-120">int</span></span>  <br/> ||<span data-ttu-id="96a0c-121">1은 알 수 없는 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="96a0c-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="96a0c-122">2는 사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="96a0c-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="96a0c-123">4는 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="96a0c-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="96a0c-124">8은 전화 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="96a0c-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="96a0c-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="96a0c-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="96a0c-126">int</span><span class="sxs-lookup"><span data-stu-id="96a0c-126">int</span></span>  <br/> |<span data-ttu-id="96a0c-127">외계인</span><span class="sxs-lookup"><span data-stu-id="96a0c-127">Foreign</span></span>  <br/> |<span data-ttu-id="96a0c-128">테넌트 테이블에서 참조되는 사용자의 테넌트입니다.</span><span class="sxs-lookup"><span data-stu-id="96a0c-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="96a0c-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="96a0c-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="96a0c-130">datetime</span><span class="sxs-lookup"><span data-stu-id="96a0c-130">datetime</span></span>  <br/> ||<span data-ttu-id="96a0c-131">사용자가 음성 통화가 불량한 경우의 최신 타임스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="96a0c-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="96a0c-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="96a0c-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="96a0c-133">datetime</span><span class="sxs-lookup"><span data-stu-id="96a0c-133">datetime</span></span>  <br/> ||<span data-ttu-id="96a0c-134">내부 용도로만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96a0c-134">For internal use only.</span></span>  <br/> |
   

