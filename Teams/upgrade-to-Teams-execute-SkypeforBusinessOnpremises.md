---
title: 비즈니스용 Skype 온-프레미스를 Microsoft 팀으로 업그레이드 | 배포 | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드 하기 위한 고려 사항
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f234c6fe959d35d2f92e117e28af8d15f0a02819
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235904"
---
![배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계] (media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계")

이 문서는 업그레이드 여행 배포 및 구현 단계의 일부입니다. 계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.

- [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해](https://aka.ms/SkypeToTeams-Coexist)
- [업그레이드 여행 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [조직 준비](https://aka.ms/SkypeToTeams-UserReadiness)
- [파일럿 수행](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드

비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포 하 고 조직에서 Microsoft 팀으로 업그레이드 하려는 사용자가 여러 공존 모드를 사용 하거나 모두 하는 경우에는이 문서의 지침을 따르세요. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>1 단계: 하이브리드 연결 배포

사용자를 팀으로 업그레이드 하기 위한 주요 전제 조건은 하이브리드 연결을 배포 하는 것입니다.

자세한 내용은 비즈니스용 [Skype 서버 간 하이브리드 연결 배포 및 비즈니스용 Skype Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) 을 참조 하세요.

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>2 단계: 조직에 대해 선택한 업그레이드 여행 구현

하이브리드 설정을 완료 한 후 사용자를 Office 365으로 이동 하도록 계획할 수 있습니다.

자세한 내용은 다음을 참조 하세요.

- [TeamsUpgradePolicy: 마이그레이션 및 공존 관리](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

- [온-프레미스에서 비즈니스용 Skype Online으로 사용자를 이동](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)합니다.

## <a name="phone-system-and-teams-upgrade"></a>전화 시스템 및 팀 업그레이드

온-프레미스 전화 시스템에서 팀으로 전환 하면 전화 시스템 다이렉트 라우팅 ("직접 라우팅") 또는 Office 365에 대 한 Microsoft 제공 전화 요금제를 활용할 수 있습니다.

Office 365에서 통화 요금제를 사용 하 고 있지 않은 경우에는 팀으로 업그레이드 하는 과정의 일부로 서 엔터프라이즈 음성 배포를 전화 시스템 다이렉트 라우팅으로 전환 해야 합니다.

자세한 내용은 [전화 시스템 다이렉트 라우팅에 대 한 추가 고려 사항을](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)참조 하세요. Office 365에서 통화 계획을 사용 하려는 경우 [office 365에 전화 번호를 전송](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365)하는 지침을 참조 하세요.