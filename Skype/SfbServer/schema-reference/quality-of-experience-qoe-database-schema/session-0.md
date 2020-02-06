---
title: 세션 보기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: 세션 보기는 데이터베이스에 레코드가 있는 세션에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: cd304123022e0d4d921ecb1cd2599c636aaa9013
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805906"
---
# <a name="session-view"></a>세션 보기
 
세션 보기는 데이터베이스에 레코드가 있는 세션에 대 한 정보를 저장 합니다. 이 보기는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**세부적인**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |dmtf  <br/> |MediaLine 테이블에서 참조 합니다.  <br/> |
|ConferenceURI  <br/> |nvarchar (450)  <br/> |회의가 면 회의 URI이 고 피어 투 피어 세션 인 경우 DialogID입니다.  <br/> |
|상관이  <br/> |varchar (max)  <br/> |세션의 상관 관계 ID입니다.  <br/> |
|DialogCategory  <br/> |다소  <br/> |대화 상자 범주 0이 (가) 서버 레그 조정을 위한 비즈니스용 Skype 서버입니다. 1이 (가) PSTN 게이트웨이 레그로 서버를 중재 합니다.  <br/> |
|MediationServerBypassFlag  <br/> |다소  <br/> |통화가 생략 되었는지 여부를 나타냅니다.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |이 필드에는 바이패스 Id가 일치 하는 경우에도 통화가 무시 되지 않은 이유가 표시 됩니다. 비즈니스용 Skype Server의 경우 하나의 값만 정의 됩니다.  <br/> 0x0001-기본 네트워크 어댑터에 대 한 알 수 없는 바이패스 ID  <br/> |
|StartTime  <br/> |dmtf  <br/> |통화 시작 시간.  <br/> |
|EndTime  <br/> |dmtf  <br/> |통화 종료 시간.  <br/> |
|CallerPool  <br/> |nvarchar (256)  <br/> |발신자 풀 FQDN.  <br/> |
|CalleePool  <br/> |nvarchar (256)  <br/> |호출 수신자 풀 FQDN입니다.  <br/> |
|CallerPAI  <br/> |nvarchar (450)  <br/> |호출자의 p-어설션된 id URI입니다.  <br/> |
|CalleePAI  <br/> |nvarchar (450)  <br/> |피호출자의 p-어설션된 id URI입니다.  <br/> |
|CallerEndpoint  <br/> |nvarchar (256)  <br/> |호출자의 끝점 이름입니다.  <br/> |
|CalleeEndpoint  <br/> |nvarchar (256)  <br/> |호출자의 끝점 이름입니다.  <br/> |
|CallerUserAgent  <br/> |nvarchar (256)  <br/> |호출자의 사용자 에이전트 문자열입니다.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |호출자의 사용자 에이전트 유형입니다. 자세한 내용은 [UserAgent 테이블](useragent.md) 을 참조 하세요. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |호출자의 사용자 에이전트 범주입니다. 자세한 내용은 [Useragentdef 테이블 (체감 품질)](useragentdef-qoe.md) 을 참조 하세요. <br/> |
|CalleeUserAgent  <br/> |nvarchar (256)  <br/> |호출 수신자의 사용자 에이전트 문자열입니다.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |호출 수신자의 사용자 에이전트 유형입니다. 자세한 내용은 [UserAgent 테이블](useragent.md) 을 참조 하세요. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |호출 수신자의 사용자 에이전트 범주입니다. 자세한 내용은 [Useragentdef 테이블 (체감 품질)](useragentdef-qoe.md) 을 참조 하세요. <br/> |
|CallerURI  <br/> |nvarchar (450)  <br/> |호출자의 URI입니다.  <br/> |
|CalleeURI  <br/> |nvarchar (450)  <br/> |호출 수신자의 URI입니다.  <br/> |
|Callto Oirty  <br/> |int  <br/> |통화의 우선 순위입니다.  <br/> |
   

