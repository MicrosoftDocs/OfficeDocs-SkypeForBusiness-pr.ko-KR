---
title: 비즈니스용 Skype 하이브리드 배포를 Teams로 업그레이드
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype 하이브리드 배포에서 Microsoft Teams로 조직을 업그레이드하는 방법을 배워야 합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802348"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>비즈니스용 Skype 하이브리드 배포에서 Teams로 업그레이드

![배포 및 구현 단계에 강조를 두는 업그레이드 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 강조를 두는 업그레이드 단계")

이 문서는 업그레이드 여정의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 활동을 완료해야 합니다.

- [프로젝트 관련자에 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 Teams의 공존 및 상호 연동성 이해](https://aka.ms/SkypeToTeams-Coexist)
- [업그레이드 여정 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [조직 준비](https://aka.ms/SkypeToTeams-UserReadiness)
- [파일럿 수행](https://aka.ms/SkypeToTeams-Pilot)

비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포하고 Microsoft 365 또는 Office 365 조직과의 하이브리드 배포에서 구성한 경우 조직에서 여러 공존 모드 또는 모든 기능을 사용하여 선택적으로 Teams로 업그레이드하려는 경우 이 문서의 지침을 따르하세요. 업그레이드 여정의 경우 사용자를 비즈니스용 Skype Online(아직 온라인에 없는 경우)으로 이동한 다음 적절한 공존 및 업그레이드 모드를 할당해야 합니다.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>1단계: 비즈니스용 Skype Online으로 사용자 이동

이 단계는 현재 홈이 있는 On-프레미스 사용자에게 적용됩니다. 이러한 사용자를 비즈니스용 Skype Online으로 이동하는 자세한 내용은 사용자를 -프레미스에서 비즈니스용 [Skype Online으로 이동을 참조하세요.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>2단계: 공존 및 업그레이드 모드 할당

사용자를 비즈니스용 Skype Online으로 이동한 후 조직에서 선택한 업그레이드 여정에 따라 적절한 공존 모드를 할당할 수 있습니다. 자세한 내용은 마이그레이션 [](https://aka.ms/SkypeToTeams-SetCoexistence) 및 공존 관리와 같은 공존 및 업그레이드 설정 및 [TeamsUpgradePolicy 설정을 참조하세요.](upgrade-to-teams-on-prem-tools.md)

> [!NOTE]
> 비즈니스용 Skype Server 2019 및 향후 비즈니스용 Skype Server 2015 누적 업데이트를 사용하면 1단계(사용자를 비즈니스용 Skype Online으로 이동) 및 2단계(사용자를 Teams로 업그레이드)를 한 단계로 수행할 수 있습니다. 비즈니스용 Skype Server 2019가 출시된 후 자세한 정보가 제공됩니다.

## <a name="phone-system-and-teams-upgrade"></a>전화 시스템 및 Teams 업그레이드

비즈니스용 Skype 하이브리드 배포를 통화 요금제로 전화 시스템으로 전환하는 경우 Microsoft는 PSTN(공용 전화망) 공급자가 되며 전화 번호 포터링을 완료했다고 생각하면 사용자를 Teams로 업그레이드하면 자동으로 인바운드 PSTN 통화가 Teams로 전환됩니다.

통화 계획을 사용할 수 없는 경우 또는 기존 PSTN 연결 공급자를 사용하려는 경우 엔터프라이즈 음성 배포 또는 기존 On-프레미스 배포 또는 Cloud Connector Edition을 사용하는 하이브리드 음성 배포를 Microsoft Phone System 직접 라우팅으로 전환해야 합니다. 사용자를 Teams로 업그레이드하려면 전화 시스템 직접 라우팅에 대한 추가 고려 [사항을 참조합니다.](2-envision-make-my-service-decisions-direct-routing.md)
