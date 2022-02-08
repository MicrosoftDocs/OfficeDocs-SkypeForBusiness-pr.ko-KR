---
title: Phones 테이블
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 데이터베이스에 레코드가 있는 VoIP 호출에 관련된 하나의 전화 번호에 대한 정보가 저장됩니다.
ms.openlocfilehash: 0dbe5065b4a0849b4538e77c05a846ed06f72da5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389810"
---
# <a name="phones-table"></a>Phones 테이블
 
Phones 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 데이터베이스에 레코드가 있는 VoIP 호출에 관련된 하나의 전화 번호에 대한 정보가 저장됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |이 전화를 식별하는 고유 번호입니다.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |전화 번호  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||타임스탬프(내부 전용)  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
   

