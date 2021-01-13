---
title: CQD(통화 품질 대시보드)에 대한 항목 서비스
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '요약: 통화 품질 대시보드에 대한 리포지토리 API의 일부인 항목 서비스에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827708"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="21712-104">CQD(통화 품질 대시보드)에 대한 항목 서비스</span><span class="sxs-lookup"><span data-stu-id="21712-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="21712-105">**요약:** 통화 품질 대시보드에 대한 리포지토리 API의 일부인 항목 서비스에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="21712-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="21712-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="21712-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="21712-107">항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="21712-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="21712-108">항목 서비스</span><span class="sxs-lookup"><span data-stu-id="21712-108">Item Service</span></span>

<span data-ttu-id="21712-109">리포지토리 API는 사용자에 대해 응용 프로그램 정의 콘텐츠를 저장하는 데 사용할 수 있는 간단한 콘텐츠 관리 서비스(항목 서비스)를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="21712-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="21712-110">시스템 콘텐츠는 시스템 사용자가 소유하며 읽기 전용 액세스 권한이 있는 모든 사용자가 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="21712-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="21712-111">전용 사용자 콘텐츠는 일반 사용자가 소유하며 소유자만 콘텐츠를 수정하거나 삭제할 수 있지만 모든 사용자는 여전히 읽기 전용으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21712-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="21712-112">이 API 설명서에는 리포지토리 API의 읽기 전용 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="21712-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="21712-113">통화 품질 대시보드에서는 보고서 및 쿼리를 리포지토리 데이터베이스에 항목으로 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="21712-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="21712-114">항목에는 선택적 하위 항목이 있으며 통화 품질 대시보드에서는 하위 항목 기능을 사용하여 보고서 및 쿼리를 계층 구조로 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="21712-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="21712-115">항목 서비스에는 다음과 같은 개념이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21712-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="21712-116">**item** - 리포지토리의 기본 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="21712-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="21712-117">각 항목은 정확히 한 사용자가 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="21712-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="21712-118">**하위 항목** - 리포지토리의 기본 조직적 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="21712-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="21712-119">항목에는 0개, 하나 이상의 하위 항목이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21712-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="21712-120">**항목 상위** - 맨 위에 있는 항목부터 시작하여 사용자의 기본 항목으로, 지정한 항목으로 이어지는 항목 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="21712-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="21712-121">**항목 콘텐츠** - 항목에 저장된 응용 프로그램별 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="21712-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="21712-122">통화 품질 대시보드에서는 보고서 및 쿼리의 JSON 표현을 콘텐츠에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="21712-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="21712-123">REST 작업은 다음 표에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21712-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="21712-124">**작업**</span><span class="sxs-lookup"><span data-stu-id="21712-124">**Operation**</span></span>|<span data-ttu-id="21712-125">**설명**</span><span class="sxs-lookup"><span data-stu-id="21712-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="21712-126">항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="21712-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="21712-127">Get Items는 리포지토리의 모든 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="21712-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="21712-128">항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="21712-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="21712-129">Get Item은 특정 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="21712-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="21712-130">하위 항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="21712-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="21712-131">Get Sub-Items 항목의 하위 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="21712-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="21712-132">상위 항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="21712-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="21712-133">항목 조상을 구하면 특정 항목의 조상이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="21712-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="21712-134">항목 업데이트</span><span class="sxs-lookup"><span data-stu-id="21712-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="21712-135">리포지토리의 특정 항목을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="21712-135">Update a specific item in the repository.</span></span>  <br/> |
   

