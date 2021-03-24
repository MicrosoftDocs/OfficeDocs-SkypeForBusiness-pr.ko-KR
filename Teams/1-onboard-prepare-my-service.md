---
title: 클라우드 음성 서비스 배포 준비
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 온보더링 검사 목록을 사용하여 Teams용 Microsoft 365 또는 Office 365를 준비하고 Teams 핵심 기능, 네트워킹 및 클라우드 음성 워크로드를 구성합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 42ded974ba5f4400bdcb5796410a8277fbed4488
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103974"
---
# <a name="prepare-my-service"></a>내 서비스 준비

이 문서에서는 조직의 클라우드 음성 서비스를 준비하기 위한 요구 사항에 대한 개요를 제공합니다. 제대로 준비하면 조직에 클라우드 음성 기능을 제공할 준비가 되었는지 확신할 수 있습니다.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Microsoft Teams 음성 워크로드에 대한 온보드 검사 목록

다음 검사 목록에서는 Microsoft Teams에서 오디오 회의, 통화 계획("통화 계획")을 통한 전화 시스템 및 전화 시스템 직접 라우팅("직접 라우팅") 기능을 구현하기 위한 단계를 설명합니다.

*  [Teams용 Microsoft 365 또는 Office 365 준비](onboarding-checklist-enable-office-365.md)

*  [Teams 핵심 기능 구성](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [네트워크 준비](prepare-network.md)

*  [Teams에서 클라우드 음성 워크로드 구성](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Teams에서 직접 라우팅 구성](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

이러한 검사 목록의 작업 및 활동은 Teams를 통해 클라우드 음성 기능을 배포하는 모든 배포에 적용되는 핵심 "할 일" 항목입니다. 검사 목록을 사용자 지정하여 자신의 Teams 여정에 특정되는 활동 및 작업을 포함할 수 있습니다.

>[!NOTE]
>이 지침은 통화 계획, 오디오 회의 및 직접 라우팅에만 초점을 맞추고 있습니다. Teams를 새로 사용 중이신 경우 [Microsoft Teams 개요를 검토하세요.](teams-overview.md) Teams 배포 계획에 대한 일반적인 지침은 [Microsoft Teams에서 채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)배포부터 시작하세요.

제공된 검사 목록을 사용하여 각 개별 활동 및 작업의 상태를 추적하고 중요한 단계를 건너뜁니다. 각 활동에는 필요한 작업에 대한 자세한 설명과 해당 작업을 완료하는 데 사용할 수 있는 추가 정보에 대한 참조가 포함됩니다.

검사 목록을 순서대로 따르는 것이 좋습니다. 정확한 순서는 배포 범위 및 환경의 구성 및 복잡성에 따라 다릅니다. "greenfield" Teams 배포(이전 비즈니스용 Skype Online 존재 없음) 또는 비즈니스용 Skype Online에서 Teams로 마이그레이션을 지원하기 위해 구성됩니다. 비즈니스용 Skype Online에서 마이그레이션하는 경우 이러한 작업 중 일부를 이미 완료하고 지금 무시할 수 있습니다.

사이트당 사용자를 온보드하는 경우 이러한 검사 목록에 대한 보조 [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 가이드로 음성용 사이트 사용 플레이북(Playbook)을 사용하는 것이 좋습니다.

>[!NOTE]
>대부분의 구성 설정은 Teams와 비즈니스용 Skype Online 간에 일반적입니다. Microsoft 365 관리 센터 및 Microsoft Teams 관리 센터를 사용하여 이러한 설정을 구성합니다.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>온보더링 검사 목록의 완료를 관리해야 할 책임은 누구인가요?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>온보더링 검사 목록을 다운로드합니다.</li><li>조직의 배포 계획에 따라 온보더링 검사 목록 항목을 단계적으로 처리합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>계속 온보드

이러한 검사 목록을 완료하면 Teams 배포에 음성 기능이 성공적으로 추가됩니다.

다음 단계로, 각 [](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 사이트에서 사용자를 온보드하고 중요한 사이트별 활동을 계획하고 실행할 수 있도록 도와주는 음성용 사이트 사용 플레이북(Playbook)을 사용하세요.

-   사이트 롤아웃 계획에 따라 준비된 사이트

-   서비스 관리 프로세스 설정

-   테스트 및 수정 실행

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Teams에서 클라우드 음성 워크로드 테스트

Envision 단계의 일부로 Teams 클라우드 음성 비즈니스 성공 및 기술 구현 계획을 정의하고 문서화하고 관리 센터에서 원하는 구성을 실행한 후 다음 단계는 조직의 기대와 요구 사항이 기능, 기능 및 사용성을 통해 충족되는지 유효성을 검사하는 것입니다. 프로덕션 환경에서 파일럿 또는 최종 배포를 배포하기 전에 이 유효성 검사 단계를 수행해야 합니다.

Envision 단계에서 정의한 비즈니스 성공 계획을 활용하여 테스트 단계에서 평가할 활동, 기대, 기능/기능 테스트 사례 및 전체 범위를 결정하는 기본 역할을 할 수 있습니다.

## <a name="define-your-testing-approach"></a>테스트 방법 정의

가장 간단한 형식의 테스트 접근 방식은 오디오 회의, 통화 계획 또는 직접 라우팅 서비스의 기능 기능을 검토하고 범위에 있는 사용자에 대해 기능 요구 사항을 충족하는지 확인하기 위한 테스트 계획을 개발하는 데 기반합니다. 다음은 오디오 회의 구현의 온보드 단계에 대한 예제 테스트 계획입니다.


| 테스트할 오디오 회의 기능 | 결과 요약 | 추가 정보 |
|------------|-----------------|------------------|
| 오디오 회의 전화 접속 정보가 포함된 Ad-Hoc Teams 모임 예약 | 통과/실패   | TBD |
| 전화 접속 정보를 사용하여 PSTN에서 모임에 전화 접속하여 모임 오디오를 위한 전화 사용 | 통과/실패 | TBD |
| PSTN을 통해 전화를 걸고 다른 사용자와 기존 모임에 참가 | 통과/실패 | TBD |



| 테스트할 계획 또는 직접 라우팅 기능 호출 | 결과 요약 | 추가 정보 |
|----------------------------------------------------|-----------------|------------------|
| PSTN 번호로 전화를 걸고 PSTN 전화 걸기       | 통과/실패       | TBD |
| 외부 라인(모바일, 유선)에서 PSTN 번호로 전화를 걸면 PSTN 통화 수신 | 통과/실패 | TBD|
| 한 Teams 사용자에서 다른 팀으로 PSTN 호출 전송 | 통과/실패 | TBD |


>[!TIP]
>테스트 사례 만들기를 시작점으로 지원하기 위해 Teams 모임 및 호출에서 사용할 수 있는 사용자 지침 목록을 [참조하세요.](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Teams에 대한 클라우드 음성 워크로드 설정

이제 테스트 방법을 정의했습니다. 다음 단계는 Teams 클라우드 음성 기능에 대한 범위에서 서비스 환경 및 사용자를 구성하는 것입니다.

자세한 내용은 다음을 참조하세요.

- [오디오 회의에 대한 기술 계획](./cloud-voice-landing-page.md)

- [Microsoft Teams용 오디오 회의 설정하기](set-up-audio-conferencing-in-teams.md)

- [통화 계획을 통해 전화 시스템에 대한 기술 계획](calling-plan-landing-page.md)

- [비즈니스용 Skype 및 Microsoft Teams에 대한 통화 계획 설정](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [직접 라우팅 계획](./direct-routing-plan.md)

- [직접 라우팅 구성](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>테스트 계획 실행

[//]: # (편집할 수 있나요? "사용자"가 약간 모호해 보였다.)
사용자 환경 및 서비스가 구성된 후 테스트의 마지막 단계에서는 기능 및 기능 유효성 검사에 중점을 두는 테스트 계획 실행이 포함됩니다. 

**범위의 사용자 및 사이트에 대한 오디오 회의 테스트의 전제 사항 및 가정:**

-   오디오 회의 서비스에 대한 비즈니스 사용 사례 정의가 완료되었습니다.

-   오디오 회의에 필요한 라이선스를 사용할 수 있으며 할당됩니다.

-   조직 사이트 및 사용자 그룹 목록이 식별되었습니다.

-   언어 기본 설정이 있는 번호의 전용 및 공유 오디오 회의 다이얼 목록이 식별되고 구성되었습니다.

-   [통신 크레딧(필요한](what-are-communications-credits.md) 경우)이 조직에 대해 설정되어 있습니다.

-   오디오 회의 회의 브리지 설정이 식별되고 구성되었습니다(PIN 길이, 진입/종료 알림, 활성화 알림 기본 설정).

-   오디오 회의 전화 접속 시나리오를 지원하는 테넌트 회의 정책 및 다이얼 플랜 설정이 식별, 구성 및 적용되었습니다.

-   오디오 회의 준수 요구 사항이 식별되고 구성되었습니다.

**계획 테스트의 전제 사항 및 범위의 사용자 및 사이트에 대한 가정을 호출합니다.**

-   호출 계획 서비스에 대한 비즈니스 사용 사례 정의가 완료되었습니다.

-   통화 계획에 필요한 라이선스를 사용할 수 있으며 할당됩니다.

-   조직 사이트 및 사용자 그룹 목록이 식별되었습니다.

-   사용자에게 할당할 전화 번호는 Microsoft로 획득 또는 포토타입되어 테넌트 포털에서 사용할 수 있습니다.

-   [통신 크레딧(필요한](what-are-communications-credits.md) 경우)이 조직에 대해 설정되어 있습니다.

-   호출 계획 시나리오를 지원하는 테넌트 사용자 정책 및 전화 요금제 설정을 식별, 구성 및 적용했습니다.

-   호출 계획 규정 준수 요구 사항이 식별되고 구성되었습니다.

**범위의 사용자 및 사이트에 대한 직접 라우팅 테스트의 전제 사항 및 가정:**

-   직접 라우팅 서비스에 대한 비즈니스 사용 사례 정의가 완료되었습니다.

-   직접 라우팅에 필요한 라이선스를 사용할 수 있으며 할당됩니다.

-   조직 사이트 및 사용자 그룹 목록이 식별되었습니다.

-   [SBC(인증된 세션](./direct-routing-plan.md#supported-session-border-controllers-sbcs) 테두리 컨트롤러)가 휴대폰 시스템과 배포, 구성 및 페어링됩니다.

-   엔터프라이즈 음성이 사용하도록 설정되어 있으며 전화 번호가 할당됩니다.

-   음성 라우팅 정책이 식별되고, 구성되고, 할당되었습니다.

-   Microsoft Teams는 범위의 사용자에 대한 기본 호출 클라이언트로 설정되어 있습니다.
 
-   직접 라우팅 규정 준수 요구 사항이 식별되고 구성되었습니다.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>배포할 오디오 회의 기능(서비스 결정)을 결정합니다.</li><li>오디오 회의에 대한 사용자 기능 요구 사항을 식별합니다.</li><li>오디오 회의에 대한 서비스 구성 요구 사항을 식별합니다.</li><br><li>직접 라우팅 또는 통화 계획이 배포 및 구성될지 여부를 결정합니다.<li>배포할 전화 시스템 기능(서비스 결정)을 결정합니다.</li><li>통화 계획 또는 직접 라우팅에 대한 사용자 기능 요구 사항을 식별합니다.</li><li>통화 계획 또는 직접 라우팅에 대한 서비스 구성 요구 사항을 식별합니다.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>테스트 계획 접근 방식을 개발하고 문서화합니다.</li><li>오디오 회의 기능에 대한 범위에서 서비스 환경 및 사용자를 준비합니다.</li><li>통화 계획 또는 직접 라우팅 기능에 대한 범위에서 서비스 환경 및 사용자를 준비합니다.</li><li>사용하려는 오디오 회의 기능에 대한 테스트 유효성 검사를 실행합니다.</li><li>사용하려는 통화 계획 또는 직접 라우팅 기능에 대한 테스트 유효성 검사를 실행합니다.</li><li>테스트 오류가 발생하면 구성이 올바른지 확인하고, 커뮤니티 문서를 검토하고, 필요한 경우 지원 사례를 제기합니다.</li></ul></td></tr>
</table>


Teams에서 오디오 회의에 대한 테스트를 수행하는 방법에 대한 자세한 지침은 오디오 회의에 대한 자세한 테스트 가이드를 [참조하세요.](./deploy-audio-conferencing-teams-landing-page.md)

Teams에서 통화 계획에 대한 테스트를 수행하는 방법에 대한 자세한 지침은 전화 시스템에 대한 자세한 테스트 [가이드를 참조하세요.](./cloud-voice-landing-page.md)

<!--ENDOFSECTION-->