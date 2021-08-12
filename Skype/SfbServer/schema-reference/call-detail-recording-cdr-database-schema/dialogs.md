---
title: 2015년 비즈니스용 Skype 서버 Dialogs 테이블
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Dialogs 테이블은 피어 투 피어 세션의 DialogID에 대한 정보를 저장하는 지원 테이블입니다.
ms.openlocfilehash: 368abb6131367434edbdf1fe142a376fe9a155277eec8b369482545146dbdc3b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302282"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 Dialogs 테이블
 
Dialogs 테이블은 피어 투 피어 세션의 DialogID에 대한 정보를 저장하는 지원 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |세션 요청 시간 세션을 고유하게 식별하기 위해 SessionIDSeq와 함께 사용됩니다.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |세션을 식별하기 위한 ID 번호입니다. SessionIDTime과 함께 세션을 고유하게 식별하는 데 사용됩니다.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |ExternalID의 체크um입니다. 이 필드는 데이터베이스 검색 속도를 높이는 데 사용됩니다.  <br/> |
|**externalId** <br/> |varbinary(775)  <br/> | <br/> |이진 파일로 저장된 SIP 대화 ID입니다. 이진 파일 형식은 다음입니다.  <br/> dialog;from-tag;to-tag  <br/> 이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

