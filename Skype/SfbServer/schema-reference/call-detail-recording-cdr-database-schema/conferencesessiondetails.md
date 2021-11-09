---
title: ConferenceSessionDetails 보기
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
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: ConferenceSessionDetails 보기에는 단체 세션에 대한 정보가 저장됩니다. 각 레코드는 Focus를 가진 세션이거나, 특정 회의 서버를 가진 세션일 수 있는 하나의 회의 세션을 나타냅니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: f35a815743dcfb8dba3d2a69943c9c5c42344a86
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849671"
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails 보기
 
ConferenceSessionDetails 보기에는 단체 세션에 대한 정보가 저장됩니다. 각 레코드는 Focus를 가진 세션이거나, 특정 회의 서버를 가진 세션일 수 있는 하나의 회의 세션을 나타냅니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |세션 요청 시간입니다. SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |세션을 식별하기 위한 ID 번호입니다. SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**InviteTime** <br/> |datetime  <br/> |첫 번째 INVITE 요청의 시간입니다. 이 필드는 일반적으로 세션의 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 필드에 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 채워집니다.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |회의의 URI입니다.  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |회의 URI의 형식입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |반복해서 수행되는 회의를 구분하는 식별자입니다. 반복되는 각 회의 인스턴스는 동일한 ConferenceURI를 갖지만 ConfInstance 값이 다릅니다.  <br/> |
|**McuConferenceUri** <br/> |nvarchar(450)  <br/> |회의 서버의 URI입니다.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar(256)  <br/> |회의 서버 URI의 형식입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |세션에 관련된 사용자의 URI입니다.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |세션에 속하는 사용자 URI의 형식입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |세션에 속하는 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |세션에 속하는 사용자의 고유 식별자입니다.  <br/> |
|**EndTime** <br/> |datetime  <br/> |세션의 종료 시간입니다.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar(256)  <br/> |회의 서버의 버전입니다.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |회의 서버의 유형입니다. 자세한 내용은 [UserAgentDef 테이블을](useragentdef.md) 참조하십시오. <br/> |
|**ConferenceCategory** <br/> |nvarchar(64)  <br/> |회의 서버 범주입니다.  <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |세션에 참가한 사용자가 사용한 클라이언트 버전입니다.  <br/> |
|**UserClientType** <br/> |int  <br/> |세션에 참가한 사용자가 사용한 클라이언트입니다. 자세한 내용은 [UserAgentDef 테이블을](useragentdef.md) 참조합니다. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |세션에 속하는 사용자가 사용한 클라이언트의 범주 이름입니다.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |세션을 대신 시작한 사용자의 URI입니다.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |세션을 대신 시작한 사용자 URI의 형식입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |세션을 대신 시작한 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |세션을 참조한 사용자의 URI입니다.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |세션을 참조한 사용자 URI의 형식입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**ReferredByUriTenant** <br/> |nvarchar(256)  <br/> |세션을 참조한 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP 대화 ID입니다. 형식은 다음과 같습니다.  <br/> :d;from-tag;to-tag  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |현재 세션으로 교체된 대화를 식별하기 위한 ID 번호입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |세션을 식별하기 위한 ID 번호입니다. ReplaceDialogIdTime과 함께 이 세션으로 교체된 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |세션이 교체하는 SIP 대화 ID입니다. 형식은 다음과 같습니다.  <br/> dialog;from-tag;to-tag  <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> |세션이 회의 서버에서 시작되었는지 여부를 나타냅니다.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> |세션이 회의 서버에서 종료되었는지 여부를 나타냅니다.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> |사용자가 내부 네트워크에서 로그온했는지 여부를 나타냅니다.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |첫 번째 INVITE 메시지에 대한 응답 시간입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.  <br/> |
|**ResponseCode** <br/> |int  <br/> |세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |세션 SIP 헤더에서 캡처된 진단 ID입니다.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |세션의 콘텐츠 형식입니다.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |세션에 대해 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.  <br/> |
|**풀** <br/> |nvarchar(256)  <br/> |세션에 대해 데이터를 캡처한 풀의 FQDN입니다.  <br/> |
|**MediationServer** <br/> |nvarchar(256)  <br/> |세션에 참가한 사용자가 사용한 중재 서버입니다.  <br/> |
|**게이트웨이** <br/> |nvarchar(256)  <br/> |세션에 참가한 사용자가 사용한 게이트웨이입니다.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |세션에 참가한 사용자가 사용한 에지 서버의 FQDN입니다.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |세션에 참가한 사용자의 특성을 나타냅니다. 허용된 특성 정의는 다음과 같습니다.  <br/> 0x01 - 데스크톱 전화와 통합됨  <br/> |
|**CallFlag** <br/> |smallint  <br/> |통화 특성을 나타냅니다. 허용된 특성 정의는 다음과 같습니다.  <br/> 0x01 - 다시 시도된 세션0  <br/> x02 - 응답 그룹을 대신하여 에이전트가 시작한 통화  <br/> |
   

