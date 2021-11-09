---
title: 인스턴트 메시징 및 현재 상태 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '요약: 인스턴트 메시징 및 현재 상태의 계획을 세우는 방법을 비즈니스용 Skype 서버.'
ms.openlocfilehash: b81da143bf7b8d917d88939d8b28261910bb8f5a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835086"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>인스턴트 메시징 및 현재 상태 비즈니스용 Skype 서버
 
**요약:** 인스턴트 메시징 및 현재 상태 계획을 세우는 방법을 비즈니스용 Skype 서버.
  
인스턴트 메시징 및 현재 상태 계획 비즈니스용 Skype 서버. IM(오프라인 인스턴트 메시징)을 사용하도록 설정하거나 사용 안 하도록 설정하는 등의 특정 배포 옵션에 대한 자세한 내용은 [Deploy instant messaging and presence in 비즈니스용 Skype 서버.](../deploy/im-and-presence/im-and-presence.md)
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>인스턴트 메시징 및 현재 상태 비즈니스용 Skype 서버

프런트 엔드 서버는 IM(비즈니스용 Skype 서버 메시징) 및 현재 상태와 같은 핵심 비즈니스용 Skype 서버 배포에 포함되어 있습니다. 사용할 수 있는 두 가지 버전은 비즈니스용 Skype 서버 Enterprise Edition, 주로 대규모 조직용으로 디자인된 비즈니스용 Skype 서버 Standard Edition 중소기업을 위해 설계되어 있으며 전체 하드웨어 투자가 필요하지 않은 소규모 조직을 위해 고안된 버전입니다. 고가용성 옵션. 두 버전 모두 IM비즈니스용 Skype 서버 현재 상태, 회의 및 회의를 비롯한 모든 Enterprise Voice.
  
IM(인스턴트 메시징)은 사용자가 텍스트 기반 메시지를 사용하여 컴퓨터에서 실시간으로 다른 사용자와 통신할 수 있도록 합니다. 양방향 및 단체 IM 세션이 모두 지원됩니다. 양방향 IM 대화의 참가자는 언제든지 대화에 세 번째 참가자를 추가할 수 있습니다. 이 경우 대화 창이 회의 기능을 지원하도록 변경됩니다.
  
현재 상태는 네트워크에 있는 다른 사용자의 상태에 대한 정보를 사용자에게 제공합니다. 사용자의 현재 상태는 다른 사용자가 사용자에게 연락해야 하는지 여부와 인스턴트 메시징, 전화 또는 전자 메일을 사용할지 여부를 결정하는 데 도움이 되는 정보를 제공합니다. 현재 상태는 가능한 경우 인스턴트 통신을 촉진하는 동시에, 사용자가 회의 중인지 또는 부재 중인지에 대한 정보를 제공하여 인스턴트 통신을 사용할 수 없다는 것도 표시합니다. 이 현재 상태는 Microsoft Outlook 메시징 및 공동 작업 클라이언트비즈니스용 Skype Microsoft SharePoint 기술 및 기타 현재 상태 인식 응용 프로그램에서 현재 상태 아이콘으로 Microsoft Office. 현재 상태 아이콘은 사용자의 현재 가용성과 통신 의사를 나타내는 아이콘입니다. 
  
### <a name="technical-requirements"></a>기술 요구 사항

IM(인스턴트 메시징) 및 현재 상태는 항상 Enterprise Edition 프런트 엔드 풀 및 Standard Edition 실행됩니다. 지원되는 하드웨어, 운영 체제 및 데이터베이스 소프트웨어에 대한 자세한 내용은 [Certified Gateways,](../../SfbPartnerCertification/certification/infra-gateways.md) [Requirements for your 비즈니스용 Skype 2015 environment](requirements-for-your-environment/requirements-for-your-environment.md)및 Infrastructure requirements for 비즈니스용 Skype 서버 [2019을 참조하십시오.](../../SfBServer2019/plan/system-requirements.md)
  
### <a name="enabling-communication-with-external-users"></a>외부 사용자와의 통신 사용

사용자가 외부 사용자와 통신할 수 있도록 비즈니스용 Skype 서버 투자 이익을 크게 증가할 수 있습니다. 외부 사용자에는 다음이 포함될 수 있습니다.
  
- 원격 사용자: 조직의 사용자가 방화벽 외부에서 랩톱 또는 기타 비즈니스용 Skype 서버.
    
- 페더러드 사용자: 사용자도 함께 작업하는 회사에서 사용자로 비즈니스용 Skype 서버. 조직의 사용자가 이러한 사용자에게 쉽게 연결할 수 있도록 하려면 이러한 회사와 페더레이션 관계를 만들면 됩니다. 
    
- Skype 사용자: 비즈니스용 Skype IM, 음성 및 비디오로 Skype 수억 명의 사용자에게 도달할 수 있습니다.
    
> [!NOTE]
> AOL, Yahoo 및 Google Talk는 더 이상 지원되지 않습니다. 
  
> [!NOTE]
> 이러한 시나리오 중 일부 또는 전체를 사용하도록 설정하려면 에지 서버를 배포하여 비즈니스용 Skype 서버 사용자 간의 보안 통신을 설정해야 합니다. 조직의 원격 사용자와 페더러드 조직의 사용자는 서로의 현재 상태와 IM을 사용하여 통신할 수 있습니다. 
  
> [!NOTE]
> XMPP(Extensible Messaging and Presence Protocol)는 JITC(Unified Capabilities Collaboration Platform) JITC(Joint Interoperability Test Command) 인증 시나리오에서만 지원됩니다. 
  
### <a name="archiving-im-content"></a>IM 콘텐츠 보관

비즈니스용 Skype 서버 준수 규정을 따라야 하는 경우 사용할 수 있는 기능을 제공합니다. 보관을 사용하여 조직의 모든 사용자 또는 지정한 특정 사용자에 대한 IM 메시지 콘텐츠를 보관할 수 있습니다. 자세한 내용은 [Plan for archiving in 비즈니스용 Skype 서버.](archiving/archiving.md) 
  
또한 Microsoft Exchange Server 2013을 배포한 경우 Exchange 데이터의 보관과 비즈니스용 Skype 서버 데이터를 통합하고 단일 도구를 사용하여 두 유형의 보관된 데이터를 모두 검색할 수 있습니다. 자세한 내용은 [Configure 비즈니스용 Skype 서버 to use Exchange Server 참조하십시오.](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)
  
### <a name="topologies-and-components"></a>토폴로지 및 구성 요소

IM(인스턴트 메시징) 및 현재 상태의 구성 요소는 다음 구성 요소뿐입니다.
  
- 조직의 프런트 엔드 서버(풀) 또는 Standard Edition 서버입니다. IM 및 현재 상태 기능은 이러한 서버에서 항상 사용하도록 설정됩니다. 프런트 엔드 풀 토폴로지 및 관리에 대한 자세한 내용은 프런트 엔드 풀 고가용성 [및 관리를 참조하세요.](high-availability-and-disaster-recovery/high-availability.md)
    
- 프런트 엔드 풀이 있는 경우 부하 Enterprise Edition 수 있습니다.
    
### <a name="supported-collocation"></a>지원되는 함께 사용

여러 역할이 설치된 단일 서버 또는 서버 그룹이 있는 것으로 정의됩니다. 병치에 대한 자세한 내용은 [Topology Basics for 비즈니스용 Skype 서버.](topology-basics/topology-basics.md) 
  

