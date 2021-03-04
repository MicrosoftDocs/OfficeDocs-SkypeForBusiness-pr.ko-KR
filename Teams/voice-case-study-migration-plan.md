---
title: Teams 음성 Contoso 사례 연구
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
description: 다국적 기업에 대한 Teams 음성 사례 연구
appliesto:
- Microsoft Teams
ms.openlocfilehash: 93f6d0877537a740dc867b44c3c4deb9bebb8441
ms.sourcegitcommit: 6f7b91f573e2a034f8c5474be2c5cb2971f4b5ab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421293"
---
# <a name="contoso-case-study-teams-upgrade-plan"></a>Contoso 사례 연구: Teams 업그레이드 계획

비즈니스용 Skype에서 Teams로 마이그레이션하기로 결정한 Contoso는 최종 사용자에게 쉬운 전환 환경을 제공하기를 원했습니다. 모든 사용자를 Teams로 동시에 전환하는 대신 하이브리드 연결을 설정하고 겹치는 기능 방법을 사용하여 사용자를 Teams로 이동하기로 결정했습니다. 이렇게 하면 Teams 및 Skype for Business On-프레미스에서 사용자가 현재 상태와 통신을 공유할 수 있습니다. 사용자가 전화 시스템에 대한 파일럿을 입력하면 Teams 전용 모드로 이동됩니다.

업그레이드, 메서드 및 모드에 대한 기본 개념을 이해하려면 Contoso는 다음 문서를 읽습니다.

- [Microsoft Teams 업그레이드 시작하기](upgrade-start-here.md)
- [IT 관리자를 위한 업그레이드 전략](upgrade-to-teams-on-prem-implement.md) 
- [마이그레이션 및 상호 실행성 지침](migration-interop-guidance-for-teams-with-skype.md)
 
Contoso는 비즈니스용 Skype에서 Teams로 경로를 디자인하는 Ignite 2019 세션에도 [참석했습니다.](https://myignite.techcommunity.microsoft.com/sessions/81820?source=sessions) Contoso는 다음에 대해 배웠다.

- 상호 운영성, 페더리게이트 및 업그레이드 동작과 같은 기본 개념 

- TeamsUpgradePolicy를 기반으로 하는 공존 모드 및 관리 

- 다음에 대한 최종 사용자 환경: 

  - 채팅 및 통화 

  - 모임일정 

  - Teams 클라이언트에서 공동 작업 기능의 가용성 

하이브리드 연결을 계획하고 구성하기 위해, 프레미스 환경의 클라우드로 이동하는 [](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity) 첫 번째 단계인 Contoso는 하이브리드 연결 계획 및 하이브리드 연결 구성을 읽고 다음 방법을 이해합니다. [](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

  - Office 365와 페더테이트하도록 프레미스 환경 서비스를 구성합니다. 

  - Office 365를 신뢰하고 Office 365를 사용하여 공유 SIP 주소 공간을 사용하도록 프레미스 환경 구성 

  - Office 365 테넌트에서 공유 SIP 주소 공간을 사용하도록 설정합니다.

  - 기술 파일럿 중에 섬 모드를 사용 합니다.

  - 사용자가 전화 시스템에 사용하도록 설정되면 사용자를 TeamsOnly 모드로 전환합니다. TeamsOnly 모드는 통화 계획 및 직접 라우팅에 필요합니다. 
