---
title: 의료 조직용 Teams 시작
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-overview
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Microsoft Teams Telehealth, EHR 통합, Frontline Worker 시스템 통합 및 Patients 앱과 같은 의료 기능에 대해 자세히 배워 봐야 합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: a5b8ea7cddba8def74a1f5b839710cf73bafc67e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125771"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a>의료 조직용 Teams 시작

Microsoft Teams는 병원 및 기타 의료 조직에 유용한 다양한 원격 분석 기능을 제공합니다. Teams 기능은 다음과 같은 병원을 지원하기 위해 개발 중입니다.

- 가상 방문 및 EHR(Electronic Healthcare Record) 통합
- Teams 정책 패키지
- 보안 메시징
- Teams 서식 파일
- 관리 조정 및 공동 작업

이 기능은 Microsoft Cloud for Healthcare의 일부입니다. Microsoft [Cloud for Healthcare에서](https://docs.microsoft.com/industry/healthcare)Azure, Dynamics 365 및 Microsoft 365의 기능을 통합하는 이 솔루션을 사용하는 방법을 자세히 설명합니다.

Microsoft Teams에서 의료 팀 공동 작업을 향상하기 위해 의료 컬렉션을 사용하는 방법을 자세히 알아보는 다음 비디오를 시청합니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hqan]

> [!NOTE]
> 이 섹션의 콘텐츠에서는 조직에 Teams를 이미 배포했다고 가정합니다. 아직 Teams를 출시하지 않은 경우 먼저 Microsoft Teams를 롤아웃하는 [방법을 읽어 읽습니다.](../../How-to-roll-out-teams.md)

의료 조직에서 사용할 수 있는 시나리오는 다음과 같습니다.

| 시나리오 | 설명 | 요구 사항 |
| -------- | -------- | -------- |
| [EHR(Electronic Healthcare Record) 통합을 통해 가상 방문](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 환자와 가상 방문을 예약, 관리 및 수행합니다. 이 시나리오는 가상 방문을 지원하기 위해 Microsoft Teams와 Epic 플랫폼을 연결합니다. | Microsoft Teams EHR Connector 독립 실행형 제안에 대한 Microsoft Cloud for Healthcare 또는 구독에 대한 활성 구독입니다. <br> 사용자에게는 Microsoft Teams 모임이 포함된 적절한 Microsoft 365 또는 Office 365 라이선스가 있어야 합니다*. <br> 조직에는 2018년 11월 이후 버전이 있어야 합니다. <br>[EHR 요구 사항에 대한 세부 정보](ehr-admin.md#before-you-begin) |
| [Microsoft Bookings 및 Bookings 앱을 통해 가상 방문](#virtual-visits-and-electronic-healthcare-record-ehr-integration) | 환자와 가상 방문을 예약, 관리 및 수행합니다. 이 시나리오는 가상 방문을 지원하기 위해 Microsoft Bookings를 사용 합니다. | 조직에 대해 Microsoft Bookings를 설정해야 합니다. <br> Bookings 앱의 모든 사용자와 모임에 참여하는 모든 직원에게 Teams 모임 예약*을 지원하는 라이선스가 있어야 합니다. <br>[Bookings 요구 사항에 대한 세부 정보](../../bookings-app-admin.md#prerequisites-for-using-the-bookings-app-in-teams)|
| [Teams 정책 패키지](#teams-policy-packages)| 의료 작업자, 정보 근로자 및 환자 방 디바이스에 Teams 기능에 대한 적절한 액세스 권한이 있도록 합니다.| 사용자에게 적절한 라이선스*가 있어야 합니다. |
| [보안 메시징](#secure-messaging) | 긴급한 메시지에 더 빠르게 주의를 기울이면 메시지가 수신 및 읽히고 있다는 확신을 얻을 수 있습니다. | 사용자에게 적절한 라이선스*가 있어야 합니다.  |
| [Teams 서식 파일](#teams-templates-for-healthcare-organizations) | 구, Pod 또는 부서 내에서 또는 여러 구, Pod 및 병원 내의 부서 간 통신 및 공동 작업을 위해 미리 정의한 설정, 채널 및 미리 설치된 앱 템플릿이 포함된 팀을 만듭니다. | 사용자에게 적절한 라이선스*가 있어야 합니다.  |
| [관리 조정 및 공동 작업](#care-coordination-and-collaboration) | 의사와 직원은 일정, 문서, 작업 등에서 내부적으로 공동 작업할 수 있습니다.| 사용자에게 적절한 라이선스*가 있어야 합니다. |

*Office 365 A3, A5, E3 및 E5뿐만 아니라 Microsoft 365 Business Standard, A3, A5, E3 및 E5도 지원됩니다. 일반 Teams 라이선스에 대한 자세한 내용은 Teams에 대한 사용자 [액세스 관리를 참조하세요.](../../user-access.md)

## <a name="virtual-visits-and-electronic-healthcare-record-ehr-integration"></a>가상 방문 및 EHR(Electronic Healthcare Record) 통합

Microsoft Teams의 전체 모임 플랫폼을 사용하여 환자와 가상 방문을 예약, 관리 및 수행합니다.

- 조직에서 이미 전자 상태 레코드 또는 EHR을 사용하는 경우 더 원활한 환경을 위해 Microsoft Teams를 통합할 수 있습니다. Microsoft Teams EHR(Electronic Health Record) 커넥터를 사용하면 의료진이 EHR 시스템에서 직접 Teams의 다른 공급자와 가상 환자 방문 또는 상담을 쉽게 할 수 있습니다. 자세한 내용은 Teams를 통해 가상 [방문 - EHR에 통합을 참조합니다.](ehr-admin.md)
- 지원되는 EHR을 사용하지 않는 경우 Teams에서 Microsoft Bookings 및 Bookings 앱을 사용할 수 있습니다. 자세한 내용은 Microsoft Teams의 Bookings 앱 및 가상 [방문을 참조하세요.](../../bookings-app-admin.md)

![Microsoft Teams를 통해 가상 방문](../../media/virtual-visits-teams.png)

## <a name="teams-policy-packages"></a>Teams 정책 패키지

Teams 정책 패키지를 적용하여 Teams에서 다양한 역할을 할 수 있는 작업을 정의합니다. 예를 들어 다음에 대한 정책을 지정합니다.

- 등록된 간호사, 간호사, 의사 및 사회복지사와 같은 의료 근로자가 채팅, 통화, 교대 근무 관리 및 모임에 대한 모든 권한을 가할 수 있도록 합니다.
- IT 직원, 정보 전문가, 재무 담당자 및 규정 준수 담당자와 같은 의료 조직의 정보 근로자는 채팅, 통화 및 모임에 대한 모든 권한을 가할 수 있습니다.
- 환자실 디바이스에 대한 설정을 제어하는 환자실입니다.

자세한 내용은 [의료용 Teams 정책 패키지를 참조합니다.](../../policy-packages-healthcare.md)

## <a name="secure-messaging"></a>보안 메시징

보안 메시징은 다음과 같은 몇 가지 새로운 기능을 포함하여 상태 팀 내에서 공동 작업을 지원합니다.

- 메시지 보낸 사람이 메시지에 대해 특별한 우선 순위를 설정할 수 있으므로 받는 사람이 메시지를 읽을 때까지 반복적으로 알림을 수신자에게 전달합니다.
- 메시지 보낸 사람이 읽은 확인을 요청할 수 있으므로 메시지 받는 사람이 보낸 메시지를 읽은 경우 알림을 보냅니다.

이러한 기능을 함께 사용하면 긴급한 메시지에 더 빠르게 주의를 기울일 수 있으며 메시지를 받고 읽었다는 신뢰도도 제공합니다. 이러한 기능을 사용하여 새로운 의료 팀을 환자당 만들 수 있습니다. 이러한 기능은 정책 기반으로 개인 또는 전체 Teams에 할당할 수 있습니다.

자세한 내용은 의료 조직에 대한 보안 메시징 정책 시작을 [참조합니다.](messaging-policies-hc.md)

또한 보안 메시지와 관련된 다른 테넌트가 의료 조직에서 페더러드되어 더 풍부한 테넌트 간 통신을 허용하는 기능도 있습니다. (Microsoft Teams에서 외부 액세스 관리(페더 [인)를 참조합니다.](../../manage-external-access.md)

## <a name="teams-templates-for-healthcare-organizations"></a>의료 조직을 위한 Teams 템플릿

Teams를 만들기 위한 새 서식 파일은 병원 설정에 적용하기 위해 개발되고 곧 더 많은 서식 파일도 개발될 예정입니다. 이렇게 하면 의료 근로자가 다양한 부서 또는 구의 환자를 관리하기 위해 사용하는 팀을 쉽게 만들 수 있습니다. 자세한 내용은 의료 조직용 Teams 서식 파일 시작을 [참조합니다.](healthcare-templates.md) Teams는 카디폴로지와 같은 내부 부서 또는 관리 구에 대해 시작할 수 있으며 더 많은 템플릿이 개발 중입니다.

## <a name="care-coordination-and-collaboration"></a>관리 조정 및 공동 작업

의료 팀을 함께 모아 관리하고 Microsoft Teams와 공동 작업합니다.

![의료: Teams에서 의료 팀과 공동 작업](../../media/teams-healthcare-collaborate-in-teams.png)

Microsoft Teams를 사용하면 의사, 의사, 간호사 및 기타 직원이 Microsoft Teams에 포함된 공동 작업 기능을 사용하여 효율적으로 공동 작업할 수 있습니다.

- 의료 팀 및 정보 근로자에 대한 팀 및 채널을 설정할 수 있습니다. 탭과 함께 채널을 사용하여 정보 원본을 고정할 수 있는 탭의 추가 도움말을 통해 작업을 구조화할 수 있습니다.
- 채팅하고, 메시지를 게시하고, 커뮤니케이션합니다. 팀은 주의가 필요한 다양한 환자에 대해 지속적인 대화를 할 수 있습니다.
- 의료 팀의 구성원과 통화하고 만났습니다. 개별 모임을 설정하거나 채널 모임을 사용하여 Teams 오디오, 비디오, 화면 공유, 녹음/녹화 및 전사 기능을 통해 일상적인 모임을 관리할 수 있습니다.
- 파일 및 문서를 저장하고 공유합니다. 상태 팀은 Office 문서에서 작업하고 공동 작업하는 단일 가상화된 팀의 일부입니다.

또한 팀에서 Teams의 앱을 사용하여 다음을 할 수 있습니다.

- 목록 앱을 통해 목록 공유 및 정보 추적
- 작업 앱을 통해 작업 추적 및 모니터링
- 승인 앱을 통해 승인 간소화
- Shifts 앱을 사용하여 일정 만들기, 관리 및 공유

### <a name="share-lists-and-track-information-with-the-lists-app"></a>목록 앱을 통해 목록 공유 및 정보 추적

> [!NOTE]
> 2020년 10월 30일부로 환자 앱은 사용 중지되고 Teams의 [목록](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 앱으로 대체됩니다. 목록을 사용하여 의료 조직의 관리 팀은 라운드 및학 간 팀 모임에서 일반 환자 모니터링에 이르는 시나리오에 대한 환자 목록을 만들 수 있습니다.

Teams의 목록 앱은 팀이 정보를 추적하고 작업을 구성하는 데 도움이 됩니다. 앱은 모든 Teams 사용자에 대해 사전 설치되어 있으며 모든 팀 및 채널에서 탭으로 사용할 수 있습니다. 목록은 미리 정의한 서식 파일에서 또는 Excel로 데이터를 가져와 처음부터 만들 수 있습니다.

의료 팀은 환자 서식 파일을 사용하여 시작할 수 있습니다. 목록을 만들어 환자의 요구와 상태를 추적할 수 있습니다. Excel 스프레드시트의 기존 환자 데이터를 가져와 Teams에서 목록을 만들 수 있습니다. 이러한 목록은 진료를 조정하기 위해 라운드 및 환자 모니터링과 같은 시나리오에 사용할 수 있습니다.

예를 들어 간호사는 모든 의료 팀 구성원을 포함하는 팀에 환자 목록을 만듭니다. 라운드 중에 의료 팀은 모바일 장치에서 Teams에 액세스하고 목록에서 환자 정보를 업데이트합니다. 이 정보는 팀의 모든 사람이 동기화된 상태 유지를 위해 볼 수 있습니다. 의료 팀이 주요 건강 성과 메트릭을 논의하고 평가하기 위해 모인 세션에서 환자가 퇴원할 올바른 경로에 있도록 하는 세션에서는 큰 디스플레이 화면에서 Teams를 사용하여 이 정보를 공유할 수 있습니다. 사이트에 없는 의료 팀 구성원은 원격으로 참가할 수 있습니다.

다음은 환자 반올원을 위해 설정된 예제 목록입니다.

:::image type="content" source="../../media/lists-patients-example.png" alt-text="환자 반올원 예제 목록 스크린샷":::

자세한 내용은 Teams에서 조직의 [목록 앱 관리를 참조하세요.](../../manage-lists-app.md)

### <a name="track-and-monitor-tasks-with-the-tasks-app"></a>작업 앱을 통해 작업 추적 및 모니터링

[Teams에서](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070) 작업을 사용하여 전체 의료 팀에 대한 항목을 추적합니다. 상태 팀은 Teams를 실행하는 모든 장치에서 작업을 만들고, 할당하고, 예약하고, 작업을 분류하고, 상태를 업데이트할 수 있습니다.

자세한 내용은 [Microsoft Teams에서](../../manage-tasks-app.md) 조직의 작업 앱 관리 참조

### <a name="streamline-approvals-with-the-approvals-app"></a>승인 앱을 통해 승인 간소화

승인을 [사용하여](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3) 팀과의 모든 요청 및 프로세스를 간소화합니다. 팀워크를 위해 허브에서 직접 승인을 만들고 관리하고 공유합니다. 채팅을 보내는 동일한 장소, 채널 대화 또는 승인 앱 자체에서 승인 흐름을 시작하세요. 승인 유형을 선택하고, 세부 정보를 추가하고, 파일을 첨부하고, 승인자만 선택하면 됩니다. 제출된 승인자는 알림을 통해 요청에 대한 검토 및 처리를 할 수 있습니다.

조직에 대한 승인 앱을 허용하고 팀에 추가할 수 있습니다. 앱 관리에 대한 자세한 내용은 Microsoft Teams 관리 센터에서 앱 [관리를 참조하세요.](../../manage-apps.md)

### <a name="create-manage-and-share-schedules-with-the-shifts-app-and-frontline-worker-integration"></a>Shifts 앱 및 Frontline Worker 통합을 사용하여 일정 만들기, 관리 및 공유

Microsoft Teams는 Shifts 앱 및 Frontline Worker와 통합됩니다. 이 기능은 교대 근무 직원 기능 조정에 사용할 수 있습니다. 예를 들어 Shifts에서 간호사 관리자는 교직원의 일정을 설정하고 조정하고 간호사는 일정을 확인하고 교대 근무를 교환할 수 있습니다. Teams에는 조직의 일선 작업자에게 할당할 수 있는 기본 제공 Frontline Worker 앱 설정 정책이 포함되어 있습니다. 기본적으로 정책에는 활동, Shifts, 채팅 및 통화 앱이 포함됩니다. 이 정책은 팀이 신속하게 액세스할 수 있도록 Shifts 앱을 앱 바에 고정하는 등 이러한 앱의 동작을 제어합니다.

자세한 내용은 [Microsoft Teams에서 조직의 Shifts 앱 관리를 참조하세요.](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)

## <a name="help-your-clinical-and-information-workers-get-going-with-teams"></a>의료 및 정보 근로자가 Teams를 사용할 수 있도록 지원

조직의 모든 사용자가 Teams를 사용하는 데 도움이 되는 여러 리소스를 사용할 수 있습니다.

- [Teams를](https://adoption.microsoft.com/microsoft-teams/) 통해 조직을 시작하거나 조직의 더 많은 영역으로 Teams를 확장하는 경우 Teams 도입 센터를 방문하여 Teams를 롤아웃하는 데 대한 조언을 구하세요.
- 사용자가 수행하는 [](https://adoption.microsoft.com/microsoft-365-learning-pathways/) 데 필요한 작업만 다루기 위해 사용자 지정 학습 경로를 설정하는 것을 고려합니다.
- 빠른 교육 비디오를 포함하여 [Teams](https://support.microsoft.com/teams)지원 사이트의 Microsoft Teams에서 기본 작업을 수행하는 방법에 대한 사용자에 대한 도움말 및 [교육을 받을 수 있습니다.](https://support.microsoft.com/office/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7) 이 사이트에는 목록, 작업, 승인, [](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)예약, [](https://support.microsoft.com/office/use-the-tasks-app-in-teams-e32639f3-2e07-4b62-9a8c-fd706c12c070)교대 근무를 비롯한 Teams 앱에 대한 도움말 [및](https://support.microsoft.com/office/overview-of-the-bookings-app-in-teams-7b8569e1-0c8a-444e-b712-d9968b05110b) [교육도 있습니다.](https://support.microsoft.com/office/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) [](https://support.microsoft.com/office/what-is-approvals-a9a01c95-e0bf-4d20-9ada-f7be3fc283d3)
