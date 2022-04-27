---
title: 문제 해결 Microsoft Teams 로그 파일 사용
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
description: Microsoft Teams 생성된 디버그, 미디어 및 데스크톱 로그, 찾을 수 있는 위치 및 모니터링 및 문제 해결에 도움이 되는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d8e3ab079498ecfca11a7d2ba48736aaf457329
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059109"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>로그 파일을 사용하여 Microsoft Teams 모니터링 및 문제 해결

클라이언트에서 자동으로 생성되는 세 가지 유형의 로그 파일이 있으며, 이를 활용하여 Teams 모니터링 및 문제 해결을 지원할 수 있습니다.

-   [로그 디버그](#debug-logs)

-   [미디어 로그](#media-logs)

-   [데스크톱 로그](#desktop-logs)

이 문서에서는 이러한 로그 및 로그 사용 방법을 설명합니다. 특정 문제 해결에 대한 자세한 내용은 [Teams 문제 해결을 참조하세요](/MicrosoftTeams/troubleshoot/teams). 지원에 문의하는 방법에 대한 자세한 내용은 [지원 받기](/microsoft-365/business-video/get-help-support)를 참조하세요. Microsoft 지원 사용하여 지원 요청을 만들 때 지원 엔지니어는 디버그 로그가 필요합니다. 지원 요청을 만들기 전에 디버그 로그를 사용하면 Microsoft에서 신속하게 문제 해결을 시작할 수 있습니다. **미디어** 또는 **데스크톱** 로그는 Microsoft에서 요청한 경우에만 필요합니다.

> [!NOTE]
> 이 문서에서 **디버그 로그** 라는 용어는 문제 해결에 사용되는 로그를 나타냅니다. 그러나 이러한 로그에 대해 생성된 파일에는 이름에 **진단 로그** 라는 용어가 포함됩니다.  

## <a name="collect-and-enable-logging"></a>로깅 수집 및 사용

문제가 발생하는 즉시 로그를 수집하는 것이 중요합니다. 로그는 몇 번의 클릭만으로 함께 수집할 수 있습니다.

- Windows: 시스템 트레이에서 Teams 아이콘을 마우스 오른쪽 단추로 클릭하고 **지원 파일 수집** 을 선택합니다. 

- Mac: 도움말 메뉴를 선택하고 **지원 파일 수집** 을 선택합니다.

디버그, 데스크톱 및 미디어 로그는 _MSTeams 진단 로그 \<local date and time\>_ 라는 이름으로 한 폴더에 수집됩니다. Microsoft 지원 사용하여 지원 요청을 열 때 이 폴더를 압축하고 공유할 수 있습니다. 폴더에는 데스크톱, 모임(미디어) 및 디버그(웹)용 폴더가 포함됩니다. 다음 바로 가기 키를 사용하여 파일을 수집할 수 있습니다.

- Windows: <kbd>Ctrl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>

- Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


미디어 로깅은 [미디어 로그](#media-logs)에 설명된 일부 CPU에 대해서만 기본적으로 설정됩니다. 그렇지 않으면 기본적으로 꺼져 있습니다. 미디어 로깅을 사용하려면 사용자가 Teams 클라이언트에서 옵션을 켜야 합니다. **설정** > **제너럴** 로 이동하고 **모임 진단에 대한 로깅 사용(Teams 다시 시작 필요)을** 선택합니다. 로깅을 시작하려면 Teams 클라이언트를 다시 시작해야 합니다(도크(Mac) 또는 작업 표시줄(Windows)에서 아이콘을 마우스 오른쪽 단추로 클릭하고 **종료** 를 선택하여 다시 시작해야 합니다. 종료한 후 앱 아이콘을 클릭하여 다시 엽니다.)

특정 모임 또는 라이브 이벤트에 문제가 발생하는 경우 모임과 연결된 URL을 갖는 것이 좋습니다. 로그에서 정확한 모임 또는 라이브 이벤트를 정확히 파악하는 데 도움이 되는 추가 정보를 제공합니다. 이 정보는 모임에 대한 모든 참가자 또는 라이브 이벤트에 대한 발표자 또는 프로듀서로부터 수집할 수 있습니다. 이 URL은 조인 URL을 마우스로 가리키고 **하이퍼링크 복사** 를 선택하여 캡처할 수 있습니다.

> [!NOTE]
> 미디어 로깅을 사용하는 경우 오디오 및 비디오 문제를 조사하는 데 필요한 추가 파일이 모임 폴더에 포함됩니다. 미디어 로깅을 사용하도록 설정하지 않으면 사용 가능한 로그 수가 제한됩니다.
  
> [!NOTE]
> 디버그 로그는 이전에 아래 바로 가기 키를 사용하여 수집했습니다. 이러한 기능은 여전히 작동하며 **지원 파일 수집** 옵션과 동일한 로그 캡처를 완료합니다.
>
> - Windows: <kbd>Crtl</kbd> + <kbd>Alt</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>
>
> - Mac: <kbd>Option</kbd> + <kbd>Command</kbd> + <kbd>Shift</kbd> + <kbd>1</kbd>


다음 표에서는 다양한 클라이언트 및 관련 로그에 대해 간략하게 설명합니다. 로그 파일은 클라이언트 및 운영 체제와 관련된 위치에 저장됩니다.


|클라이언트 |디버그|데스크톱|미디어|
|---------|---------|---------|---------|
|웹    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

지원되는 운영 체제 및 브라우저의 전체 목록은 [Microsoft Teams 클라이언트 가져오기를 참조하세요](get-clients.md).

## <a name="debug-logs"></a>로그 디버그

Windows 및 Mac 지침에 대한 _로깅 수집 및 사용_ 섹션을 참조하세요. 디버그 로그는 브라우저 기반 클라이언트뿐만 아니라 Windows 및 Mac 데스크톱 클라이언트에서 생성됩니다. 로그는 텍스트 기반이며 상향식에서 읽습니다. 텍스트 기반 편집기를 사용하여 읽을 수 있으며 클라이언트에 로그인할 때 새 로그가 만들어집니다.

디버그 로그에는 다음과 같은 데이터 흐름이 표시됩니다.

-   로그인

-   중간 계층 서비스에 대한 연결 요청

-   통화/대화

Linux에 대한 로그를 수집하려면 다음을 수행합니다.
- 바로 가기 키: <kbd>CtrlAltShift1</kbd> + <kbd></kbd> + <kbd></kbd> + <kbd></kbd>  
- 파일은 다음에서 사용할 수 있습니다. `~/Downloads`

브라우저 및 Windows 대한 로그를 수집하려면 다음을 수행합니다.
- 바로 가기 키: <kbd>CtrlAltShift1</kbd> + <kbd></kbd> + <kbd></kbd> + <kbd></kbd>  
- 파일은 다음에서 사용할 수 있습니다. `%userprofile%\Downloads`

## <a name="media-logs"></a>미디어 로그

Windows 및 Mac 지침에 대한 _로깅 수집 및 사용_ 섹션을 참조하세요. 미디어 로그에는 Teams 모임의 오디오, 비디오 및 화면 공유에 대한 진단 데이터가 포함됩니다. 통화 관련 문제와 연결된 지원 사례에 필요합니다.

CPU가 다음과 같은 경우 컴퓨터에 대해 미디어 로깅이 기본적으로 설정됩니다.
- Apple M1
- Intel Xeon
- U, G7, M 및 MQ 시리즈를 제외한 모든 Intel i9
- U, G7, M 및 MQ 시리즈를 제외한 6세대 이상 Intel i7

그렇지 않으면 기본적으로 꺼져 있습니다. Teams 모임에 대한 진단 데이터를 기록하려면 사용자가 Teams 클라이언트에서 옵션을 켜야 합니다. **설정** > **제너럴** 로 이동하여 **모임 진단에 대한 로깅 사용(Teams 다시 시작 필요**) 확인란을 선택하고, Teams 다시 시작하고, 문제를 재현합니다. 

> [!NOTE]
> Teams 로그아웃하면 미디어 로깅이 기본값으로 다시 설정됩니다. 

Microsoft 지원에 로그 파일을 보낼 때 로그 파일의 타임스탬프를 확인하여 문제를 재현할 때 로그가 시간 프레임을 커버하는지 확인하세요.

Linux에 대한 로그를 수집하려면 다음을 수행합니다.  
- 파일은 다음 위치에서 사용할 수 있습니다.
  - `~/.config/Microsoft/Microsoft Teams/media-stack/\*\.blog`
  - `~/.config/Microsoft/Microsoft Teams/skylib/\*\.blog`

Windows 대한 로그를 수집하려면 다음을 수행합니다.  
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

Windows 및 Mac 지침에 대한 _로깅 수집 및 사용_ 섹션을 참조하세요. 부트스트래퍼 로그라고도 하는 데스크톱 로그에는 데스크톱 클라이언트와 브라우저 간에 발생하는 로그 데이터가 포함됩니다. 미디어 로그와 마찬가지로 이러한 로그는 Microsoft에서 요청한 경우에만 필요합니다. 로그는 텍스트 기반이며 모든 텍스트 기반 편집기를 사용하여 하향식 형식으로 읽을 수 있습니다.

Linux에 대한 로그를 수집하려면 다음을 수행합니다.
- 시스템 트레이에서 Microsoft Teams 아이콘을 클릭하고 **로그 가져오기를** 선택합니다.
- 파일은 .에서 `~/.config/Microsoft/Microsoft Teams/logs.txt`사용할 수 있습니다.
  
Windows 대한 로그를 수집하려면 다음을 수행합니다.
- 시스템 트레이에서 Microsoft Teams 아이콘을 클릭하고 **지원 파일 수집** 을 선택합니다.
- `logs.txt` 파일이 자동으로 메모장 열립니다.

Teams 로그인하는 문제를 조사할 때 데스크톱 로그를 수동으로 수집해야 할 수 있습니다. 이러한 로그 파일은 Windows %appdata%\Microsoft\Teams 있습니다.

## <a name="browser-trace"></a>브라우저 추적

일부 오류 범주의 경우 Microsoft 지원 브라우저 추적을 수집해야 할 수 있습니다. 이 정보는 오류가 발생할 때 Teams 클라이언트의 상태에 대한 중요한 세부 정보를 제공할 수 있습니다.

브라우저 추적을 시작하기 전에 Teams 로그인했는지 확인합니다. 추적에 중요한 로그인 정보가 포함되지 않도록 추적을 시작하기 전에 이 작업을 수행하는 것이 중요합니다.

로그인한 후 브라우저에 적합한 다음 링크 중 하나를 선택하고 제공된 단계를 따릅니다. 

-   [Chrome & Edge(Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [가장자리](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [사파리](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [파이어 폭스](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> 이 단계에서는 Azure Portal 대한 모든 참조를 Teams 클라이언트로 바꿉니다.
  
## <a name="webrtc-logs-in-browsers"></a>브라우저의 WebRTC 로그
WebRTC 로그는 오디오 및 비디오 통화에 대한 연결 세부 정보를 제공하여 Microsoft 지원 지원할 수 있습니다. Edge(Chromium) 또는 Chrome에서 WebRTC 로그에 액세스하려면 다음 단계를 수행합니다. 
  
1.  새 탭을 열고 다음 URL 중 하나로 이동합니다.
    -   Edge(Chromium):`edge://webrtc-internals/`
    -   크롬: `chrome://webrtc-internals/`
  
2.  Teams 웹 애플리케이션을 열고 문제를 재현합니다.
  
3.  1단계에서 액세스한 탭으로 돌아가기 두 개 이상의 탭이 표시됩니다.
    -   GetUserMedia 요청
    -   `https://teams.microsoft.com/url`

4.  Teams 애플리케이션의 이름이 있는 탭을 선택하고 페이지 콘텐츠를 저장합니다.

## <a name="related-topics"></a>관련 항목

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
