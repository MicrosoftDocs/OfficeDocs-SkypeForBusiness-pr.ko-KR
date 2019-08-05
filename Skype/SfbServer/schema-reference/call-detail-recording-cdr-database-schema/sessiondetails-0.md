---
title: SessionDetails 뷰
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: SessionDetails view는 피어 투 피어 세션에 대 한 정보를 저장 하는데,이는 VoIP 전화 통화, 2-파티 IM 세션 또는 기타 세션 유형이 될 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 627d038389098583b5e42f73e8dd0a1cc339d014
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196692"
---
# <a name="sessiondetails-view"></a>SessionDetails 뷰
 
SessionDetails view는 피어 투 피어 세션에 대 한 정보를 저장 하는데,이는 VoIP 전화 통화, 2-파티 IM 세션 또는 기타 세션 유형이 될 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015 테이블의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**InviteTime** <br/> |dmtf  <br/> |첫 번째 초대 요청의 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |세션을 시작한 사용자의 URI입니다.  <br/> |
|**ToUri** <br/> |nvarchar (450)  <br/> |세션에 참가 한 사용자의 URI입니다.  <br/> |
|**Fromurit** <br/> |nvarchar (256)  <br/> |세션을 시작한 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**ToUriType** <br/> |nvarchar (256)  <br/> |세션에 참가 한 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**FromTenant** <br/> |nvarchar (450)  <br/> |세션을 시작한 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**ToTenant 넌 트** <br/> |nvarchar (256)  <br/> |세션에 참가 한 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |세션을 시작한 사용자의 끝점에 대 한 고유 식별자입니다.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |세션에 참가 한 사용자의 끝점에 대 한 고유 식별자입니다.  <br/> |
|**EndTime** <br/> |dmtf  <br/> |세션 종료 시간입니다.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |세션을 시작한 사용자가 보낸 메시지 수입니다.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |세션에 참가 한 사용자가 보낸 메시지 수입니다.  <br/> |
|**FromClientVersion** <br/> |nvarchar (256)  <br/> |세션을 시작한 사용자가 사용 하는 클라이언트 버전입니다.  <br/> |
|**FromClientType** <br/> |int  <br/> |세션을 시작한 사용자가 사용 하는 클라이언트입니다. 자세한 내용은 [Useragentdef 테이블](useragentdef.md) 을 참조 하세요. <br/> |
|**FromClientCategory** <br/> |nvarchar (64)  <br/> |세션을 시작한 사용자가 사용 하는 클라이언트 범주의 이름입니다.  <br/> |
|**ToClientVersion** <br/> |nvarchar (256)  <br/> |세션에 참가 한 사용자가 사용 하는 클라이언트 버전  <br/> |
|**ToClientType** <br/> |int  <br/> |세션에 참가 한 사용자가 사용 하는 클라이언트입니다. 자세한 내용은 [Useragentdef 테이블](useragentdef.md) 을 참조 하세요. <br/> |
|**ToClientCategory** <br/> |nvarchar (64)  <br/> |세션에 참가 한 사용자가 사용 하는 클라이언트 범주의 이름입니다.  <br/> |
|**TargetUri** <br/> |nvarchar (450)  <br/> |세션의 대상 사용자의 URI입니다.  <br/> |
|**TargetUriType** <br/> |nvarchar (450)  <br/> |세션에 대 한 대상 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**OnBehalfOfUri** <br/> |nvarchar (450)  <br/> |해당 세션이 시작 된 사용자의 URI입니다.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar (256)  <br/> |세션이 시작 된 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar (256)  <br/> |세션이 시작 된 사용자를 대신해 서의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**ReferredByUri** <br/> |nvarchar (450)  <br/> |세션을 참조 한 사용자의 URI입니다.  <br/> |
|**ReferredByUriType** <br/> |nvarchar (256)  <br/> |세션을 참조 한 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**ReferredByTenant** <br/> |nvarchar (256)  <br/> |세션을 참조 한 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**DialogId** <br/> |varchar (775)  <br/> |SIP 대화 상자 ID입니다. 형식은 다음과 같습니다.  <br/> 대화 상자; from 태그; 태그  <br/> |
|**Legredir** <br/> |uniqueidentifier  <br/> |여러 세션의 연관성을 위해 사용 되는 GUID입니다.  <br/> |
|**ReplaceDialogIdTime** <br/> |dmtf  <br/> |세션으로 대체 된 대화의 시간입니다. ReplaceDialogIdSeq와 함께 사용 하 여 세션으로 대체 되는 대화를 고유 하 게 식별 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |세션을 식별 하는 ID 번호입니다. ReplaceDialogIdTime와 함께 사용 하 여 세션으로 대체 되는 대화를 고유 하 게 식별 합니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**ReplacesDialogId** <br/> |varchar (775)  <br/> |세션에서 대체 하는 SIP 대화 상자 ID입니다. 형식은 다음과 같습니다.  <br/> 대화 상자; from 태그; 태그  <br/> |
|**ResponseTime** <br/> |dmtf  <br/> |첫 번째 초대 메시지에 대 한 응답 시간입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**ResponseCode** <br/> |int  <br/> |세션 초대에 대 한 SIP 응답 코드입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |SIP 헤더에서 진단 ID를 캡처 했습니다.  <br/> |
|**ContentType** <br/> |nvarchar (256)  <br/> |세션의 콘텐츠 유형입니다.  <br/> |
|**프런트** <br/> |nvarchar (256)  <br/> |세션에 대 한 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.  <br/> |
|**수영장** <br/> |nvarchar (256)  <br/> |세션에 대 한 데이터를 캡처한 풀의 FQDN입니다.  <br/> |
|**FromEdgeServer** <br/> |nvarchar (256)  <br/> |세션을 시작한 사용자가 사용 하는 Edge 서버의 FQDN입니다.  <br/> |
|**ToEdgeServer** <br/> |nvarchar (256)  <br/> |세션을 시작한 사용자가 사용 하는 Edge 서버의 FQDN  <br/> |
|**IsFromInternal** <br/> |다소  <br/> |세션을 시작한 사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.  <br/> |
|**IsToInternal** <br/> |다소  <br/> |세션에 참가 한 사용자가 내부 네트워크에서 로그온 되었는지 여부를 나타냅니다.  <br/> |
|**CallPriority** <br/> |nvarchar (256)  <br/> |세션의 호출 우선 순위입니다.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |세션을 시작한 사용자의 특성을 나타냅니다. 다음과 같은 특성 정의가 허용 됩니다.  <br/> 0x01-데스크톱 전화와 통합  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |세션을 시작한 사용자의 특성을 나타냅니다. 다음과 같은 특성 정의가 허용 됩니다.  <br/> 0x01-데스크톱 전화와 통합  <br/> |
|**CallFlag** <br/> |smallint  <br/> |통화 특성을 나타냅니다. 다음과 같은 특성 정의가 허용 됩니다.  <br/> 0x01-재시도 하는 세션  <br/> 0x02-응답 그룹을 대신 하 여 상담원이 수행한 A 통화  <br/> |
|**위치** <br/> |varchar (max)  <br/> |비상 전화의 위치입니다.  <br/> |
|**LastModifiedTime** <br/> |Dmtf  <br/> |모니터링 서비스에 내부적으로 사용 합니다.  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.  <br/> |
   

