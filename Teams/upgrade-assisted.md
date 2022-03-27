---
title: 보조 업그레이드 | Skype Business Online에서 업그레이드할 Teams
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
ms.openlocfilehash: a162a9151413137282d80e47f8f2b08c841e171a
ms.sourcegitcommit: 39378888464ade3cb45879a449143f40f202f3e9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2022
ms.locfileid: "64456891"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>온라인에서 비즈니스용 Skype 업그레이드를 Microsoft Teams

Microsoft는 비즈니스용 Skype 2021년 7월 31일 온라인을 사용 중지합니다.  Microsoft는 조직에서 나머지 온라인 사용자만 사용할 수 있도록 비즈니스용 Skype 업그레이드 프로세스를 Teams 제공합니다.  Microsoft 지원 업그레이드는 기술 작업의 수를 줄이고 조직이 어떤 조직인지 여부에 비즈니스용 Skype 없이 전 세계로의 전환을 간소화합니다.
 - 순수 온라인 전용으로 비즈니스용 Skype *온라인* 에서 업그레이드해야 하는 순수 Teams 조직 또는
 - 온라인 사용자와 비즈니스용 Skype 모두에 있는   하이브리드 조직과 비즈니스용 Skype 서버 온라인 사용자만 업그레이드해야 비즈니스용 Skype 전용  으로 업그레이드해야 Teams. 

업그레이드 전에 업그레이드 [지침을 검토하는](https://aka.ms/SkypeToTeams) 것이 좋습니다. 업그레이드 지침에는 온라인에서 온라인으로 업그레이드를 완료하기 위한 권장 비즈니스용 Skype 유용한 리소스가 Teams. 이 지침은 업그레이드의 모든 측면을 관리하거나 보조 프로세스를 Teams 조직에서 업그레이드를 계획하는 모든 조직에 적용됩니다.

## <a name="the-assisted-upgrade-experience"></a>보조 업그레이드 환경
비즈니스용 Skype 업그레이드를 예약한 Teams 온라인 고객은 메시지 센터의 게시물 변경 계획, Microsoft 365 관리 센터의 대시보드 알림 업그레이드, 최종 사용자에게 앱 내 Teams  플래그와 같은 다양한 형태의 알림을 받게 됩니다. 메시지 센터 및 Teams 관리 센터의 업그레이드 알림에는 지원된 업그레이드의 예약된 날짜뿐만 아니라 리소스 및 교육을 업그레이드하는 링크가 포함되어 있으며, 이 알림은 지원 센터의 채택 및 사용에 도움이 Teams.

지원되는 업그레이드 환경은 조직에 모든 사용자가 프레미스 환경이 있는지 여부에 따라 약간 비즈니스용 Skype 서버 다릅니다.
- **순수 온라인 조직:** Busineess Server 사용자에 대한 Skype 조직에 대한 지원 업그레이드 프로세스는 조직에 정책을 적용합니다. `TeamsUpgradeOverridePolicy` 이 정책이 적용된 경우 모든 비즈니스용 Skype Online 사용자가 TeamsOnly 모드로 배치됩니다.
- **프레** 미스 사용자와 비즈니스용 Skype 하이브리드 조직: 하이브리드가 구성되어 있는지에 관계없이 비즈니스용 Skype 서버 있는 모든 사용자가 있는 조직을 포함합니다. 이러한 조직에는 다음 범주 중 하나에 속하는 사용자가 있을 수 있습니다.

  - 프레미스에 비즈니스용 Skype 서버 사용자(사용자만 사용할 수 Teams 수 있지만 사용자만 Teams)
  - TeamsOnly Online에 비즈니스용 Skype 사용자
  - 온라인에 있는 비 TeamsOnly 비즈니스용 Skype 사용자

보조 업그레이드 프로세스는 사용자의 마지막 범주에만 영향을 미치게 됩니다. Teams 온라인에 비즈니스용 Skype 사용자만 Teams 모드로 업그레이드됩니다. 프레미스 비즈니스용 Skype TeamsOnly 사용자와 기존 TeamsOnly 사용자는 지원된 업그레이드 프로세스의 영향을 하지 않습니다.

> [!NOTE]
> 조직은 업그레이드가 완료될 때까지 비즈니스용 Skype 온라인을 계속 사용할 수 있습니다. 지원 업그레이드를 예약한 경우 Teams 업그레이드 날짜 전에 온라인에서 비즈니스용 Skype 자체 업그레이드를 수행할 수 있습니다. 수동으로 업그레이드하여 업그레이드하는 방법에 대한 자세한 Teams 업그레이드 지침을 [참조하세요](https://aka.ms/SkypeToTeams).

업그레이드 기간은 사용자 볼륨 및 배포의 특성에 따라 달라집니다. 대부분의 경우 테넌트 내의 사용자는 업그레이드가 시작된 후 24시간 이내에 업그레이드됩니다. 이 기간 동안 최종 사용자는 여전히 온라인 비즈니스용 Skype 액세스할 수 있습니다. 업그레이드가 완료되면 사용자가 온라인에서 비즈니스용 Skype, 메시지, 모임 및 통화에 Teams 시작할 것입니다.

## <a name="the-post-upgrade-experience"></a>업그레이드 후 환경

보조 업그레이드가 완료되면 업그레이드된 사용자에 대한  공존 모드가 Teams 설정됩니다. 업그레이드하기 [전에 Teams 모드](teams-only-mode-considerations.md) 고려 사항을 검토하는 것이 좋습니다. 아래 표에서는 사용자 환경만의 Teams 개요를 제공합니다.

:::row:::
    :::column span="1":::
        **채팅 및 통화**
    :::column-end:::
    :::column span="3":::
        - 모든 통화 및 채팅이 시작되어 수신됩니다Teams
        - 사용자는 모든 사용자와 통신(채팅/비즈니스용 Skype 수 있습니다.
        - 조직에서는 외부 Teams 관리하여 Skype 사용자와 통신할 [수 있습니다.](manage-external-access.md)
        - Teams 온라인에 로그인하려고 시도하는 비즈니스용 Skype 사용자가 Teams
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
            > 순수 온라인 비즈니스용 Skype 고객은 MMS(모임 마이그레이션 서비스)를 사용하여 기존 온라인 모임을 비즈니스용 Skype 모임으로 마이그레이션해야 Teams 합니다. 지원된 업그레이드 날짜 이전에 MMS를 사용하는 것이 좋습니다. MMS에 대한 자세한 내용은 [MMS(모임 마이그레이션 서비스)를 참조하세요](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms).
    :::column-end:::
:::row-end:::

하이브리드 배포 및 비즈니스용 Skype 서버 업그레이드가 Teams 경우 업그레이드가 완료된 비즈니스용 Skype 서버 Teams 이동할 수 있습니다.

## <a name="related-content"></a>관련 콘텐츠

- [Microsoft Teams 업그레이드 시작하기](upgrade-start-here.md)
- [비즈니스용 Skype Online 단종](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams 전용 모드 고려 사항](teams-only-mode-considerations.md)
