---
title: Registration 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: 각 레코드는 한 사용자의 등록 이벤트를 나타냅니다.
ms.openlocfilehash: 1ab9c4b80d7bdbbc379c202978d7639e286128fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823118"
---
# <a name="registration-table"></a>Registration 테이블
 
각 레코드는 한 사용자의 등록 이벤트를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary, Foreign  <br/> |세션 요청 시간입니다. **SessionIdSeq** 와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |세션을 식별하기 위한 ID 번호입니다. **SessionIdTime** 과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하세요. <br/> |
|**UserId** <br/> |int  <br/> |외계인  <br/> |사용자 ID입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||등록 끝점을 식별하기 위한 GUID입니다. 일반적으로 동일 사용자 및 동일 컴퓨터의 등록 이벤트는 동일한 끝점 ID를 갖습니다. 컴퓨터가 다른 경우 서로 다른 끝점 ID를 갖습니다.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||같은 사용자 및 끝점을 포함하는 등록을 구분하는 데 사용되는 ID입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |외계인  <br/> |현재 사용자의 클라이언트 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ClientVersions](clientversions.md) 테이블을 참조하세요. <br/> |
|**RegistrarId** <br/> |int  <br/> |외계인  <br/> |등록에 사용된 등록자 서버의 ID입니다. 자세한 내용은 [Servers 테이블을](servers.md) 참조하세요. <br/> |
|**PoolId** <br/> |int  <br/> |외계인  <br/> |세션이 캡처된 풀의 ID입니다. 자세한 내용은 [Pools 테이블을](pools.md) 참조하십시오. <br/> |
|**EdgeServerId** <br/> |int  <br/> |외계인  <br/> |등록이 수행되는 에지 서버입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 EdgeServers](edgeservers.md) 테이블을 참조하세요. <br/> |
|**IsInternal** <br/> |비트  <br/> ||사용자가 내부로부터 로그온되었는지 여부입니다.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||UserService를 사용할 수 있는지 여부입니다.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||기본 등록자에 등록할지 여부입니다.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||사용자가 SBA(Survivable Branch Appliance)에 등록되는지 여부를 나타냅니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||등록 시간입니다.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||등록 취소 시간입니다.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||등록 요청의 응답 코드입니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||등록 요청의 진단 ID입니다. 이 값은 진단 정보 유형을 표시합니다.  <br/> |
|**DeviceId** <br/> |int  <br/> |외계인  <br/> |등록 요청이 시작된 장치입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Devices](devices.md) 테이블을 참조하세요. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |외계인  <br/> |등록을 하지 않은 이유(예: 'user initiated', 'registration expired', 'client fail' 등) 자세한 내용은 비즈니스용 [Skype 서버 2015의 DeRegisterType](deregistertype.md) 테이블을 참조하세요. <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||사용자가 등록된 끝점의 IP 주소입니다. IPv4 주소 또는 IPv6 주소일 수 있습니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||모니터링 서비스의 내부 사용 용도  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입했습니다.  <br/> |
   

