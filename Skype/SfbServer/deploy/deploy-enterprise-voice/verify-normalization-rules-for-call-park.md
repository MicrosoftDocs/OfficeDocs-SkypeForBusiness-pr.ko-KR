---
title: 2016년 8월 통화 파크에 대한 정규화 비즈니스용 Skype
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 2016년 8월 통화 파크의 정규화 규칙에 비즈니스용 Skype 서버 Enterprise Voice.
---

# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>2016년 8월 통화 파크에 대한 정규화 비즈니스용 Skype
 
2016년 8월 통화 파크의 정규화 규칙에 비즈니스용 Skype 서버 Enterprise Voice.
  
통화 파크 궤도는 정규화할 수 없습니다. 다이얼 플랜에서 궤도 번호가 정규화되지 않은지 확인할 수 있습니다. 궤도가 정규화되지 않도록 추가 정규화 규칙을 만들어야 하는 경우 비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정의 절차 [](dial-plans.md) 에 따라 패턴이 궤도 범위를 식별하고 변환 패턴이 **$1** 이 되어야 새 정규화 규칙을 정의  합니다. 예를 들어 통화 파크 궤도 범위가 7000 -7999이면 일치할 **패턴** 은 **^(7\d)$이고{3}** 변환 패턴은 **$1입니다**.
  
> [!IMPORTANT]
> 다이얼 플랜의 기본 정규화 규칙에 **^(\d)가 포함되어 있지 않은지\* 확인하십시오**. 그렇지 않으면 통화 파크 정규화 규칙이 실행되지 않습니다.
  
## <a name="see-also"></a>참고 항목

[2013에서 다이얼 플랜을 만들거나 비즈니스용 Skype 서버](dial-plans.md)

