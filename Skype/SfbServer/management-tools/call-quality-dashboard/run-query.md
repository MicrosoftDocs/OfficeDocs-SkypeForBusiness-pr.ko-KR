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
ms.openlocfilehash: 8d31ea4c597ea3353fdd5da3e863938aababe819
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991403"
---
# <a name="run-query"></a>쿼리 실행

**요약:** 통화 품질 대시보드의 데이터 API의 일부인 쿼리 실행 작업에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.

쿼리 실행 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.

## <a name="run-query"></a>쿼리 실행

쿼리 실행 작업은 지정 된 차원, 측정값, 필터에 따라 큐브에 대 한 쿼리를 실행 하 고 데이터를 다시 반환할 수 있는 기능을 제공 합니다.


|**메서드와**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|올리기  <br/> |https://\<포털\>/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **URI 매개 변수** -없음

 **헤더 요청** -추가 헤더가 없습니다.

 **요청 본문** -JSON의 샘플 요청 페이로드는 다음과 같습니다. 쿼리에 필요한 차원, 필터, 측정이 포함 되어 있습니다.

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

 *필터* -결과 데이터 집합에 관심 있는 데이터의 하위 집합만 반영 하도록 적용 되는 필터 식의 목록입니다.

 *차원* -데이터를 집계 하는 데 사용 되는 차원의 목록입니다. 적어도 하나 이상의 차원이 필요 하지만 하위 집계의 추가 수준을 확보 하기 위해 여러 차원을 지정할 수 있습니다.

 *단위* -지정 된 차원에 따라 집계 될 원하는 메트릭으로 측정값 (팩트 라고도 함) 목록입니다.

 *추세* -결과 데이터를 사용자 지정 하는 추가 컨트롤 지침입니다.

 **응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.

 **상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.

 **응답 헤더** -추가 헤더가 없습니다.

 **응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다. 데이터를 포함 하는 데이터 테이블에는 쿼리 실행 시간 및 데이터를 캐시에서 가져온 것인지 여부를 보여 주는 메타 데이터도 포함 됩니다.

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

 *실행 시간* -서버가 데이터를 반환 하는 데 걸린 총 시간입니다. 캐시를 포함할 수도 있고 그렇지 않을 수도 있습니다.

 *데이터 결과* -쿼리 결과입니다. 차원의 구성원의 모든 순열, 그리고 지정 된 측정값의 집계 값을 비롯 하 여 차원의 구성원 이름이 포함 된 각 요소를 포함 하는 2 차원 배열입니다.

 *결과는* 진단에 대해 캐시에서 발생 합니다. 결과를 캐시에서 가져왔는지 또는 체감 품질 큐브를 통해 반환 했는지 여부를 나타냅니다.
