---
title: 비즈니스용 Skype 서버 2015의 ConferenceSessionDetails 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
description: 각 레코드는 하나의 회의 세션을 나타내며,이는 포커스가 있는 세션 또는 특정 회의 서버 세션 중 하나가 될 수 있습니다.
ms.openlocfilehash: 40216d159c9d52dcf8c22f7fe7b915255ed0f741
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196776"
---
# <a name="conferencesessiondetails-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 ConferenceSessionDetails 테이블
 
각 레코드는 하나의 회의 세션을 나타내며,이는 포커스가 있는 세션 또는 특정 회의 서버 세션 중 하나가 될 수 있습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |Dmtf  <br/> |기본, 외래  <br/> |세션 요청 시간 회의 세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |기본, 외래  <br/> |세션을 식별 하는 ID 번호입니다. 회의 세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |외부  <br/> |이 세션과 관련 된 포커스 회의 URI입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 ConferenceUris 테이블](conferenceuris.md) 을 참조 하세요. 이 URI는 포커스 기반 전화 회의 URI입니다. <br/> |
|**인스턴스** <br/> |uniqueIdentifier  <br/> ||되풀이 회의의 인스턴스를 구별 하는 식별자입니다. 각 되풀이 회의 인스턴스에는 동일한 ConferenceURI 있지만 다른 지 인 인스턴스 값이 있습니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**McuConferenceUriId** <br/> |int  <br/> |외부  <br/> |이 세션과 관련 된 회의 서버 컨퍼런스 URI입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 ConferenceUris 테이블](conferenceuris.md) 을 참조 하세요. 이 URI는 회의 서버 기반 전화 회의 URI입니다. 포커스 회의 세션의 경우이 열은 null입니다. <br/> |
|**UserId** <br/> |int  <br/> |외부  <br/> |회의 세션의 한 사용자의 ID입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**UserEndpointId** <br/> |uniqueidentifier  <br/> ||끝점의 인스턴스를 식별 하는 GUID입니다. 예를 들어 한 사용자가 동일한 계정을 사용 하 여 다른 컴퓨터에 로그온 하는 경우 각 컴퓨터에는 서로 다른 끝점 ID가 부여 됩니다.  <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |외부  <br/> |호출자가 대신 하는 사용자의 ID를 나타냅니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**ReferredById** <br/> |int  <br/> |외부  <br/> |통화를 참조 하는 사용자의 ID입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**UserClientVersionId** <br/> |int  <br/> |외부  <br/> |컨퍼런스 사용자가 클라이언트 버전을 사용 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Clientversions 테이블](clientversions.md) 을 참조 하세요. <br/> |
|**해당 클라이언트** <br/> |int  <br/> |외부  <br/> |회의 서버에서 사용 하는 클라이언트 버전. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Clientversions 테이블](clientversions.md) 을 참조 하세요. <br/> |
|**ReplaceDialogIdTime** <br/> |dmtf  <br/> |외부  <br/> |현재 세션으로 대체 된 대화 상자를 식별 하는 ID 번호입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |외부  <br/> |세션을 식별 하는 ID 번호입니다. **ReplacesDialogIdTime** 와 함께 사용 하 여이 세션으로 대체 되는 세션을 고유 하 게 식별 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**IsStartedByConfServer** <br/> |다소  <br/> ||회의 서버에서 세션을 시작 했음을 나타냅니다.  <br/> |
|**Isen이상 By참여 서버** <br/> |다소  <br/> ||회의 서버에서 세션을 종료 했음을 나타냅니다.  <br/> |
|**IsUserInternal** <br/> |다소  <br/> ||사용자가 내부에서 로그온 되었는지 여부  <br/> |
|**ResponseCode** <br/> |int  <br/> ||세션 초대에 대 한 SIP (세션 초기화 프로토콜) 응답 코드 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||SIP 헤더에서 진단 ID를 캡처 했습니다.  <br/> |
|**ServerId** <br/> |int  <br/> |외부  <br/> |이 세션에 사용 되는 프런트 엔드 서버의 ID입니다. 자세한 내용은 [서버 테이블](servers.md) 을 참조 하세요. <br/> |
|**PoolId** <br/> |int  <br/> |외부  <br/> |세션이 캡처된 풀의 ID입니다. 자세한 내용은 [풀 테이블](pools.md) 을 참조 하세요. <br/> |
|**MediationServerId** <br/> |int  <br/> |외부  <br/> |통화에서 사용 중인 중재 서버입니다. 자세한 내용은 [Mediationservers 테이블](mediationservers.md) 을 참조 하세요. <br/> |
|**GatewayId** <br/> |int  <br/> |외부  <br/> |통화에서 사용 중인 게이트웨이 자세한 내용은 [비즈니스용 Skype 서버 2015의 게이트웨이 테이블](gateways.md) 을 참조 하세요. <br/> |
|**EdgeServerId** <br/> |int  <br/> |외부  <br/> |통화에서 사용 중인 Edge 서버입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 EdgeServers 테이블](edgeservers.md) 을 참조 하세요. <br/> |
|**ContentTypeId** <br/> |int  <br/> |외부  <br/> |세션에 사용 되는 콘텐츠 형식입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Contenttypes 테이블](contenttypes.md) 을 참조 하세요. <br/> |
|**InviteTime** <br/> |dmtf  <br/> ||첫 번째 초대 요청 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**ResponseTime** <br/> |dmtf  <br/> ||첫 번째 SIP 응답의 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**SessionEndTime** <br/> |dmtf  <br/> ||세션이 종료 된 시간입니다.  <br/> |
|**UriTypeId** <br/> |tinyint  <br/> |외부  <br/> |[UriTypes 테이블](uritypes.md)의 MCU URI 유형 값을 포함 합니다. 이 필드는 쿼리 성능을 개선 하는 데 사용 됩니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**UserFlag** <br/> |smallint  <br/> || 사용자 특성을 나타내는 비트 집합입니다. 다음과 같은 특성 정의가 나열 됩니다. <br/>  데스크톱 전화번호와 통합-1 <br/> |
|**CallFlag** <br/> |smallint  <br/> || 통화 특성을 나타내는 비트 집합입니다. 다음과 같은 특성 정의가 나열 됩니다. <br/>  다시 시도 된 세션-1 <br/> |
|**LastModifiedTime** <br/> |Dmtf  <br/> ||모니터링 서비스에 내부적으로 사용 합니다.  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.  <br/> |
   
\*대부분의 세션에서 SessionIdSeq에는 값 1이 사용 됩니다. 정확히 동시에 여러 세션을 시작 하는 경우 1에 대 한 SessionIdSeq는 1이 되 고 다른 하나는 2가 됩니다.
  

