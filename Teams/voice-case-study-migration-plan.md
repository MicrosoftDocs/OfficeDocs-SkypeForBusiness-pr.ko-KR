---
title: Teams 음성 Contoso 사례 연구 업그레이드 계획
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: '다국적 기업을 위한 Teams 음성 사례 연구: 업그레이드 계획.'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39cfd66f0ff34fb0f8792871ddfdcceebb2b9961
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65822987"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso 사례 연구: 업그레이드 계획 Teams

Contoso는 비즈니스용 Skype Teams 마이그레이션하기로 결정하여 최종 사용자에게 쉬운 전환 환경을 제공하고자 했습니다. 모든 사용자를 동시에 Teams 전환하는 대신 하이브리드 연결을 설정하고 겹치는 기능 방법을 사용하여 사용자를 Teams 이동하기로 결정했습니다. 이를 통해 Teams 및 비즈니스용 Skype 온-프레미스의 사용자가 현재 상태를 공유하고 통신할 수 있었습니다. 사용자가 전화 시스템 파일럿에 들어갔을 때 Teams 전용 모드로 이동되었습니다.

업그레이드, 메서드 및 모드에 대한 기본 개념을 이해하려면 Contoso에서 다음 문서를 읽어보세요.

- [Microsoft Teams 업그레이드 시작하기](upgrade-start-here.md)
- [IT 관리자를 위한 업그레이드 전략](upgrade-to-teams-on-prem-implement.md) 
- [마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso는 또한 [비즈니스용 Skype Teams 경로를 디자인하는](https://myignite.microsoft.com/archives/IG20-OD251) Ignite 2019 세션에 참석했습니다. Contoso는 다음 사항을 알아보았습니다.

- 상호 운용성, 페더레이션 및 업그레이드 동작과 같은 기본 개념 

- TeamsUpgradePolicy 기반 공존 모드 및 관리 

- 다음을 위한 최종 사용자 환경: 

  - 채팅 및 통화 

  - 모임 예약 

  - Teams 클라이언트에서 공동 작업 기능의 가용성 

온-프레미스 환경을 클라우드로 이동하는 첫 번째 단계인 하이브리드 연결을 계획하고 구성하기 위해 Contoso는 [하이브리드 연결 계획을](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) 읽고 [하이브리드 연결을 구성](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 하여 다음 방법을 이해합니다. 

  - Office 365 페더레이션하도록 온-프레미스 환경 서비스를 구성합니다. 

  - Office 365 신뢰하고 Office 365 공유 SIP 주소 공간을 사용하도록 온-프레미스 환경을 구성합니다. 

  - Office 365 테넌트에서 공유 SIP 주소 공간을 사용하도록 설정합니다.

  - 기술 파일럿 중에 아일랜드 모드를 사용합니다.

  - 사용자가 전화 시스템 사용하도록 설정되면 사용자를 TeamsOnly 모드로 전환합니다. TeamsOnly 모드는 통화 플랜 및 직접 라우팅에 필요합니다.
