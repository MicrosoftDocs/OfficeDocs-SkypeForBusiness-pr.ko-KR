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
ms.openlocfilehash: 61a1878b3c7057de7dddbcd63c480f80c2f16e0f
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045437"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams 또는 비즈니스용 Skype Online 용 프록시 서버

이 문서에서는 Teams 또는 비즈니스용 Skype 프록시 서버를 사용하는 방법에 대한 지침을 제공합니다.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>프록시 서버를 사용하지 않는 것이 좋습니다.

프록시를 통해 트래픽을 Teams 또는 비즈니스용 Skype 경우 프록시를 우회하는 것이 좋습니다. 프록시는 트래픽이 이미 암호화되어 있으므로 Teams 또는 비즈니스용 Skype 더 안전하게 만들지 않습니다.
  
프록시를 사용하면 문제가 발생할 수 있습니다. 대기 시간 및 패킷 손실을 통해 성능 관련 문제를 환경에 도입할 수 있습니다. 이와 같은 문제로 인해 실시간 스트림이 필수적인 오디오 및 비디오와 같은 Teams 또는 비즈니스용 Skype 시나리오에서 부정적인 환경이 발생합니다.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>프록시 서버를 사용해야 하는 경우

일부 조직에서는 Teams 또는 비즈니스용 Skype 트래픽에 대한 프록시를 바이패스할 수 있는 옵션이 없습니다. 이 경우 위에서 언급한 문제를 염두에 두어야 합니다.
  
Microsoft는 다음을 강력하게 권장합니다.
  
- 외부 DNS 확인 사용
    
- 직접 UDP 기반 라우팅 사용
    
- UDP 트래픽 허용
    
- 네트워킹 지침의 다른 권장 사항에 따라: [조직의 네트워크를 Teams 준비](prepare-network.md)
  
    
이 지침에 따라 잠재적인 문제를 최소화해야 합니다.
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 및 Office 365 네트워크 연결 원칙](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Teams에 대한 조직의 네트워크 준비](prepare-network.md)