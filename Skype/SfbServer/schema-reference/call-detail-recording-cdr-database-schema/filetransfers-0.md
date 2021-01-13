---
title: 비즈니스용 Skype 서버의 FileTransfers 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
description: 각 레코드는 하나의 파일 전송 세션을 나타냅니다.
ms.openlocfilehash: fde871bb434a2aa458bc59cfdf098c82ba3a7093
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821698"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버의 FileTransfers 테이블
 
각 레코드는 하나의 파일 전송 세션을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary, Foreign  <br/> |세션 요청 시간입니다. **SessionIdSeq** 와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |세션을 식별하기 위한 ID 번호입니다. **SessionIdTime** 과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하세요. <br/> |
|**File Name** <br/> |nvarchar(256)  <br/> ||파일의 이름입니다.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||동일한 파일 이름을 포함하는 각 전송 작업을 구분하기 위한 고유 식별자입니다.  <br/> |
|**쿠키** <br/> |nvarchar(128)  <br/> |Primary  <br/> |이 항목과 연결 중인 모든 후속 작업 메시지를 식별하기 위해 사용됩니다.  <br/> |
|**수락** <br/> |bit  <br/> ||TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Reject 및 Cancel이 NULL이 됩니다.  <br/> |
|**거부** <br/> |bit  <br/> ||TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Cancel이 NULL이 됩니다.  <br/> |
|**취소** <br/> |bit  <br/> ||TRUE 또는 NULL일 수 있습니다. TRUE인 경우 Accept 및 Reject가 NULL이 됩니다.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||모니터링 서비스의 내부 사용 용도  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입했습니다.  <br/> |
   

