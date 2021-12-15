---
title: 보조 업그레이드 | Skype 업그레이드할 비즈니스 온라인 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 온라인에서 온라인으로의 비즈니스용 Skype 업그레이드 개요 Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 44ca04f9fce23876c7ee782ef5cc5078da7e67c4
ms.sourcegitcommit: 8d728ca42dc917a28b94e2de84ce4f5b2515d485
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2021
ms.locfileid: "61513469"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>온라인에서 비즈니스용 Skype 업그레이드를 Microsoft Teams

Microsoft는 서비스가 2021년 7월 31일 Teams 조직이 온라인에서 성공적인 전환을 비즈니스용 Skype 수 있도록 지원되는 업그레이드를 제공합니다. 조직이 온라인 또는 비즈니스용 Skype  또는 하이브리드를 비즈니스용 Skype *온라인에서* 업그레이드하는지 비즈니스용 Skype **온라인** 및 비즈니스용 Skype 서버 ) 환경, 보조 업그레이드는 필요한 기술 작업의 수를 줄이고 조직 준비, 사용자 인식 및 교육에 더 많은 Teams 허용합니다.

업그레이드 전에 업그레이드 지침을 [검토하는](https://aka.ms/SkypeToTeams) 것이 좋습니다. 업그레이드 지침에는 온라인에서 온라인으로 업그레이드를 완료하기 위한 권장 활동 및 비즈니스용 Skype 유용한 리소스가 Teams. 이 지침은 업그레이드의 모든 측면을 관리하거나 보조 프로세스를 Teams 조직에서 업그레이드를 계획하는 모든 조직에 적용됩니다.

> [!NOTE]
> 지원 업그레이드를 예약한 경우 Teams 업그레이드 날짜 전에 온라인에서 비즈니스용 Skype 자체 업그레이드를 수행할 수 있습니다. 수동으로 업그레이드하는 방법에 대한 자세한 내용은 업그레이드 Teams [을 참조하세요.](https://aka.ms/SkypeToTeams)
>
> 지원 업그레이드는 프레미스에서 배포할 수 비즈니스용 Skype 서버.

## <a name="notifications-for-scheduled-customers"></a>예약된 고객에 대한 알림

비즈니스용 Skype 업그레이드를 예약한 Teams 일련의 업그레이드 알림을 받게 됩니다. 이러한 알림은 예약된 업그레이드 날짜 30일 전에 시작됩니다. 이러한 알림은 메시지  센터의 변경 계획 Microsoft 365 관리 센터에서 대시보드 알림을 업그레이드하고, 최종 사용자에게 Teams 앱 내 플래그로 전달됩니다.

업그레이드 알림에는 보조 업그레이드의 예약된 날짜가 포함되어 있으며, 리소스 및 교육을 업그레이드하여 업그레이드를 통해 업그레이드를 지원하고 사용 현황을 Teams.

## <a name="the-assisted-upgrade-experience"></a>보조 업그레이드 환경

보조 업그레이드는 위에서 언급한 일정 알림에서 테넌트별 날짜를 공유하여 2021년 8월에 시작됩니다.

지원되는 업그레이드 환경은 하이브리드 환경이 있는 비즈니스용 Skype 온라인 전용 또는 비즈니스용 Skype 여부에 따라 약간 다릅니다.

- **비즈니스용 Skype 온라인 전용** 업그레이드 프로세스는 조직에 `TeamsUpgradeOverridePolicy` 정책을 적용합니다. 이 정책이 적용된 경우 모든 비즈니스용 Skype 모든 온라인 사용자가 Teams 모드로 배치됩니다.
- 비즈니스용 Skype 하이브리드 환경이 **있는 온라인에서는** 다음 범주 중 하나에 속하는 사용자가 있을 수 있습니다.

  - 프레미스에 홈이 있는 비즈니스용 Skype 서버
  - 비즈니스용 Skype 전용 모드인 Teams 온라인 사용자
  - 비즈니스용 Skype 전용 모드가 아닌  Teams 온라인 사용자

  위에 나열된 각 범주에 사용자가 혼합되어 있는 경우 보조 업그레이드 프로세스는 해당 비즈니스용 Skype 없는 경우 Teams 전용 모드로만 전환됩니다. 프레미스 비즈니스용 Skype 업그레이드 프로세스에 영향을주지 않습니다.

> [!NOTE]
> 보조 업그레이드가 2021년 7월 31일 이후 날짜로 예약된 경우 걱정하지 마세요. 조직은 업그레이드가 완료될 때까지 비즈니스용 Skype 온라인을 사용할 수 있습니다.

업그레이드 기간은 사용자 볼륨 및 배포의 특성에 따라 달라집니다. 대부분의 경우 테넌트 내의 사용자는 업그레이드가 시작된 후 24시간 이내에 업그레이드됩니다. 이 기간 동안 최종 사용자는 여전히 온라인 비즈니스용 Skype 액세스할 수 있습니다. 업그레이드가 완료되면 사용자가 온라인에서 비즈니스용 Skype, 메시지, 모임 및 통화에 Teams 시작할 것입니다.

## <a name="the-post-upgrade-experience"></a>업그레이드 후 환경

보조 업그레이드가 완료되면 업그레이드된  사용자에 대한 공존 모드가 Teams만 설정됩니다. 업그레이드하기 전에 Teams [모드](teams-only-mode-considerations.md) 고려 사항을 검토하는 것이 좋습니다. 아래 표에서는 사용자 환경만의 Teams 개요를 제공합니다.

:::row:::
    :::column span="1":::
        **채팅 및 통화**
    :::column-end:::
    :::column span="3":::
        - 모든 통화 및 채팅이 시작되어 수신됩니다Teams
        - 사용자는 모든 사용자와 통신(채팅/비즈니스용 Skype 수 있습니다.
        - 조직에서는 외부 Teams 관리하여 Skype 사용자와 통신할 [수 있습니다.](manage-external-access.md)
        - Teams 온라인에 로그인하려고 시도하는 비즈니스용 Skype 사용자로 리디렉션됩니다Teams
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **모임**
    :::column-end:::
    :::column span="3":::
        - 사용자가 모든 새 모임을 Teams(플러그 인 대체)
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **마이그레이션된 데이터**
    :::column-end:::
    :::column span="3":::
        - 페더리드를 포함하여 비즈니스용 Skype Online의 기존 연락처(메일 목록 없음)
        - 사용자가 처음으로 로그인할 때 Teams 마이그레이션됩니다.
            > [!IMPORTANT]
            >업그레이드가 완료된 후 90일 이내에 연락처를 마이그레이션해야 합니다.
        - 기존 비즈니스용 Skype 온라인 모임이 Teams 모임으로 변환됩니다.
            > [!IMPORTANT]
            > 순수 온라인 비즈니스용 Skype 고객은 MMS(모임 마이그레이션 서비스)를 사용하여 기존 온라인 모임을 비즈니스용 Skype 모임으로 마이그레이션해야 Teams 합니다. 지원된 업그레이드 날짜 이전에 MMS를 사용하는 것이 좋습니다. MMS에 대한 자세한 내용은 [MMS(모임 마이그레이션 서비스) 사용을 참조하세요.](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
    :::column-end:::
:::row-end:::

하이브리드 배포 및 비즈니스용 Skype 서버 업그레이드가 Teams 업그레이드가 완료되면 사용자 비즈니스용 Skype 서버 Teams 수 있습니다.

## <a name="related-content"></a>관련 콘텐츠

- [Microsoft Teams 업그레이드 시작하기](upgrade-start-here.md)
- [비즈니스용 Skype Online 단종](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams 모드 고려 사항](teams-only-mode-considerations.md)
