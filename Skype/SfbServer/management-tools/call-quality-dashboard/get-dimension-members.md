---
title: 차원 구성원 가져오기
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: '요약: 차원 구성원 Get 작업에 대해 자세히 알아보습니다. 차원 구성원 보기 작업은 통화 품질 대시보드에 대한 데이터 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832638"
---
# <a name="get-dimension-members"></a><span data-ttu-id="dfcad-105">차원 구성원 가져오기</span><span class="sxs-lookup"><span data-stu-id="dfcad-105">Get Dimension Members</span></span>
 
<span data-ttu-id="dfcad-106">**요약:** 차원 구성원 Get 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="dfcad-107">차원 구성원 보기 작업은 통화 품질 대시보드에 대한 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="dfcad-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="dfcad-109">차원 구성원 보기 작업은 통화 품질 대시보드에 대한 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="dfcad-110">차원 구성원 가져오기</span><span class="sxs-lookup"><span data-stu-id="dfcad-110">Get Dimension Members</span></span>

<span data-ttu-id="dfcad-111">차원 구성원 작업에서 특정 차원의 구성원 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="dfcad-112">또한 구성원 목록을 필터링하고 하위 집합을 얻을 수 있는 기능을 제공하여 전신 전송 비용을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="dfcad-113">**방법**</span><span class="sxs-lookup"><span data-stu-id="dfcad-113">**Method**</span></span>|<span data-ttu-id="dfcad-114">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="dfcad-114">**Request URI**</span></span>|<span data-ttu-id="dfcad-115">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="dfcad-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dfcad-116">POST</span><span class="sxs-lookup"><span data-stu-id="dfcad-116">POST</span></span>  <br/> |<span data-ttu-id="dfcad-117">https:// \<portal\> /QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="dfcad-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="dfcad-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="dfcad-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="dfcad-119">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="dfcad-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="dfcad-120">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="dfcad-121">**요청 본문** - 구성원이 원하는 차원의 이름이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="dfcad-122">반환되는 구성원의 최대 수도 지정할 수 있습니다. 또한 일부 필터링을 지정하여 반환된 구성원을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="dfcad-123">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="dfcad-124">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="dfcad-125">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="dfcad-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="dfcad-126">**응답 본문** - 다음은 "[StartDate]에 대한 요청에 대한 응답으로 JSON의 샘플 응답 페이로드입니다. [Month]" 차원입니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dfcad-127">목록에는 목록의 일부만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="dfcad-127">The list is only showing a small portion of the list.</span></span> 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
