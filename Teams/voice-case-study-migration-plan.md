---
title: Teams Contoso 사례 연구 업그레이드 계획
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
description: 'Teams 국가 기업에 대한 음성 사례 연구: 업그레이드 계획.'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c2d64e93e8f9ab53cd2a696af69de4b7f0d4f7348fec27a189b60896ee1ec02
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54350180"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso 사례 연구: Teams 계획

Contoso는 최종 사용자에게 비즈니스용 Skype Teams 전환 환경을 제공하기로 결정했습니다. 모든 사용자를 동시에 Teams 대신 하이브리드 연결을 설정하고 겹치는 기능 메서드를 사용하여 사용자를 다른 사용자로 Teams. 이렇게 하면 사용자가 Teams 및 비즈니스용 Skype 현재 상태 공유 및 통신을 할 수 있습니다. 사용자가 파일럿을 전화 시스템 전용 모드로 Teams 이동했습니다.

업그레이드, 메서드 및 모드에 대한 기본 개념을 이해하려면 Contoso는 다음 문서를 읽습니다.

- [Microsoft Teams 업그레이드 시작하기](upgrade-start-here.md)
- [IT 관리자를 위한 업그레이드 전략](upgrade-to-teams-on-prem-implement.md) 
- [마이그레이션 및 상호 실행성 지침](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso는 또한 Ignite 2019 세션에 참석하여 비즈니스용 Skype 에서 [Teams.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) Contoso는 다음에 대해 배웠다.

- 상호 운영성, 페더리게이트 및 업그레이드 동작과 같은 기본 개념 

- TeamsUpgradePolicy를 기반으로 하는 공존 모드 및 관리 

- 다음에 대한 최종 사용자 환경: 

  - 채팅 및 통화 

  - 모임일정 

  - 클라이언트에서 공동 작업 Teams 가용성 

하이브리드 연결을 계획하고 구성하기 위해, 프레미스 환경의 클라우드로 이동하는 [](/SkypeForBusiness/hybrid/plan-hybrid-connectivity) 첫 번째 단계인 Contoso는 하이브리드 연결 계획 및 하이브리드 연결 구성을 읽고 다음 방법을 이해합니다. [](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

  - 프레미스 환경 서비스를 구성하여 Office 365. 

  - 공유 SIP 주소 공간을 신뢰하고 Office 365 공유 SIP 주소 공간을 사용하도록 프레미스 Office 365 

  - 공유 SIP 주소 공간을 테넌트에서 Office 365.

  - 기술 파일럿 중에 섬 모드를 사용 합니다.

  - 사용자가 활성화되면 TeamsOnly 모드로 사용자를 전화 시스템. TeamsOnly 모드는 통화 계획 및 직접 라우팅에 필요합니다.
