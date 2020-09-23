---
title: 오디오 회의 설정 구성 - Microsoft Teams
ms.reviewer: ''
description: 다음의 배포 리소스를 사용하여 Microsoft Teams에서의 모임 작업의 일부로 오디오 회의를 출시하는 데 도움을 줄 수 있습니다.
ms.topic: article
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: admin
ms.date: 01/28/2019
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
ms.custom: seo-marvel-mar2020
f1.keywords:
- NOCSH
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90801c09a9dda27923fba49a3e8cbc2ef4f65e4e
ms.sourcegitcommit: fb4edc26c566228d74c10cb51a063b5fdc7e11a1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177348"
---
# <a name="learn-how-to-deploy-audio-conferencing-in-microsoft-teams"></a>Microsoft Teams에서 오디오 회의를 배포하는 방법 알아보기

오디오 회의는 일반 휴대폰에서 Teams 모임에 참가하고 모임에서 전화 번호로 전화를 걸 수 있는 기능입니다. 조직에서 오디오 회의를 출시하는 과정의 일부로서 [모임의 출시](deploy-meetings-microsoft-teams-landing-page.md)를 검토했는지 확인합니다.

## <a name="audio-conferencing-deployment-decisions"></a>오디오 회의 배포 결정

이 문서는 조직의 프로필 및 비즈니스 요구 사항에 따라 기본 오디오 회의의 설정을 변경할지 여부를 결정하는데 도움을 주고 각 변경 내용에 대해서 설명을 합니다. 당사는 사용자가 [변경할 가능성이 큰](#core-deployment-decisions) 변경 내용의 핵심 집합에서 시작하여 설정을 두 그룹으로 나누었습니다. 두 번째 그룹은 조직의 요구 사항에 따라 구성하고자 하는 [추가 설정](#additional-deployment-decisions)을 포함합니다.

모임 일정을 계획하거나 주도하는 사용자들을 위해 오디오 회의를 설정하기만 하면 됩니다. 전화를 거는 모임 참석자는 해당 사용자에게 할당된 라이선스 혹은 그 외 설정이 필요하지 않습니다. 노트북이나 모바일 장치에 설치된 비즈니스용 Skype 혹은 Teams 앱을 이용하여 모임에 전화를 거는(통화를 하는) 기능은 외부에 있어 모임에 참석할 수 없는 사용자들에게 매우 유용합니다. 


## <a name="audio-conferencing-prerequisites"></a>오디오 회의 필수 구성 요소 

Teams용 오디오 회의를 출시하기 전에 다음의 사항을 고려합니다.

|본인에게 질의하기|작업 |
|------------|-------|
|내 국가/지역에서 오디오 회의를 사용할 수 있나요?|본인의 국가/지역에서 오디오 회의를 사용할 수 있는지 확인하려면 [오디오 회의 및 통화 플랜에 대한 국가 및 지역의 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)을 참조하세요.|
|사용자에게 Teams 오디오 회의에 적절한 라이선스가 있나요?|오디오 회의 라이선스는 Microsoft 365 혹은 Office 365 E5 구독의 일부로 사용할 수 있으며 혹은 Microsoft 365 Business Standard, E1 또는 E3 구독의 추가 기능 서비스로 사용할 수 있습니다. <ul><li>라이선스를 받고 할당하려면 [Microsoft 365 혹은 Office 365에서의 오디오 회의 체험 혹은 구입](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365) 및 [비즈니스용 Microsoft 365 앱의 라이선스 할당 또는 제거](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)를 참조합니다.</li><li> 자세한 내용은 [Microsoft Teams의 추가 기능 라이센싱](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)을 검토하세요. </li><li>각 플랜에 어떤 클라우드 기능이 포함 되어있는지 확인하려면 [플랜에 기반한 라이선스 옵션](teams-add-on-licensing/office-365-business-premium.md) 문서를 참조하세요.</li></ul>|
|오디오 회의 라이선스가 할당된 사용자를 위해 통신 크레딧을 구매해야 하나요?|자세한 내용을 보려면 [통신 크레딧 소개](what-are-communications-credits.md)를 검토하고 아래에 있는 [통신 크레딧](#communications-credits) 섹션을 참조하세요.|
|||


## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

오디오 회의 필수 구성 요소를 충족시킨 후 사용자를 위한 오디오 회의를 구성하기 위해 다음의 작업을 완료합니다.


### <a name="teams-administrators"></a>Teams 관리자

Teams는 조직의 팀을 관리하는데 사용할 수 있는 사용자 지정 관리자 역할의 집합을 제공합니다. 역할은 관리자에게 다양한 기능을 제공합니다. 

| 본인에게 질의하기 | 작업 |
|--------------|--------|
|Teams 커뮤니케이션 관리자 역할은 누구에게 할당될 것인가요?|Teams 관리자 역할에 대한 자세한 내용은 [팀을 관리하기 위한 Microsoft Teams 관리 역할의 활용](using-admin-roles.md)을 참조하세요.|
|Teams 커뮤니케이션 지원 기술자 역할은 누구에게 할당될 것인가요?|관리 역할을 할당하려면 [Azure Active Directory를 사용하여 사용자에게 관리자 및 비관리자 역할 할당](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)을 참조하세요.|
|Teams 커뮤니케이션 지원 전문가자 역할은 누구에게 할당할 것인가요?||
|||

### <a name="conferencing-bridges-and-phone-numbers"></a>회의 브리지 및 전화 번호

회의 브리지를 통해 사용자는 휴대폰을 사용하여 모임에 전화를 걸 수 있습니다. 회의 브리지에 대한 기본 설정을 사용하거나 전화번호(유료 및 무료) 및 PIN이나 사용 언어와 같은 기타 설정을 변경할 수 있습니다.

자세한 내용은 [오디오 회의](audio-conferencing-in-office-365.md)를 참조하세요.

|본인에게 질의하기|작업 |
|------------|-------|
|새 회의 브리지 번호를 추가해야 하나요?| 새 번호를 추가하려면 [서비스 전화 번호 가져오기](/microsoftteams/getting-service-phone-numbers)를 참조하세요.|
|브리지 설정을 수정해야 하나요?|브리지 설정을 수정하려면 [오디오 회의 브리지의 설정 변경](change-the-settings-for-an-audio-conferencing-bridge.md)을 참조하세요.|
|오디오 회의에 사용할 포트 번호가 필요하나요?|전화 번호 포팅에 대한 내용은 [Teams로 전화 번호 전송](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)을 참조하세요.|
|||


### <a name="default-and-alternate-languages"></a>기본 및 대체 언어

Teams 오디오 회의를 사용하여 회의 브리지의 기본 및 대체 언어를 설정할 수 있습니다.

|본인에게 질의하기|작업 |
|------------|-------|
| 자동 전화 교환 인사말에 어떤 언어를 선택해야 하나요? | 언어를 선택하려면 [오디오 회의의 자동 전화 교환 언어 설정](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/set-auto-attendant-languages-for-audio-conferencing?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)을 참조하세요.|
|||

### <a name="conferencing-bridge-settings"></a>회의 브리지 설정 

기본 및 대체 언어를 포함하여 회의 브리지를 설정한 후에는 입력/종료 알림과 PIN 길이와 같은 기본 설정을 사용하고자 하는지 확인해야 합니다. 그렇지 않은 경우 변경할 수 있습니다. 

|본인에게 질의하기|작업 |
|------------|-------|
| 사용자가 모임에 참가하거나 모임을 끝낼 때 참석자가 알림을 듣게 되나요? | 이들 설정을 변경하려면 [오디오 회의 브리지의 설정 변경](change-the-settings-for-an-audio-conferencing-bridge.md)을 참조하세요.|
|모임 주최자가 모임을 시작하는 데 사용하는 PIN의 필수 길이는 얼마인가요?||
|||

### <a name="dial-in-phone-number-settings-for-users-who-lead-meetings"></a>모임을 주도하는 사용자를 위한 전화 접속 번호 설정

오디오 회의 브리지를 만든 후에는 회의를 주도하는 사용자가 사용할 유료/무료 번호를 설정해야 합니다.

|본인에게 질의하기|작업 |
|------------|-------|
| 모임을 주도하는 각 사용자에게 어떤 회의 브리지 번호를 할당하나요? | 사용자에게 접속 전화 번호를 할당하려면 [7 단계: 모임을 주도하는 사용자를 위한 접속 전화 번호 할당](set-up-audio-conferencing-in-teams.md#step-7-assign-dial-in-phone-numbers-for-users-who-lead-meetings)을 참조하세요. |
|||

### <a name="communications-credits"></a>통신 크레딧

무료 회의 브리지 전화번호를 제공하고 국제 전화번호 회의 전화 접속을 지원하기 위해서는 조직에 통신 크레딧을 설정해야 합니다. 통신 크레딧에 대한 자세한 내용은 [통신 크레딧이란?](what-are-communications-credits.md)을 참조하세요.

|본인에게 질의하기|작업 |
|------------|-------|
|오디오 회의의 구현에 통신 크레딧이 필요한가요? |통신 크레딧을 설정해야 하는지의 여부를 확인 하려면 [조직에 대한 통신 크레딧 설정](set-up-communications-credits-for-your-organization.md)을 참조하세요.|
|필요한 경우 얼마나 구입해야 하나요?|통신 크레딧 금액을 정하려면 [권장 되는 자금 금액](what-are-communications-credits.md#recommended-funding-amounts)을 참조하세요.|
|자동 재충전 금액을 구성하는 것이 좋은가요?|자동 재충전 금액을 구성하려면 [조직에 대한 통신 크레딧 설정](set-up-communications-credits-for-your-organization.md)을 참조하세요.|
|||



## <a name="additional-deployment-decisions"></a>추가 배포 결정사항

조직의 요구 사항 및 구성에 따라 이러한 설정을 변경하는 것이 좋습니다.

### <a name="outbound-calling-restriction-policies"></a>아웃바운드 호출 제한 정책 

관리자는 아웃바운드 호출 제어를 사용하여 조직의 사용자가 만들 수 있는 오디오 회의 및 최종 사용자 PSTN 통화 유형을 제한할 수 있습니다.

|본인에게 질의하기|작업 |
|------------|-------|
| 허용되는 아웃바운드 통화 유형을 제한해야 하나요? | 아웃바운드 통화를 제한하려면 [오디오 회의 및 사용자 PSTN 통화에 대한 아웃바운드 통화 제한 정책](outbound-calling-restriction-policies.md)을 참조하세요.|
|||


### <a name="dial-plans"></a>다이얼 플랜

다이얼 플랜은 Microsoft 365 혹은 Office 365에서 전화 시스템의 일부로서, 통화 승인 및 통화 라우팅을 위해 전화번호를 대체 형식(일반적으로 E.164 형식)으로 변환하는 정규화 규칙의 집합입니다.

다이얼 플랜에 대한 자세한 내용은 [다이얼 플랜이란?](what-are-dial-plans.md)을 참조하세요.

|본인에게 질의하기|작업 |
|------------|-------|
|조직에 사용자 지정 다이얼 플랜이 필요한가요?|사용자 지정 다이얼 플랜이 필요한지 판단하는 데 도움이 되는[테넌트 다이얼 플랜 계획하기](what-are-dial-plans.md#planning-for-tenant-dial-plans)를 참조하세요. |
|사용자 지정 다이얼 플랜을 필요로 하는 사용자는 누구이고 각 사용자에게 할당해야 하는 테넌트 다이얼 플랜은 무엇인가요?|PowerShell을 사용하여 사용자 지정된 다이얼 플랜에 사용자를 추가하려면 [다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md)를 참조하세요.|
|||

### <a name="troubleshoot-meeting-and-call-quality"></a>모임 및 통화 품질 문제 해결 

Teams는 통화 품질 문제를 모니터링하고 문제를 해결하기 위한 두 가지 방법인 [통화 분석 및 통화 품질 대시보드](monitor-call-quality-qos.md)를 제공합니다. Call Analytics에는 각 사용자의 특정 통화 및 모임과 관련된 디바이스, 네트워크 및 연결에 대한 자세한 정보가 표시됩니다. Call Analytics는 관리자와 지원 센터 상담원이 특정 통화의 통화 품질 문제를 해결하는데 도움을 주기 위해 설계되었고 통화 품질 대시보드는 관리자와 네트워크 엔지니어가 네트워크를 최적화하는데 도움을 주기 위해 설계되었습니다. 통화 품질 대시보드는 특정 사용자로부터 포커스를 이동하고 대신 전체 Teams 조직에 대한 집계 정보를 조사합니다. 

|본인에게 질의하기|작업 |
|------------|-------|
| 통화 품질 문제를 모니터링하고 문제를 해결할 책임이 있는 사용자는 누구인가요? | 통화 품질 문제를 해결하는 데 필요한 사용 권한 수준에 대한 내용은 [Call Analytics를 사용하여 통화 품질 저하 문제를 해결](use-call-analytics-to-troubleshoot-poor-call-quality.md)을 참조하세요.|
|||


## <a name="next-steps"></a>다음 단계
- 조직에서 오디오 회의의 [채택을 주도](adopt-microsoft-teams-landing-page.md)합니다.
- [클라우드 음성 출시](cloud-voice-landing-page.md)
- 최초 Teams를 배포 시 플래너와 같은 추천 앱을 포함합니다. Teams의 채택을 주도하면서 다른 [앱, 봇 & 커넥터](deploy-apps-microsoft-teams-landing-page.md)를 추가합니다.
