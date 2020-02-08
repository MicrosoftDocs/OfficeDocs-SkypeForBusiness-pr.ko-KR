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
description: 이 문서에서는 팀 또는 비즈니스용 Skype에 프록시 서버를 사용 하는 방법에 대 한 정보를 제공 합니다.
ms.openlocfilehash: ca81c32064406af0e5bc3d614566a96ec5646a91
ms.sourcegitcommit: 2511cd95a186d95f4571afa4212f8e0fc207817d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2020
ms.locfileid: "41863189"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a>Teams 또는 비즈니스용 Skype Online 용 프록시 서버

이 문서에서는 팀 또는 비즈니스용 Skype에서 프록시 서버를 사용 하는 방법에 대 한 지침을 제공 합니다.
  
## <a name="not-using-a-proxy-server-is-recommended"></a>프록시 서버를 사용 하지 않는 것이 좋습니다.

프록시를 통해 팀 또는 비즈니스용 Skype 트래픽을 제공 하는 경우, Microsoft에서 프록시를 우회 하는 것이 좋습니다. 프록시는 트래픽이 이미 암호화 되어 있기 때문에 비즈니스용 Skype를 더 안전 하 게 보호할 수 없습니다.
  
프록시로 인해 문제가 발생할 수 있습니다. 성능 관련 문제는 대기 시간 및 패킷 손실을 통해 환경에 도입 될 수 있습니다. 이러한 문제가 발생 하면 이러한 팀 또는 비즈니스용 Skype 시나리오에서 실시간 스트림이 필수적인 오디오 및 비디오로 인 한 환경이 저하 됩니다.
  
## <a name="if-you-need-to-use-a-proxy-server"></a>프록시 서버를 사용 해야 하는 경우

일부 조직에서는 팀 또는 비즈니스용 Skype 트래픽에 대 한 프록시를 우회 하는 옵션을 사용할 수 없습니다. 이러한 경우에는 위에서 설명한 문제를 염두에 두어야 합니다.
  
Microsoft는 또한 다음을 적극 권장 합니다.
  
- 외부 DNS 확인 사용
    
- 직접 UDP 기반 라우팅 사용
    
- UDP 트래픽 허용
    
- 네트워킹 지침의 다른 권장 사항에 따라 [팀에 맞게 조직의 네트워크를 준비](prepare-network.md) 합니다.
  
    
이 지침을 팔 로우 하면 잠재적인 문제를 최소화할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[Office 365 네트워크 연결 원칙](https://aka.ms/pnc)

[Teams에 대한 조직의 네트워크 준비](prepare-network.md)
