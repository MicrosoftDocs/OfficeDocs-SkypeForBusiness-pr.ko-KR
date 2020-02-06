---
title: 캐시 지우기
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: '요약: 통화 품질 대시보드의 데이터 API에 포함 된 지우기 캐시 작업에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 821b02f204c98f5acefe69df1c848c31cd2205b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816887"
---
# <a name="clear-cache"></a>캐시 지우기
 
**요약:** 통화 품질 대시보드의 데이터 API에 포함 된 지우기 캐시 작업에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
캐시 지우기 작업은 통화 품질 대시보드의 데이터 API의 일부입니다.
  
## <a name="clear-cache"></a>캐시 지우기

캐시 지우기 작업은 쿼리 및 데이터에 대 한 서버의 캐시를 삭제 합니다. 이렇게 하면 캐시가 다시 설정 되 고 나중에 새 요청에 대 한 체감 품질 큐브에 대 한 최신 데이터를 받게 됩니다.
  

|**메서드와**|**요청 URI**|**HTTP 버전**|
|:-----|:-----|:-----|
|올리기  <br/> |https://\<portal\>/Qoedataservice/clearcache  <br/> |HTTP/1.1  <br/> |
   
 **URI 매개 변수** -없음
  
 **헤더 요청** -추가 헤더가 없습니다.
  
 **본문 요청** -없음
  
 **응답** -응답에는 HTTP 상태 코드 및 응답 헤더 집합이 포함 됩니다.
  
 **상태 코드** -성공 작업에서 상태 코드 200 (OK)을 반환 합니다.
  
 **응답 헤더** -추가 헤더가 없습니다.
  
 **응답 본문** -없음
  

