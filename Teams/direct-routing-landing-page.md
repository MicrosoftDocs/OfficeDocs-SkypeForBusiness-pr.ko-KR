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
description: 구성, 필요한 핵심 배포 결정 및 음성 라우팅 고려 사항과 같은 직접 라우팅에 대해 자세히 설명합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c5120f60778879be0978cb80c56daf99e5b5a38
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031824"
---
# <a name="phone-system-direct-routing"></a>전화 시스템 직접 라우팅

[시작](get-started-with-teams-quick-start.md)을 완료했습니다. 조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다. 회의에 모임을 & [수도 있습니다.](deploy-meetings-microsoft-teams-landing-page.md) 이제 클라우드 음성 워크로드를 추가할 준비가 됐고 전화 시스템 직접 라우팅을 사용하여 PSTN(공용 전환 전화 네트워크) 연결에 사용자 자신의 전화 통신 회사를 사용하기로 결정했습니다. 직접 라우팅을 사용하면 거의 모든 전화 통신 사업자와 함께 전화 시스템을 사용할 수 있습니다.

이 문서에서는 직접 라우팅에 대한 핵심 배포 결정과 조직의 요구에 따라 고려할 수 있는 추가 고려 사항을 설명합니다. 또한 Microsoft의 클라우드 음성 제안에 대한 자세한 내용은 [Microsoft Teams의](cloud-voice-landing-page.md) Cloud Voice를 읽어야 합니다.

## <a name="learn-more-about-direct-routing"></a>직접 라우팅에 대해 자세히 알아보기

다음 문서에서는 전화 시스템 직접 라우팅 구성 및 사용에 대한 자세한 정보를 제공합니다. 직접 라우팅을 구성하려면 PSTN 라우팅 설계를 이해해야 합니다. 직접 라우팅을 계획하고 구성하는 방법을 이해하기 위해 다음 문서를 모두 읽어야 합니다.

- [직접 라우팅 계획](direct-routing-plan.md) 
- [직접 라우팅 구성](direct-routing-configure.md)
- [직접 라우팅으로 인증된 SBC(Session Border Controller) 목록](direct-routing-border-controllers.md)
- [직접 라우팅 모니터링 및 문제 해결](direct-routing-monitor-and-troubleshoot.md)

또한 요구 사항에 따라 다음 문서를 읽을 수 있습니다.

-  [여러 테넌트에 대해 세션 경계 컨트롤러 구성](direct-routing-sbc-multiple-tenants.md)
-  [직접 라우팅으로 마이그레이션](direct-routing-migrating.md)
-  [PSTN 연결이 포함된 하이브리드 환경의 사용자 계정](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 직접 라우팅: Microsoft Teams의 직접 라우팅에 대해 자세히 알아보는 다음 [세션을 시청합니다.](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

직접 라우팅에 대해 고려해야 할 핵심 결정입니다. 

|본인에게 질의하기|작업 |
| :------------|:-------|
|어떤 사용자가 직접 라우팅을 사용하도록 설정하나요? | 자세한 내용은 직접 라우팅 서비스에 대해 사용자 [활성화를 참조하세요.](direct-routing-configure.md) |
직접 라우팅에 필요한 라이선스가 있나요? | 자세한 내용은 라이선스 및 기타 [요구 사항을 참조하세요.](direct-routing-plan.md#licensing-and-other-requirements)
|||

### <a name="session-border-controller-sbc-considerations"></a>SBC(세션 테두리 컨트롤러) 고려 사항

직접 라우팅을 사용하면 휴대폰 시스템에 직접 SBC(세션 테두리 컨트롤러)를 연결합니다.  인증된 SBC 목록은 지원되는 세션 테두리 [컨트롤러를 참조하세요.](direct-routing-border-controllers.md)

|본인에게 질의하기|작업 |
|:------------|:-------|
| SBC는 어디에 어떻게 배포하나요? | 자세한 내용은 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md) | 
여러 테넌트가 있나요? | 자세한 내용은 여러 테넌트에 대한 세션 테두리 [컨트롤러 구성을 참조하세요.](direct-routing-sbc-multiple-tenants.md)|
|||

### <a name="voice-routing-considerations"></a>음성 라우팅 고려 사항

호출을 특정 SBC로 라우팅하도록 전화 시스템을 구성해야 합니다.

|본인에게 질의하기|작업 |
|:------------|:-------|
| 어떤 음성 라우팅 정책, PSTN 사용 및 음성 경로를 만들어야 하나요? | 음성 라우팅 정보는 음성 라우팅 [구성을 참조하세요.](direct-routing-configure.md)
| 정의한 음성 라우팅 정책에 어떤 사용자를 할당할까요? | 음성 라우팅 구성의 [예제를 참조합니다.](direct-routing-configure.md) |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>TeamsUpgradePolicy를 사용하여 수신 전화가 Teams 클라이언트에 연결되도록 합니다.

직접 라우팅은 Microsoft Teams에서만 지원됩니다. 직접 라우팅을 통해 PSTN 통화를 수신하려면 Teams에서 수신 전화가 수신되도록 TeamsUpgradePolicy를 구성해야 합니다. 사용자는 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당하여 할 수 있는 Teams 전용 모드에 있어야 합니다. 

|본인에게 질의하기|작업 |
|:------------|:-------|
|Teams 전용 모드의 의미 | 자세한 내용은 비즈니스용 Skype와 함께 Teams를 사용하는 조직에 대한 마이그레이션 및 상호 [연동성 지침을 참조하세요.](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)|
|||

## <a name="additional-deployment-considerations"></a>추가 배포 고려 사항

조직의 요구 사항 및 구성에 따라 다음 사항을 고려할 수 있습니다.

| 본인에게 질의하기| 작업 |
| :------------|:-------|
| 하이브리드 연결이 구성된 기존 비즈니스용 Skype Server 배포가 있나요? |  하이브리드 환경의 사용자 계정을 프로비전하고 관리하는 방법을 이해하기 위해 PSTN 연결이 있는 하이브리드 환경의 사용자 계정을 [참조합니다.](direct-routing-user-accounts-in-a-hybrid-environment.md)| 
| 통화 요금제에서 직접 라우팅으로 마이그레이션하나요 아니면 비즈니스용 Skype-프레미스 환경에서 마이그레이션하나요? | 기존 환경에서 직접 라우팅으로 마이그레이션하는 방법을 더 이해하려면 직접 라우팅으로 마이그레이션을 [참조합니다.](direct-routing-migrating.md) |
|||
