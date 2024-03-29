---
title: 항목 업데이트
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: '요약: 항목 서비스의 일부인 항목 업데이트 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드용 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: 9ea8a72f70b252cb44a1e4cb15e24cc3718e4be2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384256"
---
# <a name="update-item"></a>항목 업데이트
 
**요약:** 항목 서비스의 일부인 항목 업데이트 작업에 대해 자세히 알아보습니다. 항목 서비스는 통화 품질 대시보드용 리포지토리 API의 일부입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
항목 업데이트 작업은 통화 품질 대시보드에 대한 리포지토리 API의 항목 서비스의 일부입니다.
  
## <a name="update-item"></a>항목 업데이트

업데이트 항목은 리포지토리의 특정 항목을 업데이트합니다.
  

|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|PUT  <br/> |\<portal\>https:///QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **Request Headers** -Content-Type: application/json.
  
 **요청 본문** - JSON.
  
샘플 요청 페이로드:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *content*  기존 하위 항목의 새 콘텐츠로 저장할 JSON 형식 데이터입니다. 기술적으로 리포지토리는 모든 스마마의 콘텐츠를 저장할 수 있지만 통화 품질 대시보드에 사용할 경우 보고서 또는 쿼리가 되어야 합니다. *type*  통화 품질 대시보드에 대해 항상 "application/json"을 지정합니다.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 작업이 성공하면 상태 코드 204(콘텐츠 없음)가 반환됩니다. 지정한 항목 ID를 찾을 수 없는 경우 상태 코드 404(찾을 수 없습니다)를 반환합니다.
  
> [!IMPORTANT]
> "콘텐츠 없음"은 오류 상태가 아 않습니다. 즉, 응답이 본문에 아무 것도 반환하지 않았음(반대로 200 OK는 Body의 콘텐츠를 반환)을 반환합니다. 항목이 성공적으로 업데이트된 것입니다. 
  
 **응답 헤더** - 없음.
  
 **응답 본문** - 없음.
  

