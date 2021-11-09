---
title: 2015년 비즈니스용 Skype 서버 CallType 테이블
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: CallType 테이블은 사용 가능한 통화 유형 목록이 저장된 정적 테이블입니다.
ms.openlocfilehash: 7f00e924041c5b26f7045cf8f97ae82daa141611
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845091"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 CallType 테이블
 
CallType 테이블은 사용 가능한 통화 유형 목록이 저장된 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || 허용되는 값은 다음과 같습니다. <br/>  0 -- 알 수 없음 <br/>  1 - 인스턴트 메시징 <br/>  2 -- 응용 프로그램 공유 <br/>  3 -- 오디오 <br/>  4 - 오디오 및 비디오 <br/>  5 - 파일 전송 <br/> |
   

