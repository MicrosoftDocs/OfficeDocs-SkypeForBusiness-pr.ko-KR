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
description: '요약: 항목 서비스의 일부인 항목 Get 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드용 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: fa82d158b41826a950a852633e6c039e9262543d4aabece5c04397eba40be8ae
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278446"
---
# <a name="get-item"></a>항목 가져오기
 
**요약:** 항목 서비스의 일부인 항목 Get 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드용 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
항목 보기 작업은 호출 품질 대시보드에 대한 리포지토리 API의 항목 서비스의 일부입니다.
  
## <a name="get-item"></a>항목 가져오기

Get Item은 리포지토리의 특정 항목을 반환합니다.
  
|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 없음.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 작업이 성공하면 상태 코드 200(확인)이 반환됩니다. 지정한 항목 ID를 찾을 수 없는 경우 상태 코드 404(찾을 수 없습니다)를 반환합니다.
  
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
  
 *subItemIds*  - 하위 항목의 ID(있는 경우)입니다. 이 작업은 호출을 저장하기 Sub-Items Get Sub-Items 짧은 회로입니다. 응용 프로그램은 Get Sub-Items 사용할 수 있습니다.
  

