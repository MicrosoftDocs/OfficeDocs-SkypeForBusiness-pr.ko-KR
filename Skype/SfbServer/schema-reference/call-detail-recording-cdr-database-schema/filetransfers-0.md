---
title: 비즈니스용 Skype 서버 2015의 FileTransfers 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 8b287d2fc2c40fe7e20cb3abc4ed6e403da701b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815216"
---
# <a name="filetransfers-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 FileTransfers 테이블
 
각 레코드는 하나의 파일 전송 세션을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |기본, 외래  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |기본, 외래  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**파일 이름** <br/> |nvarchar (256)  <br/> ||파일의 이름입니다.  <br/> |
|**FileIdentity** <br/> |uniqueidentifier  <br/> ||동일한 파일 이름을 포함 하는 파일 전송을 구분 하는 고유 식별자입니다.  <br/> |
|**쿠키란** <br/> |name  <br/> |주요한  <br/> |모든 추가 작업 메시지를이 항목에 연결 된 것으로 식별 하는 데 사용 됩니다.  <br/> |
|**사항** <br/> |다소  <br/> ||TRUE 또는 NULL 일 수 있습니다. TRUE 인 경우 거부 및 취소는 NULL입니다.  <br/> |
|**거부** <br/> |다소  <br/> ||TRUE 또는 NULL 일 수 있습니다. TRUE 이면 Accept와 Cancel은 NULL입니다.  <br/> |
|**취소** <br/> |다소  <br/> ||TRUE 또는 NULL 일 수 있습니다. TRUE 이면 Accept 및 Reject는 NULL입니다.  <br/> |
|**LastModifiedTime** <br/> |Dmtf  <br/> ||모니터링 서비스에 내부적으로 사용 합니다.  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.  <br/> |
   

