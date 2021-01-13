---
title: 큐브 가져오기
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: '요약: 통화 품질 대시보드에 대한 데이터 API의 일부인 큐브 보기 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832628"
---
# <a name="get-cube"></a>큐브 가져오기
 
**요약:** 호출 품질 대시보드에 대한 데이터 API의 일부인 큐브 보기 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
큐브 보기 작업은 호출 품질 대시보드에 대한 데이터 API의 일부입니다.
  
## <a name="get-cube"></a>큐브 가져오기

큐브를 다운로드할 때 사용 가능한 크기 및 측정값 목록이 반환됩니다.
  

|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 없음.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.
  
 **응답 헤더** - 추가 헤더가 없음.
  
 **응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.
  
> [!NOTE]
> 이 예제에서는 각 큐브 요소 그룹의 처음 두 요소만 보여 주며, 
  
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

 *KPIS*  - 예약되어 있습니다. 요청 페이로드의 KPIS 섹션을 사용하면 쿼리 실행 작업을 통해 큐브에 정의된 KPIS의 값을 반환할 수 있습니다. 아직 QoE 큐브에 KPIS가 없습니다.
  
 *dimensions*  - 쿼리 실행 작업에 대한 요청 페이로드의 필터 및 차원 섹션에 사용될 수 있는 차원 목록입니다. 필터 식에서 차원을 사용하려면 차원 구성원 얻기 작업을 사용하여 얻을 수 있는 차원 구성원을 지정해야 합니다.
  
 *measurements*  - 쿼리 실행 작업에 대한 요청 페이로드의 측정 섹션에서 사용할 수 있는 측정 목록입니다.
  

