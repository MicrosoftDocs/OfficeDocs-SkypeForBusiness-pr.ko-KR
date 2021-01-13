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
# <a name="get-dimension-members"></a>차원 구성원 가져오기
 
**요약:** 차원 구성원 Get 작업에 대해 자세히 알아보습니다. 차원 구성원 보기 작업은 통화 품질 대시보드에 대한 데이터 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
차원 구성원 보기 작업은 통화 품질 대시보드에 대한 데이터 API의 일부입니다.
  
## <a name="get-dimension-members"></a>차원 구성원 가져오기

차원 구성원 작업에서 특정 차원의 구성원 목록을 반환합니다. 또한 구성원 목록을 필터링하고 하위 집합을 얻을 수 있는 기능을 제공하여 전신 전송 비용을 줄일 수 있습니다.
  

|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 구성원이 원하는 차원의 이름이 포함되어 있습니다. 반환되는 구성원의 최대 수도 지정할 수 있습니다. 또한 일부 필터링을 지정하여 반환된 구성원을 제한할 수 있습니다.
  
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

 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.
  
 **응답 헤더** - 추가 헤더가 없음.
  
 **응답 본문** - 다음은 "[StartDate]에 대한 요청에 대한 응답으로 JSON의 샘플 응답 페이로드입니다. [Month]" 차원입니다.
  
> [!NOTE]
> 목록에는 목록의 일부만 표시됩니다. 
  
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
