---
title: Microsoft Teams 클라우드 음성 서비스 배포
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
description: Site Enablement Playbook을 다운로드하여 Teams 롤아웃을 계획하고 사용자 채택, 품질 인식 및 만족도를 가속화하고 최적화합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112634"
---
# <a name="deploy-my-service"></a>내 서비스 배포

이 문서에서는 클라우드 음성 서비스를 올바르게 배포하기 위한 요구 사항에 대한 개요를 제공합니다. 클라우드 음성 서비스를 배포하기 위한 지침에 따라 모든 요구 사항을 성공적으로 고려하고 반복 가능한 결과를 제공할 수 있습니다.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Microsoft Teams 음성 워크로드에 대한 사이트 사용 가능 플레이북

이 플레이북을 사용하여 조직에서 사이트당 Microsoft Teams 음성 기능의 롤아웃을 성공적으로 계획하고 실행하는 데 도움이 됩니다.

필요한 모든 활동, 권장 타임라인 및 각 활동에 대한 해당 지침에 대한 링크를 포함하여 이 플레이북은 사용자에게 중요한 요소에 초점을 맞추고, 주어진 사이트에 대한 Teams 음성 배포를 성공적으로 보장하는 데 도움이 되는 종단마다 지침을 설명합니다.

이 플레이북에서 활동을 완료하면 조직에서 다음을 할 수 있습니다.

-   Teams 롤아웃을 효과적으로 계획하고 예약합니다.

-   사용자 채택을 가속화하고 최적화합니다.

-   지원 요구를 줄이고 사용자 만족도를 높입니다.

> [!NOTE]
> 이 문서 및 관련 플레이북은 서비스 사용 또는 특정 사이트에 전화 걸기 톤을 제공하는 데 필요한 모든 기술 구성 단계를 설명하기 위한 것이 아닙니다. 대신 사용자가 쉽게 온보드하는 데 권장되는 활동 및 작업에 집중하고 채택률이 높고 원활한 전환을 통해 Teams 음성 워크로드를 사용하게 하면서 지원 요구 사항을 최소화합니다. Teams 음성에 대한 환경을 가장 잘 구성하는 방법에 대한 기술 지침은 [Teams](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)음성 워크로드 구성, [Teams에서](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)직접 라우팅 구성, [](prepare-network.md) [Teams](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)핵심 기능, Teams 네트워킹 및 [Microsoft 365 또는 Office 365](onboarding-checklist-enable-office-365.md)사용에 대한 온보더링 검사 목록을 참조하세요.

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>플레이북 포커스 영역

플레이북의 초점은 Teams 음성 배포에 대한 사용자의 인식에 영향을 주는 요소를 해결하기 위한 것입니다. 활동 및 작업은 다음 포커스 영역으로 그룹화됩니다.

-   서비스 준비의 유효성 검사
    - 오디오 회의
    - 통화 플랜
    - 직접 라우팅

-   사용자 사용

-   엔드포인트

-   사용 현황 및 품질

-   채택

음성용 사이트 사용 [플레이북(Playbook)은](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) Microsoft Excel 통합 문서입니다. 이러한 5개의 포커스 영역 각각은 통합 문서의 별도 시트로, 각 배포 작업 및 활동은 이러한 시트 중 하나에 그룹화됩니다.

![사이트 사용 플레이북 스크린샷](media/deploy-my-service-image1.png "플레이북 스크린샷")

> [!NOTE]
> Teams 롤아웃 범위에서 각 사이트에 대해 플레이북의 별도 인스턴스를 만들 수 있습니다.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>플레이북을 사용하는 방법

위치의 크기와 복잡성에 관계없이 각 사이트를 사용하도록 설정하려면 작업 및 활동을 충분히 일찍 계획하고 실제 서비스 롤아웃 전, 중 및 후에 최적의 순서로 실행해야 합니다. Microsoft Teams 음성에 대한 사용자 자신의 여정을 계획하고 실행할 때 다음 단계를 따르는 것이 좋습니다.

1. Microsoft Teams Voice용 [Playbook(음성용 사이트](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 사용 플레이북)을 다운로드합니다.

2. 각 사이트에 대해 플레이북의 별도 복사본을 생성합니다.

3. **{SiteName-Code}의 Playbook이라는** 시트의 탭에서 **{SiteName-Code}를** 관련 사이트 이름 및/또는 사이트 코드로 바 대체합니다.

4. 아래와 같은 사이트 **이름, 사이트** 코드 및 **계획된** 시작 날짜를 입력합니다. 이는 플레이북의 모든 활동에 권장되는 마감일을 조정하기 때문에 중요한 단계입니다.

   ![사이트 이름, 사이트 코드 및 계획된 출시 날짜가 있는 예제](media/deploy-my-service-image2.png "뉴욕의 사이트 이름, 사이트 코드 NY01 및 예정된 출시 날짜가 20-3월 18일인 예제")

5. 각 활동을 검토하고, 필요한 작업을 수행하고, 타임라인을 진행할 때 상태를 업데이트합니다. 상태는 아래에 설명된 바와 같이 그래픽으로 표시됩니다.
  
   - ![녹색 확인 표시 ](media/deploy-my-service-image3.png) **예(녹색)의 그림:** 작업이 완료되거나 이 사이트에 적용되지 않습니다. 추가 작업이 필요하지 않습니다.</li>
   - ![노란색 느낌표의 그림: 활동이 아직 완료되지 않았습니다(노란색): 활동이 아직 완료되지 않았고 일정에 따라 예 또는 아니요로 ](media/deploy-my-service-image4.png) <strong></strong> 업데이트해야 합니다.</li>
   - ![아니요(빨간색)를 나타내는 빨간색 X 그림: 문제로 활동을 완료할 수 없습니다. 프로젝트 상태 모임으로 ](media/deploy-my-service-image5.png) <strong></strong> 진행해야 합니다.</li></ul>

6. 상태는 각 섹션 내에서 롤업됩니다. 섹션 제목은 이러한 상태 표시기 중 하나를 통해 서식이 지정됩니다. **주간 상태도** 자동으로 업데이트됩니다.

![플레이북의 주간 상태 롤업 스크린샷](media/deploy-my-service-image6.png "플레이북의 주간 상태 롤업 스크린샷")

> [!TIP]
> 모든 위치에 대해 위의 단계를 반복합니다.

> [!IMPORTANT]
> 일부 단계는 일부 위치 및 사이트에 적용되지 않을 수 있습니다. 특정 활동이 사이트와 관련이 없는 경우 이 활동에 적용할 수 없습니다를 **선택해야** 합니다. **플레이북의** 행을 삭제하지 않습니다. 이 경우 상태 롤업 수식이 작동하지 않습니다.<br/><br/>
숫자 포터링 및 조달 활동과 같이 계획보다 시간이 더 걸릴 수 있는 활동에 주의를 기울입니다. 이러한 활동은 사이트 배포 타임라인에 부정적인 영향을 줄 수 있습니다. 활동 목록 및 관련 타임라인을 매주 검토하고 업데이트하고 운영 [](./envision-steering-committee-complete-guide.md) 위원회 모임에서 발표하여 관계자가 각 사이트의 상태와 배포 일정에서 가능한 일차를 인식할 수 있도록 합니다.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>배포에 사이트 사용 플레이북이 필요한지 여부를 결정합니다.</li><li>배포할 모든 사이트에 대해 Microsoft Teams에 대한 사이트 사용 플레이북을 사용자 지정할 책임이 있는 사용자 결정</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">사이트 사용 플레이북을 다운로드합니다.</a></li><li>첫 번째 사이트에 대한 사이트 사용 플레이북을 사용자 지정합니다.</li><li>필요에 따라 추가 사이트에 대해 반복합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->