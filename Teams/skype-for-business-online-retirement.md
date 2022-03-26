---
title: 비즈니스용 Skype Online 단종
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 온라인에 대한 사용 중지 비즈니스용 Skype Microsoft가 고객이 마이그레이션할 수 있도록 도와주는 방법에 대해 Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dcd2148a3f939bd8799b7b3f8b86118359936b7c
ms.sourcegitcommit: d3d3d5a70a69359fc71f072ad6c651556f4eda00
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2022
ms.locfileid: "63783907"
---
# <a name="skype-for-business-online-retirement"></a>비즈니스용 Skype Online 단종

2021년 7월 31일 Microsoft는 온라인에서 비즈니스용 Skype 사용 중지했다. 이 사용 중지는 2019년 7월에 고객에게 2년 전에 업그레이드 계획을 수립할 수 있도록 Microsoft Teams. Teams 통신 및 공동 작업을 위한 핵심 Microsoft 365. Microsoft는 비즈니스용 Skype 온라인이 사용 중지된 경우 고객이 성공적인 업그레이드를 계획하고 실행하는 데 필요한 정보와 리소스를 확보하도록 Teams.  Skype 서비스 사용 중지의 영향을 받지 않습니다. 온라인 비즈니스용 Skype 사용 중지된 이유에 대한 배경은 [FAQ-](FAQ-journey.yml)비즈니스용 Skype 업그레이드를 Microsoft Teams.

Microsoft는 2022년 6월 30일 비즈니스용 Skype 온라인 인프라를 해제하기 시작할 것입니다. 이 문서에는 모든 버전에서 업그레이드된 TeamsOnly 사용자가 있는 조직에 대한 비즈니스용 Skype.


## <a name="organizations-with-on-premises-deployments-of-skype-for-business-server"></a>프레미스 배포가 있는 비즈니스용 Skype 서버

온라인 비즈니스용 Skype 사용 중지는 2013 및 Lync Server 2013의 온-프레미스 배포에 비즈니스용 Skype 서버 영향을 주지 않습니다. 그러나 온라인 및온-프레미스에 사용자가 혼합된 하이브리드 고객은 온라인 사용자를 업그레이드 *해야* 합니다. 모든 온라인 사용자는 TeamsUpgradePolicy를 사용하여 TeamsOnly 모드를 할당해야 합니다. Microsoft는 나머지 온라인 사용자의 업그레이드를 TeamsOnly 모드로 비즈니스용 Skype 지원 업그레이드를 제공합니다. 하이브리드 조직은 이 사용 중지  의 결과로 비즈니스용 Skype 사용자가 클라우드로 이동하지 않습니다. Microsoft는 TeamsOnly 사용자와 온-프레미스 사용자가 혼합된 하이브리드 조직을 비즈니스용 Skype 합니다. 2013 또는 Lync Server 2013의 하이브리드 비즈니스용 Skype 서버 고객은 온라인 사용 [중지를 비즈니스용 Skype 검토해야 합니다](/skypeforbusiness/hybrid/plan-hybrid-connectivity#implications-of-the-upcoming-retirement-of-skype-for-business-online).

## <a name="what-to-expect-post-retirement"></a>사후 사용 중지를 예상할 수 있는 것

클라우드에 있는 사용자가 TeamsOnly가 다른 모드로 할당되는 것이 더 이상 불가능합니다. 즉,

 - 프레미스에서 홈이 아닌 새 사용자에게 라이선스를 비즈니스용 Skype 서버 사용자는 TeamsUpgradePolicy의 테넌트의 전역 정책에 관계없이 TeamsOnly 모드가 자동으로 할당됩니다.
 - 하이브리드 조직에서 사용자가 홈온-프레미스를 클라우드로 이동하는 경우 사용자가 에 스위치를 지정한지 여부에 관계없이 TeamsOnly `MoveToTeams` 모드가 자동으로 할당됩니다 `Move-CsUser`.
 - 클라우드에 있는 사용자는 TeamsOnly 외의 모드를 할당할 수 없습니다. 홈 온라인 사용자는 *온라인* 에서 비즈니스용 Skype 사용하지 않습니다.

고객은 Online에 비즈니스용 Skype 아직 TeamsOnly 모드가 할당되지 않은 나머지 사용자가 있을 수 있습니다. 고객은 이러한 사용자에게 가능한 한 빨리 TeamsOnly 모드를 할당해야 합니다. Microsoft는 TeamsOnly 모드가 아닌 비즈니스용 Skype 온라인 사용자에 대한 보조 업그레이드를 제공합니다. 지원되는 업그레이드 환경은 조직이 순수 온라인 조직인지 아니면 사용자가 있는 조직인지에 따라 비즈니스용 Skype 있습니다. 자세한 내용은 온라인에서 온라인 비즈니스용 Skype [업그레이드](upgrade-assisted.md)를 Microsoft Teams.

보조 업그레이드가 완료되면 모든 온라인 사용자가 TeamsOnly 모드로 전환됩니다. TeamsOnly 모드의 사용자는 수신 채팅 및 전화 통화를 Teams 모임을 예약할 수도 Teams. 온라인에서 채팅 또는 통화를 시작하거나 모임을 예약할 비즈니스용 Skype 없습니다.  그러나 TeamsOnly 사용자는 이미 비즈니스용 Skype 받은 모임에 참가할 수 있습니다. 마지막으로,온-프레미스에 있는 모든 사용자는온-프레미스 상태로 유지되어 *TeamsOnly로 설정되지 않습니다*.

## <a name="actions-to-take-before-june-30-2022"></a>2022년 6월 30일 이전의 작업
이제 비즈니스용 Skype 사용 중지된 Microsoft는 지원 인프라를 2022년 6월 30일보다 빨리 해제하기 시작할 예정입니다.  모든 버전에서 업그레이드된 TeamsOnly 사용자를 비즈니스용 Skype 이러한 상황 중 하나를 적용하는 경우 조치를 취해야 합니다.

- TeamsOnly 사용자가 있는 경우 미리 비즈니스용 Skype 업그레이드된 후 아직 로그인하지 않은 Teams 사용자입니다. 
- TeamsOnly로 업그레이드하기 전에 구성한 온라인 비즈니스용 Skype 아직 TeamsOnly 사용자가 있는 경우.

이러한 상황 중 하나가 조직에 적용되는 경우 아래 설명한 바와 같이 2022년 6월 30일까지 조치를 취해야 합니다.

 - **비즈니스용 Skype** 온라인 연락처: 사용자가 TeamsOnly 모드로 업그레이드된 후 사용자가 처음으로 로그온할 Teams 해당 사용자의 비즈니스용 Skype 온라인 계정의 기존 연락처가 Teams. Microsoft에서 온라인 비즈니스용 Skype 제거한 후 아직 로그온하지 않은 사용자의 연락처를 더 이상 마이그레이션할 *수 Teams.* 연락처를 비즈니스용 Skype Teams 이전에 비즈니스용 Skype 모든 사용자가 2022년 6월 30일 이전에 Teams 로그온하는 것이 좋습니다.

 - **비즈니스용 Skype 온라인 모임:** 조직이 TeamsOnly로 업그레이드된 후 사용자는 모든 새 모임을 Teams 생성합니다. 경우에 따라 TeamsOnly 사용자는 이전에 비즈니스용 Skype 온라인 모임을 계속 사용할 수 있습니다. 현재 업그레이드된 TeamsOnly 사용자 및 초대된 참석자들은 해당 비즈니스용 Skype 클라이언트를 사용하여 이러한 비즈니스용 Skype 온라인 모임에 참가할 비즈니스용 Skype 있습니다. 그러나 Microsoft가 비즈니스용 Skype TeamsOnly 사용자에 대한 온라인 인프라를 제거한 후 해당 사용자가 비즈니스용 Skype 나머지 모든 온라인 모임은 더 이상 존재하지 않습니다. 이끌이 및 참석자는 이러한 모임에 참가할 수 없습니다. TeamsOnly 조직의 사용자가 구성한 비즈니스용 Skype 온라인 모임이 남아 있는 경우 Microsoft는 이러한 모임을 다른 모임으로 Teams 것이 좋습니다. 또는 관리자는 모임 마이그레이션 서비스를 사용하여 이러한 모임 [](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) 을 모임에 Teams 있습니다. 두 경우 모두 2022년 6월 30일까지 이러한 작업을 완료합니다.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft가 고객이 업그레이드할 수 있도록 도와주는 Teams

현재 온라인에서 온라인 비즈니스용 Skype 업그레이드를 Teams 것이 좋습니다. 사용 가능한 리소스를 활용하여 Teams 배포 및 업그레이드를 계획할 수 비즈니스용 Skype.

- [Teams 및 업그레이드](upgrade-start-here.md) 설명서 - IT 관리자를 위한 무료 기술 지침입니다.

- [Teams](./upgrade-workshops-landing-page.yml) 업그레이드 계획 워크샵 – 무료 대화형 업그레이드 계획 워크샵에서 업그레이드를 계획하고 구현할 수 있도록 설계된 지침, 모범 사례 및 리소스를 Teams.

- [온라인에서](upgrade-assisted.md) 비즈니스용 Skype 업그레이드로 Microsoft Teams - 온라인 사용자를 업그레이드하는 비즈니스용 Skype 자동화된 Teams.

- [FastTrack Microsoft 365](https://www.microsoft.com/fasttrack/microsoft-365) - Teams 계획에 사용할 수 있는 배포 지원을 제공합니다.

- [Teams](./instructor-led-training-teams-landing-page.yml) 라이브 교육 – 조직을 구성하고 실행하도록 설계된 무료 온라인 교육 Teams.

- [Teams Chalk Talks](./chalk-talks-landing-page.yml) – 주요 시나리오에 대한 모범 사례를 설명하는 IT 프로 및 의사 결정자에 대한 무료 온라인 워크샵 Teams.

- [Microsoft 파트너](https://www.microsoft.com/solution-providers/home) – Microsoft 솔루션 공급자는 Microsoft 솔루션 공급자를 사용하여 모든 기능을 활용할 수 Teams.

- [Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) 블로그 – Teams, 채택 및 사용 리소스, Teams 및 다른 비즈니스 애플리케이션과의 통합에 대한 뉴스를 제공합니다.

현재 온라인 고객인 비즈니스용 Skype 지금 업그레이드 계획을 Teams 시작하세요. 강력한 커뮤니케이션 및 공동 작업 기능을 경험할 수 있는 것을 매우 기대하며, 이를 위해 최선을 다하고 있습니다.  온라인 사용 중지에 대한 비즈니스용 Skype 대한 자세한 내용은 [FAQ-](FAQ-journey.yml)비즈니스용 Skype 업그레이드를 Microsoft Teams.





