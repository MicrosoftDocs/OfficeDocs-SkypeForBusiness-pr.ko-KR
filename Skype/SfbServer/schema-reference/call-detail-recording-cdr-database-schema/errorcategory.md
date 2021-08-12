---
title: 2015년 비즈니스용 Skype 서버 ErrorCategory 테이블
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: ErrorCategory 테이블에는 2015년 진단 분류의 각 비즈니스용 Skype 서버 이름이 포함되어 있습니다. 기본적으로 비즈니스용 Skype 서버 2015에서는 다음 분류를 사용하게 됩니다.
ms.openlocfilehash: 68114e96e04ca8e2cb45fbb2b9ba0b3934df4e363700f8a872f05cb1aa0e8a37
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347773"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>2015년 비즈니스용 Skype 서버 ErrorCategory 테이블
 
ErrorCategory 테이블에는 2015년 진단 분류의 각 비즈니스용 Skype 서버 이름이 포함되어 있습니다. 기본적으로 비즈니스용 Skype 서버 2015에서는 다음 분류를 사용하게 됩니다.
  
- 0 -- 성공
    
- 1 -- 예상 오류
    
- 2 - 예기치 않은 오류
    
이 표는 Microsoft Lync Server 2013에서 도입된 것입니다.
  
|**열**|**데이터 형식**|**키/인덱스**|**세부 정보**|
|:-----|:-----|:-----|:-----|
|**CategoryId** <br/> |tinyint  <br/> |Primary  <br/> |분류의 고유한 식별자입니다.  <br/> |
|**이름** <br/> |nvarchar(256)  <br/> || 분류에 할당된 값과 이름입니다. 허용되는 값은 다음과 같습니다. <br/>  0 -- 성공 <br/>  1 -- 예상 오류 <br/>  2 - 예기치 않은 오류 <br/> |
   

