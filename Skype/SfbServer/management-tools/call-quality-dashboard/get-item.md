---
title: 항목 가져오기
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: '요약: 항목 서비스의 일부인 항목 항목 선택 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832568"
---
# <a name="get-item"></a>항목 가져오기
 
**요약:** 항목 서비스의 일부인 항목 항목 선택 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
항목 항목 보기 작업은 호출 품질 대시보드에 대한 리포지토리 API의 항목 서비스의 일부입니다.
  
## <a name="get-item"></a>항목 가져오기

Get Item은 리포지토리의 특정 항목을 반환합니다.
  
|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 없음.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다. 지정한 항목 ID를 찾을 수 없는 경우 상태 코드 404(찾을 수 없습니다)를 반환합니다.
  
 **응답 헤더** - 추가 헤더가 없음.
  
 **응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId*  - 항목의 ID입니다.
  
 *userId*  - 이 항목을 소유한 사용자의 ID입니다.
  
 *content*  - 응용 프로그램별 콘텐츠입니다.
  
 *type*  - 콘텐츠의 형식입니다. 이 필드는 응용 프로그램에 의해 설정됩니다.
  
 *subItemIds*  - 하위 항목(있는 경우)의ID입니다. 이는 통화를 저장하기 위한 get Sub-Items 짧은 회로입니다. 또는 응용 프로그램에서 Get Sub-Items 같은 정보를 얻을 수 있습니다.
  

