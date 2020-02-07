---
title: Microsoft 팀 클라우드 음성 서비스 배포 준비
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: 온 보 딩 검사 목록을 사용 하 여 팀을 위한 Office 365을 준비 하 고 팀 핵심 기능, 네트워킹, 클라우드 음성 작업을 구성 합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 418496b5dd86fb9720393721854c0fcf68daf52a
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825146"
---
# <a name="prepare-my-service"></a>내 서비스 준비

이 문서에서는 조직에 대 한 클라우드 음성 서비스를 준비 하기 위한 요구 사항을 간략하게 설명 합니다. 올바르게 준비 하면 조직에 클라우드 음성 기능을 제공할 수 있습니다.

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a>Microsoft 팀의 온 보 딩 검사 목록 음성 작업 부하

다음 검사 목록은 Microsoft 팀에서 오디오 회의, 통화 요금제 ("통화 요금제"), 전화 시스템 직접 라우팅 ("다이렉트 라우팅") 기능을 구현 하는 단계를 안내 합니다.

*  [팀 용 Office 365 준비](onboarding-checklist-enable-office-365.md)

*  [팀 핵심 기능 구성](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [네트워킹 구성](onboarding-checklist-configure-networking.md)

*  [팀에서 클라우드 음성 작업 부하 구성](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [팀에서 직접 라우팅 구성](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

이러한 검사 목록의 작업 및 활동은 팀과 클라우드 음성 기능의 모든 배포에 적용 되는 핵심 "할 일" 항목입니다. 자신의 팀에서 여행 하는 작업과 관련 된 활동과 작업을 포함 하도록 검사 목록을 사용자 지정할 수 있습니다.

>[!NOTE]
>이 가이드는 통화 요금제, 오디오 회의 및 직접 라우팅에만 초점을 둔 것입니다. 팀을 처음 접하는 경우 [Microsoft 팀 개요](teams-overview.md)를 검토 하세요. 팀 배포 계획에 대 한 일반적인 지침은 [Microsoft 팀에서 채팅, 팀, 채널 및 앱 배포](deploy-chat-teams-channels-microsoft-teams-landing-page.md)를 시작 하세요.

제공 된 검사 목록을 사용 하 여 개별 활동 및 작업의 상태를 추적 하 고 중요 한 단계를 건너뛰지 않았는지 확인 합니다. 각 활동에는 필요한 작업에 대 한 자세한 설명과 해당 활동을 완료 하는 데 사용할 수 있는 추가 정보에 대 한 참조가 포함 됩니다.

검사 목록을 순서 대로 수행 하는 것이 좋지만 정확한 순서는 배포의 범위와 환경의 구성 및 복잡도에 따라 달라 집니다. 이는 "greenfield" 팀 배포 (비즈니스용 Skype Online 현재 상태를 포함 하지 않음) 또는 비즈니스용 Skype Online에서 팀으로 마이그레이션을 지원 하도록 구성 되어 있습니다. 비즈니스용 Skype Online에서 마이그레이션하는 경우 이미 이러한 활동 중 일부를 완료 했 고 지금 무시할 수 있습니다.

사이트 별로 온 보 딩 사용자는 이러한 검사 목록의 보조 가이드로 [음성 (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 을 사용 하 여 사이트를 Playbook 하는 방법을 사용할 것을 적극 권장 합니다.

>[!NOTE]
>대부분의 구성 설정은 팀과 비즈니스용 Skype Online 간에 일반적입니다. Microsoft 365 관리 센터 및 Microsoft 팀 관리 센터를 사용 하 여 해당 설정을 구성할 수 있습니다.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>온 보 딩 검사 완료에 대 한 책임은 누가 overseeing?</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>온 보 딩 검사 목록을 다운로드 합니다.</li><li>조직의 배포 계획에 따라 온 보 딩 검사 목록 항목을 단계별로 진행 합니다.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a>온 보 딩 계속

이러한 검사 목록을 완료 하면 팀 배포에 음성 기능을 추가 하는 데 성공 하 게 됩니다.

다음 단계로, [Playbook (Playbook) 사이트](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) 사용을 위해 각 사이트의 사용자를 등록 하 고 중요 한 사이트별 작업을 계획 하 고 실행 하도록 도와 보세요.

-   사이트 출시 계획으로 준비 된 사이트

-   서비스 관리 프로세스 설정

-   테스트 및 재구성 실행

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a>팀에서 클라우드 음성 작업 부하 테스트

구상 단계의 일부로 팀 구름 음성 비즈니스 성공 및 기술 구현 계획을 정의 하 고 문서화 하 고 관리 센터에서 원하는 구성을 수행 하는 경우 다음 단계는 조직의 예측 및 요구 사항은 기능, 기능 및 유용성을 통해 충족 됩니다. 프로덕션 환경에서 파일럿 또는 최종 배포를 배포 하기 전에이 유효성 검사 단계를 수행 해야 합니다.

구상 단계에서 정의한 비즈니스 성공 계획을 활용 하 여 테스트 단계 중 평가할 활동, 기대, 기능/기능 테스트 사례 및 전체 범위를 결정 하는 기준으로 사용할 수 있습니다.

## <a name="define-your-testing-approach"></a>테스트 접근 방법 정의

가장 간단한 형태의 테스트 접근 방법은 오디오 회의, 통화 계획 또는 직접 라우팅 서비스의 기능을 검토 하 고 사용자가 범위 내에서 기능 요구 사항이 충족 되는지 확인 하기 위해 테스트 계획을 개발 하는 것을 기반으로 합니다. 다음은 오디오 회의 구현의 온보드 단계에 대 한 테스트 계획 예제입니다.


| 테스트를 위한 오디오 회의 기능 | 결과 요약 | 추가 참고 사항 |
|------------|-----------------|------------------|
| 오디오 회의 전화 접속 정보가 포함 된 임시 팀 모임 예약 | 합격/불합격   | TBD |
| 제공 되는 전화 접속 정보를 사용 하 여 PSTN에서 모임에 전화를 걸어 모임 오디오를 사용 합니다. | 합격/불합격 | TBD |
| PSTN을 통해 전화를 걸어 기존 모임에 다른 사용자에 게 참가 | 합격/불합격 | TBD |



| 테스트에 대 한 통화 계획 또는 다이렉트 라우팅 기능 | 결과 요약 | 추가 참고 사항 |
|----------------------------------------------------|-----------------|------------------|
| PSTN 번호를 사용 하 여 PSTN 전화 걸기       | 합격/불합격       | TBD |
| 외부 회선 (휴대 전화, 유선전화)에서 PSTN 번호를 눌러 PSTN 통화 받기 | 합격/불합격 | TBD|
| 한 팀 사용자의 PSTN 통화를 다른 사람에 게 전송 | 합격/불합격 | TBD |


>[!TIP]
>테스트 사례를 시작 지점으로 만들기 위해 [팀 모임 및 통화](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings)에서 사용할 수 있는 사용자 지침 목록을 참조 하세요.

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a>팀에 대 한 클라우드 음성 작업 부하 설정

테스트 접근 방식을 정의 했으므로 다음 단계는 팀 클라우드 음성 기능에 대 한 범위에서 서비스 환경 및 사용자를 구성 하는 것입니다.

추가 정보는 다음을 참조 하세요.

- [오디오 회의를 위한 기술 계획](cloud-voice-deployment.md)

- [Microsoft 팀을 위한 오디오 회의 설정](set-up-audio-conferencing-in-teams.md)

- [통화 요금제를 사용 하 여 전화 시스템에 대 한 기술 계획](calling-plan-landing-page.md)

- [비즈니스용 Skype 및 Microsoft 팀에 대 한 통화 계획 설정](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [직접 라우팅 계획](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [직접 라우팅 구성](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a>테스트 계획 실행

[//]: # (편집 하 시겠습니까? "사용자"가 조금 불확실 한 것 같습니다.)
사용자 환경과 서비스가 구성 되 면 테스트의 마지막 단계에서는 기능 및 기능 유효성 검사에 대 한 포커스가 있는 테스트 계획 실행을 포함 합니다. 

**범위에서 사용자 및 사이트에 대 한 필수 구성 요소 및 가정을 테스트 하는 오디오 회의:**

-   오디오 회의 서비스에 대 한 비즈니스 사용 사례 정의가 완료 되었습니다.

-   오디오 회의에 필요한 라이선스를 사용할 수 있으며 할당 되었습니다.

-   조직 사이트 및 사용자 그룹 목록이 식별 되었습니다.

-   언어 기본 설정이 있는 전용 및 공유 오디오 회의 전화 접속 번호 목록이 식별 되 고 구성 되었습니다.

-   조직에 대해 [통신 크레딧을](what-are-communications-credits.md) 설정 했습니다 (필요한 경우).

-   오디오 회의 회의 브리지 설정이 식별 되 고 구성 되었습니다 (PIN 길이, 입력/종료 알림, 사용 알림 기본 설정).

-   오디오 회의 전화 접속 시나리오를 지 원하는 테 넌 트 회의 정책 및 다이얼 플랜 설정은 확인, 구성 및 적용 되었습니다.

-   오디오 회의 준수 요구 사항이 식별 되 고 구성 되었습니다.

**범위에서 사용자 및 사이트에 대 한 요구 사항 및 전제 조건을 테스트 하는 통화 계획:**

-   통화 계획 서비스에 대 한 비즈니스 사용 사례 정의가 완료 되었습니다.

-   통화 요금제에 필요한 라이선스를 사용할 수 있으며 할당 되었습니다.

-   조직 사이트 및 사용자 그룹 목록이 식별 되었습니다.

-   사용자에 게 할당 될 전화 번호를 Microsoft로 구입 또는 이식 했으며, 테 넌 트 포털에서 사용할 수 있습니다.

-   조직에 대해 [통신 크레딧을](what-are-communications-credits.md) 설정 했습니다 (필요한 경우).

-   호출 계획 시나리오를 지 원하는 테 넌 트 사용자 정책 및 다이얼 플랜 설정은 식별, 구성 및 적용 되었습니다.

-   통화 계획 준수 요구 사항이 식별 되 고 구성 되었습니다.

**범위에서 사용자 및 사이트에 대 한 직접 라우팅 테스트 선행 조건과 가정:**

-   다이렉트 라우팅 서비스에 대 한 비즈니스 사용 사례 정의가 완료 되었습니다.

-   직접 라우팅에 필요한 라이선스를 사용할 수 있으며 할당 되었습니다.

-   조직 사이트 및 사용자 그룹 목록이 식별 되었습니다.

-   일반 [SBC (인증 된 세션 경계 컨트롤러)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) 는 전화 시스템을 사용 하 여 배포, 구성 및 페어링 되었습니다.

-   Enterprise voice가 사용 하도록 설정 되 고 전화 번호가 지정 되었습니다.

-   음성 라우팅 정책을 확인 하 고 구성 하 고 할당 했습니다.

-   Microsoft 팀은 범위 내의 사용자에 대 한 기본 호출 클라이언트로 설정 되었습니다.
 
-   직접적인 라우팅 준수 요구 사항이 식별 되 고 구성 되었습니다.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>의사 결정 지점</td><td><ul><li>배포할 오디오 회의 기능 기능을 결정 합니다 (서비스 의사 결정).</li><li>오디오 회의에 대 한 사용자 기능 요구 사항을 확인 합니다.</li><li>오디오 회의에 대 한 서비스 구성 요구 사항을 확인 합니다.</li><br><li>직접 라우팅 또는 호출 계획이 배포 되 고 구성 되는지 여부를 결정 합니다.<li>어떤 전화 시스템 기능 기능을 배포할지 결정 합니다 (서비스 의사 결정).</li><li>통화 요금제 또는 직접 라우팅에 대 한 사용자 기능 요구 사항을 확인 합니다.</li><li>통화 요금제 또는 직접 라우팅에 대 한 서비스 구성 요구 사항을 확인 합니다.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>다음 단계</td><td><ul><li>테스트 계획 방법을 개발 하 고 문서화 합니다.</li><li>오디오 회의 기능을 위한 범위 내에서 서비스 환경과 사용자를 준비 합니다.</li><li>서비스 환경 및 사용자를 통화 계획 또는 다이렉트 라우팅 기능에 대 한 범위 내에서 준비 합니다.</li><li>사용 하도록 설정할 오디오 회의 기능에 대 한 테스트 유효성 검사를 실행 합니다.</li><li>사용 하도록 설정 하려는 호출 계획 또는 직접 라우팅 기능에 대 한 테스트 유효성 검사를 실행 합니다.</li><li>테스트 실패에 대 한 구성이 올바른지 확인 하 고 커뮤니티 문서를 검토 하 고 필요한 경우 지원 사례를 발생 시킵니다.</li></ul></td></tr>
</table>


팀에서 오디오 회의 테스트를 수행 하는 방법에 대 한 자세한 지침은 [오디오 회의에 대 한 자세한 테스트 가이드](onboarding-test-plan-for-enterprises-Audio-Conferencing.md)를 참조 하세요.

팀에서 통화 계획에 대 한 테스트를 수행 하는 방법에 대 한 자세한 내용은 [전화 시스템에 대 한 자세한 테스트 가이드](onboarding-test-plan-for-enterprises-Phone-System.md)를 참조 하세요.

<!--ENDOFSECTION-->
