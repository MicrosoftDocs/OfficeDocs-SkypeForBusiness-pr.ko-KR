---
title: 2015년 비즈니스용 Skype 서버 CallType 테이블
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
ms.openlocfilehash: d5dce646dfff73d9935aba568827e21671daf4073721f8b892f369d62348e945
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296967"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 CallType 테이블
 
CallType 테이블은 사용 가능한 통화 유형 목록이 저장된 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 허용되는 값은 다음과 같습니다. <br/>  0 -- 알 수 없음 <br/>  1 - 인스턴트 메시징 <br/>  2 -- 응용 프로그램 공유 <br/>  3 -- 오디오 <br/>  4 - 오디오 및 비디오 <br/>  5 - 파일 전송 <br/> |
   

