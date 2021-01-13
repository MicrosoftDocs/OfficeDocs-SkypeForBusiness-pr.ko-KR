---
title: 하위 항목 가져오기
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '요약: 항목 Sub-Items 있는 Get Sub-Items 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832508"
---
# <a name="get-sub-items"></a><span data-ttu-id="6780e-105">하위 항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="6780e-105">Get Sub-Items</span></span>
 
<span data-ttu-id="6780e-106">**요약:** 항목 서비스의 일부인 Sub-Items Get Sub-Items 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="6780e-107">항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="6780e-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="6780e-109">Get Sub-Items 호출 품질 대시보드에 대한 리포지토리 API의 항목 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="6780e-110">하위 항목 가져오기</span><span class="sxs-lookup"><span data-stu-id="6780e-110">Get Sub-Items</span></span>

<span data-ttu-id="6780e-111">Get Sub-Items 항목의 하위 항목을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="6780e-112">**방법**</span><span class="sxs-lookup"><span data-stu-id="6780e-112">**Method**</span></span>|<span data-ttu-id="6780e-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="6780e-113">**Request URI**</span></span>|<span data-ttu-id="6780e-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="6780e-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6780e-115">GET</span><span class="sxs-lookup"><span data-stu-id="6780e-115">GET</span></span>  <br/> |<span data-ttu-id="6780e-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem</span><span class="sxs-lookup"><span data-stu-id="6780e-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="6780e-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="6780e-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="6780e-118">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="6780e-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="6780e-119">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6780e-120">**요청 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="6780e-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="6780e-121">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="6780e-122">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="6780e-123">지정한 사용자 ID를 찾을 수 없는 경우 상태 코드 404(찾을 수 없습니다)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="6780e-124">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="6780e-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="6780e-125">**응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6780e-126">Item 개체의 배열이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-126">An array of Item object is returned.</span></span> 
  
```json
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

<span data-ttu-id="6780e-127">이 작업에서 반환된 Item Sub-Items 다음 세 개의 필드만 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="6780e-128">*itemId*  - 항목의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="6780e-129">*userId*  - 이 항목을 소유한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="6780e-130">*type*  - 콘텐츠의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-130">*type*  - The type of the content.</span></span> <span data-ttu-id="6780e-131">이 필드는 응용 프로그램에 의해 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="6780e-132">`Content` 필드는 네트워크를 통해 전송되는 데이터의 양을 줄이기 위해 응답에 `subItems` 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6780e-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

