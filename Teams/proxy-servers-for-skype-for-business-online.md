---
title: Teams 또는 비즈니스용 Skype Online 용 프록시 서버
ms.author: tonysmit
author: tonysmit
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: 이 문서에서는 프록시 서버와 함께 프록시 서버를 사용하는 Microsoft Teams 비즈니스용 Skype.
ms.openlocfilehash: b4724ad213d4d76c93484fb2ef33c50f4f6904b814ebd959a52adb95f1ee219b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341244"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams 또는 비즈니스용 Skype Online 용 프록시 서버

이 문서에서는 프록시 서버와 함께 프록시 서버를 사용하는 방법에 Teams 비즈니스용 Skype.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>프록시 서버를 사용하지 않는 것이 좋습니다.

프로시를 통해 트래픽을 Teams 비즈니스용 Skype 경우 Microsoft는 프로시전을 무시하는 것이 좋습니다. Proxies는 트래픽이 이미 암호화되어 Teams 비즈니스용 Skype 보안이 유지되지 않습니다.
  
프록시가 있는 경우 문제가 발생할 수 있습니다. 성능 관련 문제는 대기 시간 및 패킷 손실을 통해 환경에 도입될 수 있습니다. 이러한 문제로 인해 실시간 스트림이 필수인 오디오 Teams 비즈니스용 Skype 시나리오에서 부정적인 환경을 경험할 수 있습니다.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>프록시 서버를 사용해야 하는 경우

일부 조직에서는 트래픽 또는 트래픽에 대한 프록시를 Teams 비즈니스용 Skype 없습니다. 이 경우 위에서 언급한 문제를 염두에 두어야 합니다.
  
Microsoft는 또한 강력하게 권장합니다.
  
- 외부 DNS 확인 사용
    
- 직접 UDP 기반 라우팅 사용
    
- UDP 트래픽 허용
    
- 네트워킹 지침의 다른 권장 사항: [](prepare-network.md) 조직의 네트워크 준비를 Teams
  
    
이 지침을 따라 잠재적인 문제를 최소화해야 합니다.
  
## <a name="related-topics"></a>관련 항목

[Microsoft 365 및 Office 365 네트워크 연결 원칙](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[Teams에 대한 조직의 네트워크 준비](prepare-network.md)