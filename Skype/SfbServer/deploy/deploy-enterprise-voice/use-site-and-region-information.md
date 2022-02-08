---
title: 사이트 및 지역 정보를 비즈니스용 Skype 서버 미디어 우회 전역 설정 구성
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 특정 사이트의 특정 사이트 및 지역에만 사용하도록 미디어 우회를 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: b818d1ba68d17a45c24904a1d313bafde6e6d1d1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391830"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>사이트 및 지역 정보를 비즈니스용 Skype 서버 미디어 우회 전역 설정 구성
 
특정 사이트의 특정 사이트 및 지역에만 사용하도록 미디어 우회를 비즈니스용 Skype 서버 Enterprise Voice. 
  
 이 항목의 단계를 사용하여 미디어 우회에 대한 전역 설정을 구성하는 경우 모든 비즈니스용 Skype 끝점과 트렁크 연결에 대해 미디어 우회를 구성한 피어 간에 양호한 연결이 없다고 가정합니다.
  
> [!NOTE]
> 네트워크 지역 및 네트워크 사이트 정보는 통화 허용 제어와 미디어 바이패스 고급 Enterprise Voice 기능 간에 공유됩니다(둘 다 설정된 경우). 따라서 통화 허용 제어를 이미 구성한 경우 다음 절차에 따라 특별히 미디어 바이패스에 대해 사이트 및 지역 정보를 편집할 필요가 없습니다. 통화 허용 제어에 대한 네트워크 지역 및 사이트를 아직 구성하지 않은 상태에서 미디어 바이패스 설정을 변경하려는 경우에 이 절차의 단계를 따르십시오. 
  
미디어 우회가 제대로 작동하려면 토폴로지 작성기에서 정의한 사이트와 네트워크 지역 및 네트워크 사이트를 구성할 때 정의된 사이트 간에 일관성이 있어야 합니다. 예를 들어 토폴로지 작성기에서 PSTN 게이트웨이만 배포된 것으로 정의한 분기 사이트가 있는 경우 분기 사이트 사용자가 PSTN 통화를 분기 사이트의 PSTN 게이트웨이를 통해 라우팅할 수 있도록 하는 Enterprise Voice 정책을 사용하여 분기 사이트를 구성해야 합니다.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>미디어 바이패스에 대한 사이트 및 지역 정보를 구성하려면

1. 브라우저 창을 열고 관리 URL을 입력하여 관리 비즈니스용 Skype 서버  열 수 있습니다.  
    
2. 왼쪽 탐색 모음에서 **네트워크 구성** 을 클릭합니다.
    
3. 테이블에서 **전역** 구성을 두 번 클릭합니다.
    
4. **전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란을 선택합니다.
    
5. **사이트 및 지역 구성 사용** 을 클릭합니다.
    
6. 필요한 경우 **매핑되지 않은 사이트에 대해 바이패스 사용** 확인란을 선택합니다.
    
    > [!NOTE]
    > 이 확인란은 대역폭 제한이 없는 하나 이상의 큰 사이트(예: 대규모 중앙 사이트)를 같은 지역과 연결했지만 대역폭이 제한된 일부 분기 사이트도 이 지역과 연결한 경우에만 선택합니다. 매핑되지 않은 사이트에 대해 바이패스를 사용하도록 설정하면 모든 사이트와 연결된 모든 서브넷을 지정할 필요 없이 분기 사이트와 연결된 서브넷만 지정하면 되므로 구성이 간소화됩니다. 통화 허용 제어가 설정된 경우에는 이 확인란을 선택하지 않는 것이 좋습니다. 
  
7. **커밋** 을 클릭합니다.
    
그런 다음 네트워크 사이트에 서브넷 연결에 설명된 바와 같이 네트워크 사이트에 서브넷 [을 추가합니다](deploy-network.md#BKMK_AssociateSubnets). 모든 서브넷을 네트워크 사이트와 연결하면 미디어 바이패스 배포가 완료됩니다.
> [!IMPORTANT]
> 네트워크 지역 및 네트워크 사이트를 아직 만들지 않은 경우 미디어 바이패스 배포를 진행하려면 먼저 네트워크 지역과 네트워크 사이트를 만들어야 합니다. 자세한 내용은 [Deploy network regions, sites and subnets in 비즈니스용 Skype](deploy-network.md). 
  
## <a name="see-also"></a>참고 항목

[네트워크 사이트에 서브넷 연결](deploy-network.md#BKMK_AssociateSubnets)

