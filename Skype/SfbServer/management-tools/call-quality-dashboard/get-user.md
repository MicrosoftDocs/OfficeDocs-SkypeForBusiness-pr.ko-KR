---
title: 사용자 가져오기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '요약: 사용자 서비스의 일부인 사용자 가져오기 작업에 대해 알아봅니다. 사용자 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 09dcbbaeaae98ed7b01f3d710cfda23aa5fa986f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992625"
---
# <a name="get-user"></a>사용자 가져오기
 
**요약:** 사용자 서비스의 일부인 사용자 가져오기 작업에 대해 알아봅니다. 사용자 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
사용자 가져오기 작업은 통화 품질 대시보드의 리포지토리 API에 있는 사용자 서비스의 일부입니다.
  
## <a name="get-user"></a>사용자 가져오기

사용자가 리포지토리에서 사용자 레코드를 반환 합니다.
  
|**메서드와**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|가져오기  <br/> |https://\<포털\>/QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** -없음
  
 **헤더 요청** -추가 헤더가 없습니다.
  
 **본문 요청** -없음
  
 **응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.
  
 **상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다. 지정 된 사용자 ID를 찾을 수 없는 경우 상태 코드 404 (찾을 수 없음)을 반환 합니다.
  
 **응답 헤더** -추가 헤더가 없습니다.
  
 **응답 본문** -아래는 JSON의 샘플 응답 페이로드입니다.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId* -사용자의 ID입니다.
  
 *loginName* -일반 사용자에 대 한 외부 사용자 확인. 사용자 인증에 Windows 인증을 사용 하는 경우이는 사용자의 FQDN 일 수 있습니다.
  
 *defaultItemId* -이 사용자에 대 한 기본 항목의 ID입니다. 기본 항목은 사용자에 게 연결 된 맨 위에 있는 항목입니다. 이 사용자가 소유한 다른 모든 항목은 기본 항목에서 탐색할 수 있습니다.
  
> [!NOTE]
> 항목 가져오기 `defaultItemId` 작업에 대 한 값을 제공 하 여 기본 항목의 세부 정보를 검색 합니다.
  

