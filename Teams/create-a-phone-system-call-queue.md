---
title: 통화 대기열 만들기
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
description: Microsoft 팀을 사용 하 여 클라우드 통화 큐 용 전화 시스템을 설정 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: fc958aa1713a7cda12a054b3a029bfc1786b0955
ms.sourcegitcommit: 92a278c0145798266ecbe052e645b2259bcbd62d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/21/2020
ms.locfileid: "42897239"
---
# <a name="create-a-cloud-call-queue"></a>클라우드 통화 큐 만들기

클라우드 통화 대기열은 다음을 제공할 수 있습니다.

- 인사말 메시지입니다.
- 다른 사용자가 대기 중에 음악을 볼 수 있습니다.
- 메일 사용이 가능한 메일 그룹의 통화 에이전트와 보안 그룹에서 통화를 리디렉션합니다.
- 큐 최대 크기, 시간 제한 및 통화 처리 옵션 등의 다른 매개 변수를 설정 합니다.
- 호출자가 조직에 대 한 메시지를 남기기 위해 보이스 메일을 공유 했습니다.

전화 번호를 통화 대기열에 직접 연결 하지 않고, 대신 전화 번호가 [리소스 계정과](manage-resource-accounts.md)연결 되어 있습니다. 전화 큐는 직접 전화를 걸거나 자동 전화 교환에서 선택 하 여 액세스할 수 있습니다.

발신자는 대기 중에 음악을 듣게 되며, 통화 *는 선입 선출 (FIFO* ) 순서에 따라 통화 에이전트에 연결 됩니다.

큐의 모든 호출은 다음 메서드 중 하나를 통해 에이전트로 전송 됩니다.

- 전화 통신 라우팅을 사용 하면 큐의 첫 번째 호출이 동시에 모든 에이전트를 울릴 때
- 직렬 라우팅을 사용 하면 큐의 첫 번째 호출이 모든 통화 에이전트를 하나씩 울립니다.
- 라운드 로빈으로, 들어오는 호출의 라우팅이 각 호출 에이전트가 대기열에서 같은 수의 통화를 제공 하도록 균형을 유지 합니다.

    > [!NOTE]
    > **오프 라인**상태 이거나, 현재 상태가 **방해** 금지로 설정 되어 있거나, 통화 대기열에서 전화가 걸려 있지 않은 경우 전화를 받을 수 있습니다.

- 한 번에 하나의 수신 전화 알림 (큐 헤드의 통화에 대 한)만 통화 에이전트로 이동 합니다.
- 통화 에이전트에서 통화를 수락 하면, 큐에서 다음에 수신 되는 통화가 통화 에이전트로 연결을 시작 합니다.

> [!NOTE]
> 이 문서는 Microsoft 팀과 비즈니스용 Skype Online에 모두 적용 됩니다.

## <a name="step-1--get-started"></a>1 단계-시작 하기

통화 대기열 사용을 시작 하려면 몇 가지 사항을 기억해 야 합니다.

- 통화 대기열에는 연결 된 리소스 계정이 있어야 합니다. 리소스 계정에 대 한 자세한 내용은 [팀에서 자원 계정 관리](manage-resource-accounts.md) 를 참조 하세요.
- 전화 번호를 자원 계정에 할당 하면 이제 비용 무료 전화 시스템 [가상 사용자 라이선스](teams-add-on-licensing/virtual-user.md)를 사용할 수 있습니다. 전화 시스템은 저렴 한 자동 전화 교환 및 통화 대기열 서비스에 사용할 수 있도록 조직 수준의 전화 번호를 허용 합니다.

> [!NOTE]
> 통화 대기열에 대 한 직접 라우팅 서비스 번호는 Microsoft 팀 사용자 및 상담원만 지원 합니다.

> [!NOTE]
> 온라인 상태에 있는 조직 내 사용자에 게 통화를 리디렉션하려면 **전화 시스템** 라이선스가 있어야 하며 Enterprise Voice를 사용 하도록 설정 되어 있거나 Office 365 통화 계획이 있어야 합니다. [Microsoft 팀 라이선스 할당](assign-teams-licenses.md)을 참조 하세요. 엔터프라이즈 음성에 대해 사용 하도록 설정 하려면 Windows PowerShell을 사용 하면 됩니다. 예를 들어 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Office 365 통화 요금제에 대 한 자세한 내용은 [office 365에 대 한](calling-plans-for-office-365.md) [전화 시스템 및 통화 요금제](calling-plan-landing-page.md) 및 통화 요금제를 참조 하세요.

- 클라우드 통화 대기열에는 **Microsoft 팀 관리 센터** 에서 받은 유료 및 무료 서비스 전화번호만 할당할 수 있으며, 다른 서비스 공급자에 게 서 전송 됩니다. 무료 서비스 번호에는 통신 크레딧이 필요 합니다.

    > [!NOTE]
    > 사용자 (구독자) 전화 번호를 통화 대기열에 할당할 수 없음-서비스 수신자 또는 무료 무료 전화 번호를 사용할 수 있습니다.

- 클라우드 통화 대기열과 연결 된 통화 에이전트는 다음 클라이언트가 지원 됩니다.

  - 비즈니스용 Skype 데스크톱 클라이언트 2016 (32 비트 및 64 비트 버전)

  - Lync 데스크톱 클라이언트 2013 (32 비트 및 64 비트 버전)

  - Microsoft 팀에서 지원 되는 모든 IP 전화 모델 [비즈니스용 Skype Online 전화 받기를](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)참조 하세요.

  - Mac 비즈니스용 Skype 클라이언트 (버전 16.8.196 이상)

  - Android 비즈니스용 Skype 클라이언트 (버전 6.16.0.9 이상)

  - iPhone 비즈니스용 Skype 클라이언트 (버전 6.16.0 이상)

  - iPad 용 비즈니스용 Skype 클라이언트 (버전 6.16.0 이상)

  - Microsoft 팀 Windows 클라이언트 (32 비트 및 64 비트 버전)

  - Microsoft 팀 Mac 클라이언트

  - Microsoft 팀 iPhone 앱

  - Microsoft 팀 Android 앱

    > [!NOTE]
    > 직접 라우팅 번호로 지정 된 통화 큐는 비즈니스용 Skype 클라이언트, Lync 클라이언트 또는 비즈니스용 Skype IP 휴대폰을 에이전트로 지원 하지 않습니다.

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a>2 단계-유료 또는 무료 서비스 전화 번호 받기 또는 전송

통화 대기열을 만들고 설정 하기 전에 기존의 유료 또는 무료 서비스 번호를 가져오거나 이전 해야 합니다. 서비스 번호를 얻으려면 [서비스 전화 번호 가져오기를](getting-service-phone-numbers.md) 참조 하거나 기존 서비스 번호를 전송 하려면 [전화 번호를 Office 365에](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)연결을 참조 하세요. 무료 또는 무료 서비스 전화 번호를 얻은 후에는 **Microsoft 팀 관리 센터** > 의**음성** > **전화 번호로**표시 됩니다. 무료 전화 번호에는 다양 한 서비스 **유형** (무료 **)** 이 표시 됩니다.

> [!NOTE]
> 미국 이외의 지역에 거주 하는 경우에는 Microsoft 팀 관리 센터를 사용 하 여 서비스 번호를 얻을 수 없습니다. 미국 이외의 지역에서이를 수행 하는 방법을 확인 하려면 [조직의 전화 번호 관리](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) 로 이동 하세요.

여러 자동 전화 교환을 설정 하는 경우 일반적으로 주 자동 전화 교환의 리소스 계정에 전화 번호를 할당 합니다. 네스트된 자동 전화 교환 또는 통화 대기열에 연결 된 리소스 계정은 전화 번호가 필요 하지 않을 수도 있습니다. 이 자동 전화 교환은 전화 번호가 없는 경우에도 사용자의 통화 큐 또는 중첩 자동 전화 교환에 발신자를 보낼 수 있습니다. 이러한 경우에는 다이얼 패드 옵션을 할당 하지 않고 시스템에서 모든 자동 전화 교환 및 통화 대기열을 만든 다음 나중에 설정을 편집할 수 있습니다. 메뉴 옵션으로 설정 하려면 통화 대기열 또는 자동 수행자가 있어야 합니다.

## <a name="step-3--create-a-call-queue"></a>3 단계-통화 대기열 만들기

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> 모든 통화 대기열에는 연결 된 [리소스 계정이](manage-resource-accounts.md)있어야 합니다. 먼저 리소스 계정을 만든 다음이를 통화 큐에 연결할 수 있습니다.

### <a name="use-the-microsoft-teams-admin-center"></a>Microsoft 팀 관리 센터 사용

**Microsoft 팀 관리 센터**의 **음성** > **통화 대기열**에서 **+ 새로 추가**:를 클릭 합니다.

### <a name="set-the-display-name-and-resource-account"></a>표시 이름 및 리소스 계정 설정

![번호가 매겨진 설명선이 있는 새 통화 대기열 스크린샷](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

![이전 스크린샷](media/teamscallout1.png)
**이름의** 설명선을 참조 하는 숫자 1의 아이콘은 통화 대기열에 대 한 설명 표시 이름을 입력 합니다. 이 이름은 필수 이며 공백을 포함 하 여 최대 64 자를 포함할 수 있습니다.

 이 이름은 수신 전화에 대 한 알림에서 표시 됩니다.

* * *

![숫자 2의 아이콘으로, 이전 스크린샷](media/teamscallout2.png)
의 설명선을 참조 하 고,**계정 추가** 리소스 계정을 선택 합니다. 모든 통화 대기열에는 리소스 계정이 있어야 합니다. 자원 계정에는 서비스 수신자 또는 무료 전화 번호가 필요 하지 않습니다.

나열 되지 않는 경우 앞에서 설명한 대로 통화 대기열을 만들기 전에 서비스 번호를 가져오고이를 리소스 계정에 할당 합니다. 서비스 번호를 얻으려면 [서비스 전화 번호 가져오기를](getting-service-phone-numbers.md)참조 하세요. 전화 번호를 할당 하는 방법에 대 한 구체적인 방법은 [팀에서 자원 계정 관리](manage-resource-accounts.md) 를 참조 하세요.

> [!NOTE]
> **도메인** 을 할당 해야 하는 경우에는 호출 대기열에 대 한 리소스 계정에 할당할 수 있습니다.

### <a name="set-the-greeting-and-music-played-while-on-hold"></a>대기 중에 재생 되는 인사말 및 음악 설정

![숫자 설명선이 있는 인사말 및 음악 옵션 스크린샷](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![숫자 1의 아이콘으로,](media/teamscallout1.png)
**이전 스크린샷의** 설명선을 참조 합니다. 통화 대기열 번호를 호출 하는 사용자를 위해 재생 되는 선택적 인사말입니다.

오디오 파일 (.wav,. mp3 또는 .wma 형식)을 업로드할 수 있습니다.

![번호 2의 아이콘으로, 보류 중인 이전 스크린샷](media/teamscallout2.png)
**음악** 의 설명선을 참조 합니다. 통화 대기열과 함께 제공 된 보류에 대 한 기본 음악을 사용할 수 있습니다. .Wav, mp3 또는 .wma 형식의 오디오 파일을 업로드 하 여 사용자 지정 음악으로 저장할 수도 있습니다.

* * *

### <a name="select-the-call-answering-options"></a>통화 응답 옵션 선택

![통화 응답 옵션 스크린샷](media/5d249515-d532-4af2-90da-011404028b89.png) 

![숫자 1의 아이콘, 이전 스크린샷](media/teamscallout1.png)
**호출 에이전트 및 그룹** 에서 설명선을 참조 하 여 그룹에 추가 하지 않고 개별 에이전트를 직접 추가 하려면 **사용자 추가**를 클릭 합니다. 개별 에이전트는 전화를 받을 순서 대로 설정 합니다. 20 개 이상의 개별 에이전트를 추가 하 여 그룹에 배치할 수 있습니다.

호출은 먼저 개별 에이전트로 라우팅 한 다음 그룹의 에이전트로 전달 됩니다. 

다음 메일 목록 또는 그룹 중 하나에 속한 최대 200 개의 통화 에이전트를 선택할 수 있습니다.

- Office 365 그룹
- 보안 그룹
- 메일 그룹

선택한 통화 상담원은 다음을 수행 해야 합니다. 

- 전화 시스템 라이선스 및 Enterprise Voice가 설정 된 온라인 사용자 
- 통화 요금제를 사용 하는 온라인 사용자
- 온-프레미스 비즈니스용 Skype 서버 사용자

  > [!NOTE]
  > 이는 온라인 상태인 조직의 사용자에 게 전화를 리디렉션하는 경우에도 적용 됩니다. 이러한 개인에 게는 **전화 시스템** 라이선스와 Enterprise Voice가 설정 되어 *있거나* 통화 요금제가 있어야 합니다. 자세한 내용은 [비즈니스용 Skype 라이선스 할당](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Microsoft 팀 라이선스 할당](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)또는 [사용자에 게 적합 한 통화 계획](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page) 을 참조 하세요.

 엔터프라이즈 음성에 대 한 에이전트를 사용 하도록 설정 하려면 Windows PowerShell을 사용 하면 됩니다. 예를 들어 다음을 실행 합니다.`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`

- Office 365 그룹에 추가 되는 **전화 시스템** 라이선스 또는 통화 요금제를 사용 하는 사용자 메일 사용이 가능한 메일 그룹 또는 보안 그룹. 배포 목록 또는 보안 그룹의 에이전트를 통화 대기열 에이전트로 추가 하는 경우 첫 번째 통화가 도착 하는 데 최대 3 시간까지 걸릴 수 있습니다. 새로 만든 메일 그룹 또는 보안 그룹이 통화 큐와 함께 사용할 수 있게 되는 데 최대 48 시간이 걸릴 수 있습니다. 새로 생성 된 Office 365 그룹은 거의 즉시 사용할 수 있습니다.

- 상담원은 통화 대기열 통화를 위해 Microsoft 팀 앱을 사용 하 고 있는 경우에는 TeamsOnly 모드에 있어야 합니다.

![숫자 2의 아이콘으로, 이전 스크린샷](media/teamscallout2.png)
**라우팅 메서드의** 설명선을 참조 하 고, 배포 방법으로 **전화 교환**, **직렬**또는 **라운드 로빈** 중 하나를 선택할 수 있습니다. 모든 새로운 및 기존 통화 대기열에는 기본적으로 수행자 라우팅이 선택 되어 있습니다. 수행자 라우팅이 사용 되는 경우 큐의 첫 번째 호출은 동시에 모든 통화 에이전트를 울립니다. 통화를 선택 하는 첫 번째 호출 에이전트에서 통화를 받습니다.

- **수행자 라우팅은** 큐의 첫 번째 호출로 모든 통화 에이전트를 동시에 연결 합니다. 통화를 선택 하는 첫 번째 호출 에이전트에서 통화를 받습니다.
- **직렬 라우팅** 수신 전화는 통화 에이전트 목록의 시작 부분에서 모든 통화 에이전트를 하나씩 연결 합니다. 콜 에이전트 목록 내에서 에이전트를 주문할 수 없습니다. 에이전트가 전화를 걸거나 받지 못하는 경우 통화는 다음 에이전트로 연결 되며, 모든 에이전트가 선택 되거나 시간 초과 될 때까지 시도 하 게 됩니다.
  > [!NOTE]
  > 직렬 라우팅에서 **오프 라인** 상태 이거나 현재 상태를 **방해**금지로 설정한 에이전트의 경우, 해당 사용자에 게 연결 되 고 에이전트 목록의 다음 에이전트로의 라우팅으로는 사용할 수 없는 사용자에 게 전달 되지 않습니다. 에이전트가 통화 대기열에서 전화 **를 받지 못하는 경우에는** 그렇지 않습니다. 다음 상담원에 게 전화를 거는 시간 간격을 줄이려면 에이전트 알림 시간을 줄일 수 있습니다.
- **라운드 로빈** 각 호출 에이전트가 대기열에서 같은 개수의 호출을 받을 수 있도록 수신 전화의 라우팅을 분산 시킵니다. 이는 모든 통화 에이전트 간에 동일한 기회를 보장 하기 위해 인바운드 영업 환경에서 바람직 할 수 있습니다.

### <a name="select-an-agent-opt-out-option"></a>에이전트 옵트아웃 옵션 선택

![번호 매기기 설명선이 있는 에이전트 옵트아웃 옵션 스크린샷](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![숫자 1의 아이콘, 이전 스크린샷](media/teamscallout1.png)
**에이전트** 의 설명선을 참조 하 여 전화를 받지 못하는 경우,이 옵션을 사용 하 여 통화 대기열 에이전트에서 특정 큐의 통화를 옵트아웃 하도록 선택할 수 있습니다.

이 옵션을 사용 하도록 설정 하면이 큐의 모든 에이전트가 해당 통화 대기열의 통화를 시작 하거나 중지할 수 있습니다. 언제 든 지 에이전트 옵트아웃 (opt out) 권한을 취소할 수 있으며,이 큐에 대 한 에이전트가 자동으로 다시 옵트인 되도록 (모든 에이전트의 기본 설정) 확인란의 선택을 취소 합니다.

옵트아웃 옵션에 액세스 하려면 상담원은 다음을 수행할 수 있습니다.

 1. 바탕 화면 비즈니스용 Skype 클라이언트에서 **옵션** 을 엽니다.
 2. **착신 전환** 탭에서 **온라인 설정 편집** 링크를 클릭 합니다.
 3. 사용자 설정 페이지에서 **통화 대기열**을 클릭 한 다음 큐에서 옵트아웃 (opt out) 확인란의 선택을 취소 합니다.

    > [!NOTE]
    > 비즈니스용 Skype Desktop이 아닌 앱 또는 끝점을 사용 하는 상담원은 사용자 설정 포털 [https://aka.ms/cqsettings](https://aka.ms/cqsettings)의 옵트아웃 옵션에 액세스할 수 있습니다.
    >
    > 에이전트가 Microsoft 팀 데스크톱 클라이언트에 있는 경우에는 통화 설정을 사용 하 여 옵트아웃 (opt out) 할 수 있습니다. 

![숫자 2의 아이콘으로, 이전 스크린샷](media/teamscallout2.png)
**에이전트 알림 설정** 의 설명선을 참조 합니다.

직렬 또는 라운드 로빈 라우팅 방법이 다음 에이전트로 이동 하기 전에 에이전트의 호출을 알리는 기간을 정의 합니다.

기본 설정은 30 초 이지만 최대 3 분까지 설정할 수 있습니다.

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a>통화 오버플로 및 시간 제한 처리 옵션 설정

![숫자 매기기 설명선이 있는 오버플로 처리 옵션 스크린샷](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![숫자 1의 아이콘으로, 이전 스크린샷](media/teamscallout1.png)
의 설명선을 참조 합니다. 대기열의**최대 통화** 는 큐에서 동시에 대기할 수 있는 최대 통화를 설정 하는 데 사용 합니다. 기본값은 50 이지만, 0에서 200 까지의 범위에 있을 수 있습니다. 이 제한에 도달 하면 아래에 **최대 통화 수에 도달할 때** 설정 하는 방법에 따라 통화가 처리 됩니다.

* * *

![숫자 2의 아이콘으로, 호출 대기열이 최대 크기에 도달](media/teamscallout2.png)
하면**최대 호출 수에 도달 하면** 이전 스크린샷의 설명선을 참조 합니다 ( **큐 설정의 최대 통화** 수를 사용 하 여 설정). 새 수신 전화에 대 한 진행 상황을 선택할 수 있습니다.

- **연결 해제** 통화가 끊겼습니다.
- **리디렉션 대상** 이를 선택 하는 경우 다음 중 하나를 선택 합니다.

  - **회사의 사용자** **전화 시스템** 라이선스가 있는 온라인 사용자 이며 엔터프라이즈 음성 또는 통화 요금제를 사용할 수 있습니다. 전화를 음성 메일로 보낼 수 있도록 설정할 수 있습니다. 이렇게 하려면 **회사에서 사용자** 를 선택 하 고이 사용자가 전화를 음성 메일로 바로 착신 전환 하도록 설정 합니다.

  보이스 메일에 필요한 라이선스에 대해 알아보려면 [클라우드 보이스 메일 설정을](set-up-phone-system-voicemail.md)참조 하세요.

  - **음성 응용 프로그램** 이미 생성 된 통화 대기열 또는 자동 전화 교환에 연결 된 리소스 계정의 이름을 선택 합니다.

* * *

![숫자 3의 아이콘, 이전 스크린샷](media/teamscallout3.png)
의 설명선 참조**시간 초과: 최대 대기 시간** 또한 호출이 시간 초과 되기 전에 대기 또는 연결 해제 해야 하는 시간을 결정할 수 있습니다. 리디렉션 위치는 **통화 시간** 설정을 설정 하는 방법을 기준으로 합니다. 0에서 45 분 까지의 시간을 설정할 수 있습니다.

Timeout 값을 초 단위로 15 초 간격으로 설정할 수 있습니다. 이를 통해 호출 흐름을 보다 세밀 하 게 조작할 수 있습니다. 예를 들어 30 초 내에 에이전트가 응답 하지 않는 모든 통화가 디렉터리 검색 자동 전화 교환으로 이동 하도록 지정할 수 있습니다.

![숫자 4의 아이콘, 호출이 **큐 설정에 대기할 수** 있는 시간](media/teamscallout4.png)
에 대해 설정한 제한 시간에 도달 했을 때 전화를**건** 후의 이전 스크린샷에 대 한 설명선을 참조 하는 경우, 통화에 발생 하는 상황을 선택할 수 있습니다.

- **연결 해제** 통화가 끊겼습니다.
- **착신 전환 대상:** 이 옵션을 선택 하면 다음 옵션이 표시 됩니다.
  - **회사의 사용자** **전화 시스템** 라이선스가 있는 온라인 사용자 이며 엔터프라이즈 음성 또는 통화 요금제를 사용할 수 있습니다. 전화를 걸 사람을 음성 메일로 보낼 수 있도록 설정 하려면 **회사에서 사용자** 를 선택 하 고이 사용자가 직접 음성 메일로 착신 전환 하도록 설정 합니다.

  보이스 메일에 필요한 라이선스에 대해 알아보려면 [클라우드 보이스 메일 설정을](set-up-phone-system-voicemail.md)참조 하세요.

  - **음성 앱** 이미 만든 통화 대기열 또는 자동 전화 교환 중 하 나와 연결 된 리소스 계정의 이름을 선택 합니다.

## <a name="change-caller-id-for-outbound-calls"></a>발신 전화의 발신자 ID 변경

호출 에이전트의 id를 보호 하려면 다음 예제와 같이 **새 CsCallingLineIdentity** cmdlet을 사용 하 여 통화 큐, 자동 전화 교환 또는 서비스 번호로의 발신 호출에 대 한 발신자 ID를 변경 합니다.

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

그런 다음 다음 예제와 같이 **CallingLineIdentity** cmdlet을 사용 하 여 사용자에 게 정책을 적용 합니다. 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

자세한 내용은 [조직에서 발신자 ID를 사용 하는 방법](/microsoftteams/how-can-caller-id-be-used-in-your-organization)을 참조 하세요.

## <a name="call-queue-cmdlets"></a>통화 대기열 cmdlet

또한 Windows PowerShell을 사용 하 여 통화 대기열을 만들고 설정할 수 있습니다. 다음은 통화 대기열을 관리 하는 데 사용 하는 cmdlet입니다.

- [새로운 CsCallQueue](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [Set-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [Get-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [제거-CsCallQueue](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a>Windows PowerShell에 대 한 자세한 정보

- Windows PowerShell은 사용자 및 허용 되지 않거나 수행할 수 있는 사용자를 관리 하는 방법에 대해 설명 합니다. Windows PowerShell을 사용 하 여 단일 관리 지점으로 Office 365 및 Microsoft 팀을 관리할 수 있습니다. 여러 작업이 수행 되는 경우 일상 업무를 단순화할 수 있습니다. Windows PowerShell을 시작 하려면 다음 항목을 참조 하세요.

  - [Windows PowerShell 및 Lync Online 소개](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Office 365 PowerShell을 사용 해야 하는 이유](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- Windows PowerShell에는 여러 사용자가 한 번에 변경할 경우 Microsoft 팀 관리 센터에서 속도, 단순성, 생산성에 많은 장점이 있습니다. 다음 항목에서 이러한 이점에 대해 알아보세요.

  - [Windows PowerShell을 사용 하 여 Office 365 관리](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [Windows PowerShell용 컴퓨터 설정](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a>관련 항목

[Office 365에서 전화 시스템을 사용 하 여 얻을 수 있는 기능](here-s-what-you-get-with-phone-system.md)

[서비스 전화 번호 가져오기](getting-service-phone-numbers.md)

[오디오 회의 및 통화 플랜의 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[새로운 CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
