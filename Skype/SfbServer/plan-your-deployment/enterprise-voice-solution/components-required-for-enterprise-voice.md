---
title: Enterprise Voice 구성 요소에 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: 이 문서의 Enterprise Voice 구성 요소에 대한 비즈니스용 Skype 서버.
ms.openlocfilehash: 2fbc5aa6a7ece34db0d0ae9360d4be7c8b6f2a8d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390050"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>Enterprise Voice 구성 요소에 비즈니스용 Skype 서버
 
이 문서의 Enterprise Voice 구성 요소에 대한 비즈니스용 Skype 서버.
  
토폴로지에서 Enterprise Voice 구성 요소를 배포하려면 다음 구성 요소가 필요합니다. 
  
- 신호 및 일부 구성에서 내부 비즈니스용 Skype 서버, Enterprise Voice 인프라와 PSTN(Public Switched Telephone Network) 게이트웨이 또는 SIP(Session Initiation Protocol) 트렁크 간의 미디어를 변환하는 하나 이상의 중재 서버. 중재 서버는 배포에서 가장 중요한 Enterprise Voice 구성 요소입니다. 자세한 내용은 중재 서버 구성 요소를 [비즈니스용 Skype 서버](mediation-server.md).
    
    중재 서버는 프런트 엔드 서버와 함께 함께 설치하거나 독립 실행형 서버로 설치할 수 있습니다.
    
- SIP 트렁크 또는 PSTN 게이트웨이를 포함할 수 있는 PSTN 연결 구성 요소 자세한 내용은 [2016년 8월의 PSTN 연결](pstn-connectivity.md) 구성 요소를 비즈니스용 Skype 서버.
    
- 에지 서버 - 사용자가 조직의 방화벽 외부에 있는 Enterprise Voice 기능을 사용할 수 있도록 합니다. 
    
    액세스 에지 서비스는 조직의 방화벽 외부에 비즈니스용 Skype 사용자의 통화에 대한 SIP 신호를 제공합니다. A/V 에지 서비스를 사용하면 미디어가 NAT 및 방화벽을 트래버스할 수 있습니다. 회사 방화벽 외부에서 UC(통합 통신) 클라이언트를 사용하는 발신자는 개인적인 통화와 전화 회의 모두에 A/V 에지 서비스를 사용합니다.
    
    A/V 에지 서비스와 함께 A/V 인증 서비스가 배치되어 인증 서비스를 제공합니다. A/V 에지 서비스에 연결하려는 외부 사용자는 A/V 인증 서비스에서 제공한 인증 토큰이 있어야 통화할 수 있습니다.
    
- 또한 일부 Enterprise Voice 구성 요소는 프런트 엔드 서버에서 실행됩니다. 이러한 구성 요소에 대한 자세한 내용은 프런트 엔드 [서버 VoIP 구성 요소에서](front-end-server-voip.md) 비즈니스용 Skype 서버
    

