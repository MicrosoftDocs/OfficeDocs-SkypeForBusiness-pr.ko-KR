---
title: 비즈니스용 Skype 서버 2015의 ErrorReport 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport 테이블에는 발생 한 오류에 대 한 정보가 저장 됩니다. 각 레코드는 오류 발생 중 하나입니다. 이 오류는 프런트 엔드 서버에서 실행 되는 CDR 에이전트에서 또는 클라이언트에서 전송 된에 의해 캡처됩니다.
ms.openlocfilehash: 80a6106bd7c6b87a7519bca6ce5cc72f45147ad6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196754"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 ErrorReport 테이블
 
ErrorReport 테이블에는 발생 한 오류에 대 한 정보가 저장 됩니다. 각 레코드는 오류 발생 중 하나입니다. 이 오류는 프런트 엔드 서버에서 실행 되는 CDR 에이전트에서 또는 클라이언트에서 전송 된에 의해 캡처됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |dmtf  <br/> |주요한  <br/> |오류가 발생 한 날짜 및 시간입니다.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |주요한  <br/> |오류 보고서를 식별 하는 ID 번호입니다. 오류 보고서를 고유 하 게 식별 하는 **Errortime** 과 함께 사용 됩니다. <br/> |
|**ErrorId** <br/> |int  <br/> |외부  <br/> |오류 유형의 고유 ID입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Errordef 테이블](errordef.md) 을 참조 하세요. <br/> |
|**FromUserId** <br/> |int  <br/> |외부  <br/> |오류를 일으킨 요청을 시작한 사용자입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**ToUserId** <br/> |int  <br/> |외부  <br/> |오류가 발생 한 요청의 대상 사용자입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |외부  <br/> |오류와 관련 된 컨퍼런스 URI입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 ConferenceUris 테이블](conferenceuris.md) 을 참조 하세요. 일반적으로 ConferenceUriId가 null이 아닌 경우 FromUserId 또는 ToUserId는 null입니다. <br/> |
|**SessionIdTime** <br/> |dmtf  <br/> |외부  <br/> |세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |외부  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SourceId** <br/> |int  <br/> |외부  <br/> |오류 보고서를 보낸 서버 (보고서가 서버 구성 요소에서 전송 되는 경우) 자세한 내용은 [서버 테이블](servers.md) 을 참조 하세요. <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**ApplicationId** <br/> |int  <br/> |외부  <br/> |오류 보고서를 보낸 서버 (보고서가 서버 구성 요소에서 전송 되는 경우) 자세한 내용은 [비즈니스용 Skype 서버 2015의 응용 프로그램 테이블](application.md) 을 참조 하세요. <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**MsDiagHeader** <br/> |이미지  <br/> | <br/> |오류에 대 한 추가 정보입니다.  <br/> 이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |외부  <br/> |오류 보고서를 보내는 끝점의 클라이언트 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Clientversions 테이블](clientversions.md) 을 참조 하세요. <br/> |
|**IsCapturedByServer** <br/> |다소  <br/> ||프런트 엔드 서버에서 실행 중이거나 클라이언트가 보낸 CDR 에이전트에서 캡처한 오류 보고서입니다.  <br/> |
|**플래그** <br/> |smallint  <br/> ||나중에 사용 하기 위해 예약 되어 있습니다.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||고유한 식별자는 회의에 관련 된 다양 한 구성 요소에 대 한 조인 시간 정보를 연결 합니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**SessionSetupTime 시간** <br/> |int  <br/> ||특정 구성 요소가 컨퍼런스에 참가 하는 데 필요한 시간 (밀리초 단위)입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**ServerId** <br/> |int  <br/> |외부  <br/> |오류 보고서를 생성 한 서버의 정규화 된 도메인 이름을 나타냅니다.  <br/> |
|**PoolId** <br/> |int  <br/> |외부  <br/> |오류 보고서가 생성 된 풀의 정규화 된 도메인 이름을 나타냅니다.  <br/> |
|**LastModifiedTime** <br/> |Dmtf  <br/> ||모니터링 서비스에 내부적으로 사용 합니다.  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.  <br/> |
   

