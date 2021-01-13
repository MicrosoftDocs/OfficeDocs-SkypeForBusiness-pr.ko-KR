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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: '요약: 사용자 설정 서비스의 일부인 사용자 설정 Get 사용자 설정 작업에 대해 자세히 알아보습니다. 사용자 설정 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832478"
---
# <a name="get-user-settings"></a>사용자 설정 가져오기
 
**요약:** 사용자 설정 서비스의 일부인 사용자 설정 Get 작업에 대해 자세히 알아보습니다. 사용자 설정 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
사용자 설정 보기 작업은 통화 품질 대시보드에 대한 리포지토리 API의 사용자 설정 서비스의 일부입니다.
  
## <a name="get-user-settings"></a>사용자 설정 가져오기

사용자 설정으로 이동하면 지정된 사용자에 대한 설정 목록이 반환됩니다.
  

|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수**
  
- *effective*  - 선택 사항입니다. 이 매개 변수는 특수 사용자 ID 기본값을 사용하는 경우만 적용됩니다. 그 외의 경우에는 무시됩니다. `True` 유효 사용자 설정을 반환하고 `false` 사용자 설정만 반환합니다(기본값).
    
  **요청 헤더** - 추가 헤더가 없습니다.
  
  **요청 본문** - 없음.
  
  **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
  **상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다.
  
  **응답 헤더** - 추가 헤더가 없음.
  
  **응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
