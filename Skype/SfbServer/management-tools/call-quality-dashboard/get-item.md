---
title: 항목 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: '요약: 항목 서비스의 일부인 항목 가져오기 작업에 대해 알아보세요. 항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: bfd5015603ac73fb48c4e30635cf8ae0fb14bf13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186936"
---
# <a name="get-item"></a>항목 가져오기
 
**요약:** 항목 서비스의 일부인 항목 가져오기 작업에 대해 알아봅니다. 항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
항목 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 항목 서비스의 일부입니다.
  
## <a name="get-item"></a>항목 가져오기

항목 가져오기 리포지토리의 특정 항목을 반환 합니다.
  
|**메서드와**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|가져오기  <br/> |https://\<포털\>/QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** -없음
  
 **헤더 요청** -추가 헤더가 없습니다.
  
 **본문 요청** -없음
  
 **응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.
  
 **상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다. 지정 된 항목 ID를 찾을 수 없는 경우 상태 코드 404 (찾을 수 없음)을 반환 합니다.
  
 **응답 헤더** -추가 헤더가 없습니다.
  
 **응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId* -항목의 ID입니다.
  
 *userId* -이 항목을 소유 하는 사용자의 ID입니다.
  
 *콘텐츠* -응용 프로그램 관련 콘텐츠입니다.
  
 *type* -콘텐츠의 형식입니다. 이 필드는 응용 프로그램에 의해 설정 됩니다.
  
 *subItemIds* -하위 항목의 id입니다 (있는 경우). 이는 통화를 저장 하는 하위 항목 가져오기 작업의 짧은 회로입니다. 또한 응용 프로그램은 하위 항목 가져오기 작업을 사용 하 여 동일한 정보를 얻을 수 있습니다.
  

