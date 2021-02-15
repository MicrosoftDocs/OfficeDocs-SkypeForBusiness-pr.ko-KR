---
title: 비즈니스용 Skype 서버에서 통화 제어 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: CAC(통화 가능 제어)는 사용 가능한 대역폭을 기반으로 실시간 세션을 설정하여 정체된 네트워크의 사용자에 대한 오디오/비디오 품질을 저해할 수 있는지 여부를 결정하는 솔루션입니다.
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836888"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 통화 제어 배포
 
CAC(통화 가능 제어)는 사용 가능한 대역폭을 기반으로 실시간 세션을 설정하여 정체된 네트워크의 사용자에 대한 오디오/비디오 품질을 저해할 수 있는지 여부를 결정하는 솔루션입니다. 자세한 내용은 비즈니스용 Skype 서버의 [통화 요금제 요금제(을)를 참조하세요.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
### <a name="to-deploy-call-admission-control"></a>통화 수당 제어를 배포합니다.

1.  예제: 비즈니스용 Skype 서버에서 통화 제어에 대한 요구 사항 수집에 설명된 엔터프라이즈 네트워크 토폴로지에 필요한 모든 [정보를 수집합니다.](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md)
    
2. 아직 수행하지 않은 경우 네트워크 지역 및 사이트를 정의하고 서브넷을 네트워크 사이트에 연결해야 합니다. 자세한 내용은 비즈니스용 Skype에서 네트워크 지역, 사이트 및 [서브넷 배포를 참조하세요.](deploy-network.md)
    
3. 비즈니스용 Skype 서버에서 대역폭 정책 프로필 만들기에 자세히 설명된 대역폭 정책 프로필 [만들기](create-bandwidth-policy-profiles.md)
    
4. 비즈니스용 Skype 서버에서 네트워크 지역 링크 만들기에 자세히 설명된 네트워크 [지역 링크를 만드시다.](create-network-region-links.md)
    
5. 비즈니스용 Skype 서버에서 네트워크 지역 간 경로 만들기에 자세히 설명된 네트워크 지역 [간 경로를 만드시다.](create-network-interregional-routes.md)
    
6. 비즈니스용 Skype 서버에서 네트워크 교차 정책 만들기에 자세히 설명된 네트워크 교차 [정책을 만드시다.](create-network-intersite-policies.md)
    
7. 비즈니스용 Skype 서버에서 통화 입력 제어를 사용하도록 설정하는 데 자세히 설명된 통화 수치 [제어를 사용하도록 설정할 수 있습니다.](enable-call-admission-control.md)
    
8. 몇 가지 최종 설정을 확인하여 모든 설정이 올바르게 설정되어 있는지 확인합니다. 자세한 내용은 통화 제어 배포: 비즈니스용 Skype 서버의 최종 검사 [목록을 참조하세요.](final-checklist.md)
    

