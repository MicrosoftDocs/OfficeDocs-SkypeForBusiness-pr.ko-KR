---
title: 보조 업그레이드 | Skype Business Online에서 Teams 업그레이드로
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: billkau
audience: admin
description: 비즈니스용 Skype Online에서 Teams로의 보조 업그레이드 개요
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03ea21de9f8cb64b1221044babeeae335a52d8ea
ms.sourcegitcommit: 900f28c4ac12d65ccbd996028205ba183b4afb03
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995203"
---
# <a name="assisted-upgrades-from-skype-for-business-online-to-microsoft-teams"></a>비즈니스용 Skype Online에서 Microsoft Teams로 업그레이드 지원

Microsoft는 조직이 2021년 7월 31일 서비스를 사용 중지할 때 비즈니스용 Skype Online에서 성공적으로 전환할 수 있도록 Teams에 대한 지원 업그레이드를 제공합니다. 보조 업그레이드는 필요한 기술 작업 수를 줄이고 조직 준비, 사용자 인식 및 Teams 교육에 더 집중할 수 있도록 합니다.

업그레이드 전에 업그레이드 지침을 [검토하는](https://aka.ms/SkypeToTeams) 것이 좋습니다. 업그레이드 지침에는 비즈니스용 Skype Online에서 Teams로 업그레이드를 완료하기 위한 권장 활동 및 유용한 리소스가 포함되어 있습니다. 이 지침은 업그레이드의 모든 측면을 관리하거나 보조 프로세스를 사용하는 등 Teams로 업그레이드를 계획하는 모든 조직에 적용됩니다.

> [!NOTE]
> Teams로 보조 업그레이드를 예약하는 경우 예약된 업그레이드 날짜 전에 비즈니스용 Skype Online에서 자체 업그레이드를 수행할 수 있습니다. Teams로 수동으로 업그레이드하는 방법에 대한 자세한 내용은 업그레이드 지침 [을 참조하세요.](https://aka.ms/SkypeToTeams)
>
> 비즈니스용 Skype Server의 사내 배포에는 보조 업그레이드를 사용할 수 없습니다.

## <a name="notifications-for-scheduled-customers"></a>예약된 고객에 대한 알림

Teams로의 보조 업그레이드가 예정된 비즈니스용 Skype Online 고객은 일련의 업그레이드 알림을 받게 됩니다. 이러한 알림은 예약된 업그레이드 날짜 90일 전에 시작됩니다. 이러한 알림은 Microsoft  365 메시지 센터의 변경 계획 게시물, Teams 관리 센터의 대시보드 알림 업그레이드, 앱 내 플래그를 최종 사용자에게 전달합니다.

업그레이드 알림에는 보조 업그레이드의 예약된 날짜가 포함되어 있으며, 리소스 및 교육을 업그레이드하여 Teams 채택 및 사용에 도움이 됩니다.

## <a name="the-assisted-upgrade-experience"></a>보조 업그레이드 환경

보조 업그레이드는 위에서 언급한 일정 알림에서 테넌트별 날짜를 공유하여 2021년 8월에 시작됩니다.

업그레이드 기간은 사용자 볼륨 및 배포의 특성에 따라 달라집니다. 그러나 대부분의 경우 테넌트 내의 사용자는 업그레이드가 시작된 후 24시간 이내에 업그레이드됩니다. 이 기간 동안 최종 사용자는 비즈니스용 Skype Online 기능에 계속 액세스할 수 있습니다. 업그레이드가 완료된 후 비즈니스용 Skype Online에서 사용자가 로그인하면 메시징, 모임 및 통화에 Teams를 사용하게 됩니다.

## <a name="the-post-upgrade-experience"></a>업그레이드 후 환경

보조 업그레이드가 완료되면 업그레이드된  사용자에 대한 공존 모드가 Teams 전용으로 설정되어 Microsoft에서 다른 공존 모드로만 변경할 수 있습니다. 업그레이드하기 전에 [Teams Only 모드 고려](teams-only-mode-considerations.md) 사항을 검토하는 것이 좋습니다. 아래 표에서는 Teams Only 사용자 경험에 대한 높은 수준의 개요를 제공합니다.

:::row:::
    :::column span="1":::
        **채팅 및 통화**
    :::column-end:::
    :::column span="3":::
        - 모든 통화 및 채팅이 Teams에서 시작 및 수신됩니다.
        - 사용자는 비즈니스용 Skype 사용자와 통신(채팅/통화)할 수 있습니다.
        - 조직에서는 Teams 사용자가 외부 액세스 권한을 관리하여 Skype 소비자 서비스 사용자와 통신할 수 있도록 [설정할 수 있습니다.](manage-external-access.md)
        - 비즈니스용 Skype Online에 로그인을 시도하는 팀 사용자가 Teams로 리디렉션됩니다.
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **모임**
    :::column-end:::
    :::column span="3":::
        - 사용자가 Teams에서 모든 새 모임 예약(플러그 인 대체)
    :::column-end:::
:::row-end:::
:::row:::
    :::column span="1":::
        **마이그레이션된 데이터**
    :::column-end:::
    :::column span="3":::
        - 페더리드를 포함한 비즈니스용 Skype Online의 기존 연락처(메일 목록 없음)
        - 기존 비즈니스용 Skype Online 모임이 Teams 모임으로 변환됩니다.
    :::column-end:::
:::row-end:::

## <a name="related-content"></a>관련 콘텐츠

- [Microsoft Teams 업그레이드 시작하기](upgrade-start-here.md)
- [비즈니스용 Skype Online 단종](skype-for-business-online-retirement.md)
- [Get-CsTeamsUpgradeStatus](/powershell/module/skype/get-csteamsupgradestatus?view=skype-ps&preserve-view=true)
- [Teams 전용 모드 고려 사항](teams-only-mode-considerations.md)
