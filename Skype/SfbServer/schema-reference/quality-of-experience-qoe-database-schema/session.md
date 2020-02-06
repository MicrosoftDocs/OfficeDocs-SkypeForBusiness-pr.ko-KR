---
title: Session 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 각 레코드는 오디오 또는 오디오 및 비디오를 포함 하는 하나의 세션을 나타냅니다. 세션에 대 한 전반적인 정보를 포함 합니다. 세션은 두 끝점 간에 오디오 또는 SIP (비디오 세션 초기화 프로토콜) 대화 상자로 정의 됩니다.
ms.openlocfilehash: f48857f826a4e85519d7dc7d2942d48967df8b01
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805776"
---
# <a name="session-table"></a>Session 테이블
 
각 레코드는 오디오 또는 오디오 및 비디오를 포함 하는 하나의 세션을 나타냅니다. 세션에 대 한 전반적인 정보를 포함 합니다. 세션은 두 끝점 간에 오디오 또는 SIP (비디오 세션 초기화 프로토콜) 대화 상자로 정의 됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dmtf  <br/> |주요한  <br/> |[대화 상자 테이블](dialog.md)에서 참조 됩니다.  <br/> |
|**SessionSeq** <br/> |int  <br/> |주요한  <br/> |[대화 상자 테이블](dialog.md)에서 참조 됩니다.  <br/> |
|**ConferenceKey** <br/> |int  <br/> |외부  <br/> |회의 키입니다. [회의 테이블](conference.md)에서 참조 됩니다.  <br/> |
|**CorrelationKey** <br/> |int  <br/> |외부  <br/> |상관 관계 키입니다. [Sessioncorrelation 관계 테이블](sessioncorrelation.md)에서 참조 합니다.  <br/> |
|**DialogCategory** <br/> |다소  <br/> | <br/> |대화 상자 범주 0이 (가) 서버 레그 조정을 위한 비즈니스용 Skype 서버입니다. 1이 (가) PSTN 게이트웨이 레그로 서버를 중재 합니다.  <br/> |
|**MediationServerBypassFlag** <br/> |다소  <br/> ||통화가 바이패스 되었는지 여부를 나타내는 플래그입니다.  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||이 필드에는 바이패스 Id가 일치 하는 경우에도 통화가 무시 되지 않은 이유가 표시 됩니다. 비즈니스용 Skype Server의 경우 하나의 값만 정의 됩니다.  <br/> 0x0001-기본 네트워크 어댑터에 대 한 알 수 없는 바이패스 ID입니다.  <br/> |
|**StartTime** <br/> |dmtf  <br/> | <br/> |통화 시작 시간.  <br/> |
|**EndTime** <br/> |dmtf  <br/> | <br/> |통화 종료 시간.  <br/> |
|**CallerPool** <br/> |int  <br/> |외부  <br/> |호출자의 풀입니다. [풀 테이블](pool.md)에서 참조 됩니다.  <br/> |
|**CalleePool** <br/> |int  <br/> |외부  <br/> |통화 수신기 풀입니다. [풀 테이블](pool.md)에서 참조 됩니다.  <br/> |
|**CalleePAI** <br/> |int  <br/> |외부  <br/> |수신 끝점의 SIP p-어설션된 id (PAI)의 SIP URI입니다. [사용자 테이블](user-0.md)에서 참조 됩니다.  <br/> |
|**CallerURI** <br/> |int  <br/> |외부  <br/> |호출자의 URI입니다. [사용자 테이블](user-0.md)에서 참조 됩니다.  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |외부  <br/> |호출자의 끝점입니다. [끝점 테이블](endpoint.md)에서 참조 됩니다.  <br/> |
|**CallerUserAgent** <br/> |다소  <br/> |외부  <br/> |발신자의 사용자 에이전트. [UserAgent 테이블](useragent.md)에서 참조 됩니다.  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||이 통화의 우선 순위입니다.  <br/> |
|**ClassifiedPoorCall** <br/> |다소  <br/> ||이 열은 더 이상 사용 되지 않으며 비즈니스용 Skype 서버에서 사용 되지 않습니다. 대신이 정보는 미디어 단위 회선 기반에 보고 됩니다. 자세한 내용은 [Medialine 테이블](medialine-0.md) 을 참조 하세요. <br/> |
|**CallerPAI** <br/> |int  <br/> |외부  <br/> |P-어설션 됨-통화를 놓은 사용자의 Id입니다. P-어설션된-Id (PAI)는 통화를 설정한 사용자의 실제 id를 전달 하는 데 사용 됩니다.  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |외부  <br/> |통화를 받은 끝점입니다.  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |외부  <br/> |통화를 받은 사용자가 사용 하는 사용자 에이전트입니다. 사용자 에이전트는 클라이언트 끝점 장치를 나타냅니다.  <br/> |
|**CalleeUri** <br/> |int  <br/> |외부  <br/> |통화를 받은 사용자의 SIP URI입니다.  <br/> |
   

