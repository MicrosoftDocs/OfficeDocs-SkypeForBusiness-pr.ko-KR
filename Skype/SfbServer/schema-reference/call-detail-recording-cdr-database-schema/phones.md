---
title: Phones 테이블
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: Phones 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 데이터베이스에 레코드가 있는 VoIP 호출에 관련된 하나의 전화 번호에 대한 정보가 저장됩니다.
ms.openlocfilehash: 938e00267f5f356c646d363033ef9a8917b910261f873637c0f6b3a6b9ff8742
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329462"
---
# <a name="phones-table"></a>Phones 테이블
 
Phones 테이블은 지원 테이블입니다. 테이블의 각 레코드에는 데이터베이스에 레코드가 있는 VoIP 호출에 관련된 하나의 전화 번호에 대한 정보가 저장됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |이 전화를 식별하는 고유 번호입니다.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |전화 번호입니다.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||타임스탬프(내부 전용)  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입했습니다.  <br/> |
   

