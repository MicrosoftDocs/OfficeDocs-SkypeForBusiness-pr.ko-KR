---
title: 항목 가져오기
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: '요약: 항목 서비스의 일부인 항목 항목 Get 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드용 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: e4c93cd4f3eee724c2879752b01097f60d45a84584f06c87853238423c68a640
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278426"
---
# <a name="get-items"></a>항목 가져오기
 
**요약:** 항목 서비스의 일부인 항목 Get 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드용 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
항목 보기 작업은 통화 품질 대시보드에 대한 리포지토리 API의 항목 서비스의 일부입니다.
  
## <a name="get-items"></a>항목 가져오기

Get Items는 리포지토리의 모든 Items를 반환합니다.
  
|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 없음.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 작업이 성공하면 상태 코드 200(확인)이 반환됩니다.
  
 **응답 헤더** - 추가 헤더가 없음.
  
 **응답 본문** - 다음은 JSON의 샘플 응답 페이로드입니다.
  
> [!NOTE]
> Item 개체의 배열이 반환됩니다. Item 개체에 대한 자세한 내용은 항목 보기를 참조합니다. 
  
```json
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
