---
title: 비즈니스용 Skype Enterprise Voice 계획
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: Enterprise Voice, 지역, 사이트 간 네트워크 링크 및 음성 사용 트래픽 예측을 비롯한 비즈니스용 Skype 서버의 기본 계획에 대한 정보를 제공합니다.
ms.openlocfilehash: 8f10eed8dfcfa7a8878b673ab76fd4d1fd40cc29
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825678"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>비즈니스용 Skype Enterprise Voice 계획
 
Enterprise Voice, 지역, 사이트 간 네트워크 링크 및 음성 사용 트래픽 예측을 비롯한 비즈니스용 Skype 서버의 기본 계획에 대한 정보를 제공합니다.
  
배포 프로세스는 Enterprise Voice 기존 토폴로지, 인프라 및 지원하려는 Enterprise Voice 기능에 따라 달라 습니다. 필수 절차는 선택한 기능에 따라 달라지지만 상위 수준에서 기타 계획 고려 사항을 파악해야 합니다.
  
일반적으로 배포할 사이트 유형 및 수, 지리적 위치, 각 사이트에서의 통화량, 사이트를 연결하는 네트워크 링크 유형, 각 사이트의 음성 기능에 대해 중복성 및 장애 조치 제공 여부 및 기존 PBX 장비 사용 여부 등을 고려합니다. 비즈니스용 Skype 서버 전체를 계획할 때 고려해야 할 특정 고려 사항(예: 고가용성)이 있습니다. 이러한 고려 사항은 필요에 따라 이 섹션 전체의 항목에서 반복하여 설명됩니다.
  
## <a name="sites-and-regions"></a>사이트 및 지역

먼저 토폴로지에서 배포할 사이트와 해당 사이트가 Enterprise Voice 네트워크 지역을 식별합니다. 특히, 각 사이트에 공중 전화망(PSTN) 연결을 제공할 방법을 고려합니다. 관리 편의성 및 물류상의 이유로, 이러한 사이트가 속하는 지역은 중요한 요인이 될 수 있습니다. 게이트웨이를 로컬로 배포할 위치, SBAS(Survivable Branch Appliance)를 배포할 위치 및 SIP 트렁크(로컬 또는 중앙 사이트)를 ITSP(인터넷 전화 통신 서비스 공급자)로 구성할 수 있는 위치를 결정하십시오.
  
## <a name="network-links-between-sites"></a>사이트 간 네트워크 링크

또한 중앙 사이트와 분기 사이트 간의 네트워크 링크에서 예상되는 대역폭 사용을 고려해야 합니다. 사이트 간에 WAN 링크를 배포하거나 배포할 계획인 경우 각 분기 사이트에 게이트웨이를 배포하여 해당 사이트의 사용자에게 DID(로컬 DIRECT Inward Dial) 종료를 제공하는 것이 좋습니다. 탄력적인 WAN 링크는 있지만 해당 WAN 링크의 대역폭이 제한될 것으로 예상된다면 해당 링크에 대해 통화 허용 제어를 구성합니다. 탄력적인 WAN 링크가 없는 경우 분기 사이트에서 1,000명 미만의 사용자를 호스팅하고, 교육된 로컬 비즈니스용 Skype 서버 관리자를 사용할 수 없는 경우 분기 사이트에 Survivable Branch Appliance를 배포하는 것이 좋습니다. 분기 사이트에서 사용자 1,000~5,000명 사이를 호스팅하고, 탄력적인 WAN 연결이 부족하며 교육된 비즈니스용 Skype 서버 관리자를 사용할 수 있는 경우 분기 사이트에 작은 게이트웨이를 사용하여 Survivable Branch Server를 배포하는 것이 좋습니다. 또한 미디어 바이패스를 지원하는 게이트웨이 피어가 있는 경우에는 제한된 링크에 대해 미디어 바이패스를 사용하도록 설정하는 것도 고려하십시오.
  
## <a name="estimating-voice-usage-and-traffic"></a>음성 사용량 및 트래픽 예상

Microsoft Lync Server 2013 계획 도구는 다음 메트릭을 사용하여 각 사이트의 사용자 트래픽과 해당 트래픽을 지원하는 데 필요한 포트 수를 예측합니다.
  
> **경량 트래픽**(매시간 사용자당 PSTN 호출 하나)의 경우 포트당 사용자 15명
> 
> **중간 정도의 트래픽**(매시간 사용자당 PSTN 호출 두 개)의 경우 포트당 사용자 10명
> 
> **높은 트래픽**(매시간 사용자당 PSTN 호출 세 개 이상)의 경우 포트당 사용자 5명
    
포트 수에 따라 필요한 중재 서버 및 게이트웨이의 수가 결정됩니다. 대부분의 조직에서 배포를 고려하는 PSTN(공중 전화망) 게이트웨이의 크기는 포트 2개에서 포트 960개까지 다양합니다. 훨씬 더 큰 게이트웨이도 있지만 이러한 게이트웨이는 주로 전화 서비스 공급자가 사용합니다.
  
예를 들어 사용자 수가 1만 명이고 트래픽은 중간 정도인 조직의 경우 1,000개의 포트가 필요합니다. 필요한 게이트웨이 수는 총 게이트웨이 용량에 따라 결정되는 필요한 총 포트 수와 같습니다.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>구성 요소, 기능 및 옵션 Enterprise Voice

배포 계획에 대한 자세한 내용은 다음 섹션을 Enterprise Voice 참조하세요.
  
- [비즈니스용 Skype Enterprise Voice 구성 요소](components-required-for-enterprise-voice.md)
    
- [비즈니스용 Skype 서버에서 PSTN 연결 계획](pstn-connectivity-0.md)
    
- [비즈니스용 Skype 서버의 고급 Enterprise Voice 네트워크 설정](network-settings-for-advanced-features.md)
    
- [비즈니스용 Skype 서버의 통화 수당 제어 계획](call-admission-control.md)
    
- [비즈니스용 Skype 서버의 응급 서비스 계획](emergency-services.md)
    
- [비즈니스용 Skype의 미디어 우회 계획](media-bypass.md)
    
- [비즈니스용 Skype를 통해 전용 전화선 계획](private-telephone-lines.md)
    
- [비즈니스용 Skype에서 Location-Based 라우팅 계획](location-based-routing.md)
    
- [비즈니스용 Skype의 통화 관리 기능 계획](call-management-features.md)
    
- [비즈니스용 Skype Enterprise Voice 탄력성 계획](enterprise-voice-resiliency.md)
    

