---
title: 차원 구성원 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: '요약: 차원 구성원 가져오기 작업에 대해 알아보세요. 차원 구성원 가져오기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: c457e7f3b42aaeb11c35180bc4c1ae6ee42b914e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186948"
---
# <a name="get-dimension-members"></a><span data-ttu-id="9b10e-105">차원 구성원 가져오기</span><span class="sxs-lookup"><span data-stu-id="9b10e-105">Get Dimension Members</span></span>
 
<span data-ttu-id="9b10e-106">**요약:** 차원 구성원 가져오기 작업에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9b10e-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="9b10e-107">차원 구성원 가져오기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="9b10e-108">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9b10e-109">차원 구성원 가져오기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="9b10e-110">차원 구성원 가져오기</span><span class="sxs-lookup"><span data-stu-id="9b10e-110">Get Dimension Members</span></span>

<span data-ttu-id="9b10e-111">차원 구성원 가져오기 작업은 특정 차원의 구성원 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="9b10e-112">또한 구성원 목록을 필터링 하 고 하위 집합을 가져오는 기능을 제공 하 여 회선 전송 비용을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="9b10e-113">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="9b10e-113">**Method**</span></span>|<span data-ttu-id="9b10e-114">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="9b10e-114">**Request URI**</span></span>|<span data-ttu-id="9b10e-115">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="9b10e-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9b10e-116">올리기</span><span class="sxs-lookup"><span data-stu-id="9b10e-116">POST</span></span>  <br/> |<span data-ttu-id="9b10e-117">https://\<포털\>/Qoedataservice/dimensionmembers</span><span class="sxs-lookup"><span data-stu-id="9b10e-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="9b10e-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9b10e-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9b10e-119">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="9b10e-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9b10e-120">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9b10e-121">**요청 본문** -구성원이 원하는 차원의 이름을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="9b10e-122">또한 반환 되는 구성원의 최대 개수를 지정 하 여 반환 된 구성원을 제한 하는 필터링을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="9b10e-123">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9b10e-124">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9b10e-125">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9b10e-126">**응답 본문** -다음은 "[시작 됨]에 대 한 요청에 대 한 응답으로 JSON의 샘플 응답 페이로드입니다. [Month] "차원.</span><span class="sxs-lookup"><span data-stu-id="9b10e-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9b10e-127">목록은 목록의 일부분만 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b10e-127">The list is only showing a small portion of the list.</span></span> 
  
```
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
