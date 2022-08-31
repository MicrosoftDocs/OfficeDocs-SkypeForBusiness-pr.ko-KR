---
title: Teams에서 모니터링 및 문제 해결을 위한 로그 파일 구성
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teams에서 생성한 디버그, 미디어 및 데스크톱 로그, 찾을 수 있는 위치 및 모니터링 및 문제 해결에 도움이 되는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae6e6eb0c84eae8293f141940842506fa3f54142
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466036"
---
# <a name="configure-log-files-for-monitoring-and-troubleshooting-in-teams"></a>Teams에서 모니터링 및 문제 해결을 위한 로그 파일 구성

클라이언트에서 자동으로 생성되는 세 가지 유형의 로그 파일이 있으며, 이를 활용하여 Teams 모니터링 및 문제 해결을 지원할 수 있습니다.

-   [로그 디버그](#debug-logs)

-   [미디어 로그](#media-logs)

-   [데스크톱 로그](#desktop-logs)

이 문서에서는 이러한 로그 및 로그 사용 방법을 설명합니다. 특정 문제 해결에 대한 자세한 내용은 [Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)을 참조하세요. 

지원에 문의하는 방법에 대한 자세한 내용은 [지원 받기](/microsoft-365/business-video/get-help-support)를 참조하세요.

> [!NOTE]
> 이 문서에서 **디버그 로그** 라는 용어는 문제 해결에 사용되는 로그를 나타냅니다. 그러나 이러한 로그에 대해 생성된 파일에는 이름에 **진단 로그** 라는 용어가 포함됩니다.  

## <a name="logs-overview"></a>로그 개요

문제가 발생하는 즉시 로그를 수집하는 것이 중요합니다.

Microsoft 지원 사용하여 지원 요청을 만들 때 지원 엔지니어는 디버그 로그가 필요합니다. 지원 요청을 만들기 전에 디버그 로그를 사용하면 Microsoft에서 신속하게 문제 해결을 시작할 수 있습니다. **미디어** 또는 **데스크톱** 로그는 Microsoft에서 요청한 경우에만 필요합니다.

디버그, 데스크톱 및 미디어 로그는 _MSTeams 진단 로그 \<local date and time\>_ 라는 이름으로 한 폴더에 수집됩니다. Microsoft 지원 사용하여 지원 요청을 열 때 이 폴더를 압축하고 공유할 수 있습니다. 폴더에는 데스크톱, 모임(미디어) 및 디버그(웹)용 폴더가 포함됩니다. 다음 바로 가기 키를 사용하여 파일을 수집할 수 있습니다.

- Windows: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


특정 모임 또는 라이브 이벤트에 문제가 발생하는 경우 모임과 연결된 URL을 갖는 것이 좋습니다. URL은 로그에서 정확한 모임 또는 라이브 이벤트를 정확히 파악하는 데 도움이 되는 추가 정보를 제공합니다. 이 정보는 모임에 대한 모든 참가자 또는 라이브 이벤트에 대한 발표자 또는 프로듀서로부터 수집할 수 있습니다. 이 URL은 조인 URL을 마우스로 가리키고 **하이퍼링크 복사** 를 선택하여 캡처할 수 있습니다.

> [!NOTE]
> 미디어 로깅을 사용하는 경우 오디오 및 비디오 문제를 조사하는 데 필요한 추가 파일이 모임 폴더에 포함됩니다. 미디어 로깅을 사용하도록 설정하지 않으면 사용 가능한 로그 수가 제한됩니다.
  
다음 표에서는 다양한 클라이언트 및 관련 로그에 대해 간략하게 설명합니다. 로그 파일은 클라이언트 및 운영 체제와 관련된 위치에 저장됩니다.

|클라이언트 |디버그|데스크톱|미디어|
|---------|---------|---------|---------|
|Web    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

지원되는 운영 체제 및 브라우저의 전체 목록은 [Microsoft Teams용 클라이언트 가져오기를 참조하세요](get-clients.md).

## <a name="debug-logs"></a>로그 디버그

디버그 로그는 Windows 및 Mac 데스크톱 클라이언트와 브라우저 기반 클라이언트에서 생성됩니다. 로그는 텍스트 기반이며 상향식에서 읽습니다. 텍스트 기반 편집기를 사용하여 읽을 수 있으며 클라이언트에 로그인할 때 새 로그가 만들어집니다.

디버그 로그에는 다음과 같은 데이터 흐름이 표시됩니다.

-   로그인

-   중간 계층 서비스에 대한 연결 요청

-   통화/대화

Linux에 대한 로그를 수집하려면 다음을 수행합니다.
- 바로 가기 키: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- 파일은 다음에서 사용할 수 있습니다. `~/Downloads`

브라우저 및 Windows에 대한 로그를 수집하려면 다음을 수행합니다.
- 바로 가기 키: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- 파일은 다음에서 사용할 수 있습니다. `%userprofile%\Downloads`

Mac용 로그를 수집하려면 다음을 수행합니다.
- 바로 가기 키: <kbd>옵션</kbd> + <kbd>명령</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>  
- 파일은 다음에서 사용할 수 있습니다. `~/Downloads`

## <a name="media-logs"></a>미디어 로그

미디어 로그에는 Teams 모임의 오디오, 비디오 및 화면 공유에 대한 진단 데이터가 포함됩니다. 통화 관련 문제와 연결된 지원 사례에 필요합니다.

CPU가 다음과 같은 경우 컴퓨터에 대해 미디어 로깅이 기본적으로 설정됩니다.
- Apple M1
- Intel Xeon
- U, G7, M 및 MQ 시리즈를 제외한 모든 Intel i9
- U, G7, M 및 MQ 시리즈를 제외한 6세대 이상 Intel i7

그렇지 않으면 기본적으로 꺼져 있습니다. Teams 모임에 대한 진단 데이터를 기록하는 방법에는 두 가지가 있습니다.

- 관리 구성 - 최종 사용자의 미디어 로그를 관리할 수 있습니다.
- 최종 사용자 구성 - 최종 사용자가 미디어 로그를 켤 수 있습니다.

### <a name="admin-configuration"></a>관리 구성

최종 사용자에 대한 미디어 로그를 관리하면 특히 문제가 간헐적으로 발생하는 경우 원활한 문제 해결 환경을 제공합니다. 관리자는 TeamsMediaLoggingPolicy cmdlet을 사용하여 사용자에 대한 미디어 로깅을 사용하도록 설정하고 관리할 수 있습니다.

PowerShell cmdlet에 대한 [Grant-CsTeamsMediaLoggingPolicy](/powershell/module/teams/grant-csteamsmedialoggingpolicy) 및 자세한 내용을 읽어보세요.

### <a name="end-user-configuration"></a>최종 사용자 구성

최종 사용자가 Teams 모임에 대한 진단 데이터를 기록하려면 Teams 클라이언트에서 옵션을 설정해야 합니다. **설정** > **일반** 으로 이동하여 **미디어 로그 사용(오디오, 비디오 및 화면 공유에 대한 진단 데이터)을 선택합니다. Teams를 다시 시작해야** 합니다.) (Teams를 다시 시작해야 합니다) 확인란, Teams를 다시 시작하고 문제를 재현합니다. 로깅을 시작하려면 Teams 클라이언트를 다시 시작해야 합니다. 사용자는 도크(Mac) 또는 작업 표시줄(Windows)에서 아이콘을 마우스 오른쪽 단추로 클릭하고 종료를 선택하여 다시 시작할 수 있습니다. 종료한 후 앱 아이콘을 클릭하여 Teams를 다시 열 수 있습니다.

> [!NOTE]
> 사용자가 Teams에서 로그아웃하면 미디어 로깅이 기본값으로 다시 설정됩니다.

### <a name="collecting-and-sending-media-logs"></a>미디어 로그 수집 및 보내기

Microsoft 지원에 로그 파일을 보내기 전에 로그 파일의 타임스탬프를 확인하여 문제를 재현할 때 로그가 시간 프레임을 커버하는지 확인합니다.

Linux에 대한 로그를 수집하려면 다음을 수행합니다.  
- 파일은 다음 위치에서 사용할 수 있습니다.
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Windows용 로그를 수집하려면 다음을 수행합니다.  
- 파일은 다음 위치에서 사용할 수 있습니다.
  - `%appdata%\Microsoft\Teams\media-stack\\\*\.blog`
  - `%appdata%\Microsoft\Teams\skylib\\\*\.blog` 

Mac용 로그를 수집하려면 다음을 수행합니다.
- 파일은 다음 위치에서 사용할 수 있습니다.
  - `~/Library/Application Support/Microsoft/Teams/media-stack\\\*\.blog`
  - `~/Library/Application Support/Microsoft/Teams/skylib\\\*\.blog`

생성된 로그 파일의 목록과 여기에 포함된 정보는 다음과 같습니다.

<br/>

|로그 파일 이름  |설명  |
|---------|---------|
|`Teams.msrtc-0-s1039525249.blog`     | 미디어 스택과 관련된 정보를 포함합니다. 여기에는 해상도, 디코더 및 인코더와 같은 채널 상태, 전송 및 수신된 프레임 수, 카메라 및 VBSS(비디오 기반 화면 공유) 세션 상태가 포함됩니다.         |
|`rtmcontrol.msrtc-0-2415069487.blog`      |컨트롤이 제공된 타임스탬프를 비롯한 원격 제어 작업과 관련된 정보 및 마우스 포인터 정보를 기록합니다.          |
|`Teams_MediaStackETW-2-U-xr-U.etl`      |미디어 스택 추적 이벤트를 기록합니다.         |
|`Debug-0-s2790420889.blog`    | 렌더링 품질을 포함하여 미디어 에이전트와 관련된 정보를 포함합니다.          |
|`tscalling-0-2061129496.blog`   |ts 호출 API에 이벤트를 기록합니다.       |

## <a name="desktop-logs"></a>데스크톱 로그

부트스트래퍼 로그라고도 하는 데스크톱 로그에는 데스크톱 클라이언트와 브라우저 간에 발생하는 로그 데이터가 포함됩니다. 미디어 로그와 마찬가지로 이러한 로그는 Microsoft에서 요청한 경우에만 필요합니다. 로그는 텍스트 기반이며 모든 텍스트 기반 편집기를 사용하여 하향식 형식으로 읽을 수 있습니다.

Linux에 대한 로그를 수집하려면 다음을 수행합니다.
- 시스템 트레이에서 Microsoft Teams 아이콘을 클릭하고 **로그 가져오기를** 선택합니다.
- 파일은 .에서 `~/.config/Microsoft/Microsoft Teams/logs.txt`사용할 수 있습니다.

Mac용 로그를 수집하려면 다음을 수행합니다.
- Microsoft Teams에서 도움말 메뉴를 클릭하고 **지원 파일 수집** 을 선택합니다.
- 파일은 `logs.txt` _MSTeams 진단 로그 \<local date and time>_ 폴더 내의 데스크톱 폴더에 있습니다.

Windows용 로그를 수집하려면 다음을 수행합니다.
- 시스템 트레이에서 Microsoft Teams 아이콘을 클릭하고 **지원 파일 수집** 을 선택합니다.
- 파일이 `logs.txt` 메모장에서 자동으로 열립니다.

Teams에 로그인하는 문제를 조사할 때 데스크톱 로그를 수동으로 수집해야 할 수 있습니다. 이러한 로그 파일은 Windows의 %appdata%\Microsoft\Teams에 있습니다.

## <a name="related-topics"></a>관련 항목

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)

[Teams용 브라우저 로그 및 추적](/MicrosoftTeams/browser-logs-and-tracing-for-teams)
