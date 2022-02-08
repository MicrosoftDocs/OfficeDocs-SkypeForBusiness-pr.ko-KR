---
title: 중재 서버를 비즈니스용 Skype 서버 우회하도록 미디어 우회 구성
ms.reviewer: ''
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
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 미디어 우회에서 중재 서버를 항상 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: ef6bf5b68e5d333b1786b6fc6237784b4f5395f0
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62392240"
---
# <a name="configure-media-bypass-in-skype-for-business-server-to-always-bypass-the-mediation-server"></a>중재 서버를 비즈니스용 Skype 서버 우회하도록 미디어 우회 구성
 
미디어 우회에서 중재 서버를 항상 비즈니스용 Skype 서버 Enterprise Voice. 
  
 이 항목의 단계를 사용하여 미디어 우회에 대한 전역 설정을 구성하는 경우 트렁크 연결에 대해 미디어 우회를 구성한 피어와 비즈니스용 Skype 끝점 간의 연결이 양호한 것으로 가정합니다.
  
각 트렁크 연결이 미디어 우회를 사용하도록 설정된 중재 서버에 대한 모든 피어와 비즈니스용 Skype 끝점 간에 양호한 연결이 없는 경우 미디어 우회를 사용할 때 사이트 및 지역 정보를 사용하도록 전역 미디어 우회 설정을 구성해야 합니다. 이렇게 하면 미디어가 중재 서버를 바이패스하는 경우를 보다 정밀하게 제어할 수 있습니다. 이렇게하려면 사이트 및 지역 정보를 사용하도록 비즈니스용 Skype 서버 미디어 우회 전역 설정 구성 및 네트워크 사이트에 서브[넷](use-site-and-region-information.md) 연결의 단계를 사용합니다.[](deploy-network.md#BKMK_AssociateSubnets)
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>항상 중재 서버를 바이패스하도록 전역적으로 미디어 바이패스를 설정하려면

1. 제어판을 비즈니스용 Skype 서버 를 니다.
    
2. 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.
    
3. 목록에서 **전역** 구성을 두 번 클릭합니다.
    
4. **전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란을 선택합니다.
    
5. **항상 바이패스** 를 클릭합니다.
    
6. **커밋** 을 클릭합니다.
    
## <a name="see-also"></a>참고 항목

[2013의 미디어 우회 비즈니스용 Skype](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[미디어 우회를 비즈니스용 Skype 서버](deploy-media-bypass.md)

