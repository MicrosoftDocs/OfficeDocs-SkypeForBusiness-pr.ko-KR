---
title: 캐시 지우기
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '요약: 통화 품질 대시보드에 대한 데이터 API의 일부인 캐시 지우기 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806418"
---
# <a name="clear-cache"></a><span data-ttu-id="d3f34-104">캐시 지우기</span><span class="sxs-lookup"><span data-stu-id="d3f34-104">Clear Cache</span></span>
 
<span data-ttu-id="d3f34-105">**요약:** 통화 품질 대시보드에 대한 데이터 API의 일부인 캐시 지우기 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="d3f34-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d3f34-107">캐시 지우기 작업은 통화 품질 대시보드에 대한 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="d3f34-108">캐시 지우기</span><span class="sxs-lookup"><span data-stu-id="d3f34-108">Clear Cache</span></span>

<span data-ttu-id="d3f34-109">캐시 지우기 작업을 수행하면 쿼리 및 데이터에 대한 서버의 캐시가 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="d3f34-110">이렇게 하면 캐시가 다시 설정됩니다. 그러면 이후에 QoE 큐브에서 새 요청에 대한 새 데이터가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="d3f34-111">**방법**</span><span class="sxs-lookup"><span data-stu-id="d3f34-111">**Method**</span></span>|<span data-ttu-id="d3f34-112">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="d3f34-112">**Request URI**</span></span>|<span data-ttu-id="d3f34-113">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="d3f34-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3f34-114">POST</span><span class="sxs-lookup"><span data-stu-id="d3f34-114">POST</span></span>  <br/> |<span data-ttu-id="d3f34-115">https:// \<portal\> /QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="d3f34-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="d3f34-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d3f34-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d3f34-117">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="d3f34-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d3f34-118">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d3f34-119">**요청 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="d3f34-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d3f34-120">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d3f34-121">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d3f34-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="d3f34-122">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="d3f34-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d3f34-123">**응답 본문** - 없음.</span><span class="sxs-lookup"><span data-stu-id="d3f34-123">**Response Body** - None.</span></span>
  

