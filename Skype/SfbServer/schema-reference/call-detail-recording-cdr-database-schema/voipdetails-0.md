---
title: VoipDetails 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: 각 레코드는 하나 이상의 사용자가 VoIP 사용자 인 1 2-파티 통화를 나타냅니다.
ms.openlocfilehash: 65bf3b4d7a815434b21b761030a7ac514d9bd803
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814786"
---
# <a name="voipdetails-table"></a>VoipDetails 테이블
 
각 레코드는 하나 이상의 사용자가 VoIP 사용자 인 1 2-파티 통화를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |주요한  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 **Sessionidseq** 와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |주요한  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 **Sessionidtime** 과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**From번호 번호** <br/> |int  <br/> |외부  <br/> |발신자의 **PhoneId** . 자세한 내용은 [전화 테이블](phones.md) 을 참조 하세요. NULL이 아니고 **FromGatewayId** 가 null이 아니면 호출자는 PSTN 사용자입니다. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |외부  <br/> |통화 수신기의 **PhoneId** . 자세한 내용은 [전화 테이블](phones.md) 을 참조 하세요. NULL이 아니고 **ToGatewayId** 가 null이 아니면 통화 수신기는 PSTN 사용자입니다. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |외부  <br/> |통화를 보내는 중재 서버입니다. 자세한 내용은 [Mediationservers 테이블](mediationservers.md) 을 참조 하세요. <br/> |
|**ToMediationServerId** <br/> |int  <br/> |외부  <br/> |호출 되는 중재 서버. 자세한 내용은 [Mediationservers 테이블](mediationservers.md) 을 참조 하세요. <br/> |
|**FromGatewayId** <br/> |int  <br/> |외부  <br/> |통화를 보내는 게이트웨이. 자세한 내용은 [비즈니스용 Skype 서버 2015의 게이트웨이 테이블](gateways.md) 을 참조 하세요. <br/> |
|**ToGatewayId** <br/> |int  <br/> |외부  <br/> |전화를 받는 게이트웨이 자세한 내용은 [비즈니스용 Skype 서버 2015의 게이트웨이 테이블](gateways.md) 을 참조 하세요. <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |외부  <br/> |사용자에 게 URI가 있는 경우 전화를 끊은 사용자의 URI입니다. 자세한 내용은 [사용자 테이블](users.md) 을 참조 하세요. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |외부  <br/> |통화를 끊은 전화의 ID가 휴대폰에서 연결이 끊어졌습니다. 자세한 내용은 [전화 테이블](phones.md) 을 참조 하세요. <br/> |
|**LastModifiedTime** <br/> |Dmtf  <br/> ||모니터링 서비스에 내부적으로 사용 합니다.  <br/> 이 필드는 비즈니스용 Skype 서버 2015에서 도입 되었습니다.  <br/> |
   

