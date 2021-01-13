---
title: 비즈니스용 Skype 서버의 IMReportSummary 테이블
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
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821528"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버의 IMReportSummary 테이블
 
IMReportSummaryTable은 조직에서 진행하는 인스턴트 메시징 세션에 대한 전체 보고서를 제공합니다. 이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |datetime  <br/> |Primary  <br/> |인스턴트 메시징 세션이 시작된 날짜 및 시간입니다.  <br/> |
|**TimePeriod** <br/> |char(1)  <br/> |Primary  <br/> ||
|**PoolFQDN** <br/> |nvarchar(257)  <br/> |Primary  <br/> |세션을 호스팅하는 풀의 정규화된 도메인 이름입니다.  <br/> |
|**AuthType** <br/> |int  <br/> |Primary  <br/> |통화의 우선 순위(예: 긴급, 일반)입니다. 우선 순위 정보는 비즈니스용 Skype 서버 [2015의 CallPriorities](callpriorities.md)테이블에 저장됩니다.  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||세션 중 교환된 총 인스턴트 메시지 수입니다.  <br/> |
   

