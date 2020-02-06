---
title: SessionDetails 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
description: 각 레코드는 하나의 피어 투 피어 세션을 나타내며,이는 VoIP 전화 통화, 2-파티 IM 세션 또는 기타 세션 유형이 될 수 있습니다. 미디어 테이블과 함께 테이블 조인을 수행 하 여이 세션과 관련 된 각 미디어의 세부 정보를 찾을 수 있습니다.
ms.openlocfilehash: 1a211598e7771c5637af191f19ad2926e3cc803e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814906"
---
# <a name="sessiondetails-table"></a>SessionDetails 테이블
 
각 레코드는 하나의 피어 투 피어 세션을 나타내며,이는 VoIP 전화 통화, 2-파티 IM 세션 또는 기타 세션 유형이 될 수 있습니다. [미디어 테이블과](media.md) 함께 테이블 조인을 수행 하 여이 세션과 관련 된 각 미디어의 세부 정보를 찾을 수 있습니다.
  
IsUser1IntegratedWithDeskPhone 및 IsUser2IntegratedWithDeskPhone 필드는 비즈니스용 Skype 서버 2015에서 사용 되는 SessionDetails 테이블에서 삭제 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |기본, 외래  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |기본, 외래  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. * 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs 테이블](dialogs.md) 을 참조 하세요. <br/> |
|**Legredir** <br/> |uniqueidentifier  <br/> ||여러 세션을 연관 시킬 GUID입니다.  <br/> |
|**ReplaceDialogIdTime** <br/> |dmtf  <br/> |외부  <br/> |현재 세션으로 대체 된 대화 상자를 식별 하는 ID 번호입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |외부  <br/> |세션을 식별 하는 ID 번호입니다. **ReplacesDialogIdTime** 와 함께 사용 하 여이 세션으로 대체 되는 세션을 고유 하 게 식별 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**User1Id** <br/> |int  <br/> |외부  <br/> |세션의 한 사용자의 ID입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**User2Id** <br/> |int  <br/> |외부  <br/> |세션의 다른 사용자에 대 한 ID입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**User1EndpointId** <br/> |uniqueIdentifier  <br/> ||세션에서 첫 번째 사용자가 사용 하는 끝점을 식별 하는 GUID입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**User2EndpointId** <br/> |uniqueIdentifier  <br/> ||세션에서 두 번째 사용자가 사용 하는 끝점을 식별 하는 GUID입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**TargetUserId** <br/> |int  <br/> |외부  <br/> |SIP 요청의 원본에서 사용자 URI입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**SessionStartedById** <br/> |int  <br/> |외부  <br/> |세션을 시작한 사용자의 ID입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**OnBehalfOfId** <br/> |int  <br/> |외부  <br/> |호출자가 대신 하는 사용자의 ID를 나타냅니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**ReferredById** <br/> |int  <br/> |외부  <br/> |통화를 참조 하는 사용자의 ID입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**ServerId** <br/> |int  <br/> |외부  <br/> |이 세션에 사용 되는 프런트 엔드 서버의 ID입니다. 자세한 내용은 [서버 테이블](servers.md) 을 참조 하세요. <br/> |
|**PoolId** <br/> |int  <br/> |외부  <br/> |세션이 캡처된 풀의 ID입니다. 자세한 내용은 [풀 테이블](pools.md) 을 참조 하세요. <br/> |
|**ContentTypeID** <br/> |int  <br/> |외부  <br/> |세션에 사용 되는 콘텐츠 형식입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Contenttypes 테이블](contenttypes.md) 을 참조 하세요. <br/> |
|**User1ClientVerId** <br/> |int  <br/> |외부  <br/> |User1이 사용 하는 클라이언트 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Clientversions 테이블](clientversions.md) 을 참조 하세요. <br/> |
|**User2ClientVerId** <br/> |int  <br/> |외부  <br/> |%2에서 사용 하는 클라이언트 버전. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Clientversions 테이블](clientversions.md) 을 참조 하세요. <br/> |
|**User1EdgeServerid** <br/> |int  <br/> |외부  <br/> |User1이 사용 하는 Edge 서버입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 EdgeServers 테이블](edgeservers.md) 을 참조 하세요. <br/> |
|**User2EdgeServerid** <br/> |int  <br/> |외부  <br/> |%2에서 사용 하는 Edge 서버입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 EdgeServers 테이블](edgeservers.md) 을 참조 하세요. <br/> |
|**IsUser1Internal** <br/> |다소  <br/> ||User1이 내부에서 로그온 되었는지 여부  <br/> |
|**IsUser2Internal** <br/> |다소  <br/> ||%2이 (가) 내부에서 로그온 되었는지 여부  <br/> |
|**InviteTime** <br/> |dmtf  <br/> ||첫 번째 초대 요청 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**ResponseTime** <br/> |dmtf  <br/> ||첫 번째 초대 메시지에 대 한 응답 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||세션 초대에 대 한 SIP 응답 코드입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||SIP 헤더에서 진단 ID를 캡처 했습니다.  <br/> |
|**CallPriority** <br/> |int  <br/> |외부  <br/> |통화 우선 순위. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Callpriorities 순위 표](callpriorities.md) 를 참조 하세요. <br/> |
|**User1MessageCount** <br/> |int  <br/> ||세션 중에 User1이 보낸 메시지 수입니다.  <br/> |
|**User2MessageCount** <br/> |int  <br/> ||세션 중에 %2이 (가) 보낸 메시지 수입니다.  <br/> |
|**SessionEndTime** <br/> |dmtf  <br/> ||세션이 종료 되는 시간입니다.  <br/> |
|**MediaTypes** <br/> |int  <br/> ||이 세션의 미디어 유형을 나타내는 비트 집합입니다. 다음은 형식에 대 한 정의입니다.  <br/> 1-메신저  <br/> 2-FILE_TRANSFER  <br/> 4-REMOTE_ASSISTANCE  <br/> 8 APP_SHARING  <br/> 16-오디오  <br/> 32-영상  <br/> 64-APP_INVITE  <br/> |
|**User1Flag** <br/> |smallint  <br/> ||User1 특성을 나타내는 비트 집합입니다. 다음과 같은 특성 정의가 나열 됩니다.  <br/> 0x01-데스크톱 전화와 통합  <br/> |
|**User2Flag** <br/> |smallint  <br/> ||지 속성 특성을 나타내는 비트 집합입니다. 다음과 같은 특성 정의가 나열 됩니다.  <br/> 0x01-데스크톱 전화와 통합  <br/> |
|**CallFlag** <br/> |smallint  <br/> ||통화 특성을 나타내는 비트 집합입니다. 다음과 같은 특성 정의가 나열 됩니다.  <br/> 0x01-재시도 하는 세션  <br/> 0x02-응답 그룹을 대신 하 여 상담원이 수행한 A 통화  <br/> |
|**처리** <br/> |다소  <br/> ||모니터링 서비스에 내부적으로 사용 합니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**LastModifiedTime** <br/> |Dmtf  <br/> ||모니터링 서비스에 내부적으로 사용 합니다.  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.  <br/> |
   
\*대부분의 세션에서 SessionIdSeq에는 값 1이 사용 됩니다. 정확히 동시에 여러 세션을 시작 하는 경우 1에 대 한 SessionIdSeq는 1이 되 고 다른 하나는 2가 됩니다.
  

