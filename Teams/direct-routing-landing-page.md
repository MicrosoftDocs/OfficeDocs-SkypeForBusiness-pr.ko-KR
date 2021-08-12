---
title: 전화 시스템 직접 라우팅
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 구성, 필수 핵심 배포 결정 및 음성 라우팅 고려 사항과 같은 직접 라우팅에 대해 자세히 설명합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6cfa0f6aecf2dfeb708d51ff6ebd98f13a36167125f295329f3e37b2e39c0daf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280911"
---
# <a name="phone-system-direct-routing"></a>전화 시스템 직접 라우팅

[시작](get-started-with-teams-quick-start.md)을 완료했습니다. 조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다. 회의 를 통해 [모임을 & 수 있습니다.](deploy-meetings-microsoft-teams-landing-page.md) 이제 클라우드 음성 워크로드를 추가할 준비가 됐고, 직접 라우팅을 사용하여 PSTN(공용 전환 전화 네트워크) 연결을 위해 자체 전화 시스템 결정했습니다. 직접 라우팅을 사용하면 거의 모든 전화 통신 사업자와 함께 전화 시스템을 사용할 수 있습니다.

이 문서에서는 조직의 요구에 따라 고려할 수 있는 추가 고려 사항뿐만 아니라 직접 라우팅에 대한 핵심 배포 결정에 대해 설명합니다. Microsoft의 클라우드 [](cloud-voice-landing-page.md) 음성 Microsoft Teams 자세한 내용은 클라우드 음성을 읽어야 합니다.

## <a name="learn-more-about-direct-routing"></a>직접 라우팅에 대해 자세히 알아보기

다음 문서에서는 직접 라우팅을 구성하고 사용하는 전화 시스템 제공합니다. 직접 라우팅을 구성하려면 PSTN 라우팅 디자인을 이해해야 합니다. 직접 라우팅을 계획하고 구성하는 방법을 이해하기 위해 다음 문서를 모두 읽어야 합니다.

- [직접 라우팅 계획](direct-routing-plan.md) 
- [직접 라우팅 구성](direct-routing-configure.md)
- [직접 라우팅으로 인증된 SBC(Session Border Controller) 목록](direct-routing-border-controllers.md)
- [직접 라우팅 모니터링 및 문제 해결](direct-routing-monitor-and-troubleshoot.md)

또한 요구 사항에 따라 다음 문서를 읽을 수 있습니다.

-  [여러 테넌트에 대해 세션 경계 컨트롤러 구성](direct-routing-sbc-multiple-tenants.md)
-  [직접 라우팅으로 마이그레이션](direct-routing-migrating.md)
-  [PSTN 연결이 포함된 하이브리드 환경의 사용자 계정](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 다음 세션에서 직접 라우팅: 직접 라우팅에 대해 [자세히 Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

직접 라우팅에 대해 고려해야 할 핵심 결정입니다. 

|본인에게 질의하기|작업 |
| :------------|:-------|
|어떤 사용자가 직접 라우팅을 사용하도록 설정하나요? | 자세한 내용은 직접 라우팅 서비스에 대한 사용자 [사용 을 참조하세요.](direct-routing-configure.md) |
직접 라우팅에 필요한 라이선스가 있나요? | 자세한 내용은 라이선스 및 기타 [요구 사항을 참조하세요.](direct-routing-plan.md#licensing-and-other-requirements)
|||

### <a name="session-border-controller-sbc-considerations"></a>SBC(세션 테두리 컨트롤러) 고려 사항

직접 라우팅을 사용하여 SBC(세션 테두리 컨트롤러)를 직접 연결하여 사용자 전화 시스템.  인증된 SBC 목록은 지원되는 [세션 테두리 컨트롤러 를 참조하세요.](direct-routing-border-controllers.md)

|본인에게 질의하기|작업 |
|:------------|:-------|
| SBC를 어디서 어떻게 배포하나요? | 자세한 내용은 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md) | 
테넌트가 여러 개 있나요? | 자세한 내용은 여러 테넌트에 대한 세션 테두리 [컨트롤러 구성을 참조하세요.](direct-routing-sbc-multiple-tenants.md)|
|||

### <a name="voice-routing-considerations"></a>음성 라우팅 고려 사항

호출을 특정 SBC로 전화 시스템 구성해야 합니다.

|본인에게 질의하기|작업 |
|:------------|:-------|
| 어떤 음성 라우팅 정책, PSTN 사용 및 음성 경로를 만들어야 하나요? | 음성 라우팅 정보는 음성 라우팅 구성 [을 참조하세요.](direct-routing-configure.md)
| 정의한 음성 라우팅 정책에 할당되는 사용자는 무엇입니까? | 음성 라우팅 구성 의 [예제를 참조합니다.](direct-routing-configure.md) |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>TeamsUpgradePolicy를 사용하여 수신 Teams 클라이언트에 토지가 되도록 합니다.

직접 라우팅은 Microsoft Teams. 직접 라우팅을 통해 PSTN 호출을 수신하려면 수신 호출이 수신 수신을 보장하도록 TeamsUpgradePolicy를 구성해야 Teams. 사용자는 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 Teams 전용 모드에 있어야 합니다. 

|본인에게 질의하기|작업 |
|:------------|:-------|
|전용 Teams 무엇을 의미하나요? | 자세한 내용은 와 함께 Teams 조직에 대한 마이그레이션 및 상호 [비즈니스용 Skype.](./migration-interop-guidance-for-teams-with-skype.md)|
|||

## <a name="additional-deployment-considerations"></a>추가 배포 고려 사항

조직의 요구 사항 및 구성에 따라 다음을 고려할 수 있습니다.

| 본인에게 질의하기| 작업 |
| :------------|:-------|
| 하이브리드 연결을 비즈니스용 Skype 서버 기존 배포가 있나요? |  하이브리드 환경의 사용자 계정이 프로비전 및 관리되는 방법을 이해하기 위해 PSTN 연결이 있는 하이브리드 환경의 사용자 계정을 [참조합니다.](direct-routing-user-accounts-in-a-hybrid-environment.md)| 
| 전화 요금제 또는 프레미스 비즈니스용 Skype 직접 라우팅으로 마이그레이션하고 있나요? | 기존 환경에서 직접 라우팅으로 마이그레이션하는 방법을 더 이해하려면 직접 라우팅으로 마이그레이션을 [참조합니다.](direct-routing-migrating.md) |
|||