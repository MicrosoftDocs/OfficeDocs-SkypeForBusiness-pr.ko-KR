---
title: 업그레이드 프레임워크에 대해 - 비즈니스용 Skype Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 검증된 성공 프레임워크를 사용하여 조직의 업그레이드 비즈니스용 Skype 지원할 수 Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d0184198d7e419642a582f8642b312238900f1f8
ms.sourcegitcommit: b387296c043fcf10fba7b9ef416328383e54a565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/26/2021
ms.locfileid: "53586997"
---
# <a name="about-the-upgrade-framework"></a>업그레이드 프레임워크 정보

업그레이드 여정을 추측할 수 있도록 변경을 구현하기 위한 검증된 프레임워크를 사용했습니다. 아래와 같이 프레임워크의 각 단계는 이전 단계를 빌드하고 최적의 결과를 얻기 위해 순서대로 단계를 따르는 것이 좋습니다.  

먼저 올바른 이해 관계자를 모아 업그레이드 계획(예: 범위, 목표 및 타임라인)을 정의합니다. 계획이 준비되어 있는 경우 기술 환경을 확인하고 최종 사용자가 계획에 Teams. 그런 다음, 준비된 경우 파일럿에서 조직 전체 업그레이드로 이동하여 단계적 업그레이드를 구현합니다. 조직이 Teams 경우 품질을 모니터링하고 사용자 채택을 가속화하는 운영 계획을 수립합니다.

![업그레이드 여정 프레임워크의 그림](media/upgrade-banner-main.png "프로젝트가 올바른 프로젝트 팀과 함께 성공하도록 설정되어 있는지 확인 프로젝트 범위, 목표 및 타임라인을 정의합니다. 기술 및 사용자 준비를 모두 확인 합니다. 롤아웃 계획을 실행합니다. 결과를 최대화하기 위해 모멘텀을 유지 관리합니다.")

업그레이드 프로세스의 위치를 식별하려면 관련 페이지에서 이 프레임워크 그래픽을 찾아야 합니다.

## <a name="sample-upgrade-timeline"></a>샘플 업그레이드 타임라인

변경을 계획하기 시작할 때 업그레이드 여정이 시작됩니다. 성공 프레임워크를 지침으로 활용하는 샘플 타임라인은 업그레이드를 계획하고 준비하는 업그레이드 전 단계에서 업그레이드를 통해 그리고 업그레이드 후 운영 단계로 이동하여 결과를 유지 및 증폭하도록 설계된 샘플 타임라인입니다. 

> [!NOTE]
> 사용자 Teams 여러 모드를 활용하고 다른 시간의 [](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)사용자 그룹을 업그레이드하는 것이 포함될 수 있습니다. 사용자 업그레이드 환경을 제어하면서 사용자 업그레이드 환경을 제어할 수   Teams.  

업그레이드 여정이 어떻게 전개될 수 있는지 보여 주기 위해 아래에서 온라인에서 제도 모드로의 비즈니스용 Skype 여정을 정의하는 샘플 계획을 Teams. 또한 샘플 계획에서는 사용자를 4개의 업그레이드 그룹 또는 코호트로 나눈 조직을 간략하게 간략하게 설명합니다. 이를 템플릿으로 사용하여 사용자가 사용할 다양한 모드와 사용자를 분할할 업그레이드 그룹의 수를 Teams 특정 여정을 통합하도록 계획을 사용자 [](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)   지정합니다. 

## <a name="pre-upgrade"></a>업그레이드 전

**에 대한 조직 Teams.** 성공적인 업그레이드를 Teams 준비를 위해 적절한 시간을 할당하는 것이 중요합니다. 조직에서 해당 Teams 빠르게 인식할 수 있을 뿐만 아니라, 준비가 비즈니스용 Skype 즉시 업그레이드를 Teams 수 있습니다. 사용자와 함께 Teams 비즈니스용 Skype 사전 업그레이드 활동을 검사점으로 사용하여 사용자를 업그레이드하기 전에 조직의 준비를 검사점으로 Teams. 

> [!TIP]
> 샘플 [업그레이드](https://aka.ms/UpgradeSuccessKit)프로젝트 계획 및 파일럿 테스트 계획 외에도 통신 및 사용자 설문 조사와 같은 템플릿 사용자 준비 자료에 대한 업그레이드 성공   키트를 다운로드합니다. 키트에서 사용할 수 있는 항목은 아래 목록에서 스테리스크(*)로 표시됩니다.

### <a name="plan-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>계획: 장기적인 성공을 위해 조직이 설정되도록 업그레이드 계획 만들기

| 단계 |&nbsp;| 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **이해 관계자 정의** | 업그레이드 성공을 추진할 책임이 있는 프로젝트 팀 구성원을 할당합니다. | [이해 관계자 참여](upgrade-enlist-stakeholders.md) |
| **2** | **프로젝트 비전 및 범위 정의** | "큰 그림" 비전 및 현재 프로젝트 범위를 디자인하여 업그레이드 여정에 대한 청사진을 만들 수 있습니다. | [Project 비전](upgrade-define-project-scope.md#project-vision) <br> <br>[Project 범위](upgrade-define-project-scope.md#project-scope) |
| **3** | **프로젝트 목표 정의** | 프로젝트 성공뿐만 아니라 진행률을 측정할 수 있는 대상 목표를 설정합니다. | [Project 목표](upgrade-define-project-scope.md#project-goals) |
| **4** | **위험 및 완화 계획 식별** | 문제가 발생하면 프로젝트를 신속하게 추적할 수 있도록 완화 계획을 수립합니다. | [위험 및 완화](upgrade-define-project-scope.md#risks-and-mitigation) |
| **5** | **타임라인 정의** | 일정 및 주요 이정표를 설정하여 프로젝트가 정시에 예산을 유지하게 합니다. | [타임라인](upgrade-define-project-scope.md#timeline) <br><br> [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **6** | **업그레이드 및 비즈니스용 Skype Teams 및 공존 전략 정의** | 조직에 가장 적합한 경로를 비즈니스용 Skype Teams 매핑합니다. | [Microsoft Teams 및 비즈니스용 Skype 상호운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br><br>[전화 시스템 및 PSTN 연결 옵션 이해](cloud-voice-landing-page.md)<br><br>  [업그레이드 여정 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) |


### <a name="prepare-evaluate-your-organizations-readiness-for-teams"></a>준비: 조직의 준비 Teams

| 단계 |&nbsp;  | 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **환경 평가 및 기술 Teams 완료** | 사용자 환경을 최적화하고 시간이 Teams 업그레이드를 용이하게 할 수 있도록 환경을 사용할 준비가 되도록 합니다. | [으로 업그레이드하기 전에](upgrade-plan-journey-evaluate-environment.md)환경을 Teams.<br><br> [업그레이드를 위해 서비스를 준비합니다Teams](upgrade-prepare-environment-prepare-service.md) |
| **2** | **특히 실시간 Teams 시나리오에 대한 네트워크 최적화** | 오디오, 비디오 또는 모임을 배포하는 경우 이러한 추가 단계를 수행하여 해당 기능에 대한 네트워크를 최적화합니다. | [네트워크로 업그레이드할 Teams](prepare-network.md) |
| **3** | **조직 변경 준비 평가 및 팀워크 시나리오 정의** | 사용자 채택을 용이하고 가속화하기 위해 올바른 가치 메시징 및 교육 수준을 준비하기 위해 사용자 기반을 이해합니다. | [조직 변경 준비](upgrade-org-change-readiness.md#organizational-change-readiness) |
| **4** | **사용자 준비 계획을 준비하여 사용자를 통신, 학습 및 지원하는 방법을 정의합니다.** | 통신, 교육 및 지원 계획을 개인 설정하여 새로운 기술에 대한 최적의 받아들이기 기능을 보장합니다. | [사용자 준비 계획 준비](upgrade-user-readiness.md)<br><br>[업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **5** | **보류 중인 시작을 Microsoft Teams** | 사용자가 포함된 것으로 느끼고, 혼란을 줄이고, 흥분을 발생하도록 조기 통신합니다. | [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **6** | **IT 직원을 준비하여 Teams** | 기술 및 지원 직원이 기술 환경을 준비하고 지원하기 위해 필요한 모든 것이 Teams. | [IT 직원을 준비하여 Microsoft Teams](upgrade-prepare-it-pros.md) <br><br> [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |

### <a name="pilot-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>파일럿: 파일럿을 실행하여 조직이 준비가 됐는지 확인하고 최적의 여정을 알릴 수 Teams

| 단계 | &nbsp; | 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **파일럿 로지스틱 개요** | 조직의 업그레이드 또는 공존 준비의 유효성을 검사하기 위해 공식 파일럿 로지스틱을 정의합니다. | [파일럿 로지스틱 개요](pilot-essentials.md#1-outline-pilot-logistics) |
| **2** | **파일럿 참가자 선택 및 테스트 시나리오** | 팀워크 시나리오의 유효성을 검사하고 준비를 Teams 사용자를 식별합니다. | [파일럿 참가자 선택 및 테스트 시나리오](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
| **3** | **테스트 계획 및 피드백 설문 조사 디자인** | 참가자가 완료할 명확히 정의된 작업과 피드백을 공유할 수 있는 방법을 식별합니다. | [테스트 계획 및 피드백 설문 조사 디자인](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
| **4** | **파일럿 통신 계획 만들기** | 파일럿 참가자에게 무슨 일이 일어나고, 언제, 왜, 무엇이 예상되는지 교육합니다. | [통신 계획 만들기](pilot-essentials.md#4-create-your-communications-plan)<br><br>[업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **5** | **파일럿 수행** | 파일럿을 시작하고, 진행 상황을 추적하고, 파일럿 결과를 최적화하기 위해 필요한 경우 다시합니다. | [파일럿 수행](pilot-essentials.md#5-conduct-your-pilot) |
| **6** | **학습 평가 및 진행 계획 평가** | 목표에 대한 분석에 대한 사용자 피드백, 네트워크 통계 및 지원 티켓을 수집하고 진행 계획을 확인합니다. | [학습 평가 및 진행 계획 평가](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan)

### <a name="deploy-run-teams-in-coexistence-with-skype-for-business"></a>배포: Teams 함께 비즈니스용 Skype

| 단계 |&nbsp;  | 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **공식 출시를 Teams** | 준비가 된 경우 공식 출시 공지를 보내 흥분과 Teams 생성합니다. | [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **2** | **업그레이드 수행** | 수행되는 단계는 현재 배포에 따라 비즈니스용 Skype. | [업그레이드 수행](upgrade-to-teams.md) |
| **3** | **로드맵에 대한 Teams 계속 알려드릴 수 있습니다.** | 조직이 Teams 올바른 시기를 식별하기 위해 로드맵을 모니터링하여 Teams. | [Teams 로드맵](https://aka.ms/teamsroadmap) |
| **4** | **추가 통신을 보내고 Teams 챔피언에게 참여하여 Teams** | 지속적인 통신 및 챔피언을 통해 사용자 채택을 장려하고 Teams 흥분을 유지해야 합니다. | [Microsoft 365 챔피언 프로그램](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>업그레이드 

**으로** 공식 Teams. 사용자를 업그레이드할 때 사용자만 모드로 Teams 합니다. Teams 채팅, 모임, 통화 및 공동 작업을 위한 기본 앱으로 설정하고 앱에 대한 비즈니스용 Skype 사용할 수 없습니다. 이 단계의 기술적인 측면은 매우 간단하지만 변경이 사용자 경험에 영향을 미치고 사용자가 공식적으로 활동을 비즈니스용 Skype 시간을 Teams. 다른 클라이언트와 다른 환경을 갖는 사용자를 줄이기 위해 종단간 업그레이드 기간을 45일로 제한합니다.

### <a name="upgrade-implement-your-upgrade-from-skype-for-business-to-teams"></a>업그레이드: 업그레이드를 비즈니스용 Skype 구현합니다Teams

| 단계 |&nbsp;  | 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **위에서 설명한 업그레이드 전 작업을 완료한지 확인** | 모든 계획 및 준비 작업의 완료를 확인하여 업그레이드 성공을 보장하는 데 도움이 됩니다. | 위의 모든 |
| **2** | **첫 번째 업그레이드 그룹의 사용자에게 통신 시작** | 업그레이드가 시작되고 있는 경우 사용자에게 알리고 프로세스 전반에 걸쳐 정보를 계속 알려야 합니다. | [사용자 준비 계획 준비](upgrade-user-readiness.md) <br><br> [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **3** | **첫 번째 업그레이드 그룹의 사용자만 Teams 공존 모드 사용** | 기술 사용자 마이그레이션을 수행하기 위해 비즈니스용 Skype 환경에 적합한 단계를 수행합니다. | [온라인에서 비즈니스용 Skype 업그레이드합니다Teams](upgrade-to-Teams-execute-SkypeforBusinessOnline.md) <br><br>[비즈니스용 Skype 프레미스에서 Teams](upgrade-to-Teams-execute-SkypeforBusinessHybridOnprem.md)
| **4** | **롤링 주기에서 나머지 업그레이드 그룹에 대한 이전 업그레이드 작업을 반복합니다.** | 계획에 따라 지속적인 통신 계획을 계속 진행하고 사용자 그룹을 업그레이드합니다. | |
| **5** | **모든 사용자에게 업그레이드 후 피드백 설문 조사 보내기** | 피드백 설문 조사를 사용하여 사용자로부터 피드백 및 인사이트를 캡처합니다. | [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>업그레이드 후

**을 통해** 비즈니스 Teams. 조직이 완전히 업그레이드된 Teams 목표에 대한 성공을 평가하고 추진을 계속할 계획을 구현합니다. 

### <a name="operate-measure-the-success-of-your-upgrade"></a>작동: 업그레이드의 성공 측정

| 단계 | &nbsp; | 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **초기 업그레이드 성공 평가** | 업그레이드 전 단계에서 설정한 목표에 대해 진행률을 평가합니다. | [Project 목표](upgrade-define-project-scope.md#project-goals) |
| **2** | **추적되지 않는 모든 목표에 대한 완화 계획 구현** | 충족되지 않는 목표에 대한 완화 또는 과정 수정 전략을 정의합니다. | [Project 목표](upgrade-define-project-scope.md#project-goals) |
| **3** | **네트워크 상태 및 품질 모니터링** | 긍정적인 사용자 환경을 보장하고 지원 데스크에 대한 호출을 줄일 수 있도록 품질 검사 및 모니터링 계획을 구현합니다. | [네트워크 상태 및 품질 모니터링](continue-journey.md#monitor-for-network-health-and-quality) |
| **4** | **사용자 모멘텀 및 채택을 주도합니다.** | 지속적인 채택 계획을 통해 사용자 채택을 장려하고 Teams 기대를 유지해야 합니다. | [사용자 모멘텀 및 채택을 주도합니다.](continue-journey.md#drive-user-momentum-and-adoption) |
| **5** | **새 기능에 대한 준비** | 새로운 혁신 및 제품 개선을 위한 변경 주기를 설정하여 최대 가치를 실현합니다. | [새 기능에 대한 준비](continue-journey.md#prepare-for-new-functionality)


> [!Note]
> 업그레이드 콘텐츠는 지속적으로 발전하고 있습니다. 최신 지침은 다시 확인한 다음, Teams [를 참조하세요.](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog) 

> [!Important]
> 비즈니스용 Skype Online은 2021년 7월 31일에 서비스가 종료되며 이후에는 더 이상 액세스할 수 없게 되거나 지원되지 않습니다. 혜택 현실화를 최대화하고 조직에서 업그레이드를 구현할 적절한 시간을 확보하기 위해 현재 업그레이드를 위한 여정을 Microsoft Teams 권장됩니다. 성공적인 업그레이드는 기술 및 사용자 준비를 일치시 하도록 설정하기 때문에 다음 지침을 활용하여 업그레이드를 진행하는 Microsoft Teams.