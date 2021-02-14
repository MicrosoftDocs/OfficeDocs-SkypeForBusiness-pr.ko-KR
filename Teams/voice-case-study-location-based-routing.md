---
title: Teams 음성 Contoso 사례 연구
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
description: 다국적 기업에 대한 Teams 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: f1ba92794b2ba17cc23e1bca55800c9307707636
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786075"
---
# <a name="contoso-case-study-location-based-routing"></a>Contoso 사례 연구: Location-Based 라우팅

Location-Based 라우팅(LBR)은 통화를 받거나 받을 때 정책 및 사용자의 물리적 위치에 따라 수신 우회를 제한하는 기능입니다.  

## <a name="overview"></a>개요

Contoso에는 PSTN(Public Switched Telephone Network) 공급자를 우회하여 장거리 통화 비용을 절감하는 것이 불법인 두 개의 사무실이 있습니다. 주 사무실은 주 사무실과 두 번째 사무실에서 사용하는 인터넷 연결이 있습니다. 각 사무실에는 PSTN 통신 사업자에 연결된 자체 SBC(세션 테두리 컨트롤러)가 있습니다.  
 
이 국가에서 Contoso는 비즈니스용 Skype 배포를 위해 LBR을 구성했습니다. Teams용 LBR을 구성하는 방법을 결정하기 위해 Contoso는 직접 라우팅에 [Location-Based 계획을 읽습니다.](location-based-routing-plan.md) Contoso는 통화를 걸 수 있는 경우, 통화를 수신할 수 있는 경우, PSTN 통화를 Teams 사용자에게 전송할 수 있는 경우 및 다른 Teams 사용자를 PSTN 통화로 전송할 수 있는 경우와 동일한 시나리오를 따르는 것으로 결정했습니다.  

비즈니스용 Skype의 경우 LBR은 PSTN 통신 사업자에 연결하는 SBC(세션 테두리 컨트롤러) SIP 트렁크로 구성됩니다. 이 SBC의 경우 Contoso는 인증된 [SBC](direct-routing-border-controllers.md) 목록을 검토하고 배포된 SBC가 직접 라우팅에 대해 인증되지만 미디어 우회에 대해 인증되지 않은 것으로 결정했습니다. LBR을 지원하려면 SBC 사이트로 직접 라우팅을 구성해야 합니다. 로컬 인터넷 시작이 필요하며 미디어 우회에 대해 SBC를 구성해야 합니다. 이 정보에 따라 Contoso는 다음을 결정합니다.

- 기존 SBC가 미디어 우회에 대해 인증될 때까지 Teams LBR의 사용이 지연됩니다.   

- Contoso는 Office 365에 대한 직접 경로에 기본 사이트 SBC를 사용하기로 결정했습니다.  기본 사이트 SBC는 원격 사이트에 대한 프록시 SBC가 됩니다.  

- Contoso는 인도에 기반한 타사 컨설턴트가 국가에 있는 통신 회사와 LBR 구성의 인증을 지원했습니다.  

- 사무실 외부에서 근무하는 사용자가 PSTN 통화를 걸 수 있도록 회사에서 발급한 휴대폰을 직원에게 제공했습니다. 

다음 다이어그램은 라우팅이 필요한 전화 통신 규정이 있는 국가에 대한 배포 전후의 Location-Based 보여 있습니다.

**원래 배포**

![이전 상태를 보여주는 다이어그램](media/voice-case-study-5.png)

**직접 라우팅을 통해 배포**

![이전 상태를 보여주는 다이어그램](media/voice-case-study-6.png)


## <a name="configuration"></a>구성: 

Contoso는 Teams에서 네트워크 구성 요소를 구성하기 위해 클라우드 음성 기능에 대한 네트워크 토폴로지 관리의 [지침을 따릅니다.](manage-your-network-topology.md) Contoso는 다음 단계를 완료하여 라우팅을 Location-Based 완료했습니다. 

- 네트워크 지역 정의 - 하나의 네트워크 지역이 정의됩니다. 

- 네트워크 사이트 정의 - 두 개의 네트워크 사이트가 정의되었습니다. 지역의 각 사무실 위치에 대한 하나의 사이트입니다.

- 네트워크 서브넷 정의 - 사무실 위치 내의 각 층에는 유선 및 무선 네트워크에 대한 자체 서브넷이 있습니다. 이 구성으로 인해 Contoso에 대한 서브넷이 20개가 됩니다. 

- 신뢰할 수 있는 IP 주소 정의 - SBC의 외부 연결 IP 주소가 신뢰할 수 있는 IP 주소에 추가되었습니다.  

