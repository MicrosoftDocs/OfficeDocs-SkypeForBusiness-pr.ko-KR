---
title: 비즈니스용 Skype 서버 2015의 ConferenceUris 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 테이블은 데이터베이스에 기록 된 회의 세션에 참가 한 다양 한 회의 Uri 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 회의 URI를 나타냅니다.
ms.openlocfilehash: f1e95cce4fedf26477973a4fba6a9d3a32288f92
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815316"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 ConferenceUris 테이블
 
ConfereneUris 테이블은 데이터베이스에 기록 된 회의 세션에 참가 한 다양 한 회의 Uri 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 회의 URI를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |dmtf  <br/> |주요한  <br/> |내부에 사용 되는 타임 스탬프입니다.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |주요한  <br/> |이 회의 URI를 식별 하는 고유 번호입니다.  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> ||회의 URI.  <br/> |
|**검사** <br/> |int  <br/> ||ConferenceUri의 검사 값입니다. 데이터베이스 검색 속도를 향상 시키는 데 사용 됩니다.  <br/> |
|**UriTypeId** <br/> |int  <br/> |외부  <br/> |회의: IM 회의에 대 한 채팅 또는 컨퍼런스: 오디오/비디오 회의를 위한 오디오-영상 통화 등의 URI 형식 자세한 내용은 [UriTypes 표](uritypes.md) 표를 참조 하세요. <br/> |
   

