---
title: 사용자 설정 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: '요약: 사용자 설정 서비스의 일부인 사용자 가져오기 설정 작업에 대해 알아봅니다. 사용자 설정 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 168e61aaebb47cb087e77cbd18e3e6edfd987227
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992645"
---
# <a name="get-user-setting"></a>사용자 설정 가져오기
 
**요약:** 사용자 설정 서비스의 일부인 사용자 가져오기 설정 작업에 대해 알아봅니다. 사용자 설정 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
사용자 가져오기 설정 작업은 통화 품질 대시보드의 리포지토리 API에 있는 사용자 설정 서비스의 일부입니다.
  
## <a name="get-user-setting"></a>사용자 설정 가져오기

사용자 설정 가져오기 단일 사용자 설정을 반환 합니다.
  

|**메서드와**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|가져오기  <br/> |https://\<포털\>/QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** -없음
  
 **헤더 요청** -추가 헤더가 없습니다.
  
 **본문 요청** -없음
  
 **응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.
  
 **상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.
  
 **응답 헤더** -추가 헤더가 없습니다.
  
 **응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId* -사용자의 ID입니다.
  
 setting의 *key* 키입니다.
  
 *value* -설정 값입니다.
  

