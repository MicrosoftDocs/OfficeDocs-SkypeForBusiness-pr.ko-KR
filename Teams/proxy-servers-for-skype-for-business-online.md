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
ms.openlocfilehash: b2d46cbaa46670daf0235bfd020cae90c5bf624b
ms.sourcegitcommit: 00a526c5b9829302f7c4e0631d0c2dac50b7d004
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2022
ms.locfileid: "69436684"
---
# <a name="proxy-servers-for-teams-and-skype-for-business-online"></a>Teams 및 비즈니스용 Skype Online용 프록시 서버

이 문서에서는 Teams 또는 비즈니스용 Skype 프록시 서버를 사용하는 방법에 대한 지침을 제공합니다.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>프록시 서버를 사용하지 않는 것이 좋습니다.

Teams 또는 프록시를 통해 트래픽을 비즈니스용 Skype 경우 Microsoft 프록시를 우회하는 것이 좋습니다. 프록시는 트래픽이 이미 암호화되어 있기 때문에 Teams 또는 비즈니스용 Skype 더 안전하게 만들지 않습니다.
  
그리고 프록시를 사용하면 문제가 발생할 수 있습니다. 프록시 서버를 통해 Teams 트래픽을 라우팅하려고 시도하여 대기 시간 및 패킷 손실을 통해 성능 관련 문제를 환경에 도입할 수 있습니다. 이와 같은 문제로 인해 실시간 스트림이 필수적인 Teams 또는 오디오 및 비디오와 같은 비즈니스용 Skype 시나리오에서 부정적인 환경이 발생합니다.

Teams 트래픽은 프록시 서버 인프라를 우회하는 것이 좋습니다. Teams 휴대폰 및 회의실 디바이스를 자체 VLAN에 배치하고 인터넷 액세스를 제공하여 이 작업을 수행할 수 있습니다.

## <a name="windows-based-teams-devices"></a>Teams 디바이스 Windows-Based

Windows 기반 Teams 회의실 및 Surface Hubs는 일부 프록시 서버를 지원하지만 인증이 필요한 프록시 서버는 지원하지 않습니다.

이러한 디바이스는 프록시 인프라를 우회하고 방화벽을 통해 Microsoft 365 서비스에 액세스하는 것이 좋습니다.

## <a name="android-based-teams-devices"></a>Teams 디바이스 Android-Based

Teams 휴대폰, 패널, 디스플레이 및 보드를 포함한 Android 기반 Teams 디바이스는 프록시 서버를 지원하지 않습니다.

이러한 디바이스에서 실행되는 특정 구성 요소가 인터넷에 액세스하는 방식으로 인해 프록시를 통해 모든 트래픽을 라우팅할 수 없습니다. 이러한 디바이스와 Microsoft 365 서비스 간의 트래픽이 방화벽을 통해 허용되는지 확인해야 합니다.

## <a name="if-you-need-to-use-a-proxy-server"></a>프록시 서버를 사용해야 하는 경우

일부 조직에서는 Teams 또는 비즈니스용 Skype 트래픽에 대한 프록시를 우회할 수 있는 옵션이 없습니다. 이 경우 위에서 언급한 문제를 염두에 두어야 합니다.

> [!Note]
> 프록시 인프라에서 비공개로 서명된 인증서를 사용하는 경우 디바이스가 인증서를 신뢰할 수 있도록 Teams 회의실 디바이스에 비공개 서명된 인증서 및 인증서 체인을 설치해야 합니다. Teams 휴대폰 및 기타 Android 기반 Teams 디바이스에 비공개로 서명된 인증서 설치는 지원되지 않습니다.
  
Microsoft 또한 다음을 강력하게 권장합니다.
  
- 로컬 외부 DNS 확인을 사용합니다(일부 클라우드 기반 프록시 솔루션으로 인해 다른 위치에서 DNS 확인이 발생할 수 있습니다).

- Teams 디바이스와 서비스 간의 경로가 최대한 짧고 직접적인지 확인
    
- 미디어에 대한 TCP 기반 라우팅에 의존하지 않고 직접 UDP 기반 라우팅 사용
    
- 방화벽을 통해 Teams Media에 대한 UDP 트래픽 허용(3478-3481)

- 방화벽을 통해 Azure, Office 365, Intune 및 Teams Room Pro(사용되는 경우)에 대한 URL 및 IP를 포함하여 필요한 모든 URL 및 IP 허용
    
- 네트워킹 지침의 다른 권장 사항에 따라 [: Teams를 위한 조직의 네트워크 준비](prepare-network.md)
  
    
이 지침에 따라 잠재적인 문제를 최소화해야 합니다.
  
## <a name="related-topics"></a>관련 주제

[Microsoft 365 및 Office 365 네트워크 연결 원칙](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Teams에 대한 조직의 네트워크 준비](prepare-network.md)
