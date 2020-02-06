---
title: 캐시 지우기
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '요약: 통화 품질 대시보드의 데이터 API에 포함 된 지우기 캐시 작업에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 821b02f204c98f5acefe69df1c848c31cd2205b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816887"
---
# <a name="clear-cache"></a><span data-ttu-id="c0f17-104">캐시 지우기</span><span class="sxs-lookup"><span data-stu-id="c0f17-104">Clear Cache</span></span>
 
<span data-ttu-id="c0f17-105">**요약:** 통화 품질 대시보드의 데이터 API에 포함 된 지우기 캐시 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="c0f17-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c0f17-107">캐시 지우기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="c0f17-108">캐시 지우기</span><span class="sxs-lookup"><span data-stu-id="c0f17-108">Clear Cache</span></span>

<span data-ttu-id="c0f17-109">캐시 지우기 작업은 쿼리 및 데이터에 대 한 서버의 캐시를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="c0f17-110">이렇게 하면 캐시가 다시 설정 되 고 나중에 새 요청에 대 한 체감 품질 큐브에 대 한 최신 데이터를 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="c0f17-111">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="c0f17-111">**Method**</span></span>|<span data-ttu-id="c0f17-112">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="c0f17-112">**Request URI**</span></span>|<span data-ttu-id="c0f17-113">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="c0f17-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c0f17-114">올리기</span><span class="sxs-lookup"><span data-stu-id="c0f17-114">POST</span></span>  <br/> |<span data-ttu-id="c0f17-115">https://\<portal\>/Qoedataservice/clearcache</span><span class="sxs-lookup"><span data-stu-id="c0f17-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="c0f17-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c0f17-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c0f17-117">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="c0f17-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c0f17-118">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c0f17-119">**본문 요청** -없음</span><span class="sxs-lookup"><span data-stu-id="c0f17-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="c0f17-120">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c0f17-121">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="c0f17-122">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c0f17-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c0f17-123">**응답 본문** -없음</span><span class="sxs-lookup"><span data-stu-id="c0f17-123">**Response Body** - None.</span></span>
  

