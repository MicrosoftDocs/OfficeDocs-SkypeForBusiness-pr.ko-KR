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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Optimization
description: 이 문서에서는 프록시 서버와 함께 프록시 서버를 사용하는 비즈니스용 Skype.
ms.openlocfilehash: b0f8e9898e2c898387e7f726b470013dcf62caae
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585992"
---
# <a name="proxy-servers-for-skype-for-business-online"></a>온라인용 프록시 비즈니스용 Skype 서버

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

이 문서에서는 프록시 서버와 함께 프록시 서버를 사용하는 방법에 대한 비즈니스용 Skype.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>프록시 서버를 사용하지 않는 것이 좋습니다.

xies를 통해 트래픽을 비즈니스용 Skype 경우 Microsoft는 프로시전을 무시하는 것이 좋습니다. Proxies는 트래픽이 이미 암호화되어 비즈니스용 Skype 보안이 유지되지 않습니다.
  
프록시가 있는 경우 문제가 발생할 수 있습니다. 성능 관련 문제는 대기 시간 및 패킷 손실을 통해 환경에 도입될 수 있습니다. 이러한 문제로 인해 실시간 스트림이 필수인 오디오 Teams 비즈니스용 Skype 시나리오에서 부정적인 환경을 경험할 수 있습니다.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>프록시 서버를 사용해야 하는 경우

일부 조직에서는 트래픽에 대한 프록시를 비즈니스용 Skype 없습니다. 이 경우 위에서 언급한 문제를 염두에 두어야 합니다.
  
Microsoft는 또한 강력하게 권장합니다.
  
- 외부 DNS 확인 사용
    
- 직접 UDP 기반 라우팅 사용
    
- UDP 트래픽 허용
    
- 네트워킹 지침의 다른 권장 사항을 따릅니다.
    
  - [온라인에서 미디어 품질 및 비즈니스용 Skype 성능](media-quality-and-network-connectivity-performance.md)
    
  - [온라인용 네트워크 비즈니스용 Skype 최적화](optimizing-your-network.md)
    
이 지침을 따라 잠재적인 문제를 최소화해야 합니다.
  
## <a name="related-topics"></a>관련 주제

[온라인용 네트워크 비즈니스용 Skype 최적화](optimizing-your-network.md)
 
