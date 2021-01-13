---
title: 비즈니스용 Skype 서버의 DeRegisterType 테이블
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 테이블은 'client initiated', 'registration expired' 또는 'client stopped responding'(클라이언트가 응답하지 않은 경우)을 등록을 끊을 수 있는 사용자 유형 목록을 저장하는 정적 테이블입니다.
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816078"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버의 DeRegisterType 테이블
 
DeRegisterType 테이블은 'client initiated', 'registration expired' 또는 'client stopped responding'(클라이언트가 응답하지 않은 경우)을 등록을 끊을 수 있는 사용자 유형 목록을 저장하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || 허용되는 값은 다음과 같습니다. <br/>  0 - 알 수 없음 <br/>  1 -- 클라이언트가 등록 취소 시작 <br/>  2 -- 등록 만료 <br/>  3 - 클라이언트 충돌 <br/>  4 -- 사용자 특성 변경 <br/>  5 - 기본 설정 등록자 변경 <br/>  6 -- 레거시 클라이언트가 서바이벌 모드임 <br/> |
   

