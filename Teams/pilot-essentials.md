---
title: 사용자 파일럿을 수행하여 조직에서 Microsoft Teams 평가하고 테스트합니다.
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 파일럿을 Microsoft Teams 계속 사용하는 동안 조직에 제공할 수 있는 모든 Teams 탐색하기 위한 비즈니스용 Skype
ms.localizationpriority: medium
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 22ee8e22f7954814aa98b43d1eac250ac38b17cd
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014612"
---
# <a name="conduct-a-user-pilot"></a>사용자 파일럿 수행

![배포 및 구현을 강조 표시하는 업그레이드 여정 다이어그램입니다.](media/upgrade-banner-deployment.png "배포 및 구현 단계에 주안점 있는 업그레이드 여정의 단계")

이 문서는 업그레이드 단계의 배포 및 구현 단계의 일부로, 효과적인 파일럿을 실행하기 위한 인사이트를 공유합니다. 계속하기 전에 다음 작업을 완료한지 확인합니다.

- [프로젝트 관계자 인리스트](upgrade-enlist-stakeholders.md)
- [프로젝트 범위 정의](./upgrade-define-project-scope.md)
- [비즈니스용 Skype 및 상호운용성을 Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [업그레이드 여정을 선택했습니다.](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [환경 준비](./upgrade-prepare-environment.md)
- [조직 준비](./upgrade-prepare-organization.md)

새 기술을 배포하면 조직에서 비용 절감, 보안 준수, 직원 만족도 및 운영 효율성과 같은 비즈니스 가치를 실현할 수 있지만 사용자의 생산성 및 조직 인프라(네트워크)에도 영향을 줄 수 있습니다. 조직 전체에서 새 기술을 사용하도록 설정하기 전에 공식 사용자 파일럿을 수행합니다. 전체 방을 그리기 전에 벽에 작은 색 패치를 그리는 것 처럼 파일럿을 수행하여 기술 및 사용자 준비의 유효성을 검사하고 문제를 식별하고 완화하며, 조직 전체의 성공적인 구현을 보장하는 데 도움이 되도록 파일럿을 수행하여 더 작은 규모로 광범위한 롤아웃을 테스트할 수 있습니다.

가장 현실적인 결과를 달성하기 위해 파일럿은 실제 사용자를 포함하고, 통신 및 공동 작업 방법을 모방하고 기술 및 사용자 환경을 모두 확인해야 합니다. 조직에서 비즈니스용 Skype Teams 나란히 실행하거나, Teams 또는 호출 또는 회의와 같은 새로운 기능을 배포하는 것을 고려하는 경우 파일럿은 조직에 대한 올바른 경로를 식별하는 데 도움이 될 수 있습니다. 때로는 롤아웃의 1단계로 간주되는 이상적인 파일럿은 이미 시작한 준비를 활용하고 대상 사용자 그룹으로 정의된 계획을 구현합니다.

|&nbsp; | &nbsp;|
|---|---|
| ![의사 결정 지점을 묘사하는 아이콘.](media/audio_conferencing_image7.png) <br/>결정 지점|<ul><li>파일럿을 사용하여 프로젝트 방향을 알려주는 방법</li></ul> |
| ![다음 단계를 묘사하는 아이콘](media/audio_conferencing_image9.png)<br/>다음 단계|<ul><li>아래 지침을 사용하여 공식 파일럿을 설계하고 실행합니다.</li></ul>|

> [!Tip]
> 샘플 [파일럿 리소스를 사용하여](https://aka.ms/UpgradeSuccessKit) 통신, 테스트 계획 및 피드백 설문 조사를 디자인하는 데 도움이 됩니다.

## <a name="1-outline-pilot-logistics"></a>1. 파일럿 로지스틱 개요

성공적인 파일럿은 시작 및 종료 [](upgrade-define-project-scope.md#project-goals) 날짜를 정의하고 성공을 측정하기 위한 목표를 명확하게 정의했습니다. 이러한 목표는 프로젝트 범위를 정의할 때 설명한처럼 광범위한 [](upgrade-define-project-scope.md)프로젝트의 범위와 일치해야 합니다. 파일럿이 끝났을 때 경로를 전달하는 데 사용됩니다. 또한 프로젝트 기간 동안 적절한 이해 관계자를 포함해야 합니다. 파일럿을 실행하고 그 영향을 평가하는 데 충분한 시간을 허용해야 합니다. 최소 30일이 권장됩니다.

소규모를 시작하고 워크로드 또는 기능을 추가하거나 추가 사용자를 추가하여 결과를 평가하고 파일럿을 다시 작업할 때 조정하는 데 시간을 내어 적절하게 파일럿에 추가합니다. 새 파일럿 기능이 로드맵에 따라 릴리스될 Teams 후속 파일럿을 실행하기로 선택할 수도 있습니다.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. 파일럿 참가자를 선택하고 시나리오를 테스트합니다.

파일럿 계획의 가장 중요한 작업 중 하나는 사려 스러운 참가자 선택입니다. 팀워크에 Teams 최적화되어 있으므로, 파일럿 참가자는 역할이나 사람만이 아니라 프로젝트 및 팀 간 작업을 기반으로 선택해야 합니다. 가장 좋은 시작점은 이해 관계자 및 부서 관리자에게 실제 프로젝트에서 유효성을 검사할 수 있는 Teams. 역할 기반 프로젝트의 예로 영업 조직과 함께 Teams 현장 구성원이 필요한 리소스에 쉽게 액세스하고 다른 필드 구성원과 인사이트를 공유할 수 있도록 하는 것이 있습니다. 프로젝트 기반 작업의 예는 마케팅, 교육, 홍보 및 이벤트 계획 팀과 제품 출시 이벤트를 조정하는 것입니다. 어떤 시나리오를 선택하든 파일럿은 IT, 교육 및 헬프데스크의 주요 사용자로 확장해야 하여 프로젝트 관리 리소스를 완전히 최적화하면서 솔루션의 유효성을 철저히 검사할 수 있습니다.

> [!Tip]
> 파일럿 그룹 Teams 선택할 때 상위 사용자도 포함해야 비즈니스용 Skype. 이러한 사용자와 함께 현재 비즈니스용 Skype 사용하는 방법을 파악한 다음, 테스트 계획을 빌드하여 현재 요구 사항을 충족할 수 Teams 수 있는지를 테스트합니다.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. 테스트 계획 및 피드백 설문 조사 디자인

성공적인 파일럿 환경을 위해 참가자에게 명확히 정의된 작업을 완료하고 피드백을 공유할 수 있는 방법을 제공합니다. 작업을 그룹화하여 사용자에게 실제 시나리오를 제공하여 일상 활동과의 연계를 시연합니다. 조직 변경 준비 평가에서 정의한 사용 사례가 테스트 [계획을](./upgrade-org-change-readiness.md) 안내합니다.

조직은 모든 기능을 한 번 파일럿하거나, 먼저 파일럿 공동 작업, 모임, 채팅 및 통화와 같은 차분한 접근 방식을 사용할 수 있습니다. 진행 상황을 추적하고 결과를 측정할 수 있는 열린 피드백 채널이 있는지 확인하세요. 미리 정의된 설문 조사를 사용하여 파일럿 결과를 쉽게 캡처하고 평가할 수 있습니다. 설문 조사 디자인은 테스트 계획의 시나리오 및 기능을 기반으로 해야 합니다.

## <a name="4-create-your-communications-plan"></a>4. 통신 계획 만들기

파일럿의 성공을 위해 파일럿 참가자에게 무슨 일이 일어나고, 언제, 왜, 무엇이 예상되는지 교육하는 것이 중요합니다. 흥분과 최대 참여를 구동하기 위해 사용자가 파일럿을 진행할 때 추가 정보를 얻을 수 있는 교육 및 지원에 대한 링크 외에도 사용자 가치 메시징을 포함해야 합니다. 다음은 파일럿 통신 계획을 시작하는 몇 가지 샘플 리소스입니다.

- [파일럿 리소스](https://aka.ms/UpgradeSuccessKit)( 전자 메일 템플릿 및 샘플 피드백 설문 조사 질문 포함)
- [사용자가](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)Teams 시작할 수 있도록 비즈니스용 Skype 빠른 시작 가이드인 비즈니스용 Skype 시작 가이드로 Teams

## <a name="5-conduct-your-pilot"></a>5. 파일럿 수행

모든 물류가 준비되어 이제 파일럿을 시작할 준비가 완료되었습니다. 파일럿을 수행하면 사용자와 통신하고 네트워크 및 사용량을 모니터링하여 네트워크 성능 및 통화 품질이 정상 상태로 유지되도록 보장하고, 참가자의 피드백을 수집하고, 지원 데스크 티켓에 대한 질문과 관련된 질문을 검토하는 Teams.

### <a name="tips-for-pilot-success"></a>팁 성공을 위한 지원

다음 팁은 파일럿의 성공을 보장하는 데 도움이 될 수 있습니다.

- 파일럿을 시작하기 전에 모든 파일럿 참가자가 적절한 [공존 모드]에 사용하도록 설정되어 있는지 확인합니다.
- https://aka.ms/SkypeToTeams-SetCoexistence)(유효성을 검사합니다.
- 매주 파일럿 전반에 걸쳐 프로젝트 관계자를 만나 사용자 피드백, 사용 데이터, 네트워크 데이터 및 헬프데스크 티켓을 검토하여 파일럿이 원활하게 실행되도록 합니다. 필요한 경우 조정합니다.

### <a name="suggested-timeline"></a>제안된 타임라인

30일 파일럿에 대한 제안된 타임라인은 다음과 같습니다.

- 파일럿 시작 1주일 전: 파일럿 사용자에게 초기 통신 보내기.
- 1일차: 파일럿 사용자에게 킥오프 통신 보내기
- 7일차: 첫 번째 주간 프로젝트 팀 검사점 모임을 개최합니다.
- 14일차: 파일럿 사용자에게 중간 지점 통신을 보내고 주간 프로젝트 팀 검사점 모임을 개최합니다.
- 21일차: 주간 프로젝트 팀 검사점 모임을 개최합니다.
- 30일차: 파일럿 사용자에게 최종 통신 보내기
- 31-45일: 파일럿 결과를 평가하고 다음 단계를 계획합니다.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. 학습 평가 및 진행 계획 평가

파일럿이 완료되면 모든 피드백 설문 조사, 최종 네트워크 통계 및 목표에 대한 분석을 위한 지원 티켓을 수집하고 진행 계획을 구현할지 여부를 결정해야 합니다. 조직이 광범위한 배포를 준비하거나 파일럿을 더 많은 사용자로 확장하려는 경우 또는 확인한 문제가 완화된 후 나중에 파일럿을 다시 찾아보려 할 수 있습니다. 파일럿은 제어된 환경에서 기술 및 사용자 결과를 예측하는 좋은 _방법입니다._ 너무 빨리 뛰어야 합니다.

결과가 표시하는 경우:

- **파일럿** 목표(예: 사용자 만족도 및 네트워크 품질)가 달성되었습니다. 롤아웃의 다음 단계를 진행할 준비가 되어 있습니다. 프로젝트의 목표에 따라 다음 중 하나일 수 있습니다.
  - 파일럿을 추가 참가자로 확장
  - [조직의 Teams(비즈니스용 Skype)와 함께 비즈니스용 Skype(섬 모드)를 사용하도록 설정](./setting-your-coexistence-and-upgrade-settings.md)
  - [조직의 일부 또는 비즈니스용 Skype 사용자 Teams(Teams 전용 모드)로 업그레이드](./setting-your-coexistence-and-upgrade-settings.md)
- **파일럿이** 원하는 결과(예: 사용자 만족도 및 네트워크 품질)를 달성하지 못했습니다. 계획을 적절하게 조정하고 파일럿을 다시 조사하는 데 시간이 걸릴 수 있습니다.

> [!Tip]
> 파일럿 참가자를 피어 챔피언으로 참가하여 새 사용자를 전도하고 온보딩할 수 있도록 Teams. 동료 챔피언은 다른 사용자와 쉽게 관련이 있으며, 자신의 경험과 학습을 공유하고 동료에게 지원 및 지침을 제공합니다. 챔피언에 [대해 자세히 알아보고](https://go.microsoft.com/fwlink/?linkid=859068) 롤아웃 내에서 챔피언을 사용하는 방법에 대해 자세히 알아보습니다.