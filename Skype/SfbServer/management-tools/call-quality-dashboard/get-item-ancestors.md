---
title: 상위 항목 가져오기
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: '요약: 항목 서비스의 일부인 항목의 상위 항목 가져오기 작업에 대해 알아보세요. 항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 7beaffbb670f664ec7181482dbceb120a8b7d9e8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816807"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="33fd4-105">상위 항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="33fd4-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="33fd4-106">**요약:** 항목 서비스의 일부인 항목의 상위 항목 가져오기 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="33fd4-107">항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="33fd4-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="33fd4-109">항목 조상 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 항목 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="33fd4-110">상위 항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="33fd4-110">Get Item Ancestors</span></span>

<span data-ttu-id="33fd4-111">Item 상위 항목 가져오기 저장소에서 상위 항목을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="33fd4-112">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="33fd4-112">**Method**</span></span>|<span data-ttu-id="33fd4-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="33fd4-113">**Request URI**</span></span>|<span data-ttu-id="33fd4-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="33fd4-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="33fd4-115">가져오기</span><span class="sxs-lookup"><span data-stu-id="33fd4-115">GET</span></span>  <br/> |<span data-ttu-id="33fd4-116">https://\<포털\>/QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="33fd4-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="33fd4-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="33fd4-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="33fd4-118">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="33fd4-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="33fd4-119">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="33fd4-120">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="33fd4-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="33fd4-121">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="33fd4-122">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="33fd4-123">지정 된 사용자 ID를 찾을 수 없는 경우 상태 코드 404 (찾을 수 없음)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="33fd4-124">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="33fd4-125">**응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 <span data-ttu-id="33fd4-126">*Item1* -항목의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="33fd4-127">*Item2* -깊이는 항목 으로부터의 거리입니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="33fd4-128">0이 바로 상위입니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="33fd4-129">*Item3* -항목의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="33fd4-129">*Item3*  - Title of the item.</span></span>
  

