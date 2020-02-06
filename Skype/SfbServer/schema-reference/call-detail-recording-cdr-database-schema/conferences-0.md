---
title: 회의 보기
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
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: 회의 보기는 회의에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 9f9448769256bfb05e6552a41c2521defa65ded0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815366"
---
# <a name="conferences-view"></a>회의 보기
 
회의 보기는 회의에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |dmtf  <br/> |세션 요청 시간입니다. 세션을 고유 하 게 식별 하는 SessionIdSeq와 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |세션을 식별 하는 ID 번호입니다. 세션을 고유 하 게 식별 하는 SessionIdTime과 함께 사용 됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 대화 상자 표](dialogs.md) 를 참조 하세요. <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |회의 URI입니다.  <br/> |
|**ConferenceUriType** <br/> |nvarchar (256)  <br/> |회의 URI의 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**인스턴스** <br/> |uniqueidentifier  <br/> |되풀이 회의에 사용 됩니다. 되풀이 회의의 각 인스턴스에는 동일한 ConferenceUri 있지만 다른 지 인 인스턴스가 있습니다.  <br/> |
|**ConferenceStartTime** <br/> |dmtf  <br/> |회의 시작 시간입니다.  <br/> |
|**ConferenceEndTime** <br/> |dmtf  <br/> |회의 종료 시간입니다.  <br/> |
|**OrganizerUri** <br/> |nvarchar (450)  <br/> |회의를 구성한 사용자의 URI입니다.  <br/> |
|**OrganizerType** <br/> |nvarchar (256)  <br/> |회의를 구성한 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블](uritypes.md) 을 참조 하세요. <br/> |
|**OrganizerTenant** <br/> |nvarchar (256)  <br/> |회의를 구성한 사용자의 테 넌 트입니다. 자세한 내용은 [테 넌 트 테이블](tenants.md) 을 참조 하세요. <br/> |
|**풀** <br/> |nvarchar (256)  <br/> |컨퍼런스를 호스팅한 풀의 정규화 된 도메인 이름입니다.  <br/> |
|**플래그** <br/> |smallint  <br/> |회의 특성을 포함 하는 비트 마스크입니다. 사용할 수 있는 값은 다음과 같습니다.  <br/> 0X01-가상 트랜잭션  <br/> |
   

