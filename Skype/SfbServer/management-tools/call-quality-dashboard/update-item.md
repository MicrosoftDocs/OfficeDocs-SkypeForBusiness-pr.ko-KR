---
title: 항목 업데이트
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: '요약: 항목 서비스의 일부인 항목 업데이트 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803088"
---
# <a name="update-item"></a><span data-ttu-id="91923-105">항목 업데이트</span><span class="sxs-lookup"><span data-stu-id="91923-105">Update Item</span></span>
 
<span data-ttu-id="91923-106">**요약:** 항목 서비스의 일부인 항목 업데이트 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="91923-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="91923-107">항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="91923-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="91923-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="91923-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="91923-109">항목 업데이트 작업은 통화 품질 대시보드에 대한 리포지토리 API의 항목 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="91923-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="91923-110">항목 업데이트</span><span class="sxs-lookup"><span data-stu-id="91923-110">Update Item</span></span>

<span data-ttu-id="91923-111">업데이트 항목은 리포지토리의 특정 항목을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="91923-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="91923-112">**방법**</span><span class="sxs-lookup"><span data-stu-id="91923-112">**Method**</span></span>|<span data-ttu-id="91923-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="91923-113">**Request URI**</span></span>|<span data-ttu-id="91923-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="91923-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="91923-115">PUT</span><span class="sxs-lookup"><span data-stu-id="91923-115">PUT</span></span>  <br/> |<span data-ttu-id="91923-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="91923-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="91923-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="91923-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="91923-118">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="91923-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="91923-119">**Request Headers** -Content-Type: application/json.</span><span class="sxs-lookup"><span data-stu-id="91923-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="91923-120">**요청 본문** - JSON.</span><span class="sxs-lookup"><span data-stu-id="91923-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="91923-121">샘플 요청 페이로드:</span><span class="sxs-lookup"><span data-stu-id="91923-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="91923-122">*콘텐츠*  기존 하위 항목의 새 콘텐츠로 저장할 JSON 서식 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="91923-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="91923-123">기술적으로 리포지토리는 모든 스마마의 콘텐츠를 저장할 수 있지만 통화 품질 대시보드에 사용할 경우 보고서 또는 쿼리가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="91923-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="91923-124">*type*  통화 품질 대시보드에 대해 항상 "application/json"을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="91923-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="91923-125">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="91923-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="91923-126">**상태 코드** - 작업이 성공하면 상태 코드 204(콘텐츠 없음)가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="91923-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="91923-127">지정한 항목 ID를 찾을 수 없는 경우 상태 코드 404(찾을 수 없습니다)를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="91923-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="91923-128">"콘텐츠 없음"은 오류 상태가 아니며,</span><span class="sxs-lookup"><span data-stu-id="91923-128">"No Content" is not an error status.</span></span> <span data-ttu-id="91923-129">즉, 응답이 본문에 아무 것도 반환하지 않았음(반대로 200 OK는 본문의 콘텐츠를 반환)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="91923-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="91923-130">항목이 성공적으로 업데이트된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="91923-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="91923-131">**응답 헤더** - 없음.</span><span class="sxs-lookup"><span data-stu-id="91923-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="91923-132">**응답 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="91923-132">**Response Body** - None.</span></span>
  

