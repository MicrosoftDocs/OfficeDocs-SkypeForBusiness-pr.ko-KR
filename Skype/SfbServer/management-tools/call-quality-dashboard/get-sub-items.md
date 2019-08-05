---
title: 하위 항목 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '요약: 항목 서비스의 일부인 하위 항목 가져오기 작업에 대해 알아봅니다. 항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 7be427ed4ea90cd46c6f8cea4ffe3a97be98479b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186912"
---
# <a name="get-sub-items"></a><span data-ttu-id="1d3be-105">하위 항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="1d3be-105">Get Sub-Items</span></span>
 
<span data-ttu-id="1d3be-106">**요약:** 항목 서비스의 일부인 하위 항목 가져오기 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="1d3be-107">항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1d3be-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1d3be-109">하위 항목 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 항목 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="1d3be-110">하위 항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="1d3be-110">Get Sub-Items</span></span>

<span data-ttu-id="1d3be-111">하위 항목 가져오기 특정 항목의 하위 항목을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="1d3be-112">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="1d3be-112">**Method**</span></span>|<span data-ttu-id="1d3be-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="1d3be-113">**Request URI**</span></span>|<span data-ttu-id="1d3be-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="1d3be-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1d3be-115">가져오기</span><span class="sxs-lookup"><span data-stu-id="1d3be-115">GET</span></span>  <br/> |<span data-ttu-id="1d3be-116">https://\<포털\>/QoERepositoryService/repository/item/{itemId}/subitem</span><span class="sxs-lookup"><span data-stu-id="1d3be-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="1d3be-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1d3be-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1d3be-118">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="1d3be-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1d3be-119">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1d3be-120">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="1d3be-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1d3be-121">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1d3be-122">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="1d3be-123">지정 된 사용자 ID를 찾을 수 없는 경우 상태 코드 404 (찾을 수 없음)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="1d3be-124">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1d3be-125">**응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1d3be-126">Item 개체의 배열이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-126">An array of Item object is returned.</span></span> 
  
```
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

<span data-ttu-id="1d3be-127">하위 항목 작업에서 반환 되는 항목 개체에는 다음 세 개의 필드만 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="1d3be-128">*itemId* -항목의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="1d3be-129">*userId* -이 항목을 소유 하는 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="1d3be-130">*type* -콘텐츠의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-130">*type*  - The type of the content.</span></span> <span data-ttu-id="1d3be-131">이 필드는 응용 프로그램에 의해 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="1d3be-132">`Content`네트워크 `subItems` 를 통해 전송 되는 데이터의 양을 줄이기 위해 응답에는 및 필드가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d3be-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

