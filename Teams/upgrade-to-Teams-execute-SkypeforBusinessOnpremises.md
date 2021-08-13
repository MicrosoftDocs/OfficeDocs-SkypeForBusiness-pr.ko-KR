---
title: 비즈니스용 Skype 온-프레미스를 Teams로 업그레이드
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 조직을 프레미스 Microsoft Teams 배포에서 비즈니스용 Skype 방법을 설명합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1bf5529cf37ca3217c5af0411a1d12f0e752c583cb869273f9ba5b068d5633da
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298998"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>비즈니스용 Skype 배포에서 Teams

![배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계")

이 문서는 업그레이드 여정의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 작업을 완료한지 확인합니다.

- [프로젝트 관계자 인리스트](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](./upgrade-define-project-scope.md)
- [비즈니스용 Skype 및 상호운용성을 Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [업그레이드 여정을 선택했습니다.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](./upgrade-prepare-environment.md)
- [조직 준비](./upgrade-prepare-organization.md)
- [파일럿 수행](./pilot-essentials.md)

이 문서의 지침에 따라 비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포하고 조직에서 여러 공존 모드 또는 올인을 사용하여 선택적으로 Microsoft Teams 업그레이드하려는 경우 이 문서의 지침을 따르고 있습니다. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>1단계: 하이브리드 연결 배포

사용자를 업그레이드하기 위한 주요 구성 Teams 하이브리드 연결을 배포하는 것입니다.

자세한 내용은 온라인 및 비즈니스용 Skype 서버 비즈니스용 Skype [참조하세요.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>2단계: 조직에 대해 선택한 업그레이드 여정 구현

하이브리드 설정을 완료한 후 사용자를 Microsoft 365 또는 Office 365.

자세한 내용은 다음을 참조하세요.

- [TeamsUpgradePolicy: 마이그레이션](upgrade-to-teams-on-prem-tools.md)및 공존 관리.

- 사용자를 프레미스에서 온라인 [비즈니스용 Skype 이동합니다.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>전화 시스템 및 Teams 업그레이드

프레미스 전화 시스템에서 Teams 직접 라우팅("직접 라우팅") 또는 Microsoft에서 제공하는 전화 전화 시스템 또는 전화 통화 계획을 활용할 수 Microsoft 365 Office 365.

통화 계획을 사용하지 않는 경우 업그레이드의 일부로 엔터프라이즈 음성 배포를 전화 시스템 직접 라우팅으로 전환해야 Teams.

자세한 내용은 직접 라우팅 에 대한 전화 시스템 [고려 사항을 참조하세요.](./direct-routing-landing-page.md) 통화 요금제 사용을 계획하는 경우 전화 번호를 로 전송하기 위한 지침을 [Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)