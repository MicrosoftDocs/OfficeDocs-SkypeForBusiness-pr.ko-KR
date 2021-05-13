---
title: 로그 파일을 사용하여 문제 해결 Microsoft Teams
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
description: 디버그, 미디어 및 데스크톱 로그를 Microsoft Teams 찾을 수 있는 위치 및 모니터링 및 문제 해결에 도움이 되는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337745"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a>로그 파일을 사용하여 로그 파일을 모니터링하고 문제를 Microsoft Teams

클라이언트에서 자동으로 생성되는 세 가지 유형의 로그 파일이 있습니다. 이러한 로그 파일을 모니터링 및 문제 해결을 지원하기 위해 활용할 수 Teams.

-   [로그 디버그](#debug-logs)

-   [미디어 로그](#media-logs)

-   [데스크톱 로그](#desktop-logs)

이 문서에서는 세 개의 로그와 이 로그가 사용되는 방법을 설명합니다. 

특정 문제 해결에 대한 자세한 내용은 문제 [해결 Teams 참조하세요.](/MicrosoftTeams/troubleshoot/teams) 지원에 문의하는 방법에 대한 자세한 내용은 지원 을 [참조하세요.](/microsoft-365/business-video/get-help-support)

Microsoft Support를 사용하여 지원 요청을 만들 때 지원 엔지니어는 디버그 로그를 요구합니다. 지원 요청을 만들기 전에 디버그 로그를 진행하면 Microsoft에서 문제 해결을 신속하게 시작할 수 있습니다. **미디어** 또는 **데스크톱** 로그는 Microsoft에서 요청한 경우만 필요합니다.

> [!NOTE]
> 이 문서에서 **디버그** 로그는 문제 해결에 사용되는 로그를 참조합니다. 그러나 이러한 로그에 대해 생성된 파일에는 이름에 진단 **로그이라는** 용어가 포함되어 있습니다.  

다음 표에서는 다양한 클라이언트 및 해당 관련 로그를 간략하게 설명합니다. 로그 파일은 클라이언트 및 운영 체제에 특정 위치에 저장됩니다.


|클라이언트 |디버그|데스크톱|미디어|
|---------|---------|---------|---------|
|웹    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

지원되는 운영 체제 및 브라우저의 전체 목록은 에 대한 클라이언트 [Microsoft Teams.](get-clients.md)

## <a name="debug-logs"></a>로그 디버그

이러한 로그는 가장 일반적인 로그로 모든 Microsoft 지원 사례에 필요합니다. 디버그 로그는 브라우저 기반 Windows 및 Mac 데스크톱 클라이언트에서 생성됩니다. 로그는 텍스트 기반이 며 아래쪽에서 읽습니다. 텍스트 기반 편집기를 사용하여 읽을 수 있으며, 클라이언트에 로그인할 때 새 로그가 만들어집니다.

디버그 로그에는 다음 데이터 흐름이 표시됩니다.

-   로그인

-   중간 계층 서비스에 대한 연결 요청

-   통화/대화

디버그 로그는 다음 OS별 메서드를 사용하여 생성됩니다.

-   Windows:

      바로 가기 키: Ctrl + Alt + Shift + 1

-   Mac OSX:

      바로 가기 키: 옵션 + 명령 + Shift+1

-   Linux:

      바로 가기 키: Ctrl + Alt + Shift + 1

디버그 로그는 다음 폴더에 자동으로 다운로드됩니다.

-   Windows: %userprofile% \\ 다운로드

-   Mac OSX: ~/Downloads

-   Linux: ~/Downloads

-   브라우저: 디버그 로그를 기본 저장 위치로 저장하라는 메시지가 표시됩니다.

## <a name="media-logs"></a>미디어 로그

미디어 로그에는 오디오, 비디오 및 화면 공유에 대한 진단 데이터가 Teams 있습니다. 호출 관련 문제에 연결된 지원 사례에 필요합니다.

미디어 로깅이 기본적으로 해제됩니다. 모임에 대한 진단 데이터를 Teams 클라이언트에서 옵션을 설정해야 Teams 합니다. 일반 **설정** 으로 이동하여 모임 진단에 로깅 사용(Teams 다시 시작 필요) 확인란을 선택하고, Teams 다시 시작하고  >  문제를 재현합니다.  

다음 표에서는 미디어 로그 위치를 간략하게 간략하게 설명합니다. Microsoft 지원에 로그 파일을 보낼 때 로그 파일의 타임스탬프를 확인하여 문제를 재현할 때 로그가 시간 프레임을 커버하는지 확인해야 합니다.

|클라이언트 |위치 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

생성되는 로그 파일 목록과 포함된 정보는 다음과 같습니다.

|로그 파일 이름  |설명  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | 미디어 스택과 관련된 정보가 포함되어 있습니다. 여기에는 해상도, 디코더 및 인코더와 같은 채널 상태, 전송 및 수신된 프레임 수, 카메라 및 VBSS(비디오 기반 화면 공유) 세션 상태가 포함됩니다.         |
|rtmcontrol.msrtc-0-2415069487.blog      |제어가 제공된 타임스탬프 및 마우스 포인터 정보와 같은 원격 제어 작업과 관련된 정보를 기록합니다.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |미디어 스택 추적 이벤트를 기록합니다.         |
|Debug-0-s2790420889.blog    | 렌더링 품질을 포함하여 미디어 에이전트와 관련된 정보를 제공합니다.          |
|tscalling-0-2061129496.blog   |ts-calling API에서 이벤트를 기록합니다.       |

## <a name="desktop-logs"></a>데스크톱 로그

부트스트래퍼 로그라고도 하는 데스크톱 로그에는 데스크톱 클라이언트와 브라우저 간에 발생하는 로그 데이터가 포함되어 있습니다. 미디어 로그와 마찬가지로 이러한 로그는 Microsoft에서 요청한 경우만 필요합니다. 로그는 텍스트 기반이 며, 하락 형식의 텍스트 기반 편집기를 사용하여 읽을 수 있습니다.

Windows:

 - 시스템 **트레이에서** Microsoft Teams 아이콘을 마우스 오른쪽 단추로 클릭하고 로그를 **선택합니다.**

Mac OsX:

 - 도움말 **풀다운 메뉴에서** 로그를 선택합니다. 

Linux:

 - 시스템 **트레이에서** Microsoft Teams 아이콘을 클릭하고 로그를 **선택합니다.**

|클라이언트 |위치 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="browser-trace"></a>브라우저 추적

일부 오류 범주의 경우 Microsoft 지원에서 브라우저 추적을 수집해야 할 수 있습니다. 이 정보는 오류 발생 시 클라이언트의 Teams 중요한 세부 정보를 제공할 수 있습니다.

브라우저 추적을 시작하기 전에 로그인되어 있는지 Teams. 추적에 중요한 로그인 정보가 포함되지 않습니다. 추적을 시작하기 전에 이 작업을 하는 것이 중요합니다.

로그인한 후 브라우저에 적합한 다음 링크 중 하나를 선택하고 제공된 단계를 따릅니다. 

-   [Chrome & Edge(Chromium)](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [Edge](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [Safari](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [Firefox](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> 이 단계에서 Azure Portal에 대한 모든 참조를 Teams 클라이언트로 바 대체합니다. 

## <a name="related-topics"></a>관련 항목

[Teams 문제 해결](/MicrosoftTeams/troubleshoot/teams)
