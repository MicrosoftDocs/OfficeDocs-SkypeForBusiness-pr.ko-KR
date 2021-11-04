---
title: UserAgent 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: UserAgent 테이블은 데이터베이스에 기록된 세션에 참가한 다양한 사용자 에이전트 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 사용자 에이전트를 나타임
ms.openlocfilehash: 7e870e9d63f3d1c9e199df36c5225af704388746
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771824"
---
# <a name="useragent-table"></a>UserAgent 테이블
 
UserAgent 테이블은 데이터베이스에 기록된 세션에 참가한 다양한 사용자 에이전트 목록을 저장하는 지원 테이블입니다. 테이블의 각 레코드는 하나의 사용자 에이전트를 나타임
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |이 사용자 에이전트를 식별하는 고유 번호입니다.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Unique  <br/> |사용자 에이전트 문자열입니다.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1은 중재 서버입니다.  <br/> 2는 A/V 회의 서버입니다.  <br/> 4는 비즈니스용 Skype.  <br/> 8은 IP 전화.  <br/> 16은 Live Meeting Console입니다.  <br/> 32는 DVT(배포 유효성 검사 도구)입니다.  <br/> 64는 Macintosh 비즈니스용 Skype 서버 사용할 수 있습니다.  <br/> 128은 비즈니스용 Skype 서버 있습니다.  <br/> 256은 회의 알림 있습니다.  <br/> 512는 회의 자동 전화 교환.  <br/> 1024는 응답 그룹 응용 프로그램입니다.  <br/> 2048은 외부 음성 제어입니다.  <br/> |
   

