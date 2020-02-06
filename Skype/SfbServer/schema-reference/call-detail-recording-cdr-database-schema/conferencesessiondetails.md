---
title: ConferenceSessionDetails 보기
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
ms.assetid: 5858c84d-baed-421d-ad1d-3726e150e256
description: ConferenceSessionDetails 보기는 단체 세션에 대 한 정보를 저장 합니다. 각 레코드는 하나의 회의 세션을 나타내며,이는 포커스가 있는 세션 또는 특정 회의 서버 세션 중 하나가 될 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 3dc345c10836a34f99baa4d6a088ab152b23427d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815336"
---
# <a name="conferencesessiondetails-view"></a>ConferenceSessionDetails 보기
 
ConferenceSessionDetails 보기는 단체 세션에 대 한 정보를 저장 합니다. 각 레코드는 하나의 회의 세션을 나타내며,이는 포커스가 있는 세션 또는 특정 회의 서버 세션 중 하나가 될 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**InviteTime** <br/> |dmtf  <br/> |첫 번째 초대 요청의 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |회의의 URI입니다.  <br/> |
|**ConferenceUriType** <br/> |nvarchar (256)  <br/> |회의 URI의 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**인스턴스** <br/> |uniqueidentifier  <br/> |되풀이 회의의 인스턴스를 구별 하는 식별자입니다. 각 되풀이 회의 인스턴스에는 동일한 ConferenceURI 있지만 다른 지 인 인스턴스 값이 있습니다.  <br/> |
|**McuConferenceUri** <br/> |nvarchar (450)  <br/> |회의 서버의 URI입니다.  <br/> |
|**McuConferenceUriType** <br/> |nvarchar (256)  <br/> |회의 서버 URI의 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |세션과 관련 된 사용자의 URI입니다.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |세션의 일부인 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**UserTenant 넌 트** <br/> |nvarchar (256)  <br/> |세션에 참가 하 고 있던 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> |세션의 일부인 사용자의 고유 식별자입니다.  <br/> |
|**EndTime** <br/> |dmtf  <br/> |세션 종료 시간입니다.  <br/> |
|**ConferenceClientVersion** <br/> |nvarchar (256)  <br/> |컨퍼런스 서버의 버전.  <br/> |
|**ConferenceClientType** <br/> |int  <br/> |회의 서버의 유형입니다. 자세한 내용은 [Useragentdef 테이블](useragentdef.md) 을 참조 하세요. <br/> |
|**ConferenceCategory** <br/> |nvarchar (64)  <br/> |회의 서버 범주.  <br/> |
|**UserClientVersion** <br/> |nvarchar (256)  <br/> |세션에 참가 한 사용자가 사용 하는 클라이언트 버전입니다.  <br/> |
|**UserClientType** <br/> |int  <br/> |세션에 참가 한 사용자가 사용 하는 클라이언트 자세한 내용은 [Useragentdef 테이블](useragentdef.md) 을 참조 하세요. <br/> |
|**UserClientCategory** <br/> |nvarchar (64)  <br/> |세션에 참가 한 사용자가 사용 하는 클라이언트 범주의 이름입니다.  <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |해당 세션이 시작 된 사용자의 URI입니다.  <br/> |
|**OnBehalfOfUriType** <br/> |nvarchar (256)  <br/> |세션이 시작 된 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar (256)  <br/> |세션이 시작 된 사용자를 대신해 서의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |세션을 참조 한 사용자의 URI입니다.  <br/> |
|**ReferredByUriType** <br/> |nvarchar (256)  <br/> |세션을 참조 한 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**ReferredByUriTenant** <br/> |nvarchar (256)  <br/> |세션을 참조 한 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**DialogId** <br/> |varstring (775)  <br/> |SIP 대화 상자 ID입니다. 형식은  <br/> :d ialog; from 태그; to 태그  <br/> |
|**ReplaceDialogIdTime** <br/> |dmtf  <br/> |현재 세션으로 대체 된 대화 상자를 식별 하는 ID 번호입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |세션을 식별 하는 ID 번호입니다. ReplaceDialogIdTime와 함께 사용 하 여이 세션으로 대체 되는 세션을 고유 하 게 식별 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**ReplacesDialogId** <br/> |varchar (775)  <br/> |세션에서 대체 하는 SIP 대화 상자 ID입니다. 의 형식은 다음과 같습니다.  <br/> 대화 상자; from 태그; 태그  <br/> |
|**IsStartedByConfServer** <br/> |다소  <br/> |회의 서버에 의해 세션이 시작 되었는지 여부를 나타냅니다.  <br/> |
|**Isen이상 By참여 서버** <br/> |다소  <br/> |회의 서버에 의해 세션이 종료 되었는지 여부를 나타냅니다.  <br/> |
|**IsUserInternal** <br/> |다소  <br/> |사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.  <br/> |
|**ResponseTime** <br/> |dmtf  <br/> |첫 번째 초대 메시지에 대 한 응답 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**ResponseCode** <br/> |int  <br/> |세션 초대에 대 한 SIP 응답 코드입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |세션 SIP 헤더에서 진단 ID를 캡처 했습니다.  <br/> |
|**ContentType** <br/> |nvarchar (256)  <br/> |세션의 콘텐츠 형식입니다.  <br/> |
|**FrontEnd** <br/> |nvarchar (256)  <br/> |세션에 대 한 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.  <br/> |
|**풀** <br/> |nvarchar (256)  <br/> |세션에 대 한 데이터를 캡처한 풀의 FQDN입니다.  <br/> |
|**MediationServer** <br/> |nvarchar (256)  <br/> |세션에 참가 한 사용자가 사용 하는 중재 서버입니다.  <br/> |
|**게이트웨이와** <br/> |nvarchar (256)  <br/> |세션에 참가 한 사용자가 사용 하는 게이트웨이  <br/> |
|**EdgeServer** <br/> |nvarchar (256)  <br/> |세션에 참가 한 사용자가 사용 하는 Edge 서버의 FQDN입니다.  <br/> |
|**UserFlag** <br/> |smallint  <br/> |세션에 참가 한 사용자의 특성을 나타냅니다. 허용 되는 특성 정의는 다음과 같습니다.  <br/> 0x01-데스크톱 전화와 통합  <br/> |
|**CallFlag** <br/> |smallint  <br/> |통화 특성을 나타냅니다. 다음과 같은 특성 정의가 허용 됩니다.  <br/> 0x01-재시도 Session0  <br/> x02-응답 그룹을 대신 하 여 상담원이 수행한 통화입니다.  <br/> |
   

