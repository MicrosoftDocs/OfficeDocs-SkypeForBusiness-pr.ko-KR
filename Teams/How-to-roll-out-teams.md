---
title: Microsoft Teams를 배포하는 방법
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dstrome
audience: admin
description: 한 번에 롤아웃하거나 단계적으로 시작하여 조직에 Microsoft Teams를 성공적으로 구현할 수 있는 과정을 계획하세요.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.rolloutteams
- seo-marvel-mar2020
- seo-marvel-may2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d55f9d0ce9d3a7668abb6c02435acaa83a06324
ms.sourcegitcommit: 4dd8a326a7284872f0d14e0a61bd4fcbe2297c10
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071759"
---
# <a name="how-to-roll-out-microsoft-teams"></a>Microsoft Teams를 배포하는 방법

## <a name="start-here"></a>여기에서 시작
소규모 기업 혹은 다국적 기업인지 여부에 상관없이 [시작하기](get-started-with-teams-quick-start.md)에서 Teams 배포를 시작합니다. 소규모 기업의 경우이거나 **원격 작업자** 를 지원하기 위해 빠르게 Teams를 최초 Microsoft 365 혹은 Office 365 워크로드로 배포하는 경우에 필요한 모든 사항일 수 있는 소규모 Teams 배포에 대해 처음부터 과정을 안내합니다. 대규모 조직의 경우, [시작하기](get-started-with-teams-quick-start.md)를 사용하여 Teams를 소규모의 얼리어답터와 시험하여 Teams에 대해 자세히 알아보고 조직 전체 배포를 계획하기 시작할 수 있도록 합니다. 

## <a name="recommended-path-to-teams"></a>Teams에 대한 권장 경로


조직이 준비되면 Teams를 워크로드별로 단계적으로 배포할 것을 권장합니다. **한 단계를 마치고 다음 단계로 넘어갈 때까지 기다릴 필요가 없습니다.** 일부 조직은 모든 Teams 기능을 한 번에 배포하고, 또 다른 조직은 단계적 접근 방식을 선호할 수 있습니다. Teams 워크로드를 다음 순서대로 배포할 것을 권장합니다.

- [시작하기](get-started-with-teams-quick-start.md)
- [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [모임 및 회의](deploy-meetings-microsoft-teams-landing-page.md)
- [클라우드 음성](cloud-voice-landing-page.md)

[채택 허브](adopt-microsoft-teams-landing-page.md): Teams 배포 전체에서 이러한 리소스를 활용하여 팀 채택을 촉진하세요.

![Teams 배포 경로를 보여주는 다이어그램](media/how-to-roll-out-teams-image1.png)


## <a name="if-youre-starting-from-skype-for-business-on-premises-or-hybrid-deployments"></a>비즈니스용 Skype, 온-프레미스 또는 하이브리드 배포에서 시작하는 경우

비즈니스용 Skype(온라인 또는 온-프레미스)에서 Teams를 배포하거나 하이브리드 구성이 필요한 경우, Teams를 배포하기 위해 위의 [권장 경로](#recommended-path-to-teams)를 따르기에 앞서 먼저 몇 가지 추가 계획을 수행해야 합니다. 아래 표에서 조직의 프로필에 적용되는 지침을 검토하고 시작합니다.



|  |조직의 프로필|지침  |
|---------|---------|---------|
|<IMG src="https://docs.microsoft.com/office/media/icons/migration-teams.svg" alt="Migration arrow symbol" height="50" width="50">|현재 비즈니스용 Skype Online을 사용하고 있으며 Teams로 이동할 준비가 되었습니다. |[Teams로 업그레이드](upgrade-start-here.md)로 이동합니다.        |
|<IMG SRC="https://docs.microsoft.com/office/media/icons/hybrid-teams.svg" alt="Hybrid symbol" height="50" width="50">|조직에서 비즈니스용 Skype 서버를 실행하고 있으며 Teams를 배포하려고 합니다. |대규모 Teams 배포의 경우, 먼저 온-프레미스 환경과 Microsoft 365 사이에 하이브리드 연결을 구성해야 합니다. [비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 계획](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity)을 읽고 시작합니다.<br><br>또한 [Teams로 업그레이드](upgrade-start-here.md)를 검토해야 합니다.   |
|<IMG src="https://docs.microsoft.com/office/media/icons/on-premises-teams.svg" alt="On premises symbol" height="50" width="50">|비즈니스용 Skype 서버는 없지만 온-프레미스 PSTN 솔루션이 있습니다. Teams를 배포하려고 하지만 온-프레미스 PSTN 솔루션을 유지하고 싶습니다. |위의 [권장 경로](#recommended-path-to-teams)에 따라 Teams를 배포하세요.<br><br>그런 다음 [직접 라우팅 계획](direct-routing-plan.md)을 읽고 전화 시스템 직접 라우팅을 사용하여 온-프레미스 PSTN 솔루션을 Teams와 연결하는 방법에 대해 알아보세요.|
|


