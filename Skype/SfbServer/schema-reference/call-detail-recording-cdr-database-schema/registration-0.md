---
title: 등록 보기
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
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: 등록 보기에는 사용자 등록에 대 한 정보가 저장 됩니다. 이 보기는 Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 0ee19d4addae9ee7318828c4ab294dc15bd72f86
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814956"
---
# <a name="registration-view"></a>등록 보기
 
등록 보기에는 사용자 등록에 대 한 정보가 저장 됩니다. 이 보기는 Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**RegisterTime** <br/> |dmtf  <br/> |등록이 발생 한 시간입니다.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |등록 된 사용자의 URI입니다.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |등록 된 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**UserTenant 넌 트** <br/> |nvarchar (256)  <br/> |등록 된 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |등록 된 사용자의 끝점에 대 한 고유 식별자입니다.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |같은 사용자 및 같은 끝점과 관련 된 등록을 구분 하는 데 사용 되는 고유 식별자입니다.  <br/> |
|**DeRegisterType** <br/> |dmtf  <br/> |등록 취소가 발생 한 시간입니다.  <br/> |
|**DeRegisterReason** <br/> |nvarchar (256)  <br/> |등록 취소 이유.  <br/> |
|**ClientVersion** <br/> |nvarchar (256)  <br/> |등록 한 사용자가 사용 하는 클라이언트 버전입니다.  <br/> |
|**ClientType** <br/> |int  <br/> |등록 한 사용자가 사용 하는 클라이언트 자세한 내용은 [Useragentdef 테이블](useragentdef.md) 을 참조 하세요. <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |등록 하는 사용자가 사용 하는 클라이언트의 범주입니다.  <br/> |
|**IpAddress** <br/> |nvarchar (256)  <br/> |사용자가 등록 된 IP 주소입니다. IPv4 또는 IPv6 주소를 사용할 수 있습니다.  <br/> |
|**DialogId** <br/> |varstring (775)  <br/> |SIP 대화 상자 ID입니다. 의 형식은 다음과 같습니다.  <br/> 대화 상자; from 태그; 태그  <br/> |
|**ResponseCode** <br/> |int  <br/> |세션 초대에 대 한 SIP 응답 코드입니다. 일반적으로이 필드는 세션의 초기 초대 메시지에서 생성 된 데이터에 의해 채워집니다. 초대 메시지가 없는 경우 첫 번째 관련 SIP 메시지의 날짜 및 시간 (BYE, 취소, 메시지 또는 정보)으로 필드가 채워집니다.  <br/> |
|**DiagnosticId** <br/> |int  <br/> |SIP 헤더에서 진단 ID를 캡처 했습니다.  <br/> |
|**레지스터** <br/> |nvarchar (256)  <br/> |등록자의 FQDN입니다.  <br/> |
|**풀** <br/> |nvarchar (256)  <br/> |세션에 대 한 데이터를 캡처한 풀의 FQDN입니다.  <br/> |
|**EdgeServer** <br/> |nvarchar (256)  <br/> |등록 된 사용자가 사용 하는 Edge 서버의 FQDN입니다.  <br/> |
|**IsInternal** <br/> |다소  <br/> |사용자가 내부 네트워크에서 로그온 했는지 여부를 나타냅니다.  <br/> |
|**IsUserServiceAvailable 가능** <br/> |다소  <br/> |등록할 때 UserService를 사용할 수 있는지 여부를 나타냅니다.  <br/> |
|**IsPrimaryRegistrar** <br/> |다소  <br/> |등록이 기본 등록자를 사용 하 고 있는지 여부를 나타냅니다.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |등록 된 디바이스의 MAC 주소입니다.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar (256)  <br/> |등록 된 디바이스의 제조업체입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 제조업체 표](manufacturers.md) 를 참조 하세요. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar (256)  <br/> |등록 된 디바이스의 하드웨어 버전입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015에서 HardwareVersions 테이블](hardwareversions.md) 을 참조 하세요. <br/> |
   

