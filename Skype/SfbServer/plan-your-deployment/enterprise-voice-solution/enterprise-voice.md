---
title: 비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fd8d5867-0ac9-47f8-94f0-1c3ee5e25575
description: 사이트, 지역, 사이트 간 네트워크 링크, 음성 사용량 트래픽 예측 등 비즈니스용 Skype 서버의 Enterprise Voice 계획 기본 사항입니다.
ms.openlocfilehash: fdc653404f6b7182086af00e6e788a1d3bd421eb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187695"
---
# <a name="plan-for-enterprise-voice-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 계획
 
사이트, 지역, 사이트 간 네트워크 링크, 음성 사용량 트래픽 예측 등 비즈니스용 Skype 서버의 Enterprise Voice 계획 기본 사항입니다.
  
엔터프라이즈 음성에 대 한 배포 프로세스는 지원 하려는 기존 토폴로지, 인프라 및 엔터프라이즈 음성 기능에 따라 달라 집니다. 필요한 절차는 어떤 기능을 선택 하느냐에 따라 다르지만 상위 수준에서 수행 해야 하는 다른 계획 고려 사항이 있습니다.
  
일반적으로 배포 하려는 사이트의 종류 및 개수와 지리적 위치, 각 사이트의 통화 볼륨, 사이트를 연결 하는 네트워크 링크 유형, 각각에 대 한 음성 기능에 대 한 중복성 및 장애 조치 (failover) 제공 여부를 고려해 야 합니다. 사이트 및 기존 PBX 장비 사용 여부 비즈니스용 Skype 서버를 전체적으로 계획할 때 고려해 야 하는 중요 한 고려 사항이 있습니다. 이러한 고려 사항은 필요한 경우이 섹션의 항목에서 설명 합니다.
  
## <a name="sites-and-regions"></a>사이트 및 지역

먼저 엔터프라이즈 음성과 해당 사이트가 속한 네트워크 지역을 배포할 토폴로지에서 사이트를 식별 합니다. 특히, 각 사이트에 대 한 PSTN (공개 교환 전화 네트워크) 연결을 제공 하는 방법을 고려 하세요. 관리 효율성 및 logistical 이유로 이러한 사이트가 속한 지역은 결정 요인이 될 수 있습니다. 게이트웨이가 로컬로 배포 되는 위치 (Survivable Branch 기기 (SBAs)가 배포 되 고 SIP trunks (로컬 또는 중앙 사이트에서)를 인터넷 전화 통신 서비스 공급자 (ITSP)에 구성할 수 있는 위치를 결정 합니다.
  
## <a name="network-links-between-sites"></a>사이트 간 네트워크 링크

또한 중앙 사이트와 해당 지점 사이트 간의 네트워크 연결에 대해 예상 되는 대역폭 사용량을 고려해 야 합니다. 사이트 간 WAN 연결을 보유 하 고 있거나 배포 하려는 경우 각 지점 사이트에서 게이트웨이를 배포 하 여 해당 사이트의 사용자에 대 한 로컬 직접 안쪽 다이얼 (의) 종료를 제공 하는 것이 좋습니다. 복원성 WAN 링크가 있지만 WAN 링크의 대역폭이 제한 될 가능성이 높은 경우 해당 링크에 대 한 통화 허용 제어를 구성 합니다. 회복성 있지 않은 WAN 연결이 없는 경우, 지점 사이트에서 1000 사용자 보다 적은 수의 호스트를 보유 하 고 있으며, 로컬의 비즈니스용 Skype Server 관리자가 제공 되지 않는 경우, 지점 사이트에서 Survivable Branch 기기를 배포 하는 것이 좋습니다. 지점 사이트에서 1000와 5000 사용자 간 호스팅, 복원성 WAN 연결이 부족 하 고, 비즈니스용 Skype Server 관리자가 교육을 받을 수 있는 경우, 지점 사이트에 small gateway를 사용 하 여 Survivable Branch 서버를 배포 하는 것이 좋습니다. 미디어 바이패스를 지 원하는 게이트웨이 피어가 있는 경우 제한 된 링크에서 미디어 바이패스를 사용 하도록 설정 하는 것도 고려해 야 합니다.
  
## <a name="estimating-voice-usage-and-traffic"></a>음성 사용량 및 트래픽 예상

Microsoft Lync Server 2013, 계획 도구는 다음 메트릭을 사용 하 여 각 사이트의 사용자 트래픽과 해당 트래픽을 지 원하는 데 필요한 포트 수를 계산 합니다.
  
> **가벼운 트래픽** (사용자 당 한 시간에 한 PSTN 통화), 그림 15 포트 당 사용자.
> 
> **중간 규모의 소통량** (사용자 당 2 시간 당 PSTN 통화), 그림 10 사용자/포트
> 
> **사용량이 많은 트래픽** (3 개 이상의 PSTN 사용자 통화/시간)은 포트 당 5 명의 사용자를 위한 것입니다.
    
그런 다음 포트의 수에 따라 필요한 중재 서버 및 게이트웨이 수가 결정 됩니다. 대부분의 조직이 2 개 포트에서 960 포트로의 크기를 배포 하는 것으로 간주 하는 PSTN (공개 전화망 네트워크) 게이트웨이 (더 많은 게이트웨이가 있지만 이러한 게이트웨이는 주로 전화 통신 서비스 공급자가 사용 합니다.)
  
예를 들어 1만 사용자 및 중간 트래픽을 포함 하는 조직에는 1000 포트가 필요 합니다. 필요한 게이트웨이 수는 게이트웨이의 총 용량에 따라 결정 되는 데 필요한 총 포트 수와 같습니다.
  
## <a name="components-features-and-options-of-enterprise-voice"></a>엔터프라이즈 음성의 구성 요소, 기능 및 옵션

엔터프라이즈 음성 배포 계획에 대 한 자세한 내용은 다음 섹션을 참조 하세요.
  
- [비즈니스용 Skype 서버에서 엔터프라이즈 음성에 필요한 구성 요소](components-required-for-enterprise-voice.md)
    
- [비즈니스용 Skype 서버에서 PSTN 연결 계획](pstn-connectivity-0.md)
    
- [비즈니스용 Skype 서버의 고급 엔터프라이즈 음성 기능에 대 한 네트워크 설정](network-settings-for-advanced-features.md)
    
- [비즈니스용 Skype 서버에서 통화 허용 제어 계획](call-admission-control.md)
    
- [비즈니스용 Skype 서버에서 응급 서비스 계획](emergency-services.md)
    
- [비즈니스용 Skype에서 미디어 바이패스 계획](media-bypass.md)
    
- [비즈니스용 Skype를 사용 하 여 사설 전화선에 대 한 계획](private-telephone-lines.md)
    
- [비즈니스용 Skype의 위치 기반 라우팅 계획](location-based-routing.md)
    
- [비즈니스용 Skype의 통화 관리 기능 계획](call-management-features.md)
    
- [비즈니스용 Skype 서버에서 엔터프라이즈 음성 복원 계획](enterprise-voice-resiliency.md)
    

