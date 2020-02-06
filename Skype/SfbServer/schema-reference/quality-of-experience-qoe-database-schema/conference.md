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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 회의 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 또는 피어 투 피어 세션을 나타냅니다.
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810306"
---
# <a name="conference-table"></a>Conference 테이블
 
회의 테이블은 지원 테이블입니다. 각 레코드는 하나의 회의 또는 피어 투 피어 세션을 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ConferenceKey** <br/> |int  <br/> |주요한  <br/> |이 회의 레코드를 식별 하는 고유 번호입니다.  <br/> |
|**ConfURI** <br/> |nvarchar (450)  <br/> |독특한  <br/> |회의가 면 회의 URI이 고 피어 투 피어 세션 인 경우 DialogID입니다.  <br/> |
|**검사** <br/> |int  <br/> |색인  <br/> |회의 URI의 체크섬입니다. 이는 내부적으로 사용 됩니다.  <br/> |
|**NextUpdateTS** <br/> |dmtf  <br/> ||내부용 으로만 사용 됩니다.  <br/> |
   

