---
title: 캐시 지우기
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '요약: 통화 품질 대시보드에 대한 데이터 API의 일부인 캐시 지우기 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: f48c2308785a03ca9e344a31eddc7f5cc7f38a92
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778198"
---
# <a name="clear-cache"></a>캐시 지우기
 
**요약:** 통화 품질 대시보드에 대한 데이터 API의 일부인 캐시 지우기 작업에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
캐시 지우기 작업은 통화 품질 대시보드용 데이터 API의 일부입니다.
  
## <a name="clear-cache"></a>캐시 지우기

캐시 지우기 작업을 수행하면 쿼리 및 데이터에 대한 서버의 캐시가 삭제됩니다. 이렇게 하면 캐시가 다시 설정됩니다. 그러면 이후에 새 요청에 대한 QoE 큐브에서 새 데이터를 얻게 됩니다.
  

|**방법**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** - 없음.
  
 **요청 헤더** - 추가 헤더가 없습니다.
  
 **요청 본문** - 없음.
  
 **응답** - 응답에는 HTTP 상태 코드와 응답 헤더 집합이 포함됩니다.
  
 **상태 코드** - 작업이 성공하면 상태 코드 200(확인)이 반환됩니다.
  
 **응답 헤더** - 추가 헤더가 없음.
  
 **응답 본문** - 없음.
  

