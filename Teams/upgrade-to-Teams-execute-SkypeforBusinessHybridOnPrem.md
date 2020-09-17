---
title: 비즈니스용 Skype 온-프레미스를 Teams로 업그레이드
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 비즈니스용 Skype 온-프레미스 배포에서 조직을 Microsoft 팀으로 업그레이드 하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: 0b63473dcb07c5fcac49902ced6d11777217a0c5
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940598"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>비즈니스용 Skype 온-프레미스에서 팀으로 업그레이드

![여행 다이어그램 업그레이드, 배포 및 구현 강조](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점을 두어 업그레이드 여행 단계")

이 문서는 업그레이드 여행 배포 및 구현 단계의 일부입니다. 계속 하기 전에 다음 활동을 완료 했는지 확인 합니다.

-   [프로젝트 이해 관계자 참여](upgrade-enlist-stakeholders.md)
-   [프로젝트 범위 정의](https://aka.ms/SkypetoTeams-Scope)
-   [비즈니스용 Skype 및 팀의 공존 성과 상호 운영성 이해](https://aka.ms/SkypeToTeams-Coexist)
-   [업그레이드 여행 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [환경 준비](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [조직 준비](https://aka.ms/SkypeToTeams-UserReadiness)
-   [파일럿 수행](https://aka.ms/SkypeToTeams-Pilot)

비즈니스용 Skype 서버 또는 Microsoft Lync 온-프레미스를 배포 하 고 조직에서 팀으로 업그레이드 하려는 경우이 문서의 지침을 따르세요. Microsoft 365 또는 Office 365 조직과 하이브리드 연결을 설정 하 고 사용자를 단계별로 팀으로 이동 하는 경우 공존 요구 사항을 결정 해야 합니다. 

> [!IMPORTANT]
> 비즈니스용 Skype Online은 2021년 7월 31일에 서비스가 종료되며 이후에는 더 이상 액세스할 수 없게 되거나 지원되지 않습니다. 조직의 혜택 실현을 최대화 하 고 업그레이드를 구현 하는 데 적절 한 시간을 확보 하려면 지금 Microsoft 팀으로 여행을 시작 하는 것이 좋습니다. 성공적으로 업그레이드 하면 기술 및 사용자의 준비가 정렬 되므로 Microsoft 팀으로 여행을 이동할 때이 가이드의 지침을 활용 해야 합니다.

## <a name="step-1-configure-hybrid-connectivity"></a>1 단계: 하이브리드 연결 구성 

온-프레미스 사용자를 팀으로 업그레이드 하기 위한 주요 전제 조건은 비즈니스용 Skype Server 온-프레미스 배포에 하이브리드 연결을 구성 하는 것입니다. 

먼저 [하이브리드 연결 계획](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) 을 읽고 [하이브리드 연결 구성](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)에 설명 된 작업을 수행 합니다.


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>2 단계: 전환 공존 모드 설정 (선택 사항)

비즈니스용 Skype 및 팀 간 공존 및 상호 운용성 클라이언트와 사용자는 팀 업그레이드 모드에서 정의 합니다.  기본적으로 조직은 사용자가 팀과 비즈니스용 Skype 클라이언트를 나란히 사용할 수 있도록 하는 군도 모드입니다.

팀으로 이동 하는 조직의 경우 각 사용자에 대 한 최종 대상, 즉 모든 사용자가 동시에 Teamonly (또는 다른 모드)를 할당 해야 하는 것은 아닙니다.

사용자가 팀의 유일한 모드에 도달 하기 전에, 조직에서 비즈니스용 Skype 공존 모드를 사용 하 여 필요한 경우 팀 전용 모드의 사용자와 아직 없는 사용자 간에 예측 가능한 의사 소통을 보장할 수 있습니다.  비즈니스용 skype 공존 모드 (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings)는 조직의 비즈니스용 Skype에서 팀으로 전환 하는 등 최종 사용자에 게 예측 가능한 간단한 환경을 제공 하는 데 목적이 있습니다. 

사용자가 비즈니스용 Skype 모드에 있는 경우 모든 수신 채팅 및 통화는 사용자의 비즈니스용 Skype 클라이언트로 라우팅됩니다. 사용자가 비즈니스용 Skype 모드에 있는 경우 최종 사용자의 혼란을 방지 하 고 적절 한 라우팅이 가능 하도록 팀 클라이언트의 통화 및 채팅 기능을 사용 하지 않도록 설정 합니다. 마찬가지로 사용자가 SfBOnly 또는 SfBWithTeamsCollab 모드에 있고 사용자가 SfBWithTeamsCollabAndMeetings 모드일 때 명시적으로 사용 하도록 설정 되어 있는 경우 팀에서 모임 예약을 명시적으로 사용할 수 없습니다.

요구 사항에 따라 조직에서 선택한 업그레이드 경로에 따라 적절 한 공존 모드를 할당할 수 있습니다. 자세한 내용은 비즈니스용 [Skype로 팀을 사용 하는 조직에 대 한 마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md) 을 참조 하 고 [공존 및 업그레이드 설정을 설정](https://aka.ms/SkypeToTeams-SetCoexistence)합니다.


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>3 단계: 비즈니스용 Skype 온-프레미스에서 팀 으로만 사용자 이동

궁극적으로 사용자를 팀 전용 모드로 이동 해야 합니다. 이 작업에는 온-프레미스 환경에 따라 하나 또는 두 단계가 포함 될 것입니다.  

자세한 내용은 온 [-프레미스와 클라우드 간에 사용자 이동을](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) 참조 하 고 온 [-프레미스에서 팀으로 사용자를 이동](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)합니다. 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>4 단계: 하이브리드를 사용 하지 않도록 설정 하 여 클라우드로 마이그레이션 완료

모든 사용자를 온-프레미스에서 클라우드로 이동한 후에는 온-프레미스 Skype 비즈니스 배포를 해제할 수 있습니다. 자세한 내용은 [클라우드로 마이그레이션을 완료 하기 위해 하이브리드 사용 안 함을](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)참조 하세요.


## <a name="phone-system-and-pstn-connectivity-options"></a>전화 시스템 및 PSTN 연결 옵션

사용자가 TeamsOnly 모드에 있는 경우 팀이 포함 된 전화 시스템이 지원 됩니다. (사용자가 군도 모드에 있는 경우, 전화 시스템은 비즈니스용 Skype 에서만 지원 됩니다.) 

### <a name="pstn-connectivity-options"></a>PSTN 연결 옵션

PSTN (공용 전환 전화 네트워크) 연결 옵션을 고려할 때 비즈니스용 Skype에서 팀 전용 모드로 전환할 때 다음과 같은 두 가지 시나리오가 가능 합니다.

- Enterprise Voice를 사용 하는 비즈니스용 Skype 온-프레미스 사용자로 서, 온라인으로 이동 하 고 Microsoft의 통화 요금제를 사용 하 게 됩니다. 이 사용자를 팀으로 마이그레이션하면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동 하 고 해당 사용자의 전화 번호를 Microsoft 통화 요금제 또는 B로 이동 하 여 사용 가능한 지역에서 새 구독자 번호를 할당 해야 합니다.  자세한 내용은 [비즈니스용 Skype Server 온-프레미스에서 엔터프라이즈 음성을 사용 하 여 Microsoft 전화 요금제를](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)참조 하세요.

- 비즈니스용 Skype 온-프레미스에서 엔터프라이즈 음성을 사용 하 여 온라인으로 전환 하 고 온-프레미스 PSTN 연결을 유지 하는 사용자입니다. 이 사용자를 팀으로 마이그레이션하면 사용자의 온-프레미스 비즈니스용 Skype 계정을 클라우드로 이동 하 고 사용자의 직접 라우팅에 맞게 이동 하도록 조정 해야 합니다. 자세한 내용은 [비즈니스용 Skype Server 온-프레미스에서 엔터프라이즈 음성을 사용 하 여 직접 라우팅](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)을 참조 하세요.
