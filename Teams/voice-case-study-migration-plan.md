---
title: 팀 음성 Contoso 사례 연구
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
description: 여러 국가의 기업에 대 한 팀 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: d5429b4c45ccea82d1451210438bedd328618604
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786091"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso 사례 연구: 팀 업그레이드 계획

비즈니스용 Skype에서 팀으로 마이그레이션을 할 때 Contoso는 최종 사용자에 게 쉬운 전환 환경을 제공 하고자 했습니다. 동시에 모든 사람을 팀으로 전환 하는 대신 하이브리드 연결을 설정 하 고 겹치는 기능 방법을 사용 하 여 사용자를 팀으로 이동 하기로 결정 했습니다. 이 허용 된 사용자는 팀 및 비즈니스용 Skype 온-프레미스에서 현재 상태를 공유 하 고 통신할 수 있습니다. 사용자가 전화 시스템의 파일럿을 입력 하면 팀 전용 모드로 옮겨졌습니다.

업그레이드, 메서드 및 모드에 대 한 기본 개념을 이해 하기 위해 Contoso는 다음 문서를 읽어 보세요.

- [Microsoft Teams 업그레이드 시작하기](upgrade-start-here.md)
- [비즈니스용 Skype에서 Teams로 업그레이드](upgrade-to-teams-on-prem-overview.md) 
- [마이그레이션 및 상호 운용성 지침](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso는 비즈니스용 [Skype에서 팀으로 경로를 디자인](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions)하는 Ignite 2019 세션에도 참가 했습니다. Contoso는 다음 정보를 얻었습니다.

- 상호 운용성, 페더레이션, 업그레이드 동작 등의 기본 개념 

- TeamsUpgradePolicy 기반 공존 모드 및 관리 

- 최종 사용자 환경: 

  - 채팅 및 통화 

  - 모임 예약 

  - 팀 클라이언트의 공동 작업 기능 가용성 

하이브리드 연결을 계획 하 고 구성 하려면 (온-프레미스 환경을 클라우드로 이동 하는 첫 번째 단계), Contoso는 [하이브리드 연결 계획](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) 및 [하이브리드 연결 구성](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 을 참조 하세요. 

  - Office 365와 페더레이션 하도록 온-프레미스 환경 서비스를 구성 합니다. 

  - Office 365을 신뢰 하도록 온-프레미스 환경을 구성 하 고 Office 365에서 공유 SIP 주소 공간 사용 

  - Office 365 테 넌 트에서 공유 SIP 주소 공간을 사용 하도록 설정 합니다.

  - 기술 시험 운용 중에 아일랜드 모드를 사용 합니다.

  - 사용자가 전화 시스템을 사용할 수 있게 되 면 사용자를 TeamsOnly 모드로 전환 합니다. 팀 전용 모드는 호출 계획 및 직접 라우팅에 필요 합니다. 
