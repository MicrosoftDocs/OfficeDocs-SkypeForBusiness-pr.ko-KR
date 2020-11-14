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
description: 구성, 필요한 핵심 배포 결정, 음성 라우팅 고려 사항 등의 직접적인 라우팅에 대해 자세히 알아보세요.
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

[시작](get-started-with-teams-quick-start.md)을 완료했습니다. 조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다. [모임 & 회의](deploy-meetings-microsoft-teams-landing-page.md)를 배포 했을 수도 있습니다. 이제 클라우드 음성 작업 부하를 추가할 준비가 되었으며, 전화 시스템 직접 라우팅을 사용 하 여 PSTN (공개 교환 통신망) 연결에 고유한 전화 통신 회사를 사용 하기로 결정 했습니다. 직접 라우팅을 사용하면 거의 모든 전화 통신 사업자와 함께 전화 시스템을 사용할 수 있습니다.

이 문서에서는 조직의 요구 사항에 따라 직접 라우팅에 대 한 핵심 배포 결정 및 고려해 볼 수 있는 추가 고려 사항을 설명 합니다. Microsoft의 클라우드 음성 제공에 대 한 자세한 내용은 [Microsoft 팀에서 클라우드 음성을](cloud-voice-landing-page.md) 참조 하세요.

## <a name="learn-more-about-direct-routing"></a>직접 라우팅에 대 한 자세한 정보

다음 문서는 전화 시스템 다이렉트 라우팅 구성 및 사용에 대 한 자세한 정보를 제공 합니다. 직접 라우팅 구성에는 PSTN 라우팅 디자인에 대 한 이해가 필요 합니다. 직접 라우팅을 계획 하 고 구성 하는 방법을 이해 하려면 다음 문서를 모두 읽어 보아야 합니다.

- [직접 라우팅 계획](direct-routing-plan.md) 
- [직접 라우팅 구성](direct-routing-configure.md)
- [직접 라우팅으로 인증된 SBC(Session Border Controller) 목록](direct-routing-border-controllers.md)
- [직접 라우팅 모니터링 및 문제 해결](direct-routing-monitor-and-troubleshoot.md)

또한 요구 사항에 따라 다음 문서를 읽어 보려는 경우도 있습니다.

-  [여러 테넌트에 대해 세션 경계 컨트롤러 구성](direct-routing-sbc-multiple-tenants.md)
-  [직접 라우팅으로 마이그레이션](direct-routing-migrating.md)
-  [PSTN 연결이 포함된 하이브리드 환경의 사용자 계정](direct-routing-user-accounts-in-a-hybrid-environment.md)
- 직접 라우팅에 대해 자세히 알아보려면 다음 세션을 시청 하세요. [Microsoft 팀의 직접 라우팅](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

이는 직접 라우팅에 대해 고려해 야 할 핵심 결정 사항입니다. 

|본인에게 질의하기|작업 |
| :------------|:-------|
|사용자가 직접 라우팅을 사용할 수 있도록 설정 하는 방법은 무엇 인가요? | 자세한 내용은 [직접 라우팅 서비스에 대 한 사용자 사용](direct-routing-configure.md)을 참조 하세요. |
직접 라우팅에 필요한 라이선스가 있나요? | 자세한 내용은 [라이선스 및 기타 요구 사항을](direct-routing-plan.md#licensing-and-other-requirements)참조 하세요.
|||

### <a name="session-border-controller-sbc-considerations"></a>SBC (세션 경계 컨트롤러) 고려 사항

직접 라우팅이 있으면 자체의 SBC (세션 경계 컨트롤러)을 전화 시스템에 직접 연결 합니다.  인증 된 SBCs 목록은 [지원 되는 세션 경계 컨트롤러](direct-routing-border-controllers.md)를 참조 하세요.

|본인에게 질의하기|작업 |
|:------------|:-------|
| SBCs를 배포 하는 위치는 어디 인가요? | 자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md) 참조 하세요. | 
여러 테 넌 트가 있습니까? | 자세한 내용은 [여러 테 넌 트에 대 한 세션 경계 컨트롤러 구성을](direct-routing-sbc-multiple-tenants.md)참조 하세요.|
|||

### <a name="voice-routing-considerations"></a>음성 라우팅 고려 사항

특정 SBCs에 게 통화를 라우팅하려면 전화 시스템을 구성 해야 합니다.

|본인에게 질의하기|작업 |
|:------------|:-------|
| 만들어야 할 음성 라우팅 정책, PSTN 사용 및 음성 경로는 무엇 인가요? | 음성 라우팅에 대 한 자세한 내용은 [음성 라우팅 구성을](direct-routing-configure.md)참조 하세요.
| 내가 정의한 음성 라우팅 정책에 어떤 사용자를 할당 해야 하나요? | [음성 라우팅 구성](direct-routing-configure.md)의 예제를 참조 하세요. |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>TeamsUpgradePolicy를 사용 하 여 팀 클라이언트에서 걸려오는 전화가 있는지 확인

직접 라우팅은 Microsoft 팀 에서만 지원 됩니다. 직접 라우팅을 통해 PSTN 통화를 받으려면 팀에서 수신 전화를 받을 수 있도록 TeamsUpgradePolicy를 구성 해야 합니다. 사용자는 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스에 할당 하 여 팀 전용 모드 여야 합니다. 

|본인에게 질의하기|작업 |
|:------------|:-------|
|팀 전용 모드의 의미 | 자세한 내용은 [비즈니스용 Skype로 함께 팀을 사용 하는 조직의 마이그레이션 및 상호 운용성 지침](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)을 참조 하세요.|
|||

## <a name="additional-deployment-considerations"></a>추가 배포 고려 사항

조직의 요구 및 구성에 따라 다음을 고려해 볼 수 있습니다.

| 본인에게 질의하기| 작업 |
| :------------|:-------|
| 하이브리드 연결을 사용 하는 기존 비즈니스용 Skype 서버 배포가 구성 되어 있습니까? |  하이브리드 환경의 사용자 계정을 프로 비전 하 고 관리 하는 방법을 이해 하려면 [PSTN 연결을 사용 하는 하이브리드 환경에서 사용자 계정을](direct-routing-user-accounts-in-a-hybrid-environment.md)참조 하세요.| 
| 통화 요금제에서 직접 라우팅 하거나 비즈니스용 Skype 온-프레미스 환경에서 마이그레이션하는 경우 | 기존 환경에서 직접 라우팅으로 마이그레이션하는 방법에 대 한 자세한 내용은 [직접 라우팅으로 마이그레이션을](direct-routing-migrating.md)참조 하세요. |
|||
