---
title: 라이브 Microsoft Teams 무엇입니까?
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365solution-spcomms
- m365solution-scenario
ms.reviewer: sonua
audience: admin
search.appverid: MET150
description: 라이브 이벤트를 통해 사용자가 비디오 및 콘텐츠를 대규모 온라인 대상에게 브로드캐스트하는 방법을 Teams, Yammer 알아보겠습니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: 8f196e1539085966c22a775a784913ced417c9cb
ms.sourcegitcommit: 50111653f72f6758a3491a4dc3e91160ab75022c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2021
ms.locfileid: "51506725"
---
# <a name="what-are-microsoft-teams-live-events"></a>라이브 Microsoft Teams 무엇이 하나요

## <a name="overview"></a>개요

조직 Teams 이벤트를 통해 조직의 사용자는 대규모 온라인 대상에게 비디오 및 모임 콘텐츠를 브로드캐스트할 수 있습니다.

Microsoft 365 라이브 이벤트는 라이브 비디오 스트리밍을 새로운 수준으로 제공합니다. 라이브 이벤트는 라이브 이벤트 전, 중 및 후에 참석자들과의 전체 참여 수명 주기 전반에 걸쳐 연결을 장려합니다. Microsoft Stream, Teams 또는 커뮤니티를 사용하여 청중, 팀 또는 커뮤니티가 어디에 있든 라이브 이벤트를 만들 수 Yammer.  

Teams 채팅 기반 공동 작업, 통화, 모임 및 라이브 이벤트를 제공하면 모임의 대상을 확장할 수 있습니다. Teams 라이브 이벤트는 Teams 확장되어 사용자가 대규모 온라인 대상에게 비디오 및 모임 콘텐츠를 브로드캐스트할 수 있습니다. 라이브 이벤트는 이벤트 호스트가 상호 작용을 주도하고 청중 참여는 주로 호스트가 공유하는 콘텐츠를 보기 위한 일대다 통신을 위한 것입니다. 참석자는 라이브 또는 녹화된 이벤트를 Yammer Teams 또는 Stream에서 볼 수 있으며, 중재된 Q & 또는 Yammer 사용하여 발표자와 상호 작용할 수 있습니다.

Teams 라이브 이벤트는 다음 버전의 Skype 모임 브로드캐스트로 간주되어 나중에 브로드캐스트에서 제공하는 기능을 Skype 모임 합니다. 이 시점에서 Microsoft는 새 이벤트 또는 향후 Skype 모임 서비스를 중단하지 비즈니스용 Skype 사용자에 대한 브로드캐스트를 계속 지원할 것입니다. 그러나 화면 공유 및 외부 하드웨어/소프트웨어 인코더에 대한 지원을 포함하여 Teams 새롭고 흥미로운 기능을 사용할 수 있는 라이브 이벤트를 사용해보는 것이 권장됩니다.

이제 시작해보죠. 먼저 라이브 이벤트와 관련된 높은 수준의 구성 요소와 연결되는 방법을 Microsoft 365 다이어그램을 살펴 봐야 합니다.

![라이브 이벤트의 주요 구성 요소](../media/live-event-flow-diagram.png  "라이브 이벤트, 일정, 프로덕션, Stream 플랫폼, 인증된 타사 eCDN 공급자의 주요 구성 요소")

> [!Note]
> 브로드캐스트 기술의 특성을 Teams 라이브 이벤트가 보통(내부) 모임 모집단을 초과하는 경우가 종종 있습니다.
>
> 다른 더 큰 도달하는 미디어 브로드캐스트 서비스와 같은 경우처럼, 콘텐츠 배달 네트워크를 통해 수신자에게 라이브 이벤트의 콘텐츠를 배달합니다. 이 콘텐츠는 암호화 방법으로 보호하며 라이브 이벤트 모임 구성에 따라 받는 사람에게만 발급되는 액세스 토큰에 의해 권한 부여의 대상이 됩니다.
>
> 모임 콘텐츠가 이러한 대규모 대상에게 적합하거나 중요한 콘텐츠에 대해 대상이 적절하게 줄어든지 확인하도록 주의해야 합니다.  
>
> 업계에서 일반적인 경우와 같이 직원 또는 인프라와 같은 보안의 다른 요소에 손상이 가해지면 라이브 이벤트의 보안에 영향을 줄 수 있습니다. 조직은 라이브 이벤트 및 기타 브로드캐스트 서비스를 보안 계획 및 연습에 포함하는 것이 고려해야 합니다.

### <a name="event-group-roles"></a>이벤트 그룹 역할

라이브 이벤트는 Teams 성공적으로 브로드캐스트하고 참여할 수 있는 여러 역할(이끌이, 프로듀서, 발표자 및 참석자)에게 권한을 부여합니다. 자세한 내용은 이벤트 그룹 [역할 을 참조합니다.](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles)

## <a name="key-components"></a>주요 구성 요소

위의 그림에서 라이브 이벤트와 함께 사용되는 5개의 주요 구성 요소가 Teams.

> [!NOTE]
> 라이브 이벤트 및 참석자 환경을 설정하는 방법에 대한 개요는 이 짧은 비디오를 [참조하세요.](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)

### <a name="scheduling"></a>스컬링

Teams 권한으로 이벤트를 만들고, 이벤트 팀 구성원을 지정하고, 프로덕션 방법을 선택하고, 참석자 초대를 할 수 있는 기능을 제공합니다. 라이브 이벤트를 그룹 내에서 만든 Yammer 라이브 이벤트 참석자는 이벤트의 사용자와 상호 작용하는 데 Yammer 대화를 사용할 수 있습니다.

![새 라이브 이벤트 화면](../media/teams-live-events-schedule.png "새 라이브 이벤트를 만들고 예약하는 새 라이브 이벤트 화면을 보여주는 스크린샷")

> [!IMPORTANT]
> Teams는 사용자가 오프라인 상태이거나 제한된 대역폭으로 실행되는 경우 회의 또는 라이브 이벤트를 예약하지 못하도록 합니다.

### <a name="production"></a>프로덕션

비디오 입력은 라이브 이벤트의 기본이 며 단일 웹캠에서 멀티 카메라 전문 비디오 프로덕션에 다양할 수 있습니다. 이 Microsoft 365 라이브 이벤트는 다양한 프로덕션 시나리오를 지원하고, 웹캠을 Teams 또는 외부 앱 또는 디바이스에서 생성되는 이벤트를 사용하여 생성되는 이벤트를 포함합니다. 프로젝트 요구 사항 및 예산에 따라 이러한 옵션을 선택할 수 있습니다. 이벤트를 생성하는 방법에는 두 가지가 있습니다.

- **Teams**: 이 프로덕션 방법을 사용하면 사용자가 웹캠을 Teams 룸 시스템의 A/V 입력을 사용하여 라이브 이벤트를 Teams 수 있습니다. 이 옵션은 PC에 연결된 오디오 및 비디오 디바이스를 사용하려는 경우 또는 원격 발표자에 이벤트에 참가할 수 있도록 하는 경우 가장 빠르고 가장 빠른 옵션입니다. 이 옵션을 사용하면 사용자가 웹캠을 쉽게 사용할 수 있으며 해당 화면을 이벤트의 입력으로 공유할 수 있습니다.

- **외부 앱 또는 디바이스:** 외부 인코더를 사용하면 사용자가 Stream을 사용하여 외부 하드웨어 또는 소프트웨어 기반 인코더에서 직접 라이브 이벤트를 생성할 수 [있습니다.](https://stream.microsoft.com) 이 옵션은 실시간 RTMP(메시징 프로토콜) 서비스에 스트리밍을 지원하는 스튜디오 품질 장비(예: 미디어 믹서)가 이미 있는 경우 가장 좋습니다. 이러한 유형의 프로덕션은 일반적으로 미디어 믹서의 단일 스트림이 청중에게 브로드캐스트되는 이그제큐티브 타운 홀과 같은 대규모 이벤트에서 사용됩니다.

    ![외부 앱 또는 디바이스를 사용하여 생성된 라이브 이벤트](../media/teams-live-events-external-encoder.png "외부 앱 또는 디바이스 프로덕션 방법을 사용하여 생성되는 라이브 이벤트를 보여주는 스크린샷")

>[!Note]
> Microsoft Stream의 사용에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](../tmr-meeting-recording-change.md)로의 변경은 단계별 접근 방식을 사용합니다. 출시하면 이 환경에 대해 옵트인할 수 있고 11월에는 Stream을 계속 사용하려는 경우, 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 모임 녹음/녹화를 위해 비즈니스용 OneDrive와 SharePoint를 사용해야 합니다.

### <a name="streaming-platform"></a>스트리밍 플랫폼

라이브 이벤트 스트리밍 플랫폼은 다음 조각으로 만들어

- **Azure Media Services** [:](/azure/media-services/previous/) Azure Media Services 비디오 스트리밍 서비스를 통해 오늘날 가장 인기 있는 모바일 장치에서 더 많은 대상에게 도달할 수 있습니다. Media Services 접근성, 배포 및 확장성을 향상하고 콘텐츠를 보호하는 동시에 로컬 또는 전 세계 대상에게 콘텐츠를 쉽고 비용 효율적인 스트리밍할 수 있습니다.
- **Azure Content Delivery Network(CDN)**: 스트림이 라이브로 진행된 후 Azure Content Delivery Network(CDN) 를 통해 [전달됩니다.](/azure/cdn/) Azure Media Services 엔드포인트에 대한 통합 CDN 제공합니다. 이렇게 하면 버퍼링이 없는 전 세계 스트림을 볼 수 있습니다.

### <a name="enterprise-content-delivery-network-ecdn"></a>Enterprise Content Delivery Network(eCDN)

eCDN의 목표는 인터넷에서 비디오 콘텐츠를 찍고 네트워크 성능에 영향을주지 않고 엔터프라이즈 전체에 콘텐츠를 배포하는 것입니다. 다음 인증된 eCDN 파트너 중 하나를 사용하여 조직 내에서 개최되는 라이브 이벤트에 대한 네트워크를 최적화할 수 있습니다.

- [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](https://kollective.com/ecdn-solutions/microsoft-live-events/)
- [램프](https://rampecdn.com)
- [Riverbed](https://www.riverbed.com/solutions/office-365.html)

### <a name="attendee-experience"></a>참석자 환경

참석자 환경은 라이브 이벤트의 가장 중요한 측면으로, 참석자들은 문제 없이 라이브 이벤트에 참가할 수 있는 것이 중요합니다. 참석자 환경은 Stream Player(외부 Teams 디바이스에서 생성되는 이벤트의 경우)와 Azure Media Player(외부 앱 또는 디바이스에서 생성되는 이벤트의 경우)를 사용하며 데스크톱, 브라우저 및 모바일(iOS, Android)에서 작동합니다. Microsoft 365 및 Office 365 Yammer Teams 허브로 제공하고 라이브 참석자 환경이 이러한 공동 작업 도구에 통합됩니다.

![라이브 이벤트 참석자 환경의 예](../media/teams-live-events-attendee.png "라이브 이벤트 참석자 환경을 보여주는 스크린샷")

### <a name="live-event-usage-report"></a>라이브 이벤트 사용 현황 보고서

테넌트 관리자는 관리 센터의 라이브 이벤트에 대한 실시간 Microsoft Teams 있습니다.  라이브 [이벤트 사용 보고서는](../teams-analytics-and-reports/teams-live-event-usage-report.md) 조직에서 개최된 라이브 이벤트의 활동 개요를 보여 줍니다.  관리자는 이벤트 상태, 시작 시간, 보기 및 프로덕션 유형을 비롯한 이벤트 사용 정보를 볼 수 있습니다.  

## <a name="next-steps"></a>다음 단계

라이브 [이벤트에 대한 Teams 로 이동하세요.](plan-for-teams-live-events.md)

### <a name="related-topics"></a>관련 항목

- [Microsoft 365, Yammer 및 Microsoft Stream의 Microsoft Teams 라이브 이벤트](/stream/live-event-m365)
- [Microsoft Teams 라이브 이벤트 시작하기](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [라이브 이벤트가 Yammer](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Microsoft Stream의 라이브 이벤트](/stream/live-event-overview)
