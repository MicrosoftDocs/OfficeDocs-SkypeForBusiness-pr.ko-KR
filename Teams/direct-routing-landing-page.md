---
title: 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 직접 라우팅을 사용한 Teams 전화 시스템에 대해 알아봅니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: dff97fc683acd693f867126661c9bf90550ebbe5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269923"
---
# <a name="direct-routing"></a>직접 라우팅

[시작](get-started-with-teams-quick-start.md)을 완료했습니다. 조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다. [모임 & 회의를](deploy-meetings-microsoft-teams-landing-page.md) 배포했을 수도 있습니다. 이제 음성 워크로드를 추가할 준비가 되었으며 직접 라우팅과 함께 전화 시스템을 사용하여 PSTN(공중 전화망) 연결에 고유한 전화 통신 사업자를 사용하기로 결정했습니다. 직접 라우팅을 사용하면 거의 모든 전화 통신 사업자와 함께 전화 시스템을 사용할 수 있습니다.

이 문서에서는 직접 라우팅에 대한 핵심 배포 결정과 조직의 요구 사항에 따라 고려할 수 있는 추가 고려 사항에 대해 설명합니다. 또한 Microsoft의 음성 제품에 대한 자세한 내용은 [음성 솔루션 계획을](cloud-voice-landing-page.md) 읽어야 합니다.

## <a name="learn-more-about-direct-routing"></a>직접 라우팅에 대해 자세히 알아보기

다음 문서에서는 직접 라우팅을 구성하고 사용하는 방법에 대한 자세한 정보를 제공합니다. 직접 라우팅을 구성하려면 PSTN 라우팅 디자인을 이해해야 합니다. 직접 라우팅을 계획하고 구성하는 방법을 이해하려면 다음 문서를 모두 읽어야 합니다.

- [직접 라우팅 계획](direct-routing-plan.md) 
- [직접 라우팅 구성](direct-routing-configure.md)
- [직접 라우팅으로 인증된 SBC(Session Border Controller) 목록](direct-routing-border-controllers.md)
- [직접 라우팅 모니터링 및 문제 해결](direct-routing-monitor-and-troubleshoot.md)

또한 요구 사항에 따라 다음 문서를 읽을 수 있습니다.

-  [여러 테넌트에 대해 세션 경계 컨트롤러 구성](direct-routing-sbc-multiple-tenants.md)
-  [직접 라우팅으로 마이그레이션](direct-routing-migrating.md)
-  [PSTN 연결이 포함된 하이브리드 환경의 사용자 계정](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 직접 라우팅: [Microsoft Teams의 직접 라우팅](https://aka.ms/teams-direct-routing)에 대해 자세히 알아보려면 다음 세션을 시청하세요.

## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

직접 라우팅에 대해 고려해야 할 핵심 결정 사항입니다. 

|본인에게 질의하기|작업 |
| :------------|:-------|
|직접 라우팅을 사용하도록 설정할 사용자는 무엇인가요? | 자세한 내용은 [직접 라우팅 서비스에 대한 사용자 사용을](direct-routing-configure.md) 참조하세요. |
직접 라우팅에 필요한 라이선스가 있나요? | 자세한 내용은 [라이선스 및 기타 요구 사항을 참조하세요](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>SBC(세션 테두리 컨트롤러) 고려 사항

직접 라우팅을 사용하면 사용자 고유의 SBC(세션 테두리 컨트롤러)를 전화 시스템에 직접 연결합니다. 인증된 SCC 목록은 [지원되는 세션 테두리 컨트롤러를 참조하세요](direct-routing-border-controllers.md).

|본인에게 질의하기|작업 |
|:------------|:-------|
| SCC는 어디에서 어떻게 배포하나요? | 자세한 내용은 [직접 라우팅 구성을 참조하세요.](direct-routing-configure.md) | 
테넌트가 여러 대 있나요? | 자세한 내용은 [여러 테넌트에 대한 세션 테두리 컨트롤러 구성을 참조하세요](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>음성 라우팅 고려 사항

특정 SBC로 통화를 라우팅하도록 전화 시스템을 구성해야 합니다.

|본인에게 질의하기|작업 |
|:------------|:-------|
| 어떤 음성 라우팅 정책, PSTN 사용 및 음성 경로를 만들어야 하나요? | 음성 라우팅 정보는 [음성 라우팅 구성을 참조하세요](direct-routing-configure.md).
| 정의한 음성 라우팅 정책에 할당되는 사용자는 무엇인가요? | [음성 라우팅 구성](direct-routing-configure.md)의 예제를 참조하세요. |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>TeamsUpgradePolicy를 사용하여 Teams 클라이언트에 들어오는 통화가 있는지 확인합니다.

직접 라우팅은 Microsoft Teams에서만 지원됩니다. 직접 라우팅을 통해 PSTN 통화를 받으려면 Teams에서 수신 전화를 받도록 TeamsUpgradePolicy를 구성해야 합니다. 사용자는 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당하여 수행할 수 있는 TeamsOnly 모드에 있어야 합니다. 

|본인에게 질의하기|작업 |
|:------------|:-------|
|TeamsOnly 모드는 무엇을 의미하나요? | 자세한 내용은 [비즈니스용 Skype 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 운용성 지침을](./migration-interop-guidance-for-teams-with-skype.md) 참조하세요.|
|||


