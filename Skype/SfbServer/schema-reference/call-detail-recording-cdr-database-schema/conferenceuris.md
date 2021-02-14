---
title: 비즈니스용 Skype 서버의 ConferenceUris 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: ConfereneUris 테이블은 데이터베이스에 기록된 회의 세션에 참가한 다양한 회의 URI 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 회의 URI를 나타내며,
ms.openlocfilehash: f439c828460f06067105f8f2da493616c223ed85
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816138"
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버의 ConferenceUris 테이블
 
ConfereneUris 테이블은 데이터베이스에 기록된 회의 세션에 참가한 다양한 회의 URI 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 회의 URI를 나타내며,
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |타임스탬프, 내부 사용  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |이 전화 회의 URI를 식별하는 고유 번호입니다.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||회의 URI입니다.  <br/> |
|**체크 um** <br/> |int  <br/> ||ConferenceUri의 체크um입니다. 데이터베이스 검색 속도를 향상하는 데 사용됩니다.  <br/> |
|**UriTypeId** <br/> |int  <br/> |외계인  <br/> |URI 유형(예: IM 회의용 conf:chat 또는 오디오/비디오 회의의 경우 conf:audio-video) 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
   

