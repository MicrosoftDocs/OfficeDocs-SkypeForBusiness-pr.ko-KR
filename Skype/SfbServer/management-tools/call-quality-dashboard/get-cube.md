---
title: 큐브 가져오기
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: '요약: 통화 품질 대시보드에 대한 데이터 API의 일부인 큐브 보기 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: 961453404d4abe4f026f240cd03e59a3b4c82993
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827501"
---
# <a name="get-cube"></a>큐브 가져오기
 
**요약:** 통화 품질 대시보드에 대한 데이터 API의 일부인 큐브 보기 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
큐브 보기 작업은 호출 품질 대시보드에 대한 데이터 API의 일부입니다.
  
## <a name="get-cube"></a>큐브 가져오기

큐브 다운로드 작업은 사용 가능한 크기 및 측정값 목록을 반환합니다.
  

|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 없음.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 작업이 성공하면 상태 코드 200(확인)이 반환됩니다.
  
 **응답 헤더** - 추가 헤더가 없음.
  
 **응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.
  
> [!NOTE]
> 이 예제에서는 각 Cube 요소 그룹의 처음 두 요소만 보여 주며, 
  
```json
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 *KPIS*  - 예약되어 있습니다. 요청 페이로드의 KPIS 섹션에서는 쿼리 실행 작업을 통해 큐브에 정의된 KPIS의 값을 반환할 수 있습니다. QoE 큐브에는 아직 KPIS가 없습니다.
  
 *차원*  - 쿼리 실행 작업에 대한 요청 페이로드의 필터 및 차원 섹션에서 사용할 수 있는 차원 목록입니다. 필터 식에서 차원을 사용하려면 차원 구성원 얻기 작업을 사용하여 얻을 수 있는 차원 구성원을 지정해야 합니다.
  
 *측정값*  - 쿼리 실행 작업에 대한 요청 페이로드의 측정 섹션에서 사용할 수 있는 측정 목록입니다.
  

