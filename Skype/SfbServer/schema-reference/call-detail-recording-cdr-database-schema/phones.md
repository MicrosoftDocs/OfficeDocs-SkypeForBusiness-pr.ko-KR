---
title: Phones 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: 전화 테이블은 지원 테이블입니다. 표의 각 레코드에는 데이터베이스의 레코드를 포함 하는 VoIP 통화와 관련 된 하나의 전화 번호에 대 한 정보가 저장 됩니다.
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196709"
---
# <a name="phones-table"></a>Phones 테이블
 
전화 테이블은 지원 테이블입니다. 표의 각 레코드에는 데이터베이스의 레코드를 포함 하는 VoIP 통화와 관련 된 하나의 전화 번호에 대 한 정보가 저장 됩니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |주요한  <br/> |이 전화를 식별 하는 고유 번호입니다.  <br/> |
|**PhoneUri** <br/> |nvarchar (450)  <br/> | <br/> |전화 번호입니다.  <br/> |
|**NextUpdateTS** <br/> |Dmtf  <br/> ||타임 스탬프 (내부용).  <br/> 이 필드는 Microsoft Lync Server 2013에서 도입 되었습니다.  <br/> |
   

