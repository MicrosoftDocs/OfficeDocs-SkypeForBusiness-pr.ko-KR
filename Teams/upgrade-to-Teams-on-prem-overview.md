---
title: 비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드-Microsoft 팀
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype에서 Teams로 업그레이드
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 528dcfd975616d213b8a9fbd2499dc5d798708b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533585"
---
# <a name="upgrade-from-skype-for-business-to-teams-mdash-for-it-administrators"></a>비즈니스용 Skype에서 IT 관리자를 위한 팀으로 업그레이드 &mdash;

## <a name="overview"></a>개요

비즈니스용 Skype에서 팀으로 업그레이드할 때 일부 조직에서는 IT 부서가 계획 하 고 관리 하는 점진적 롤아웃을 필요로 합니다. 이 섹션의 문서는 주로 대규모 조직의 IT 관리자에 게 적용 됩니다. 이러한 조직은 일반적으로 온-프레미스 이며, 대규모 비즈니스용 Skype Online 조 직 일 수도 있습니다. 이 문서를 읽기 전에 먼저 [팀 업그레이드](upgrade-start-here.md) 와 [업그레이드 프레임 워크에 대 한 자세한](upgrade-framework.md)내용을 참조 하세요.


조직의 업그레이드 프로세스를 안내 하는 문서는 다음과 같습니다. 

- [업그레이드 방법](upgrade-to-teams-on-prem-upgrade-methods.md)
- [업그레이드 관리 도구](upgrade-to-teams-on-prem-tools.md)
- [비즈니스용 Skype 온-프레미스를 사용 하는 조직에 대 한 추가 고려 사항](upgrade-to-teams-on-prem-considerations.md)
- [업그레이드 수행](upgrade-to-teams-on-prem-implement.md)
- [PSTN (공개 통신 네트워크) 고려 사항](upgrade-to-teams-on-prem-pstn-considerations.md)

또한 다음 문서에서는 중요 한 업그레이드 개념 및 공존 동작에 대해 설명 합니다.

- [팀과 비즈니스용 Skype의 공존](upgrade-to-teams-on-prem-coexistence.md)
- [공존 모드-참조](migration-interop-guidance-for-teams-with-skype.md)
- [Teams 클라이언트 환경 및 공존 모드 준수](teams-client-experience-and-conformance-to-coexistence-modes.md)

>[!NOTE]
>이 문서는 비즈니스용 Skype Online, 비즈니스용 Skype Server 온-프레미스, 비즈니스용 Skype를 사용 합니다. 후자의 용어는 온라인 및 온-프레미스 버전을 모두 의미 합니다.

시작 하기 전에, 팀으로 마이그레이션한 사용자가 비즈니스용 Skype에서 호스트 된 모임에 참가 하는 것 외에는 비즈니스 클라이언트를 더 이상 사용 하지 않는다는 점에 유의 하세요.  발신자가 팀과 비즈니스용 Skype를 사용 하는지 여부에 관계 없이 사용자의 팀 클라이언트에 있는 모든 수신 채팅 및 통화입니다. 마이그레이션된 사용자가 구성한 모든 새 모임은 팀 모임으로 예약 됩니다. 사용자가 비즈니스용 Skype 클라이언트를 사용 하려고 시도 하는 경우 채팅 및 통화에 대 한 시작이 차단 됩니다.  그러나 사용자는 비즈니스용 Skype 클라이언트를 사용 하 여 초대 받은 비즈니스용 Skype 모임에 참가할 수 있습니다. (2017 이전에 출시 된 이전 비즈니스용 Skype 클라이언트는 TeamsUpgradePolicy를 준수 하지 않습니다. 최신 비즈니스용 Skype 클라이언트를 사용 하 고 있는지 확인 합니다.
 
[TeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)의 속성인 [mode](migration-interop-guidance-for-teams-with-skype.md)개념을 사용 하 여 팀으로 사용자의 전환을 관리 합니다. 위에 설명 된 대로 팀으로 마이그레이션한 사용자는 "TeamsOnly" 모드에 있습니다.  팀으로 마이그레이션하는 조직의 경우 궁극적인 목표는 모든 사용자를 TeamsOnly 모드로 이동 하는 것입니다.

>[!NOTE]
>비즈니스용 Skype 온-프레미스 계정이 있는 사용자는 TeamsOnly 일 수 없습니다. 이러한 사용자는 [아일랜드 모드에서 팀을 사용할](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)수 있지만,이는 TeamsOnly 모드에서 사용할 수 있는 전체 팀 기능 집합을 제공 하지 않습니다. 이러한 사용자를 팀에 게만 자신 있게 하려면 온 `Move-CsUser` -프레미스 비즈니스용 Skype 서버 도구를 사용 하 여 클라우드로 이동 해야 합니다.

그래. 시작 하겠습니다.  첫 번째 단계는 [사용할 수 있는 업그레이드 방법을 이해 하](upgrade-to-teams-on-prem-upgrade-methods.md)는 것입니다.







   

## <a name="related-links"></a>관련 링크

[비즈니스용 Skype로 팀을 함께 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md) 

[비즈니스용 Skype 서버와 Microsoft 365 또는 Office 365 간 하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[온-프레미스와 클라우드 간에 사용자 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md)

[부여-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[MMS (모임 마이그레이션 서비스) 사용](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

