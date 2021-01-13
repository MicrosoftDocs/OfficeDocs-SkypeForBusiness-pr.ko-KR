---
title: 사용자 가져오기
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: '요약: 사용자 서비스의 일부인 사용자 Get 사용자 작업에 대해 자세히 알아보습니다. 사용자 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832418"
---
# <a name="get-user"></a>사용자 가져오기
 
**요약:** 사용자 서비스의 일부인 사용자 Get 사용자 작업에 대해 자세히 알아보습니다. 사용자 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
사용자 보기 작업은 통화 품질 대시보드에 대한 리포지토리 API의 사용자 서비스의 일부입니다.
  
## <a name="get-user"></a>사용자 가져오기

사용자 레코드를 리포지토리에서 반환합니다.
  
|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 없음.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 성공적인 작업이 상태 코드 200(확인)을 반환합니다. 지정한 사용자 ID를 찾을 수 없는 경우 상태 코드 404(찾을 수 없습니다)를 반환합니다.
  
 **응답 헤더** - 추가 헤더가 없음.
  
 **응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId*  - 사용자의 ID입니다.
  
 *loginName*  - 일반 사용자의 외부 사용자 ID입니다. Windows 인증을 사용하여 사용자를 인증하는 경우 사용자의 FQDN일 수 있습니다.
  
 *defaultItemId*  - 이 사용자의 기본 항목 ID입니다. 기본 항목은 사용자에게 연결된 최상위 항목입니다. 이 사용자가 소유한 다른 모든 항목은 기본 항목에서 탐색할 수 있습니다.
  
> [!NOTE]
> 기본 항목의 세부 정보를 검색하기 위해 항목 Get 작업에  `defaultItemId` 값을 제공합니다.
  

