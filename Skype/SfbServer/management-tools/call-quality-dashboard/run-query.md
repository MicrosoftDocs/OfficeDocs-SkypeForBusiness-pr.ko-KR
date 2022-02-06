---
title: 쿼리 실행
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: '요약: 통화 품질 대시보드에 대한 데이터 API의 일부인 쿼리 실행 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
---

# <a name="run-query"></a>쿼리 실행

**요약:** 통화 품질 대시보드에 대한 데이터 API의 일부인 쿼리 실행 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.

쿼리 실행 작업은 통화 품질 대시보드용 데이터 API의 일부입니다.

## <a name="run-query"></a>쿼리 실행

쿼리 실행 작업을 사용하면 지정된 차원, 측정값 및 필터를 기반으로 큐브에서 쿼리를 실행하고 데이터를 반환할 수 있습니다.


|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|POST  <br/> |\<portal\>https:///QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **URI 매개 변수** - 없음.

 **요청 헤더** - 추가 헤더가 없습니다.

 **요청 본문** - JSON의 샘플 요청 페이로드입니다. 쿼리에 필요한 차원, 필터 및 측정값이 들어 있습니다.

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

 *Filters*  - 결과 데이터 집합이 관심 있는 데이터의 하위 집합만 반영하는 적용될 필터 식 목록입니다.

 *차원*  - 데이터 집계에 사용할 차원 목록입니다. 하나 이상의 차원이 필요하지만 하위 집계의 추가 수준을 얻기 위해 여러 차원을 지정할 수 있습니다.

 *측정*  값 - 지정한 차원을 기준으로 집계하기 원하는 메트릭인 측정 목록(팩트라고도 합니다.

 *추세* - 결과 데이터를 사용자 지정하는 추가 제어 지침입니다.

 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.

 **상태 코드** - 작업이 성공하면 상태 코드 200(확인)이 반환됩니다.

 **응답 헤더** - 추가 헤더가 없음.

 **응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다. 이 테이블에는 데이터가 포함된 데이터 테이블이 포함되어 있으며 쿼리 실행 시간 및 데이터가 캐시의 데이터인지 여부를 표시하는 메타 데이터가 포함되어 있습니다.

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

 *실행 시간*  - 서버에서 데이터를 반환하는 데 걸려온 총 시간입니다. 캐시를 포함하거나 포함하지 않을 수 있습니다.

 *데이터 결과*  - 쿼리의 결과입니다. 차원 구성원의 모든 음영과 차원의 구성원 이름과 지정된 Measurements의 집계 값을 포함하는 각 요소를 포함하는 2차원 배열입니다.

 *결과는 캐시에서*  - 진단용입니다. 결과가 캐시에서 왔는지 아니면 QoE 큐브에서 왔는가를 나타냅니다.
