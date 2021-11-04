---
title: SessionDetails 보기
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
description: SessionDetails 보기에는 피어 투 피어 세션에 대한 정보가 저장됩니다. 이 세션은 VoIP-VoIP 전화 통화, 두 사용자 IM 세션 또는 다른 유형의 세션일 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 5a278960912ac38dc75fe398e3d75de710785800
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767456"
---
# <a name="sessiondetails-view"></a>SessionDetails 보기
 
SessionDetails 보기에는 피어 투 피어 세션에 대한 정보가 저장됩니다. 이 세션은 VoIP-VoIP 전화 통화, 두 사용자 IM 세션 또는 다른 유형의 세션일 수 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |세션 요청 시간입니다. SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 Table의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |세션을 식별하기 위한 ID 번호입니다. SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**InviteTime** <br/> |datetime  <br/> |첫 번째 INVITE 요청의 시간입니다. 이 필드는 일반적으로 세션의 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.  <br/> |
|**FromUri** <br/> |nvarchar(450)  <br/> |세션을 시작한 사용자의 URI입니다.  <br/> |
|**ToUri** <br/> |nvarchar(450)  <br/> |세션에 참가한 사용자의 URI입니다.  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |세션을 시작한 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |세션에 참가한 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**FromTenant** <br/> |nvarchar(450)  <br/> |세션을 시작한 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |세션에 참가한 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**FromEndpointId** <br/> |uniqueidentifier  <br/> |세션을 시작한 사용자의 끝점 고유 식별자입니다.  <br/> |
|**ToEndpointId** <br/> |uniqueidentifier  <br/> |세션에 참가한 사용자의 끝점에 대한 고유 식별자입니다.  <br/> |
|**EndTime** <br/> |datetime  <br/> |세션 종료 시간입니다.  <br/> |
|**FromMessageCount** <br/> |int  <br/> |세션을 시작한 사용자가 보낸 메시지 수입니다.  <br/> |
|**ToMessageCount** <br/> |int  <br/> |세션에 참가한 사용자가 보낸 메시지 수입니다.  <br/> |
|**FromClientVersion** <br/> |nvarchar(256)  <br/> |세션을 시작한 사용자가 사용한 클라이언트 버전입니다.  <br/> |
|**FromClientType** <br/> |int  <br/> |세션을 시작한 사용자가 사용한 클라이언트입니다. 자세한 내용은 [UserAgentDef 테이블을](useragentdef.md) 참조합니다. <br/> |
|**FromClientCategory** <br/> |nvarchar(64)  <br/> |세션을 시작한 사용자가 사용한 클라이언트 범주의 이름입니다.  <br/> |
|**ToClientVersion** <br/> |nvarchar(256)  <br/> |세션에 참가한 사용자가 사용한 클라이언트 버전  <br/> |
|**ToClientType** <br/> |int  <br/> |세션에 참가한 사용자가 사용한 클라이언트입니다. 자세한 내용은 [UserAgentDef 테이블을](useragentdef.md) 참조합니다. <br/> |
|**ToClientCategory** <br/> |nvarchar(64)  <br/> |세션에 참가한 사용자가 사용한 클라이언트 범주의 이름입니다.  <br/> |
|**TargetUri** <br/> |nvarchar(450)  <br/> |세션의 대상 사용자의 URI입니다.  <br/> |
|**TargetUriType** <br/> |nvarchar(450)  <br/> |세션에 대한 대상 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**OnBehalfOfUri** <br/> |nvarchar(450)  <br/> |세션을 대신 시작한 사용자의 URI입니다.  <br/> |
|**OnnnBehalfOfUriType** <br/> |nvarchar(256)  <br/> |세션을 대신 시작한 사용자 URI의 형식입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**OnBehalfOfTenant** <br/> |nvarchar(256)  <br/> |세션을 대신 시작한 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**ReferredByUri** <br/> |nvarchar(450)  <br/> |세션을 참조한 사용자의 URI입니다.  <br/> |
|**ReferredByUriType** <br/> |nvarchar(256)  <br/> |세션을 참조한 사용자 URI의 형식입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**ReferredByTenant** <br/> |nvarchar(256)  <br/> |세션을 참조한 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |SIP 대화 ID입니다. 형식:  <br/> dialog;from-tag;to-tag  <br/> |
|**CorrelationId** <br/> |uniqueidentifier  <br/> |여러 세션의 상관 관계에 사용되는 GUID입니다.  <br/> |
|**ReplaceDialogIdTime** <br/> |datetime  <br/> |세션으로 대체된 대화 상자의 시간입니다. ReplaceDialogIdSeq와 함께 세션으로 대체된 대화 상자를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**ReplaceDialogIdSeq** <br/> |int  <br/> |세션을 식별하기 위한 ID 번호입니다. ReplaceDialogIdTime과 함께 세션으로 대체된 대화 상자를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**ReplacesDialogId** <br/> |varchar(775)  <br/> |세션이 교체하는 SIP 대화 ID입니다. 형식:  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseTime** <br/> |datetime  <br/> |첫 번째 INVITE 메시지에 대한 응답 시간입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.  <br/> |
|**ResponseCode** <br/> |int  <br/> |세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |SIP 헤더에서 캡처된 진단 ID입니다.  <br/> |
|**ContentType** <br/> |nvarchar(256)  <br/> |세션의 콘텐츠 형식입니다.  <br/> |
|**FrontEnd** <br/> |nvarchar(256)  <br/> |세션에 대해 데이터를 캡처한 프런트 엔드 서버의 FQDN입니다.  <br/> |
|**풀** <br/> |nvarchar(256)  <br/> |세션에 대해 데이터를 캡처한 풀의 FQDN입니다.  <br/> |
|**FromEdgeServer** <br/> |nvarchar(256)  <br/> |세션을 시작한 사용자가 사용한 에지 서버의 FQDN입니다.  <br/> |
|**ToEdgeServer** <br/> |nvarchar(256)  <br/> |세션을 시작한 사용자가 사용한 에지 서버의 FQDN  <br/> |
|**IsFromInternal** <br/> |bit  <br/> |세션을 시작한 사용자가 내부 네트워크에서 로그온한 상태인지 여부를 나타냅니다.  <br/> |
|**IsToInternal** <br/> |bit  <br/> |세션에 참가한 사용자가 내부 네트워크에서 로그온되어 있는지 여부를 나타냅니다.  <br/> |
|**CallPriority** <br/> |nvarchar(256)  <br/> |세션의 통화 우선 순위입니다.  <br/> |
|**FromUserFlag** <br/> |smallint  <br/> |세션을 시작한 사용자의 특성을 나타냅니다. 허용된 특성 정의는 다음과 같습니다.  <br/> 0x01 - 데스크톱 전화와 통합됨  <br/> |
|**ToUserFlag** <br/> |smallint  <br/> |세션을 시작한 사용자의 특성을 나타냅니다. 허용된 특성 정의는 다음과 같습니다.  <br/> 0x01 - 데스크톱 전화와 통합됨  <br/> |
|**CallFlag** <br/> |smallint  <br/> |통화 특성을 나타냅니다. 허용된 특성 정의는 다음과 같습니다.  <br/> 0x01 - 다시 시도된 세션  <br/> 0x02 - 응답 그룹을 대신하여 에이전트가 한 통화  <br/> |
|**위치** <br/> |varchar(max)  <br/> |응급 통화의 위치입니다.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> |모니터링 서비스의 내부 사용 용도  <br/> 이 필드는 2015년 비즈니스용 Skype 서버 도입했습니다.  <br/> |
   

