---
title: Session 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 각 레코드는 오디오 또는 오디오 및 비디오와 관련된 하나의 세션을 나타내며, 세션에 대한 전체 정보가 포함되어 있습니다. 세션은 두 끝점 간의 오디오 또는 비디오 SIP(Session Initiation Protocol) 대화 상자로 정의됩니다.
ms.openlocfilehash: bc88a924d16e8e2193b0cce5c487004ab66f47a7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58611847"
---
# <a name="session-table"></a>Session 테이블
 
각 레코드는 오디오 또는 오디오 및 비디오와 관련된 하나의 세션을 나타내며, 세션에 대한 전체 정보가 포함되어 있습니다. 세션은 두 끝점 간의 오디오 또는 비디오 SIP(Session Initiation Protocol) 대화 상자로 정의됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |[Dialog 테이블에서 참조됩니다.](dialog.md)  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[Dialog 테이블에서 참조됩니다.](dialog.md)  <br/> |
|**ConferenceKey** <br/> |int  <br/> |외계인  <br/> |회의 키. Conference [테이블에서 참조됩니다.](conference.md)  <br/> |
|**CorrelationKey** <br/> |int  <br/> |외계인  <br/> |상관 관계 키입니다. [SessionCorrelation 테이블에서 참조됩니다.](sessioncorrelation.md)  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |대화 상자 범주; 0은 비즈니스용 Skype 서버 서버 레그에 연결됩니다. 1은 중재 서버-PSTN 게이트웨이 레그입니다.  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||통화가 바이패스되었는지 여부를 나타내는 플래그입니다.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||이 필드(제공된 경우)는 우회 ID가 일치했어도 통화가 우회되지 않은 이유를 나타냅니다. 이 비즈니스용 Skype 서버 값 하나만 정의됩니다.  <br/> 0x0001 - 기본 네트워크 어댑터의 알 수 없는 우회 ID입니다.  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |통화 시작 시간입니다.  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |통화 종료 시간입니다.  <br/> |
|**CallerPool** <br/> |int  <br/> |외계인  <br/> |발신자 풀입니다. [Pool 테이블에서 참조됩니다.](pool.md)  <br/> |
|**CalleePool** <br/> |int  <br/> |외계인  <br/> |통화 수신기의 풀입니다. [Pool 테이블에서 참조됩니다.](pool.md)  <br/> |
|**CalleePAI** <br/> |int  <br/> |외계인  <br/> |받는 끝점의 SIP PAI(p-asserted IDENTITY)의 SIP URI입니다. User [테이블에서 참조됩니다.](user-0.md)  <br/> |
|**CallerURI** <br/> |int  <br/> |외계인  <br/> |발신자 URI입니다. User [테이블에서 참조됩니다.](user-0.md)  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |외계인  <br/> |발신자 끝점입니다. [Endpoint 테이블에서 참조됩니다.](endpoint.md)  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |외계인  <br/> |발신자 사용자 에이전트입니다. [UserAgent 테이블에서 참조됩니다.](useragent.md)  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||이 호출의 우선 순위입니다.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||이 열은 더는 사용되지 않습니다. 이 열은 비즈니스용 Skype 서버. 대신 이 정보는 미디어당 줄 기준에 보고됩니다. 자세한 내용은 [MediaLine 테이블을](medialine-0.md) 참조하십시오. <br/> |
|**CallerPAI** <br/> |int  <br/> |외계인  <br/> |통화를 걸었다는 사용자의 P-Asserted-Identity입니다. PAI(P-Asserted-Identity)는 전화를 걸었다는 사용자의 실제 ID를 전달하는 데 사용됩니다.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |외계인  <br/> |통화를 수신한 끝점입니다.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |외계인  <br/> |통화를 받은 사용자가 고용한 사용자 에이전트입니다. 사용자 에이전트는 클라이언트 끝점 장치를 나타났습니다.  <br/> |
|**CalleeUri** <br/> |int  <br/> |외계인  <br/> |통화를 받은 사용자의 SIP URI입니다.  <br/> |
   

