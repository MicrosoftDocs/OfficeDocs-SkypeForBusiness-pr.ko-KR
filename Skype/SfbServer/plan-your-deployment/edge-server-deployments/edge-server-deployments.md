---
title: 비즈니스용 Skype 서버에서 Edge 서버 배포 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype Server Edge 환경에 대 한 계획입니다. 이 항목에서는 Edge 개념을 소개 하 고 자세한 내용으로 구성 하는 데 도움이 되는 정보를 제공 합니다.'
ms.openlocfilehash: f19f00aab393ed94735f47f2e66ab0a2869d2d7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803368"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 Edge 서버 배포 계획
 
**요약:** 비즈니스용 Skype Server Edge 환경에 대 한 계획 이 항목에서는 Edge 개념을 소개 하 고 자세한 내용으로 구성 하는 데 도움이 되는 정보를 제공 합니다.
  
내부적으로 제대로 작동 하는 비즈니스용 Skype 서버 환경이 있는 경우 다음 단계는 환경에 대 한 Edge 서버 또는 Edge 풀을 소개 하는 것입니다. 이 역할은 비즈니스용 Skype 서버에서 제공 하는 서비스를 내부 네트워크 외부의 사용자가 사용할 수 있도록 하려는 경우에 중요 합니다. 다음과 같은 항목이 포함 될 수 있습니다.
  
- 원격 사용자: 일시적으로 또는 지속적으로 진행 중인 오프 사이트용 직원입니다.
    
- 페더레이션 사용자: 파트너 조직의 직원
    
- 모바일 사용자.
    
- 모임 및 프레젠테이션에 초대 하려는 잠재 고객, 파트너 및 익명 사용자도 포함 합니다.
    
Edge 서버에서 제공 하는 외부 사용자 액세스를 사용 하 여 모든 작업을 수행 합니다. 내부 사용자는 비즈니스용 Skype 서버 배포에 의해 호스팅되는 다음 서비스를 즐길 수 있습니다.
  
- 통신 IM 및 현재 상태: 권한이 있는 외부 사용자는 메신저 대화 및 회의에 참가할 수 있습니다. 다른 사용자에 대 한 현재 상태 정보를 얻을 수 있습니다 (현재 상태 정보를 받는 사람). 공용 IM 공급자를 사용 하는 경우에는 단체 회의를 할 수 없으며,이는 완전히 피어 투 피어 통신입니다. 하지만 SIP와 XMPP 프로토콜은 모두 지원 됩니다.
    
- 오디오/비디오 (A/V) 회의: 권한이 있는 외부 사용자는 비즈니스용 Skype 서버 오디오 및 비디오 회의에 참가할 수 있습니다.
    
- 웹 회의: 권한이 있는 외부 사용자는 비즈니스용 Skype 컨퍼런스에 참가할 수 있습니다. 원할 경우 원격 사용자, 페더레이션 사용자, 익명 사용자에 대 한 참여를 설정할 수도 있습니다. 공용 메신저 사용자는 회의에 참가할 수 없습니다. 또한 이러한 사용자가 응용 프로그램 및 데스크톱 공유에 참여할 수 있도록 하는 옵션과 모임 이끌이 또는 발표자 역할을 할 수도 있습니다.
    
모바일 장치 액세스는 엔터프라이즈 음성과 마찬가지로 지원 됩니다. 해당 사용자에 게 사용 권한을 부여 하려는 경우 익명 사용자를 포함 하 여 참가 하도록 할 모임에 외부 사용자를 초대할 수 있습니다.
  
조직에서 요구 하는 것 처럼 생각 되는 경우에는 Edge 환경에 대 한 계획을 수립할 때 큰 도움이 될 것입니다. 자세한 내용은 아래에 나열 된 항목을 참조 하세요.

> [!NOTE]
> XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 자세한 내용은 [XMPP 페더레이션 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조 하세요. 
  
## <a name="planning-topics"></a>계획 항목:

계획 문서는 다음과 같습니다.
  
- [비즈니스용 Skype 서버 2015의 Edge 서버 시스템 요구 사항](system-requirements.md)
    
- [비즈니스용 Skype 서버 2015의 Edge 서버 환경 요구 사항](edge-environmental-requirements.md)
    
- [비즈니스용 Skype Server 2015의 Edge 서버 시나리오](scenarios.md)
    

