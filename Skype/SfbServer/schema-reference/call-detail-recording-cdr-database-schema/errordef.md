---
title: 2015년 비즈니스용 Skype 서버 ErrorDef 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 테이블에는 발생할 수 있는 각 오류 유형에 대한 정보가 저장됩니다. 각 레코드는 하나의 오류 유형입니다.
ms.openlocfilehash: c4480df63b081fc264334ffeb7031c54de887875
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743884"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 ErrorDef 테이블
 
ErrorDef 테이블에는 발생할 수 있는 각 오류 유형에 대한 정보가 저장됩니다. 각 레코드는 하나의 오류 유형입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |Primary  <br/> |이 유형의 오류를 식별하는 고유 ID 번호입니다.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |이 오류와 관련된 표준 SIP 응답 코드입니다.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 진단 ID입니다.  <br/> |
|**CallTypeId** <br/> |임계값  <br/> |외계인  <br/> |통화 유형입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 CallType](calltype.md) 테이블을 참조하십시오. <br/> |
|**RequestType** <br/> |varbinary(33)  <br/> | <br/> |실패한 요청 유형입니다.  <br/> 이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary(257)  <br/> | <br/> |실패한 요청의 콘텐츠 유형입니다.  <br/> 이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

