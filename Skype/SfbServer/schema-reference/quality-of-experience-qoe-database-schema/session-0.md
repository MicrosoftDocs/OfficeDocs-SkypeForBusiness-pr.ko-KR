---
title: 세션 보기
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: 세션 보기에는 데이터베이스의 레코드가 포함된 세션에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
ms.openlocfilehash: 22ad5fdc02eb7b3dc7531a18f4b40bee0334ce09
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776018"
---
# <a name="session-view"></a>세션 보기
 
세션 보기에는 데이터베이스의 레코드가 포함된 세션에 대한 정보가 저장됩니다. 이 보기는 Microsoft Lync Server 2013에서 도입했습니다.
  
|**열**|**데이터 형식**|**세부 정보**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |MediaLine 테이블에서 참조됩니다.  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |항목이 회의인 경우 회의 URI이고 피어 투 피어 세션인 경우에는 DialogID입니다.  <br/> |
|Correlation  <br/> |varchar(max)  <br/> |세션의 상관 관계 ID입니다.  <br/> |
|DialogCategory  <br/> |bit  <br/> |대화 상자 범주; 0은 비즈니스용 Skype 서버 서버 레그에 연결됩니다. 1은 중재 서버-PSTN 게이트웨이 레그입니다.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |통화가 우회되었는지 여부를 나타냅니다.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |이 필드(제공된 경우)는 우회 ID가 일치했어도 통화가 우회되지 않은 이유를 나타냅니다. 이 비즈니스용 Skype 서버 값 하나만 정의됩니다.  <br/> 0x0001 - 기본 네트워크 어댑터의 알 수 없는 우회 ID  <br/> |
|StartTime  <br/> |datetime  <br/> |통화 시작 시간입니다.  <br/> |
|EndTime  <br/> |datetime  <br/> |통화 종료 시간입니다.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |발신자 풀 FQDN입니다.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |수신자 풀 FQDN입니다.  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |발신자의 p-asserted ID URI입니다.  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |발신자의 p-asserted ID URI입니다.  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |발신자 끝점 이름입니다.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |발신자 끝점 이름입니다.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |발신자 사용자 에이전트 문자열입니다.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |발신자 사용자 에이전트의 유형입니다. 자세한 내용은 [UserAgent 테이블을](useragent.md) 참조합니다. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |발신자 사용자 에이전트의 범주입니다. 자세한 내용은 [UserAgentDef 테이블(QoE)을](useragentdef-qoe.md) 참조합니다. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |발신자 사용자 에이전트 문자열입니다.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |수신자의 사용자 에이전트 유형입니다. 자세한 내용은 [UserAgent 테이블을](useragent.md) 참조합니다. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |수신자의 사용자 에이전트 범주입니다. 자세한 내용은 [UserAgentDef 테이블(QoE)을](useragentdef-qoe.md) 참조합니다. <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |발신자 URI입니다.  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |발신자 URI입니다.  <br/> |
|CallPrioirty  <br/> |int  <br/> |통화 우선 순위입니다.  <br/> |
   

