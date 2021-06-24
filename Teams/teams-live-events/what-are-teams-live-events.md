---
title: Microsoft Teams 라이브 이벤트란 무엇인가요?
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
description: 라이브 이벤트를 통해 사용자가 Teammer, Yammer 및 Stream에서 대규모 온라인 청중에게 비디오 및 컨텐츠를 브로드캐스트할 수 있는 방법을 알아보세요.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.liveevents
- ms.teamsadmincenter.liveevents.policies
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 0d1d453e0d9d6575ec108b4bc17cdce1f4dac839
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096332"
---
# <a name="what-are-microsoft-teams-live-events"></a>Microsoft Teams 라이브 이벤트란

## <a name="overview"></a>개요

Teams 라이브 이벤트를 사용하여 조직의 사용자는 비디오 및 모임 콘텐츠를 대규모 온라인 대상 그룹에 브로드캐스트할 수 있습니다.

Microsoft 365 라이브 이벤트는 라이브 비디오 스트리밍을 새로운 차원으로 끌어올립니다. 라이브 이벤트는 전체 참여 수명 주기 동안 라이브 이벤트 전, 도중 및 후에 참여자들과의 연결을 장려합니다. Microsoft Stream, Teams 또는 Yammer를 사용하여 대상 그룹, 팀 또는 커뮤니티가 상주하는 모든 곳에 라이브 이벤트를 만들 수 있습니다.  

Teams는 채팅 기반 공동 작업, 통화, 모임 및 라이브 이벤트를 제공하여 모임 대상을 확장할 수 있습니다. Teams 라이브 이벤트는 Teams 모임의 확장으로, 사용자가 온라인 대규모 청중에게 동영상 및 회의 내용을 브로드캐스트할 수 있게 해줍니다. 라이브 이벤트는 이벤트 주최자가 상호 작용을 주도하는 일대다 통신을 위한 것이며, 주로 호스트에서 공유하는 콘텐츠를 보기 위한 청중 참여입니다. 참석자는 Yammer, Teams 또는 Stream에서 라이브 이벤트나 녹음/녹화된 이벤트를 볼 수 있으며 중재 Q&A 또는 Yammer 대화를 사용하여 발표자와 상호 작용할 수 있습니다.

Teams 라이브 이벤트는 Skype 모임 브로드캐스트의 다음 버전으로 Skype 모임 브로드캐스트에서 제공하는 기능을 대체하게 됩니다. 현재 Microsoft는 비즈니스용 Skype를 조직에서 사용하는 사용자를 위해 Skype 모임 브로드캐스트를 신규 이벤트나 향후 이벤트에 대한 서비스 중단 없이 계속 지원할 예정입니다. 하지만 Teams 라이브 이벤트를 통해 화면 공유 및 외부 하드웨어/소프트웨어 암호기를 지원하는 등 새롭고 흥미로운 모든 기능을 사용해 보는 것이 좋습니다.

지금부터 시작하겠습니다. 먼저 다음 다이어그램에서 Microsoft 365 라이브 이벤트와 관련된 상위 구성 요소와 이러한 구성 요소의 연결 방식을 살펴보세요.

![라이브 이벤트의 주요 구성 요소](../media/live-event-flow-diagram.png  "라이브 이벤트, 예약, 운영, 스트림 플랫폼, 인증된 타사 eCDN 공급업체의 주요 구성 요소")

> [!Note]
> Teams 라이브 이벤트는 브로드캐스트 기술의 특성을 고려할 때 일반(내부) 모임 인원을 초과하는 경우가 많다는 점을 강조하고 싶습니다.
>
> 다른 대규모 미디어 브로드캐스트 서비스의 경우와 마찬가지로 라이브 이벤트에 대한 콘텐츠를 수신자에게 전달하기 위해 콘텐츠 전송 네트워크에 의존합니다. 이 콘텐츠는 암호화 방법으로 보호되며 실시간 이벤트 모임 구성에 따라 수신인에게만 발급되는 액세스 토큰에 의해 인증됩니다.
>
> 모임 내용이 이렇게 많은 청중에게 적합한지 또는 민감한 내용에 대해 청중이 적절히 감소하는지 확인하는 데 각별한 주의를 기울여야 합니다.  
>
> 업계에서 흔히 볼 수 있듯이 직원이나 인프라와 같은 다른 보안 요소가 손상될 경우 라이브 이벤트의 보안에 영향을 줄 수 있습니다. 조직은 보안 계획 및 연습에 라이브 이벤트 및 기타 브로드캐스트 서비스를 포함시키는 것을 고려해야 합니다.

### <a name="event-group-roles"></a>이벤트 그룹 역할

Teams의 라이브 이벤트는 여러 역할(주최자, 프로듀서, 발표자 및 참석자)이 성공적으로 이벤트를 브로드캐스트하고 참여할 수 있도록 합니다. 자세한 내용은 [이벤트 그룹 역할](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a?ui=en-US&rs=en-US&ad=US#bkmk_roles)을 참조하세요.

## <a name="key-components"></a>핵심 구성 요소

위의 그림을 보면 Teams의 라이브 이벤트와 함께 사용되는 다섯 가지 주요 구성 요소가 있음을 알 수 있습니다.

> [!NOTE]
> 라이브 이벤트 및 참석자 환경을 설정하는 방법에 대한 개요는 짧은 [비디오](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502)를 확인하세요.

### <a name="scheduling"></a>일정

Teams에서는 주최자가 적절한 참석자 권한을 가진 이벤트를 만들며 이벤트 팀 구성원을 지정하고 프로덕션 방법을 선택하고 참석자를 초대할 수 있는 기능을 제공합니다. Yammer 그룹 내에서 라이브 이벤트를 만든 경우 라이브 이벤트 참석자는 이벤트에서 사용자와 상호 작용을 위해 Yammer 대화를 사용할 수 있습니다.

![새 라이브 이벤트 화면](../media/teams-live-events-schedule.png "새 라이브 이벤트를 만들고 예약하기 위한 새 라이브 이벤트 화면이 표시된 스크린샷")

> [!IMPORTANT]
> Teams는 사용자가 오프라인 상태이거나 제한된 대역폭으로 실행되는 경우 회의 또는 라이브 이벤트를 예약하지 못하도록 합니다.

### <a name="production"></a>프로덕션

비디오 입력은 라이브 이벤트의 기초이며 단일 웹캠에서 다중 카메라 전문 비디오 제작까지 다양할 수 있습니다. Microsoft 365의 라이브 이벤트는 웹캠을 사용하여 Teams에서 제작한 이벤트 또는 외부 응용 프로그램 또는 디바이스에서 생성된 이벤트를 비롯한 다양한 프로덕션 시나리오를 지원합니다. 이러한 옵션은 프로젝트 요구 사항 및 예산에 따라 선택할 수 있습니다. 이벤트를 생성하는 방법에는 두 가지가 있습니다.

- **Teams**: 이 제작 방법을 사용하면 웹캠을 사용하거나 Teams 룸 시스템의 A/V 입력을 사용하여 Teams에서 라이브 이벤트를 생성할 수 있습니다. PC에 연결된 오디오 및 비디오 장치를 사용하려는 경우 또는 이벤트에 참여하도록 원격 발표자를 초대하는 경우 이 옵션이 가장 빠르고 최상의 옵션입니다. 이 옵션을 사용하면 웹캠을 쉽게 사용하고 이벤트에서 입력으로 화면을 공유할 수 있습니다.

- **외부 앱 또는 디바이스**: 외부 인코더를 사용하면 사용자가 외부 하드웨어나 소프트웨어 기반 인코더에서 [Stream](https://stream.microsoft.com)을 통해 직접 라이브 이벤트를 생성할 수 있습니다. 이 옵션은 RTMP(실시간 메시징 프로토콜) 서비스로 스트리밍을 지원하는 스튜디오 품질 장비(예: 미디어 믹서)가 이미 있는 경우에 가장 좋습니다. 이러한 유형의 프로덕션은 일반적으로 경영진 타운 홀과 같은 대규모 이벤트에서 사용됩니다. 이 홀에서는 미디어 믹서의 단일 스트림이 청중에게 방송됩니다.

    ![외부 앱 또는 디바이스를 사용하여 생성된 라이브 이벤트](../media/teams-live-events-external-encoder.png "외부 앱 또는 기기 제작 방법을 사용하여 생성된 라이브 이벤트를 보여주는 스크린샷")

>[!Note]
> Microsoft Stream의 사용에서 [모임 녹음/녹화를 위해 비즈니스용 OneDrive 및 SharePoint](../tmr-meeting-recording-change.md)로의 변경은 단계별 접근 방식을 사용합니다. 출시하면 이 환경에 대해 옵트인할 수 있고 11월에는 Stream을 계속 사용하려는 경우, 옵트아웃해야 합니다. 2021년 초에는 모든 고객이 모임 녹음/녹화를 위해 비즈니스용 OneDrive와 SharePoint를 사용해야 합니다.

### <a name="streaming-platform"></a>스트리밍 플랫폼

라이브 이벤트 스트리밍 플랫폼은 다음 부분으로 구성됩니다.

- **Azure Media Services**:  [Azure Media Services](/azure/media-services/previous/)는 오늘날의 가장 인기 있는 모바일 디바이스를 통해 보다 많은 시청자에게 브로드캐스트 품질의 비디오 스트리밍 서비스를 제공합니다. 미디어 서비스는 접근성, 배포 및 확장성을 향상시키며 콘텐츠를 보호하는 동시에 로컬 또는 전 세계 청중에게 콘텐츠를 쉽고 비용 효율적으로 스트리밍할 수 있도록 지원합니다.
- **Azure CDN(콘텐츠 전송 네트워크)**:  스트림이 라이브 상태가 되면 [Azure CDN(콘텐츠 전송 네트워크)](/azure/cdn/)을 통해 전송됩니다. Azure Media Services는 스트리밍 엔드포인트를 위한 통합 CDN을 제공합니다. 이를 통해 버퍼링 없이 전 세계에서 스트림을 볼 수 있습니다.

### <a name="enterprise-content-delivery-network-ecdn"></a>엔터프라이즈 CDN(콘텐츠 전송 네트워크)

eCDN의 목표는 인터넷에서 비디오 콘텐츠를 가져와 네트워크 성능에 영향을 주지 않고 기업 전체에 콘텐츠를 배포하는 것입니다. 다음 공인 eCDN 파트너 중 하나를 사용하여 조직 내에서 열리는 라이브 이벤트에 맞게 네트워크를 최적화할 수 있습니다.

- [하이브](https://www.hivestreaming.com/partners/integration-partners/microsoft/)
- [Kollective](https://kollective.com/ecdn-solutions/microsoft-live-events/)
- [램프](https://rampecdn.com)
- [Riverbed](https://www.riverbed.com/solutions/office-365.html)

### <a name="attendee-experience"></a>참석자 환경

라이브 이벤트의 가장 중요한 측면은 참가자 환경이며, 문제 없이 라이브 이벤트에 참여할 수 있는 것이 중요합니다. 참석자 환경은 Stream Player(Teams에서 생성된 이벤트의 경우)와 Azure Media Player(외부 앱 또는 디바이스에서 생성된 이벤트의 경우)를 사용하며 데스크톱, 브라우저 및 모바일(iOS, Android)에서 작동합니다. Microsoft 365 및 Office 365는 Yammer와 Teams를 두 개의 공동 작업 허브로 제공하며, 라이브 참가자 환경이 이러한 공동 작업 도구에 통합되어 있습니다.

![라이브 이벤트 참석자 환경의 예](../media/teams-live-events-attendee.png "라이브 이벤트 참석자 환경을 보여 주는 스크린샷")

### <a name="live-event-usage-report"></a>라이브 이벤트 사용 현황 보고서

테넌트 관리자는 Microsoft Teams 관리 센터에서 라이브 이벤트에 대한 실시간 사용 분석을 볼 수 있습니다.  [라이브 이벤트 사용 현황 보고서](../teams-analytics-and-reports/teams-live-event-usage-report.md)는 조직에서 개최되는 라이브 이벤트의 활동 개요를 보여 줍니다.  관리자는 이벤트 상태, 시작 시간, 보기 및 운영 유형을 비롯한 이벤트 사용량 정보를 볼 수 있습니다.  

## <a name="next-steps"></a>다음 단계

[Teams 라이브 이벤트 계획](plan-for-teams-live-events.md)으로 이동합니다.

### <a name="related-topics"></a>관련 항목

- [Yammer, Microsoft Teams 및 Microsoft Stream에서 Microsoft 365 라이브 이벤트 진행](/stream/live-event-m365)
- [Microsoft Teams 라이브 이벤트 시작하기](https://support.office.com/article/d077fec2-a058-483e-9ab5-1494afda578a)
- [Yammer의 라이브 이벤트](https://support.office.com/article/live-events-in-yammer-4ece0ee2-c268-4636-bf2a-16e454befe57)
- [Microsoft Stream의 라이브 이벤트](/stream/live-event-overview)
