---
title: 비즈니스용 Skype 서버에서 엔터프라이즈 음성에 필요한 구성 요소
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: 비즈니스용 Skype 서버의 엔터프라이즈 음성 구성 요소 요약
ms.openlocfilehash: 2c87cc6dceb344e8f39717a62b27e7b50cdff643
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187749"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 엔터프라이즈 음성에 필요한 구성 요소
 
비즈니스용 Skype 서버의 엔터프라이즈 음성 구성 요소 요약
  
엔터프라이즈 음성을 배포 하려면 토폴로지에 다음 구성 요소가 필요 합니다. 
  
- 신호를 변환 하는 하나 이상의 중재 서버, 일부 구성에서 내부 비즈니스용 Skype 서버 간 미디어, 엔터프라이즈 음성 인프라 및 PSTN (공개 교환 전화 네트워크) 게이트웨이 또는 세션 초기화 프로토콜 (SIP) 트렁크. 중재 서버는 엔터프라이즈 음성 배포에서 가장 중요 한 구성 요소입니다. 자세한 내용은 [비즈니스용 Skype 서버에서 중재 서버 구성 요소](mediation-server.md)조정을 참조 하세요.
    
    중재 서버는 프런트 엔드 서버와 collocated 또는 독립 실행형 서버로 설치 될 수 있습니다.
    
- PSTN 연결 구성 요소-SIP trunks 또는 PSTN 게이트웨이를 포함할 수 있습니다. 자세한 내용은 [비즈니스용 Skype 서버의 PSTN 연결 구성 요소](pstn-connectivity.md)를 참조 하세요.
    
- Edge 서버-사용자가 조직의 방화벽 외부에 있을 때 Enterprise Voice 기능을 사용할 수 있도록 합니다. 
    
    액세스에 지 서비스는 조직의 방화벽 외부에 있는 비즈니스용 Skype 사용자의 통화에 대 한 SIP 신호를 제공 합니다. A/V Edge 서비스는 NAT와 방화벽의 미디어 이동을 사용 하도록 설정 합니다. 회사 방화벽 외부에서 통합 커뮤니케이션 (UC) 클라이언트를 사용 하는 발신자는 개인 및 전화 회의 둘 다에 대 한 A/V에 지 서비스에 의존 합니다.
    
    A/V 인증 서비스는 A/v에 대 한 인증 서비스를 제공 하는 collocated와 함께 지원 됩니다. A/V Edge 서비스에 연결 하려고 하는 외부 사용자는 해당 통화를 통과할 수 있도록 A/V 인증 서비스에서 제공 하는 인증 토큰이 필요 합니다.
    
- 또한 일부 엔터프라이즈 음성 구성 요소는 프런트 엔드 서버에서 실행 됩니다. 이러한 구성 요소에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 프런트 엔드 서버 VoIP 구성 요소](front-end-server-voip.md) 를 참조 하세요.
    

