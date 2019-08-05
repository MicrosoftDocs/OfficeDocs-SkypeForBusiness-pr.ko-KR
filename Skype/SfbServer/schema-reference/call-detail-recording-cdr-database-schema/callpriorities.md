---
title: 비즈니스용 Skype 서버 2015의 CallPriorities 순위 표
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 순위 테이블은 "비상 ', ' 긴급 ' 또는 ' normal ' 등의 가능한 통화 우선 순위 목록을 저장 하는 정적 테이블입니다.
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196796"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 CallPriorities 순위 표
 
CallPriorities 순위 테이블은 "비상 ', ' 긴급 ' 또는 ' normal ' 등의 가능한 통화 우선 순위 목록을 저장 하는 정적 테이블입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |주요한  <br/> ||
|**중요도** <br/> |nvarchar (256)  <br/> || 허용 되는 값: <br/>  0-알 수 없음 <br/>  1-비 긴급 <br/>  2-보통 <br/>  3-긴급 <br/>  4-긴급 <br/> |
   

