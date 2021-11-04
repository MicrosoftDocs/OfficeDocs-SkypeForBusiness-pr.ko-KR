---
title: McuJoinsAndLeaves 보기
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
description: McuJoinsAndLeaves 보기에는 한 회의 서버에 참가 및 나가는 사용자에 대한 정보가 저장됩니다. 이 보기의 각 레코드에는 사용자 참가 또는 나가기 및 회의 서버의 한 조합에 대한 통화 세부 정보가 포함되어 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 509eca981381b052962ac516a1b0d5537e8c27f1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763336"
---
# <a name="mcujoinsandleaves-view"></a>McuJoinsAndLeaves 보기
 
McuJoinsAndLeaves 보기에는 한 회의 서버에 참가 및 나가는 사용자에 대한 정보가 저장됩니다. 이 보기의 각 레코드에는 사용자 참가 또는 나가기 및 회의 서버의 한 조합에 대한 통화 세부 정보가 포함되어 있습니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |회의 인스턴스 시간입니다. SessionIdSeq와 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |전화 회의 인스턴스를 식별하기 위한 ID 번호입니다. SessionIdTime과 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하십시오. <br/> |
|**McuUri** <br/> |nvarchar(256)  <br/> |사용자가 연결한 회의 서버의 URI입니다.  <br/> |
|**McuUriType** <br/> |nvarchar(256)  <br/> |사용자가 연결한 회의 서버의 URI입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |회의 서버 참가/나가기 정보가 캡처된 사용자의 URI입니다.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |회의 서버 참가/나가기 정보가 캡처된 사용자의 URI 유형입니다. 자세한 내용은 [UriTypes 테이블을](uritypes.md) 참조하십시오. <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |회의 서버 참가/나가기 정보가 캡처된 사용자의 테넌트입니다. 자세한 내용은 [Tenants 테이블을](tenants.md) 참조하세요. <br/> |
|**UserClientVersion** <br/> |nvarchar(256)  <br/> |회의 서버 참가/나가기 정보가 캡처된 사용자가 사용한 클라이언트 버전입니다.  <br/> |
|**UserClientType** <br/> |int  <br/> |회의 서버 참가/나가기 정보가 캡처된 사용자가 사용한 클라이언트입니다. 자세한 내용은 [UserAgentDef 테이블을](useragentdef.md) 참조합니다. <br/> |
|**UserClientCategory** <br/> |nvarchar(64)  <br/> |회의 서버 참가/나가기 정보가 캡처된 사용자가 사용한 클라이언트 범주의 이름입니다.  <br/> |
|**McuUserInstance** <br/> |int  <br/> |동시에 여러 장치에 로그온한 사용자의 사용자/장치 조합을 고유하게 식별합니다.  <br/> |
|**IsUserFromPstn** <br/> |bit  <br/> |사용자가 내부 사용자인지 여부를 나타내는 비트입니다.  <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |세션 요청 시간입니다. SessionIdSeq와 함께 회의 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |세션을 식별하기 위한 ID 번호입니다. SessionIdTime과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**DialogId** <br/> |varchar(775)  <br/> |세션의 SIP 대화 ID입니다. 형식은 dialog;from-tag;to-tag입니다.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> |사용자가 회의 서버에 참가한 시간입니다.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> |사용자가 회의 서버를 떠나는 시간입니다.  <br/> |
   

