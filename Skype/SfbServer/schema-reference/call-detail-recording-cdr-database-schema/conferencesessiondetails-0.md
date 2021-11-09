---
title: 2015년 비즈니스용 Skype 서버 ConferenceSessionDetails 테이블
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
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: 각 레코드는 Focus를 가진 세션이거나, 특정 회의 서버를 가진 세션일 수 있는 하나의 회의 세션을 나타냅니다.
ms.openlocfilehash: fc69150cf95ca0f00a4c1731aeda44f1e674a6cd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843671"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 ConferenceSessionDetails 테이블
 
각 레코드는 Focus를 가진 세션이거나, 특정 회의 서버를 가진 세션일 수 있는 하나의 회의 세션을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Datetime  <br/> |Primary, Foreign  <br/> |세션 요청 시간 세션 세션을 고유하게 식별하기 위해 **SessionIdSeq와** 함께 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |세션을 식별하기 위한 ID 번호입니다. **SessionIdTime과** 함께 회의 세션을 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |외계인  <br/> |이 세션과 관련된 회의 센터 회의 URI입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ConferenceUris 테이블을](conferenceuris.md) 참조하세요. 이 URI는 회의 센터 기반 회의 URI입니다. <br/> |
|**ConfInstance** <br/> |uniqueIdentifier  <br/> ||반복해서 수행되는 회의를 구분하는 식별자입니다. 반복되는 각 회의 인스턴스는 동일한 ConferenceURI를 갖지만 ConfInstance 값이 다릅니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |외계인  <br/> |이 세션과 관련된 회의 서버 회의 URI입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ConferenceUris 테이블을](conferenceuris.md) 참조하세요. 이 URI는 회의 서버 기반 회의 URI입니다. 회의 센터 회의 세션의 경우 이 열은 Null입니다. <br/> |
|**UserId** <br/> |int  <br/> |외계인  <br/> |회의 세션에 있는 한 사용자의 ID입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||끝점 인스턴스를 식별하기 위한 GUID입니다. 예를 들어 한 사용자가 동일 계정을 사용하여 여러 컴퓨터에 로그온하면 각 컴퓨터가 서로 다른 끝점 ID를 갖습니다.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |외계인  <br/> |발신자가 역할을 대신 수행하고 있는 원래 사용자의 ID를 나타냅니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**ReferredById** <br/> |int  <br/> |외계인  <br/> |통화를 참조한 사용자의 ID입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**UserClientVersionId** <br/> |int  <br/> |외계인  <br/> |회의 사용자가 사용한 클라이언트 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ClientVersions](clientversions.md) 테이블을 참조하세요. <br/> |
|**ConfClientVersionId** <br/> |int  <br/> |외계인  <br/> |회의 서버가 사용한 클라이언트 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ClientVersions](clientversions.md) 테이블을 참조하세요. <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |외계인  <br/> |현재 세션으로 교체된 대화를 식별하기 위한 ID 번호입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |외계인  <br/> |세션을 식별하기 위한 ID 번호입니다. **ReplacesDialogIdTime** 과 함께 이 세션으로 교체된 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**IsStartedByConfServer** <br/> |bit  <br/> ||세션이 회의 서버에서 시작되었는지 여부를 나타냅니다.  <br/> |
|**IsEndedByConfServer** <br/> |bit  <br/> ||세션이 회의 서버에서 종료되었는지 여부를 나타냅니다.  <br/> |
|**IsUserInternal** <br/> |bit  <br/> ||사용자가 내부로부터 로그온되었는지 여부입니다.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||세션 초대에 대한 SIP(Session Initiation Protocol) 응답 코드입니다. 이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||SIP 헤더에서 캡처된 진단 ID입니다.  <br/> |
|**ServerId** <br/> |int  <br/> |외계인  <br/> |이 세션에 사용된 프런트 엔드 서버의 ID입니다. 자세한 내용은 [Servers 테이블을](servers.md) 참조하십시오. <br/> |
|**PoolId** <br/> |int  <br/> |외계인  <br/> |세션이 캡처된 풀의 ID입니다. 자세한 내용은 [Pools 테이블을](pools.md) 참조하십시오. <br/> |
|**MediationServerId** <br/> |int  <br/> |외계인  <br/> |통화를 사용 중인 중재 서버입니다. 자세한 내용은 [MediationServers 테이블을](mediationservers.md) 참조하세요. <br/> |
|**GatewayId** <br/> |int  <br/> |외계인  <br/> |통화를 사용 중인 게이트웨이입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Gateways](gateways.md) 테이블을 참조하십시오. <br/> |
|**EdgeServerId** <br/> |int  <br/> |외계인  <br/> |통화를 사용 중인 에지 서버입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 EdgeServers 테이블을](edgeservers.md) 참조하세요. <br/> |
|**ContentTypeId** <br/> |int  <br/> |외계인  <br/> |세션에 사용된 콘텐츠 형식입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ContentTypes 테이블을](contenttypes.md) 참조하십시오. <br/> |
|**InviteTime** <br/> |datetime  <br/> ||첫 번째 INVITE 요청 시간입니다. 이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 이 필드가 첫 번째 해당 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜와 시간으로 채워집니다.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||첫 번째 SIP RESPONSE 시간입니다. 이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 이 필드가 첫 번째 해당 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜와 시간으로 채워집니다.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||세션이 종료된 시간입니다.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |외계인  <br/> |[UriTypes 테이블의](uritypes.md)MCU URI 형식 값을 포함 이 필드는 쿼리 성능을 높이기 위해 사용됩니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || 사용자 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다. <br/>  일반 전화기와 통합됨 - 1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || 통화 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다. <br/>  다시 시도된 세션 - 1 <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||모니터링 서비스의 내부 사용 용도  <br/> 이 필드는 2015년 비즈니스용 Skype 서버 도입했습니다.  <br/> |
   
\* 대부분의 세션에서 SessionIdSeq의 값은 1입니다. 여러 세션이 정확히 동시에 시작될 경우 한 세션에 대한 SessionIdSeq가 1이 되고 다른 세션에 대해서는 2, 3, 4의 순서로 지정됩니다.
  

