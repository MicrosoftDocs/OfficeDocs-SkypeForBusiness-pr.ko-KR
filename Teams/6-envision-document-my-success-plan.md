---
title: 성공 Microsoft Teams 문서화
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/13/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 배포 모델을 선택하고, 책임감 있는 RACI(책임 있는 컨설팅) 매트릭스를 개발하고, 실행 및 거버넌스 계획을 만듭니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 40f88c93e20fde89eb9791cc90760d554e52a004
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44512815"
---
# <a name="document-my-success-plan"></a>내 성공 계획 문서화

이 문서에서는 클라우드 음성 배포를 올바르게 문서화하기 위한 요구 사항에 대한 개요를 제공합니다. 클라우드 음성 배포를 계획하는 동안 모든 의사 결정 지점 및 다음 단계를 정의하고 문서화하면 모든 이해 관계자와 프로젝트 팀 구성원이 성공적인 결과 전달에 맞게 조정될 수 있습니다. 

## <a name="execution-planning"></a>실행 계획 

조직에서 호출 계획 솔루션을 통해 오디오 회의 또는 전화 시스템 구현 방법을 정의한 후 구현 프로젝트 실행을 계획해야 합니다.

조직에 사이트가 하나 또는 두 개만 있는 경우 이 문서에 제공된 모든 세부 정보를 완료할 필요가 없지만 접근 방식을 안내하기 위해 이 문서를 읽어야 합니다.

<!--ENDOFSECTION-->

## <a name="deployment-model"></a>배포 모델 

조직에서 작업하는 방법을 변환하는 모든 기술 구현과 함께 배포를 진행하는 올바른 방법을 선택하면 클라우드 음성 구현의 성공에 크게 영향을 줄 수 있습니다.

잠재적인 배포 모델에는 다음이 포함됩니다.

-   **사이트당:** 이 모델은 조직이 지리적으로 분산되어 있으며 분기에는 많은 직원이 있는 경우에 적합합니다. 그러나 이 배포 모델은 부서 직원이 여러 위치에 분산되는 부서 내의 통신을 방해할 수 있습니다.

-   **부서당**: 일반적으로 이 모델은 중간 규모 회사에 더 나은 옵션으로 관련 부서가 동일한 환경을 하도록 보장합니다.

-   **전체 회사를 한 번씩:** 이 모델은 일반적으로 모든 직원이 배포 첫날부터 동일한 환경을 얻을 수 있는 소규모 회사에 가장 적합한 옵션입니다.


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>조직에 Teams 배포 실행 모델을 결정합니다.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>선택한 Teams 배포 실행 모델을 문서화하고 비즈니스 및 기술적 명분을 포함합니다.</li></ul></td></tr></table>

## <a name="raci-modeling"></a>RACI 모델링

프로젝트에서 책임이 있는 사용자에 대한 명확성을 얻게 하려면 책임 할당 매트릭스(RACI라고도 하는 책임, 책임, 컨설팅 및 정보 매트릭스)를 사용하세요. 각 작업에 대한 책임과 책임이 있는 사람 또는 그룹과 의사 결정 프로세스에서 협의할 이해 관계자와 프로젝트 실행 전반에 걸쳐 각 의사 결정 및 작업에 대해 알릴 이해 관계자를 나열합니다.

다음은 클라우드 음성 구현에 대한 RACI 매트릭스의 예입니다.

| 활동/역할                                         | Project 잠재 고객 | 공동 작업 리드/설계자 | 컨설턴트 | 변경 관리/채택 전문가 | 비즈니스 단위 담당자 |
|-------------------------------------------------------|--------------|------------------------------|------------|---------------------------------------|-------------------------------|
| 프로그램 프레젠테이션 킥오프 호출                     | R, A         | C                            |            |                                       |                               |
| 통화 품질 대시보드 설정                         | I            | C                            | R, A       |                                       |                               |
| 킥오프 호출 중에 검색 질문 공유 | I            | C                            | R, A       |                                       |                               |
| 계획 단계 킥오프                                | R, A         | C                            |            |                                       |                               |
| 비즈니스 사용 사례 워크샵                           | A            |                              |            | R                                     | C                             |
| 검색 질문지 검토                    |              | R, A                         | C          |                                       |                               |
| 아키텍처 워크샵                                 | I            | R, A                         | C          |                                       |                               |
| 채택 사용자 시나리오 Envision 단계 워크샵       | C            | I                            | A          | R                                     |                               |
| 채택 성공 워크샵                             |              |                              | R, A       | C                                     |                               |
| 클라이언트 및 디바이스 준비 워크샵                  | I            |                              | R, A       | C                                     |                               |


<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>클라우드 음성 구현 프로젝트와 관련된 활동/역할을 결정합니다.</li><li>클라우드 음성 구현 프로젝트의 책임 할당 매트릭스(RACI 매트릭스)에 할당할 팀 또는 인원을 결정합니다.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>RACI 매트릭스를 문서화합니다.</li></ul></td></tr></table>

## <a name="quarterly-execution-plan"></a>분기별 실행 계획

관리 가능한 작업 청크에서 클라우드 음성 배포를 실행하기 위해 목표 키 결과(OKRS), 선택한 배포 모델 및 조직의 프로젝트 실행 기능에 따라 분기별 실행 계획을 만드는 것이 좋습니다.

이렇게 하면 분기별 진행 상황을 추적하고, 필요한 경우 계획을 변경하고, 조직의 실행 능력에 따라 클라우드 음성 기능을 배포할 수 있습니다.

조직에 사이트가 하나 또는 두 개만 있는 경우 단기간에 완전히 배포될 것으로 예상하기 때문에 분기별 실행 계획이 필요하지 않을 수 있습니다.

다음은 클라우드 음성 구현의 Envision 단계에 대한 분기별 실행 계획의 예입니다.

| 사이트/부서                            | 직원 수 | 오디오 회의 | 전화 시스템                    | 실행할 분기 |
|------------------------------------------|---------------------|--------------------|---------------------------------|--------------------|
| 미국: 뉴욕                             | 2000                | 예                | 통화 플랜을 사용하는 전화 시스템 | Q1 CY2018          |
| 아일랜드: 더블린                          | 300                 | 예                | 통화 플랜을 사용하는 전화 시스템 | Q1 CY2018          |
| 오스트리아: 비엔나                          | 500                 | 예                | 전화 시스템 직접 라우팅     | Q2 CY2018          |
| 이탈리아: 밀라노                             | 200                 | 예                | 해당 없음                             | Q2 CY2018          |
| 남아메리카: 브라질                    | 1500                | 예                | 전화 시스템 직접 라우팅     | Q2 CY2018          |
| 인도: Delhi                             | 7000                | 예                | 해당 없음                             | Q3 CY2018          |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>목표 핵심 결과(OKRS)를 달성하기 위해 분기별 실행 계획을 결정합니다.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>분기별 실행 계획을 문서화합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="communications-and-governance-plan"></a>통신 및 거버넌스 계획

프로젝트 관계자가 배포 진행 상황을 최신으로 유지하려면 프로젝트의 상태, 주요 이정표, 차단자 및 확립된 KSIS에 대한 프로젝트의 다양한 검토와 관련된 문제를 논의하기 위해 핵심 프로젝트 팀 구성원 및 이해 관계자와 통신이 어떻게 진행될지 계획을 수립해야 합니다. , 운영 메트릭 및 전략적 목표.

다음은 클라우드 음성 구현 프로젝트에서 활용할 수 있는 통신 및 거버넌스 계획의 예입니다.

| 유형                                        | 목표                                                                                                                                                      | 참가자 | 일/시간                                     | 위치             | 모임 소유자 |
|---------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------|-----------------------------------------------|----------------------|---------------|
| Project 대기 호출                       | 프로젝트의 상태 동기화, 주요 이정표 및 차단기 추적                                                                                           | TBA          | 월요일, 화요일, 수요일, 목요일 오후 5시 PST | 가상              | TBA           |
| 주간 운영위원회                   | 클라우드 음성 프로젝트의 상태를 검토하고, 임원에게 보고하고, 경영진의 도움이 필요한 문제를 해결해야 합니다.                                        | TBA          | 매주 금요일 오전 11시 PST                        | 가상              | TBA           |
| 월간 프로젝트 비즈니스/운영 검토 | 확장된 이해 관계자, 주요 연락처 및 임원 후원자를 통해 프로젝트 상태를 검사합니다. 배포 계획, KSIS 및 운영 메트릭 검토 | TBA          | 월의 두 번째 화요일                       | 가상 또는 개인 | TBA           |
| 분기별 비즈니스 검토(QBR)             | 프로젝트 상태를 확인하고 전략적 목표, KSIS 및 운영 메트릭에 대해 진행 상황을 검토합니다. 필요한 경우 요금제 재방사                                 | TBA          | 매 분기의 마지막 목요일                | 대면            | TBA           |


<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>정기 상태 업데이트 빈도(일별, 매주, 월별 또는 분기별), 상태 업데이트 모임을 수행하기 위한 방법 및 각 모임의 소유자를 포함하여 통신 및 거버넌스 계획을 결정합니다.</li></ul></td></tr>

<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>통신 및 거버넌스 계획을 문서화합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="finalize-my-success-plan"></a>성공 계획 마무리

성공 계획은 Envision 단계에서 만든 설명서의 요약입니다.

성공 계획은 FastTrack 또는 배포 파트너를 포함할 수 있는 프로젝트 팀에게 오디오 회의 또는 호출 계획 서비스를 사용하여 조직의 목표를 실현하기에 전화 시스템 제공합니다.

일반적으로 성공 계획에는 다음 주요 섹션이 포함되어 있습니다. 많은 섹션은 Envision 단계를 통해 작업하게 됩니다.

-   비즈니스 사례

-   서비스 준비

-   서비스 결정

-   실행 계획

-   채택 계획

-   운영 계획

### <a name="business-case"></a>비즈니스 사례

비즈니스 사용 사례, 이해 관계자, OKRS 및 KSIS, 위험 레지스터 및 프로젝트 타임라인은 일반적으로 비즈니스 사례에 필요한 많은 정보를 제공합니다. 이러한 문서는 성공 계획의 일부로 문서화해야 합니다.

### <a name="service-readiness"></a>서비스 준비

환경 평가는 전화 요금제로 오디오 회의 및/또는 전화 시스템 조직의 기술 준비를 결정하는 데 필요한 초기 전화 시스템 제공합니다.

여기에는 서비스 준비 평가 및 환경 평가를 통해 발견한 수정이 필요한 영역을 해결하기 위한 계획이 포함되어 있습니다.

### <a name="service-decisions"></a>서비스 결정

조직에 대한 Calling Plan 서비스 기술 구현을 통해 오디오 회의 또는 전화 시스템 계획 방법을 문서화합니다.

### <a name="execution-plan"></a>실행 계획

조직 전체에서 솔루션을 구현하기 위해 프로젝트 실행을 계획한 방법을 문서화합니다.

### <a name="adoption-plan"></a>채택 계획

채택 준비 평가를 수행한 후 프로젝트 팀은 출시 전, 시작 및 사후 도입 활동에 대한 포괄적인 통신 계획, 교육 계획 및 계획을 수립해야 합니다.

조직의 요구 사항을 충족하는 데 필요한 사용자 지정과 함께 전단지, 환영 전자 메일 및 교육 자료와 같은 채택 활동을 지원하는 리소스를 식별합니다.

고객 성공 키트에서 채택 [Microsoft Teams 템플릿을 다운로드합니다.](https://aka.ms/TeamsCustomerSuccess)

### <a name="operational-plan"></a>운영 계획

운영 역할 매핑의 연습은 역할과 책임을 설정하고 각 운영 역할에 할당된 팀을 설정하며, 오디오 회의 구현을 지원해야 합니다.

이 작업을 완료하고 솔루션의 운영 준비를 보장하기 위해 성공 계획의 일부로 운영 계획을 포함해야 합니다.

<table>

<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>클라우드 음성 워크로드를 제공하기 위한 전체 성공 계획을 문서화하는 방법을 결정합니다.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>성공 계획의 모든 구성 요소가 문서화되어 있는지 확인할 수 있습니다.</li><li>성공 계획의 개별 구성 요소를 단일 요약 문서(선택 사항)로 집계합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->
