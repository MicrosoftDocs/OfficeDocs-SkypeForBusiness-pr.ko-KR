---
title: 비즈니스용 Skype에서 통화 공원에 대 한 정규화 규칙 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: 비즈니스용 Skype Server Enterprise Voice의 통화 공원에 대 한 정규화 규칙에 대해 알아보세요.
ms.openlocfilehash: 36e9a91ff1269caffb8eab5be9a2c681d3244b31
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197153"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>비즈니스용 Skype에서 통화 공원에 대 한 정규화 규칙 확인
 
비즈니스용 Skype Server Enterprise Voice의 통화 공원에 대 한 정규화 규칙에 대해 알아보세요.
  
통화 공원 orbits는 정규화 해서는 안 됩니다. 전화 걸기 계획을 검사 하 여 궤도 번호가 정규화 되지 않았는지 확인 합니다. Orbits 정규화 되지 않도록 추가 정규화 규칙을 만들어야 하는 경우 비즈니스용 [Skype 서버에서 다이얼 플랜 만들기 또는 수정](dial-plans.md) 의 절차에 따라 새 정규화 규칙을 정의 하 여 **일치 시킬 패턴** 을 지정 합니다. 궤도 범위와 **번역 패턴** 을 **$1**으로 식별 합니다. 예를 들어 통화 공원 궤도 범위가 7000-7999 이면 **일치 하는 패턴** 은 **^{3}(7 \ d) $** 이 고 **번역 패턴** 은 **$1**입니다.
  
> [!IMPORTANT]
> 다이얼 플랜의 기본 정규화 규칙에 **^ (\d\*)** 이 포함 되어 있지 않은지 확인 합니다. 그렇지 않으면 통화 공원 표준화 규칙이 실행 되지 않습니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버에서 다이얼 플랜 만들기 또는 수정](dial-plans.md)

