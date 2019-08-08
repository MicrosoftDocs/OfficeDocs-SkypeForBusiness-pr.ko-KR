---
title: 비즈니스용 Skype 서버에서 미디어 바이패스를 구성 하 여 항상 중재 서버를 우회 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 비즈니스용 Skype Server Enterprise Voice에서 항상 중재 서버를 우회 하도록 미디어 바이패스를 사용 하도록 설정 합니다.
ms.openlocfilehash: dfffda1130fc1fb119e6cbf5d9b12af766b9c038
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234036"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>비즈니스용 Skype 서버에서 미디어 바이패스를 구성 하 여 항상 중재 서버를 우회 합니다.
 
비즈니스용 Skype Server Enterprise Voice에서 항상 중재 서버를 우회 하도록 미디어 바이패스를 사용 하도록 설정 합니다. 
  
 이 항목의 단계를 사용 하 여 미디어 바이패스에 대 한 전역 설정을 구성 하는 경우 비즈니스용 Skype 끝점 및 트렁크 연결에서 미디어 바이패스를 구성한 피어 간에 연결이 양호한 것으로 가정 합니다.
  
비즈니스용 Skype 끝점 및 모든 피어가 미디어 바이패스에 대해 사용 하도록 설정 되어 있는 중재 서버와의 연결이 적절 하지 않은 경우에는 사이트 및 지역 정보를 사용 하도록 전역 미디어 우회 설정을 구성 해야 합니다. 미디어 바이패스를 사용 하는 경우 이를 통해 미디어가 중재 서버를 우회 하는 시기를 결정 하는 데 더 많은 제어가 가능 합니다. 이렇게 하려면 [비즈니스용 Skype 서버에서 미디어 구성 건너뛰기 전역 설정 단계를 사용 하 여 사이트 및 지역 정보를 사용 하](use-site-and-region-information.md) 고 [서브넷을 네트워크 사이트와 연결](deploy-network.md#BKMK_AssociateSubnets) 합니다.
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>항상 중재 서버를 우회 하기 위해 미디어 우회를 전역적으로 사용 하도록 설정 하려면

1. 비즈니스용 Skype Server 제어판을 엽니다.
    
2. 왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.
    
3. 목록에서 **전역** 구성을 두 번 클릭 합니다.
    
4. **전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란을 선택 합니다.
    
5. **항상 무시**를 클릭 합니다.
    
6. **커밋**을 클릭합니다.
    
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype에서 미디어 바이패스 계획](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[비즈니스용 Skype 서버에서 미디어 바이패스 배포](deploy-media-bypass.md)

