---
title: 비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '요약: 비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획을 세우는 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: a29d68cc66e0ac4a70fc759283646fc3ce49cdf5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816278"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획
 
**요약:** 비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획을 세우는 방법을 배워야 합니다.
  
비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획 IM(오프라인 인스턴트 메시징) 사용 또는 사용 안 하도록 설정과 같은 특정 배포 옵션에 대한 자세한 내용은 비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 [배포를 참조하세요.](../deploy/im-and-presence/im-and-presence.md)
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 인스턴트 메시징 및 현재 상태 계획

프런트 엔드 서버는 IM(인스턴트 메시징) 및 현재 상태와 같은 핵심 비즈니스용 Skype 서버 기능을 제공하고 모든 비즈니스용 Skype 서버 배포에 포함됩니다. 사용할 수 있는 두 가지 버전은 주로 대규모 조직을 위해 설계된 비즈니스용 Skype 서버 Enterprise Edition과 전체 고가용성 옵션이 필요하지 않은 소규모 하드웨어 투자를 원하는 소규모 조직을 위해 설계된 비즈니스용 Skype 서버 Standard Edition입니다. 두 버전 모두 IM, 현재 상태, 회의 및 회의를 비롯한 모든 비즈니스용 Skype 서버 작업을 Enterprise Voice.
  
IM(인스턴트 메시징)은 사용자가 텍스트 기반 메시지를 사용하여 컴퓨터에서 실시간으로 다른 사용자와 통신할 수 있도록 합니다. 양방향 및 단체 IM 세션이 모두 지원됩니다. 양방향 IM 대화의 참가자는 언제든지 대화에 세 번째 참가자를 추가할 수 있습니다. 이 경우 대화 창이 회의 기능을 지원하도록 변경됩니다.
  
현재 상태는 네트워크의 다른 사용자 상태에 대한 정보를 사용자에게 제공합니다. 사용자의 현재 상태는 다른 사용자가 사용자에게 연락할지 여부와 메신저, 전화 또는 전자 메일을 사용할지 여부를 결정하는 데 도움이 되는 정보를 제공합니다. 현재 상태는 가능한 경우 인스턴트 통신을 촉진하는 동시에, 사용자가 회의 중인지 또는 부재 중인지에 대한 정보를 제공하여 인스턴트 통신을 사용할 수 없다는 것도 표시합니다. 이 현재 상태는 비즈니스용 Skype 및 Microsoft Outlook 메시징 및 공동 작업 클라이언트, Microsoft SharePoint 기술 및 기타 현재 상태 인식 응용 프로그램에서 현재 상태 아이콘으로 Microsoft Office. 현재 상태 아이콘은 사용자의 현재 가용성 및 통신 의사를 나타내는 아이콘입니다. 
  
### <a name="technical-requirements"></a>기술 요구 사항

IM(인스턴트 메시징) 및 현재 상태는 항상 Enterprise Edition 프런트 엔드 풀 및 Standard Edition 서버에서 실행됩니다. 지원되는 하드웨어, 운영 체제 및 데이터베이스 소프트웨어에 대한 자세한 내용은 인증  [게이트웨이,](../../SfbPartnerCertification/certification/infra-gateways.md)비즈니스용  [Skype 2015](requirements-for-your-environment/requirements-for-your-environment.md)환경에 대한 요구 사항 및 비즈니스용 [Skype 서버 2019의](../../SfBServer2019/plan/system-requirements.md)인프라 요구 사항을 참조하세요.
  
### <a name="enabling-communication-with-external-users"></a>외부 사용자와의 통신 사용

사용자가 외부 사용자와 통신할 수 있도록 하여 비즈니스용 Skype 서버에 대한 투자 이익을 크게 증가할 수 있습니다. 외부 사용자에는 다음이 포함될 수 있습니다.
  
- 원격 사용자: 방화벽 외부에서 랩톱 또는 기타 비즈니스용 Skype 서버 장치를 사용하는 조직의 사용자
    
- 페더타 사용자: 비즈니스용 Skype 서버를 실행하기도 하는 회사에서 작업하는 사용자입니다. 조직의 사용자가 이러한 사용자에게 쉽게 연결할 수 있도록 하려면 이러한 회사와 페더레이션 관계를 만들면 됩니다. 
    
- Skype 사용자: 비즈니스용 Skype 사용자는 IM, 음성 및 비디오를 사용하여 Skype에서 수억 명의 사용자에게 도달할 수 있습니다.
    
> [!NOTE]
> AOL, Yahoo 및 Google Talk는 더 이상 지원되지 않습니다. 
  
> [!NOTE]
> 이러한 시나리오 중 일부 또는 전체를 사용하도록 설정하려면 에지 서버를 배포하여 비즈니스용 Skype 서버 배포와 외부 사용자 간의 보안 통신을 사용하도록 설정해야 합니다. 조직의 원격 사용자와 페더타 조직의 사용자는 서로의 현재 상태와 IM을 사용하여 통신할 수 있습니다. 
  
> [!NOTE]
> XMPP(Extensible Messaging and Presence Protocol)는 UCCP(Unified Capabilities Collaboration Platform) JITC(Joint Interoperability Test Command) 인증 시나리오에서만 지원됩니다. 
  
### <a name="archiving-im-content"></a>IM 콘텐츠 보관

비즈니스용 Skype 서버는 조직이 규정 준수 규정을 따라야 하는 경우 사용할 수 있는 기능을 제공합니다. 보관을 사용하여 조직의 모든 사용자 또는 지정한 특정 사용자에 대한 IM 메시지 콘텐츠를 보관할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버의 보관 [계획을 참조하세요.](archiving/archiving.md) 
  
또한 Microsoft Exchange Server 2013을 배포한 경우 Exchange 데이터의 보관을 비즈니스용 Skype 서버 데이터의 보관과 통합하고 단일 도구를 사용하여 두 유형의 보관된 데이터를 모두 검색할 수 있습니다. 자세한 내용은 보관을 사용하도록 비즈니스용 Skype 서버 [Exchange Server 참조하세요.](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)
  
### <a name="topologies-and-components"></a>토폴로지 및 구성 요소

IM(인스턴트 메시징) 및 현재 상태의 구성 요소는 다음뿐입니다.
  
- 조직의 프런트 엔드 서버(풀) 또는 Standard Edition 서버 IM 및 현재 상태 기능은 이러한 서버에서 항상 사용하도록 설정됩니다. 프런트 엔드 풀 토폴로지 및 관리에 대한 자세한 내용은 프런트 엔드 풀 고가용성 [및 관리를 참조하십시오.](high-availability-and-disaster-recovery/high-availability.md)
    
- Enterprise Edition 프런트 엔드 풀이 있는 경우 부하가 있는 경우
    
### <a name="supported-collocation"></a>지원되는Ococation

여러 역할이 설치된 단일 서버 또는 서버 그룹이 함께 있는 것으로 정의됩니다. 설명에 대한 자세한 내용은 비즈니스용 [Skype 서버의 토폴로지 기본 사항을 참조하세요.](topology-basics/topology-basics.md) 
  

