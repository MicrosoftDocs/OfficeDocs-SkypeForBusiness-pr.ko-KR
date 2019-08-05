---
title: 비즈니스용 Skype 서버 2015의 IMReportSummary 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: Imreport요약 테이블은 조직에 보관 된 인스턴트 메시징 세션에 대 한 전반적인 보고서를 제공 합니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196736"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 IMReportSummary 테이블
 
Imreport요약 테이블은 조직에 보관 된 인스턴트 메시징 세션에 대 한 전반적인 보고서를 제공 합니다. 이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**StartTime** <br/> |dmtf  <br/> |주요한  <br/> |인스턴트 메시징 세션이 시작 된 날짜 및 시간입니다.  <br/> |
|**TimePeriod** <br/> |char (1)  <br/> |주요한  <br/> ||
|**PoolFQDN** <br/> |nvarchar (257)  <br/> |주요한  <br/> |세션을 호스트 하는 풀의 정규화 된 도메인 이름입니다.  <br/> |
|**AuthType** <br/> |int  <br/> |주요한  <br/> |우선 순위 (예: 긴급 또는 비 긴급 통화) 우선 순위 정보는 비즈니스용 [Skype 서버 2015의 callpriorities 테이블](callpriorities.md)에 저장 됩니다.  <br/> |
|**SessionCount** <br/> |bigint  <br/> |||
|**MsgCount** <br/> |bigint  <br/> ||세션 중에 교환 된 총 인스턴트 메시지 수입니다.  <br/> |
   

