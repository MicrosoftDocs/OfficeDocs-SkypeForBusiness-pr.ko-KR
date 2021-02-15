---
title: 상위 항목 가져오기
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: '요약: 항목 서비스의 일부인 항목 Ancestors 항목 확인 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832578"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="ead9a-105">상위 항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="ead9a-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="ead9a-106">**요약:** 항목 서비스의 일부인 항목 Ancestors 항목 확인 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="ead9a-107">항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ead9a-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ead9a-109">항목 조상 보기 작업은 호출 품질 대시보드에 대한 리포지토리 API의 항목 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="ead9a-110">상위 항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="ead9a-110">Get Item Ancestors</span></span>

<span data-ttu-id="ead9a-111">항목 조상을 지정하면 리포지토리에서 특정 항목 조상을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="ead9a-112">**방법**</span><span class="sxs-lookup"><span data-stu-id="ead9a-112">**Method**</span></span>|<span data-ttu-id="ead9a-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="ead9a-113">**Request URI**</span></span>|<span data-ttu-id="ead9a-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="ead9a-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ead9a-115">GET</span><span class="sxs-lookup"><span data-stu-id="ead9a-115">GET</span></span>  <br/> |<span data-ttu-id="ead9a-116">https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="ead9a-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="ead9a-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="ead9a-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="ead9a-118">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="ead9a-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="ead9a-119">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ead9a-120">**요청 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="ead9a-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="ead9a-121">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="ead9a-122">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="ead9a-123">지정한 사용자 ID를 찾을 수 없는 경우 상태 코드 404(찾을 수 없습니다)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="ead9a-124">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="ead9a-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="ead9a-125">**응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="ead9a-126">*Item1*  - 항목의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="ead9a-127">*Item2*  - 깊이는 항목과의 거리입니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="ead9a-128">0은 직계 부모입니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="ead9a-129">*Item3*  - 항목의 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="ead9a-129">*Item3*  - Title of the item.</span></span>
  

