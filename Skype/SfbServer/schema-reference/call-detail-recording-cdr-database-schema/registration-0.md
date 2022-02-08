---
title: 등록 보기
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: 등록 보기에는 사용자 등록에 대한 정보가 저장됩니다. 이 보기는 Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: ccd868c228b32f69240d6b2c7a10d4c07ac90d56
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384116"
---
# <a name="registration-view"></a>등록 보기
 
등록 보기에는 사용자 등록에 대한 정보가 저장됩니다. 이 보기는 Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |세션 요청 시간입니다. SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs 테이블](dialogs.md)을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |세션을 식별하기 위한 ID 번호입니다. SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs 테이블](dialogs.md)을 참조하십시오. <br/> |
|**RegisterTime** <br/> |datetime  <br/> |등록이 발생한 시간입니다.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |등록한 사용자의 URI입니다.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |등록한 사용자 URI의 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조하십시오. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |등록한 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블](tenants.md) 을 참조하세요. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |등록한 사용자의 끝점에 대한 고유 식별자입니다.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |동일 사용자 및 동일 끝점이 포함된 등록을 구분하는 데 사용되는 고유 식별자입니다.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |등록 취소가 발생한 시간입니다.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |등록 취소에 대한 이유입니다.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |등록한 사용자가 사용한 클라이언트 버전입니다.  <br/> |
|**ClientType** <br/> |int  <br/> |등록한 사용자가 사용한 클라이언트입니다. 자세한 내용은 [UserAgentDef 테이블](useragentdef.md) 을 참조합니다. <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |등록한 사용자가 사용한 클라이언트의 범주입니다.  <br/> |
|**IpAddress** <br/> |nvarchar(256)  <br/> |사용자가 등록한 IP 주소입니다. IPv4 또는 IPv6 주소일 수 있습니다.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |SIP 대화 ID입니다. 형식은 다음과 같습니다.  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseCode** <br/> |int  <br/> |세션 초대에 대한 SIP 응답 코드입니다. 이 필드는 일반적으로 세션에서 초기 INVITE 메시지로부터 생성된 데이터로 채워집니다. INVITE 메시지가 없으면 첫 번째 관련 SIP 메시지(BYE, CANCEL, MESSAGE 또는 INFO)의 날짜 및 시간이 필드에 채워집니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |SIP 헤더에서 캡처된 진단 ID입니다.  <br/> |
|**등록자** <br/> |nvarchar(256)  <br/> |등록자의 FQDN입니다.  <br/> |
|**풀** <br/> |nvarchar(256)  <br/> |세션에 대해 데이터를 캡처한 풀의 FQDN입니다.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |등록한 사용자가 사용한 에지 서버의 FQDN입니다.  <br/> |
|**IsInternal** <br/> |bit  <br/> |사용자가 내부 네트워크에서 로그온했는지 여부를 나타냅니다.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |등록 시에 UserService를 사용할 수 있었는지를 나타냅니다.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |기본 등록자로 등록이 수행되었는지를 나타냅니다.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |등록된 장치의 MAC 주소입니다.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |등록된 장치의 제조업체입니다. 자세한 [내용은 비즈니스용 Skype 서버 2015의 Manufacturers 테이블](manufacturers.md)을 참조하십시오. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |등록된 장치의 하드웨어 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 HardwareVersions 테이블](hardwareversions.md)을 참조하세요. <br/> |
   

