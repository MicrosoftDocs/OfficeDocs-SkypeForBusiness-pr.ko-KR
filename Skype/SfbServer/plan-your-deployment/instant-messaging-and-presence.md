---
title: 비즈니스용 Skype 서버에서 인스턴트 메시지 및 현재 상태에 대 한 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70d2151e-9382-485d-ab14-758597571a74
description: '요약: 비즈니스용 Skype 서버에서 인스턴트 메시지 및 현재 상태를 계획 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: d62559afe0c7767ee7863f41b41f2d1b64127643
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815906"
---
# <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 인스턴트 메시지 및 현재 상태에 대 한 계획
 
**요약:** 비즈니스용 Skype 서버에서 인스턴트 메시지 및 현재 상태를 계획 하는 방법에 대해 알아봅니다.
  
비즈니스용 Skype 서버에서 인스턴트 메시지 및 현재 상태에 대 한 계획을 수립 합니다. 오프 라인 메신저 대화 (인스턴트 메시징) 설정 또는 해제와 같은 특정 배포 옵션에 대 한 자세한 내용은 [비즈니스용 Skype 서버에서 메신저 대화 및 현재 상태 배포](../deploy/im-and-presence/im-and-presence.md)를 참조 하세요.
  
## <a name="plan-for-instant-messaging-and-presence-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 인스턴트 메시지 및 현재 상태에 대 한 계획

프런트 엔드 서버는 IM (인스턴트 메시징) 및 현재 상태 등의 핵심 비즈니스용 Skype Server 기능을 제공 하며 모든 비즈니스용 Skype 서버 배포에 포함 됩니다. 두 가지 버전의 비즈니스용 Skype Server Enterprise Edition을 사용할 수 있습니다 (대규모 조직을 위해 기본적으로 설계 되었으며,이는 주로 소규모 조직을 위해 디자인 된 비즈니스용 Skype for Business Server Standard Edition)입니다. 하드웨어 투자 및 전체 가용성 옵션이 필요 하지 않습니다. 두 에디션 모두 IM, 현재 상태, 회의, 엔터프라이즈 음성을 비롯 한 모든 비즈니스용 Skype 서버 작업을 지원 합니다.
  
인스턴트 메시지 (IM)를 사용 하면 사용자가 텍스트 기반 메시지를 사용 하 여 컴퓨터에서 실시간으로 서로 통신할 수 있습니다. 2-파티 및 단체 IM 세션이 모두 지원 됩니다. 타사 메신저 대화의 참가자는 언제 든 지 대화에 세 번째 참가자를 추가할 수 있습니다. 이런 경우 대화 창이 회의 기능을 지원 하도록 변경 됩니다.
  
현재 상태는 네트워크에 있는 다른 사용자의 상태에 대 한 정보를 제공 합니다. 사용자의 현재 상태는 다른 사람이 사용자에 게 연락 여부, 인스턴트 메시지, 전화 또는 전자 메일을 사용할지 여부를 결정 하는 데 도움이 되는 정보를 제공 합니다. 현재 상태는 즉각적인 의사 소통을 가능 하 게 하는 반면, 사용자가 인스턴트 통신을 할 수 없음을 나타내는 office 모임 인지 또는 부재 중인지에 대 한 정보를 제공 합니다. 이 현재 상태는 비즈니스용 Skype 및 기타 현재 상태 인식 응용 프로그램 (Microsoft Outlook messaging 및 공동 작업 클라이언트, Microsoft SharePoint 기술, Microsoft Office 포함)에 현재 상태 아이콘으로 표시 됩니다. 현재 상태 아이콘은 사용자의 현재 상태 및 통신 하는 willingness를 나타냅니다. 
  
### <a name="technical-requirements"></a>기술 요구 사항

인스턴트 메시지 (IM) 및 현재 상태는 항상 엔터프라이즈 버전의 프런트 엔드 풀 및 Standard Edition 서버에서 실행 됩니다. 지원 되는 하드웨어, 운영 체제 및 데이터베이스 소프트웨어에 대 한 자세한 내용은 [인증 된 게이트웨이](../../SfbPartnerCertification/certification/infra-gateways.md), 비즈니스용 [skype 2015 환경에 대 한 요구 사항](requirements-for-your-environment/requirements-for-your-environment.md)및 비즈니스용 [skype Server 2019의 인프라 요구 사항을](../../SfBServer2019/plan/system-requirements.md)참조 하세요.
  
### <a name="enabling-communication-with-external-users"></a>외부 사용자와의 통신 설정

사용자가 외부 사용자와 통신할 수 있도록 하 여 비즈니스용 Skype 서버에서 투자의 혜택을 크게 높일 수 있습니다. 외부 사용자는 다음을 포함할 수 있습니다.
  
- 원격 사용자: 사용자가 방화벽 외부에서 작업 중일 때 자신의 랩톱이 나 다른 비즈니스용 Skype 서버 장치를 사용 하는 경우입니다.
    
- 페더레이션 사용자: 비즈니스용 Skype 서버를 사용 하 여 작업 하는 회사 사용자입니다. 사용자가 이러한 사용자에 게 쉽게 연락할 수 있도록 이러한 회사와의 페더레이션 관계를 만듭니다. 
    
- Skype 사용자: Skype for Business 사용자는 메신저, 음성, 영상 등 Skype를 통해 수백만 명의 사용자에 게 연락할 수 있습니다.
    
> [!NOTE]
> AOL, Yahoo 및 Google 대화가 더 이상 지원 되지 않습니다. 
  
> [!NOTE]
> 이러한 시나리오 중 일부 또는 모두를 사용 하도록 설정 하려면 Edge 서버를 배포 하 여 비즈니스용 Skype 서버 배포와 외부 사용자 간의 보안 통신을 사용 하도록 설정 해야 합니다. 조직의 원격 사용자 및 페더레이션된 조직의 사용자는 서로의 현재 상태를 확인 하 고 IM을 사용 하 여 통신할 수 있습니다. 
  
> [!NOTE]
> XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜)는 통합 된 기능 공동 작업 플랫폼 (JITC) 인증 시나리오에만 지원 됩니다. 
  
### <a name="archiving-im-content"></a>IM 콘텐츠 보관

비즈니스용 Skype 서버는 조직이 규정 준수 규정을 따라야 하는 경우 사용할 수 있는 기능을 제공 합니다. 보관을 사용 하 여 조직의 모든 사용자 또는 지정 된 특정 사용자에 대 한 IM 메시지의 콘텐츠를 보관할 수 있습니다. 자세한 내용은 비즈니스용 [Skype 서버에서 보관 계획](archiving/archiving.md)을 참조 하세요. 
  
Microsoft Exchange Server 2013을 배포한 경우 비즈니스용 Skype 서버 데이터 보관을 통해 Exchange 데이터 보관을 통합 하 고 단일 도구를 사용 하 여 보관 된 데이터의 두 가지 유형을 모두 검색할 수 있습니다. 자세한 내용은 [Exchange server 보관을 사용 하려면 비즈니스용 Skype 서버 구성을](../deploy/integrate-with-exchange-server/use-exchange-archiving.md)참조 하세요.
  
### <a name="topologies-and-components"></a>토폴로지 및 구성 요소

인스턴트 메시징 (IM) 및 현재 상태에 필요한 유일한 구성 요소는 다음과 같습니다.
  
- 조직의 프런트 엔드 서버 (풀 이라고 함) 또는 Standard Edition server 이러한 서버에서 IM 및 현재 상태 접근 권한 값을 항상 사용할 수 있습니다. 프런트 엔드 풀 토폴로지와 관리에 대 한 자세한 내용은 [프런트 엔드 풀 고가용성 및 관리](high-availability-and-disaster-recovery/high-availability.md)를 참조 하세요.
    
- 부하 분산 장치 (Enterprise Edition 프런트 엔드 풀을 사용 하는 경우)
    
### <a name="supported-collocation"></a>지원 되는 collocation

Collocation은 여러 역할이 설치 된 단일 서버 또는 서버 그룹이 있는 것으로 정의 됩니다. Collocation에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 토폴로지 기본 사항을](topology-basics/topology-basics.md)참조 하세요. 
  

