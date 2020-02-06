---
title: ErrorReport 보기
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
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: ErrorReport 보기는 보고 된 오류에 대 한 정보를 저장 합니다. 각 레코드는 오류 발생 중 하나입니다. 이 오류는 프런트 엔드 서버에서 실행 되는 CDR 에이전트에서 또는 클라이언트에서 전송 된에 의해 캡처됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: d51b085d5dabb8a6ae0dc367b23dd23a1702174e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815246"
---
# <a name="errorreport-view"></a>ErrorReport 보기
 
ErrorReport 보기는 보고 된 오류에 대 한 정보를 저장 합니다. 각 레코드는 오류 발생 중 하나입니다. 이 오류는 프런트 엔드 서버에서 실행 되는 CDR 에이전트에서 또는 클라이언트에서 전송 된에 의해 캡처됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |dmtf  <br/> |오류가 발생 한 시간입니다. 오류를 고유 하 게 식별 하는 ErrorReportSeq와 함께 사용 합니다.  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |오류를 식별 하는 ID 번호입니다. 오류를 고유 하 게 식별 하는 ErrorTime과 함께 사용 됩니다.  <br/> |
|**MsDiagId** <br/> |int  <br/> |오류 보고서의 진단 ID입니다.  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |오류를 발생 시킨 사용자의 URI입니다.  <br/> |
|**Fromurit** <br/> |nvarchar (256)  <br/> |오류를 발생 시킨 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**FromTenant** <br/> |nvarchar (256)  <br/> |오류를 발생 시킨 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**ToUri** <br/> |nvarchar (450)  <br/> |오류 보고서를 대상으로 하는 사용자의 URI입니다.  <br/> |
|**ToUriType** <br/> |nvarchar (256)  <br/> |오류 보고서를 대상으로 하는 사용자의 URI 유형입니다. 자세한 내용은 UriTypes 테이블을 참조 하세요.  <br/> |
|**ToTenant 넌 트** <br/> |nvarchar (256)  <br/> |오류 보고서를 대상으로 하는 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |오류 보고서의 대상인 컨퍼런스의 URI입니다.  <br/> |
|**ConferenceUriType** <br/> |nvarchar (256)  <br/> |오류 보고서의 대상에 해당 하는 회의의 URI 형식입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**SessionIdTime** <br/> |dmtf  <br/> |오류 보고를 시작 하는 세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |오류 보고서를 시작 하는 세션 요청을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**DialogId** <br/> |varstring (775)  <br/> |오류를 발생 시킨 세션의 SIP 대화 상자 ID입니다. 형식은 다음과 같습니다.  <br/> 대화 상자; from 태그; 태그  <br/> 이 구문을 사용 하 여이 데이터를 텍스트 형식으로 변환할 수 있습니다.  <br/> 캐스트 (cast (max) as varchar (max))  <br/> |
|**ClientVersion** <br/> |nvarchar (256)  <br/> |오류를 발생 시킨 사용자가 사용 하는 클라이언트 버전입니다.  <br/> |
|**ClientType** <br/> |int  <br/> |오류를 발생 시킨 사용자가 사용 하는 클라이언트입니다. 자세한 내용은 [Useragentdef 테이블](useragentdef.md) 을 참조 하세요. <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |오류를 발생 시킨 사용자가 사용 하는 클라이언트 범주의 이름입니다.  <br/> |
|**Source** <br/> |nvarchar (256)  <br/> |오류를 발생 시킨 서버의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).  <br/> |
|**응용 프로그램** <br/> |nvarchar (256)  <br/> |오류를 발생 시킨 응용 프로그램의 이름입니다 (보고서가 서버 구성 요소에서 전송 된 경우).  <br/> |
|**ResponseCode** <br/> |int  <br/> |오류 보고서를 포함 하는 SIP 메시지의 세션에 대 한 SIP 응답 코드  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |실패 한 요청의 유형입니다.  <br/> |
|**ContentType** <br/> |varchar (max)  <br/> |실패 한 요청의 콘텐츠 형식입니다.  <br/> |
|**CallType** <br/> |nvarchar (256)  <br/> |세션의 유형입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Calltype 테이블](calltype.md) 을 참조 하세요. <br/> |
|**TelemetryId** <br/> |uniqueidentifier  <br/> |고유한 식별자는 회의에 관련 된 다양 한 구성 요소에 대 한 조인 시간 정보를 연결 합니다.  <br/> |
|**SetupTime 시간** <br/> |int  <br/> |특정 구성 요소가 컨퍼런스에 참가 하는 데 필요한 시간 (밀리초 단위)입니다.  <br/> |
|**IsCapturedByServer** <br/> |다소  <br/> |프런트 엔드 서버에서 실행 중이거나 클라이언트가 보낸 CDR 에이전트에 의해 오류 보고서가 캡처 되었는지 여부를 나타냅니다.  <br/> |
|**플래그** <br/> |smallint  <br/> |나중에 사용 하기 위해 예약 되어 있습니다.  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |오류에 대 한 추가 정보입니다.  <br/> |
|**FrontEnd** <br/> |varchar  <br/> |보고서를 제출한 프런트 엔드 서버의 정규화 된 도메인 이름입니다.  <br/> |
|**풀** <br/> |varchar  <br/> |보고서를 제출한 프런트 엔드 서버를 포함 하는 풀의 정규화 된 도메인 이름입니다.  <br/> |
   

