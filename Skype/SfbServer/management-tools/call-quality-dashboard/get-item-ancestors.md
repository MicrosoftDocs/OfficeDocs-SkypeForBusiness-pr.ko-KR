---
title: 상위 항목 가져오기
ms.reviewer: ''
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: '요약: 항목 서비스의 일부인 항목 Ancestors 항목 확인 작업에 대해 자세히 알아보는 방법을 설명하는 문서입니다. 항목 서비스는 통화 품질 대시보드용 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: 0cfc5385af1c0c821d4dc64e9ba0e0bd092fe833
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393740"
---
# <a name="get-item-ancestors"></a>상위 항목 가져오기
 
**요약:** 항목 서비스의 일부인 항목 Ancestors Get 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드용 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
항목 Ancestors Get 작업은 호출 품질 대시보드에 대한 리포지토리 API의 항목 서비스의 일부입니다.
  
## <a name="get-item-ancestors"></a>상위 항목 가져오기

항목 선행 항목은 리포지토리에서 특정 항목의 선조를 반환합니다.
  

|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 없음.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 작업이 성공하면 상태 코드 200(확인)이 반환됩니다. 지정한 사용자 ID를 찾을 수 없는 경우 상태 코드 404(찾을 수 없습니다)를 반환합니다.
  
 **응답 헤더** - 추가 헤더가 없음.
  
 **응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1*  - 항목의 ID입니다.
  
 *Item2*  - 깊이는 항목과의 거리입니다. 0은 직계 부모입니다.
  
 *Item3*  - 항목의 제목입니다.
  

