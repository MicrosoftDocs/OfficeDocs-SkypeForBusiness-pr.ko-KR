---
title: 비즈니스용 Skype 서버 2015의 CallPriorities 테이블
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 테이블은 'emergency', 'urgent' 또는 'normal' 등의 가능한 통화 우선 순위 목록을 저장하는 정적 테이블입니다.
ms.openlocfilehash: 73452cba57830ce08d7a4cf79ed78bf275101de0658ef006bc04efff44ee0d75
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296956"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 CallPriorities 테이블
 
CallPriorities 테이블은 'emergency', 'urgent' 또는 'normal' 등의 가능한 통화 우선 순위 목록을 저장하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**우선 순위** <br/> |nvarchar(256)  <br/> || 허용되는 값 <br/>  0 - 알 수 없음 <br/>  1 - 긴급하지 않은 <br/>  2 - 보통 <br/>  3 - 긴급 <br/>  4 - 응급 <br/> |
   

