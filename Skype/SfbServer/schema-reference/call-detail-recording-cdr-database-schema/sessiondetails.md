---
title: SessionDetails 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: 각 레코드는 VoIP-VoIP 전화 통화, 두 사용자 간 IM 세션 또는 기타 유형의 세션일 수 있는 하나의 피어 투 피어 세션을 나타냅니다. Media 테이블과 함께 테이블 조인을 수행하여 이 세션에 관련된 각 미디어의 세부 정보를 찾을 수 있습니다.
ms.openlocfilehash: eb47c87be69bfc9308c8c641c54a2173ba2ed03eeae7f7543ce6a5cbb97f7092
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284488"
---
# <a name="sessiondetails-table"></a>SessionDetails 테이블
 
각 레코드는 VoIP-VoIP 전화 통화, 두 사용자 간 IM 세션 또는 기타 유형의 세션일 수 있는 하나의 피어 투 피어 세션을 나타냅니다. Media 테이블과 함께 테이블 조인을 [수행하여](media.md) 이 세션에 관련된 각 미디어의 세부 정보를 찾을 수 있습니다.
  
IsUser1IntegratedWithDeskPhone 및 IsUser2IntegratedWithDeskPhone 필드는 비즈니스용 Skype 서버 2015에서 사용된 SessionDetails 테이블에서 삭제됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary, Foreign  <br/> |세션 요청 시간입니다. **SessionIdSeq** 와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |세션을 식별하기 위한 ID 번호입니다. **SessionIdTime과** 함께 세션을 고유하게 식별하는 데 사용됩니다.* 자세한 내용은 비즈니스용 Skype 서버 [2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> ||여러 세션의 관계를 지정하기 위한 GUID입니다.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |외계인  <br/> |현재 세션으로 교체된 대화를 식별하기 위한 ID 번호입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |외계인  <br/> |세션을 식별하기 위한 ID 번호입니다. **ReplacesDialogIdTime** 과 함께 이 세션으로 교체된 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**User1Id** <br/> |int  <br/> |외계인  <br/> |세션에 포함된 한 사용자의 ID입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**User2Id** <br/> |int  <br/> |외계인  <br/> |세션에 포함된 다른 사용자의 ID입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||세션의 첫 번째 사용자가 사용한 끝점을 식별하는 GUID입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||세션의 두 번째 사용자가 사용한 끝점을 식별하는 GUID입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**TargetUserId** <br/> |int  <br/> |외계인  <br/> |SIP 요청에서 원래의 대상 사용자 URI입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하세요. <br/> |
|**SessionStartedById** <br/> |int  <br/> |외계인  <br/> |세션을 시작한 사용자의 ID입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |외계인  <br/> |발신자가 역할을 대신 수행하고 있는 원래 사용자의 ID를 나타냅니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**ReferredById** <br/> |int  <br/> |외계인  <br/> |통화를 참조한 사용자의 ID입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**ServerId** <br/> |int  <br/> |외계인  <br/> |이 세션에 사용된 프런트 엔드 서버의 ID입니다. 자세한 내용은 [Servers 테이블을](servers.md) 참조하십시오. <br/> |
|**PoolId** <br/> |int  <br/> |외계인  <br/> |세션이 캡처된 풀의 ID입니다. 자세한 내용은 [Pools 테이블을](pools.md) 참조하십시오. <br/> |
|**ContentTypeID** <br/> |int  <br/> |외계인  <br/> |세션에 사용된 콘텐츠 형식입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ContentTypes 테이블을](contenttypes.md) 참조하십시오. <br/> |
|**User1ClientVerId** <br/> |int  <br/> |외계인  <br/> |User1이 사용한 클라이언트 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ClientVersions](clientversions.md) 테이블을 참조하세요. <br/> |
|**User2ClientVerId** <br/> |int  <br/> |외계인  <br/> |User2가 사용한 클라이언트 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ClientVersions](clientversions.md) 테이블을 참조하세요. <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |외계인  <br/> |User1이 사용한 에지 서버입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 EdgeServers 테이블을](edgeservers.md) 참조하세요. <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |외계인  <br/> |User2가 사용한 에지 서버입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 EdgeServers 테이블을](edgeservers.md) 참조하세요. <br/> |
|**IsUser1Internal** <br/> |bit  <br/> ||User1이 내부로부터 로그온되었는지 여부입니다.  <br/> |
|**IsUser2Internal** <br/> |bit  <br/> ||User2가 내부로부터 로그온되었는지 여부입니다.  <br/> |
|**InviteTime** <br/> |datetime  <br/> ||첫 번째 INVITE 요청 시간입니다. 이 필드는 대개 세션의 초기 INVITE 메시지에서 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 이 필드가 첫 번째 해당 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜와 시간으로 채워집니다.  <br/> |
|**ResponseTime** <br/> |datetime  <br/> ||첫 번째 INVITE 메시지에 대한 응답 시간입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||SIP 헤더에서 캡처된 진단 ID입니다.  <br/> |
|**CallPriority** <br/> |int  <br/> |외계인  <br/> |통화 우선 순위입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 CallPriorities 테이블을](callpriorities.md) 참조하십시오. <br/> |
|**User1MessageCount** <br/> |int  <br/> ||세션 중 User1이 보낸 메시지 수입니다.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||세션 중 User2가 보낸 메시지 수입니다.  <br/> |
|**SessionEndTime** <br/> |datetime  <br/> ||세션 종료 시 시간입니다.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||이 세션의 미디어 유형을 나타내는 비트 집합입니다. 다음 유형의 정의가 나열됩니다.  <br/> 1- IM  <br/> 2- FILE_TRANSFER  <br/> 4- REMOTE_ASSISTANCE  <br/> 8- APP_SHARING  <br/> 16- 오디오  <br/> 32- 비디오  <br/> 64- APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||User1 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.  <br/> 0x01 - 데스크톱 전화와 통합됨  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||User2 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.  <br/> 0x01 - 데스크톱 전화와 통합됨  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||통화 특성을 나타내는 비트 집합입니다. 다음 특성 정의가 나열됩니다.  <br/> 0x01 - 다시 시도된 세션  <br/> 0x02 - 응답 그룹을 대신하여 에이전트가 시작한 통화  <br/> |
|**처리** <br/> |bit  <br/> ||모니터링 서비스의 내부 사용 용도  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||모니터링 서비스의 내부 사용 용도  <br/> 이 필드는 2015년 비즈니스용 Skype 서버 도입했습니다.  <br/> |
   
\* 대부분의 세션에서 SessionIdSeq의 값은 1입니다. 여러 세션이 정확히 동시에 시작될 경우 한 세션에 대한 SessionIdSeq가 1이 되고 다른 세션에 대해서는 2, 3, 4의 순서로 지정됩니다.
  

