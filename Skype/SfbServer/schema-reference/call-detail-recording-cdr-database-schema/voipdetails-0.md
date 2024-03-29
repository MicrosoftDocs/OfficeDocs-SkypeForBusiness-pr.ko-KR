---
title: VoipDetails 테이블
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: 각 레코드는 적어도 한 명의 사용자가 VoIP 사용자인 하나의 두 사용자 간 통화를 나타냅니다.
ms.openlocfilehash: 4cb3513ae5eb528c5e681cd55b173749c8cf1a02
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416371"
---
# <a name="voipdetails-table"></a>VoipDetails 테이블
 
각 레코드는 적어도 한 명의 사용자가 VoIP 사용자인 하나의 두 사용자 간 통화를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |세션 요청 시간입니다. **SessionIdSeq** 와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs 테이블](dialogs.md)을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |세션을 식별하기 위한 ID 번호입니다. **SessionIdTime** 과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs 테이블](dialogs.md)을 참조하십시오. <br/> |
|**FromNumberId** <br/> |int  <br/> |외계인  <br/> |발신자의 **PhoneId** 입니다. 자세한 [내용은 Phones 테이블](phones.md) 을 참조하십시오. NULL이 아니고 **FromGatewayId** 가 NULL이 아니면 발신자가 PSTN 사용자입니다. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |외계인  <br/> |통화 수신자의 **PhoneId** 입니다. 자세한 [내용은 Phones 테이블](phones.md) 을 참조하십시오. NULL이 아니고 **ToGatewayId** 가 NULL이 아니면 통화 수신자가 PSTN 사용자입니다. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |외계인  <br/> |통화의 발신측 중재 서버입니다. 자세한 내용은 [MediationServers 테이블](mediationservers.md) 을 참조하세요. <br/> |
|**ToMediationServerId** <br/> |int  <br/> |외계인  <br/> |통화의 수신측 중재 서버입니다. 자세한 내용은 [MediationServers 테이블](mediationservers.md) 을 참조하세요. <br/> |
|**FromGatewayId** <br/> |int  <br/> |외계인  <br/> |통화의 발신측 게이트웨이입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Gateways](gateways.md) 테이블을 참조하십시오. <br/> |
|**ToGatewayId** <br/> |int  <br/> |외계인  <br/> |통화의 수신측 게이트웨이입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Gateways](gateways.md) 테이블을 참조하십시오. <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |외계인  <br/> |사용자가 URI를 갖고 있는 경우 통화 연결을 끊은 사용자의 URI입니다. 자세한 내용은 [Users 테이블](users.md) 을 참조하십시오. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |외계인  <br/> |전화에서 연결을 끊은 경우 통화 연결을 끊은 전화의 ID입니다. 자세한 [내용은 Phones 테이블](phones.md) 을 참조하십시오. <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||모니터링 서비스의 내부 사용 용도  <br/> 이 필드는 2015년 비즈니스용 Skype 서버 도입했습니다.  <br/> |
   

