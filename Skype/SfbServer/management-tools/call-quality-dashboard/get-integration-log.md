---
title: 통합 로그 가져오기
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
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: '요약: 통화 품질 대시보드에 대한 데이터 API의 일부인 통합 로그 보기 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: b82ecffd5b39df6e149787ec7b3265f3e8176376
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388076"
---
# <a name="get-integration-log"></a>통합 로그 가져오기
 
**요약:** 통화 품질 대시보드에 대한 데이터 API의 일부인 통합 로그 보기 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
통합 로그 보기 작업은 통화 품질 대시보드에 대한 데이터 API의 일부입니다.
  
## <a name="get-integration-log"></a>통합 로그 가져오기

통합 로그 얻기 작업은 QoE 큐브 처리의 활동을 설명하는 로그 항목 목록을 반환합니다.
  
보안상의 이유로 이 작업은 기본적으로 사용하지 않도록 설정되어 있습니다. 이 설정을 사용하지 않도록 설정하면 빈 문자열이 반환됩니다. 이 작업을 사용하도록 설정하려면 관리자가 데이터 API의 web.config 응용 프로그램에 대한 웹 응용 프로그램을 구성해야 합니다.
  

|메서드|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 없음.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 작업이 성공하면 상태 코드 200(확인)이 반환됩니다.
  
 **응답 헤더** - 추가 헤더가 없음.
  
 **응답 본문** - 다음은 로그 항목의 샘플 구조입니다.
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


