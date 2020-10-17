---
title: Microsoft 팀 클라우드 음성 서비스 배포
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 사이트 사용 Playbook을 다운로드 하 여 팀의 출시를 계획 하 고 사용자 채택을 향상 하 고 최적화 하며, 품질 및 만족도를 높입니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae9a1e6abf7dbf97e625be4eb69a0ef95b1910da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532575"
---
# <a name="deploy-my-service"></a>내 서비스 배포

이 문서에서는 클라우드 음성 서비스를 올바르게 배포 하기 위한 요구 사항에 대해 간략하게 설명 합니다. 클라우드 음성 서비스 배포에 대 한 규범적인 지침을 따라 모든 요구 사항을 성공적으로 설명 하 고 반복 가능한 결과를 제공할 수 있도록 합니다.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Microsoft 팀의 사이트 playbook 음성 작업 부하

이 playbook를 사용 하 여 조직에서 사이트별로 Microsoft 팀 음성 기능 롤아웃을 성공적으로 계획 하 고 실행할 수 있습니다.

이 playbook는 필요한 모든 활동, 권장 시간 표시 막대, 각 활동에 대 한 해당 지침에 대 한 링크를 포함 하 여, 특정 사이트에 대 한 팀 음성 배포를 성공적으로 수행 하는 데 도움이 되는 사용자에 게 중요 한 요인에 초점을 둘 수 있도록 엔드 투 엔드 지침을 다룹니다.

이 playbook의 활동을 완료 하 여 조직에서 다음을 수행할 수 있습니다.

-   팀 출시를 효과적으로 계획 하 고 예약 합니다.

-   사용자 채택을 가속화 하 고 최적화 합니다.

-   지원 요구를 줄이고 사용자 만족도를 높입니다.

> [!NOTE]
> 이 문서 및 관련 playbook는 서비스 사용 또는 특정 사이트에 발신음을 제공 하는 데 필요한 모든 기술 구성 단계를 설명 하는 것이 아닙니다. 대신 사용자가 쉽게 사용할 수 있도록 하는 작업 및 작업에 중점을 두 며, 지원 요구 사항을 최소화 하면서, 채택 률이 높은 빠른 전환 및 원활한 전환을 통해 팀 음성 작업량을 소모 하기 시작 합니다. 팀 음성에 가장 적합 한 환경을 구성 하는 방법에 대 한 기술 지침은 팀 [음성 작업을 구성](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)하기 위한 온 보 딩 검사 목록, 팀 [에서 직접 라우팅 구성](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), 팀 [핵심 기능](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), 팀 [네트워킹](prepare-network.md), [Microsoft 365 또는 Office 365 사용](onboarding-checklist-enable-office-365.md)을 참조 하세요.

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Playbook 포커스 영역

Playbook의 초점은 팀 음성 배포의 사용자의 인식에 영향을 주는 요소를 처리 하는 것입니다. 활동 및 작업은 다음 포커스 영역으로 그룹화 됩니다.

-   서비스 준비 상태 확인
    - 오디오 회의
    - 통화 플랜
    - 직접 라우팅

-   사용자 사용

-   끝점

-   사용 및 품질

-   도입할

[Playbook (Playbook) 사이트를 사용할 수 있도록](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) Microsoft Excel 통합 문서를 만듭니다. 이러한 다섯 가지 포커스 영역은 통합 문서의 개별 시트 이며 각 배포 작업 및 활동은 이러한 시트 중 하나로 그룹화 됩니다.

![사이트 활용 playbook 스크린샷](media/deploy-my-service-image1.png "Playbook 스크린샷")

> [!NOTE]
> 팀 배포 범위에서 각 사이트에 대 한 playbook의 개별 인스턴스를 만듭니다.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Playbook를 사용 하는 방법

위치에 대 한 크기와 복잡도에 관계 없이 각 사이트를 사용 하도록 설정 하면 작업 및 활동을 초기에 계획 하 고 실제 서비스 출시 전, 중, 그리고 그 후에 최적의 순서로 실행 해야 합니다. Microsoft 팀 음성으로 직접 여행을 계획 하 고 실행할 때 다음 단계를 수행 하는 것이 좋습니다.

1. Microsoft 팀 음성에 대 한 [Playbook (Playbook)의 비즈니스용 전화](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 를 다운로드 합니다.

2. 각 사이트에 대 한 playbook의 별도 복사본을 만듭니다.

3. **{Sitename-code}에 대 한 Playbook**이라는 시트의 탭에서 **{sitename-code}** 를 관련 사이트 이름 및/또는 사이트 코드로 바꿉니다.

4. 아래 그림과 같이 **사이트 이름, 사이트 코드**및 **계획 된 시작 날짜**를 입력 합니다. 이것은 playbook의 모든 활동에 대해 권장 되는 마감 기한을 조정 하기 때문에 중요 한 단계입니다.

   ![사이트 이름, 사이트 코드 및 계획 된 시작 날짜가 있는 예제](media/deploy-my-service-image2.png "뉴욕의 사이트 이름, 사이트 코드 NY01, 계획 된 시작 날짜: 20 년 3 월 18 일")

5. 각 활동을 검토 하 고 필요한 작업을 수행 하 고 시간 표시 막대를 진행할 때 상태를 업데이트 합니다. 상태는 아래에 설명 된 대로 그래픽으로 표시 됩니다.
  
   - ![녹색 확인 표시 ](media/deploy-my-service-image3.png) **예, 적용 되지 않음 (녹색):** 활동이 완료 되었거나이 사이트에 적용 되지 않으며 추가 작업이 필요 하지 않습니다.</li>
   - ![노란색 느낌표 그림 ](media/deploy-my-service-image4.png) <strong>활동은 아직 완료 되지 않음 (노란색):</strong> 작업이 아직 완료 되지 않았으므로 해당 일정의 예 또는 아니요로 업데이트 해야 합니다.</li>
   - ![](media/deploy-my-service-image5.png) <strong>아니요 (빨강)</strong> 를 표시 하는 빨간색 X 그림: 문제로 인해 작업을 완료할 수 없어 프로젝트 상태 모임에 전달 해야 합니다.</li></ul>

6. 상태가 각 섹션 내에 겹쳐서 표시 되 고 섹션 제목에 다음 상태 표시기 중 하나로 서식이 지정 됩니다. **주간 상태** 도 자동으로 업데이트 됩니다.

![Playbook의 주간 상태 롤업 스크린샷](media/deploy-my-service-image6.png "Playbook의 주간 상태 롤업 스크린샷")

> [!TIP]
> 사용 중인 모든 위치에 대해 위 단계를 반복 합니다.

> [!IMPORTANT]
> 일부 단계는 일부 위치 및 사이트에 적용 되지 않을 수 있습니다. 특정 활동이 사이트와 관련이 없는 경우이 활동에는 **해당 하지 않음** 을 선택 해야 합니다. Playbook에서 행을 **삭제 하지 마세요** . 이렇게 하면 상태 롤업 수식이 작동 하지 않습니다.<br/><br/>
전화 번호 포팅, 조달 활동 등 예정 보다 시간이 더 걸릴 수 있는 활동에 주의를 기울여야 합니다. 이러한 활동은 사이트 배포 시간 표시 막대에 부정적인 영향을 미칠 수 있습니다. 활동 목록과 관련 시간 표시 막대를 매주 검토 하 고 업데이트 한 후, 관계자가 각 사이트의 상태와 배포 일정의 가능한 편차를 알 수 있도록 개체를 [조종 위원회 모임](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) 에 제시 하세요.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>배포에 사이트 Playbook 필요한 지 여부를 결정 합니다.</li><li>배포할 모든 사이트에 대해 Microsoft 팀의 사이트 이용 Playbook 사용자 지정을 담당할 사용자를 결정 합니다.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">사이트 Playbook를 다운로드</a>합니다.</li><li>첫 번째 사이트의 사이트 Playbook을 사용자 지정 합니다.</li><li>추가 사이트에 대해 필요에 따라 반복 합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->