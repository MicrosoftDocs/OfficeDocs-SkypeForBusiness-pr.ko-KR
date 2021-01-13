---
title: 항목 가져오기
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: '요약: 항목 서비스의 일부인 항목 항목 선택 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832568"
---
# <a name="get-item"></a><span data-ttu-id="a6c30-105">항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="a6c30-105">Get Item</span></span>
 
<span data-ttu-id="a6c30-106">**요약:** 항목 서비스의 일부인 항목 항목 선택 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="a6c30-107">항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a6c30-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a6c30-109">항목 항목 보기 작업은 호출 품질 대시보드에 대한 리포지토리 API의 항목 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="a6c30-110">항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="a6c30-110">Get Item</span></span>

<span data-ttu-id="a6c30-111">Get Item은 리포지토리의 특정 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="a6c30-112">**방법**</span><span class="sxs-lookup"><span data-stu-id="a6c30-112">**Method**</span></span>|<span data-ttu-id="a6c30-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="a6c30-113">**Request URI**</span></span>|<span data-ttu-id="a6c30-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="a6c30-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a6c30-115">GET</span><span class="sxs-lookup"><span data-stu-id="a6c30-115">GET</span></span>  <br/> |<span data-ttu-id="a6c30-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="a6c30-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="a6c30-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a6c30-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a6c30-118">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="a6c30-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a6c30-119">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a6c30-120">**요청 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="a6c30-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a6c30-121">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a6c30-122">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="a6c30-123">지정한 항목 ID를 찾을 수 없는 경우 상태 코드 404(찾을 수 없습니다)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="a6c30-124">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="a6c30-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a6c30-125">**응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="a6c30-126">*itemId*  - 항목의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="a6c30-127">*userId*  - 이 항목을 소유한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="a6c30-128">*content*  - 응용 프로그램별 콘텐츠입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="a6c30-129">*type*  - 콘텐츠의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-129">*type*  - The type of the content.</span></span> <span data-ttu-id="a6c30-130">이 필드는 응용 프로그램에 의해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="a6c30-131">*subItemIds*  - 하위 항목(있는 경우)의ID입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="a6c30-132">이는 통화를 저장하기 위한 get Sub-Items 짧은 회로입니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="a6c30-133">또는 응용 프로그램에서 Get Sub-Items 같은 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6c30-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

