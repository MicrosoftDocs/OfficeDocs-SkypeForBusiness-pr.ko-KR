---
title: 비즈니스용 Skype 서버 2015의 CallPriorities 테이블
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 테이블은 'emergency', 'urgent' 또는 'normal' 등의 가능한 통화 우선 순위 목록을 저장하는 정적 테이블입니다.
ms.openlocfilehash: 21924d712ff4ee658f757911ce168fe8b662357d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743214"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 CallPriorities 테이블
 
CallPriorities 테이블은 'emergency', 'urgent' 또는 'normal' 등의 가능한 통화 우선 순위 목록을 저장하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**우선 순위** <br/> |nvarchar(256)  <br/> || 허용되는 값 <br/>  0 - 알 수 없음 <br/>  1 - 긴급하지 않은 <br/>  2 - 보통 <br/>  3 - 긴급 <br/>  4 - 응급 <br/> |
   

