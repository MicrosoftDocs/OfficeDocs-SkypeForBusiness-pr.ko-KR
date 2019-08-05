---
title: 비즈니스용 Skype 서버 2015의 ErrorCategory 테이블
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 테이블에는 각 비즈니스용 Skype Server 2015 진단 분류에 대 한 친근 한 이름이 있습니다. 기본적으로 비즈니스용 Skype 서버 2015에는 다음 분류가 사용 됩니다.
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196757"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015의 ErrorCategory 테이블
 
ErrorCategory 테이블에는 각 비즈니스용 Skype Server 2015 진단 분류에 대 한 친근 한 이름이 있습니다. 기본적으로 비즈니스용 Skype 서버 2015에는 다음 분류가 사용 됩니다.
  
- 0--성공
    
- 1--실패 예상
    
- 2-예기치 않은 오류
    
이 표는 Microsoft Lync Server 2013에서 도입 되었습니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부적인**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |주요한  <br/> |분류의 고유 식별자입니다.  <br/> |
|**이름** <br/> |nvarchar (256)  <br/> || 분류에 할당 된 값 및 식별 이름입니다. 사용 가능한 값은 다음과 같습니다. <br/>  0--성공 <br/>  1--실패 예상 <br/>  2-예기치 않은 오류 <br/> |
   

