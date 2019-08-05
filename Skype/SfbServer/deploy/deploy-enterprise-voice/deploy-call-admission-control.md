---
title: 비즈니스용 Skype 서버에서 통화 허용 제어 배포
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: CAC (통화 허용 제어)는 사용 가능한 대역폭을 기준으로 실시간 세션을 설정할 수 있는지를 결정 하는 솔루션으로, 혼잡 네트워크 사용자에 게 좋지 않은 오디오/비디오 품질을 방지 하는 데 도움이 됩니다.
ms.openlocfilehash: 7f7f8dee4e25061533564ce517f797281bef042e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189033"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 통화 허용 제어 배포
 
CAC (통화 허용 제어)는 사용 가능한 대역폭을 기준으로 실시간 세션을 설정할 수 있는지를 결정 하는 솔루션으로, 혼잡 네트워크 사용자에 게 좋지 않은 오디오/비디오 품질을 방지 하는 데 도움이 됩니다. 자세한 내용은 비즈니스용 [Skype 서버의 통화 허용 제어 계획](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)을 참조 하세요.
  
### <a name="to-deploy-call-admission-control"></a>통화 허용 제어 배포

1.  [예를 들어 비즈니스용 Skype 서버에서 통화 허용 제어에 대 한 요구 사항 수집](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)을 참조 하 여 엔터프라이즈 네트워크 토폴로지에 필요한 모든 정보를 수집 합니다.
    
2. 아직 수행 하지 않은 경우 네트워크 지역과 사이트를 정의 하 고 서브넷을 네트워크 사이트와 연결 해야 합니다. 자세한 내용은 [비즈니스용 Skype에서 네트워크 지역, 사이트 및 서브넷 배포](deploy-network.md)를 참조 하세요.
    
3. [비즈니스용 Skype 서버에서 대역폭 정책 프로필 만들기](create-bandwidth-policy-profiles.md) 에 자세히 설명 된 대로 대역폭 정책 프로필 만들기
    
4. [비즈니스용 Skype 서버의 네트워크 지역 링크 만들기](create-network-region-links.md)에 자세히 설명 된 대로 네트워크 지역 링크를 만듭니다.
    
5. [비즈니스용 Skype 서버의 네트워크 간 경로 만들기](create-network-interregional-routes.md)에 자세히 설명 된 대로 네트워크 교차 영역 경로를 만듭니다.
    
6. [비즈니스용 Skype 서버의 네트워크 사이트 간 정책 만들기](create-network-intersite-policies.md)에 자세히 설명 된 대로 네트워크 사이트 간 정책을 만듭니다.
    
7. [비즈니스용 Skype 서버에서 통화 허용 제어 사용](enable-call-admission-control.md)에 자세히 설명 된 대로 통화 허용 제어 기능을 사용 하도록 설정 합니다.
    
8. 일부 최종 설정을 확인 하 여 모든 항목이 올바르게 설정 되어 있는지 확인 합니다. 자세한 내용은 [통화 허용 제어 배포: 비즈니스용 Skype 서버에 대 한 최종 검사 목록](final-checklist.md)입니다.
    

