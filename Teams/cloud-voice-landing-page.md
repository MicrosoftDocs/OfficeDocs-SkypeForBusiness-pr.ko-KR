---
title: Microsoft Teams의 클라우드 음성
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: 클라우드 음성 기능에 대해 자세히 알아보고 필요한 배포 결정을 이해 하세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 851e14e934578b0da8853991e1bc993e8483f818
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814878"
---
# <a name="voice---phone-system-and-pstn-connectivity-options"></a>음성 전화 시스템 및 PSTN 연결 옵션

[시작](get-started-with-teams-quick-start.md)을 완료했습니다. 조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다. [모임 & 회의](deploy-meetings-microsoft-teams-landing-page.md)를 배포 했을 수도 있습니다. 이제 사용자에 게 음성 기능을 추가할 준비가 되었습니다. 

음성은 PBX (개인 브랜치 교환) 기능 및 PSTN (공개 통신 네트워크)에 연결 하기 위한 옵션을 제공 합니다.

이 문서는 조직의 프로필 및 비즈니스 요구 사항에 따라 기본 음성 설정을 변경 해야 하는지 여부를 결정 하는 데 도움이 되며 각 변경 내용을 안내 합니다. 두 그룹으로 설정 된 핵심 [변경 내용](#core-deployment-decisions)집합부터 시작 하 여 설정을 나눌 수 있습니다. 두 번째 그룹은 조직의 요구 사항에 따라 구성하고자 하는 [추가 설정](#additional-deployment-decisions)을 포함합니다.

모든 조직에서 핵심 의사 결정을 수행 하는 것이 좋으며 조직에 추가 요구 사항이 있는 경우 다음 자료를 검토 합니다.

 > [!Note]
 > 자세한 내용은 [플랫폼용 팀 기능](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3) 을 참조 하세요.

## <a name="learn-more-about-voice"></a>음성에 대 한 자세한 정보

다음 문서는 팀에서 음성 기능을 배포 하 고 사용 하는 방법에 대 한 자세한 정보를 제공 합니다.

- [Microsoft 365 또는 Office 365의 전화 시스템](what-is-phone-system-in-office-365.md)
- [통화 요금제가 포함 되어 있는 전화 시스템](calling-plan-landing-page.md)
- [전화 시스템 직접 라우팅](direct-routing-landing-page.md)
- [Microsoft 전화 통신 솔루션](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- 전화 시스템에 대 한 자세한 내용을 보려면 다음 세션을 시청 하세요. [Microsoft 팀의 전화 시스템 소개](https://aka.ms/teams-phone-system)


## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

대부분의 조직이 변경하려는 설정입니다 (Teams의 기본 설정이 조직에 적합하지 않은 경우).

## <a name="phone-system-office-365"></a>전화 시스템 (Office 365)

전화 시스템은 Microsoft 365 또는 Office 365 클라우드에서 통화 제어 및 PBX (개인 브랜치 교환) 기능을 사용 하도록 설정 하기 위한 Microsoft의 기술입니다. 전화 시스템을 사용 하면 기존 개인 분기 교환 (PBX) 시스템을 Microsoft 365 또는 Office 365에서 직접 제공 되는 기능 집합으로 대체 하 고 회사의 클라우드 생산성 환경에 긴밀 하 게 통합할 수 있습니다.


|본인에게 질의하기|작업 |
|:------------|:-------|
|어떤 사용자 위치 또는 사무실에서 전화 시스템을 구현 하나요? |전화 시스템에 대 한 자세한 내용은 [Microsoft 365 또는 Office 365의 전화 시스템](what-is-phone-system-in-office-365.md)을 참조 하세요.</li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a>PSTN (공개 교환 전화 네트워크)에 대 한 연결

사용자가 전세계에서 전화를 걸 수 있도록 휴대폰 시스템을 PSTN (공개 교환 전화 네트워크)에 연결 하려면 비즈니스 요구 사항에 따라 옵션을 사용 합니다.  사용자에 게 다음을 요청 합니다.


|본인에게 질의하기|작업 |
| :------------|:-------|
| Microsoft 통화 요금제를 내 통신 회사로 사용 하 고 싶으세요? | 자세한 내용은 통화 [요금제를 사용 하는 전화 시스템](calling-plan-landing-page.md)을 참조 하세요.|
| 자체 전화 통신 회사를 사용 해야 하나요? | 자세한 내용은 [직접 라우팅이 포함 되어 있는 전화 시스템](direct-routing-landing-page.md)을 참조 하세요.
|||


## <a name="additional-deployment-decisions"></a>추가 배포 결정사항

조직의 필요 및 구성에 따라 다음에 대 한 설정을 변경할 수 있습니다.

- 음성 메일
- 통화 id
- Microsoft의 전화 번호
- 다이얼 플랜
- 통화 큐
- 자동 전화 교환

### <a name="voicemail"></a>음성 메일

Azure 보이스 메일 서비스를 통해 제공 되는 클라우드 보이스 메일은 Exchange 사서함에 대 한 보이스 메일 저축과 지원 하며 타사 전자 메일 시스템을 지원 하지 않습니다. 클라우드 보이스 메일에는 조직의 모든 사용자가 기본적으로 사용 하도록 설정 된 음성 메일의 내용이 포함 됩니다. 비즈니스 요구에 따라 특정 사용자 또는 조직 전체에 대 한 보이스 메일을 사용 하지 않도록 설정 해야 할 수 있습니다.

|본인에게 질의하기|작업 |
|:------------|:-------|
| 클라우드 보이스 메일을 사용 하 고 싶으세요? | 보이스 메일 설정 절차는 [클라우드 보이스 메일 설정을](set-up-phone-system-voicemail.md)참조 하세요.
| 일부 또는 전체 사용자에 대해 음성 메일을 사용 하도록 설정 하 고 싶으신가요? | 보이스 메일 기록을 끄려면 [조직의 보이스 메일 정책 설정을](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization)참조 하세요.</li></ul>|
|||

### <a name="calling-identity"></a>통화 id

기본적으로 모든 아웃 바운드 통화는 지정 된 전화 번호를 통화 id (발신자 ID)로 사용 합니다. 통화를 받는 사람은 발신자를 빠르게 확인 하 고 통화 수락 또는 거부 여부를 결정할 수 있습니다.

|본인에게 질의하기|작업 |
|:------------|:-------|
|발신자 ID를 마스킹 또는 사용 하지 않도록 설정 하 시겠습니까? | 발신자 ID를 변경 하거나 차단 하려면 [사용자의 발신자 Id 설정을](set-the-caller-id-for-a-user.md)참조 하세요. |
|||

### <a name="phone-numbers-from-microsoft"></a>Microsoft의 전화 번호

Microsoft에는 두 가지 유형의 전화 번호, 즉 조직의 사용자에 게 할당할 수 있는 *구독자* (사용자) 번호와 구독자 번호 보다 높은 동시 통화 용량을 갖는 유료 서비스 번호와 *서비스* 번호, 그리고 오디오 회의, 자동 전화 교환, 통화 대기열 등의 서비스에 할당할 수 있습니다.

|본인에게 질의하기|작업 |
| :------------|:-------|
| Microsoft에서 새 전화 번호를 필요로 하는 사용자 위치는 무엇 인가요? | 전화 번호를 가져오는 방법에 대 한 자세한 내용은 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 및 [사용자의 전화 번호 가져오기를](getting-phone-numbers-for-your-users.md)참고 하세요. 
| 어떤 종류의 전화 번호 (구독자 또는 서비스)가 필요 합니까? | 필요한 전화 번호 유형을 선택 하는 데 도움이 되도록 [통화 요금제에 사용 되는 다른 종류의 전화](different-kinds-of-phone-numbers-used-for-calling-plans.md)번호를 참조 하세요.
기존 전화 번호를 팀에 게 이식 하려면 어떻게 하나요?|자세한 내용은 [Microsoft 팀으로 전화 번호 전송을](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)참조 하세요.
|||

### <a name="dial-plans"></a>다이얼 플랜

Microsoft 365 또는 Office 365의 전화 시스템 기능에 있는 다이얼 플랜은 전화 걸기 전화 번호를 대체 형식 (일반적으로 E. \ 164 형식)으로 변환 하는 표준화 규칙 집합으로, 통화 승인 및 통화 라우팅을 위한 것입니다.

다이얼 플랜에 대한 자세한 내용은 [다이얼 플랜이란?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)을 참조하세요.

|본인에게 질의하기|작업 |
|:------------|:-------|
| 조직에 사용자 지정 다이얼 플랜이 필요한가요? | 사용자 지정 다이얼 플랜이 필요한 지 여부를 결정 하려면 [테 넌 트 다이얼 플랜 계획](what-are-dial-plans.md#planning-for-tenant-dial-plans) 을 참조 하세요.|
사용자 지정 다이얼 플랜을 필요로 하는 사용자는 누구이고 각 사용자에게 할당해야 하는 테넌트 다이얼 플랜은 무엇인가요? | PowerShell의 사용자 지정 다이얼 플랜에 사용자를 추가 하려면 [다이얼 플랜 만들기 및 관리](create-and-manage-dial-plans.md)를 참조 하세요. |
|||

### <a name="call-queues"></a>통화 큐

클라우드 통화 큐에는 사용자가 조직의 전화 번호를 호출할 때 사용 되는 인사말, 통화를 자동으로 대기 하는 기능, 전화를 걸고 있는 사용자가 대기 중인 음악을 수신 대기 하는 동안 사용 가능한 다음 통화 에이전트를 검색 하 여 통화를 처리 하는 기능이 포함 됩니다. 조직에 대 한 단일 또는 복수 통화 대기열을 만들 수 있습니다. 


|본인에게 질의하기|작업 |
|:------------|:-------|
| 내 조직에 통화 대기열이 필요 한가요? | 자세한 내용은 [클라우드 통화 대기열 만들기](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) 및 [전화 시스템 설정을](setting-up-your-phone-system.md)참조 하세요. |

### <a name="auto-attendants"></a>자동 전화 교환

클라우드 자동 전화 교환을 사용 하 여 외부 및 내부 발신자가 조직의 회사 사용자 또는 부서로 전화를 걸고 배치 하거나 양도할 수 있는 조직의 메뉴 시스템을 만들 수 있습니다.

|본인에게 질의하기|작업 |
|:------------|:-------|
| 내 조직에 자동 전화 교환이 필요 한가요? | 자세한 내용은 [클라우드 자동 전화 교환 소개](what-are-phone-system-auto-attendants.md) 및 [클라우드 자동 전화 교환 설정](create-a-phone-system-auto-attendant.md)을 참조 하세요. |

### <a name="devices"></a>디바이스

지원 되는 장치에 대 한 자세한 내용은 다음을 참고 하세요.

- [Microsoft 팀에서 장치 관리](devices/device-management.md)
- [IP 전화](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [USB 오디오 및 비디오 디바이스](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [장치에 대 한 지능형 통신](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


