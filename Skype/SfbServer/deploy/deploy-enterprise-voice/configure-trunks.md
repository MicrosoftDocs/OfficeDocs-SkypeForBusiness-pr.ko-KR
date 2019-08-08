---
title: 비즈니스용 Skype 서버에서 trunks 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: '요약: 비즈니스용 Skype 서버에서 중재 서버와 Enterprise Voice 용 피어 간 트렁크를 구성 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 714c712816709e8f2211e752f87d20c8d2067c7b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233853"
---
# <a name="configure-trunks-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 trunks 구성
 
**요약:** 비즈니스용 Skype 서버에서 중재 서버와 Enterprise Voice 용 피어 간의 트렁크를 구성 하는 방법을 알아봅니다.
  
엔터프라이즈 음성 배포의 일부로, 중재 서버와 다음 피어 중 하나 이상을 구성할 수 있으므로 조직의 엔터프라이즈 음성 클라이언트 및 장치에 대 한 PSTN (공개 통신 네트워크) 연결을 제공 합니다.
  
- 인터넷 전화 통신 서비스 공급자 (ITSP)에 대 한 SIP 트렁크 연결
    
- PSTN 게이트웨이
    
- PBX (사설 분기 교환)
    
자세한 내용은 비즈니스용 [Skype 서버의 PSTN 연결 계획](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)을 참조 하세요.
  
비즈니스용 Skype 서버 기능은 게이트웨이와 중재 서버 간의 복수 연결을 지원 합니다. 이러한 연결은 중재 서버 풀과 PSTN (공개 교환 통신 네트워크) 게이트웨이, SBC (세션 경계 컨트롤러) 또는 IP-PBX 간의 논리적 연결 인 트렁크를 정의 하 여 이루어집니다. 토폴로지 작성기를 사용 하 여 게이트웨이를 중재 서버와 연결 합니다 (즉, trunks).
  
- 비즈니스용 Skype 서버에서 트렁크를 할당 또는 제거 하려면 먼저 토폴로지 작성기에서 트렁크를 정의 해야 합니다. 트렁크는 다음 연결로 구성 됩니다. 중재 서버 FQDN (정규화 된 도메인 이름), 중재 서버 수신 포트, 게이트웨이 FQDN 및 게이트웨이 수신 대기 포트.
    
- 여러 trunks를 구성 하려면 동일한 게이트웨이와 중재 서버 간에 여러 연결을 만들 수 있습니다. 이렇게 하면 PBX (개인 브랜치 교환) interoperational 시나리오에서 특히 유용한 엔터프라이즈 음성 인프라에 대 한 추가 탄력성을 제공 합니다. 
    
트렁크가 정의 되 면 경로에 연결 되어 있어야 합니다. 트렁크를 경로에 연결 하려면 토폴로지 작성기에서 트렁크에 대 한 간단한 이름을 정의 합니다. 이 간단한 이름은 비즈니스용 Skype Server 제어판에서 트렁크 이름으로 사용 되며, trunks 연결 될 수 있습니다. 간단한 트렁크 이름을 비즈니스용 Skype 서버 관리 셸에서의 게이트웨이 이름으로 사용 합니다. 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

관리자는 중재 서버와 연결 된 기본 트렁크를 선택 해야 합니다. 토폴로지 작성기에서 연결 된 중재 서버를 마우스 오른쪽 단추로 클릭 한 다음 **속성**을 클릭 합니다. 중재 서버의 기본 게이트웨이를 지정 합니다. 
  

