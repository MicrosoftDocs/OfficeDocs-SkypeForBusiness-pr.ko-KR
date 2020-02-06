---
title: 항목 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: '요약: 항목 서비스의 일부인 항목 가져오기 작업에 대해 알아보세요. 항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 295276e6f3b0f577dae9a43c4c0f62e23b8582f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816797"
---
# <a name="get-item"></a><span data-ttu-id="7ec79-105">항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="7ec79-105">Get Item</span></span>
 
<span data-ttu-id="7ec79-106">**요약:** 항목 서비스의 일부인 항목 가져오기 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="7ec79-107">항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7ec79-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7ec79-109">항목 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 항목 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="7ec79-110">항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="7ec79-110">Get Item</span></span>

<span data-ttu-id="7ec79-111">항목 가져오기 리포지토리의 특정 항목을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="7ec79-112">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="7ec79-112">**Method**</span></span>|<span data-ttu-id="7ec79-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="7ec79-113">**Request URI**</span></span>|<span data-ttu-id="7ec79-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="7ec79-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ec79-115">가져오기</span><span class="sxs-lookup"><span data-stu-id="7ec79-115">GET</span></span>  <br/> |<span data-ttu-id="7ec79-116">https://\<포털\>/QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="7ec79-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="7ec79-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7ec79-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7ec79-118">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="7ec79-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7ec79-119">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7ec79-120">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="7ec79-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7ec79-121">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7ec79-122">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="7ec79-123">지정 된 항목 ID를 찾을 수 없는 경우 상태 코드 404 (찾을 수 없음)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="7ec79-124">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7ec79-125">**응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="7ec79-126">*itemId* -항목의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="7ec79-127">*userId* -이 항목을 소유 하는 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="7ec79-128">*콘텐츠* -응용 프로그램 관련 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="7ec79-129">*type* -콘텐츠의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-129">*type*  - The type of the content.</span></span> <span data-ttu-id="7ec79-130">이 필드는 응용 프로그램에 의해 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="7ec79-131">*subItemIds* -하위 항목의 id입니다 (있는 경우).</span><span class="sxs-lookup"><span data-stu-id="7ec79-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="7ec79-132">이는 통화를 저장 하는 하위 항목 가져오기 작업의 짧은 회로입니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="7ec79-133">또한 응용 프로그램은 하위 항목 가져오기 작업을 사용 하 여 동일한 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ec79-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

