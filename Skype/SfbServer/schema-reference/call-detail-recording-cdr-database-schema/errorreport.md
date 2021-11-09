---
title: 2015년 비즈니스용 Skype 서버 ErrorReport 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport 테이블에는 발생한 오류에 대한 정보가 저장됩니다. 각 레코드는 발생한 한 가지 오류를 나타냅니다. 오류는 프런트 엔드 서버에서 실행하는 CDR 에이전트로 캡처되거나 클라이언트로 전송됩니다.
ms.openlocfilehash: 3047ede92ec248f612249a27b7c04fc3c9f046c1
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849641"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 ErrorReport 테이블
 
ErrorReport 테이블에는 발생한 오류에 대한 정보가 저장됩니다. 각 레코드는 발생한 한 가지 오류를 나타냅니다. 오류는 프런트 엔드 서버에서 실행하는 CDR 에이전트로 캡처되거나 클라이언트로 전송됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary  <br/> |오류가 발생한 날짜 및 시간입니다.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |오류 보고서를 식별하기 위한 ID 번호입니다. **ErrorTime과** 함께 오류 보고서를 고유하게 식별하는 데 사용됩니다. <br/> |
|**ErrorId** <br/> |int  <br/> |외계인  <br/> |오류 유형의 고유 ID입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ErrorDef 테이블을](errordef.md) 참조하십시오. <br/> |
|**FromUserId** <br/> |int  <br/> |외계인  <br/> |오류를 유발한 요청을 시작한 사용자입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**ToUserId** <br/> |int  <br/> |외계인  <br/> |오류를 유발한 요청의 대상 사용자입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**ConferenceUriId** <br/> |int  <br/> |외계인  <br/> |오류와 관련된 회의 URI입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ConferenceUris 테이블을](conferenceuris.md) 참조하세요. 일반적으로 ConferenceUriId가 null이 아닌 경우 FromUserId 또는 ToUserId는 null이 됩니다. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |외계인  <br/> |**SessionIdSeq** 와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |외계인  <br/> |세션을 식별하기 위한 ID 번호입니다. **SessionIdTime** 과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**SourceId** <br/> |int  <br/> |외계인  <br/> |오류 보고서를 보낸 서버입니다(보고서가 서버 구성 요소에서 전송되는 경우). 자세한 내용은 [Servers 테이블을](servers.md) 참조하십시오. <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**ApplicationId** <br/> |int  <br/> |외계인  <br/> |오류 보고서를 보낸 서버입니다(보고서가 서버 구성 요소에서 전송되는 경우). 자세한 [내용은 비즈니스용 Skype 서버 2015의 Application](application.md) 테이블을 참조하십시오. <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**MsDiagHeader** <br/> |이미지  <br/> | <br/> |오류에 대한 자세한 정보  <br/> 이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |외계인  <br/> |오류 보고서를 보내는 끝점의 클라이언트 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ClientVersions](clientversions.md) 테이블을 참조하세요. <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||프런트 엔드 서버에서 실행되는 CDR 에이전트가 캡처하거나 클라이언트가 보낸 오류 보고서입니다.  <br/> |
|**플래그** <br/> |smallint  <br/> ||나중에 사용하도록 예약됩니다.  <br/> |
|**TelemetryId** <br/> |uniqueIdentifier  <br/> ||회의에 포함된 서로 다른 구성 요소의 참가 시간 정보와 연결된 고유 ID입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||회의에 참가하는 특정 구성 요소에 필요한 시간(밀리초)입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**ServerId** <br/> |int  <br/> |외계인  <br/> |오류 보고서를 생성한 서버의 정식 도메인 이름을 지정합니다.  <br/> |
|**PoolId** <br/> |int  <br/> |외계인  <br/> |오류 보고서가 생성된 풀의 정식 도메인 이름을 지정합니다.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||모니터링 서비스의 내부 사용 용도  <br/> 이 필드는 2015년 비즈니스용 Skype 서버 도입했습니다.  <br/> |
   

