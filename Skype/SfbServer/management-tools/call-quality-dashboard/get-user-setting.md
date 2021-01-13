---
title: 사용자 설정 가져오기
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '요약: 사용자 설정 서비스의 일부인 사용자 설정 사용 작업에 대해 자세히 알아보습니다. 사용자 설정 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832488"
---
# <a name="get-user-setting"></a>사용자 설정 가져오기
 
**요약:** 사용자 설정 서비스의 일부인 사용자 설정 사용 작업에 대해 자세히 알아보습니다. 사용자 설정 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
사용자 설정 저장 작업은 통화 품질 대시보드에 대한 리포지토리 API의 사용자 설정 서비스의 일부입니다.
  
## <a name="get-user-setting"></a>사용자 설정 가져오기

사용자 설정에서 단일 사용자 설정을 반환합니다.
  

|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 없음.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.
  
 **응답 헤더** - 추가 헤더가 없음.
  
 **응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId*  - 사용자의 ID입니다.
  
 *key*  - 설정의 키입니다.
  
 *value*  - 설정 값입니다.
  

