---
title: Microsoft Teams에서의 모임 및 회의
ms.reviewer: ''
description: 다음 배포 리소스를 사용하여 Microsoft Temas에서 모임과 오디오 회의을 배포하는 데 도움을 줄 수 있습니다.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bf5dea8846815f052099193f03f4f90aaf951de6
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583967"
---
# <a name="meetings-and-conferencing-in-microsoft-teams"></a>Microsoft Teams에서의 모임 및 회의

> [!NOTE]
> - 시작하는데 도움이 되는 원격 학습 및 리소스를 전환하는 방법에 대한 개요는 [**원격 학습 홈페이지**](https://www.microsoft.com/education/remote-learning)를 참조하세요.
> - 교사와 학생에게 도움을 주는 원격 학습 리소스를 [**Office 365 Education 원격 교육 및 학습**](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4)에서 사용할 수 있습니다.


[시작](get-started-with-teams-quick-start.md)을 완료했습니다. 조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다. 이제 [오디오 회의](deploy-audio-conferencing-teams-landing-page.md), 비디오 및 공유를 포함한 모임 작업을 추가할 준비가 되었습니다. 이 문서에서는 모임 및 오디오 회의의 배포를 안내합니다. 팀 모임, 회의 및 장치 비디오 (3:28 분)를 보고 시작해 보세요.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE46ZdQ]

사용자들의 모임 경험에 대해 자세히 알아보려면 [모임 및 통화](https://support.office.com/article/meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8)를 참조하세요. 


*2020년 4월의 새로운 기능*: 모음 이끌이는 모임 내 모임 컨트롤에서 **모임 종료**를 클릭하여 Teams에서 모든 모임 참가자를 위해 모임을 종료할 수 있습니다.  

*2019년 11월의 새로운 기능*: 이제 [Advisor for Teams(미리 보기)를 사용하여 Microsoft Teams를 배포하는 데 도움을 받을 수 있습니다](use-advisor-teams-roll-out.md). Advisor for Teams(미리 보기)는 모임 및 회의를 포함하여 Teams의 배포 과정을 안내합니다. Advisor for Teams(미리 보기)는 Office 365 환경을 평가하고 Teams에서 모임 및 회의를 성공적으로 배포하기 전에 업데이트 또는 수정해야 할 수 있는 가장 일반적인 구성을 식별합니다.

## <a name="meetings-and-conferencing-deployment-decisions"></a>모임 및 회의 배포 결정

Teams는 조직을 위해 즉시 사용 가능한 뛰어난 경험을 제공하고 대부분의 조직에 그 기본 설정이 적합합니다. 이 문서에서는 조직의 프로필 및 비즈니스 요구 사항에 따라 기본 설정을 변경할지 여부를 결정 하는데 도움을 주고 각 변경 내용에 대해 설명을 합니다. 당사는 사용자가 [변경할 가능성이 큰](#core-deployment-decisions) 변경 내용의 핵심 집합에서 시작하여 설정을 두 그룹으로 나누었습니다. 두 번째 그룹은 조직의 요구 사항에 따라 구성하고자 하는 [추가 설정](#additional-deployment-decisions)을 포함합니다.

> [!Tip]
> 모임에 대한 자세한 내용은 다음 세션을 참고 하세요. [IT 전문가를 위한 Microsoft Teams의 모임 소개](https://aka.ms/teams-meetings-intro)


## <a name="meetings-and-conferencing-prerequisites"></a>모임 및 회의 필수 구성 요소 

조직 전체에서 모임 배포를 확장하기 전에 시간을 내어 사용자에게 최상의 경험을 제공할 준비가 되었는지 검토하고 확인합니다. 다음의 정보를 검토하고 필요에 따라 환경을 변경합니다.

Teams에서 최상의 경험을 얻으려면 조직이 *Exchange Online 및 SharePoint Online*을 보유하고 사용자는 검증된 O365용 도메인을 보유해야 합니다(예: contoso.com).

조직 전체에서 모임을 확장하려면 모든 사용자가 인터넷에 연결하여 Office 365 서비스에 연결할 수 있도록 해야합니다. 최소한 사용자의 위치에서 다음과 같은 일반 포트가 인터넷에 열려 있는지도 확인해야 합니다.

- Teams를 사용하는 클라이언트가 발신하는 TCP 포트 80 및 443
- Teams를 사용하는 클라이언트가 발신하는 UDP 포트 3478~3481

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|네트워크가 Teams 모임을 배포할 준비가 되었나요? | 네트워크가 준비되었는지 확인하려면 다음을 참조하세요.<ul><li>[Microsoft Teams에 대한 조직의 네트워크 준비](https://docs.microsoft.com/MicrosoftTeams/prepare-network)</li><li>[URL 및 IP 주소 범위](https://docs.microsoft.com/MicrosoftTeams/office-365-urls-ip-address-ranges)</li></ul> |
|||

## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

대부분의 조직이 변경하려는 설정입니다 (Teams의 기본 설정이 조직에 적합하지 않은 경우).

### <a name="teams-administrators"></a>Teams 관리자

Teams는 조직의 팀을 관리하는데 사용할 수 있는 사용자 지정 관리자 역할의 집합을 제공합니다. 역할은 관리자에게 다양한 기능을 제공합니다. 

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|Teams 커뮤니케이션 관리자 역할은 누구에게 할당될 것인가요?|Teams 관리자 역할에 대한 자세한 내용은 [팀을 관리하기 위한 Microsoft Teams 관리 역할의 활용](using-admin-roles.md)을 참조하세요.|
|Teams 커뮤니케이션 지원 기술자 역할은 누구에게 할당될 것인가요?|관리 역할을 할당하려면 [Azure Active Directory를 사용하여 사용자에게 관리자 및 비관리자 역할 할당](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)을 참조하세요.|
|Teams 커뮤니케이션 지원 전문가자 역할은 누구에게 할당할 것인가요?||
|||

### <a name="meetings-settings"></a>모임 설정 

모임 설정은 익명 사용자가 Teams 모임에 참여하고 모임 초대를 설정하고 QoS (서비스 품질)를 설정하려는 경우 실시간 트래픽에 대한 포트를 설정하는 데 사용됩니다. 이러한 설정은 사용자가 조직에서 예약하는 모든 Teams 모임에 대해 사용됩니다. 

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|초기 모임 설정을 사용자 지정하나요? |모임 설정에 대해 자세히 알아보려면 [Teams 내 모임 자습서](tutorial-meetings-in-teams.yml)를 참조하세요.|
|QoS를 구현할 수 있나요?|QoS 개념에 대한 자세한 내용은 [Microsoft Teams의 서비스 품질](qos-in-teams.md)을 참조하세요. 시나리오 및 구현.|
|||

### <a name="meeting-policies"></a>모임 정책

모임 정책은 사용자가 Teams 모임에 참가할 때 사용 가능한 기능을 제어하는 데 사용됩니다. 조직에서 모임을 호스팅하는 사용자에게 기본 정책을 사용하거나 하나 이상의 사용자 지정 모임 정책을 만들 수 있습니다. 자세한 내용은 [Microsoft Teams의 모임 자습서](tutorial-meetings-in-teams.yml)를 참조하세요.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|<ul><li>초기 모임 정책을 사용자 지정하나요?</li><li>여러개의 모임 정책이 필요한가요?</li><li>어떠한 사용자 그룹에 어떠한 모임 정책이 적용될지를 어떻게 결정하나요?</li></ul>|<br>[Teams에서의 모임 정책 관리](meeting-policies-in-teams.md)를 읽어보세요.|
|||

### <a name="audio-conferencing"></a>오디오 회의

오디오 회의는 기존의 유선 전화, PBX(Private Branch Exchange) 또는 휴대폰을 사용하여 전화 회의 참가자가 PSTN(Public Switched Telephone Network)을 통해 회의에 참가할 수 있게 허용하여 모든 회의(임시 또는 예약)에 추가 진입점을 제공합니다. 

오디오 회의를 배포할 준비가 되면 자세한 [오디오 회의 배포](deploy-audio-conferencing-teams-landing-page.md) 지침을 참조하세요.

### <a name="meeting-room-and-personal-devices"></a>회의실 및 개인 장치 정책

Teams에서 최적의 모임 경험을 위해 회의실 시스템, 전화, 헤드셋 및 카메라와 같은 Teams 장치 사용을 고려해야 합니다. 자세한 내용은 [지능적인 커뮤니케이션을 위한 Teams 장치](https://products.office.com/microsoft-teams/across-devices)를 참조하세요.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|사용자를 위한 개인 장치를 구입하나요? |[Teams에서 디바이스 관리](devices/device-management.md)를 읽어보세요. |
|회의실용 회의실 시스템 장치를 구입하여 배포하나요?|[회의실 장치 및 솔루션](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)을 읽어보세요.|
|||

### <a name="reporting"></a>보고

활동 보고서를 사용하여 조직의 사용자가 Teams를 어떻게 사용하고 있는지 확인하세요. 예를 들어, 아직 Teams를 사용하고 있지 않은 경우 Teams를 사용하여 생산성과 공동 작업을 향상 시키는 방법을 모를 수도 있습니다. 조직에서 활동 보고서를 사용하여 교육 및 커뮤니케이션 노력에 대한 우선 순위를 결정할 수 있습니다. 


| 본인에게 질의하기 | 작업 |
|--------------|--------|
|누가 보고해야 하나요?|[Teams에 대한 활동 보고서 사용](teams-activity-reports.md)을 읽어보세요.  |
|누가 사용 현황을 모니터링하나요?|[Teams에서 사용 현황 및 사용자 의견 모니터링](get-started-with-teams-monitor-usage-and-feedback.md)을 읽어보세요.|
|||

## <a name="additional-deployment-decisions"></a>추가 배포 결정사항

조직의 요구 사항 및 구성에 따라 이러한 설정을 변경하는 것이 좋습니다.

### <a name="bandwidth-planning"></a>대역폭 계획 

대역폭 계획을 통해 조직은 광역 네트워크와 인터넷 링크에서 모임을 지원하는 데 필요한 대역폭을 예측하여 네트워크를 올바르게 프로비전하여 확장된 모임 서비스를 지원할 수 있는지 확인할 수 있습니다. 

| 본인에게 질의하기 | 작업 |
|--------------|--------|
| 모임 배포 이전 및 도중에 대역폭 계획을 수행해야하나요? |계획 프로세스를 단순화 하는 방법에 대한 자세한 내용과 도구에 대한 링크는 [네트워크 준비](3-envision-evaluate-my-environment.md#network-readiness)를 참조하세요.|
|||

### <a name="meeting-recording-and-archiving"></a>모임 녹음/녹화 및 보관

사용자는 자신의 모임 및 그룹 통화를 녹음/녹화하여 오디오, 비디오, 화면 공유 활동을 캡처할 수 있습니다. 사용자가 선택 캡션을 사용하여 모임을 녹음/녹화한 것을 재생하고 대화 내용에서 중요한 토론 항목을 검색할 수 있도록 녹음/녹화를 위한 자동 기록 옵션도 있습니다. 녹음/녹화는 클라우드에서 이루어지고 Microsoft Stream에 저장되므로 사용자는 조직 전체에서 안전하게 공유할 수 있습니다. 모임 녹음/녹화를 찾으려면 모임 대화로 이동합니다.

자세한 내용은 [Teams 클라우드 모임 녹음/녹화](cloud-recording.md)를 참조하세요.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
| 모임 기록 서비스를 켜나요?|[녹음/녹화 기록 설정 또는 해제](cloud-recording.md#turn-on-or-turn-off-recording-transcription)를 참조하세요.|
|||


### <a name="live-events-policies"></a>라이브 이벤트 정책

Teams 라이브 이벤트 정책은 사용자 그룹의 이벤트 설정을 관리하는 데 사용됩니다. 기본 정책을 사용하거나 조직 내에서 라이브 이벤트를 보유한 사용자에게 할당할 수있는 추가 정책을 만들 수 있습니다. 

| 본인에게 질의하기 | 작업 |
|--------------|--------|
| 조직에서 Teams의 라이브 이벤트를 사용하나요?| 팀의 라이브 이벤트 계획, 설정 및 구성에 대한 자세한 내용은 [라이브 이벤트 문서](teams-live-events/what-are-teams-live-events.md)를 참조하세요.|
|||

### <a name="conference-room-systems-rollout"></a>회의실 시스템 출시

다수의 회의실을 보유한 조직은 회의실 목록을 작성하고 적절한 장치를 식별한 다음 이를 배포하는 체계적인 접근 방식을 고려해 볼 수 있습니다. 



| 본인에게 질의하기 | 작업 |
|--------------|--------|
| 회의실 시스템을 배포하려면 무엇을 해야하나요?|[Microsoft Teams 룸 계획](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/skype-room-systems-v2-0?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)문서를 확인하세요.|
|||

### <a name="cloud-video-interop"></a>클라우드 비디오 interop

클라우드 비디오 interop을 사용하면 타사 회의실 장치에서 Teams 모임에 참가할 수 있습니다. 

컨텐츠 협업을 통한 화상 회의는 모임을 최대한 활용하는 데 도움이 됩니다. 그러나 회의실 시스템과 장치는 업그레이드 하는 데 비용이 많이 듭니다. Teams용 클라우드 비디오 interop은 타사 시스템과 함께 작동하며 회의실 또는 Teams 클라이언트 내에서 모든 참가자에게 네이티브 모임 경험을 제공합니다. 

| 본인에게 질의하기 | 작업 |
|--------------|--------|
| 회의실 시스템 배포의 일부로 클라우드 비디오 interop 솔루션을 사용하나요? | [Teams용 클라우드 비디오 interop](cloud-video-interop.md)을 읽어보세요.|
|||


### <a name="personal-device-rollout"></a>개인 장치 배포

모임이나 음성 배포를 지원하기 위해 개인 장치의 대규모 배포를 계획 중인 경우, 반복 가능한 품질을 제공하는 반복 가능한 사이트별 출시 프로세스 사용을 고려해 볼 수 있습니다.

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|사이트별 접근 방식을 사용하여 모임을 배포하나요? |  [Teams용 사이트 인에이블먼트 플레이북](3-onboard-deploy-my-service.md#site-enablement-playbook-for-microsoft-teams-voice-workloads)은 자체 배포에 사용할 수 있는 훌륭한 기반을 제공합니다. 이 가이드는 음성에 중점을 두지만 장치 전달, 계정 준비, 도입 및 교육에 대한 일반적인 원칙은 대규모 모임 배포에 적용됩니다. |
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>모임 및 통화 품질 문제 해결 

Teams는 통화 품질 문제를 모니터링하고 문제를 해결하기 위한 두 가지 방법인 [통화 분석 및 통화 품질 대시보드](monitor-call-quality-qos.md)를 제공합니다. Call Analytics에는 각 사용자의 특정 통화 및 모임과 관련된 디바이스, 네트워크 및 연결에 대한 자세한 정보가 표시됩니다. Call Analytics는 관리자와 지원 센터 상담원이 특정 통화의 통화 품질 문제를 해결하는데 도움을 주기 위해 설계되었고 통화 품질 대시보드는 관리자와 네트워크 엔지니어가 네트워크를 최적화하는데 도움을 주기 위해 설계되었습니다. 통화 품질 대시보드는 특정 사용자로부터 포커스를 이동하고 대신 전체 Teams 조직에 대한 집계 정보를 조사합니다. 

|본인에게 질의하기|작업 |
|------------|-------|
| 통화 품질 문제를 모니터링하고 문제를 해결할 책임이 있는 사용자는 누구인가요? | 통화 품질 문제를 해결하는 데 필요한 사용 권한 수준에 대한 내용은 [Call Analytics를 사용하여 통화 품질 저하 문제를 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)을 읽어보세요.|
|||

### <a name="operate-your-meetings-service"></a>모임 서비스 운영

조직에 있는 다른 사용자에게 서비스에 영향을 주는 이벤트를 사전에 알릴 수 있도록 Teams 서비스의 전반적인 상태를 파악하는 것이 중요합니다. [내 서비스 운영](1-drive-value-operate-my-service.md) 문서를 통해 서비스 작업에 대한 상세한 안내를 받을 수 있습니다.

|본인에게 질의하기|작업 |
|------------|-------|
|조직에서 모임 서비스를 관리해야 하는 사람은 누구인가요? | 이 사람이 모임 서비스를 관리하는 데 필요한 팀 관리자 권한을 보유하고 있는지 확인합니다. Teams 관리자 역할에 대한 자세한 내용은 [팀을 관리하기 위한 Microsoft Teams 관리 역할의 활용](using-admin-roles.md)을 참조하세요.|
|||


## <a name="next-steps"></a>다음 단계
- 조직 전체의 모임 및 회의 [도입을 주도](adopt-microsoft-teams-landing-page.md).
- [오디오 회의 추가](deploy-audio-conferencing-teams-landing-page.md)
- [클라우드 음성 출시](cloud-voice-landing-page.md)
- 최초 Teams를 배포 시 플래너와 같은 추천 앱을 포함합니다. Teams의 채택을 주도하면서 다른 [앱, 봇 & 커넥터](deploy-apps-microsoft-teams-landing-page.md)를 추가합니다.
