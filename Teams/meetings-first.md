---
title: 모임 우선 - Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: 채팅, 통화, 현재 상태 등 비즈니스용 Skype를 계속 사용하면서 사용자가 Teams에서 모임을 만들 수 있는 모임 우선에 대해 자세히 배워야 합니다.
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
ms.openlocfilehash: c4e4eba45e7f6719b1fb3427ebd169b69a1e86c9
ms.sourcegitcommit: 4e648c3dd71d9c38cbcb81fab9e8cb9d241fe79c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871079"
---
# <a name="meetings-first"></a>무엇보다도 모임을 우선으로

"모임 우선"은 Teams 모임을 최대한 신속하게 사용하려는 Enterprise Voice 비즈니스용 Skype Server 조직을 대상으로 하고 최적화됩니다. 이러한 조직의 경우 모임 우선 순위를  지정하는 제도 모드를 사용하는 대신 모임 우선 순위를 지정합니다.

## <a name="what-is-meetings-first"></a>모임 우선이란?

Meetings First는 **SfBWithTeamsCollabAndMeetings** 공존 모드를 기반으로 합니다. 모임 우선은 제품이나 기능이 아니며, Teams 및 비즈니스용 Skype의 기능 및 기능을 사용하여 고유한 맞춤형 공존 환경을 제공하는 구성입니다.

모임 우선에서 사용자는 Teams에서 모임을 만들고 채팅, 통화, 현재 상태 등 비즈니스용 Skype를 계속 사용할 수 있습니다. Teams와 비즈니스용 Skype 간에는 겹치는 겹치지 않습니다. 채팅, 통화, 현재 상태는 비즈니스용 Skype 및 Teams에서 해제됩니다. 이를 통해 비즈니스용 Skype와 Teams 간에 고유한 "더 나은" 시나리오를 사용할 수 있으며, 이 시나리오는 Teams만 사용자와의 상호 연동성 시나리오뿐만 아니라 공존하는 동안 사용자의 경험을 **향상할 수** 있습니다.

![Teams 및 비즈니스용 Skype와 함께 더 나은 시나리오 스크린샷](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> 모임 우선은 활성 Teams 채팅 사용자가 거의 없는 조직에 더 잘 맞습니다. Active Teams 채팅 사용자는 Teams에서 채팅하고 채팅 기록에 액세스할 수 있는 기능을 상실하기에 모임 첫 번째 모드로 전환하면 안 됩니다. 이러한 사용자는 제도 모드에서 할아버지가 됐고, 모임 우선에는 Teams에서 아직 채팅에 참여하지 않은 사용자에게만 부여됩니다. 

## <a name="who-should-consider-meetings-first"></a>모임을 먼저 고려해야 하는 사람

Meetings First는 Teams 모임으로의 이동을 가속화하려는 Enterprise Voice 비즈니스용 Skype Server를 사용하는 조직, 특히 Teams에 대한 관리되고 적인 업그레이드 경로를 원하는 강력한 IT 분야를 사용하는 조직을 위해 고안된 것입니다.

복잡하거나 대규모 조직의 경우 음성 마이그레이션은 일반적으로 사이트 기준으로 수행하며, 잠재적으로 몇 년이 걸릴 수 있으며, 이로 인해 확장된 공존 시나리오가 발생할 수 있습니다. 이 공존이 제도  모드인 경우 사용자는 항상 두 가지 모임 솔루션(비즈니스용 Skype 및 Teams)을 선택할 수 있으며, 이로 인해 혼동되거나 상황에 따라 다를 수 있습니다. 음성 마이그레이션과 달리 모임 마이그레이션은 일반적으로 회사 전체에서 짧은 시간으로 완료할 수 있습니다. 음성 마이그레이션이 완료될 때까지 기다리지 않고 Teams 모임을 최대한 빨리 Teams 모임으로 전환하려는 조직은 모임 우선을 고려해야 합니다.

모임 우선은 사용자가 없는 조직에는 유용하지 않을 Enterprise Voice 있습니다. 이러한 조직은 Teams 모임을 채택하는 즉시 **Teams로** 업그레이드할 수 있습니다. 먼저 모임을 건너뛰는 것이 고려해야 합니다.

또한 모임 우선은 범위가 순수하게 재생되는 모임 솔루션인 조직(예: "모임 전용" RFP가 발급되는 경우)에 유용합니다.

## <a name="capabilities-in-meetings-first"></a>모임의 기능 우선

Meeting First는 다음과 같은 기능을 함께 제공합니다.

- Teams 오디오 회의를 통해 [비즈니스용 Skype 서버(-프레미스)](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) 사용자를 [프로비전합니다.](tutorial-audio-conferencing.yml)
- [모임 마이그레이션 서비스:](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)사용자가 구성한 모임은 클라우드로 마이그레이션되어 사용자가 모임 우선으로 승격될 때 Teams 모임으로 변환됩니다(Exchange Online 필요).
- Teams 모임 및 팀 및 채널을 중심으로 하는 Teams의 간소화된 사용자 환경(선택적으로 앱 사용 권한 정책을 사용하여 숨길 [수](teams-app-permission-policies.md)있습니다.) [Teams 비공개 채팅, 통화](teams-client-experience-and-conformance-to-coexistence-modes.md) 및 셀프 에세이션은 모임 우선에 노출되지 않습니다. 이를 통해 배포 및 채택 노력이 모임에 완전히 집중할 수 있습니다.
- 우수한 [Teams 모임 환경.](tutorial-meetings-in-teams.yml)
- Teams와 비즈니스용 Skype 간의 "더 나은 함께" 
  - 자동 보류: Teams에서 모임에 참가할 때 비즈니스용 Skype에서 전화를 걸면 Teams 모임이 보류 중이고 그 반대의 경우도 마찬가지입니다. 이렇게 하면 모임 참가자가 비공개 통화를 과도하게 할 수 없습니다.
    ![Teams 및 비즈니스용 Skype와 함께 더 나은 시나리오 스크린샷](media/meetings-first-better-together-hold.png)
  - 현재 상태 화해: Teams의 활동은 사용자의 현재 상태(채팅 및 통화가 비즈니스용 Skype에 존재하기 때문에 비즈니스용 Skype 현재 상태)에 반영됩니다. 특히 모임 첫 번째 사용자가 Teams 모임에 있는 경우 해당 사용자의 현재 상태는 이를 반영하기 위해 업데이트됩니다. 사용자가 화면을 표시하면 자신의 현재 상태는 방해 금지(비즈니스용 Skype의 설정에 따라)를 표시하기 위해 업데이트됩니다.
  - USB 장치 HID 제어 화해(Mac에서도 사용 가능): Teams 모임 중 Teams와 비즈니스용 Skype에서 다른 모든 상황에서 HID 컨트롤을 사용할 수 있습니다.
  - 달리 언급하지 않는 한 Better Together 기능에는 현재 최신 Windows 데스크톱 클라이언트가 요구됩니다.

## <a name="prerequisites-for-meetings-first"></a>먼저 모임을 위한 전제적 준비

모임 우선에 대한 유일한 어려운 요구 사항은 온라인 프레미스 Active Directory 및 비즈니스용 Skype-프레미스 배포가 있는 Teams의 요구 사항과 같습니다.

- [Teams에](upgrade-plan-journey-prerequisites.md)대한 일반적인 전제적 전제
- [Teams의](identify-models-authentication.md) ID 및 인증 및
- [Teams 및 비즈니스용 Skype용 Azure Active Directory를 구성합니다.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)

비즈니스용 [Skype 하이브리드 토폴로지가](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) 필요하지 않지만 권장됩니다. 모임 마이그레이션 서비스 및 상호 연동성과 같은 일부 기능은 토폴로지에 따라 다를 수 있습니다.

모임 우선은 비즈니스용 Skype 서버의 모든 버전에서 지원됩니다(더 이상 지원되지 않는 Lync Server에서 작업하는 것으로 알려져 있습니다). 지원되는 비즈니스용 Skype 클라이언트에서 지원됩니다. 하지만 Better Together 기능을 사용하려면 최신 클라이언트가 필요 합니다.

이러한 요구 사항을 충족하면(이전이 아닌) [사용자에게 Microsoft 365 또는 Office 365](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts)및 Teams에 대한 라이선스를 부여할 수 있습니다.

최상의 모임 첫 번째 환경을 위해 사용자는 [Exchange Online,](exchange-teams-interact.md)SharePoint Online 및 비즈니스용 [OneDrive](sharepoint-onedrive-interact.md)및 Microsoft 365 그룹 만들기를 사용하도록 설정해야 합니다. 모임 우선은 사서함이 Exchange On-프레미스에 있는 사용자 또는 SharePoint Online 또는 비즈니스용 OneDrive 또는 Microsoft 365 그룹 생성이 없는 사용자에 대해 지원됩니다. 그러나 이러한 환경은 완전하지 않습니다. 특히 Exchange Server 프레미스를 사용하는 조직의 경우(Exchange Server 버전에 따라) Teams 클라이언트에서 모임을 만들고 볼 수 있을 뿐만 아니라 규정 준수 기능과 관련한 몇 가지 제한 사항이 있을 수 있습니다.

최소한 사용자가 [Teams에 대한 라이선스를 부여해야 합니다.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) 또한 필요한 경우 오디오 회의에 대한 라이선스를 부여할 수 있습니다. [](set-up-audio-conferencing-in-teams.md)

사용자에게 라이선스를 부여할 때 [ **SfBOnly** 또는 **SfBWithTeamsCollab**](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 모드를 테넌트 기본값으로 부여하는 것이 좋습니다. 이렇게 하면 모임을 먼저 시작할 준비가 됐기 전에 사용자가 기본 제도 모드에서 Teams를 직접 사용하지 않도록 할 수 있습니다. 

모임 우선은 전체 데스크톱 클라이언트(Windows 및 Mac), 브라우저 클라이언트 및 모바일 클라이언트에서 지원됩니다. Microsoft [Teams 회의실과도 호환됩니다.](https://docs.microsoft.com/microsoftteams/room-systems/) Better Together에는 전체 데스크톱 클라이언트가 필요합니다.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>먼저 모임에서 Teams 모임 준비

사용자가 Teams 모임에서 최상의 경험을 할 수 있도록 다음을 해야 합니다.

- 특히 Microsoft [Teams에](deploy-meetings-microsoft-teams-landing-page.md)대한 모임 및 회의의 단계를 따릅니다.
- [환경을 평가합니다.](3-envision-evaluate-my-environment.md)
- [Microsoft Teams에 대한 조직의 네트워크를 준비합니다.](prepare-network.md)
- Teams 지원 회의실 장치 [](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)및 솔루션을 사용하여 회의실을 업그레이드하거나 [Microsoft Teams용 클라우드 비디오 Interop을](cloud-video-interop.md) 사용하여 기존 타사 회의실과 장치를 Teams 모임에 참가할 수 있습니다.
- 사용자에게 인증된 USB 오디오 [및 비디오 장치를 설치합니다.](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- Teams [모임을 인식하고](adopt-microsoft-teams-landing-page.md)채택할 수 있는 준비를 합니다.
- [서비스 관리를 계획합니다.](4-envision-plan-my-service-management.md)
- 다양한 통화 분석 보고서를 익숙하게 활용하여 통화 품질이 나쁜 [문제를 해결하세요.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

이 단계에서는 보통 규모의 프로덕션 준비 파일럿을 실행하는 것이 고려할 수 있습니다.

## <a name="configure-users-for-meetings-first"></a>먼저 모임에 대한 사용자 구성

사용자에게 라이선스를 부여하고 Teams 모임을 위해 조직을 준비한 후 사용자가 먼저 모임을 할 수 있도록 설정해야 합니다. 한 가지 설정으로 모든 작업을 쉽게 할 수 있습니다.

Teams 클라이언트 구성 및 사용자 환경의 자동 준수, [](teams-client-experience-and-conformance-to-coexistence-modes.md) 모임 마이그레이션 서비스 및 Better Together 기능을 비롯한 모임 우선의 모든 기능 및 사용자 환경은 [Microsoft Teams](manage-teams-in-modern-portal.md) 관리 센터에서 또는 [PowerShell을](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)사용하여 [SfBWithTeamsCollabAndMeetings](setting-your-coexistence-and-upgrade-settings.md) 공존 모드(또는 사용자 그룹 또는 테넌트 기본값)를 부여하여 구성됩니다.

![먼저 모임을 사용하도록 설정하는 관리자 설정 스크린샷](media/teams-meeting-admin-settings.png)

필요한 경우 앱 사용 권한 정책을 사용하여 달성할 수 있는 모임에 더 집중하기 위해 사용자의 Teams 클라이언트의 왼쪽 탐색에서 Teams 및 채널 애플리케이션을 숨기려 [할 수 있습니다.](teams-app-permission-policies.md)

## <a name="reporting-and-call-analytics"></a>보고 및 호출 분석

모임에서 Teams 모임에 대한 보고 및 통화 분석은 다른 모드의 모임과는 다른 것입니다.

## <a name="related-links"></a>관련 링크

이 문서를 검토한 후 자세한 내용은 업그레이드 여정 [](migration-interop-guidance-for-teams-with-skype.md) [선택,](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)마이그레이션 및 상호 운영성 지침 및 비즈니스용 [Skype와의](coexistence-chat-calls-presence.md) 공존을 참조할 수 있습니다.


