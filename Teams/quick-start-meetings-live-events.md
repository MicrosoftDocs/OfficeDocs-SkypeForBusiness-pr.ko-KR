---
title: 모임, 웨비나 및 라이브 이벤트
ms.reviewer: ''
description: 관리자가 Microsoft Teams에서 모임, 웹 세미나 및 라이브 이벤트를 배포하고 구성하기 위한 가이드입니다.
ms.topic: article
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.service: msteams
ms.subservice: meetings
ms.custom: intro-overview
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
- highpri
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45148768d023b3cb6b609c1f315fe8d71031a573
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392198"
---
# <a name="meetings-webinars-and-live-events"></a>모임, 웨비나 및 라이브 이벤트

[!INCLUDE[Teams Premium](includes/teams-premium-ecm.md)]

Microsoft Teams에서는 모임, 웨비나, 라이브 이벤트 등 여러 가지 방법으로 모임을 할 수 있습니다.

관리자와 IT 전문가를 대상으로 하는 이 문서에서는 모임, 웨비나 및 라이브 이벤트의 차이점에 대해 설명합니다. 그런 다음 사용자를 위해 이 기능을 신속하게 롤아웃하는 데 필요한 정보에 대한 링크를 제공합니다.

[Meetings](#meetings), [webinars](#webinars), and [live events](#live-events) are all types of meetings, but webinars and live events provide additional control for the organizer over the conversation and participants. Webinars provide two-way interaction while live events provide a managed Q&A experience. 

모임 유형에 따라 참가자 제한 및 참가자 기능도 다릅니다. 

다음 표에는 세 가지 유형의 모임, 권장 참가자 수 및 참가자가 모임에서 상호 작용할 수 있는 방법이 요약되어 있습니다. 각 모임 유형에 대한 자세한 정보가 포함된 섹션은 다음 표를 따릅니다. 이 문서에는 [대규모 모임을 위한 모범 사례](#best-practices-for-large-meetings) 섹션도 포함되어 있습니다.

| 모임 유형 | 참가자 수 | 상호 작용 | 등록 지원 |
|----------|--------|--------|-----|
| 모임  | 최대 20,000* | - 최대 1,000명의 참가자가 완전히 상호 작용하는 동등한 모임 기능을 갖습니다. <br> - 1,000명 이상 최대 20,000명의 참가자에게 [보기 전용](view-only-meeting-experience.md) 기능이 있습니다.  | 예, 등록이 있는 모임 사용(웨비나 1.0) |
| 웨비나 | - 최대 1,000명<br>- 곧 제공될 [보기 전용](view-only-meeting-experience.md) 기능의 제한이 높아졌습니다. |- 최대 1,000명의 참가자가 완전한 대화형 기능을 사용할 수 있습니다.<br> - 대상 그룹 상호 작용을 구성할 수 있습니다.<br> - 발표자를 지정할 수 있습니다. | 예 |
| 라이브 이벤트 | 최대 20,000**명 |- 많은 대상 그룹에게 브로드캐스트할 수 있습니다. <br>- 대상 그룹 상호 작용을 위한 중재된 질문 및 답변입니다. <br> - 외부 발표자를 포함한 제작자 및 발표자를 지정할 수 있습니다.<br>- 보다 고도화된 프로덕션 기능을 지원합니다. | 아니요 |

*2022년 12월 31일까지 기존 10,000명에서 20,000명으로 상향 조정됩니다.

**2022년 12월 31일까지 기존 10,000명에서 20,000명으로 상향 조정됩니다. Yammer 및/또는 Microsoft Stream의 라이브 이벤트로 더 많은 수를 예약할 수 있습니다. 자세한 내용은 [Microsoft 365의 라이브 이벤트](/stream/live-event-m365)를 참조하세요. 참석자가 20,000명이 넘는 이벤트에는 [라이브 이벤트 지원 프로그램](/stream/live-events-assistance)이 필요합니다.

Note that NDI is fully supported in meetings, webinars, and live events, allowing you to produce the broadcast by using tools such as OBS and Wirecast. For more information, see [Use NDI® technology in Microsoft Teams](use-ndi-in-meetings.md).

> [!NOTE]
> 자세한 내용과 Microsoft Teams를 사용하여 온라인 이벤트를 제공하기 위한 역할별 지침을 얻으려면 [가상 이벤트 플레이북](https://aka.ms/VirtualEventPlaybook)을 참조하세요. Microsoft Tech Community [가상 이벤트 포럼](https://aka.ms/VirtualEventForum)에 참가할 수도 있습니다.

> [!NOTE]
> 다양한 플랫폼에서 Teams 모임 및 이벤트를 신속하게 구성하는 방법에 대한 자세한 내용은 [플랫폼별 Teams 기능](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)을 참조하세요.

## <a name="meetings"></a>모임

Teams의 **모임** 에는 최대 1,000명을 위한 오디오, 동영상 및 화면 공유와 1,000명 이상의 참가자를 위한 [보기 전용 기능](view-only-meeting-experience.md)이 ​​포함됩니다. 참가자는 Teams 모임에 참가하기 위해 조직의 구성원이거나 Teams 계정이 없어도 됩니다. 모임 참여 링크를 통해 일정 초대에서 직접 참여하거나 가능한 경우 오디오를 통해 전화를 걸 수 있습니다.  

관리자는 모임 설정을 구성하고 모임 정책을 지정하여 조직에 사용할 수 있는 모임 기능을 제어합니다.  

정기적으로 예약된 모임 외에도 사용자는 채널 모임을 만들 수 있습니다. 채널 모임을 사용하면 팀의 모든 사람이 모임이 있음을 확인하고 모임에 참여하고 모임 채팅을 사용할 수 있습니다. 채널 모임은 팀의 모든 사람을 모임에 빠르게 초대하는 방법입니다. 최종 사용자가 모임을 예약하는 방법에 대한 자세한 내용은 [모임 예약](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5)을 참조하세요.

보기 전용 모임 환경에 대한 자세한 내용은 [Teams 보기 전용 모임 환경](view-only-meeting-experience.md)을 참조하세요.

### <a name="articles-for-administrators"></a>관리자를 위한 게시물

다음 표에는 사용자가 검토할 주요 게시물이 하이라이트되어 있습니다.

| 게시물 | 설명 |
|----------|--------|
| [모임 설정](meeting-settings-in-teams.md) |  익명 사용자, 모임 초대 및 미디어 트래픽에 대한 모임 설정을 구성하는 방법을 설명합니다.  |
| [모임 정책](meeting-policies-overview.md)  | 모임 참가자가 사용할 수 있는 기능을 결정하는 정책을 만들고 관리하는 방법을 설명합니다. | 
| [Teams 클라우드 모임 녹화 관리](cloud-recording.md) | 모임 녹음을 관리하는 방법을 설명합니다. |
| [조직의 디바이스 관리](device-management.md)| 전화 및 Teams 룸과 같은 조직의 장치를 관리하는 방법을 설명합니다. |
| [실시간 원격 분석을 사용하여 모임 품질 저하 문제 해결](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md) | RTA(실시간 분석)를 사용하여 개별 사용자를 위해 Microsoft Teams 모임 품질 저하 문제를 해결하는 방법을 설명합니다.|

### <a name="key-training-for-end-users"></a>최종 사용자를 위한 핵심 교육

다음 표에는 조직의 최종 사용자가 사용할 수 있는 교육이 나와 있습니다.

| 교육 | 설명 |
|----------|--------|
| [모임 관리](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) | Teams 모임을 처음 사용하는 사용자를 위한 빠른 교육 비디오입니다. |
| [모임 예약](https://support.microsoft.com/office/schedule-a-meeting-in-teams-943507a9-8583-4c58-b5d2-8ec8265e04e5) | 다양한 유형의 모임을 예약하는 방법을 설명하는 게시물입니다. |
| [Teams로 효과적인 모임 실행](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings) | 모임을 더 매력적이고 생산적이며 의미 있게 만드는 방법에 대한 강사 주도 수업의 무료 수업입니다. |
| [Teams 모임 참가자 설정 변경](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) | 모임 옵션 관리에 대한 게시물입니다. |

## <a name="webinars"></a>웨비나

**웹 세미나** 는 발표자와 참가자가 명확한 역할을 하는 구조화된 모임입니다. 웨비나 모임과 Teams 모임의 주요 차이점은 웨비나는 강력한 등록 관리, 사용자 지정 가능한 이벤트 및 등록 사이트, 이벤트 지향 기본 모임 옵션을 지원한다는 것입니다.

조직에서 이미 웨비나를 사용하고 있는 경우 Teams 모임 정책 및 모임 등록을 지원하고 참여 데이터를 추적할 수 있는 다음 설정에 익숙합니다.

- AllowMeetingRegistration(사용 또는 사용 안 함)
- WhoCanRegister(게스트 또는 모든 사람을 제외한 회사의 모든 사용자)

새 웨비나 환경이 릴리스되면 다음 설정이 포함된 새 Teams 이벤트 정책이 제공됩니다.

- AllowWebinars(사용 또는 사용 안 함)
- EventAccessType(게스트 또는 모든 사람을 제외한 회사의 모든 사용자)

새 정책은 등록 및 추적을 계속 지원하며 웨비나 환경에 추가 기능을 제공합니다. 처음에는 다음을 사용할 수 있습니다.

- 사용 약관 사용자 지정 질문
- 발표자 bio
- 배너, 로고 및 미리 정의된 색
- 고급 등록 기능: 수동 승인, 대기 목록, 등록 날짜 및 시간 제한
- 등록 개요 및 관리: 각 이벤트에 대해 다른 등록 상태의 참석자 목록이 있는 등록 상태의 요약으로, 사용하도록 설정된 등록 기능에 따라 달라집니다.

새 정책을 사용하여 새 기능을 사용할 수 있게 되면 활용하려고 합니다.

기능 및 웨비나를 설정하는 방법에 대한 자세한 내용은 [웨비나 설정을 참조하세요](set-up-webinars.md).


### <a name="key-training-for-end-users"></a>최종 사용자를 위한 핵심 교육

다음 표에는 조직의 최종 사용자가 사용할 수 있는 교육이 나와 있습니다.

| 교육 | 설명 | 
|----------|--------|
| [Teams 웹 세미나 시작하기](https://support.microsoft.com/office/get-started-with-teams-webinars-42f3f874-22dc-4289-b53f-bbc1a69013e3) | Teams 웹 세미나를 처음 접하는 사용자를 위한 빠른 교육 비디오입니다. |
| [시각적 빠른 시작 가이드](https://adoption.microsoft.com/files/assets/TeamsWebinarsGetStartedGuide.pdf) | 웹 세미나 예약을 시작하는 방법을 설명하는 다운로드 가능한 시각적 가이드입니다. |


## <a name="live-events"></a>라이브 이벤트

**라이브 이벤트** 는 조직에서 최대 20,000명의 대규모 온라인 대상 그룹에게 스트리밍되는 이벤트를 예약하고 제작할 수 있는 구조화된 모임입니다. 라이브 이벤트에서 대상 그룹과의 상호 작용은 관리되는 질문 및 답변 환경입니다.

### <a name="articles-for-administrators"></a>관리자를 위한 게시물

다음 표에는 사용자가 검토할 주요 게시물이 하이라이트되어 있습니다.

| 게시물 | 설명 |
|----------|--------|
| [Teams 라이브 이벤트란 무엇인가요?](teams-live-events/what-are-teams-live-events.md)  | 라이브 이벤트에 대한 간략한 소개입니다. |
| [Teams 라이브 이벤트 계획](teams-live-events/plan-for-teams-live-events.md) | 라이브 이벤트를 구성하기 전에 알아야 할 사항입니다. |
| [Teams 라이브 이벤트 설정하기](teams-live-events/set-up-for-teams-live-events.md) | 네트워크 계획과 같은 전제 조건을 설명합니다. |
| [라이브 이벤트 구성](teams-live-events/configure-teams-live-events.md) | 라이브 이벤트 구성 단계입니다.|

### <a name="key-training-for-end-users"></a>최종 사용자를 위한 핵심 교육

다음 표에는 조직의 최종 사용자가 사용할 수 있는 교육이 나와 있습니다.

| 교육 | 설명 |
|:----------|:--------|
| [라이브 이벤트 시작하기](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a) | 라이브 이벤트 및 시작 방법에 대한 소개입니다. |
| [Teams 라이브 이벤트 동영상 교육](https://support.microsoft.com/en-us/office/plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502?ui=en-US&rs=en-US&ad=US) | 라이브 이벤트를 계획하고 예약하는 방법을 설명하는 비디오입니다.  |

대규모 가상 이벤트를 제작하려면 이벤트 이끌이, 기술 제작자, IT 전문가 및 콘텐츠 제작자를 위한 지침이 있는 [가상 이벤트 가이드](https://adoption.microsoft.com/virtual-event-guidance/)를 검토하세요.

## <a name="apps-for-meetings"></a>모임용 앱

Microsoft enables you to enhance meeting experiences by integrating and using meeting apps. For example, whiteboard integration in Teams meetings is powered by the Whiteboard web app, which lets Teams meeting participants draw, sketch, and write together on a shared digital canvas.

Teams와 함께 제공되는 앱을 사용하고, 인증된 타사 앱과 템플릿을 사용하고, 고유한 사용자 지정 앱을 만들어 Teams 배포에 모임 앱을 추가할 수 있습니다.

다음 표에는 자세한 내용이 나와 있는 게시물이 나와 있습니다.

| 게시물 | 설명 |
|----------|--------|
| [Teams 앱 개요](deploy-apps-microsoft-teams-landing-page.md) | 앱 소개 및 조직에 앱을 배포하는 방법입니다. |
| [Teams 모임용 앱](/microsoftteams/platform/apps-in-teams-meetings/teams-apps-in-meetings) | 모임 앱 확장성 개요, API 참조, 모임용 앱 활성화 및 구성 방법. |
| [Teams에서 화이트보드 관리](manage-whiteboard.md) | 화이트보드 기능과 조직에 대해 활성화 및 비활성화하는 방법을 설명합니다. |

## <a name="license-requirements-for-meetings-webinars-and-live-events"></a>모임, 웨비나 및 라이브 이벤트에 대한 라이선스 요구 사항

라이선스 없이 누구나 Teams 모임, 웹 세미나 또는 공개 라이브 이벤트에 무료로 참석할 수 있습니다.

모임, 웨비나 또는 라이브 이벤트를 조직, 예약 및 주최하는 사용자에게는 [Microsoft Teams 서비스 설명](/office365/servicedescriptions/teams-service-description)에 나열된 Microsoft 365 라이선스 중 하나가 필요합니다. 이미 Teams를 사용하고 있다면 모임, 웨비나 및 라이브 이벤트를 구성하고 주최하는 데 필요한 라이선스가 있을 것입니다.

Teams Premium 라이선스에 대한 자세한 내용은 [Teams Premium 라이선스](teams-add-on-licensing/licensing-enhance-teams.md)를 참조하세요.

사람들이 전화로 모임에 전화를 걸 수 있도록 하려면 오디오 회의를 설정해야 합니다. 오디오 회의에 대한 자세한 내용은 [Teams의 오디오 회의](deploy-audio-conferencing-teams-landing-page.md)를 참조하세요.

## <a name="best-practices-for-large-meetings"></a>대규모 모임에 대한 모범 사례

이 섹션에서는 관리자를 위한 지침과 함께 관리자가 발표자 및 이끌이와 공유할 수 있는 팁을 제공합니다.

성공적인 이벤트를 실행하려면 아래에 설명된 방법을 따르세요.

- 대규모 모임, 웨비나 및 실시간 이벤트에서 최상의 경험을 위해 Microsoft는 Teams 데스크톱 클라이언트 또는 Teams 모바일 클라이언트의 최신 버전을 사용할 것을 권장합니다.

- 온-프레미스와 원격 사용자 모두에 대해 모든 Microsoft [네트워크 연결 원칙](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)을 준수했는지 확인합니다.
- [실시간 데이터 원격 분석](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-real-time-call-quality-analytics/ba-p/2912146)을 사용하여 이벤트를 모니터링하고 가능한 문제와 원인을 식별합니다.
  - 임계값을 초과하는 메트릭으로 인해 사용자 경험이 좋지 않은 사용자를 위해 원격 측정을 [분석](use-real-time-telemetry-to-troubleshoot-poor-meeting-quality.md)하도록 모임 모니터를 지정합니다.
  - 모임 모니터를 발표자로 설정하여 불량 비디오 스트림을 비활성화하고, 우발적인 라이브 마이크를 음소거하고, 필요한 경우 참석자를 제거합니다.

### <a name="guidelines-for-your-end-users"></a>최종 사용자를 위한 지침

이끌이와 발표자는 다음 권장 사항을 구현해야 합니다.

- 참가자가 10명 이상인 모임의 경우 [Q&A](/MicrosoftTeams/manage-qna-for-teams)를 사용하여 참가자에게 공식적으로 질문하고 질문에 대한 답변을 받을 수 있는 기회를 제공하고 구조화된 토론에 참여할 수 있습니다.

- 원활한 모임을 만들기 위해 이벤트 이끌이는 미리 정의된 발표자를 설정할 수 있습니다. 모임이 시작된 후 발표자는 다른 참석자를 발표자 역할로 승격할 수도 있습니다.

- 모임 옵션을 통해 공동 이끌이 정의(공개 미리 보기)

- 참석자의 경험을 제어하기 위해 비디오 및 마이크 설정을 사전 구성합니다.
  - 방해를 피하기 위해 참석자의 마이크를 비활성화합니다. 누군가가 모임 중에 상호 작용해야 하는 경우 손을 들었을 때 음소거 해제를 허용합니다.
  - 시각적 방해를 피하기 위해 참석자의 비디오를 비활성화합니다. 모임의 적절한 시간 동안 모든 참석자 또는 특정 개인에게 비디오가 허용될 수 있습니다.

- 모임 중에 설문 조사 및 Q&A를 사용합니다.

- 로비 제어를 사용하여 모임 입장 또는 대기실 보류를 제어합니다.

- 이벤트 며칠 전과 당일에 네트워크 적합성을 확인하려면 [Microsoft 365 네트워크 연결 테스트](https://connectivity.office.com/)를 실행하세요.

- 집에서 발표하는 경우 다른 장치가 고대역폭을 사용하고 있지 않은지 확인하세요(스트리밍 서비스, 온라인 게임, 대용량 다운로드).

- 보다 안정적인 오디오, 비디오 및 화면 공유를 위해 유선 연결을 통해 엔드포인트에서 프레젠테이션하세요.

- 사용자가 데스크톱 또는 모바일 장치에서 최신 Teams 앱을 사용 중인지 확인하세요.

- 노트북을 사용할 때 높은 네트워크 연결과 충분한 전원을 확인하세요.

- 장치, 조명 또는 네트워크 문제를 식별하기 위해 이벤트 전에 테스트 실행을 예약합니다. 이렇게 하면 이끌이/발표자가 사용할 기능에 익숙해질 수도 있습니다.
  - 문제가 발생한 경우 수정 노력이 성공적으로 수행되었는지 확인하기 위해 추가 연습 실행을 예약합니다.
  
- 스포트라이트, PowerPoint Live, 모임 녹음, 캡션 및 텍스트 변환과 같은 기능을 활용하여 참여와 효율성을 높입니다.

- 발표자와 참가자는 최적의 경험을 제공하기 위해 Teams 데스크톱 앱을 사용해야 합니다.

- 참가자는 주의가 산만하지 않도록 대규모 모임 중에 채팅 알림을 꺼야 합니다.

- 대규모 모임을 호스트하는 방법에 대한 자세한 내용은 [대규모 Teams 모임에 대한 모범 사례](https://support.microsoft.com/office/best-practices-for-a-large-teams-meeting-ce2cdb9a-0546-43a4-bb55-34ab98ab6b16)를 참조하세요.

## <a name="related-topics"></a>관련 항목

[Teams의 모임 및 모임](deploy-meetings-microsoft-teams-landing-page.md)

[Teams에서 웨비나 설정](set-up-webinars.md)

[Teams의 라이브 이벤트](teams-live-events/what-are-teams-live-events.md)

[Teams 보기 전용 모임 환경](view-only-meeting-experience.md)

[Teams의 제한과 사양](limits-specifications-teams.md)

