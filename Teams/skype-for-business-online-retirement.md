---
title: 비즈니스용 Skype Online 단종
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 비즈니스용 Skype Online의 사용 중지 계획과 Microsoft가 고객이 Teams로 마이그레이션하도록 돕는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: 0e6118e42600bda58bf7ddc9d7f8e0fee0b7ad9f
ms.sourcegitcommit: 0bf44683f5263d7bf635689b4c1d813bd9842650
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67706147"
---
# <a name="skype-for-business-online-retirement"></a>비즈니스용 Skype Online 단종

2021년 7월 31일, Microsoft는 비즈니스용 Skype Online을 사용 중지했습니다. 이 사용 중지는 2019년 7월에 발표되어 고객에게 Microsoft Teams로의 업그레이드 계획을 2년 전에 미리 알립니다. Teams는 Microsoft 365의 커뮤니케이션 및 공동 작업을 위한 핵심 앱입니다. 비즈니스용 Skype Online이 사용 중지된 상태에서 Microsoft는 고객이 Teams로의 성공적인 업그레이드를 계획하고 실행하는 데 필요한 정보와 리소스를 확보하려고 합니다.  Skype 소비자 서비스는 이 사용 중지의 영향을 받지 않습니다. 비즈니스용 Skype Online이 사용 중지된 이유에 대한 배경 정보는 [FAQ(비즈니스용 Skype에서 Microsoft Teams로 업그레이드](FAQ-journey.yml))를 참조하세요.

Microsoft는 2022년 6월 30일 이후에 비즈니스용 Skype Online 인프라의 서비스 해제를 시작합니다. 또한 Microsoft는 2022년 10월부터 하이브리드 조직과 관련된 인프라의 측면을 서비스 해제하기 시작합니다. 이 문서에는 모든 버전의 비즈니스용 Skype 업그레이드된 TeamsOnly 사용자가 있는 조직에 대한 지침이 포함되어 있습니다.

> [!Important]
> **비즈니스용 Skype Online의 사용 중지는 비즈니스용 Skype 서버 및 Lync Server 2013의 온-프레미스 배포 지원에 영향을 주지 않습니다**. 그러나 온라인 및 온-프레미스에 사용자가 혼합된 하이브리드 고객은 모든 *온라인* 사용자를 TeamsOnly로 업그레이드 *해야 합니다*. 모든 온라인 사용자에게 TeamsUpgradePolicy를 사용하여 TeamsOnly 모드를 할당해야 합니다. 또한 Microsoft는 나머지 비즈니스용 Skype Online 사용자를 TeamsOnly 모드로의 업그레이드를 자동화하는 데 도움이 되는 보조 업그레이드를 제공하고 있습니다. 하이브리드 조직은 이러한 사용 중지로 인해 *온-프레미스* 비즈니스용 Skype 사용자를 클라우드로 이동할 필요가 없습니다. *Microsoft는 TeamsOnly 사용자와 온-프레미스 비즈니스용 Skype 사용자가 혼합된 하이브리드 조직을 완벽하게 지원합니다*. 비즈니스용 Skype 서버 또는 Lync Server 2013의 하이브리드 배포를 사용하는 고객은 [비즈니스용 Skype Online 사용 중지의 영향을](/skypeforbusiness/hybrid/plan-hybrid-connectivity.md#implications-of-the-upcoming-retirement-of-skype-for-business-online) 검토해야 합니다.


## <a name="what-to-expect-post-retirement"></a>은퇴 후 예상되는 사항

더 이상 클라우드에 있는 사용자가 TeamsOnly 이외의 모드를 할당할 수 없습니다. 즉, 다음을 의미합니다.

 - 온-프레미스 비즈니스용 Skype 서버 없는 새 사용자에게 라이선스를 부여하면 테넌트의 TeamsUpgradePolicy 글로벌 정책에 관계없이 TeamsOnly 모드가 자동으로 할당됩니다.
 - 하이브리드 조직에서는 온-프레미스에 있는 사용자를 클라우드로 이동할 때 스위치가 지정되었는지 여부에 `MoveToTeams` 관계없이 TeamsOnly 모드가 자동으로 할당됩니다 `Move-CsUser`.
 - 클라우드에 있는 사용자는 TeamsOnly 이외의 모드를 할당할 수 없습니다. 온라인이 있는 사용자는 온-프레미스에서 비즈니스용 Skype 서버를 사용하지 *않습니다*.

남은 사용자가 비즈니스용 Skype Online에 있지만 아직 TeamsOnly 모드가 할당되지 않은 고객은 가능한 한 빨리 TeamsOnly 모드를 이러한 사용자에게 할당해야 합니다. 또한 Microsoft는 TeamsOnly 모드가 아닌 비즈니스용 Skype Online 사용자를 위한 보조 업그레이드를 제공합니다. 지원 업그레이드 환경은 조직이 순수 온라인 조직인지 아니면 온-프레미스 비즈니스용 Skype 사용자가 있는 조직인지에 따라 달라집니다. 자세한 내용은 [비즈니스용 Skype Online에서 Microsoft Teams로의 보조 업그레이드를 참조하세요](upgrade-assisted.md). 지원 업그레이드가 완료되면 모든 *온라인* 사용자가 TeamsOnly 모드로 전환됩니다. *온-프레미스에 있는 모든 사용자는 온-프레미스에 남아 있으며 TeamsOnly가 되지 않습니다*.

TeamsOnly 모드의 사용자는 Teams에서 들어오는 채팅 및 전화를 받고 Teams에서 모임을 예약합니다. 비즈니스용 Skype Online에서는 채팅이나 통화를 시작하거나 모임을 예약할 수 없습니다. TeamsOnly 사용자는 이미 가지고 있거나 나중에 받은 비즈니스용 Skype 모임에 참가할 수 있습니다. 그러나 Microsoft가 지정된 TeamsOnly 사용자에 대한 비즈니스용 Skype Online 인프라를 제거한 후에 TeamsOnly 사용자는 익명으로만 비즈니스용 Skype 모임에 참가할 수 있습니다.  2022년 6월 30일부터 새로 만든 TeamsOnly 사용자는 더 이상 비즈니스용 Skype Online 인프라로 프로비전되지 않으므로 비즈니스용 Skype 모임에 초대된 경우 익명으로 참가해야 합니다. 마찬가지로 하이브리드 조직에서 온-프레미스에서 Teams로 이동한 사용자는 2022년 10월부터 비즈니스용 Skype Online 인프라로 더 이상 프로비전되지 않습니다. 이러한 사용자가 비즈니스용 Skype 모임에 초대된 경우 익명으로 참가해야 합니다.


## <a name="guidance-for-organizations-with-on-premises-deployments-of-skype-for-business-server"></a>비즈니스용 Skype 서버 온-프레미스 배포를 사용하는 조직에 대한 지침

 - 온-프레미스 Active Directory 환경에서 새 사용자를 만들 때 이러한 사용자가 Azure AD 동기화되고 Teams에 대한 라이선스를 부여하려는 경우 *이러한 사용자에게 라이선스를 할당하기 전에* **먼저 온-프레미스 비즈니스용 Skype 배포에서 사용하도록 설정하고 변경 내용이 클라우드에 동기화되었는지 확인해야 합니다. Azure AD 연결** 합니다.  Get-CsOnlineUser를 사용하여 변경 내용이 클라우드와 완전히 동기화되었는지 확인할 수 있습니다. 사용자의 HostingProvider= "SRV:"인 경우 변경 내용이 동기화되었습니다.  "sipfed.online.lync.com"해서는 안 됩니다.   

 - Microsoft가 2022년 10월부터 하이브리드 조직을 위한 레거시 비즈니스용 Skype Online 인프라를 제거하면 TeamsOnly 사용자는 익명으로 비즈니스용 Skype 모임에 참가해야 합니다.  자세한 내용은 [사용 중지 후 예상되는 사항을 참조하세요](#what-to-expect-post-retirement). 또는 조직의 모든 사용자(온-프레미스 또는 Teams만)가 예약한 모임이 Teams 모임인지 확인할 수 있습니다. 그러면 조직의 모든 사용자(정책 구성에 따라)에 대해 인증된 모임 참가가 가능합니다. 이를 위해 다음 작업을 수행합니다.
   - **Teams 협업** 모드를 **사용하여 비즈니스용 Skype 전용** 또는 비즈니스용 Skype 할당된 모든 사용자의 경우 공존 모드를 **Teams 공동 작업 및 모임에 비즈니스용 Skype 변경합니다**.  이 모드는 사용자가 예약한 새 모임이 비즈니스용 Skype 모임 대신 Teams 모임이 되는 것을 제외하고 다른 두 모임과 동일한 기능을 제공합니다. 이 모드를 테넌트 수준과 달리 사용자에게 직접 할당하면 기본적으로 모든 비즈니스용 Skype 모임을 해당 사용자가 구성한 Teams 모임으로 자동 변환합니다.
   - 아일랜드 모드에 있는 사용자의 경우 PreferredMeetingProviderForIslandsMode=Teams를 사용하여 TeamsMeetingPolicy 인스턴스를 할당하여 Teams에서 모임을 항상 예약하도록 요구할 수 있습니다. 
   - 기존 비즈니스용 Skype 모임이 Teams 모임으로 변환되도록 하려면(예: 아일랜드 사용자가 있는 경우) Start-CsExMeetingMigration 사용하여 [모임 마이그레이션 서비스를](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms.md#trigger-meeting-migration-manually-via-powershell-cmdlet) 트리거하여 사용자의 모임을 Teams로 변환할 수 있습니다.
  

## <a name="actions-to-take-before-june-30-2022"></a>2022년 6월 30일 이전에 수행할 작업
비즈니스용 Skype Online이 사용 중지되었으므로 Microsoft는 2022년 6월 30일까지 지원 인프라의 서비스 해제를 시작합니다.  모든 버전의 비즈니스용 Skype 업그레이드된 TeamsOnly 사용자가 있는 조직의 경우 다음 상황 중 하나가 적용되는 경우 조치를 취해야 합니다.

- 비즈니스용 Skype 연락처가 있고 업그레이드된 이후 Teams에 아직 로그인하지 않은 TeamsOnly 사용자가 있는 경우 
- TeamsOnly로 업그레이드하기 전에 구성한 비즈니스용 Skype Online 모임이 있는 TeamsOnly 사용자가 있는 경우

이러한 상황 중 하나가 조직에 적용되는 경우 아래 설명된 대로 2022년 6월 30일까지 조치를 취해야 합니다.

 - **비즈니스용 Skype 온라인 연락처:** 사용자가 TeamsOnly 모드로 업그레이드된 후 사용자가 Teams에 처음으로 로그온하면 해당 사용자의 비즈니스용 Skype Online 계정에 있는 모든 기존 연락처가 Teams로 마이그레이션됩니다. Microsoft가 비즈니스용 Skype Online 인프라를 제거한 후에 *는 Teams에 아직 로그온하지 않은 사용자의* 연락처를 더 이상 마이그레이션할 수 없습니다. 비즈니스용 Skype 연락처를 Teams로 마이그레이션하려면 이전에 비즈니스용 Skype 모든 사용자가 2022년 6월 30일 이전에 Teams에 한 번 이상 로그온하는 것이 좋습니다.

 - **비즈니스용 Skype 온라인 모임:** 조직이 TeamsOnly로 업그레이드된 후 사용자는 모든 새 모임을 Teams 모임으로 만듭니다. 경우에 따라 TeamsOnly 사용자는 이전에 구성한 비즈니스용 Skype 온라인 모임이 있을 수 있습니다. 현재 업그레이드된 TeamsOnly 사용자 및 초대된 참석자는 비즈니스용 Skype 클라이언트를 사용하여 이러한 비즈니스용 Skype Online 모임에 참가할 수 있습니다. 그러나 Microsoft가 지정된 TeamsOnly 사용자에 대한 비즈니스용 Skype Online 인프라를 제거한 후에는 해당 사용자가 비즈니스용 Skype 모임에 익명으로만 참가할 수 있으며, *해당 사용자가 구성한* 나머지 비즈니스용 Skype Online 모임은 더 이상 존재하지 않습니다. 이끌이와 참석자는 이러한 모임에 참가할 수 없습니다. TeamsOnly 조직의 사용자가 조직한 나머지 비즈니스용 Skype Online 모임이 있는 경우 Microsoft는 이러한 모임의 일정을 Teams 모임으로 다시 예약하는 것이 좋습니다. 또는 관리자는 [모임 마이그레이션 서비스를](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms#trigger-meeting-migration-manually-via-powershell-cmdlet) 사용하여 이러한 모임을 Teams 모임으로 변환할 수 있습니다. 두 경우 모두 2022년 6월 30일까지 이러한 작업을 완료합니다.  


## <a name="how-microsoft-is-helping-customers-upgrade-to-teams"></a>Microsoft가 고객이 Teams로 업그레이드할 수 있도록 돕는 방법

현재 비즈니스용 Skype Online에서 Teams로 업그레이드를 시작하는 것이 좋습니다. Teams 배포를 계획하고 비즈니스용 Skype 업그레이드하는 데 사용할 수 있는 리소스를 활용합니다.

- [Teams 배포 및 업그레이드 설명서](upgrade-start-here.md) – IT 관리자를 위한 무료 기술 지침입니다.

- [Teams 업그레이드 계획 워크샵](./upgrade-workshops-landing-page.yml) - 무료 대화형 업그레이드 계획 워크샵으로, Teams로의 업그레이드를 계획하고 구현하는 데 도움이 되도록 설계된 지침, 모범 사례 및 리소스를 받게 됩니다.

- [비즈니스용 Skype Online에서 Microsoft Teams로의 보조 업그레이드](upgrade-assisted.md) - 비즈니스용 Skype Online 사용자를 Teams로 업그레이드하는 데 도움이 되는 자동화된 프로그램입니다.

- [Microsoft 365용 FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) – 적격 플랜에 사용할 수 있는 Teams 배포 지원.

- [Teams 라이브 교육](./instructor-led-training-teams-landing-page.yml) – Teams를 사용하여 조직을 시작하고 실행하도록 설계된 무료 온라인 교육 클래스입니다.

- [Teams 분필 회담 – Teams](./chalk-talks-landing-page.yml) 의 주요 시나리오에 대한 모범 사례를 설명하는 IT 전문가 및 의사 결정자를 위한 무료 온라인 워크샵입니다.

- [Microsoft 파트너](https://www.microsoft.com/solution-providers/home) – Microsoft 솔루션 공급자는 Teams를 최대한 활용하는 데 도움을 줄 수 있습니다.

- [Microsoft Teams 블로그](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/bg-p/MicrosoftTeamsBlog) – 새로운 기능, 채택 및 사용량 리소스, Teams 디바이스 및 기타 비즈니스 애플리케이션과의 통합에 대한 Teams 뉴스입니다.

현재 비즈니스용 Skype Online 고객인 경우 지금 Teams로의 업그레이드 계획을 시작하세요. 강력한 커뮤니케이션 및 공동 작업 기능을 경험하게 되어 기쁘게 생각하고 있으며, 이 과정에서 도움을 제공하기 위해 최선을 다하고 있습니다.  비즈니스용 Skype Online 사용 중지에 대한 자세한 내용은 [FAQ(비즈니스용 Skype에서 Microsoft Teams로 업그레이드](FAQ-journey.yml))를 참조하세요.





