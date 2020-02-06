---
title: 사용자 설정 가져오기
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: '요약: 사용자 설정 서비스의 일부인 사용자 설정 가져오기 작업에 대해 알아봅니다. 사용자 설정 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 5b5ad679387866ba6562e031b6d3a42cc68851a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816747"
---
# <a name="get-user-settings"></a>사용자 설정 가져오기
 
**요약:** 사용자 설정 서비스의 일부인 사용자 설정 가져오기 작업에 대해 알아봅니다. 사용자 설정 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
사용자 설정 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 사용자 설정 서비스의 일부입니다.
  
## <a name="get-user-settings"></a>사용자 설정 가져오기

사용자 설정 가져오기 지정 된 사용자에 대 한 설정 목록을 반환 합니다.
  

|**메서드와**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|가져오기  <br/> |https://\<포털\>/QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수**
  
- *유효* -선택 사항입니다. 이 매개 변수는 특별 한 사용자 ID default를 사용 하는 경우에만 적용 됩니다. 다른 경우에는이를 무시 합니다. `True`유효 사용자 설정을 반환 하 `false` 고 사용자 설정만 반환 합니다 (기본값).
    
  **헤더 요청** -추가 헤더가 없습니다.
  
  **본문 요청** -없음
  
  **응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.
  
  **상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.
  
  **응답 헤더** -추가 헤더가 없습니다.
  
  **응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.
  
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
