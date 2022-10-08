---
title: 모임 우선 - Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: lsomi
description: 채팅, 통화 및 현재 상태를 위해 비즈니스용 Skype 계속 사용하면서 사용자가 Teams에서 모임을 만들 수 있는 모임 우선에 대해 알아봅니다.
ms.localizationpriority: medium
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
ms.openlocfilehash: 88be8ef1e43cc9d17fb541f6c56186959aeeb8a4
ms.sourcegitcommit: 401cee68d4f6f9470d614dda12b9cb023f382ff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2022
ms.locfileid: "67999343"
---
# <a name="meetings-first"></a>무엇보다도 모임을 우선으로

"모임 우선"은 Teams 모임을 최대한 빠르게 사용하려는 온-프레미스 Enterprise Voice 있는 비즈니스용 Skype 서버 조직을 대상으로 하고 최적화됩니다. 이러한 조직의 경우 Meetings First는 Teams 모임 환경의 우선 순위를 지정하는 **아일랜드** 모드를 사용하는 대안입니다.

## <a name="what-is-meetings-first"></a>모임 우선이란?

Meetings First는 **SfBWithTeamsCollabAndMeetings** 공존 모드를 기반으로 합니다. 모임 우선은 제품이나 기능이 아니며 Teams 및 비즈니스용 Skype 기능과 기능을 사용하여 고유하게 맞춤형 공존 환경을 제공하는 구성입니다.

모임 우선에서 사용자는 채팅, 통화 및 현재 상태를 위해 비즈니스용 Skype 계속 사용하면서 Teams에서 모임을 만듭니다. Teams와 비즈니스용 Skype 간에는 형식이 겹치지 않습니다. 채팅, 통화 및 현재 상태는 Teams에서 비즈니스용 Skype 및 해제됩니다. 이 구성을 사용하면 teams만 사용자와의 상호 운용성 시나리오뿐만 아니라 공존하는 동안 사용자의 환경을 향상시키는 비즈니스용 Skype **Teams** 간의 고유한 "더 나은" 시나리오를 사용할 수 있습니다.

![Teams 및 비즈니스용 Skype 함께하는 더 나은 시나리오의 스크린샷.](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> 모임 우선은 활성 Teams 채팅 사용자가 없거나 거의 없는 조직에 더 적합합니다. 활성 Teams 채팅 사용자는 Teams에서 채팅하고 채팅 기록에 액세스할 수 없기 때문에 모임 첫 번째 모드로 전환해서는 안 됩니다. 이러한 사용자는 대신 **아일랜드** 모드에서 할아버지가 되어야 하며, 모임 우선은 Teams에서 채팅에 아직 활성화되지 않은 사용자에게만 부여됩니다.

## <a name="who-should-consider-meetings-first"></a>모임을 먼저 고려해야 하는 사람은 누구인가요?

모임 우선은 Teams 모임으로의 이동을 가속화하려는 Enterprise Voice 함께 비즈니스용 Skype 서버 사용하는 조직을 위한 것입니다. 모임 우선은 특히 Teams로의 관리되는 업그레이드 경로를 원하는 강력한 IT 분야를 가진 조직을 위한 것입니다.

복잡하거나 대규모 조직의 경우 음성 마이그레이션은 일반적으로 사이트별로 수행되며 시간이 오래 걸릴 수 있으며 잠재적으로 몇 년이 걸릴 수 있으므로 공존 시나리오가 확장될 수 있습니다. 해당 공존이 **아일랜드** 모드인 경우 사용자는 항상 두 개의 모임 솔루션(비즈니스용 Skype 및 Teams)을 선택할 수 있으므로 혼란스럽거나 최적이 아닙니다. 음성 마이그레이션과 달리 모임 마이그레이션은 일반적으로 짧은 시간 안에 회사 전체에서 완료될 수 있습니다. 최대한 빨리(그리고 음성 마이그레이션이 완료될 때까지 기다리지 않고) Teams 모임으로 완전히 전환하려는 조직은 먼저 모임을 고려해야 합니다.

모임 우선은 Enterprise Voice 사용자가 없는 조직에는 유용하지 않을 수 있습니다. 이러한 조직은 Teams 모임을 채택하는 즉시 **Teams** 로 업그레이드할 수 있어야 합니다. 먼저 모임을 건너뛰는 것을 고려해야 합니다.

또한 모임 우선은 "모임 전용" RFP가 발급되는 경우와 같이 범위가 순수 재생 모임 솔루션인 조직에 유용합니다.

## <a name="capabilities-in-meetings-first"></a>먼저 모임의 기능

Meeting First는 다음과 같은 기능을 함께 제공합니다.

- [Teams 오디오 회의를](tutorial-audio-conferencing.yml) [사용하여 비즈니스용 Skype 서버(온-프레미스) 사용자를 프로비전합니다](./tutorial-audio-conferencing.yml?tutorial-step=3).
- [모임 마이그레이션 서비스](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms): 사용자가 구성한 모임은 클라우드로 마이그레이션되고 사용자가 모임 우선으로 승격될 때 Teams 모임으로 변환됩니다(Exchange Online 필요).
- Teams 모임 및 팀 및 채널을 중심으로 Teams에서 간소화된 사용자 환경( [앱 사용 권한 정책을](teams-app-permission-policies.md) 사용하여 숨길 수 있음). [Teams 비공개 채팅, 통화 및 자체 프레즌](teams-client-experience-and-conformance-to-coexistence-modes.md) 스는 모임 우선에 노출되지 않으므로 배포 및 채택 노력이 모임에 집중할 수 있습니다.
- 우수한 [Teams 모임 환경](tutorial-meetings-in-teams.yml).
- Teams와 비즈니스용 Skype 간의 "Better Together": 
  - 자동 보류: Teams에서 모임에 참가할 때 비즈니스용 Skype 전화를 받으면 Teams 모임이 보류되고 그 반대의 경우도 마찬가지입니다. 이렇게 하면 사용자가 모임 참가자의 비공개 통화가 들리지 않습니다.
    ![Teams 및 비즈니스용 Skype 함께하는 더 나은 시나리오의 스크린샷.](media/meetings-first-better-together-hold.png)
  - 현재 상태 조정: Teams의 활동은 사용자의 현재 상태(채팅 및 통화가 비즈니스용 Skype 이후 비즈니스용 Skype 현재 상태)에 반영됩니다. 특히 모임 첫 번째 사용자가 Teams 모임에 있는 경우 해당 사용자의 현재 상태가 이를 반영하도록 업데이트됩니다. 화면을 표시하면 현재 상태가 방해 금지(비즈니스용 Skype 설정에 따라)를 표시하도록 업데이트됩니다.
  - USB 장치 HID 컨트롤 조정(Mac에서도 사용 가능): HID 컨트롤은 Teams 모임에 참가하는 동안 Teams에서, 그리고 다른 모든 상황에서 비즈니스용 Skype 적용됩니다.
  - 달리 언급하지 않는 한 Better Together 기능에는 현재 최신 Windows 데스크톱 클라이언트가 필요합니다.

## <a name="prerequisites-for-meetings-first"></a>먼저 모임을 위한 필수 구성 요소

모임 우선에 대한 유일한 어려운 요구 사항은 온-프레미스 Active Directory 및 비즈니스용 Skype 온-프레미스 배포를 사용하는 Teams의 요구 사항과 동일합니다.

- [Teams에 대한 일반적인 필수 구성 요소](upgrade-plan-journey-prerequisites.md)(예:
- [Teams의 ID 및 인증 및](identify-models-authentication.md)
- [Teams 및 비즈니스용 Skype 대한 Azure Active Directory를 구성합니다](/skypeforbusiness/hybrid/configure-azure-ad-connect).

[비즈니스용 Skype 하이브리드 토폴로](/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online)지가 필요하지는 않지만 권장됩니다. 모임 마이그레이션 서비스 및 상호 운용성과 같은 일부 기능은 해당 토폴로지에서 사용합니다.

Meetings First는 모든 버전의 비즈니스용 Skype 서버 지원되며 더 이상 지원되지 않는 Lync Server에서 작동하는 것으로 알려져 있습니다. 지원되는 모든 비즈니스용 Skype 클라이언트에서 지원되지만 Better Together 기능에는 최근 클라이언트가 필요합니다.

이러한 요구 사항이 충족되면(이전이 아님) [Microsoft 365 또는 Office 365 및 Teams에 대해 사용자에게 라이선스](/office365/enterprise/assign-licenses-to-user-accounts)를 부여할 수 있습니다.

최상의 모임 첫 번째 환경을 위해 사용자는 [Exchange Online](exchange-teams-interact.md), [SharePoint Online 및 비즈니스용 OneDrive](sharepoint-onedrive-interact.md) 및 Microsoft 365 그룹 만들기를 사용하도록 설정해야 합니다. 모임 우선은 사서함이 Exchange 온-프레미스에 있거나 SharePoint Online 또는 비즈니스용 OneDrive 또는 Microsoft 365 그룹을 만들지 않은 사용자에 대해 지원됩니다. 그러나, 그들의 경험은 덜 완전 할 것이다. 온-프레미스에서 Exchange Server 사용하는 조직의 경우 Teams 클라이언트에서 모임을 만들고 보는 데 몇 가지 제한 사항(Exchange Server 버전에 따라 다름)과 규정 준수 기능과 관련된 몇 가지 제한 사항이 있을 수 있습니다.

최소한 사용자는 [Teams에 대한 라이선스를](/microsoft-365/admin/manage/assign-licenses-to-users) 받아야 합니다. 또한 필요한 경우 [오디오 회의에](set-up-audio-conferencing-in-teams.md) 대한 라이선스를 부여할 수 있습니다.

사용자에게 라이선스를 부여할 때 [**SfBOnly** 또는 **SfBWithTeamsCollab**](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 모드를 테넌트 기본값으로 부여하는 것이 좋습니다. 이 설정은 사용자가 모임을 먼저 시작하기 전에 기본 **아일랜드** 모드에서 Teams를 직접 사용하지 않도록 합니다.

모임 우선은 전체 데스크톱 클라이언트(Windows 및 Mac), 브라우저 클라이언트 및 모바일 클라이언트에서 지원됩니다. [또한 Microsoft Teams 룸](/microsoftteams/room-systems/) 호환 가능합니다. Better Together에는 전체 데스크톱 클라이언트가 필요합니다.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>먼저 모임에서 Teams 모임 준비

사용자가 Teams 모임에서 최상의 환경을 갖도록 하려면 다음을 수행해야 합니다.

- 특히 [Microsoft Teams에 대한 모임 및 회의](deploy-meetings-microsoft-teams-landing-page.md)의 단계를 수행합니다.
- [환경을 평가합니다](3-envision-evaluate-my-environment.md).
- [Microsoft Teams를 위해 조직의 네트워크를 준비합니다](prepare-network.md).
- Teams 지원 [회의실 장치 및 솔루션](/skypeforbusiness/certification/devices-meeting-rooms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json)으로 회의실을 업그레이드하거나 [Microsoft Teams용 Cloud Video Interop](cloud-video-interop.md) 을 사용하여 기존 타사 회의실 및 디바이스가 Teams 모임에 참가할 수 있도록 합니다.
- 사용자에게 [인증된 USB 오디오 및 비디오 장치를 장착합니다](/skypeforbusiness/certification/devices-usb-devices?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json).
- [Teams 모임에 대한 인식 및 채택을 촉진할 준비를 합니다](adopt-microsoft-teams-landing-page.md).
- [서비스 관리를 계획합니다](4-envision-plan-my-service-management.md).
- 풍부한 통화 분석 보고서를 숙지하여 [통화 품질 저하 문제를 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)합니다.

이 단계에서는 적당한 규모의 프로덕션 준비 파일럿을 실행하는 것이 좋습니다.

## <a name="configure-users-for-meetings-first"></a>모임에 대한 사용자 구성 우선

사용자에게 라이선스를 부여하고 Teams 모임을 위해 조직을 준비한 후에는 사용자가 모임을 먼저 사용할 수 있도록 해야 합니다. 우리는 쉽게 만들었습니다 : 하나의 설정은 모든 것을 할 것입니다.

Teams 클라이언트 구성 및 사용자 환경의 [자동 준수](teams-client-experience-and-conformance-to-coexistence-modes.md), 모임 마이그레이션 서비스 및 Better Together 기능을 포함한 모임 우선의 모든 기능 및 사용자 환경은 사용자(또는 사용자 그룹 또는 테넌트 기본값)에게 [Microsoft Teams 관리 센터](manage-teams-in-modern-portal.md) 또는 [PowerShell](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)을 사용하여 [SfBWithTeamsCollabAndMeetings 공존 모드](setting-your-coexistence-and-upgrade-settings.md)를 부여하여 구성됩니다.

![모임을 먼저 사용하도록 설정하는 관리자 설정의 스크린샷.](media/teams-meeting-admin-settings.png)

사용자의 Teams 클라이언트 왼쪽 탐색에서 Teams 및 채널 애플리케이션을 숨겨 모임에 대한 환경을 더욱 집중하려는 경우 [앱 설정 정책을](teams-app-setup-policies.md) 사용할 수 있습니다.

## <a name="reporting-and-call-analytics"></a>보고 및 통화 분석

모임 우선에서 Teams용 보고 및 통화 분석 모임은 다른 모드의 모임과 변경되지 않습니다.

## <a name="related-links"></a>관련 링크

자세한 내용은 [업그레이드 경험 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md) 및 [비즈니스용 Skype 공존](coexistence-chat-calls-presence.md)을 참조하세요.
