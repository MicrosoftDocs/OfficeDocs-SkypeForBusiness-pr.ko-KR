---
title: 비즈니스용 Skype 서버 2015의 McuJoinsAndLeaves 테이블
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
ms.assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
description: 이 표의 각 레코드에는 사용자 조인 또는 나가기 및 회의 서버의 한 조합에 대한 통화 세부 정보가 포함되어 있습니다. 예를 들어 사용자가 웹 회의 및 오디오/비디오 요소가 포함된 회의에 참가하는 경우 해당 사용자의 웹 회의 참가에 대한 레코드가 하나 만들어지며 사용자의 오디오/비디오 회의 참가에 대한 레코드가 만들어집니다.
ms.openlocfilehash: df18ca4785fab9b56057eb439ab55caa2b1a170f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737605"
---
# <a name="mcujoinsandleaves-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 McuJoinsAndLeaves 테이블
 
이 표의 각 레코드에는 사용자 조인 또는 나가기 및 회의 서버의 한 조합에 대한 통화 세부 정보가 포함되어 있습니다. 예를 들어 사용자가 웹 회의 및 오디오/비디오 요소가 포함된 회의에 참가하는 경우 해당 사용자의 웹 회의 참가에 대한 레코드가 하나 만들어지며 사용자의 오디오/비디오 회의 참가에 대한 레코드가 만들어집니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary, Foreign  <br/> |회의 인스턴스 시간입니다. **SessionIdSeq와** 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |전화 회의 인스턴스를 식별하기 위한 ID 번호입니다. **SessionIdTime과** 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하십시오. <br/> |
|**UserId** <br/> |int  <br/> |Primary, Foreign  <br/> |이 사용자를 식별하는 고유 번호입니다. 자세한 내용은 [Users 테이블을](users.md) 참조하십시오. <br/> |
|**McuUserInstance** <br/> |int  <br/> |Primary  <br/> |사용자가 여러 컴퓨터 또는 디바이스에서 동시에 로그온하는 경우 McuUserInstance는 사용자/장치 조합을 고유하게 식별합니다.  <br/> |
|**IsFromPstn** <br/> |bit  <br/> | <br/> |사용자가 PSTN에서 참가하는지 여부입니다.  <br/> |
|**McuId** <br/> |int  <br/> |Primary, Foreign  <br/> |이 회의 서버를 식별하는 고유 번호입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Mcus](mcus.md) 테이블을 참조하세요. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |외계인  <br/> |세션 요청 시간입니다. **SessionIdSeq** 와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |외계인  <br/> |세션을 식별하기 위한 ID 번호입니다. **SessionIdTime** 과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |이 사용자가 이 회의 서버에 참가한 시간입니다.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |이 사용자가 이 회의 서버를 떠나는 시간입니다.  <br/> |
|**ClientVerId** <br/> |int  <br/> |외계인  <br/> |회의에서 사용하는 클라이언트 소프트웨어의 버전 번호를 지정하는 식별자입니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 ClientVersions](clientversions.md) 테이블을 참조하세요. <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||모니터링 서비스의 내부 사용 용도  <br/> 이 필드는 2015년 비즈니스용 Skype 서버 도입했습니다.  <br/> |
   

