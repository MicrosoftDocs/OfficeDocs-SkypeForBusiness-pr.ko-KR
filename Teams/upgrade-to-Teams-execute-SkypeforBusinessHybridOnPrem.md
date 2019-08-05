---
title: 비즈니스용 Skype 하이브리드 또는 온-프레미스 배포에서 팀으로 업그레이드-Microsoft 팀
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 비즈니스용 Skype 하이브리드 또는 온-프레미스 배포에서 팀으로 업그레이드 하기 위한 고려 사항
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 731a6b30fe2476d180198e88f83e80f24c8e8227
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "36185219"
---
![여행 다이어그램 업그레이드, 배포 및 구현 강조] (media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계")

이 문서는 업그레이드 여행 배포 및 구현 단계의 일부입니다. 계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.

-   [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)
-   [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
-   [비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해](https://aka.ms/SkypeToTeams-Coexist)
-   [업그레이드 여행 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [환경 준비](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [조직 준비](https://aka.ms/SkypeToTeams-UserReadiness)
-   [파일럿 수행](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>비즈니스용 Skype 하이브리드 또는 온-프레미스 배포에서 팀으로 업그레이드

비즈니스용 Skype 또는 Microsoft Lync 온-프레미스를 배포 하 고 조직이 여러 공존 모드를 사용 하 여 선택적으로 팀으로 업그레이드 하려는 경우이 문서의 지침을 따르세요. 첫 번째 단계는 Office 365 테 넌 트와 하이브리드 연결을 설정한 다음 사용자를 비즈니스용 Skype Online으로 이동 하 고 적절 한 공존 및 업그레이드 모드를 할당 하는 것입니다. 

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021 년 7 월 31 일에 만료 되며, 그 이후에는 더 이상 접근성 또는 지원 되지 않습니다. 조직의 혜택 실현을 최대화 하 고 업그레이드를 구현 하는 데 적절 한 시간을 확보 하려면 지금 Microsoft 팀으로 여행을 시작 하는 것이 좋습니다. 성공적으로 업그레이드 하면 기술 및 사용자의 준비가 정렬 되므로 Microsoft 팀으로 여행을 이동할 때이 가이드의 지침을 활용 해야 합니다.

## <a name="step-1-deploy-hybrid-connectivity"></a>1 단계: 하이브리드 연결 배포 

사용자를 팀으로 업그레이드 하기 위한 주요 전제 조건은 하이브리드 연결을 배포 하는 것입니다. 여기에는 기존 비즈니스용 Skype 또는 Lync 배포에 새 외부 연결을 배포 하거나 Office 365 테 넌 트에서 하이브리드 관계를 구성 하는 작업이 포함 될 것입니다. 

자세한 내용은 비즈니스용 [Skype 서버와 비즈니스용 Skype Online 간 하이브리드 연결 배포](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)를 참조 하세요.

## <a name="step-2-move-users-to-skype-for-business-online"></a>2 단계: 비즈니스용 Skype Online으로 사용자 이동 

하이브리드 설정을 완료 한 후에는 비즈니스용 Skype Online으로 사용자를 이동 합니다. 

자세한 내용은 [온-프레미스에서 비즈니스용 Skype Online으로 사용자 이동을](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)참조 하세요. 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>3 단계: 공존 및 업그레이드 모드 지정

사용자를 비즈니스용 Skype Online으로 이동한 후에는 조직이 선택한 업그레이드의 여행에 따라 적절 한 공존 모드를 할당할 수 있습니다. 자세한 내용은 [공존 및 업그레이드 설정](https://aka.ms/SkypeToTeams-SetCoexistence) 및 TeamsUpgradePolicy 설정 ( [마이그레이션 및 공존 관리](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence))을 참조 하세요.

> [!NOTE]
> 비즈니스용 skype 서버 2019 및 향후 비즈니스용 Skype Server 2015의 누적 업데이트를 사용 하 여 2 단계 (비즈니스용 Skype Online으로 사용자 이동)와 3 단계 (사용자를 팀으로 업그레이드)를 한 번에 수행할 수 있습니다. 자세한 내용은 비즈니스용 Skype 서버 2019이 출시 된 후에 제공 됩니다.

## <a name="phone-system-and-teams-upgrade"></a>전화 시스템 및 팀 업그레이드

Skype for Business 하이브리드 배포를 통화 요금제를 사용 하는 전화 시스템으로 전환 하는 경우, Microsoft는 전화 번호 포팅를 완료 했다고 가정 하 고, 사용자를 업그레이드 하는 경우 팀은 인바운드 PSTN 통화를 팀으로 자동 전환 합니다.

통화 요금제를 사용할 수 없는 경우에는 엔터프라이즈 음성 배포를 Microsoft 전화 시스템 다이렉트 라우팅으로 전환 해야 합니다. 사용자를 팀으로 업그레이드 하려면 [전화 시스템 다이렉트 라우팅에 대 한 추가 고려 사항을](2-envision-make-my-service-decisions-direct-routing.md)참조 하세요.
