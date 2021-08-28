---
title: 비즈니스용 Skype 서버 2015의 FocusJoinsAndLeaves 테이블
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
ms.localizationpriority: medium
ms.assetid: e6f0212c-67e9-4061-8720-d0296e855991
description: 이 표의 각 레코드에는 한 사용자의 참가 및 회의 나가기 정보에 대한 CDR 정보가 포함되어 있습니다. 각 회의는 사용자가 회의에 참가하고 회의에서 나날 때마다 한 레코드씩 이 표에 표시됩니다.
ms.openlocfilehash: 80f4d9f93b840b4c76e28c295356ebd85cc88979
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58632672"
---
# <a name="focusjoinsandleaves-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 FocusJoinsAndLeaves 테이블
 
이 표의 각 레코드에는 한 사용자의 참가 및 회의 나가기 정보에 대한 CDR 정보가 포함되어 있습니다. 각 회의는 사용자가 회의에 참가하고 회의에서 나날 때마다 한 레코드씩 이 표에 표시됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary, Foreign  <br/> |회의 인스턴스 시간입니다. **SessionIdSeq와** 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하십시오. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |전화 회의 인스턴스를 식별하기 위한 ID 번호입니다. **SessionIdTime과** 함께 회의 인스턴스를 고유하게 식별하는 데 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Conferences](conferences.md) 테이블을 참조하십시오. <br/> |
|**DialogSessionIdTime** <br/> |datetime  <br/> |Primary, Foreign  <br/> |세션 요청 시간입니다. **SessionIdSeq** 와 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 2015의 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**DialogSessionIdSeq** <br/> |int  <br/> |Primary, Foreign  <br/> |세션을 식별하기 위한 ID 번호입니다. **SessionIdTime** 과 함께 세션을 고유하게 식별하기 위해 사용됩니다. 자세한 내용은 [비즈니스용 Skype 서버 Dialogs](dialogs.md) 테이블을 참조하십시오. <br/> |
|**UserId** <br/> |int  <br/> |외계인  <br/> |Users 테이블에서 참조되는 이 사용자를 식별하는 [고유 번호입니다.](users.md)  <br/> |
|**FocusUserInstance** <br/> |int  <br/> ||사용자가 여러 컴퓨터 또는 장치에서 동시에 로그온되어 있는 경우 **UserInstance를** 사용하여 사용자/장치 조합을 고유하게 식별합니다. <br/> |
|**IsUserInternal** <br/> |bit  <br/> | <br/> |사용자가 내부에서 로그온한 경우의 로그온 여부입니다.  <br/> |
|**UserRole** <br/> |int  <br/> | <br/> |회의에서 이 사용자의 역할(예: 발표자 또는 참석자)입니다.  <br/> |
|**UserJoinTime** <br/> |datetime  <br/> | <br/> |이 사용자가 회의에 참가한 시간입니다.  <br/> |
|**UserLeaveTime** <br/> |datetime  <br/> | <br/> |이 사용자가 회의에서 나간 시간입니다.  <br/> |
|**ClientVerId** <br/> |int  <br/> |외계인  <br/> |2015년 10월의 [ClientVersions](clientversions.md)테이블에 비즈니스용 Skype 서버 클라이언트 소프트웨어 버전입니다.  <br/> |
|**UserEndpointId** <br/> |uniqueIdentifier  <br/> ||회의에 사용된 끝점의 GUID(Globally Unique Identifier)입니다.  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||모니터링 서비스의 내부 사용 용도  <br/> 이 필드는 2015년 비즈니스용 Skype 서버 도입했습니다.  <br/> |
   

