---
title: Microsoft 팀 | 모임 먼저
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: francoid
description: 사용자가 팀에서 모임을 만들 수 있으며, 채팅, 통화 및 현재 상태에 대해 비즈니스용 Skype를 계속 사용 하면서 모임에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 10321d02398c6c2b0ffc2143a9bafa406fbec637
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836458"
---
# <a name="meetings-first"></a>무엇보다도 모임을 우선으로

"모임 먼저"는 비즈니스용 Skype 서버 조직을 대상으로 지정 하 고 최적화 하며, 팀 모임 사용을 최대한 빠르게 시작 하려는 경우 온-프레미스입니다. 이러한 조직의 경우 첫 번째 모임은 팀 모임 경험에 우선 순위를 두는 **아일랜드** 모드를 사용 하는 대신 사용할 수 있습니다.

## <a name="what-is-meetings-first"></a>모임을 먼저 소개 하세요.

모임은 먼저 **SfBWithTeamsCollabAndMeetings** 공존 모드를 기반으로 합니다. 모임 먼저 제품이 나 기능이 아닌, 팀과 비즈니스용 Skype의 기능을 활용 하 여 고유 하 게 맞춤형 공존 환경을 제공 하는 구성입니다.

먼저 모임에서 사용자는 비즈니스용 Skype를 사용 하 여 채팅, 통화, 현재 상태를 진행 하면서 팀에서 모임을 만듭니다. 팀과 비즈니스용 Skype 간에는 겹치는 형식을 없습니다. 채팅, 통화, 현재 상태는 비즈니스용 Skype 및 팀에서 사용할 수 있습니다. 이렇게 하면 함께 사용할 때 사용자 환경을 개선 하는 비즈니스용 Skype와 팀 간에 고유한 "더 나은" 시나리오를 사용할 수 있으며, **팀 전용** 사용자와의 상호 운용성 시나리오는 매우 다양 합니다.

![팀과 비즈니스용 Skype로 더 나은 통합 시나리오의 스크린샷](media/meetings-first-meeting-in-meeting.png)

> [!Important]
> 모임 우선은 활성 팀 채팅 사용자가 없는 조직에 대 한 더 나은 검색입니다. 활성 팀 채팅 사용자는 팀에서 채팅을 하 고 채팅 내용에 액세스할 수 없게 되므로 모임 첫 번째 모드로 전환 되어서는 안 됩니다. 이러한 사용자는 대신 **아일랜드** 모드에서 grandfathered 팀의 채팅에서 아직 활성화 되지 않은 사용자 에게만 먼저 부여 됩니다.

## <a name="who-should-consider-meetings-first"></a>누가 모임을 먼저 고려해 야 하나요?

처음에는 비즈니스용 Skype 서버를 사용 하 여 팀 모임으로 이동 (특히 팀에 대해 관리 되 고 명확한 업그레이드 경로를 원하는 강력한 IT 규칙이 적용 되는 조직)으로 해당 사용자의 업무를 신속 하 게 사용할 수 있도록 고안 되었습니다.

복잡 한 조직 또는 대규모 조직의 경우 일반적으로 사이트 별로 음성 마이그레이션이 수행 되며, 몇 년이 지난 후에는 확장 공존 시나리오가 발생할 때까지 시간이 오래 걸릴 수 있습니다. 이 동시 사용이 **아일랜드** 모드에 있는 경우 사용자는 항상 두 개의 모임 솔루션 (비즈니스용 Skype 및 팀)을 선택 하 여 혼동 되거나 최적이 되지 않는 상황을 초래할 수 있습니다. 음성 마이그레이션과는 달리, 모임 마이그레이션은 일반적으로 전체 회사에서 짧은 시간에 완료할 수 있습니다. 가능한 한 신속 하 게 팀 회의에 완전히 전환 하려는 조직 (즉, 음성 마이그레이션 완료를 기다리지 않고) 하려면 먼저 모임을 고려해 야 합니다.

모임 먼저 엔터프라이즈 음성 사용자가 없는 조직에는 유용 하지 않을 수 있습니다. 이러한 조직은 팀 회의를 채택할 수 있는 바로 **팀** 으로 업그레이드할 수 있습니다. 먼저 모임을 건너뛰는 것을 고려해 야 합니다.

또한 모임 우선은 "모임 전용" RFP가 발행 되는 등의 경우와 같이 범위가 순수한 재생 모임 솔루션 인 조직에 유용 합니다.

## <a name="capabilities-in-meetings-first"></a>우선 모임 기능

모임에서는 먼저 다음과 같은 기능을 함께 제공 합니다.

- [비즈니스용 Skype Server (온-프레미스)](https://docs.microsoft.com/microsoftteams/tutorial-audio-conferencing?tutorial-step=3) 의 [팀 오디오 회의](tutorial-audio-conferencing.yml)를 프로 비전 합니다.
- [모임 마이그레이션 서비스](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms): 사용자가 모임으로 승격 됨에 따라 사용자가 구성한 모임이 클라우드로 마이그레이션되고 팀 모임으로 변환 됩니다 (Exchange Online 필요).
- 팀의 간소화 된 사용자 환경, 팀 모임, 팀 및 채널 (선택적으로 [앱 사용 권한 정책을](teams-app-permission-policies.md)사용 하 여 숨길 수 있음)에 집중 [팀 비공개 채팅, 통화 및 자체 현재 상태](teams-client-experience-and-conformance-to-coexistence-modes.md) 는 모임에 먼저 표시 되지 않으며, 배포 및 채택을 통해 모임에 완벽 하 게 집중할 수 있습니다.
- 상사 [팀 모임 경험](tutorial-meetings-in-teams.yml).
- 팀과 비즈니스용 Skype 간의 "서로 더 좋음": 
  - 자동 보관: 팀의 모임 중에 비즈니스용 Skype에서 전화를 거는 경우 팀 모임이 보류 되어 있으며 그 반대의 경우도 마찬가지입니다. 이렇게 하면 사용자가 모임 참가자에 게 개인 전화를 overheard 수 없습니다.
    ![팀과 비즈니스용 Skype로 더 나은 통합 시나리오의 스크린샷](media/meetings-first-better-together-hold.png)
  - 현재 상태 조정: 팀의 활동은 사용자의 현재 상태, 즉 채팅 및 통화는 비즈니스용 Skype에 있기 때문에 비즈니스용 Skype에 반영 됩니다. 특히 팀 모임에 처음으로 모임 사용자가 있는 경우에는이를 반영 하도록 현재 상태가 업데이트 됩니다. 화면을 표시 하면 해당 사용자의 상태는 비즈니스용 Skype의 설정을 기반으로 하는 방해 금지로 업데이트 됩니다.
  - USB 장치 HID 제어 조정 (Mac 에서도 사용 가능): HID 컨트롤은 팀 회의 중에 팀에서 다른 모든 상황의 비즈니스용 Skype에 의해 적용 됩니다.
  - 다른 언급이 없는 한, 더 나은 접근 능력으로 지금 최신 Windows 데스크톱 클라이언트가 필요 합니다.

## <a name="prerequisites-for-meetings-first"></a>모임에 대 한 선행 조건 먼저

첫 번째 모임에 대 한 하드 요구 사항은 온-프레미스 Active Directory 및 비즈니스용 Skype 온-프레미스 배포를 사용 하는 팀의 요구 사항과 동일 합니다.

- [팀에 대 한 일반적인 사전 요구](upgrade-plan-journey-prerequisites.md)조건 (포함)
- [팀의 id 및 인증](identify-models-authentication.md)
- [팀과 비즈니스용 Skype에 대 한 Azure Active Directory를 구성](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-azure-ad-connect)합니다.

[비즈니스용 Skype 하이브리드 토폴로지가](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-federation-with-skype-for-business-online) 필요 하지는 않지만 권장 되는 방법입니다. 모임 마이그레이션 서비스 및 상호 운용성 등의 일부 기능은 해당 토폴로지에 의존 합니다.

모임 먼저는 비즈니스용 Skype 서버의 모든 버전에서 지원 되며 더 이상 지원 되지 않는 Lync Server에서 작업 하는 것으로 알려져 있습니다. 지원 되는 모든 비즈니스용 Skype 클라이언트에서 지원 되지만, 더 나은 기능을 위해서는 최신 클라이언트가 필요 합니다.

이러한 요구 사항이 충족 되 고 이전이 아닌 경우에는 사용자에 게 [Office 365 및 팀에 대 한 라이선스가 부여](https://docs.microsoft.com/office365/enterprise/assign-licenses-to-user-accounts)될 수 있습니다.

최상의 모임 첫 경험을 위해서는 사용자가 [Exchange Online](exchange-teams-interact.md), [SharePoint Online, 비즈니스용 OneDrive](sharepoint-onedrive-interact.md), Office 365 그룹 만들기를 사용 해야 합니다. 사서함이 Exchange 온-프레미스에 있거나 SharePoint Online 또는 비즈니스용 OneDrive 또는 Office 365 그룹 만들기가 없는 사용자에 게는 먼저 모임이 지원 됩니다. 그러나, 그 환경은 그다지 완벽 하지 않을 것입니다. 특히 Exchange Server 온-프레미스를 사용 하는 조직의 경우 팀 클라이언트에서 모임을 만들고 볼 때 준수 기능과 관련 하 여 몇 가지 제한 사항이 있을 수 있습니다 (Exchange Server 버전에 따라 다름).

최소한 사용자는 [팀에 대 한 라이선스가](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)있어야 합니다. 또한 필요한 경우 [오디오 회의](set-up-audio-conferencing-in-teams.md)에 대 한 사용이 허가 될 수 있습니다.

사용자를 라이선스 할 때 테 넌 트 기본값으로 [ **SfBOnly** 또는 **SfBWithTeamsCollab** ](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps) 모드를 부여 하는 것이 좋습니다. 이렇게 하면 사용자가 처음에 모임 시작을 준비 하기 전에 기본 **제도** 모드에서 팀을 사용 하 여 시작 하지 않아도 됩니다.

모임이 먼저 전체 데스크톱 클라이언트 (Windows 및 Mac), 브라우저 클라이언트 및 모바일 클라이언트에서 지원 됩니다. 또한 [Microsoft 팀 대화방](https://docs.microsoft.com/microsoftteams/room-systems/)과 호환 됩니다. 더 잘 협력 하려면 전체 데스크톱 클라이언트가 필요 합니다.

## <a name="prepare-for-teams-meetings-in-meetings-first"></a>먼저 모임에서 팀 모임 준비

사용자가 팀 모임에서 최상의 환경을 제공 하려면 다음을 수행 해야 합니다.

- 특히 [Microsoft 팀의 모임 및 회의에 대 한](deploy-meetings-microsoft-teams-landing-page.md)단계를 따릅니다.
- [환경을 평가](3-envision-evaluate-my-environment.md)합니다.
- [조직의 네트워크에서 Microsoft 팀을 준비](prepare-network.md)합니다.
- [회의실 장치 및 솔루션](https://docs.microsoft.com/skypeforbusiness/certification/devices-meeting-rooms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)을 갖춘 팀에서 회의실을 업그레이드 하거나, [Microsoft 팀을 위한 클라우드 비디오 Interop](cloud-video-interop.md) 를 사용 하 여 팀 모임에 참가할 수 있는 기존 타사 채팅방과 장치를 사용 하도록 설정할 수 있습니다.
- [인증 된 USB 오디오 및 비디오 장치](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)를 사용 하 여 사용자를 장착 하세요.
- [팀 모임에 대 한 인식과 채택을](adopt-microsoft-teams-landing-page.md)준비 합니다.
- [서비스 관리 계획을 수립](4-envision-plan-my-service-management.md)합니다.
- [통화 품질 저하 문제를 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)하기 위해 다양 한 통화 분석 보고서에 대해 익힙니다.

이 단계에서는 중간 규모의 실제 시험 운용 파일럿을 실행 하는 것을 고려할 수 있습니다.

## <a name="configure-users-for-meetings-first"></a>먼저 모임에 대 한 사용자 구성

사용자에 게 라이선스를 부여 하 고 팀 모임에 대 한 조직을 준비한 후에는 먼저 모임에 대해 사용자를 사용할 수 있도록 설정 해야 합니다. 한 번에 하나의 설정으로 더욱 간편 하 게 할 수 있습니다.

팀 클라이언트 구성 및 사용자 환경에 대 한 [자동 준수](teams-client-experience-and-conformance-to-coexistence-modes.md) , 모임 마이그레이션 서비스, 더 나은 기능을 비롯 한 모든 모임의 모든 기능 및 사용자는 [Microsoft 팀 관리 센터](manage-teams-in-modern-portal.md) 에서 또는 [PowerShell](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)을 사용 하 여 [SfBWithTeamsCollabAndMeetings 공존 모드](setting-your-coexistence-and-upgrade-settings.md) 를 사용자에 게 부여 하는 방법 (또는 사용자 그룹 또는 테 넌 트의 기본 설정)

![모임을 먼저 사용 하도록 설정 하는 관리자 설정 스크린샷](media/teams-meeting-admin-settings.png)

필요에 따라 사용자의 팀 클라이언트 탐색에서 팀과 채널 응용 프로그램을 숨겨 모임에 대 한 환경을 더욱 강조 하 고 [앱 권한 정책을](teams-app-permission-policies.md)사용 하 여 달성할 수 있도록 해야 합니다.

## <a name="reporting-and-call-analytics"></a>보고 및 통화 분석

모임에서 팀 모임에 대 한 보고 및 통화 분석이 먼저 다른 모드의 경우와 변경 되지 않습니다.

## <a name="related-links"></a>관련 링크

이 문서를 검토 한 후에는 [업그레이드 여행](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md), [마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)을 참조 하 고 [비즈니스용 Skype를 사용 하 여](coexistence-chat-calls-presence.md) 추가 정보를 확인할 수 있습니다.


