---
title: User 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: 사용자 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 한 명의 사용자를 나타냅니다.
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196517"
---
# <a name="user-table"></a><span data-ttu-id="2e56c-104">User 테이블</span><span class="sxs-lookup"><span data-stu-id="2e56c-104">User table</span></span>
 
<span data-ttu-id="2e56c-105">사용자 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자의 목록을 저장 하는 지원 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="2e56c-105">The User table is a supporting table that stores a list of the various users who have participated in sessions recorded in the database.</span></span> <span data-ttu-id="2e56c-106">테이블의 각 레코드는 한 명의 사용자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2e56c-106">Each record in the table represents one user.</span></span>
  
|<span data-ttu-id="2e56c-107">**열**</span><span class="sxs-lookup"><span data-stu-id="2e56c-107">**Column**</span></span>|<span data-ttu-id="2e56c-108">**데이터 형식**</span><span class="sxs-lookup"><span data-stu-id="2e56c-108">**Data Type**</span></span>|<span data-ttu-id="2e56c-109">**키/인덱스**</span><span class="sxs-lookup"><span data-stu-id="2e56c-109">**Key/Index**</span></span>|<span data-ttu-id="2e56c-110">**세부적인**</span><span class="sxs-lookup"><span data-stu-id="2e56c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2e56c-111">**UserKey**</span><span class="sxs-lookup"><span data-stu-id="2e56c-111">**UserKey**</span></span> <br/> |<span data-ttu-id="2e56c-112">int</span><span class="sxs-lookup"><span data-stu-id="2e56c-112">int</span></span>  <br/> |<span data-ttu-id="2e56c-113">주요한</span><span class="sxs-lookup"><span data-stu-id="2e56c-113">Primary</span></span>  <br/> |<span data-ttu-id="2e56c-114">이 사용자를 식별 하는 고유 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="2e56c-114">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="2e56c-115">**URL**</span><span class="sxs-lookup"><span data-stu-id="2e56c-115">**URI**</span></span> <br/> |<span data-ttu-id="2e56c-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2e56c-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="2e56c-117">독특한</span><span class="sxs-lookup"><span data-stu-id="2e56c-117">Unique</span></span>  <br/> |<span data-ttu-id="2e56c-118">URI 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2e56c-118">URI string.</span></span>  <br/> |
|<span data-ttu-id="2e56c-119">**URIType**</span><span class="sxs-lookup"><span data-stu-id="2e56c-119">**URIType**</span></span> <br/> |<span data-ttu-id="2e56c-120">int</span><span class="sxs-lookup"><span data-stu-id="2e56c-120">int</span></span>  <br/> ||<span data-ttu-id="2e56c-121">1은 알 수 없는 URI 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2e56c-121">1 is unknown URI type.</span></span>  <br/> <span data-ttu-id="2e56c-122">2는 사용자 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2e56c-122">2 is user URI.</span></span>  <br/> <span data-ttu-id="2e56c-123">4는 회의 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2e56c-123">4 is conference URI.</span></span>  <br/> <span data-ttu-id="2e56c-124">8은 phone URI입니다.</span><span class="sxs-lookup"><span data-stu-id="2e56c-124">8 is phone URI.</span></span>  <br/> |
|<span data-ttu-id="2e56c-125">**TenantKey**</span><span class="sxs-lookup"><span data-stu-id="2e56c-125">**TenantKey**</span></span> <br/> |<span data-ttu-id="2e56c-126">int</span><span class="sxs-lookup"><span data-stu-id="2e56c-126">int</span></span>  <br/> |<span data-ttu-id="2e56c-127">외부</span><span class="sxs-lookup"><span data-stu-id="2e56c-127">Foreign</span></span>  <br/> |<span data-ttu-id="2e56c-128">테 넌 트 테이블에서 참조 하는 사용자의 테 넌 트입니다.</span><span class="sxs-lookup"><span data-stu-id="2e56c-128">Tenant of the user, referenced from tenant table.</span></span>  <br/> |
|<span data-ttu-id="2e56c-129">**LastPoorCallTime**</span><span class="sxs-lookup"><span data-stu-id="2e56c-129">**LastPoorCallTime**</span></span> <br/> |<span data-ttu-id="2e56c-130">dmtf</span><span class="sxs-lookup"><span data-stu-id="2e56c-130">datetime</span></span>  <br/> ||<span data-ttu-id="2e56c-131">사용자가 음성 통화에 좋지 않은 경우의 최신 타임 스탬프입니다.</span><span class="sxs-lookup"><span data-stu-id="2e56c-131">Latest time stamp when the user had a poor audio call.</span></span>  <br/> |
|<span data-ttu-id="2e56c-132">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="2e56c-132">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="2e56c-133">dmtf</span><span class="sxs-lookup"><span data-stu-id="2e56c-133">datetime</span></span>  <br/> ||<span data-ttu-id="2e56c-134">내부용 으로만 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e56c-134">For internal use only.</span></span>  <br/> |
   

