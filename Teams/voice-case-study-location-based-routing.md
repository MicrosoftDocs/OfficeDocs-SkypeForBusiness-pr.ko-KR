---
title: 'Teams Contoso 사례 연구: 위치 기반 라우팅'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Teams 기업에 대한 음성 사례 연구: 위치 기반 라우팅'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 974053f3e438ecaee3f9eb876eb99e2cf6e40d151be802acb31183620eabc583
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54319641"
---
# <a name="contoso-case-study-location-based-routing"></a>Contoso 사례 연구: Location-Based 라우팅

Location-Based LBR(라우팅)은 통화를 배치하거나 받을 때 사용자의 실제 위치와 정책에 따라 수신자 우회를 제한하는 기능입니다.  

## <a name="overview"></a>개요

Contoso에는 장거리 통화 비용을 절감하기 위해 PSTN(공용 전환 전화 네트워크) 공급자를 우회하는 것이 불법인 두 개의 사무실이 있습니다. 본점은 본점 및 두 번째 사무실에서 사용하는 인터넷 연결이 있습니다. 각 사무실에는 PSTN 캐리어에 연결된 자체 SBC(세션 테두리 컨트롤러)가 있습니다.  
 
이 나라에서 Contoso는 해당 배포에 대해 LBR을 비즈니스용 Skype했습니다. 에 대한 LBR을 구성하는 Teams 결정하기 위해 Contoso는 직접 라우팅에 Location-Based 계획 Location-Based [를 읽습니다.](location-based-routing-plan.md) Contoso는 호출을 Teams 비즈니스용 Skype 수 있는 경우, 수신할 수 있는 경우, PSTN 호출을 사용자로 전송할 수 있는 Teams 경우, 다른 사용자를 PSTN 호출로 Teams 수 있는 경우와 동일한 시나리오를 따르는 것으로 결정했습니다.  

비즈니스용 Skype, LBR은 PSTN 캐리어에 연결하는 SBC(세션 테두리 컨트롤러) SIP 트렁크로 구성됩니다. 이 SBC의 경우 Contoso는 인증된 [SBC](direct-routing-border-controllers.md) 목록을 검토하고 배포된 SBC가 직접 라우팅에 대해 인증되지만 Media Bypass에 대해 인증되지 않은 것으로 결정했습니다. LBR을 지원하려면 직접 라우팅을 SBC 현장에 구성해야 합니다. 로컬 인터넷을 시작해야 합니다. 미디어 우회를 위해 SBC를 구성해야 합니다. 이 정보를 바탕으로 Contoso는 다음을 결정했다.

- 기존 SBC가 Media bypass에 Teams 때까지 LBR의 사용이 지연됩니다.   

- Contoso는 직접 경로에 기본 사이트 SBC를 사용하기로 Office 365.  기본 사이트 SBC는 원격 사이트의 프록시 SBC입니다.  

- Contoso는 인도에 있는 타사 컨설턴트가 국가의 전화 통신 회사와의 LBR 구성 인증을 지원하기 위해 사용했습니다.  

- 사무실 외부에서 PSTN 통화를 하는 사용자를 지원하기 위해 회사에서 발급한 휴대폰을 해당 직원에게 제공했습니다. 

다음 다이어그램은 라우팅이 필요한 전화 통신 규정이 있는 국가에 대한 배포 전후 Location-Based 보여 니다.

**원래 배포**

![상태 앞에 보여진 다이어그램입니다.](media/voice-case-study-5.png)

**직접 라우팅을 통해 배포**

![상태 전에 보여진 다이어그램 2.](media/voice-case-study-6.png)


## <a name="configuration"></a>구성: 

에서 네트워크 구성 요소를 Teams Contoso는 클라우드 음성 기능에 대한 네트워크 토폴로지 관리의 지침을 [따릅니다.](manage-your-network-topology.md) Contoso는 다음 단계를 완료하여 라우팅을 Location-Based 완료했습니다. 

- 네트워크 지역 정의 - 하나의 네트워크 지역이 정의됩니다. 

- 네트워크 사이트 정의 - 두 개의 네트워크 사이트가 정의되었습니다. 지역의 각 사무실 위치에 대한 하나의 사이트입니다.

- 네트워크 서브넷 정의 - 사무실 위치 내의 각 층에는 유선 및 무선 네트워크에 대한 자체 서브넷이 있습니다. 이 구성으로 인해 Contoso에 대한 서브넷이 20개나 됩니다. 

- 신뢰할 수 있는 IP 주소 정의 - SBC의 외부 연결 IP 주소가 신뢰할 수 있는 IP 주소에 추가되었습니다.  

