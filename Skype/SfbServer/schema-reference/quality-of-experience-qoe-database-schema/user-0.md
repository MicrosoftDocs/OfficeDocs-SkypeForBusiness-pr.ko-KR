---
title: User 테이블
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
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: 사용자 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 한 명의 사용자를 나타냅니다.
ms.openlocfilehash: fcb6c4d45f1392c31ba87637d6e3a1a697f7be9e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805096"
---
# <a name="user-table"></a>User 테이블
 
사용자 테이블은 데이터베이스에 기록 된 세션에 참가 한 다양 한 사용자의 목록을 저장 하는 지원 테이블입니다. 테이블의 각 레코드는 한 명의 사용자를 나타냅니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |주요한  <br/> |이 사용자를 식별 하는 고유 번호입니다.  <br/> |
|**URL** <br/> |nvarchar (450)  <br/> |독특한  <br/> |URI 문자열입니다.  <br/> |
|**URIType** <br/> |int  <br/> ||1은 알 수 없는 URI 형식입니다.  <br/> 2는 사용자 URI입니다.  <br/> 4는 회의 URI입니다.  <br/> 8은 phone URI입니다.  <br/> |
|**TenantKey** <br/> |int  <br/> |외부  <br/> |테 넌 트 테이블에서 참조 하는 사용자의 테 넌 트입니다.  <br/> |
|**LastPoorCallTime** <br/> |dmtf  <br/> ||사용자가 음성 통화에 좋지 않은 경우의 최신 타임 스탬프입니다.  <br/> |
|**NextUpdateTS** <br/> |dmtf  <br/> ||내부용 으로만 사용 됩니다.  <br/> |
   

