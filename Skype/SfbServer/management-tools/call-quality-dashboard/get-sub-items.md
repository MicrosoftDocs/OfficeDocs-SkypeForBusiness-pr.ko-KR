---
title: 하위 항목 가져오기
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: '요약: 항목 서비스의 일부인 Sub-Items Get Sub-Items 방법을 설명하는 정보를 제공합니다. 항목 서비스는 통화 품질 대시보드용 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: 3d17ab46ece202ea36dce45b6266a1cd3de74928
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774648"
---
# <a name="get-sub-items"></a>하위 항목 가져오기
 
**요약:** 항목 서비스의 일부인 Sub-Items Get Sub-Items 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드용 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
Get Sub-Items 호출 품질 대시보드에 대한 리포지토리 API의 항목 서비스의 일부입니다.
  
## <a name="get-sub-items"></a>하위 항목 가져오기

Get Sub-Items 항목의 하위 항목을 반환합니다.
  

|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 없음.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 작업이 성공하면 상태 코드 200(확인)이 반환됩니다. 지정한 사용자 ID를 찾을 수 없는 경우 상태 코드 404(찾을 수 없습니다)를 반환합니다.
  
 **응답 헤더** - 추가 헤더가 없음.
  
 **응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.
  
> [!NOTE]
> Item 개체의 배열이 반환됩니다. 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

Sub-Items 반환된 Item 개체에는 다음 세 개의 필드만 들어 있습니다. 
  
 *itemId*  - 항목의 ID입니다.
  
 *userId*  - 이 항목을 소유한 사용자의 ID입니다.
  
 *type*  - 콘텐츠의 형식입니다. 이 필드는 응용 프로그램에 의해 설정됩니다.
  
> [!NOTE]
>  `Content` 및 필드는 네트워크를 통해 전송되는 데이터의 양을 줄이기 위해 응답에 `subItems` 포함되지 않습니다.
  

