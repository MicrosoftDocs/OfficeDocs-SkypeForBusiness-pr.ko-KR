---
title: 미디어 구성 비즈니스용 Skype 서버의 전역 설정 무시 사이트 및 지역 정보 사용
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 비즈니스용 Skype Server Enterprise Voice에서 특정 사이트 및 지역에 대해서만 미디어 바이패스를 사용 하도록 구성 합니다.
ms.openlocfilehash: 3a9dc907dd516151e8b6ddd509a43b49c87e3b9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197152"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>미디어 구성 비즈니스용 Skype 서버의 전역 설정 무시 사이트 및 지역 정보 사용
 
비즈니스용 Skype Server Enterprise Voice에서 특정 사이트 및 지역에 대해서만 미디어 바이패스를 사용 하도록 구성 합니다. 
  
 이 항목의 단계를 사용 하 여 미디어 바이패스에 대 한 전역 설정을 구성 하는 경우, 모든 비즈니스용 Skype 끝점과 사용자의 트렁크 연결에서 미디어 바이패스를 구성한 피어 사이에는 적절 하 게 연결 되지 않은 것으로 가정 합니다.
  
> [!NOTE]
> 네트워크 지역 및 네트워크 사이트 정보는 통화 허용 제어와 미디어 건너뛰기 고급 Enterprise Voice 기능을 모두 사용 하도록 설정 되어 있는 경우 공유 됩니다. 따라서 통화 허용 제어를 이미 구성한 경우에는 다음 절차를 사용 하 여 미디어 바이패스에 대 한 사이트 및 지역 정보를 편집할 필요는 없습니다. 통화 허용 제어에 대해 아직 네트워크 지역과 사이트를 구성 하지 않은 경우 미디어 우회 설정을 변경 하려면이 절차의 단계를 따릅니다. 
  
미디어 bypass이 제대로 작동 하려면 토폴로지 작성기에 정의 된 사이트와 네트워크 지역 및 네트워크 사이트를 구성할 때 정의 된 것과 동일한 사이트가 일치 해야 합니다. 예를 들어, PSTN 게이트웨이만 배포 된 상태로 토폴로지 작성기에 정의한 지점 사이트를 사용 하는 경우에는 지점 사이트 사용자가 pstn을 통해 라우팅되는 PSTN 통화를 할 수 있는 엔터프라이즈 음성 정책으로 해당 지점 사이트를 구성 해야 합니다. 지사 사이트의 게이트웨이입니다.
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>미디어 바이패스에 대 한 사이트 및 지역 정보를 구성 하려면

1. 브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.  
    
2. 왼쪽 탐색 모음에서 **네트워크 구성을**클릭 합니다.
    
3. 표에서 **전역** 구성을 두 번 클릭 합니다.
    
4. **전역 설정 편집** 페이지에서 **미디어 무시 사용** 확인란을 선택 합니다.
    
5. **사이트 및 지역 구성 사용을**클릭 합니다.
    
6. 필요한 경우 **매핑되지 않은 사이트에 바이패스 사용** 확인란을 선택 합니다.
    
    > [!NOTE]
    > 대역폭 제약 조건이 없는 (예: 대규모 중앙 사이트) 동일한 지역과 연결 된 대규모 사이트가 하나 이상 있는 경우에만이 확인란을 선택 하 고, 대역폭이 있는 동일한 지역에 연결 된 일부 지점 사이트도 사항이. 매핑되지 않은 사이트에 대해 바이패스를 사용 하도록 설정 하면 모든 사이트와 연결 된 모든 서브넷을 지정할 필요 없이 분기 사이트와 연결 된 서브넷만 지정 하는 구성이 간소화 됩니다. 통화 허용 제어를 사용 하는 경우이 확인란을 선택 하지 않는 것이 좋습니다. 
  
7. **커밋**을 클릭합니다.
    
다음으로, [서브넷을 네트워크 사이트에 연결](deploy-network.md#BKMK_AssociateSubnets)의 설명에 따라 네트워크 사이트에 서브넷을 추가 합니다. 모든 서브넷을 네트워크 사이트에 연결한 후에는 미디어 바이패스 배포가 완료 됩니다.
> [!IMPORTANT]
> 아직 네트워크 지역과 네트워크 사이트를 만들지 않은 경우에는 먼저 해당 지역을 만들어야 미디어 건너뛰기 배포를 진행할 수 있습니다. 자세한 내용은 [비즈니스용 Skype에서 네트워크 지역, 사이트 및 서브넷 배포](deploy-network.md)를 참조 하세요. 
  
## <a name="see-also"></a>참고 항목

[네트워크 사이트에 서브넷 연결](deploy-network.md#BKMK_AssociateSubnets)

