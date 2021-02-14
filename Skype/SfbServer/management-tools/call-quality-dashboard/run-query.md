---
title: 쿼리 실행
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: '요약: 통화 품질 대시보드에 대한 데이터 API의 일부인 쿼리 실행 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803118"
---
# <a name="run-query"></a><span data-ttu-id="70af9-104">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="70af9-104">Run Query</span></span>

<span data-ttu-id="70af9-105">**요약:** 통화 품질 대시보드에 대한 데이터 API의 일부인 쿼리 실행 작업에 대해 자세히 알아보습니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="70af9-106">통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="70af9-107">쿼리 실행 작업은 통화 품질 대시보드에 대한 데이터 API의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="70af9-108">쿼리 실행</span><span class="sxs-lookup"><span data-stu-id="70af9-108">Run Query</span></span>

<span data-ttu-id="70af9-109">쿼리 실행 작업은 지정된 차원, 측정값 및 필터를 기반으로 큐브에서 쿼리를 실행하고 데이터를 반환하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="70af9-110">**방법**</span><span class="sxs-lookup"><span data-stu-id="70af9-110">**Method**</span></span>|<span data-ttu-id="70af9-111">**요청 URI**</span><span class="sxs-lookup"><span data-stu-id="70af9-111">**Request URI**</span></span>|<span data-ttu-id="70af9-112">**HTTP 버전**</span><span class="sxs-lookup"><span data-stu-id="70af9-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="70af9-113">POST</span><span class="sxs-lookup"><span data-stu-id="70af9-113">POST</span></span>  <br/> |<span data-ttu-id="70af9-114">https:// \<portal\> /QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="70af9-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="70af9-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="70af9-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="70af9-116">**URI 매개 변수** - 없음.</span><span class="sxs-lookup"><span data-stu-id="70af9-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="70af9-117">**요청 헤더** - 추가 헤더가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="70af9-118">**요청 본문** - JSON의 샘플 요청 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="70af9-119">쿼리에 필요한 차원, 필터 및 측정값이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-119">It contains dimensions, filters, and measurement required for a query.</span></span>

```json
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

 <span data-ttu-id="70af9-120">*필터*  - 결과 데이터 집합이 관심 있는 데이터의 하위 집합만 반영하는 필터 식 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="70af9-121">*차원*  - 데이터 집계에 사용할 차원 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="70af9-122">하나 이상의 차원이 필요하지만 하위 집계의 추가 수준을 얻기 위해 여러 차원을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="70af9-123">*측정값*  - 지정한 차원을 기준으로 집계하기 원하는 메트릭인 측정 목록(팩트라고도 합니다.)</span><span class="sxs-lookup"><span data-stu-id="70af9-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="70af9-124">*추세*  - 결과 데이터를 사용자 지정하기 위한 추가 제어 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="70af9-125">**응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="70af9-126">**상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="70af9-127">**응답 헤더** - 추가 헤더가 없음.</span><span class="sxs-lookup"><span data-stu-id="70af9-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="70af9-128">**응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="70af9-129">데이터를 포함하는 데이터 테이블을 포함하며 쿼리 실행 시간 및 데이터가 캐시의 데이터인지 여부를 표시하는 메타 데이터를 포함하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

```json
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

 <span data-ttu-id="70af9-130">*실행 시간*  - 서버에서 데이터를 반환하는 데 걸려온 총 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="70af9-131">캐시를 포함하거나 포함하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="70af9-132">*데이터 결과*  - 쿼리의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="70af9-133">이 배열은 차원 구성원의 모든 음영과 차원의 멤버 이름 및 지정된 Measurements의 집계된 값을 포함하는 각 요소를 포함하는 2차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="70af9-134">*결과는 캐시에서 생성됩니다.*  진단용입니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="70af9-135">결과가 캐시에서 왔거나 QoE 큐브에서 왔는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70af9-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
