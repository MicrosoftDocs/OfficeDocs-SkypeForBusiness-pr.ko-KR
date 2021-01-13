---
title: 비즈니스용 Skype 온-프레미스를 Teams로 업그레이드
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype-프레미스 배포에서 조직을 Microsoft Teams로 전환하는 방법을 배워보는 것이 좋습니다.
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
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820948"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>비즈니스용 Skype-프레미스 배포에서 Teams로 업그레이드

![배포 및 구현 단계에 강조를 두는 업그레이드 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 강조를 두는 업그레이드 단계")

이 문서는 업그레이드 여정의 배포 및 구현 단계의 일부입니다. 계속하기 전에 다음 활동을 완료해야 합니다.

- [프로젝트 이해 관계자에 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 Teams의 공존성 및 상호 연동성 이해](https://aka.ms/SkypeToTeams-Coexist)
- [업그레이드 여정 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [조직 준비](https://aka.ms/SkypeToTeams-UserReadiness)
- [파일럿 수행](https://aka.ms/SkypeToTeams-Pilot)

비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포하고 조직에서 여러 공존 모드를 사용하여 선택적으로 또는 모든 기능을 사용하여 Microsoft Teams로 업그레이드하려는 경우 이 문서의 지침을 따르하세요. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>1단계: 하이브리드 연결 배포

사용자를 Teams로 업그레이드하기 위한 주요 구성은 하이브리드 연결을 배포하는 것입니다.

자세한 내용은 비즈니스용 Skype Server와 비즈니스용 Skype Online 간에 하이브리드 연결 [배포를 참조하세요.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>2단계: 조직에 대해 선택한 업그레이드 여정 구현

하이브리드 설정을 완료한 후 사용자를 Microsoft 365 또는 Office 365로 이동할 계획입니다.

자세한 내용은 다음을 참조하세요.

- [TeamsUpgradePolicy: 마이그레이션](upgrade-to-teams-on-prem-tools.md)및 공존 관리.

- [사용자를 비즈니스용 Skype Online으로 프레미스에서 이동](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>전화 시스템 및 Teams 업그레이드

전화 시스템 다이렉트 라우팅("직접 라우팅") 또는 Microsoft에서 제공한 Microsoft 365 또는 Office 365 통화 요금제의 장점을 활용할 수 있습니다.

통화 계획을 사용하지 않는 경우 Teams로 업그레이드하는 동안 엔터프라이즈 음성 배포를 전화 시스템 직접 라우팅으로 전환해야 합니다.

자세한 내용은 전화 시스템 직접 라우팅에 대한 추가 [고려 사항을 참조하세요.](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing) 통화 요금제 사용을 계획하는 경우 전화 번호를 Teams로 이전하기 위한 지침을 [참조하세요.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)