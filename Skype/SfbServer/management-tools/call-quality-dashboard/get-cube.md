---
title: 큐브 가져오기
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: '요약: 통화 품질 대시보드의 데이터 API의 일부인 큐브 가져오기 작업에 대해 알아보세요. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 7ae24309ea49d8f7d8d2684c141adb44c5bff2b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816837"
---
# <a name="get-cube"></a>큐브 가져오기
 
**요약:** 통화 품질 대시보드의 데이터 API의 일부인 큐브 가져오기 작업에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
큐브 가져오기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.
  
## <a name="get-cube"></a>큐브 가져오기

큐브 가져오기 작업은 사용 가능한 차원과 측정값의 목록을 반환 합니다.
  

|**메서드와**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|가져오기  <br/> |https://\<portal\>/Qoedataservice/cubestructure  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** -없음
  
 **헤더 요청** -추가 헤더가 없습니다.
  
 **본문 요청** -없음
  
 **응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.
  
 **상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.
  
 **응답 헤더** -추가 헤더가 없습니다.
  
 **응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.
  
> [!NOTE]
> 이 샘플은 각 큐브 요소 그룹의 처음 두 요소만 표시 합니다. 
  
```
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

 *Kpi* -예약 됨. 요청 페이로드의 Kpi 섹션을 사용 하면 쿼리 실행 작업에서 큐브에 정의 된 Kpi에 대 한 값을 반환할 수 있습니다. 체감 품질 큐브에 Kpi가 아직 없습니다.
  
 *차원* -쿼리 실행 작업에 대 한 요청 페이로드의 필터 및 차원 섹션에서 사용할 수 있는 차원의 목록입니다. 필터 식에서 차원을 사용 하려면 차원 구성원 가져오기 작업을 사용 하 여 가져올 수 있는 차원 구성원을 지정 해야 합니다.
  
 *단위* -쿼리 실행 작업에 대 한 요청 페이로드의 측정 섹션에서 사용할 수 있는 측정값 목록입니다.
  

