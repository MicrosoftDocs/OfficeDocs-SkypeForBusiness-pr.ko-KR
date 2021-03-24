---
title: 모임 첫 번째 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: 채팅, 통화 및 현재 상태의 비즈니스용 Skype를 계속 사용하는 동안 사용자가 Teams에서 모임을 만들 수 있는 모임 우선에 대해 자세히 알아보습니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b691a9d722a82e68384f8937479c5f71d3f4c11d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096172"
---
# <a name="meetings-first"></a>무엇보다도 모임을 우선으로

"모임 우선"은 Teams 모임을 가능한 Enterprise Voice 비즈니스용 Skype 서버 조직을 대상으로 하고 최적화됩니다. 이러한 조직의 경우 모임 우선 순위가  Teams 모임 환경의 우선 순위를 지정하는 제도 모드를 사용하는 대안입니다.

## <a name="what-is-meetings-first"></a>모임 우선이란?

모임 첫 번째는 **SfBWithTeamsCollabAndMeetings** 공존 모드를 기반으로 합니다. 모임 우선은 제품 또는 기능이 아니며, Teams 및 Skype for Business의 기능 및 기능을 사용하여 고유하게 맞춤된 공존 환경을 제공하는 구성입니다.

모임 첫 번째에서는 사용자가 채팅, 통화 및 현재 상태의 비즈니스용 Skype를 계속 사용하는 동안 Teams에서 모임을 만들 수 있습니다. Teams와 비즈니스용 Skype 간에는 모달이 겹치지 않습니다. 채팅, 통화 및 현재 상태는 비즈니스용 Skype 및 Teams에서 해제됩니다. 이를 통해 비즈니스용 Skype와 Teams 간에 고유한 "더 나은 함께" 시나리오를 사용할 수 있으며, 이 시나리오는 Teams **Only** 사용자와의 상호 연동성 시나리오뿐만 아니라 공존하는 동안 사용자의 환경을 개선합니다.

![Teams 및 비즈니스용 Skype와 함께 더 나은 시나리오 스크린샷](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> 모임 먼저 활성 Teams 채팅 사용자가 없는 조직과 더 잘 일치합니다. Active Teams 채팅 사용자는 Teams에서 채팅하고 채팅 기록에 액세스할 수 있는 기능을 잃게 하여 모임 첫 번째 모드로 전환하면 안 됩니다. 이러한 사용자는 할아버지  대신 섬 모드에서 할아버지가 됐고, 모임 우선은 Teams에서 채팅에 아직 활성화되지 않은 사용자에게만 부여됩니다.

## <a name="who-should-consider-meetings-first"></a>모임을 먼저 고려해야 하는 사람이 누구인가요?

모임 우선은 비즈니스용 Skype 서버를 사용하는 조직과 팀 모임으로의 Enterprise Voice 이동을 가속화하려는 조직, 특히 Teams에 대한 관리되고, 의제적인 업그레이드 경로를 원하는 강력한 IT 분야를 사용하는 조직을 위해 고안된 것입니다.

복잡한 조직 또는 대규모 조직의 경우 음성 마이그레이션은 일반적으로 사이트 기준으로 수행됩니다. 시간이 오래 걸릴 수 있으며 잠재적으로 몇 년이 걸릴 수 있습니다. 따라서 확장된 공존 시나리오가 발생할 수 있습니다. 이러한 공존이 **제도** 모드인 경우 사용자는 항상 두 가지 모임 솔루션(비즈니스용 Skype 및 Teams)을 선택할 수 있으며, 이는 혼동되거나 부재 중일 수 있습니다. 음성 마이그레이션과 달리 모임 마이그레이션은 일반적으로 회사 전체에서 단시간에 완료될 수 있습니다. 최대한 빨리 Teams 모임으로 전환하려는 조직(음성 마이그레이션이 완료될 때까지 기다리지 않고) 먼저 모임을 고려해야 합니다.

모임 우선 사용자가 없는 조직에는 유용하지 않을 Enterprise Voice 있습니다. 이러한 조직은 Teams 모임을 채택하는 즉시 **Teams로** 업그레이드할 수 있습니다. 먼저 모임을 건너뛰는 것이 고려됩니다.

또한 모임 우선 범위가 순수 재생 모임 솔루션인 조직에 유용합니다(예: "모임 전용" RFP가 발급되는 경우).

## <a name="capabilities-in-meetings-first"></a>모임의 기능 우선

모임 먼저 다음 기능을 함께 제공합니다.

- Teams 오디오 회의를 통해 [비즈니스용 Skype 서버(-프레미스)](./tutorial-audio-conferencing.yml?tutorial-step=3) 사용자를 [프로비전합니다.](tutorial-audio-conferencing.yml)
- [모임 마이그레이션 서비스:](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)사용자가 조직한 모임은 사용자가 모임 우선으로 승격될 때 클라우드로 마이그레이션되어 Teams 모임으로 변환됩니다(Exchange Online 필요).
- Teams 모임 및 팀 및 채널을 중심으로 하는 Teams의 간소화된 사용자 환경(선택적으로 앱 사용 권한 정책을 사용하여 숨길 [수](teams-app-permission-policies.md)있습니다).; [팀 개인 채팅, 통화](teams-client-experience-and-conformance-to-coexistence-modes.md) 및 자체 상태는 모임 우선에 노출되지 않습니다. 배포 및 채택 노력이 모임에 완전히 집중할 수 있습니다.
- Superior [Teams 모임 환경](tutorial-meetings-in-teams.yml)입니다.
- Teams와 비즈니스용 Skype 간의 "더 나은 함께": 
  - 자동 보류: Teams에서 모임에 참석할 때 비즈니스용 Skype에서 전화를 걸면 Teams 모임이 보류 중이고 그 반대의 경우도 마찬가지입니다. 이렇게 하면 사용자가 모임 참가자가 개인 통화를 과열할 수 없습니다.
    ![Teams 및 비즈니스용 Skype와 함께 더 나은 시나리오 스크린샷](media/meetings-first-better-together-hold.png)
  - 현재 상태 화해: Teams의 활동은 채팅 및 통화가 비즈니스용 Skype에 존재하기 때문에 비즈니스용 Skype 상태인 사용자의 현재 상태에 반영됩니다. 특히 모임 첫 번째 사용자가 Teams 모임에 있는 경우 해당 사용자의 현재 상태는 이를 반영하기 위해 업데이트됩니다. 화면을 표시하면 방해 금지(비즈니스용 Skype의 설정에 따라)를 표시하기 위해 현재 상태가 업데이트됩니다.
  - USB 디바이스 HID 제어 화해(Mac에서도 사용 가능): 다른 모든 상황에서 Teams 모임 및 비즈니스용 Skype에서 HID 컨트롤을 사용할 수 있습니다.
  - 달리 언급하지 않는 한 Better Together 기능에는 현재 최신 Windows 데스크톱 클라이언트가 필요하게 됩니다.

## <a name="prerequisites-for-meetings-first"></a>모임 우선의 전제

모임 우선에 대한 유일한 어려운 요구 사항은 프레미스 Active Directory 및 비즈니스용 Skype를 배포하는 Teams에 대한 요구 사항과 동일합니다.

- [Teams에](upgrade-plan-journey-prerequisites.md)대한 일반 전제요구
- [Teams의 ID 및](identify-models-authentication.md) 인증 및
- [Teams 및 비즈니스용 Skype용 Azure Active Directory를 구성합니다.](/skypeforbusiness/hybrid/configure-azure-ad-connect)

[비즈니스용 Skype 하이브리드](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) 토폴로지가 필요하지는 않지만 권장됩니다. 모임 마이그레이션 서비스 및 상호 실행성과 같은 일부 기능은 토폴로지에 따라 사용됩니다.

모임 우선은 비즈니스용 Skype 서버의 모든 버전에서 지원됩니다(더 이상 지원되지 않는 Lync Server와 함께 작업하는 것으로 알려져 있습니다). 지원되는 비즈니스용 Skype 클라이언트에서 지원됩니다. 그러나 Better Together 기능에는 최신 클라이언트가 필요하게 됩니다.

이러한 요구 사항이 충족된 후(이전이 아닌) [사용자는 Microsoft 365 또는 Office 365 및 Teams에 대해 라이선스를 부여할 수 있습니다.](/office365/enterprise/assign-licenses-to-user-accounts)

최상의 모임 첫 경험의 경우 Exchange [Online,](exchange-teams-interact.md) [SharePoint Online 및 비즈니스용 OneDrive](sharepoint-onedrive-interact.md)및 Microsoft 365 그룹 만들기에 대해 사용자를 사용하도록 설정해야 합니다. 모임 우선은 사서함이 Exchange온-프레미스에 있는 사용자 또는 SharePoint Online 또는 비즈니스용 OneDrive 또는 Microsoft 365 그룹 생성이 없는 사용자에 대해 지원됩니다. 그러나 이러한 환경은 덜 완료되지 않습니다. 특히, Exchange Server 프레미스를 사용하는 조직의 경우 규정 준수 기능뿐만 아니라 teams 클라이언트에서 모임을 만들고 Exchange Server 보기에 대한 몇 가지 제한 사항이 있을 수 있습니다.

최소한 Teams에 대한 [라이선스가 있어야 합니다.](/microsoft-365/admin/manage/assign-licenses-to-users) 또한 필요한 경우 [오디오](set-up-audio-conferencing-in-teams.md)회의에 대해 라이선스를 부여할 수 있습니다.

사용자에게 라이선스를 부여할 때 [ **SfBOnly** 또는 **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 모드를 테넌트 기본값으로 부여하는 것이 좋습니다. 이렇게 하면 사용자가 모임을 먼저 시작할 준비가  되도록 준비하기 전에 기본 제도 모드에서 자체적으로 Teams 사용을 시작하지 않도록 합니다.

모임 우선 전체 데스크톱 클라이언트(Windows 및 Mac), 브라우저 클라이언트 및 모바일 클라이언트에서 지원됩니다. Microsoft [Teams Rooms와도 호환됩니다.](/microsoftteams/room-systems/) Better Together에는 전체 데스크톱 클라이언트가 필요합니다.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>모임에서 Teams 모임 준비 먼저

사용자가 Teams 모임에서 최상의 환경을 경험할 수 있도록 다음을 해야 합니다.

- 특히 Microsoft [Teams에](deploy-meetings-microsoft-teams-landing-page.md)대한 모임 및 회의의 단계를 따릅니다.
- [환경을 평가합니다.](3-envision-evaluate-my-environment.md)
- [Microsoft Teams에 대한 조직의 네트워크를 준비합니다.](prepare-network.md)
- Teams 지원 회의실 디바이스 [](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)및 솔루션으로 회의실을 업그레이드하거나 [Microsoft Teams용 Cloud Video Interop을](cloud-video-interop.md) 사용하여 기존 타사 회의실 및 디바이스가 Teams 모임에 참가할 수 있도록 합니다.
- 사용자에게 인증된 USB 오디오 및 비디오 [디바이스를 장비합니다.](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)
- Teams 모임에 대한 인식을 높이고 [채택할 준비를 합니다.](adopt-microsoft-teams-landing-page.md)
- [서비스 관리를 계획합니다.](4-envision-plan-my-service-management.md)
- 부실한 통화 품질 문제를 해결하기 위해 다양한 Call Analytics [보고서에 익숙해지세요.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

이 단계에서 적당한 규모 프로덕션 준비 파일럿을 실행하는 것이 고려될 수 있습니다.

## <a name="configure-users-for-meetings-first"></a>모임에 대한 사용자 구성 먼저

사용자에게 라이선스를 부여하고 Teams 모임을 위해 조직을 준비한 후 먼저 사용자를 모임에 사용하도록 설정해야 합니다. 한 가지 설정으로 모든 작업을 쉽게 할 수 있습니다.

Teams 클라이언트 구성 및 사용자 환경의 자동 준수, [](teams-client-experience-and-conformance-to-coexistence-modes.md) 모임 마이그레이션 서비스 및 더 나은 함께 기능 등 모임의 모든 기능과 사용자 환경은 Microsoft Teams 관리 센터 또는 [PowerShell을](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)사용하여 [SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) 공존 모드(또는 사용자 그룹 또는 테넌트 기본값)를 부여하여 구성됩니다. [](manage-teams-in-modern-portal.md)

![먼저 모임을 사용하도록 설정하는 관리자 설정 스크린샷](media/teams-meeting-admin-settings.png)

선택적으로 사용자 Teams 클라이언트의 왼쪽 탐색에서 Teams 및 채널 애플리케이션을 숨기고 앱 사용 권한 정책을 사용하여 모임에 자신의 환경을 더 집중할 [수 있습니다.](teams-app-permission-policies.md)

## <a name="reporting-and-call-analytics"></a>보고 및 통화 분석

먼저 모임에서 Teams 모임에 대한 보고 및 통화 분석은 다른 모드의 모임과는 다를 수 있습니다.

## <a name="related-links"></a>관련 링크

이 문서를 검토한 후 자세한 내용은 업그레이드 여정 [](migration-interop-guidance-for-teams-with-skype.md) [선택,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)마이그레이션 및 상호 운영성 지침 및 [비즈니스용 Skype와의](coexistence-chat-calls-presence.md) 공존을 참조하세요.