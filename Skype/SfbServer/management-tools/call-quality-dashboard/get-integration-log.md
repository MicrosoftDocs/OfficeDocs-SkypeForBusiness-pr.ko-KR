---
title: 통합 로그 가져오기
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '요약: 통화 품질 대시보드의 데이터 API의 일부인 통합 로그 가져오기 작업에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: e1d790f4723eaaf716482143f08c78624db47433
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888807"
---
# <a name="get-integration-log"></a>통합 로그 가져오기
 
**요약:** 통화 품질 대시보드의 데이터 API에 포함 된 통합 로그 가져오기 작업에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
통합 로그 가져오기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.
  
## <a name="get-integration-log"></a>통합 로그 가져오기

통합 로그 가져오기 작업 체감 품질 큐브 처리에서 작업을 설명 하는 로그 항목의 목록을 반환 합니다.
  
이 작업은 보안상의 이유로 기본적으로 사용 하지 않도록 설정 되어 있습니다. 이 기능을 사용 하지 않도록 설정 하면 빈 문자열이 반환 됩니다. 이 작업을 사용 하도록 설정 하려면 관리자가 Data API의 호스트 웹 응용 프로그램에 대 한 web.config를 구성 해야 합니다.
  

|메서드와|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|가져오기  <br/> |https://\<포털\>/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** -없음
  
 **헤더 요청** -추가 헤더가 없습니다.
  
 **본문 요청** -없음
  
 **응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.
  
 **상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.
  
 **응답 헤더** -추가 헤더가 없습니다.
  
 **응답 본문** -아래에는 로그 항목의 샘플 구조가 나와 있습니다.
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


