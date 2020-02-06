---
title: Server 테이블
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: 서버 테이블은 지원 테이블입니다. 각 레코드는 하나의 서버를 나타냅니다.
ms.openlocfilehash: e57bb96fd715d67a5b6676a2399dc520f08bac96
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41806136"
---
# <a name="server-table"></a>Server 테이블
 
서버 테이블은 지원 테이블입니다. 각 레코드는 하나의 서버를 나타냅니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |주요한  <br/> |서버를 식별 하는 고유 번호입니다.  <br/> |
|**FQDNOrIP** <br/> |nvarchar (256)  <br/> |색인  <br/> |MAC 주소 문자열입니다.  <br/> |
|**ServerType** <br/> |int  <br/> |외부  <br/> |1: 중재 서버  <br/> 2: a/V 회의 Server16394: A/v Edge service32769: Gateway  <br/> |
|**PoolName** <br/> |nvarchar (512)  <br/> ||서버가 속한 풀. A/V 회의 서버에만 해당 됩니다.  <br/> |
|**NextUpdateTS** <br/> |dmtf  <br/> ||내부용 으로만 사용 됩니다.  <br/> |
   

