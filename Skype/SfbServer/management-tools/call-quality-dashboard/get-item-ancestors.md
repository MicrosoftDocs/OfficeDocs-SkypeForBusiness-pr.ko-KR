---
title: Item 상위 항목 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: '요약: 항목 서비스의 일부인 항목의 상위 항목 가져오기 작업에 대해 알아보세요. 항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 77fb5f46ada278bcb172a51620317182fe5d61b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186942"
---
# <a name="get-item-ancestors"></a>Item 상위 항목 가져오기
 
**요약:** 항목 서비스의 일부인 항목의 상위 항목 가져오기 작업에 대해 알아봅니다. 항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
항목 조상 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 항목 서비스의 일부입니다.
  
## <a name="get-item-ancestors"></a>Item 상위 항목 가져오기

Item 상위 항목 가져오기 저장소에서 상위 항목을 지정 합니다.
  

|**메서드와**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|가져오기  <br/> |https://\<포털\>/QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** -없음
  
 **헤더 요청** -추가 헤더가 없습니다.
  
 **본문 요청** -없음
  
 **응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.
  
 **상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다. 지정 된 사용자 ID를 찾을 수 없는 경우 상태 코드 404 (찾을 수 없음)을 반환 합니다.
  
 **응답 헤더** -추가 헤더가 없습니다.
  
 **응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.
  
```
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

 *Item1* -항목의 ID입니다.
  
 *Item2* -깊이는 항목 으로부터의 거리입니다. 0이 바로 상위입니다.
  
 *Item3* -항목의 제목입니다.
  

