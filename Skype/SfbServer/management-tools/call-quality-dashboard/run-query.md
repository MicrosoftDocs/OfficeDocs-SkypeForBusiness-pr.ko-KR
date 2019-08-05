---
title: 쿼리 실행
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: '요약: 통화 품질 대시보드의 데이터 API의 일부인 쿼리 실행 작업에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 0b4c44c93009e014579a53872de82297c1486573
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186870"
---
# <a name="run-query"></a><span data-ttu-id="118f7-104">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="118f7-104">Run Query</span></span>

<span data-ttu-id="118f7-105">**요약:** 통화 품질 대시보드의 데이터 API의 일부인 쿼리 실행 작업에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="118f7-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="118f7-107">쿼리 실행 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="118f7-108">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="118f7-108">Run Query</span></span>

<span data-ttu-id="118f7-109">쿼리 실행 작업은 지정 된 차원, 측정값, 필터에 따라 큐브에 대 한 쿼리를 실행 하 고 데이터를 다시 반환할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="118f7-110">**메서드와**</span><span class="sxs-lookup"><span data-stu-id="118f7-110">**Method**</span></span>|<span data-ttu-id="118f7-111">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="118f7-111">**Request URI**</span></span>|<span data-ttu-id="118f7-112">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="118f7-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="118f7-113">올리기</span><span class="sxs-lookup"><span data-stu-id="118f7-113">POST</span></span>  <br/> |<span data-ttu-id="118f7-114">https://\<포털\>/QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="118f7-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="118f7-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="118f7-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="118f7-116">**URI 매개 변수** -없음</span><span class="sxs-lookup"><span data-stu-id="118f7-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="118f7-117">**헤더 요청** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="118f7-118">**요청 본문** -JSON의 샘플 요청 페이로드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="118f7-119">쿼리에 필요한 차원, 필터, 측정이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-119">It contains dimensions, filters, and measurement required for a query.</span></span>

```
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}
```

 <span data-ttu-id="118f7-120">*필터* -결과 데이터 집합에 관심 있는 데이터의 하위 집합만 반영 하도록 적용 되는 필터 식의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="118f7-121">*차원* -데이터를 집계 하는 데 사용 되는 차원의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="118f7-122">적어도 하나 이상의 차원이 필요 하지만 하위 집계의 추가 수준을 확보 하기 위해 여러 차원을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="118f7-123">*단위* -지정 된 차원에 따라 집계 될 원하는 메트릭으로 측정값 (팩트 라고도 함) 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="118f7-124">*추세* -결과 데이터를 사용자 지정 하는 추가 컨트롤 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="118f7-125">**응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="118f7-126">**상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="118f7-127">**응답 헤더** -추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="118f7-128">**응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="118f7-129">데이터를 포함 하는 데이터 테이블에는 쿼리 실행 시간 및 데이터를 캐시에서 가져온 것인지 여부를 보여 주는 메타 데이터도 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

```
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}
```

 <span data-ttu-id="118f7-130">*실행 시간* -서버가 데이터를 반환 하는 데 걸린 총 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="118f7-131">캐시를 포함할 수도 있고 그렇지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="118f7-132">*데이터 결과* -쿼리 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="118f7-133">차원의 구성원의 모든 순열, 그리고 지정 된 측정값의 집계 값을 비롯 하 여 차원의 구성원 이름이 포함 된 각 요소를 포함 하는 2 차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="118f7-134">*결과는* 진단에 대해 캐시에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="118f7-135">결과를 캐시에서 가져왔는지 또는 체감 품질 큐브를 통해 반환 했는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="118f7-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
