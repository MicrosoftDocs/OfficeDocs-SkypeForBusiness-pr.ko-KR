---
title: Registration 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 각 레코드는 하나의 사용자 등록 이벤트를 나타냅니다.
ms.openlocfilehash: 7dcf96c5cb5b140711590943eb7ae5d2be8704b4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196697"
---
# <a name="registration-table"></a>Registration 테이블
 
각 레코드는 하나의 사용자 등록 이벤트를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |기본, 외래  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |기본, 외래  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**UserId** <br/> |int  <br/> |외부  <br/> |사용자 ID입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||등록 끝점을 식별 하는 GUID입니다. 일반적으로 같은 사용자의 동일한 컴퓨터의 register 이벤트는 동일한 끝점 ID를 갖습니다. 다른 컴퓨터에는 다른 끝점 ID가 있습니다.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||같은 사용자 및 같은 끝점과 관련 된 등록을 구분 하는 데 사용 되는 ID입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |외부  <br/> |현재 사용자의 클라이언트 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Clientversions 테이블](clientversions.md) 을 참조 하세요. <br/> |
|**RegistrarId** <br/> |int  <br/> |외부  <br/> |등록에 사용 되는 등록자 서버의 ID입니다. 자세한 내용은 [서버 테이블](servers.md) 을 참조 하세요. <br/> |
|**PoolId** <br/> |int  <br/> |외부  <br/> |세션이 캡처된 풀의 ID입니다. 자세한 내용은 [풀 테이블](pools.md) 을 참조 하세요. <br/> |
|**EdgeServerId** <br/> |int  <br/> |외부  <br/> |Edge 서버 등록을 진행 하는 동안. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 EdgeServers 테이블](edgeservers.md) 을 참조 하세요. <br/> |
|**IsInternal** <br/> |다소  <br/> ||사용자가 내부에서 로그온 되었는지 여부  <br/> |
|**IsUserServiceAvailable 가능** <br/> |다소  <br/> ||UserService를 사용할 수 있는지 여부  <br/> |
|**IsPrimaryRegistrar** <br/> |다소  <br/> ||기본 등록 기관에 등록할 것인지 여부  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |다소  <br/> ||사용자가 survivable branch 기기에 등록 되었는지 여부를 나타냅니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**RegisterTime** <br/> |dmtf  <br/> ||등록 시간.  <br/> |
|**DeRegisterTime** <br/> |dmtf  <br/> ||등록 취소 시간.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Register 요청의 응답 코드입니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Register 요청의 진단 ID입니다. 이는 진단 정보 유형을 나타냅니다.  <br/> |
|**DeviceId** <br/> |int  <br/> |외부  <br/> |등록 요청이 들어오는 장치입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 장치 테이블](devices.md) 을 참조 하세요. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |외부  <br/> |' 사용자 시작 ', ' 등록 만료 ', ' 클라이언트 실패 ' 등의 등록을 취소 하는 이유입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 DeRegisterType 테이블](deregistertype.md) 을 참조 하세요. <br/> |
|**IPAddress** <br/> |nvarchar (256)  <br/> ||사용자가 등록 한 끝점의 IP 주소입니다. IPv4 주소 또는 IPv6 주소를 사용할 수 있습니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
|**LastModifiedTime** <br/> |Dmtf  <br/> ||모니터링 서비스에 내부적으로 사용 합니다.  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.  <br/> |
   

