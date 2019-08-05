---
title: Conference 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 회의 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 또는 피어 투 피어 세션을 나타냅니다.
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196575"
---
# <a name="conference-table"></a>Conference 테이블
 
회의 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 또는 피어 투 피어 세션을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |주요한  <br/> |이 회의 레코드를 식별 하는 고유 번호입니다.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |독특한  <br/> |회의가 면 회의 URI이 고 피어 투 피어 세션 인 경우 DialogID입니다.  <br/> |
|**검사** <br/> |int  <br/> |색인  <br/> |회의 URI의 체크섬입니다. 이는 내부적으로 사용 됩니다.  <br/> |
|**NextUpdateTS** <br/> |dmtf  <br/> ||내부용 으로만 사용 됩니다.  <br/> |
   

