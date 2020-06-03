---
title: 비즈니스용 Skype 하이브리드 배포를 팀에 업그레이드
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 비즈니스용 Skype 하이브리드 배포에서 조직을 Microsoft 팀으로 업그레이드 하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: a9cc76313bb65a79241e26ab70a38d8698f27e7c
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523441"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>비즈니스용 Skype 하이브리드 배포에서 팀으로 업그레이드

![배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계")

이 문서는 업그레이드 여행 배포 및 구현 단계의 일부입니다. 계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.

- [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
- [비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해](https://aka.ms/SkypeToTeams-Coexist)
- [업그레이드 여행 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [조직 준비](https://aka.ms/SkypeToTeams-UserReadiness)
- [파일럿 수행](https://aka.ms/SkypeToTeams-Pilot)

비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포 하 고 Office 365 조직에 하이브리드 배포로 구성한 경우, 조직에서 여러 공존 모드를 사용 하 여 선택적으로 팀으로 업그레이드 하려는 경우이 문서의 지침을 따르세요. 업그레이드 여행 중에는 사용자를 비즈니스용 Skype Online으로 이동 (아직 온라인 상태가 되지 않은 경우) 한 다음 적절 한 공존 및 업그레이드 모드를 할당 해야 합니다.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>1 단계: 비즈니스용 Skype Online으로 사용자 이동

이 단계는 현재 온-프레미스 상태인 사용자에 게 적용 됩니다. 이러한 사용자를 비즈니스용 Skype Online으로 이동 하는 방법에 대 한 자세한 내용은 온 [-프레미스에서 비즈니스용 Skype online으로 사용자 이동을](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)참조 하세요.

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>2 단계: 공존 및 업그레이드 모드 할당

사용자를 비즈니스용 Skype Online으로 이동한 후에는 조직이 선택한 업그레이드의 여행에 따라 적절 한 공존 모드를 할당할 수 있습니다. 자세한 내용은 [공존 및 업그레이드 설정](https://aka.ms/SkypeToTeams-SetCoexistence) 및 TeamsUpgradePolicy 설정 ( [마이그레이션 및 공존 관리](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence))을 참조 하세요.

> [!NOTE]
> 비즈니스용 skype 서버 2019 및 향후 비즈니스용 Skype Server 2015의 누적 업데이트는 1 단계 (비즈니스용 Skype Online으로 사용자 이동)와 2 단계 (사용자를 팀으로 업그레이드)를 수행 하 여 한 번에 수행할 수 있게 됩니다. 자세한 내용은 비즈니스용 Skype 서버 2019이 출시 된 후에 제공 됩니다.

## <a name="phone-system-and-teams-upgrade"></a>전화 시스템 및 팀 업그레이드

Skype for Business 하이브리드 배포를 통화 요금제로 전화 시스템으로 전환 하는 경우, Microsoft는 전화 번호 포팅를 완료 했다고 가정 하 고, 사용자를 팀으로 업그레이드 하면 자동으로 인바운드 PSTN 통화가 팀으로 전환 됩니다.

통화 요금제를 사용할 수 없거나 기존 PSTN 연결 공급자를 사용 하려는 경우 엔터프라이즈 음성 배포 또는 기존 온-프레미스 배포 또는 클라우드 커넥터 에디션을 사용 하는 하이브리드 음성 배포를 Microsoft 전화 시스템 다이렉트 라우팅으로 전환 해야 합니다. 사용자를 팀으로 업그레이드 하려면 [전화 시스템 다이렉트 라우팅에 대 한 추가 고려 사항을](2-envision-make-my-service-decisions-direct-routing.md)참조 하세요.
