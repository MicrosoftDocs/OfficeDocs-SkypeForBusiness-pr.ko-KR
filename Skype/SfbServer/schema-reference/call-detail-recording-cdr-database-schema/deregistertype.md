---
title: 2015년 비즈니스용 Skype 서버 DeRegisterType 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 테이블은 'client initiated', 'registration expired' 또는 'client stopped responding'(클라이언트가 응답하지 않은 경우)을 등록을 끊을 수 있는 사용자 등록을 끊은 유형 목록을 저장하는 정적 테이블입니다.
ms.openlocfilehash: 4ce03a677ed275a925c56fe29b729fa2ead3eff3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845071"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 DeRegisterType 테이블
 
DeRegisterType 테이블은 'client initiated', 'registration expired' 또는 'client stopped responding'(클라이언트가 응답하지 않은 경우)을 등록을 끊을 수 있는 사용자 등록을 끊은 유형 목록을 저장하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || 허용되는 값은 다음과 같습니다. <br/>  0 - 알 수 없음 <br/>  1 -- 클라이언트가 등록 취소 시작 <br/>  2 -- 등록 만료 <br/>  3 - 클라이언트 충돌 <br/>  4 -- 사용자 특성 변경 <br/>  5 - 기본 설정 등록자 변경 <br/>  6 -- 레거시 클라이언트가 서바이벌 모드임 <br/> |
   

