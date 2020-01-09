---
title: 항목 업데이트
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: '요약: 항목 서비스의 일부인 항목 업데이트 작업에 대해 알아봅니다. 항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 55d21d1e1b8f3814dab7699ff864ba8fea1d23be
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991393"
---
# <a name="update-item"></a>항목 업데이트
 
**요약:** 항목 서비스의 일부인 항목 업데이트 작업에 대해 알아보세요. 항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
항목 업데이트 작업은 통화 품질 대시보드의 리포지토리 API에 있는 항목 서비스의 일부입니다.
  
## <a name="update-item"></a>항목 업데이트

항목 업데이트는 리포지토리의 특정 항목을 업데이트 합니다.
  

|**메서드와**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|저장할  <br/> |https://\<포털\>/QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** -없음
  
 **요청 헤더** -콘텐츠 형식: application/json.
  
 **요청 본문** -JSON.
  
샘플 요청 페이로드:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *내용*  기존 하위 항목의 새 콘텐츠로 저장할 JSON 형식 데이터입니다. 기술적으로, 저장소는 모든 스키마의 콘텐츠를 저장할 수 있지만, 통화 품질 대시보드에 사용 되는 경우에는 보고서 또는 쿼리 중 하나 여야 합니다. *입력*  통화 품질 대시보드의 경우 항상 "application/json"을 지정 합니다.
  
 **응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.
  
 **상태 코드** -성공한 작업은 상태 코드 204 (콘텐츠 없음)을 반환 합니다. 지정 된 항목 ID를 찾을 수 없는 경우 상태 코드 404 (찾을 수 없음)을 반환 합니다.
  
> [!IMPORTANT]
> "내용 없음"은 오류 상태가 아닙니다. 응답은 본문에 아무것도 반환 하지 않은 것을 의미 합니다 (대조적으로 200 OK는 본문의 콘텐츠를 반환 함). 이는 항목이 성공적으로 업데이트 되었음을 나타냅니다. 
  
 **응답 헤더** -없음
  
 **응답 본문** -없음
  

