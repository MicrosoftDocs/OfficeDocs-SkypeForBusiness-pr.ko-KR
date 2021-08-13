---
title: 비즈니스용 Skype 서버 2015의 IMReportSummary 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable은 조직에서 진행하는 인스턴트 메시징 세션에 대한 전체 보고서를 제공합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
ms.openlocfilehash: 204aeb21037f69eb34c2e12ee642d2ed6495111f8ae68d8c8f3786eb49a957fa
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341723"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 IMReportSummary 테이블
 
IMReportSummaryTable은 조직에서 진행하는 인스턴트 메시징 세션에 대한 전체 보고서를 제공합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |인스턴트 메시징 세션이 시작된 날짜 및 시간입니다.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |세션을 호스팅하는 풀의 정규화된 도메인 이름입니다.  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |통화의 우선 순위(예: 긴급, 일반)입니다. 우선 순위 정보는 2015년 10월의 [CallPriorities 테이블에 비즈니스용 Skype 서버 저장됩니다.](callpriorities.md)  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||세션 중 교환된 총 인스턴트 메시지 수입니다.  <br/> |
   

