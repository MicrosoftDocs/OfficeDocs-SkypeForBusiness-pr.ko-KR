---
title: 토폴로지 기본 비즈니스용 Skype 서버
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
ms.assetid: 113e8c3f-71de-435c-bc4a-918ac7b50008
description: '요약: 토폴로지에서 토폴로지 비즈니스용 Skype 서버. 서버의 서버 비즈니스용 Skype 서버.'
ms.openlocfilehash: 579c14471daab8c96eb6b55bdc2f21fc0b3b7eb4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394900"
---
# <a name="topology-basics-for-skype-for-business-server"></a>토폴로지 기본 비즈니스용 Skype 서버

**요약:** 토폴로지에서 토폴로지 비즈니스용 Skype 서버. 서버의 서버 비즈니스용 Skype 서버.

다른 모든 것을 준비하기 전에 배포에 적합한 토폴로지 계획을 세우고 비즈니스용 Skype 서버. 가장 먼저 결정해야 할 것은 비즈니스용 Skype 서버 배포를 배포할지 아니면 하이브리드 배포에서 비즈니스용 Skype 서버 Online 배포와 결합할지 여부를 결정하는 것입니다. 어느 쪽이든, 여기에서는 사내 토폴로지가 자세히 설명되어 있지만 하이브리드 세부 정보는 자체 섹션에 설명되어 있습니다.

참조 토폴로지에서 몇 가지 예제 토폴로지[도 볼 수 비즈니스용 Skype 서버](reference-topologies.md).

## <a name="sites"></a>사이트

이 비즈니스용 Skype 서버 구성 요소가 포함된 네트워크의 비즈니스용 Skype 서버 정의합니다. 사이트는 단일 LAN(Local Area Network)이나 고속 광섬유 네트워크로 연결된 두 개의 네트워크와 같이 고속, 짧은 대기 시간 네트워크로 견고하게 연결된 컴퓨터 집합입니다. 비즈니스용 Skype 서버 사이트는 Active Directory 도메인 서비스 사이트 및 사이트와는 별도의 Microsoft Exchange Server 있습니다. 사용자 비즈니스용 Skype 서버 Active Directory 사이트에 해당할 필요가 없습니다.

비즈니스용 Skype 서버 및 위치 요구 사항에 따라 확장할 수 있는 하나 이상의 사이트에 대한 사내 배포를 지원할 수 있습니다.

배포에는 하나 이상의 중앙 사이트(데이터 센터라고도 합니다. 이 사이트는 데이터 센터라고도 합니다.) 배포의 각 중앙 사이트에는 하나의 Standard Edition 서버 또는 하나 이상의 Enterprise Edition 프런트 엔드 풀이 있습니다. 아래 각 옵션의 차이점을 볼 수 있습니다.

- Standard Edition 서버에는 함께 SQL Server Express 데이터베이스가 포함되어 있습니다.

- Enterprise Edition 프런트 엔드 풀에는 다음이 포함됩니다.

  - 하나 이상의 프런트 엔드 서버(이상적으로는 확장성을 위해 3개 이상) 최대 12대의 프런트 엔드 서버. 부하 분산은 두 개 이상의 서버에 필요합니다.

  - 별도의 백 엔드 서버.

이 섹션의  나중에 다양한 서버 역할에 대해 자세히 알아보십시오.

중앙 사이트 외에도 중앙 사이트와 연결된 분기 사이트가 하나 이상 있을 수도 있습니다. 이러한 사이트는 거의 모든 기능에 대해 중앙 사이트에 종속되어 있으므로 정확히 어떤 기능으로 구성합니까?

- SSN(Survivable Branch Appliance)은 PSTN(Public Switched Telephone Network) 게이트웨이와 몇 가지 비즈니스용 Skype 서버 결합합니다.

- SSS(Survivable Branch Server)는 등록자 및 중재 서버 Windows 설치된 비즈니스용 Skype 서버 실행되는 서버입니다.

- 독립 실행형 PSTN 게이트웨이(Survivable Branch Appliance의 일부가 아 아는 경우).

- 독립 실행형 중재 서버 또는 독립 실행형 중재 서버 풀(이 역할을 Survivable Branch Appliance와 함께 사용하려는 경우)

## <a name="whats-in-a-skype-for-business-server-site"></a>사이트가 비즈니스용 Skype 서버 있는 경우

좀 더 자세히 설명하기 위해 중앙 사이트에는 다음을 사용할 수 있습니다.

- 동일한 도메인 또는 다른 도메인에 있는 여러 프런트 엔드 풀(풀의 백 엔드 서버와 함께 프런트 엔드 풀의 모든 프런트 엔드 서버가 동일한 도메인에 있을 수 있습니다.)

- 여러 Standard Edition 서버

- Office 프레젠테이션을 공유하고 렌더링하기 위해 Office Web Apps 비즈니스용 Skype 서버 Web Apps 서버와 함께 PowerPoint 서버입니다.

- 경계 네트워크의 에지 서버 또는 에지 풀 배포에서 페더니티 파트너, 공용 IM 연결, XMPP(Extensible Messaging and Presence Protocol) 게이트웨이 및 원격 사용자 액세스를 지원하도록 하려는 경우 필요합니다. 자세한 내용은 에지 서버 계획 설명서에서 찾을 수 있습니다.

- 영구 채팅 서버. 사용자가 시간이 지날 때 지속되는 주제 기반의 여러 대화에 참여할 수 있도록 하려는 경우 유용합니다. 자세한 내용은 Planning for Persistent Chat Server 항목을 참조하십시오.

- 모니터링. 배포에서 A/V(오디오/비디오) QoE(QoE) 및 CDR(통화 정보 기록)에 대한 데이터 수집을 Enterprise Voice 및 A/V 회의에 사용됩니다. 이 내용은 Planning for Monitoring 항목에서 자세히 설명됩니다.

- Director 또는 Director 풀. 필수는 아니며, 사용자의 홈 풀에 대한 사용자 비즈니스용 Skype 리디렉션을 사용하도록 설정하려는 경우 유용합니다. Director를 배포하려는 경우 풀당 최대 10개가 지원됩니다. 필요한 경우 반드시 Planning for Directors 항목에서 계속 읽어야 합니다.

- 역방향 프록시입니다. 이 구성 요소는 비즈니스용 Skype 서버 구성 요소가 아니며 페더링 사용자에 대한 웹 콘텐츠 공유를 지원하려는 경우 모바일 트래픽을 지원하려는 경우 원격 사용자가 주소 책을 사용, 모임에 참가하는 등 환경에서 이 기능을 사용하려는 경우 이 구성 요소를 사용할 수 있습니다. 준비되면 역방향 프록시 서버 설정 항목에서 자세한 내용을 확인할 수 있습니다.

이러한 서버의 함께 사용에 대한 추가 정보는 아래에서 찾을 수 있습니다.

중앙 사이트에 배포된 모든 Standard Edition 풀 및 서버는 배포했다고 하여 다음을 공유합니다.

|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|
|디렉터 또는 디렉터 풀   |독립 실행형 중재 서버 또는 중재 서버 풀   |Office Web Apps 서버   |
|에지 서버 또는 에지 풀   |영구 채팅 서버 또는 영구 채팅 서버 풀   |모니터링   |

이 Exchange UM(통합 메시징) 서버는 어디에 있나요? 비즈니스용 Skype 서버 UM과 통합하려는 경우 비즈니스용 Skype 서버 Exchange 사용할 수 있지만 비즈니스용 Skype 서버 사이트의 구성 요소는 아니기 때문에 여기에서는 언급하지 않습니다.

중앙 사이트가 여러 개 있을 계획일 수 있으며, 이 경우 중앙 사이트에 배포된 경우 다음 서버 및 역할을 공유할 수 있습니다.

|&nbsp;|&nbsp;|
|:-----|:-----|
|독립 실행형 중재 서버 또는 중재 서버 풀   |에지 서버 또는 에지 풀   |
|영구 채팅 서버 또는 영구 채팅 서버 풀   |모니터링   |

마지막 목록과 마찬가지로 Exchange UM Server는 비즈니스용 Skype 서버 배포에 속하지 않지만 여기에도 동일한 범주에 속하기 때문에 여기서는 Exchange UM Server를 포함하지 않습니다.

물론 배포에 들어가는 몇 가지 다른 구성 요소와 옵션이 있습니다.

|&nbsp;|&nbsp;|&nbsp;|&nbsp;|
|:-----|:-----|:-----|:-----|
|방화벽   |PSTN 게이트웨이(배포하는 Enterprise Voice   |Exchange UM 서버(Exchange UM과 통합하려는 경우)   |DNS 부하 분산   |
|하드웨어 부하 분산 장치   |SQL Server 데이터베이스   |파일 공유   ||

## <a name="server-roles"></a>서버 역할

각 서버를 실행하는 비즈니스용 Skype 서버 하나 이상의 서버 역할을 실행합니다. 서버 역할은 해당 서버에서 비즈니스용 Skype 서버 정의된 서버 기능 집합입니다. 네트워크에서 사용 가능한 모든 서버 역할을 배포할 필요는 없습니다. 필요한 기능이 포함된 서버 역할만 설치하면 됩니다.

대부분의 서버 역할은 확장성 및 고가용성을 위해 모두 같은 서버 역할을 실행하는 여러 서버 풀을 배포할 수 있습니다. 풀의 각 서버는 동일한 서버 역할을 실행해야 합니다. 대부분의 풀 유형의 비즈니스용 Skype 서버 풀의 여러 서버 간에 트래픽을 분산하기 위해 부하 분산을 배포해야 합니다. 비즈니스용 Skype 서버 DNS(Domain Name System) 부하 분산과 하드웨어 부하 분산을 모두 지원할 수 있습니다.

### <a name="front-end-server-and-back-end-server"></a>프런트 엔드 서버 및 백 엔드 서버

비즈니스용 Skype 서버 Enterprise Edition 프런트 엔드 서버는 핵심 서버 역할로, 여러 가지 기본 비즈니스용 Skype 서버 실행됩니다. 프런트 엔드 서버와 백 엔드 서버는 모든 서버 배포에 필요한 비즈니스용 Skype 서버 Enterprise Edition 서버입니다.

프런트 엔드 풀은 동일하게 구성된 프런트 엔드 서버 집합으로서, 이러한 서버가 함께 일반 사용자 그룹에 대한 서비스를 제공합니다. 동일 역할을 실행하는 여러 서버로 구성된 풀은 확장성 및 장애 조치(Failover) 기능을 제공합니다.

프런트 엔드 서버에는 다음과 같은 항목이 포함됩니다.

- 사용자 인증 및 등록.

- 현재 상태 정보 및 연락처 카드 교환.

- 주소장 서비스 및 메일 목록 확장.

- IM 기능(다국어 IM 회의 포함)

- 웹 회의, PSTN 전화 접속 회의 및 A/V 회의(배포된 경우)

- 응용 프로그램 호스팅(예: 비즈니스용 Skype 서버 및 응답 그룹 응용 프로그램) 및 회의 도우미 응용 프로그램 모두에 대해 호스팅합니다.

- CDR(통화 정보 기록) 및 CER(통화 오류 기록)의 형식으로 사용 정보를 수집하는 모니터링(선택 사항). 이 정보는 Enterprise Voice A/V 회의에 대해 네트워크를 트래버스하는 미디어(오디오 및 비디오)의 품질에 대한 메트릭을 제공합니다.

- 웹 스케줄러 및 참가 시작 관리자와 같은 지원되는 웹 기반 작업에 대한 웹 구성 요소

- 준수 목적의 IM 통신 및 모임 콘텐츠에 대한 보관(선택 사항). 자세한 내용은 계획 설명서에서 [Planning for Archiving](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-archiving)을 참조하십시오.

    Lync Server 2010 및 이전 버전에서는 모니터링 및 보관이 별도의 서버 역할이 아니며 프런트 엔드 서버에는 함께 제공되지 않습니다.

- 영구 채팅이 사용하도록 설정된 경우 채팅방 관리를 위한 영구 채팅 웹 서비스 및 파일 업로드/다운로드를 위한 영구 채팅 웹 서비스(선택 사항)

프런트 엔드 풀은 사용자 및 회의 데이터의 기본 저장소로도 사용됩니다. 각 사용자에 대한 정보는 풀에 있는 3개의 프런트 엔드 서버 간에 복제되고 백 엔드 서버에서 백업됩니다.

또한 배포의 한 프런트 엔드 서버가 중앙 관리 서버를 실행하여 기본 구성 데이터를 관리하고 해당 서버를 실행하는 모든 서버에 비즈니스용 Skype 서버. 또한 중앙 관리 서버는 Lync Server 관리 셸 및 파일 전송 기능을 제공합니다.

백 엔드 서버는 프런트 엔드 풀에 Microsoft SQL Server 서비스를 제공하는 데이터베이스 서버를 실행하는 데이터베이스 서버입니다. 백 엔드 서버는 풀의 사용자 및 회의 데이터에 대한 백업 저장소 역할을 하며 응답 그룹 데이터베이스와 같은 다른 데이터베이스의 기본 저장소입니다. 단일 백 엔드 서버를 사용할 수 있지만 장애 조치(failover[)](../high-availability-and-disaster-recovery/back-end-server.md)에는 백 엔드 서버의 비즈니스용 Skype 서버 것이 좋습니다. 백 엔드 서버는 모든 소프트웨어 비즈니스용 Skype 서버 실행하지 않습니다.

> [!IMPORTANT]
> 데이터베이스를 다른 비즈니스용 Skype 서버 함께 두지 않는 것이 좋습니다. 그렇지 않으면 가용성 및 성능에 영향을 줄 수 있습니다.

> [!NOTE]
> SQL 미러링은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. AlwaysOn 가용성 그룹, AlwaysOn FCI(장애 조치(failover) 클러스터 인스턴스) 및 SQL 장애 조치(failover) 클러스터링 방법이 비즈니스용 Skype 서버 선호됩니다.

백 엔드 서버 데이터베이스에 저장되는 정보에는 현재 상태 정보, 사용자의 대화 상대 목록, 모든 현재 전화 회의의 상태에 대한 영구 데이터를 비롯한 회의 데이터 및 전화 회의 일정 데이터가 포함됩니다.

### <a name="edge-server"></a>에지 서버

에지 서버를 사용하면 사용자가 조직의 방화벽 외부의 사용자와 통신하고 공동 작업을 할 수 있습니다. 이러한 외부 사용자에는 현재 오프사이트에서 작업 중인 조직의 사용자, 페더러티 파트너 조직의 사용자 및 조직 배포에서 호스팅되는 회의에 참가할 수 있도록 초대된 외부 비즈니스용 Skype 서버 있습니다.

에지 서버를 배포하면 모바일 장치에서 Lync 기능을 지원하는 모바일 서비스도 사용하도록 설정됩니다. 사용자는 지원된느 Apple iOS, Android, Windows Phone 또는 Nokia 모바일 장치를 사용해서 인스턴트 메시지 전송 및 수신, 연락처 보기 및 현재 상태 보기와 같은 활동을 수행할 수 있습니다. 또한 모바일 장치에서는 클릭하여 회의 참가, 회사번호로 전화, 단일 번호 연결, 음성 메일, 부재 중 통화 등의 일부 Enterprise Voice 기능도 지원됩니다. 모바일 기능에는 또한 백그라운드에서 실행 중인 응용 프로그램을 지원하지 않는 모바일 장치를 위한 푸시 알림도 지원됩니다. 푸시 알림은 해당 모바일 응용 프로그램이 비활성 상태일 때 발생한 이벤트에 대해 모바일 장치에 전송되는 알림입니다.

에지 서버에는 또한 프런트 엔드 서버에 포함된 XMPP 게이트웨이를 포함하는 완전히 통합된 XMPP(Extensible Messaging and Presence Protocol) 프록시가 포함됩니다. 사용자가 인스턴트 메시징 및 현재 비즈니스용 Skype 서버 위해 XMPP 기반 파트너의 연락처를 추가할 수 있도록 이러한 XMPP 구성 요소를 구성할 수 있습니다.

> [!NOTE]
> XMPP 게이트웨이 및 xxies는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. 자세한 [내용은 XMPP 페더링 마이그레이션](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 을 참조하세요.

### <a name="mediation-server"></a>중재 서버

중재 서버는 Enterprise Voice, 업무를 통한 전화 및 전화 접속 회의를 구현하는 데 필요한 구성 요소입니다. 중재 서버는 신호 및 일부 구성에서 내부 비즈니스용 Skype 서버 인프라와 PSTN(Public Switched Telephone Network) 게이트웨이, IP-PBX 또는 SIP(Session Initiation Protocol) 트렁크 간의 미디어를 변환합니다. 중재 서버는 프런트 엔드 서버와 동일한 서버에 함께 배치하여 실행하거나 독립 실행형 중재 서버 풀에 별도로 배치한 상태로 실행할 수 있습니다.

자세한 내용은 [Mediation Server component in 비즈니스용 Skype 서버](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md).

### <a name="video-interop-server"></a>비디오 Interop 서버

Video Interop Server는 2015년 비즈니스용 Skype 서버 새로운 역할입니다. 이 기능을 사용하면 특정 타사 VTC(비즈니스용 Skype 서버 시스템) 솔루션과 통합할 수 있습니다. VIS는 제3자 전화 통신 시스템과 시스템 배포 간의 비즈니스용 Skype 서버 역할을 합니다. 이 릴리스에서 VIS는 Cisco/Tandberg 비디오 시스템과의 상호 운영성에 중점을  두고 있습니다.

자세한 내용은 [Plan for Video Interop Server in 비즈니스용 Skype 서버](../../plan-your-deployment/video-interop-server.md).

### <a name="director"></a>이사

이사는 사용자 비즈니스용 Skype 서버 인증할 수 있지만 사용자 계정을 제공하거나 현재 상태 또는 회의 서비스를 제공하지는 않습니다. 디렉터는 외부 사용자 액세스를 지원하는 배포에서 보안을 효과적으로 향상시켜줍니다. 디렉터는 요청을 내부 서버로 전송하기 전에 요청에 대한 인증을 수행할 수 있습니다. 서비스 거부 공격이 있더라도 공격이 디렉터에서 끝나고 프런트 엔드 서버에 도달하지 못합니다.

### <a name="persistent-chat-server-roles"></a>영구 채팅 서버 역할

> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요](/microsoftteams/upgrade-start-here). 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.

영구 채팅을 통해 사용자는 장기간 지속되는 주제 기반의 단체 대화에 참가할 수 있습니다. 영구 채팅 프런트 엔드 서버는 영구 채팅 서비스를 실행합니다. 영구 채팅 백 엔드 서버는 채팅 기록 데이터와 범주 및 채팅방에 대한 정보를 저장합니다. 영구 채팅 준수 백 엔드 서버(선택 사항)는 준수 목적으로 채팅 콘텐츠 및 준수 이벤트를 저장할 수 있습니다.

영구 채팅을 비즈니스용 Skype 서버 Standard Edition 동일한 서버에 함께 있는 영구 채팅을 실행할 수도 있습니다. 영구 채팅 프런트 엔드 서버를 프런트 엔드 서버와 함께 Enterprise Edition 수 없습니다.

자세한 내용은 [Plan for Persistent Chat Server in 비즈니스용 Skype 서버 참조하세요](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).

## <a name="high-availability-and-disaster-recovery-support"></a>고가용성 및 재해 복구 지원

비즈니스용 Skype 서버 풀링을 통해 서버 중복성으로 고가용성을 제공합니다. 특정 서버 역할을 실행하는 서버에서 오류가 발생하면 같은 역할을 실행하는 풀의 다른 서버가 해당 서버의 부하를 대신 처리합니다. 이는 프런트 엔드 서버, 에지 서버, 중재 서버 및 디렉터에 적용됩니다.

비즈니스용 Skype 서버 풀 페어링을 사용하도록 설정하여 재해 복구 조치도 제공합니다. 이 토폴로지가 배포되면 프런트 엔드 풀 쌍을 지정하고 각 풀은 별도의 데이터 센터 및 별도의 지리적 영역에 있는 쌍으로 지정합니다. 한 풀 또는 사이트가 다운되는 경우 서비스 중단을 최소화하면서 해당 풀의 사용자가 쌍의 다른 풀을 사용하게 리디렉션할 수 있습니다.

비즈니스용 Skype 서버 백 엔드 서버 고가용성을 위한 여러 옵션도 지원됩니다. 이러한 경계 및 제한은 다음과 같습니다.

- 데이터베이스 미러링

- AlwaysOn 가용성 그룹

- AlwaysOn FCI(장애 조치(Failover) 클러스터 인스턴스)

- SQL 클러스터링

풀 페어링 및 백 엔드 서버 고가용성에 대한 자세한 내용은 [Plan for high availability and disaster recovery in 비즈니스용 Skype 서버](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).

## <a name="server-collocation-in-skype-for-business-server"></a>비즈니스용 Skype 서버

이미 '공주'란 용어를 사용했지만 이 용어는 무엇을 의미하나요? 비즈니스용 Skype 서버 서버는 배치되는 서버 또는 다른 서버에서 일부 서버 역할과 기능을 찾을 수 있지만 시작할 때와 Standard Edition 또는 Enterprise Edition 서버 배포를 수행하고 있는지(각각 자체 규칙과 함께 제공) 혼동될 수 있습니다. 계획을 지원하기 위해 Standard Edition 서버 배포 및 Enterprise Edition 프런트 엔드 풀 배포에 서버 배치를 포함해야 합니다(대부분의 경우 이 정보는 동일하며 서로 다른 경우 특별히 호출).

### <a name="collocation-of-server-roles"></a>서버 역할의 함께 사용

Standard Edition 서버에는 다음과 같은 역할이 배치되어 있으며(추가 구성은 필요한 경우), Enterprise Edition 프런트 엔드 풀에서는 이 역할을 배치하거나 별도의 서버에 배포할 수 있습니다.

- 중재

이러한 서버 역할은 각각 별도의 서버에 배포해야 합니다.

- 이사

- Edge

- 비디오 Interop 서버

- Office Web Apps

### <a name="databases"></a>데이터베이스

이 영역은 Standard Edition 서버 배포와 Enterprise Edition 서버 풀 배포 간에 실제 차이점이 있는 영역이기 때문에 아래 두 섹션과 두 가지에 대한 몇 가지 추가 규칙이 있습니다.

#### <a name="standard"></a>Standard

SQL Server Express 서버에 Standard Edition 이동할 수 없습니다. 이는 매우 간단합니다. 또한 Standard Edition 서버에 영구 채팅 서버를 배포하는 경우 영구 채팅 및 영구 채팅 준수 데이터베이스를 Standard Edition 서버에 함께 배치할 수도 있지만 이렇게 할 수 없습니다.

> [!NOTE]
> 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요](/microsoftteams/upgrade-start-here). 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.

이러한 서버는 Standard Edition 서버에 함께 사용할 수 없지만 자체 데이터베이스 서버 하나에 함께 사용할 수 있습니다.

- 모니터링 데이터베이스

- 보관 데이터베이스

- Enterprise Edition 풀에 대한 모든 백 엔드 데이터베이스

#### <a name="enterprise"></a>엔터프라이즈

다음 데이터베이스는 동일한 백 엔드 에 함께 SQL Server.

- 백 엔드 데이터베이스

- 모니터링 데이터베이스

- 보관 데이터베이스

- 영구 채팅 데이터베이스

- 영구 채팅 준수 데이터베이스

#### <a name="both"></a>둘 다

이제 단일 비즈니스용 Skype 서버 인스턴스 또는 동일한 SQL 데이터베이스의 여러 SQL 인스턴스에 SQL Server 규칙이 추가로 추가되었습니다.

- 각 SQL 인스턴스는 Enterprise Edition 프런트 엔드 풀에 대한 단일 백 엔드 데이터베이스, 단일 모니터링 데이터베이스, 단일 보관 데이터베이스, 단일 영구 채팅 데이터베이스 및 단일 영구 채팅 준수 데이터베이스만 포함할 수 있습니다.

- 데이터베이스 서버는 두 개 이상의 Enterprise Edition 프런트 엔드 풀, 보관을 실행하는 서버 한 대, 모니터링을 실행하는 서버, 단일 영구 채팅 데이터베이스 및 단일 영구 채팅 준수 데이터베이스를 지원할 수 없지만 데이터베이스에서 동일한 SQL Server 인스턴스를 사용하는지 아니면 별도의 영구 채팅 준수 데이터베이스를 사용하는지 여부에 관계없이 각각 하나씩 지원할 수 SQL Server.

    > [!NOTE]
    > 영구 채팅은 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 2019년 8월에는 더 이상 비즈니스용 Skype 서버 없습니다. 동일한 기능을 사용할 수 Teams. 자세한 내용은 업그레이드 시작을 [Microsoft Teams 참조하세요](/microsoftteams/upgrade-start-here). 영구 채팅을 사용해야 하는 경우 이 기능이 필요한 사용자를 Teams 또는 비즈니스용 Skype 서버 2015를 계속 사용할 수 있습니다.

### <a name="file-shares"></a>파일 공유

파일 공유는 별도의 서버에 있을 수도 있습니다. 또는 다음 중 모두 또는 전체와 동일한 서버에 함께 사용할 수 있습니다.

- Enterprise Edition 프런트 엔드 풀의 백 엔드 서버를 포함하는 데이터베이스 서버

- 모니터링 데이터베이스

- 보관 데이터베이스

- 영구 채팅 데이터베이스

- 영구 채팅 준수 데이터베이스

> [!CAUTION]
> 이러한 서버에 파일 공유를 함께 사용할 수 있는 반면, 권장되지는 않습니다. 파일 공유를 다른 서버 역할과 함께 설치하는 경우 디스크 공간 및 성능 문제를 정기적으로 모니터링하고 있는지 확인하시기 바랍니다.

### <a name="keep-in-mind"></a>유의

- 역방향 프록시 서버는 비즈니스용 Skype 서버 아니며 토폴로지에 있지 않을 수도 있습니다. 페더링된 사용자에 대한 웹 콘텐츠 공유를 지원하려면 역방향 프록시가 필요합니다. 필요한 경우 다른 응용 프로그램에서 사용 비즈니스용 Skype 서버 이미 조직에 있는 기존 역방향 프록시 서버를 구성하여 서버에 대한 역방향 프록시 지원을 구현합니다.

- UM 구성 요소 또는 Exchange 서버 구성 요소를 SharePoint 역할과 함께 비즈니스용 Skype 서버 없습니다.

## <a name="see-also"></a>참고 항목

[에 대한 참조 토폴로지 비즈니스용 Skype 서버](reference-topologies.md)