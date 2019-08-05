---
title: 항목 업데이트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: '요약: 항목 서비스의 일부인 항목 업데이트 작업에 대해 알아봅니다. 항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: aa46be0babf5998fcf2fabea797cb7a769914f8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186858"
---
# <a name="update-item"></a><span data-ttu-id="af2c9-105">항목 업데이트</span><span class="sxs-lookup"><span data-stu-id="af2c9-105">Update Item</span></span>
 
<span data-ttu-id="af2c9-106">**요약:** 항목 서비스의 일부인 항목 업데이트 작업에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="af2c9-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="af2c9-107">항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="af2c9-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="af2c9-109">항목 업데이트 작업은 통화 품질 대시보드의 리포지토리 API에 있는 항목 서비스의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="af2c9-110">항목 업데이트</span><span class="sxs-lookup"><span data-stu-id="af2c9-110">Update Item</span></span>

<span data-ttu-id="af2c9-111">항목 업데이트는 리포지토리의 특정 항목을 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="af2c9-112">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="af2c9-112">**Method**</span></span>|<span data-ttu-id="af2c9-113">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="af2c9-113">**Request URI**</span></span>|<span data-ttu-id="af2c9-114">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="af2c9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af2c9-115">저장할</span><span class="sxs-lookup"><span data-stu-id="af2c9-115">PUT</span></span>  <br/> |<span data-ttu-id="af2c9-116">https://\<포털\>/QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="af2c9-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="af2c9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="af2c9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="af2c9-118">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="af2c9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="af2c9-119">**요청 헤더** -콘텐츠 형식: application/json.</span><span class="sxs-lookup"><span data-stu-id="af2c9-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="af2c9-120">**요청 본문** -JSON.</span><span class="sxs-lookup"><span data-stu-id="af2c9-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="af2c9-121">샘플 요청 페이로드:</span><span class="sxs-lookup"><span data-stu-id="af2c9-121">Sample request payload:</span></span>
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="af2c9-122">*내용*  기존 하위 항목의 새 콘텐츠로 저장할 JSON 형식 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="af2c9-123">기술적으로, 저장소는 모든 스키마의 콘텐츠를 저장할 수 있지만, 통화 품질 대시보드에 사용 되는 경우에는 보고서 또는 쿼리 중 하나 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="af2c9-124">*입력*  통화 품질 대시보드의 경우 항상 "application/json"을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="af2c9-125">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="af2c9-126">**상태 코드** -성공한 작업은 상태 코드 204 (콘텐츠 없음)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="af2c9-127">지정 된 항목 ID를 찾을 수 없는 경우 상태 코드 404 (찾을 수 없음)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="af2c9-128">"내용 없음"은 오류 상태가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-128">"No Content" is not an error status.</span></span> <span data-ttu-id="af2c9-129">응답은 본문에 아무것도 반환 하지 않은 것을 의미 합니다 (대조적으로 200 OK는 본문의 콘텐츠를 반환 함).</span><span class="sxs-lookup"><span data-stu-id="af2c9-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="af2c9-130">이는 항목이 성공적으로 업데이트 되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="af2c9-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="af2c9-131">**응답 헤더** -없음</span><span class="sxs-lookup"><span data-stu-id="af2c9-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="af2c9-132">**응답 본문** -없음</span><span class="sxs-lookup"><span data-stu-id="af2c9-132">**Response Body** - None.</span></span>
  

