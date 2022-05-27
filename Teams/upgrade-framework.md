---
title: 업그레이드 프레임워크 정보 - Teams 비즈니스용 Skype
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 검증된 성공 프레임워크를 사용하여 비즈니스용 Skype Teams 조직의 업그레이드 과정을 지원합니다.
ms.localizationpriority: medium
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
ms.openlocfilehash: 0cfc8a3855da45b80ac5cd97d273b9f6c1d90ded
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681969"
---
# <a name="about-the-upgrade-framework"></a>업그레이드 프레임워크 정보

업그레이드 과정에서 추측을 수행하기 위해 변경 사항을 구현하기 위한 검증된 프레임워크를 사용했습니다. 아래와 같이 프레임워크의 각 단계는 이전 단계를 기반으로 하며 최적의 결과를 얻으려면 단계를 순서대로 따르는 것이 좋습니다.  

먼저 올바른 관련자를 모으고 업그레이드 계획(예: 범위, 목표 및 타임라인)을 정의합니다. 계획이 준비되면 기술 환경과 최종 사용자가 Teams 준비가 되는지 확인합니다. 그런 다음, 준비가 되면 파일럿에서 조직 전체 업그레이드로 이동하는 단계별로 업그레이드를 구현합니다. 조직이 Teams 상태이면 품질을 모니터링하고 사용자 채택을 가속화하는 운영 계획을 수립합니다.

![업그레이드 경험 프레임워크의 그림.](media/upgrade-banner-main.png "프로젝트가 올바른 프로젝트 팀과 함께 성공하도록 설정되어 있는지 확인합니다. 프로젝트 범위, 목표 및 타임라인을 정의합니다. 기술 및 사용자 준비 상태를 모두 확인합니다. 롤아웃 계획을 실행합니다. 결과를 최대화하기 위한 모멘텀을 유지합니다.")

관련 페이지에서 이 프레임워크 그래픽을 찾아 업그레이드 프로세스의 위치를 확인합니다.

## <a name="sample-upgrade-timeline"></a>샘플 업그레이드 타임라인

업그레이드 과정은 변경 계획을 시작할 때 시작됩니다. 아래는 성공 프레임워크를 지침으로 활용하여 업그레이드를 계획하고 준비하는 업그레이드 전 단계에서 업그레이드를 통해 그리고 업그레이드 후 운영 단계로 이동하여 결과를 유지하고 증폭하도록 설계된 샘플 타임라인입니다. 

> [!NOTE]
> Teams 여정에는 여러 [모드](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)를 활용하고 서로 다른 시간에 사용자 그룹을 업그레이드하는 작업이 포함될 수 있으므로 Teams 통해 추진력을 유지하면서 사용자 업그레이드 환경을 제어할 수 있습니다.  

업그레이드 여정이 어떻게 전개될지 보여 주기 위해 비즈니스용 Skype Online에서 아일랜드 Teams 모드로의 여정을 정의하는 샘플 계획을 아래 제공했습니다. 또한 샘플 계획은 사용자를 4개의 업그레이드 그룹 또는 코호트로 나눈 조직을 간략하게 설명합니다. 이를 템플릿으로 사용하여 사용할 다양한 [모드](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)와 사용자를 세분화할 업그레이드 그룹 수를 통합하여 Teams 위한 특정 여정을 포함하도록 계획을 사용자 지정합니다. 

## <a name="pre-upgrade"></a>업그레이드 전

**Teams 위해 조직을 준비합니다**. Teams 성공적으로 업그레이드할 수 있도록 준비에 적절한 시간을 할당하는 것이 중요합니다. 조직에서 Teams 가치를 빠르게 실현할 수 있을 뿐만 아니라 Teams 준비되는 즉시 비즈니스용 Skype 업그레이드를 가속화할 수 있습니다. 비즈니스용 Skype 함께 Teams 이미 사용하도록 설정한 경우 사용자를 Teams 업그레이드하기 전에 이러한 업그레이드 전 활동을 검사점으로 사용하여 조직의 준비 상태를 확인합니다. 

> [!TIP]
> 샘플 업그레이드 프로젝트 계획 및 파일럿 테스트 계획 외에도 통신 및 사용자 설문 조사와 같은 템플릿 사용자 준비 자료에 대한 업그레이드 [성공 키트](https://aka.ms/UpgradeSuccessKit) 를 다운로드합니다. 키트에서 사용할 수 있는 항목은 아래 목록에 별표(*)로 표시됩니다.

### <a name="plan-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>계획: 조직이 장기적인 성공을 위해 설정되도록 업그레이드 계획 만들기

| 단계 |&nbsp;| 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **관련자 정의** | 업그레이드 성공에 대한 책임을 프로젝트 팀 구성원에게 할당합니다. | [관련자 참여](upgrade-enlist-stakeholders.md) |
| **2** | **프로젝트 비전 및 범위 정의** | "큰 그림" 비전과 현재 프로젝트 범위를 디자인하여 업그레이드 과정을 위한 청사진을 만듭니다. | [Project 비전](upgrade-define-project-scope.md#project-vision) <br> <br>[Project 범위](upgrade-define-project-scope.md#project-scope) |
| **3** | **프로젝트 목표 정의** | 프로젝트 성공뿐만 아니라 진행률을 측정할 수 있는 목표 목표를 설정합니다. | [Project 목표](upgrade-define-project-scope.md#project-goals) |
| **4** | **위험 및 완화 계획 식별** | 문제가 발생할 경우 프로젝트를 신속하게 다시 진행할 수 있도록 완화 계획을 수립합니다. | [위험 및 완화](upgrade-define-project-scope.md#risks-and-mitigation) |
| **5** | **타임라인 정의** | 프로젝트가 시간과 예산에 맞게 유지되도록 타임라인 및 주요 중요 시점을 설정합니다. | [타임 라인](upgrade-define-project-scope.md#timeline) <br><br> [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **6** | **적절한 비즈니스용 Skype 정의하고 업그레이드 및 공존 전략을 Teams.** | 비즈니스용 Skype 조직의 Teams 가장 적합한 경로를 보장하기 위해 여정을 매핑합니다. | [Microsoft Teams 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md) <br><br>[전화 시스템 및 PSTN 연결 옵션 이해](cloud-voice-landing-page.md)<br><br>  [업그레이드 여정 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md) |


### <a name="prepare-evaluate-your-organizations-readiness-for-teams"></a>준비: Teams 대한 조직의 준비 상태 평가

| 단계 |&nbsp;  | 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **환경 평가 및 기술 온보딩 Teams 완료** | 사용자 환경을 최적화하고 시간이 지남에 따라 업그레이드를 용이하게 하는 데 도움이 되도록 환경이 Teams 준비가 되었는지 확인합니다. | [Teams 업그레이드하기 전에 환경을 평가합니다](upgrade-plan-journey-evaluate-environment.md).<br><br> [Teams 업그레이드할 서비스 준비](upgrade-prepare-environment-prepare-service.md) |
| **2** | **특히 실시간 미디어 시나리오에서 Teams 위한 네트워크 최적화** | 오디오, 비디오 또는 모임을 배포하는 경우 이러한 추가 단계를 수행하여 해당 기능에 맞게 네트워크를 최적화합니다. | [Teams 업그레이드할 네트워크 준비](prepare-network.md) |
| **3** | **조직 변경 준비 상태 평가 및 팀워크 시나리오 정의** | 사용자 채택을 촉진하고 가속화하기 위해 올바른 가치 메시징 및 교육 수준을 준비하도록 사용자 기반을 이해합니다. | [조직 변경 준비 상태](upgrade-org-change-readiness.md#organizational-change-readiness) |
| **4** | **사용자 통신, 학습 및 지원 방법을 정의하는 사용자 준비 계획 준비** | 커뮤니케이션, 교육 및 지원 계획을 개인 설정하여 새 기술에 대한 최적의 수용성을 보장합니다. | [사용자 준비 계획 준비](upgrade-user-readiness.md)<br><br>[업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **5** | **보류 중인 Microsoft Teams 시작 발표** | 사용자가 포함감을 느끼고, 혼란을 줄이고, 흥분을 유발할 수 있도록 조기에 커뮤니케이션합니다. | [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **6** | **IT 직원이 Teams 준비** | 기술 및 지원 담당자에게 준비에 필요한 모든 것이 있는지 확인하고 Teams 위한 기술 환경을 지원합니다. | [IT 직원이 Microsoft Teams 준비](upgrade-prepare-it-pros.md) <br><br> [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |

### <a name="pilot-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>파일럿: 파일럿을 실행하여 조직이 준비되어 있는지 확인하고 최적의 Teams

| 단계 | &nbsp; | 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **파일럿 물류 개요** | 조직의 업그레이드 또는 공존 준비 상태를 확인하는 데 도움이 되는 공식 파일럿 물류를 정의합니다. | [파일럿 물류 개요](pilot-essentials.md#1-outline-pilot-logistics) |
| **2** | **파일럿 참가자 및 테스트 시나리오 선택** | 팀워크 시나리오의 유효성을 검사하고 Teams 준비 상태를 확인할 수 있는 사용자를 식별합니다. | [파일럿 참가자 및 테스트 시나리오 선택](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
| **3** | **테스트 계획 및 피드백 설문 조사 디자인** | 참가자가 완료할 명확하게 정의된 작업과 피드백을 공유할 수 있는 방법을 식별합니다. | [테스트 계획 및 피드백 설문 조사 디자인](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
| **4** | **파일럿 통신 계획 만들기** | 파일럿 참가자에게 무슨 일이 일어나고 있는지, 언제, 왜, 그리고 무엇을 기대하는지 교육합니다. | [통신 계획 만들기](pilot-essentials.md#4-create-your-communications-plan)<br><br>[업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **5** | **파일럿 수행** | 파일럿을 시작하고, 진행 상황을 추적하고, 필요에 따라 반복하여 파일럿 결과를 최적화합니다. | [파일럿 수행](pilot-essentials.md#5-conduct-your-pilot) |
| **6** | **학습 평가 및 진행 계획 평가** | 목표에 대한 분석을 위한 사용자 피드백, 네트워크 통계 및 지원 티켓을 수집하고 진행 계획을 결정합니다. | [학습 평가 및 진행 계획 평가](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan)

### <a name="deploy-run-teams-in-coexistence-with-skype-for-business"></a>배포: 비즈니스용 Skype 함께 Teams 실행

| 단계 |&nbsp;  | 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **Teams 공식 출시 발표** | Teams 준비가 되면 공식 출시 발표를 보내 흥분과 모멘텀을 생성합니다. | [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **2** | **업그레이드 수행** | 수행하는 단계는 현재 비즈니스용 Skype 배포에 따라 달라집니다. | [업그레이드 수행](upgrade-to-teams.md) |
| **3** | **Teams 로드맵에 대한 정보 유지** | Teams 로드맵을 모니터링하여 조직이 Teams 전환할 적절한 시기를 식별합니다. | [Teams 로드맵](https://aka.ms/teamsroadmap) |
| **4** | **추가 커뮤니케이션을 보내고 Teams 챔피언을 참여시켜 Teams 흥분과 채택을 촉진합니다.** | 지속적인 커뮤니케이션 및 챔피언과의 Teams 대한 사용자 채택을 장려하고 흥분을 유지합니다. | [Microsoft 365 챔피언 프로그램](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>업그레이드 

**Teams 공식적으로 이동합니다**. 사용자를 업그레이드할 때 사용자를 Teams 전용 모드로 이동합니다. Teams 채팅, 모임, 통화 및 공동 작업을 위한 기본 앱이 되며 비즈니스용 Skype 앱에 대한 액세스가 비활성화됩니다. 이 단계의 기술적 측면은 매우 간단하지만, 변경이 사용자 환경에 미칠 수 있는 영향을 고려하고 사용자가 공식적으로 비즈니스용 Skype 활동을 Teams 전환할 수 있는 시간을 허용합니다. 다른 클라이언트와 다른 환경을 가진 사용자를 줄이려면 종단 간 업그레이드 기간을 45일 정도로 제한해 보세요.

### <a name="upgrade-implement-your-upgrade-from-skype-for-business-to-teams"></a>업그레이드: 비즈니스용 Skype Teams 업그레이드 구현

| 단계 |&nbsp;  | 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **위에서 설명한 업그레이드 전 작업을 완료했는지 확인합니다.** | 모든 계획 및 준비 작업의 완료를 확인하여 업그레이드 성공을 보장하는 데 도움이 됩니다. | 위의 모든 항목 |
| **2** | **첫 번째 업그레이드 그룹에서 사용자에 대한 통신 시작** | 업그레이드가 시작되고 있음을 사용자에게 알리고 프로세스 전체에서 정보를 유지합니다. | [사용자 준비 계획 준비](upgrade-user-readiness.md) <br><br> [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |
| **3** | **첫 번째 업그레이드 그룹의 사용자에 대해서만 Teams 공존 모드를 사용하도록 설정** | 비즈니스용 Skype 환경에 적합한 단계에 따라 기술 사용자 마이그레이션을 수행합니다. | [비즈니스용 Skype Online에서 Teams](upgrade-to-Teams-execute-SkypeforBusinessOnline.md) <br><br>[비즈니스용 Skype 온-프레미스에서 Teams 업그레이드](upgrade-to-Teams-execute-SkypeforBusinessHybridOnprem.md)
| **4** | **롤링 주기에 나머지 업그레이드 그룹에 대해 이전 업그레이드 작업을 반복합니다.** | 계속 진행 중인 통신 계획을 추진하고 계획에 따라 사용자 그룹을 업그레이드합니다. | |
| **5** | **모든 사용자에게 업그레이드 후 피드백 설문 조사 보내기** | 피드백 설문 조사를 사용하여 사용자의 피드백과 인사이트를 캡처합니다. | [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>업그레이드 후

**Teams 사용하여 비즈니스 가치를 최대화** 합니다. 조직이 Teams 완전히 업그레이드된 후 시간을 내어 목표에 대해 성공을 평가하고 추진력을 지속할 계획을 구현합니다. 

### <a name="operate-measure-the-success-of-your-upgrade"></a>운영: 업그레이드 성공 측정

| 단계 | &nbsp; | 요약 | 리소스 |
|------|--|---------|----------|
| **1** | **초기 업그레이드 성공 평가** | 업그레이드 전 단계에서 설정한 목표에 대해 진행률을 평가합니다. | [Project 목표](upgrade-define-project-scope.md#project-goals) |
| **2** | **궤도에 있지 않은 모든 목표에 대한 완화 계획 구현** | 충족되지 않는 목표에 대한 완화 또는 과정 수정 전략을 정의합니다. | [Project 목표](upgrade-define-project-scope.md#project-goals) |
| **3** | **네트워크 상태 및 품질 모니터링** | 긍정적인 사용자 환경을 보장하고 지원 센터에 대한 호출을 줄이는 데 도움이 되는 품질 검사 및 모니터링 계획을 구현합니다. | [네트워크 상태 및 품질 모니터링](continue-journey.md#monitor-for-network-health-and-quality) |
| **4** | **사용자 모멘텀 및 채택 추진력** | 지속적인 채택 계획을 사용하여 사용자 채택을 장려하고 Teams 대한 흥분을 유지합니다. | [사용자 모멘텀 및 채택 추진력](continue-journey.md#drive-user-momentum-and-adoption) |
| **5** | **새 기능 준비** | 새로운 혁신 및 제품 개선을 위한 변경 주기를 설정하여 최대 가치를 실현합니다. | [새 기능 준비](continue-journey.md#prepare-for-new-functionality)


> [!Note]
> 업그레이드 콘텐츠는 지속적으로 진화하고 있습니다. 최신 지침을 다시 확인하고 [Teams 블로그](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)를 읽어보세요. 

> [!Important]
> 비즈니스용 Skype Online은 2021년 7월 31일에 은퇴했습니다. 혜택 실현을 최대화하고 조직에서 업그레이드를 구현할 적절한 시간을 갖도록 하려면 오늘 Microsoft Teams 위한 여정을 시작하는 것이 좋습니다. 성공적인 업그레이드는 기술 및 사용자 준비 상태를 조정하므로 Microsoft Teams 여정을 탐색할 때 여기에 있는 지침을 활용해야 합니다.