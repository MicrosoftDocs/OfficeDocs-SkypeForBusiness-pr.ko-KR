---
title: UserAgent 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자 에이전트의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 한 명의 사용자 에이전트를 나타냅니다.
ms.openlocfilehash: d0a287881a352801d237894c5b150b5a08d91fc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805056"
---
# <a name="useragent-table"></a>UserAgent 테이블
 
UserAgent 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자 에이전트의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 한 명의 사용자 에이전트를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |주요한  <br/> |이 사용자 에이전트를 식별 하는 고유 번호입니다.  <br/> |
|**UserAgent** <br/> |nvarchar (256)  <br/> |독특한  <br/> |사용자 에이전트 문자열입니다.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1은 중재 서버입니다.  <br/> 2는 A/V 회의 서버입니다.  <br/> 4 비즈니스용 Skype.  <br/> 8은 IP 전화입니다.  <br/> 16 개는 Live Meeting Console입니다.  <br/> 32는 DVT (배포 유효성 검사 도구)입니다.  <br/> Macintosh 컴퓨터의 비즈니스용 Skype 서버는 64입니다.  <br/> 128는 비즈니스용 Skype 서버 수행자입니다.  <br/> 256는 회의 알림 서비스입니다.  <br/> 512는 회의 자동 전화 교환입니다.  <br/> 1024는 응답 그룹 응용 프로그램입니다.  <br/> 2048는 음성 제어를 벗어납니다.  <br/> |
   

