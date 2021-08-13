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
description: '요약: User 설정 서비스의 일부인 사용자 설정 작업을 자세히 알아보는 방법을 설명하는 설정 있습니다. User 설정 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: b541cacf3c777ca5991640f3bff05265cf6eeeb5c88f59f9731d46318247c171
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298148"
---
# <a name="get-user-settings"></a>사용자 설정 가져오기
 
**요약:** User 설정 서비스에 설정 Get User 설정 대해 자세히 알아보습니다. User 설정 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
사용자 설정 Get User 설정 는 통화 품질 대시보드에 대한 리포지토리 API의 사용자 설정 서비스의 일부입니다.
  
## <a name="get-user-settings"></a>사용자 설정 가져오기

Get User 설정 지정된 사용자에 대한 설정 목록을 반환합니다.
  

|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수**
  
- *effective*  - 선택 사항입니다. 이 매개 변수는 특수 사용자 ID 기본값을 사용하는 경우만 적용됩니다. 그 외의 경우에는 무시됩니다. `True` 유효 사용자 설정을 반환하고 `false` 사용자 설정만 반환합니다(기본값).
    
  **요청 헤더** - 추가 헤더가 없습니다.
  
  **요청 본문** - 없음.
  
  **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
  **상태 코드** - 작업이 성공하면 상태 코드 200(확인)이 반환됩니다.
  
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
