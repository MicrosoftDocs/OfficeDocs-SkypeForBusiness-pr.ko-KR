---
title: Microsoft 팀 용 Pro 업그레이드 | 로드맵
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: 대규모 조직에 있거나 비즈니스용 Skype 배포를 많이 사용자 지정한 경우이 지침을 사용 하세요.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3d34c111302c3e8de173b4c553589ab840495118
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236040"
---
# <a name="upgrade-pro"></a>Pro 업그레이드

대규모 조직 또는 비즈니스용 Skype (예: 하이브리드 또는 클라우드 음성 배포)를 복잡 하 게 배포 하는 경우 Microsoft 실행을 비롯 한 다양 한 업그레이드 시나리오와 함께 Pro 계정을 업그레이드 하 여 더 오래 업그레이드 수명 주기 팀이 조직에 사용할 준비가 될 때까지 비즈니스용 Skype와 함께 팀.

다음과 같이 3 단계로 분할 하 여 Pro 표지를 업그레이드 합니다.

|**[업그레이드 전](#pre-upgrade)** |**[업그레이드](#upgrade)** |**[업그레이드 후](#post-upgrade)** |
|---|---|---|
|팀의 가치 실현<ul><li>환경 준비</li><li>공동 작업, 모임, 통화를 위한 팀 채택</li><li>시간 경과에 따른 비즈니스용 Skype의 팀 업그레이드 계획</li></ul> |비즈니스용 Skype에서 사용자 마이그레이션<ul><li>사용자에 게 알림 및 준비</li><li>팀 전용 모드로 사용자 이동</li><li>목표에 대 한 사용 현황 진행 추적</li></ul> | ROI 확장할 <ul><li>네트워크 상태/품질 모니터링</li><li>사용자의 흥미로운 유지 관리</li><li>진행 중인 팀의 혁신에 대 한 계획</li></ul>|

> [!NOTE]
> 팀으로의 여행에는 다양 한 시간에 여러 [모드](https://aka.ms/skypetoteams-coexist) 를 이용 하 고 사용자 그룹을 업그레이드 하는 작업이 포함 될 수 있으며,이를 통해 팀과 통해 계속 앞서을 유지 하면서 사용자 업그레이드 환경을 제어할 수 있습니다. <br><br>
업그레이드의 여행에 unfold 하는 방법을 설명 하기 위해 비즈니스용 Skype에서 **아일랜드** 모드로의 여행에 대 한 여행을 팀 전용으로 정의 하는 샘플 계획을 제공 했습니다. 또한 샘플 계획에서는 사용자를 네 가지 업그레이드 그룹 또는 _cohorts_으로 나눈 조직을 간략하게 설명 합니다. 이 서식 파일을 사용 하 여 팀에 게 특정 한 여행에 맞게 계획을 사용자 지정 하 여 사용할 다양 한 [모드](https://aka.ms/skypetoteams-coexist) 와 사용자가 세그먼트화 할 업그레이드 그룹의 수를 통합 합니다.

## <a name="pre-upgrade"></a>업그레이드 전

**팀을 위해 조직을 준비 합니다.** 팀으로 성공적으로 업그레이드 하려면 준비에 적절 한 시간을 할당 하는 것이 중요 합니다. 조직에서 팀의 가치를 신속 하 게 실현 하도록 할 수 있을 뿐만 아니라 팀이 준비 되는 즉시 비즈니스용 Skype에서 업그레이드를 가속화할 수 있게 됩니다. 팀에 대해 계획 된 개선 사항에 대 한 [로드맵을](https://aka.ms/O365Roadmap) 모니터링 합니다. 이렇게 하면 조직의 올바른 업그레이드 시간 표시 막대를 식별 하는 데 도움이 됩니다. 이미 비즈니스용 Skype와 함께 팀을 사용 하도록 설정한 경우에는 이러한 사전 업그레이드 작업을 검사점으로 사용 하 여 사용자를 팀으로 업그레이드 하기 전에 조직의 준비 상태를 확인 합니다.

> [!Tip]
> 예제 업그레이드 프로젝트 계획 및 파일럿 테스트 계획 외에, 커뮤니케이션 및 사용자 조사 등의 서식 파일 사용자 준비 자료에 대 한 [업그레이드 성공 키트](https://aka.ms/UpgradeSuccessKit) 를 다운로드 합니다. 키트에서 사용할 수 있는 항목은 아래 목록에서 별표 (\*)로 표시 됩니다.

### <a name="days-1ndash7-create-your-upgrade-plan-to-help-ensure-your-organization-is-set-up-for-long-term-success"></a>일 1&ndash;7: 조직이 장기간 성공 하도록 설정할 수 있도록 업그레이드 계획 만들기

|단계만||요약 |자원별 |
|---|---|---|---|
|**raid-1** |**관련자 정의** |프로젝트의 범위를 고려 하 고 기술 관련 관련자와 사용자가 책임을 부여 하 고 성공 하도록 준비 합니다. |[관련자 참여](upgrade-enlist-stakeholders.md) |
|**2** |**프로젝트 비전 정의** |여러분의 비전은 "" 대규모 사진 "" 또는 "이 프로젝트를 진행 하는 이유는 무엇 인가요?" 라는 질문에 대 한 답을 제공 하는 궁극적인 종료 상태입니다. 이상적인 비전은 조직의 비즈니스 드라이버와 사용자 가치-전망을 추가 하는 것을 다룹니다. |[프로젝트 비전](upgrade-define-project-scope.md#project-vision) |
|**3-4** |**프로젝트 범위 정의** |비전은 다양 한 단계를 통해 시간에 따라 실현 될 수 있습니다. 프로젝트 범위는 지금 프로젝트의 초점을 정의 하 고, 프로젝트 팀이 현재 작업을 중점적으로 진행 하 여 장기간의 비전을 실현할 수 있도록 하는 역할을 합니다. |[프로젝트 범위](upgrade-define-project-scope.md#project-scope) |
|**4(tcp/ipv4)** |**프로젝트 목표 정의** |목표는 원하는 결과를 정의 하 고 프로젝트의 성공 여부를 측정할 수 있도록 합니다. 목표는 목표 및 키 결과 (OKRs)로 정의 될 수 있으며, 프로젝트 성공의 측정값은 키 성공 표시기 (KSIs)로 정의할 수 있습니다. 사용자가 소유권을 인식 하 고 정의 된 프로젝트 작업에 이러한 측정값을 정렬 하는 데 도움이 되도록, OKRs와 KSIs를 정의 하는 것은 프로젝트 관련자 로부터 완전히 참여 하는 것이 중요 합니다. 목표에는 기술 및 사용자 중심 성공의 혼합이 포함 되어야 합니다. |[프로젝트 목표](upgrade-define-project-scope.md#project-goals) |
|**5mb** |**위험 및 완화 계획 식별** |잠재적 위험을 사전 평가 하 고 발생할 수 있는 문제를 극복 하는 완화 계획을 정의 하는 것이 중요 하므로 프로젝트는 목표를 계속 진행할 수 있습니다. 위험 등록기는 프로젝트 위험을 추적 하는 훌륭한 도구 이며, 잠재적인 영향과 잠재적 영향, 완화 계획을 캡처할 수 있습니다. 다음 표에서는 샘플 위험 등록기를 보여 줍니다. |[위험 및 완화](upgrade-define-project-scope.md#risks-and-mitigation) |
|**26** |**시간 표시 막대 정의** |주요 중요 시점 (예: 모든 사용자에 대해 비즈니스용 Skype를 사용 하도록 설정 또는 사용자의 단계적 업그레이드 시작)에 대 한 시간 표시 막대를 설정 합니다. 정의 된 시간 표시 막대를 사용 하면 프로젝트 팀이 일관성 있는 종료 상태를 유지 하 고 적절 한 작업 진행 일정을 알려 주므로 프로젝트를 추적할 수 있습니다. 가속 되지 않는 시간 표시 막대 (작업 목록 일 수 있음)를 고려 합니다. |[시간대](upgrade-define-project-scope.md#timeline)<br><br>[성공 키트 업그레이드](https://aka.ms/UpgradeSuccessKit)|
|**7** |**비즈니스에 적합 한 Skype 및 팀 업그레이드 및 공존 전략 정의** |기존 비즈니스용 Skype 고객의 경우 팀으로의 완벽 한 전환에는 약간의 시간이 걸릴 수 있습니다. 그러나 사용자가 비즈니스용 Skype와 함께 팀을 사용할 수 있도록 하 여 지금 팀의 가치를 현실화 하는 것이 시작 됩니다. 두 앱 사이에 일부 겹치는 기능이 있는 경우 조직에 적합 한 경로를 결정 하는 데 도움이 되도록 사용 가능한 공존 및 업그레이드 모드를 검토 하는 것이 좋습니다. 최상의 환경을 위해서는 모든 사용자에 게 광범위 하 게 배포 하기 전에 계획 된 공존 전략을 시험 운용 하세요. |[Microsoft 팀 및 비즈니스용 Skype 공존 및 상호 운용성 이해](teams-and-skypeforbusiness-coexistence-and-interoperability.md)<br><br>[업그레이드 여행 선택](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)|

### <a name="days-8ndash15-evaluate-your-organizations-readiness-for-teams"></a>일 8&ndash;15: 조직에서 팀의 준비 상태 평가

|단계만 | |요약 |자원별 |
|---|---|---|---|
|**raid-1** |**기존 환경을 평가 하 여 위험 및 요구 사항 식별** |환경을 평가 하 여 전체 배포에 영향을 주는 위험 및 요구 사항을 식별 합니다. 이러한 항목을 사전에 확인 하면 계획을 조정 하 여 성공 여부를 확인할 수 있습니다. |[팀으로 업그레이드 하기 전에 환경 평가](upgrade-plan-journey-evaluate-environment.md) |
|**2** |**Office 365 및 팀 기술 온 보 딩 완료** |팀과 공동 작업 및 음성 기능을 완벽 하 게 사용할 수 있도록 작업 및 활동을 식별 하는 기존 온 보 딩 검사를 활용 합니다. |[팀으로 업그레이드 하기 위해 서비스 준비](upgrade-prepare-environment-prepare-service.md) |
|**3-4** |**특히 실시간 미디어 시나리오용으로 팀 네트워크 최적화** |오디오, 비디오 또는 모임을 배포 하는 경우 몇 가지 추가 단계를 수행 하 여 해당 기능에 맞게 네트워크를 최적화할 수 있습니다. 팀은&mdash;&mdash;대부분의 네트워크 조건에 맞게 조정 하 여 더 나은 성능을 가질 수 있는 오디오 및 비디오 기술 (코덱)을 사용 합니다. 최적의 성능을 유지 하려면 팀을 위해 네트워크를 준비 해야 합니다. |[팀으로 업그레이드 하기 위한 네트워크 준비](upgrade-prepare-environment-prepare-network.md) |
|**4(tcp/ipv4)** |**조직 변경 준비 사항 평가** |팀에서 가치를 실현 하려면 사용자가 실제로이를 사용 해야 합니다. 팀을 사용 하는 것은 목표를 달성 하는 것을 보장 하지 않습니다. 사용자는 다양 한 사용 사례와 다양 한 학습 스타일을 사용할 수 있으며 다양 한 속도로 새로운 기술에 적응 합니다. 사용자 기반을 이해 하면 사용자 채택을 편리 하 고 신속 하 게 사용할 수 있도록 적절 한 수준의 교육을 준비할 수 있습니다. |[조직 변경 준비](upgrade-org-change-readiness.md#organizational-change-readiness) |
|**5mb** |**사용자의 커뮤니케이션, 교육 및 지원 방법을 정의 하는 사용자 준비 계획 준비** |새로운 기술에 대 한 최적의 receptiveness을 보장 하기 위해, 사용자가 정의한 가상 사용자 및 cohorts에 맞게 광범위 한 메시지 (비전/값 메시징 및 유니버설 사용 사례 통합)와 메시징, 교육 및 지원을 조합 하 여 사용 합니다. 또한 적절 하 게 laggards 합니다. 이 맞춤형 계획은 사용자가 팀과 더 빠르게 연관 시킬 수 있도록 하는 동시에 사용자의 요구를 이해 하는 데 도움을 줍니다. 이는 팀으로 시험, 등록, 업그레이드 하는 데 사용 될 수 있습니다. |[사용자 준비 계획 준비](upgrade-user-readiness.md)<br><br>[성공 키트 업그레이드](https://aka.ms/UpgradeSuccessKit)<br><br>[팀 영상 교육](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?wt.mc_id=otc_home)<br><br>[비즈니스용 Skype에서 팀으로 전환](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964) |
|**26** |**Microsoft 팀의 보류 중인 시작 알림** |사용자와의 통신은 사용자에 게 제공 되는 것이 편리 하며, Microsoft 팀에 대 한 혼란을 최소화 하 여 비즈니스용 Skype에서 지속적으로 업그레이드 속도를 향상 시킵니다. | [성공 키트 업그레이드](https://aka.ms/UpgradeSuccessKit) |
|**7** |**팀을 위한 IT 직원 준비** |Office 365 테 넌 트 관리자, 기술 팀장 및 지원 센터는 고품질 사용자 환경을 추진 하는 데 책임이 있습니다. 여기에는 네트워크가 팀을 지원할 준비가 되어 있는지 확인 하 고, 사용자를 위해 팀을 구성 하 고, 발생할 수 있는 문제를 효과적으로 해결 하 고 해결할 수 있습니다. |[Microsoft 팀을 위한 IT 직원 준비](https://docs.microsoft.com/microsoftteams/upgrade-prepare-it-pros)<br><br>[성공 키트 업그레이드](https://aka.ms/UpgradeSuccessKit) |

### <a name="days-16ndash60-run-a-pilot-to-confirm-that-your-organization-is-ready-and-inform-your-optimal-journey-to-teams"></a>일 16&ndash;60: 파일럿을 실행 하 여 조직이 준비 된 상태 인지 확인 하 고 팀에 게 최적의 여행에 대해 알립니다.

|단계만 | |요약 |자원별 |
|---|---|---|---|
|**raid-1** |**시범 물류 개요** |성공적인 파일럿은 시작 및 종료 날짜를 정의 하 고 성공 여부를 측정할 목적으로 명확 하 게 정의 되었습니다. 이러한 목표는 광범위 한 프로젝트의 범위와 맞춰야 하며 파일럿이 끝난 후에 경로를 전달 하는 데 사용 됩니다. |[시범 물류 개요](pilot-essentials.md#1-outline-pilot-logistics) |
|**2** |**파일럿 참가자 및 테스트 시나리오 선택** |역할 또는 가상 사용자를 기준으로 한 것이 아니라 프로젝트와 팀 간 작업에 따라 파일럿 참가자를 선택 합니다. 파일럿은 IT, 교육, 기술 지원팀의 주요 사용자에 게 확대 되어야 하므로 프로젝트 관리 리소스를 완전히 최적화 하는 동안 솔루션을 철저히 확인할 수 있으므로 비즈니스 사용자를 위한 최고의 Skype를 포함 해야 합니다. |[파일럿 참가자 및 테스트 시나리오 선택](pilot-essentials.md#2-select-your-pilot-participants-and-test-scenarios) |
|**3-4** |**테스트 계획 및 피드백 설문 조사 디자인** |참가자가 완료 해야 하는 명확 하 게 정의 된 작업과 해당 사용자의 피드백을 공유 하는 방법을 식별 합니다. 작업을 그룹화 하 여 일상 활동에 대 한 관련성을 보여 주는 실제 시나리오를 사용자에 게 제공할 수 있습니다. |[테스트 계획 및 피드백 설문 조사 디자인](pilot-essentials.md#3-design-your-test-plan-and-feedback-survey) |
|**4(tcp/ipv4)** |**파일럿 통신 계획 만들기** |진행 상황, 시기, 이유, 예상 되는 상황에 따라 파일럿 참가자를 교육 합니다. 원하는 시간과 최대 참가를 하려면 사용자에 게 교육 및 지원에 대 한 링크 외에도 파일럿을 진행 하는 동안 사용자가 추가 정보를 얻을 수 있도록 하는 방법에 대해 설명 합니다. |[의사 소통 계획 만들기](pilot-essentials.md#4-create-your-communications-plan)<br><br>[성공 키트 업그레이드](https://aka.ms/UpgradeSuccessKit) |
|**5mb** |**시험 운용 실시** |시험 운용에는 사용자와의 통신, 네트워크 성능 및 통화 품질이 양호한 상태를 유지 하 고, 참가자 로부터 피드백을 수집 하 고, 헬프 데스크 티켓을 검토 하 여 관련 질문에 대 한 질문이 포함 됩니다. 성과. |[시험 운용 실시](pilot-essentials.md#5-conduct-your-pilot) |
|**26** |**학습이 평가 및 전달 진행 계획 평가** |모든 피드백 설문 조사, 최종 네트워크 통계, 목표에 대 한 지원 티켓을 수집 하 고 진행 중 계획을 구현할지 여부를 결정 합니다. |[학습이 평가 및 전달 진행 계획 평가](pilot-essentials.md#6-assess-learnings-and-evaluate-your-go-forward-plan) |

### <a name="day-60-until-upgrade-deploy-teams-in-coexistence-with-skype-for-business"></a>60 일 업그레이드: 비즈니스용 Skype와 함께 팀 배포

|단계만 | |요약 |자원별 |
|---|---|---|---|
|**raid-1** |**팀의 공식적인 시작 알림** |팀의 조직 실행 시작에 대해 사용자와 의사 소통 하 여 인식 및 지역 가치와 혜택을 확인 합니다. 시작 이벤트 및 전자 메일을 포함 하 여 여러 형태의 통신을 고려 합니다. |[성공 키트 업그레이드](https://aka.ms/UpgradeSuccessKit) |
|**2** |**사용자에 대해 적절 한 공존 모드를 사용 하도록 설정** |단계에 따라 조직에 적합 한 공존 모드를 설정 합니다. |[공존 및 업그레이드 설정 설정](setting-your-coexistence-and-upgrade-settings.md) |
|**3-4** |**팀 로드맵에 대 한 정보 유지** |팀의 로드맵을 모니터링 하 고 조직에서 팀으로 이동할 적절 한 시간을 확인 하기 위해 조직의 준비 상태를 지속적으로 평가 합니다. |[팀 로드맵](https://aka.ms/teamsroadmap) |
|**4(tcp/ipv4)** |팀의 흥미로운 성과 채택을 **챔피언 추가 통신을 보내고 팀을 참여 시킬 수** 있습니다. |지속적으로 커뮤니케이션 및 챔피언 팀에 대해 사용자 채택을 유도 하 고 흥미로운 것을 유지 합니다. |[Microsoft 365 챔피언 프로그램](https://aka.ms/O365Champions) |

## <a name="upgrade"></a>업그레이드

**공식적인 팀으로 이동 합니다.** 사용자를 업그레이드 하는 경우 **팀만** 공존 모드로 전환 합니다. 팀은 채팅, 모임, 통화, 공동 작업을 위한 기본 앱이 되어 비즈니스용 Skype 앱에 대 한 액세스를 사용할 수 없습니다. 이 단계의 기술적 측면은 매우 간단 하지만, 변경이 사용자 환경에 미칠 수 있는 영향을 고려 하 고 사용자가 자신의 활동을 비즈니스용 Skype에서 팀으로 공식적으로 전환 하는 데 걸리는 시간을 허용 합니다. 다른 클라이언트와의 다른 경험을 사용 하는 사용자를 줄이려면 종단 간 업그레이드 창을 45 days 이상으로 제한 하십시오.

### <a name="days-1ndash45-implement-your-upgrade-from-skype-for-business-to-teams"></a>일 1&ndash;45: 비즈니스용 Skype에서 팀으로 업그레이드 구현

|단계만 | |요약 |자원별 |
|---|---|---|---|
|**raid-1** |**위에서 설명한 업그레이드 사전 작업을 완료 했는지 확인 합니다.** |모든 계획 및 준비 작업의 완료를 확인 하 여 업그레이드 성공 여부를 확인 합니다. |위의 모든 것 |
|**2** |**첫 번째 업그레이드 그룹의 사용자에 게 통신 시작** |사전, 업그레이드 이후 통신 계획 실행을 시작 하 고, 기대치를 설정 하 고, 사용자의 업그레이드 전에 팀의 혜택을 공유 합니다. |[사용자 준비 계획 준비](upgrade-user-readiness.md)<br><br>[성공 키트 업그레이드](https://aka.ms/UpgradeSuccessKit)<br><br>[팀 영상 교육](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7?wt.mc_id=otc_home)<br><br>[비즈니스용 Skype에서 팀으로 전환](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964) |
|**3-4** |**첫 번째 업그레이드 그룹의 사용자에 대해서만 공존 모드를 팀으로 사용** |Skype for Business 환경에 맞는 단계를 따라 기술 사용자 마이그레이션을 수행 합니다. |[비즈니스용 Skype Online에서 팀으로 업그레이드](upgrade-to-teams-execute-skypeforbusinessonline.md)<br><br>[비즈니스용 Skype 하이브리드 배포에서 팀으로 업그레이드](upgrade-to-teams-execute-skypeforbusinesshybrid.md)<br><br>[비즈니스용 Skype 온-프레미스 배포에서 팀으로 업그레이드](upgrade-to-teams-execute-skypeforbusinessonpremises.md) |
|**4(tcp/ipv4)** |**순환 주기에 나머지 업그레이드 그룹에 대해 앞의 업그레이드 작업 반복** |계속 진행 되는 통신 계획을 관리 하 고 계획에 따라 사용자 그룹을 업그레이드 합니다. | |
|**5mb** |**업그레이드 후 피드백 설문 조사를 모든 사용자에 게 보내기** |피드백 설문 조사를 활용 하 여 사용자의 피드백 및 통찰력을 수집 합니다. |[성공 키트 업그레이드](https://aka.ms/UpgradeSuccessKit) |

## <a name="post-upgrade"></a>업그레이드 후

**팀과 비즈니스 가치 극대화.** 조직이 팀으로 완전히 업그레이드 된 후에는 목표에 대 한 성공 여부를 평가 하 고 통해 계속 앞서를 전달 하는 계획을 구현 하세요.

### <a name="days-1ndash14-measure-the-success-of-your-upgrade"></a>일 1&ndash;14: 업그레이드 성공 측정

|단계만 | |요약 |자원별 |
|---|---|---|---|
|**raid-1** |**초기 업그레이드 성공 평가** |업그레이드 전 단계에서 설정한 목표에 대해 진행 상황을 평가 합니다. |[프로젝트 목표](upgrade-define-project-scope.md#project-goals) |
|**2** |**추적 하지 않는 모든 목표에 대해 완화 계획을 구현 합니다.** |충족 되지 않는 목표에 대 한 완화 또는 과정 수정 전략을 정의 합니다. |[프로젝트 목표](upgrade-define-project-scope.md#project-goals) |

### <a name="ongoing"></a>지속

|단계만 | |요약 |자원별 |
|---|---|---|---|
|**raid-1** |**네트워크 상태 및 품질 모니터링** |네트워크 상태 모니터링 및 완화 계획을 구현 하면 지원 센터에 대 한 통화를 줄이는 것 외에도 긍정적인 사용자 환경을 유지 하는 데 도움이 됩니다. |[네트워크 상태 및 품질 모니터링](continue-journey.md#monitor-for-network-health-and-quality) |
|**2** |**드라이브 사용자 통해 계속 앞서 및 채택** |진행 중인 채택 계획이 있는 팀에 대해 사용자 채택을 장려 하 고 흥미로운 것을 유지 합니다. |[드라이브 사용자 통해 계속 앞서 및 채택](continue-journey.md#drive-user-momentum-and-adoption) |
|**3-4** |**새로운 기능 준비** |조직 내에서 변경 주기를 설정 하면 지속적인 공동 작업 개선 기능을 관리 하 고 최대 가치를 실현할 수 있습니다. |[새로운 기능 준비](continue-journey.md#prepare-for-new-functionality) |

> [!Note]
> 저희 업그레이드 전문가 콘텐츠는 지속적으로 발전 하 고 있습니다. 최신 지침을 다시 확인 하 고 [팀 블로그](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/bg-p/MicrosoftTeamsBlog)를 읽어 보세요.

> [!Important]
> 비즈니스용 Skype Online은 2021 년 7 월 31 일에 만료 되며, 그 이후에는 더 이상 접근성 또는 지원 되지 않습니다. 조직의 혜택 실현을 최대화 하 고 업그레이드를 구현 하는 데 적절 한 시간을 확보 하려면 지금 Microsoft 팀으로 여행을 시작 하는 것이 좋습니다. 성공적으로 업그레이드 하면 기술 및 사용자의 준비가 정렬 되므로 Microsoft 팀으로 여행을 이동할 때이 가이드의 지침을 활용 해야 합니다.
