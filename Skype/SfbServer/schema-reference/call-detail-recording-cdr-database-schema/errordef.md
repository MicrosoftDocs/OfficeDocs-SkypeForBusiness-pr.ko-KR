---
title: 비즈니스용 Skype 서버 2015의 ErrorDef 테이블
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: ErrorDef 테이블에는 발생할 수 있는 각 유형의 오류에 대 한 정보가 저장 됩니다. 각 레코드는 오류 유형 중 하나입니다.
ms.openlocfilehash: f686692bee334c0927b6e8342cfb7152b3e54f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815236"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 ErrorDef 테이블
 
ErrorDef 테이블에는 발생할 수 있는 각 유형의 오류에 대 한 정보가 저장 됩니다. 각 레코드는 오류 유형 중 하나입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ErrorId** <br/> |int  <br/> |주요한  <br/> |이 유형의 오류를 식별 하는 고유 ID 번호입니다.  <br/> |
|**ResponseCode** <br/> |int  <br/> | <br/> |이 오류와 연결 된 표준 SIP 응답 코드입니다.  <br/> |
|**MsDiagId** <br/> |int  <br/> | <br/> |Microsoft 진단 ID입니다.  <br/> |
|**CallTypeId** <br/> |Int  <br/> |외부  <br/> |통화의 유형입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Calltype 테이블](calltype.md) 을 참조 하세요. <br/> |
|**RequestType** <br/> |varbinary (33)  <br/> | <br/> |실패 한 요청의 유형입니다.  <br/> 이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|**ContentType** <br/> |varbinary (257)  <br/> | <br/> |실패 한 요청의 콘텐츠 형식입니다.  <br/> 이 데이터는이 syntaxt를 사용 하 여 텍스트 형식으로 변환할 수 있습니다.  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

