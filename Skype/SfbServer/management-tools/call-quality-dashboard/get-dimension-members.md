---
title: 차원 구성원 가져오기
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: '요약: 차원 구성원 가져오기 작업에 대해 알아보세요. 차원 구성원 가져오기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 40e5ac8b95c24c3a8cb759da99f7d7aeaa391576
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888817"
---
# <a name="get-dimension-members"></a>차원 구성원 가져오기
 
**요약:** 차원 구성원 가져오기 작업에 대해 알아보세요. 차원 구성원 가져오기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
차원 구성원 가져오기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.
  
## <a name="get-dimension-members"></a>차원 구성원 가져오기

차원 구성원 가져오기 작업은 특정 차원의 구성원 목록을 반환 합니다. 또한 구성원 목록을 필터링 하 고 하위 집합을 가져오는 기능을 제공 하 여 회선 전송 비용을 줄입니다.
  

|**메서드와**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|올리기  <br/> |https://\<포털\>/Qoedataservice/dimensionmembers  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** -없음
  
 **헤더 요청** -추가 헤더가 없습니다.
  
 **요청 본문** -구성원이 원하는 차원의 이름을 포함 합니다. 또한 반환 되는 구성원의 최대 개수를 지정 하 여 반환 된 구성원을 제한 하는 필터링을 지정할 수 있습니다.
  
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

 **응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.
  
 **상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.
  
 **응답 헤더** -추가 헤더가 없습니다.
  
 **응답 본문** -다음은 "[시작 됨]에 대 한 요청에 대 한 응답으로 JSON의 샘플 응답 페이로드입니다. [Month] "차원.
  
> [!NOTE]
> 목록은 목록의 일부분만 표시 합니다. 
  
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
