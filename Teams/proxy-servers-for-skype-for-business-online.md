---
title: Teams 또는 비즈니스용 Skype Online 용 프록시 서버
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: 이 문서에서는 Microsoft Teams 또는 비즈니스용 Skype 프록시 서버를 사용하는 방법에 대한 정보를 제공합니다.
ms.openlocfilehash: cdb4e6ccf05f597c87d066c18b1722eb08f89374
ms.sourcegitcommit: e9718ad7e23317d490b238b3801267cb2e6b26e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2022
ms.locfileid: "69176675"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams 또는 비즈니스용 Skype Online 용 프록시 서버

이 문서에서는 Teams 또는 비즈니스용 Skype 프록시 서버를 사용하는 방법에 대한 지침을 제공합니다.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>프록시 서버를 사용하지 않는 것이 좋습니다.

Teams 또는 프록시를 통해 트래픽을 비즈니스용 Skype 경우 Microsoft 프록시를 우회하는 것이 좋습니다. 프록시는 트래픽이 이미 암호화되어 있기 때문에 Teams 또는 비즈니스용 Skype 더 안전하게 만들지 않습니다.
  
그리고 프록시를 사용하면 문제가 발생할 수 있습니다. 프록시 서버를 통해 Teams 트래픽을 라우팅하려고 시도하여 대기 시간 및 패킷 손실을 통해 성능 관련 문제를 환경에 도입할 수 있습니다. 이와 같은 문제로 인해 실시간 스트림이 필수적인 Teams 또는 오디오 및 비디오와 같은 비즈니스용 Skype 시나리오에서 부정적인 환경이 발생합니다.

Teams 트래픽은 프록시 서버 인프라를 우회하는 것이 좋습니다.

## <a name="teams-phones"></a>Teams 휴대폰

Teams 전화는 프록시 서버를 지원하지 않습니다.

TCP 443(신호) 및 미디어(UDP 3478-3481) 트래픽이 프록시 서버 인프라를 우회하도록 하는 것이 좋습니다.

## <a name="teams-meeting-rooms-and-panels"></a>Teams 회의실 및 패널

Teams 회의실에서 프록시 인프라를 우회하도록 하는 것이 좋습니다.

Windows 기반 Teams 회의실은 프록시 서버를 지원하지만 인증이 필요한 프록시 서버는 지원하지 않습니다. Android 기반 Teams 회의실은 프록시 서버를 지원하지 않습니다.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>프록시 서버를 사용해야 하는 경우

일부 조직에서는 Teams 또는 비즈니스용 Skype 트래픽에 대한 프록시를 우회할 수 있는 옵션이 없습니다. 이 경우 위에서 언급한 문제를 염두에 두어야 합니다.
  
Microsoft 또한 다음을 강력하게 권장합니다.
  
- 로컬 외부 DNS 확인을 사용합니다(일부 클라우드 기반 프록시 솔루션으로 인해 다른 위치에서 DNS 확인이 발생할 수 있습니다).
    
- 미디어에 대한 TCP 기반 라우팅에 의존하지 않고 직접 UDP 기반 라우팅 사용
    
- UDP 트래픽 허용(3478-3481)

- Azure, Office 365, Intune 및 Teams Room Pro(사용되는 경우)를 포함하여 필요한 모든 URL 및 IP 허용
    
- 네트워킹 지침의 다른 권장 사항에 따라 [: Teams를 위한 조직의 네트워크 준비](prepare-network.md)
  
    
이 지침에 따라 잠재적인 문제를 최소화해야 합니다.
  
## <a name="related-topics"></a>관련 주제

[Microsoft 365 및 Office 365 네트워크 연결 원칙](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Teams에 대한 조직의 네트워크 준비](prepare-network.md)
