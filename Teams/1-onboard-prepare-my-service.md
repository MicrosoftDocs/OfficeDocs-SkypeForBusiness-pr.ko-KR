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
description: 온보딩 검사 목록을 사용하여 Teams 대한 Microsoft 365 또는 Office 365 준비하고 Teams 핵심 기능, 네트워킹 및 클라우드 음성 워크로드를 구성합니다.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: a91a57a077db38675a62238289ad2c204040a9cd
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675440"
---
# <a name="prepare-my-service"></a>내 서비스 준비

이 문서에서는 조직을 위한 클라우드 음성 서비스를 준비하기 위한 요구 사항에 대한 개요를 제공합니다. 제대로 준비하면 조직에 클라우드 음성 기능을 제공할 준비가 되었는지 확인할 수 있습니다.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Microsoft Teams 음성 워크로드에 대한 검사 목록 온보딩

다음 검사 목록은 Microsoft Teams 오디오 회의 구현, 통화 플랜 전화 시스템("통화 플랜") 및 전화 시스템 직접 라우팅("직접 라우팅") 기능을 구현하는 단계를 안내합니다.

*  [Teams 대한 Microsoft 365 또는 Office 365 준비](onboarding-checklist-enable-office-365.md)

*  [Teams 핵심 기능 구성](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [네트워크 준비](prepare-network.md)

*  [Teams 클라우드 음성 워크로드 구성](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [Teams 직접 라우팅 구성](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

이러한 검사 목록의 작업 및 활동은 Teams 있는 클라우드 음성 기능의 모든 배포에 적용되는 핵심 "할 일" 항목입니다. 사용자 고유의 Teams 여정과 관련된 활동 및 작업을 포함하도록 검사 목록을 사용자 지정할 수 있습니다.

>[!NOTE]
>이 지침은 통화 플랜, 오디오 회의 및 직접 라우팅에만 중점을 둡니다. Teams 새로운 경우 [Microsoft Teams 개요를](teams-overview.md) 검토하세요. Teams 배포를 계획하기 위한 일반적인 지침은 [Microsoft Teams 채팅, 팀, 채널 및 앱 배포부터](deploy-chat-teams-channels-microsoft-teams-landing-page.md) 시작합니다.

제공된 검사 목록을 사용하여 각 개별 활동 및 작업의 상태를 추적하고 중요한 단계를 건너뛰지 않았는지 확인합니다. 각 활동에는 필요한 작업에 대한 자세한 설명과 해당 작업을 완료하는 데 사용할 수 있는 추가 정보에 대한 참조가 포함됩니다.

검사 목록을 순서대로 따르는 것이 좋습니다. 정확한 순서는 배포 범위와 환경의 구성 및 복잡성에 따라 달라집니다. "greenfield" Teams 배포(이전 비즈니스용 Skype Online이 없는 배포)를 지원하거나 비즈니스용 Skype Online에서 Teams 마이그레이션하도록 구성됩니다. 비즈니스용 Skype Online에서 마이그레이션하는 경우 이러한 활동 중 일부를 이미 완료했으며 지금은 무시할 수 있습니다.

사이트별로 사용자를 온보딩하는 경우 이러한 검사 목록에 대한 추가 가이드로 [음성용 사이트 사용 플레이북(플레이북)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 을 사용하는 것이 좋습니다.

>[!NOTE]
>대부분의 구성 설정은 Teams 비즈니스용 Skype Online 간에 일반적입니다. Microsoft 365 관리 센터 및 Microsoft Teams 관리 센터를 사용하여 이러한 설정을 구성합니다.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>Who 온보딩 검사 목록의 완료를 감독할 책임이 있나요?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>온보딩 검사 목록을 다운로드합니다.</li><li>조직의 배포 계획에 따라 온보딩 검사 목록 항목을 단계별로 진행합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>온보딩 계속

이러한 검사 목록을 완료하면 Teams 배포에 음성 기능이 성공적으로 추가됩니다.

다음 단계로, [음성용 사이트 사용 플레이북(플레이북)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 을 사용하여 각 사이트에서 사용자를 온보딩하고 중요한 사이트별 활동을 계획하고 실행할 수 있도록 도와줍니다.

-   사이트별 준비 사이트 롤아웃 계획

-   서비스 관리 프로세스 설정

-   테스트 및 수정 실행

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>Teams 클라우드 음성 워크로드 테스트

구상 단계의 일부로 Teams 클라우드 음성 비즈니스 성공 및 기술 구현 계획을 정의하고 문서화하고 관리 센터에서 원하는 구성을 수행한 후 다음 단계는 기능, 기능 및 유용성을 통해 조직의 기대와 요구 사항이 충족되는지 확인하는 것입니다. 프로덕션 환경에서 파일럿 또는 최종 배포를 배포하기 전에 이 유효성 검사 단계를 수행해야 합니다.

구상 단계에서 정의한 비즈니스 성공 계획을 활용하여 테스트 단계에서 평가할 활동, 기대, 기능/기능 테스트 사례 및 전체 범위를 결정하는 기초 역할을 할 수 있습니다.

## <a name="define-your-testing-approach"></a>테스트 방법 정의

가장 간단한 형태로 테스트 방법은 오디오 회의, 통화 플랜 또는 직접 라우팅 서비스의 기능 기능을 검토하고 범위 내 사용자에 대한 기능 요구 사항이 충족되는지 확인하기 위한 테스트 계획을 개발하는 것을 기반으로 합니다. 다음은 오디오 회의 구현의 온보드 단계에 대한 테스트 계획의 예입니다.


| 테스트할 오디오 회의 기능 | 결과 요약 | 추가 참고 사항 |
|------------|-----------------|------------------|
| 오디오 회의 전화 접속 정보가 포함된 임시 Teams 모임 예약 | 통과/실패   | 미정 |
| 제공된 전화 접속 정보를 사용하여 PSTN에서 모임에 전화 접속하여 모임 오디오에 휴대폰 사용 | 통과/실패 | 미정 |
| PSTN을 통해 전화를 걸어 기존 모임에 다른 사용자 참가 | 통과/실패 | 미정 |



| 테스트할 요금제 또는 직접 라우팅 기능 호출 | 결과 요약 | 추가 참고 사항 |
|----------------------------------------------------|-----------------|------------------|
| PSTN 번호로 전화를 걸어 PSTN 호출       | 통과/실패       | 미정 |
| 외부 회선(모바일, 유선)에서 PSTN 번호로 전화를 걸어 PSTN 통화를 받습니다. | 통과/실패 | 미정|
| 한 Teams 사용자에서 다른 사용자로 PSTN 호출 전송 | 통과/실패 | 미정 |


>[!TIP]
>테스트 사례 만들기를 시작점으로 지원하려면 [Teams 모임 및 통화](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)에서 사용할 수 있는 사용자 지침 목록을 참조하세요.

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>Teams 클라우드 음성 워크로드 설정

이제 테스트 방법을 정의했으므로 다음 단계는 Teams 클라우드 음성 기능에 대한 범위에서 서비스 환경 및 사용자를 구성하는 것입니다.

자세한 내용은 다음을 참조하세요.

- [오디오 회의 기술 계획](./cloud-voice-landing-page.md)

- [Microsoft Teams용 오디오 회의 설정하기](set-up-audio-conferencing-in-teams.md)

- [통화 플랜을 사용하여 전화 시스템 기술 계획](calling-plan-landing-page.md)

- [비즈니스용 Skype 및 Microsoft Teams 대한 통화 플랜 설정](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [직접 라우팅 계획](./direct-routing-plan.md)

- [직접 라우팅 구성](./direct-routing-configure.md)

### <a name="execute-the-test-plan"></a>테스트 계획 실행

[//]: # (편집해도 될까요? "사용자"는 나에게 조금 모호한 것 같았다.)
사용자 환경 및 서비스를 구성한 후 테스트의 마지막 단계에는 기능 및 기능 유효성 검사에 중점을 둔 테스트 계획 실행이 포함됩니다. 

**범위 내 사용자 및 사이트에 대한 테스트 필수 구성 요소 및 가정을 오디오 회의.**

-   오디오 회의 서비스에 대한 비즈니스 사용 사례 정의가 완료되었습니다.

-   오디오 회의 데 필요한 라이선스를 사용할 수 있으며 할당되었습니다.

-   조직 사이트 및 사용자 그룹 목록이 식별되었습니다.

-   언어 기본 설정이 있는 숫자의 전용 및 공유 오디오 회의 다이얼 목록이 식별되고 구성되었습니다.

-   [조직에 대해 통신 크레딧](what-are-communications-credits.md) (필요한 경우)이 설정되었습니다.

-   오디오 회의 회의 브리지 설정이 식별되고 구성되었습니다(PIN 길이, 진입/종료 알림, 사용 알림 기본 설정).

-   오디오 회의 전화 접속 시나리오를 지원하는 테넌트 회의 정책 및 다이얼 플랜 설정이 식별, 구성 및 적용되었습니다.

-   오디오 회의 규정 준수 요구 사항이 식별되고 구성되었습니다.

**통화 플랜은 범위 내 사용자 및 사이트에 대한 필수 구성 요소 및 가정을 테스트합니다.**

-   통화 플랜 서비스에 대한 비즈니스 사용 사례 정의가 완료되었습니다.

-   통화 플랜에 필요한 라이선스를 사용할 수 있으며 할당되었습니다.

-   조직 사이트 및 사용자 그룹 목록이 식별되었습니다.

-   사용자에게 할당할 전화 번호는 Microsoft로 획득 또는 이식되었으며 테넌트 포털에서 사용할 수 있습니다.

-   [조직에 대해 통신 크레딧](what-are-communications-credits.md) (필요한 경우)이 설정되었습니다.

-   통화 플랜 시나리오를 지원하는 테넌트 사용자 정책 및 전화 걸기 계획 설정이 식별, 구성 및 적용되었습니다.

-   통화 플랜 규정 준수 요구 사항이 식별되고 구성되었습니다.

**범위 내 사용자 및 사이트에 대한 직접 라우팅 테스트 필수 구성 요소 및 가정:**

-   직접 라우팅 서비스에 대한 비즈니스 사용 사례 정의가 완료되었습니다.

-   직접 라우팅에 필요한 라이선스를 사용할 수 있으며 할당되었습니다.

-   조직 사이트 및 사용자 그룹 목록이 식별되었습니다.

-   [SBC(인증된 세션 테두리 컨트롤러)](./direct-routing-plan.md#supported-session-border-controllers-sbcs)가 전화 시스템 배포, 구성 및 페어링되었습니다.

-   Enterprise 음성이 활성화되었으며 전화 번호가 할당되었습니다.

-   음성 라우팅 정책이 식별, 구성 및 할당되었습니다.

-   Microsoft Teams 범위 내 사용자의 기본 호출 클라이언트로 설정되었습니다.
 
-   직접 라우팅 규정 준수 요구 사항이 식별되고 구성되었습니다.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>배포할 오디오 회의 기능 기능을 결정합니다(서비스 결정).</li><li>오디오 회의 대한 사용자 기능 요구 사항을 식별합니다.</li><li>오디오 회의 대한 서비스 구성 요구 사항을 식별합니다.</li><br><li>직접 라우팅 또는 통화 계획을 배포하고 구성할지 여부를 결정합니다.<li>배포할 전화 시스템 기능 기능을 결정합니다(서비스 결정).</li><li>통화 플랜 또는 직접 라우팅에 대한 사용자 기능 요구 사항을 식별합니다.</li><li>통화 플랜 또는 직접 라우팅에 대한 서비스 구성 요구 사항을 식별합니다.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>테스트 계획 접근 방식을 개발하고 문서화합니다.</li><li>오디오 회의 기능에 대한 범위에서 서비스 환경 및 사용자를 준비합니다.</li><li>통화 플랜 또는 직접 라우팅 기능에 대한 범위에서 서비스 환경 및 사용자를 준비합니다.</li><li>사용하도록 설정하려는 오디오 회의 기능에 대한 테스트 유효성 검사를 실행합니다.</li><li>사용하려는 통화 계획 또는 직접 라우팅 기능에 대한 테스트 유효성 검사를 실행합니다.</li><li>테스트 실패의 경우 구성이 올바른지 확인하고, 커뮤니티 문서를 검토하고, 필요한 경우 지원 사례를 제기합니다.</li></ul></td></tr>
</table>


Teams 오디오 회의 테스트를 수행하는 방법에 대한 자세한 지침은 [오디오 회의 대한 자세한 테스트 가이드를](./deploy-audio-conferencing-teams-landing-page.md) 참조하세요.

Teams 통화 플랜 테스트를 수행하는 방법에 대한 자세한 지침은 전화 시스템 [대한 자세한 테스트 가이드를](./cloud-voice-landing-page.md) 참조하세요.

<!--ENDOFSECTION-->