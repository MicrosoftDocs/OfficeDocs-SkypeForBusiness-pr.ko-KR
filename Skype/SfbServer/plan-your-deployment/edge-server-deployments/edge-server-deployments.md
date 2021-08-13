---
title: 에지 서버 비즈니스용 Skype 서버 배포 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: '요약: 에지 환경을 비즈니스용 Skype 서버 계획합니다. 이 항목에서는 Edge 개념에 대해 소개하고 좀 더 자세한 주제를 통해 구성할 수 있습니다.'
ms.openlocfilehash: 5a0541eabdc0f3db9a8fb23eaa9d20b0792750263e8d576bcf11e6d96c0fd2d1
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320051"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>에지 서버 비즈니스용 Skype 서버 배포 계획
 
**요약:** 에지 비즈니스용 Skype 서버 계획합니다. 이 항목에서는 Edge 개념에 대해 소개하고 좀 더 자세한 주제를 통해 구성할 수 있습니다.
  
내부적으로 비즈니스용 Skype 서버 환경이 있는 경우 다음 단계는 에지 서버 또는 에지 풀을 환경에 도입하는 것입니다. 내부 네트워크 외부에 있는 사용자가 비즈니스용 Skype 서버 서비스를 사용하려는 경우 이 역할이 중요합니다. 이러한 데이터에는 다음이 포함됩니다.
  
- 원격 사용자: 일시적으로 또는 지속적인 방식으로 오프사이트에 있는 직원입니다.
    
- 페더타 사용자: 파트너 조직의 직원.
    
- 모바일 사용자.
    
- 모임 및 프레젠테이션에 초대하려는 잠재 고객, 파트너 및 익명 사용자
    
에지 서버에서 제공하는 외부 사용자 액세스는 이러한 모든 문제가 발생하도록 허용합니다. 내부 사용자는 사용자 배포에서 호스팅하는 다음 서비스를 비즈니스용 Skype 서버 있습니다.
  
- 통신을 위한 IM 및 현재 상태: 권한이 부여된 외부 사용자는 IM 대화 및 회의에 참가할 수 있습니다. 다른 사용자에 대한 현재 상태 정보를 얻을 수 있습니다(현재 상태 정보를 얻음). 공용 IM 공급자(엄격히 피어 투 피어 통신)를 사용하는 경우 다국어 회의를 할 수 없습니다. 그러나 SIP 및 XMPP 프로토콜이 모두 지원됩니다.
    
- A/V(오디오/비디오) 회의: 권한이 부여된 외부 사용자는 오디오 비즈니스용 Skype 서버 회의에 참가할 수 있습니다.
    
- 웹 회의: 권한이 부여된 외부 사용자는 비즈니스용 Skype 회의에 참가할 수 있습니다. 원할 경우 원격 사용자, 페더타인 사용자 및 익명 사용자에 대해 참가를 사용하도록 설정할 수도 있습니다. 공용 IM 사용자는 회의에 참가할 수 없습니다. 이러한 사용자가 응용 프로그램 및 데스크톱 공유에 참여하고 모임 이끌이 또는 발표자 역할을 하게 하는 옵션도 있습니다.
    
모바일 장치 액세스는 모바일 장치와 Enterprise Voice. 외부 사용자를 참석하려는 모임에 초대할 수 있습니다( 익명 사용자에게도 권한을 부여하려는 경우).
  
조직에 필요한 경우 에지 환경을 계획하는 것이 배포에 큰 도움이 될 것입니다. 자세한 내용은 아래 항목을 참조하세요.

> [!NOTE]
> XMPP 게이트웨이 및 xxies는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. 자세한 [내용은 XMPP 페더링 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조하세요. 
  
## <a name="planning-topics"></a>계획 항목:

계획 문서는 다음을 다합니다.
  
- [비즈니스용 Skype 서버 에지 서버 시스템 요구 사항](system-requirements.md)
    
- [2015년 에지 비즈니스용 Skype 서버 요구 사항](edge-environmental-requirements.md)
    
- [2015년 비즈니스용 Skype 서버 에지 서버 시나리오](scenarios.md)
    

