---
title: Server 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: Server 테이블은 지원 테이블입니다. 각 레코드는 하나의 서버를 나타냅니다.
ms.openlocfilehash: e43e245e62b1b40f318d1920ae93d82ae9e8bad0e28436f31d9cc2f0fe54bac1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341623"
---
# <a name="server-table"></a>Server 테이블
 
Server 테이블은 지원 테이블입니다. 각 레코드는 하나의 서버를 나타냅니다. 
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |이 서버를 식별하는 고유 번호입니다.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |index  <br/> |MAC 주소 문자열입니다.  <br/> |
|**ServerType** <br/> |int  <br/> |외계인  <br/> |1: 중재 서버  <br/> 2: A/V 회의 서버 16394: A/V 에지 서버 32769: 게이트웨이  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||서버가 속하는 풀입니다. A/V 회의 서버에만 적용할 수 있습니다.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||내부 용도로만 사용됩니다.  <br/> |
   

