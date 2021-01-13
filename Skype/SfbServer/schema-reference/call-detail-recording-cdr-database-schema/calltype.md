---
title: 비즈니스용 Skype 서버의 CallType 테이블
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 테이블은 사용 가능한 통화 유형 목록이 저장된 정적 테이블입니다.
ms.openlocfilehash: 89f29a2c826f4aef12cc0332e40df0fb421c3932
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813368"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버의 CallType 테이블
 
CallType 테이블은 사용 가능한 통화 유형 목록이 저장된 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 허용되는 값은 다음과 같습니다. <br/>  0 -- 알 수 없음 <br/>  1 - 인스턴트 메시징 <br/>  2 -- 응용 프로그램 공유 <br/>  3 -- 오디오 <br/>  4 - 오디오 및 비디오 <br/>  5 - 파일 전송 <br/> |
   

