---
title: ErrorReport 보기
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
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: ErrorReport 보기에는 보고된 오류에 대한 정보가 저장됩니다. 각 레코드는 발생한 한 가지 오류를 나타냅니다. 오류는 프런트 엔드 서버에서 실행하는 CDR 에이전트로 캡처되거나 클라이언트로 전송됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 324c22f58883207d49c0224043b8672560f1cf6e64551ca93b9ac43540d46ceb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295385"
---
# <a name="errorreport-view"></a>ErrorReport 보기
 
ErrorReport 보기에는 보고된 오류에 대한 정보가 저장됩니다. 각 레코드는 발생한 한 가지 오류를 나타냅니다. 오류는 프런트 엔드 서버에서 실행하는 CDR 에이전트로 캡처되거나 클라이언트로 전송됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |오류가 발생한 시간입니다. ErrorReportSeq와 함께 오류를 고유하게 식별하기 위해 사용됩니다.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |오류를 식별하기 위한 ID 번호입니다. ErrorTime과 함께 오류를 고유하게 식별하기 위해 사용됩니다.  <br/> |
|**MsDiagId** <br/> |int  <br/> |오류 보고서의 진단 ID입니다.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |오류가 유발된 사용자의 URI입니다.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |오류가 유발된 사용자의 URI 형식입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |오류가 유발된 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |오류 보고서의 대상인 사용자의 URI입니다.  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |오류 보고서의 대상인 사용자의 URI 형식입니다. 자세한 내용은 UriTypes Table을 참조하십시오.  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |오류 보고서의 대상인 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |오류 보고서의 대상인 회의의 URI입니다.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |오류 보고서의 대상인 회의의 URI 형식입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |오류 보고서를 시작한 세션 요청의 시간입니다. SessionIdSeq과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |오류 보고서를 시작한 세션 요청을 식별하는 ID 번호입니다. SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |오류가 유발된 세션의 SIP 대화 ID입니다. 형식:  <br/> dialog;from-tag;to-tag  <br/> 이 데이터는 다음 구문을 사용하여 텍스트 형식으로 변환할 수 있습니다.  <br/> cast(cast(ExternalId as varbinary(max)) as varchar(max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |오류를 유발한 사용자가 사용하는 클라이언트 버전입니다.  <br/> |
|**ClientType** <br/> |int  <br/> |오류를 유발한 사용자가 사용한 클라이언트입니다. 자세한 내용은 [UserAgentDef 테이블을](useragentdef.md) 참조합니다. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |오류를 유발한 사용자가 사용한 클라이언트 범주 이름입니다.  <br/> |
|**원본** <br/> |nvarchar(256)  <br/> |오류를 유발한 서버 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).  <br/> |
|**응용 프로그램** <br/> |nvarchar(256)  <br/> |오류를 유발한 응용 프로그램 이름입니다(보고서가 서버 구성 요소에서 전송된 경우).  <br/> |
|**ResponseCode** <br/> |int  <br/> |오류 보고서를 포함하는 SIP 메시지 세션에 대한 SIP 응답 코드입니다.  <br/> |
|**RequestType** <br/> |varchar(max)  <br/> |실패한 요청 유형입니다.  <br/> |
|**ContentType** <br/> |varchar(max)  <br/> |실패한 요청의 콘텐츠 유형입니다.  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |세션 유형입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 CallType](calltype.md) 테이블을 참조하십시오. <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |회의에 포함된 서로 다른 구성 요소의 참가 시간 정보와 연결된 고유 ID입니다.  <br/> |
|**SetupTime** <br/> |int  <br/> |회의에 참가하는 특정 구성 요소에 필요한 시간(밀리초)입니다.  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |프런트 엔드 서버에서 실행하는 CDR 에이전트에 의해 캡처되었는지, 아니면 클라이언트에 의해 전송되었는지를 나타냅니다.  <br/> |
|**플래그** <br/> |smallint  <br/> |나중에 사용하도록 예약됩니다.  <br/> |
|**MsDiagHeader** <br/> |varchar(max)  <br/> |오류에 대한 추가 정보입니다.  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |보고서를 제출한 프런트 엔드 서버의 정식 도메인 이름입니다.  <br/> |
|**풀** <br/> |nvarchar  <br/> |보고서를 제출한 프런트 엔드 서버가 포함된 풀의 정식 도메인 이름입니다.  <br/> |
   

