---
title: Microsoft Teams에서 통화 큐 만들기
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System - seo-marvel-apr2020
description: Microsoft Teams 대규모 조직에서 인사말 메시지를 제공하고, 음악을 누르고, 통화 리디렉션 및 기타 기능을 제공하는 통화 큐를 설정하는 방법을 알아봅니다.
ms.openlocfilehash: 4e194a315abecdf779a2df48c7fbb7b6412693cc
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2022
ms.locfileid: "64846547"
---
# <a name="create-a-call-queue"></a>통화 큐 만들기

통화 큐는 특정 문제나 질문에 대한 도움을 줄 수 있는 조직의 사용자에게 통화를 걸 수 있는 방법을 제공합니다. 호출은 큐의 사용자(*에이전트* 라고 함)에게 한 번에 하나씩 배포됩니다. 

> [!TIP]
> 이 문서는 대규모 조직을 위한 것입니다. 조직이 중소기업인 경우 [통화 큐 만들기 - 소규모 비즈니스 자습서](/microsoftteams/business-voice/create-a-phone-system-call-queue-smb) 를 읽어보세요.

통화 큐는 다음을 제공합니다.

- 인사말 메시지

- 큐에서 대기 중인 음악

- 에이전트에 대한 *FIFO(선입선출)* 순서 통화 라우팅.

- 큐 오버플로 및 시간 제한에 대한 처리 옵션

이 문서의 절차를 따르기 전에 [Teams 자동 전화 교환 및 통화 큐에 대한 계획을](plan-auto-attendant-call-queue.md) 읽고 [시작 단계를](plan-auto-attendant-call-queue.md#getting-started) 수행했는지 확인합니다.

**자세한 내용은 아래 [의 통화 큐 기능 호환성](#call-queue-feature-compatibility) 매트릭스를 참조하세요.**

## <a name="video-demonstration"></a>비디오 데모

이 비디오에서는 Teams 통화 큐를 만드는 방법에 대한 기본 예제를 보여줍니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWCF23?autoplay=false]

## <a name="create-the-call-queue"></a>호출 큐 만들기

통화 큐를 설정하려면 Teams 관리 센터에서 **음성** 확장하고 **통화 큐** 클릭한 다음 **추가** 를 클릭합니다.

통화 큐의 이름을 입력합니다.

## <a name="resource-accounts"></a>리소스 계정

![리소스 계정 설정의 스크린샷.](media/call-queue-name-language.png)

**계정 추가** 를 클릭하고 이 통화 큐에 사용할 리소스 계정을 검색하고 **추가** 를 클릭하고 **추가** 를 클릭합니다. (들어오는 전화를 받으면 에이전트에 리소스 계정 이름이 표시됩니다.)

자세한 내용은 [Teams 리소스 계정 관리를 참조하세요](manage-resource-accounts.md).

## <a name="dynamic-caller-id"></a>동적 호출자 ID

![ID 설정 호출 스크린샷](media/call-queue-assign-calling-id.png)

**표준 통화 큐가 있는 Teams 채널/협업 통화 데스크톱 사용자 및 Teams 모바일 클라이언트 사용자에게 사용 가능**

전화 번호가 있는 하나 이상의 리소스 계정을 지정하여 에이전트에 대한 아웃바운드 발신자 ID 번호를 할당할 수 있습니다. 에이전트는 각 아웃바운드 호출에 사용할 아웃바운드 호출자 ID 번호를 선택할 수 있습니다.

**추가** 를 클릭하고, 에이전트가 아웃바운드 호출을 수행할 때 호출자 ID 용도로 사용할 수 있도록 허용할 리소스 계정을 검색하고 **추가** 를 클릭한 다음 **추가** 를 클릭합니다.

**표준 호출 큐**

Teams 데스크톱 사용자 및 표준 통화 큐의 경우 통화 큐의 멤버에 대한 호출자 ID를 호출 큐의 서비스 번호 또는 적절한 자동 전화 교환으로 직접 설정하는 것이 좋습니다. 자세한 내용은 [Microsoft Teams 호출자 ID 정책 관리를 참조](caller-id-policies.md)하세요.

> [!NOTE]
> ID를 호출하는 데 사용되는 리소스 계정에는 Microsoft Teams 전화 시스템 가상 사용자 라이선스와 다음 중 하나가 할당되어 있어야 합니다.
>
> - 통화 플랜 라이선스 및 할당된 전화 번호
> - 할당된 운영자 연결 전화 번호
> - 온라인 음성 라우팅 정책(직접 라우팅을 사용하는 경우 전화 번호 할당은 선택 사항)


## <a name="language"></a>언어

![언어 설정의 스크린샷.](media/call-queue-language.png)

[지원되는 언어](create-a-phone-system-call-queue-languages.md)를 선택합니다. 이 언어는 시스템에서 생성된 음성 프롬프트 및 음성 메시지(사용하도록 설정한 경우)에 사용됩니다.

## <a name="greetings-and-music-on-hold-in-queue"></a>대기 중인 인사말 및 음악

![큐 설정에서 대기 중인 인사말 및 음악의 스크린샷.](media/call-queue-greetings-music.png)

발신자가 큐에 도착하면 발신자들에게 인사말을 재생할지 지정합니다. 재생하려는 인사말이 포함된 MP3, WAV 또는 WMA 파일을 업로드해야 합니다. 업로드된 녹음/녹화의 크기는 5MB 이상일 수 없습니다.

Teams에서 사용자가 큐에 있는 동안 발신자에게 기본 음악이 제공됩니다. Teams 통화 큐에서 제공하는 기본 음악은 조직에서 지불해야 하는 로열티가 없습니다. 특정 오디오 파일을 재생하려면 **오디오 파일 재생** 을 선택하고 MP3 WAV 또는 WMA 파일을 업로드합니다.

> [!NOTE]
> 사용자는 아티스트, 행위자, 행위자를 포함할 수 있는 모든 관련 권리 보유자의 오디오 파일의 음악, 음향 효과, 오디오, 브랜드, 이름 및 기타 콘텐츠에 대한 지적 재산권 및 기타 권리를 포함할 수 있는 Microsoft Teams 서비스에서 음악 또는 오디오 파일을 사용하는 데 필요한 모든 권리와 권한을 독립적으로 지우고 보호해야 합니다.  공연자, 음악가, 작곡가, 음반 레이블, 음악 출판사, 노조, 길드, 권리 사회, 집단 관리 조직 및 음악 저작권, 음향 효과, 오디오 및 기타 지적 재산권을 소유, 제어 또는 허가하는 기타 당사자.

## <a name="call-agents"></a>통화 에이전트

[호출 큐에 에이전트를 추가하기 위한 필수 구성 요소를 검토합니다](plan-auto-attendant-call-queue.md#prerequisites).

![통화 큐에 대한 사용자 및 그룹 설정의 스크린샷.](media/call-queue-users-groups.png)

##### <a name="teams-channel"></a>Teams 채널

Teams 채널을 통해 최대 200명의 에이전트를 추가할 수 있습니다. 큐에 채널을 추가하려면 팀의 구성원이거나 채널의 작성자 또는 소유자여야 합니다.

[Teams 채널을 사용하여 큐를 관리](https://support.microsoft.com/office/9f07dabe-91c6-4a9b-a545-8ffdddd2504e)하려면 **팀 선택** 옵션을 선택하고 **채널 추가를** 클릭합니다. 사용할 팀을 검색하고 선택하고 **추가** 를 클릭합니다. 사용할 채널을 선택하고(표준 채널만 지원됨) **적용** 을 클릭합니다. 

다음 클라이언트는 통화 큐에 Teams 채널을 사용할 때 지원됩니다. 

  - Microsoft Teams Windows 클라이언트
  - Microsoft Teams Mac 클라이언트

> [!NOTE]
> 이 옵션을 사용하는 경우 호출 큐가 완전히 작동하는 데 최대 24시간이 걸릴 수 있습니다.

##### <a name="users-and-groups"></a>사용자 및 그룹

그룹을 통해 최대 20대의 에이전트를 개별적으로, 최대 200명까지 에이전트를 추가할 수 있습니다.

큐에 개별 사용자 또는 그룹을 추가하려면 **사용자 및 그룹 선택** 옵션을 선택합니다. 

큐에 사용자를 추가하려면 **사용자 추가** 를 클릭하고 사용자를 검색한 다음 **추가** 를 클릭하고 **추가** 를 클릭합니다.

큐에 그룹을 추가하려면 **그룹 추가** 를 클릭하고 그룹을 검색한 다음 **추가** 를 클릭하고 **추가** 를 클릭합니다. 메일 그룹, 보안 그룹, Microsoft 365 그룹 또는 Microsoft Teams 팀을 사용할 수 있습니다.

> [!NOTE]
> 그룹에 추가된 새 사용자는 첫 번째 통화가 도착하는 데 최대 8시간이 걸릴 수 있습니다.

## <a name="call-routing"></a>통화 라우팅

![회의 모드 및 라우팅 방법 설정의 스크린샷.](media/call-queue-conference-mode-routing-method.png)

**회의 모드** 를 사용하면 에이전트가 호출을 수락한 후 호출자가 에이전트에 연결되는 데 걸리는 시간이 크게 줄어듭니다. 회의 모드가 작동하려면 통화 큐의 에이전트가 다음 클라이언트 중 하나를 사용해야 합니다.

  - 최신 버전의 Microsoft Teams 데스크톱 클라이언트, Android 앱 또는 iOS 앱
  - Microsoft Teams 전화 버전 1449/1.0.94.2020051601 이상
  
에이전트의 Teams 계정은 Teams 전용 모드로 설정해야 합니다. 요구 사항을 충족하지 않는 에이전트는 통화 라우팅 목록에 포함되지 않습니다. 에이전트가 모두 호환되는 클라이언트를 사용하고 있는 경우 통화 큐에 통화 회의 모드를 설정하는 것이 좋습니다.

> [!NOTE]
> 전화 통화가 위치 기반 라우팅에 사용하도록 설정된 직접 라우팅 게이트웨이에서 큐로 라우팅되는 경우 회의 모드가 지원되지 않습니다.

> [!TIP]
> **전화 회의 모드** 를 **켜** 기로 설정하는 것이 좋습니다.

**라우팅 방법** 은 에이전트가 큐에서 통화를 받는 순서를 결정합니다. 다음 옵션 중에서 선택합니다.

- **참석자 라우팅** 은 큐에 있는 모든 에이전트를 동시에 링합니다. 통화를 받은 첫 번째 통화 에이전트가 통화를 받습니다.

- **직렬 라우팅** 은 모든 **콜 에이전트** 를 콜 에이전트 목록에 지정된 순서대로 하나씩 울립니다. 에이전트가 통화를 해제하거나 받지 않으면 호출이 다음 에이전트에 울림됩니다. 이 작업은 호출이 선택되거나 시간이 초과될 때까지 반복됩니다.

- **라운드 로빈** 은 각 호출 에이전트가 큐에서 동일한 수의 호출을 수신하도록 수신 호출 라우팅의 균형을 조정합니다. 이 라우팅 방법은 모든 호출 에이전트 간에 동일한 기회를 보장하기 위해 인바운드 판매 환경에서 바람직할 수 있습니다.

- **가장 긴 유휴 상태** 는 각 통화를 가장 오랫동안 유휴 상태인 에이전트로 라우팅합니다. 에이전트의 현재 상태가 사용 가능한 경우 유휴 상태로 간주됩니다. 현재 상태를 사용할 수 없는 에이전트는 현재 상태를 사용 가능으로 변경할 때까지 전화를 받을 수 없습니다. 

> [!TIP]
> **라우팅 메서드를** **라운드 로빈** 또는 **가장 긴 유휴** 상태로 설정하는 것이 좋습니다.

> [!NOTE]
> 에이전트에서 [규정 준수 기록을](teams-recording-policy.md) 사용하도록 설정하면 **회의 모드** 와 **전화 교환 라우팅** 의 조합이 지원되지 않습니다. **회의 모드** 를 사용해야 하는 경우 라우팅 **방법으로** **직렬 라우팅**, **라운드 로빈** 또는 **가장 긴 유휴** 를 선택합니다. **전화 교환 라우팅을** 사용해야 하는 경우 **전화 회의 모드** 를 **해제** 로 설정합니다.
> 
> **가장 긴 유휴 상태** 이고 사용 가능한 에이전트보다 큐에 호출이 적은 경우 처음 두 개의 가장 긴 유휴 에이전트만 큐의 호출과 함께 표시됩니다.
> 
> **가장 긴 유휴를** 사용하는 경우 에이전트가 사용할 수 없게 된 직후 큐에서 전화를 받거나 사용할 수 있게 된 후 큐에서 전화를 받는 데 짧은 지연이 있을 수 있습니다.
> 
> 에이전트에 대한 통화 큐 호출 프레젠테이션이 위치 기반 라우팅 제한과 충돌할 수 있습니다. 이 경우 에이전트는 통화 알림을 받지만 통화에 응답할 수 없습니다. 이 조건은 다른 에이전트가 통화에 응답할 수 있거나, 호출자가 중단되거나, 통화 큐 시간 제한 조건이 발생할 때까지 계속됩니다.  


![라우팅, 옵트아웃 및 경고 시간 설정의 스크린샷.](media/call-queue-presence-agents-time.png)

**현재 상태 기반 라우팅** 은 통화 에이전트의 가용성 상태를 사용하여 선택한 라우팅 방법에 대한 통화 라우팅 목록에 에이전트를 포함할지 여부를 결정합니다. 가용성 상태가 **사용 가능** 으로 설정된 통화 에이전트는 통화 라우팅 목록에 포함되며 호출을 수신할 수 있습니다. 가용성 상태가 다른 상태로 설정된 에이전트는 통화 라우팅 목록에서 제외되며, 가용성 상태가 다시 **사용 가능** 으로 변경될 때까지 호출을 수신하지 않습니다. 

라우팅 방법을 사용하여 현재 상태 기반 통화 라우팅을 사용하도록 설정할 수 있습니다.

에이전트가 통화를 옵트아웃하면 해당 에이전트가 수신 가능 여부가 설정된 상태와 관계없이 통화 라우팅 목록에 포함되지 않습니다. 

> [!NOTE]
> **가장 긴 유휴** 상태를 라우팅 방법으로 선택하면 현재 상태 기반 라우팅 토글이 **꺼** 지고 회색으로 표시되더라도 현재 상태 기반 라우팅이 필요하고 자동으로 사용하도록 설정됩니다.
>
> 현재 상태 기반 라우팅이 사용하도록 설정되어 있지 않은 경우 큐에 여러 통화가 있는 경우 시스템에서 현재 상태와 상관없이 이러한 통화를 에이전트에게 동시에 제공합니다. 이렇게 하면 에이전트에게 여러 통화 알림이 전송됩니다. 특히 일부 에이전트가 최초 통화에 응답하지 않는 경우가 있습니다.
>
> **현재 상태 기반 라우팅을** 사용하는 경우 에이전트가 사용할 수 없게 된 직후 큐에서 전화를 받거나 사용할 수 있게 된 후 큐에서 전화를 받는 데 잠시 지연될 수 있습니다.
> 
> 현재 상태 기반 라우팅이 사용하도록 설정된 경우 비즈니스용 Skype 클라이언트를 사용하는 에이전트가 통화 라우팅 목록에 포함되지 않습니다. 비즈니스용 Skype를 사용하는 에이전트가 있는 경우 현재 상태 기반 통화 라우팅을 사용하지 않습니다.

> [!TIP]
> **현재 상태 기반 라우팅을** **On** 으로 설정하는 것이 좋습니다.

**에이전트 알림 시간** 은 큐가 다음 에이전트로 통화를 리디렉션하기 전에 에이전트의 통화가 울리는 시간을 지정합니다.

> [!TIP]
> **에이전트 경고 시간을** **20초** 로 설정하는 것이 좋습니다.

## <a name="call-overflow-handling"></a>통화 오버플로 처리

![호출 오버플로 설정의 스크린샷.](media/call-queue-overflow-handling.png)

**큐 최대 호출 수** 는 지정된 시간에 큐에 대기할 수 있는 최대 통화 수를 지정합니다. 기본값은 50이지만 0에서 200까지의 범위일 수 있습니다. 이 제한에 도달하면 **최대 통화 수에 도달할 때** 설정에 지정된 대로 통화가 처리됩니다.

통화 연결을 끊거나 통화 라우팅 대상로 리디렉션할 수 있습니다. 예를 들어 발신자에 큐에 있는 에이전트에 대한 음성 메일이 남아 있을 수 있습니다. 외부 전송의 경우 [필수 구성 요소](plan-auto-attendant-call-queue.md#prerequisites) 및 [외부 전화 번호 전송을 참조하세요.](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 번호 서식에 대한 기술 세부 정보입니다.

> [!NOTE]
> 최대 통화 수가 0으로 설정된 경우 인사말 메시지는 재생되지 않습니다.

## <a name="call-timeout-handling"></a>통화 시간 제한 처리

![통화 시간 제한 설정의 스크린샷.](media/call-queue-timeout-handling.png)

**통화 시간 초과: 최대 대기 시간** 은 통화가 리디렉션되거나 연결이 끊어지기 전에 큐에 대기할 수 있는 최대 시간을 지정합니다. 0초에서 45분까지 지정할 수 있습니다.

통화 연결을 끊거나 통화 라우팅 대상로 리디렉션할 수 있습니다. 예를 들어 발신자에 큐에 있는 에이전트에 대한 음성 메일이 남아 있을 수 있습니다. 외부 전송의 경우 [필수 구성 요소](plan-auto-attendant-call-queue.md#prerequisites) 및 [외부 전화 번호 전송을 참조하세요.](create-a-phone-system-auto-attendant.md#external-phone-number-transfers---technical-details) 번호 서식에 대한 기술 세부 정보입니다.

통화 시간 제한 옵션을 선택한 경우 **저장** 을 클릭합니다.

## <a name="summary-of-recommended-call-queue-settings"></a>권장 통화 큐 설정 요약

다음 설정은 권장되는 항목입니다.

- **전화 회의 모드** 에서 **켜** 기
- **라우팅 방법** 은 **라운드 로빈** 또는 **최대 유휴 상태** 로
- **현재 상태 기반 라우팅** 은 **켬** 으로
- **에이전트 경고 시간** 은 **20초로**


## <a name="call-queue-feature-compatibility"></a>통화 큐 기능 호환성

|기능                          |Teams <sup>Desktop1</sup> |Teams <sup>Mobile2</sup> |Lync |IP 휴대폰 | 표준 호출 큐 |채널 기반 통화 큐 | 코멘트 |
|:--------------------------------|:------------------------:|:-----------------------:|:---:|:--------:|:--------------------:|:------------------------:|:-------------|
|**에이전트 라우팅 메서드**        |                          |                         |     |          |                      |                          |              |
|`Attendant Routing`              |Y                         |Y                        |Y    |Y         |Y                     |Y                         |*기본*     |
|`Longest Idle`<sup>3</sup>       |Y                         |Y                        |N    |Y         |Y                     |Y                         |*권장* |
|`Round Robin`                    |Y                         |Y                        |Y    |Y         |Y                     |Y                         |*권장* |
|`Serial`                         |Y                         |Y                        |Y    |Y         |Y4<sup></sup>         |Y4<sup></sup>             |              |
|**전송 모드**               |                          |                         |     |          |                      |                          |              |
|`Conference Mode`<sup>5</sup>    |Y                         |Y                        |N    |Y6<sup></sup>|Y                  |Y                         |*권장* |
|`Transfer Mode`                  |Y                         |Y                        |Y    |Y         |Y                     |Y                         |              |
|현재 상태 기반 라우팅<sup>3</sup>|Y                        |Y                        |N    |Y         |Y                     |Y                         |*권장* |
|에이전트는 옵트아웃할 수 있습니다.               |Y                         |Y                        |Y7<sup></sup>|Y7<sup></sup>|Y          |Y                         |*기본*     |
|채널 기반 큐             |Y                         |N                        |N    |N         |n/a                   |Y8<sup></sup>             |              |
|통화 알림에 리소스 계정 이름이 표시됩니다. |Y9<sup></sup>       |Y                        |Y    |          |Y                     |Y                         |              |
|**동적 호출자 ID**            |                          |                         |     |          |                      |                          |              |
|`Standard call queue`            |N                         |Y                        |N    |N         |Y                     |n/a                       |              |
|`Channel based call queue`       |Y                         |n/a                      |n/a  |n/a       |n/a                   |Y                         |              |
|**PSTN 연결 방법**    |                          |                         |     |          |                      |                          |참고 10 참조   |
|`Calling Plans`                  |Y                         |Y                        |Y    |Y         |Y                     |Y                         |              |
|`Direct Routing`                 |Y                         |Y                        |N    |N         |Y                     |Y                         |              |
|`Operator Connect`               |Y                         |Y                        |     |          |Y                     |Y                         |              |

참고:
1. Microsoft Teams Windows 클라이언트, Microsoft Teams Mac 클라이언트, 가상화된 데스크톱 인프라, Microsoft Teams 웹 클라이언트에서 Microsoft Teams.
2. Microsoft Teams iPhone 앱, Microsoft Teams Android 앱
3. 에이전트 라우팅 방법에 대해 가장 긴 유휴 상태를 선택하면 프레즌스 기반 라우팅이 자동으로 활성화됩니다.
4. 표준 통화 큐의 일부로 개별 사용자를 추가할 때만 주문을 설정할 수 있습니다. 배포 목록 또는 Teams 채널이 사용되는 경우 순서는 사전순입니다.
5. 전화 통화가 위치 기반 라우팅에 사용하도록 설정된 직접 라우팅 게이트웨이에서 큐로 라우팅되는 경우 회의 모드가 지원되지 않습니다.
6. 휴대폰만 Microsoft Teams.
7. 에서 사용자 설정 포털 페이지를 통해https://aka.ms/vmsettings
8. 공용 채널만 지원됩니다.
9. Teams 웹 클라이언트 제외.
10. 자동 전화 교환 및 통화 큐는 PSTN 연결 방법 간에 호출을 전송할 수 없습니다.


## <a name="supported-clients"></a>지원되는 클라이언트

다음 클라이언트는 통화 큐의 통화 에이전트에 대해 지원됩니다.

  - 비즈니스용 Skype 데스크톱 클라이언트 2016(32비트 및 64비트 버전)
  - Lync 데스크톱 클라이언트 2013(32비트 및 64비트 버전)
  - 모든 IP 통화 모델은 Microsoft Teams에서 지원됩니다. [비즈니스용 Skype Online 휴대폰 받기](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)를 참조하세요.
  - Mac용 비즈니스용 Skype(버전 16.8.196 이상)
  - Android 비즈니스용 Skype® 클라이언트(버전 6.16.0.9 이상)
  - iPhone용 비즈니스용 Skype® 클라이언트(버전 6.16.0 이상)
  - iPad용 비즈니스용 Skype® 클라이언트(버전 6.16.0 이상)
  - Microsoft Teams Windows 클라이언트(32비트 및 64비트 버전)
  - Microsoft Teams Mac 클라이언트
  - [가상화된 데스크톱 인프라](/microsoftteams/teams-for-vdi)의 Microsoft Teams(Windows Virtual Desktop, Citrix 및 VMware)
  - Microsoft Teams iPhone 앱
  - Microsoft Teams Android 앱

    > [!NOTE]
    > 직접 라우팅 번호가 할당된 통화 큐는 비즈니스용 Skype 클라이언트, Lync 클라이언트 또는 비즈니스용 Skype IP 통화가 에이전트로 지원되지 않습니다. Teams 클라이언트는 [Teams 전용의 공존 모드](/microsoftteams/setting-your-coexistence-and-upgrade-settings)에서만 지원됩니다.

## <a name="call-queue-cmdlets"></a>통화 큐 cmdlets

Windows PowerShell 배치 또는 프로그래밍 방식으로 명령줄을 통해 호출 큐를 만들고 관리할 수 있습니다.

다음 cmdlet을 사용하면 통화 큐를 관리할 수 있습니다.

- [New-CsCallQueue](/powershell/module/skype/New-CsCallQueue)
- [Get-CsCallQueue](/powershell/module/skype/Get-CsCallQueue)
- [Set-CsCallQueue](/powershell/module/skype/Set-CsCallQueue)
- [Remove-CsCallQueue](/powershell/module/skype/Remove-CsCallQueue)

또한 통화 큐에 사용할 사용자, 리소스 계정, Microsoft Teams 전화 라이선스, 전화 번호, 오디오 파일 및 지원되는 언어를 관리하려면 다음과 같은 추가 cmdlet이 필요합니다.

사용자/Teams

- 사용자
- - [Get-CsOnlineUser](/powershell/module/skype/Get-CsOnlineUser)

- Teams: 
- - [Get-Team](/powershell/module/teams/Get-Team)
- - [Get-TeamChannel](/powershell/module/teams/Get-TeamChannel)

리소스 계정:

- [New-CsOnlineApplicationInstance](/powershell/module/skype/New-CsOnlineApplicationInstance)
- [Find-CsOnlineApplicationInstance](/powershell/module/skype/Find-CsOnlineApplicationInstance)
- [Get-CsOnlineApplicationInstance](/powershell/module/skype/Get-CsOnlineApplicationInstance)
- [Set-CsOnlineApplicationInstance](/powershell/module/skype/Set-CsOnlineApplicationInstance)
- [New-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/New-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociation)
- [Remove-CsOnlineApplicationInstanceAssociation](/powershell/module/skype/Remove-CsOnlineApplicationInstanceAssociation)
- [Get-CsOnlineApplicationInstanceAssociationStatus](/powershell/module/skype/Get-CsOnlineApplicationInstanceAssociationStatus)

가상 Teams 전화 라이선스:

- [Get-MsolAccountSku](/powershell/module/msonline/get-msolaccountsku)
- [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense)

전화 번호 할당:

- [Get-CsOnlineTelephoneNumber](/powershell/module/skype/Get-CsOnlineTelephoneNumber)
- [Set-CsPhoneNumberAssignment](/powershell/module/teams/Set-csphonenumberassignment)

오디오 파일

- [Get-CsOnlineAudioFile](/powershell/module/skype/Get-CsOnlineAudioFile)
- [Import-CsOnlineAudioFile](/powershell/module/skype/Import-CsOnlineAudioFile)
- [Export-CsOnlineAudioFile](/powershell/module/skype/Export-CsOnlineAudioFile)
- [Remove-CsOnlineAudioFile](/powershell/module/skype/Remove-CsOnlineAudioFile)

지원 언어 목록

- [Get-CsAutoAttendantSupportedLanguage](/powershell/module/skype/Get-CsAutoAttendantSupportedLanguage)

PowerShell을 사용하여 통화 큐를 만드는 단계별 가이드는 [PowerShell cmdlet을 사용하여 통화 큐 만들기를 참조하세요.](create-a-phone-system-call-queue-via-cmdlets.md)

## <a name="call-queue-diagnostic-tool"></a>통화 큐 진단 도구

관리자인 경우 다음 진단 도구를 사용하여 통화 큐가 전화를 받을 수 있는지 확인할 수 있습니다.

1. 아래의 **테스트 실행** 을 선택하면 Microsoft 365 관리 센터에서 진단이 채워집니다. 

   > [!div class="nextstepaction"]
   > [테스트 실행: Teams 통화 큐](https://aka.ms/TeamsCallQueueDiag)

2. 진단 실행 창의 **사용자 이름 또는 전자 메일** 필드에 리소스 계정을 입력한 다음 **테스트 실행을** 선택합니다.

3. 테스트는 모든 테넌트, 정책 및 리소스 계정 구성을 처리하는 최상의 다음 단계를 반환하여 호출 큐가 호출을 받을 수 있는지 확인합니다.

## <a name="related-topics"></a>관련 항목

[Microsoft Teams 전화](here-s-what-you-get-with-phone-system.md)

[서비스 통화 번호 가져오기](getting-service-phone-numbers.md)

[오디오 회의 및 통화 요금제 국가 및 지역 가용성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
