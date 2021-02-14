---
title: Microsoft Teams 문제 해결에 로그 파일 사용
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Microsoft Teams에서 생성한 디버그, 미디어 및 데스크톱 로그, 로그를 찾을 수 있는 위치 및 문제 해결에 도움이 되는 방법에 대해 자세히 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 295886e7a5c50107672d17dcfa06067ba1b0ac9b
ms.sourcegitcommit: 48b8801b86a6c900c224853590daa3cb3c8d4ded
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49761096"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Microsoft Teams 문제 해결에 로그 파일 사용
=================================================

클라이언트에서 자동으로 생성되는 세 가지 유형의 로그 파일이 있습니다. 이 로그 파일은 Microsoft Teams 문제 해결을 지원하기 위해 활용할 수 있습니다.

-   로그 디버그

-   미디어 로그

-   데스크톱 로그

Microsoft 지원으로 지원 요청을 만들 때 지원 엔지니어에게 디버그 로그가 필요하게 됩니다. 지원 요청을 만들기 전에 디버그 로그를 진행하면 Microsoft에서 문제 해결을 신속하게 시작할 수 있습니다. **미디어** 또는 **데스크톱** 로그는 Microsoft에서 요청한 경우 필요합니다.

> [!NOTE]
> 이 문서에서 **디버그** 로그란 문제 해결에 사용되는 로그를 참조합니다. 그러나 이러한 로그에 대해 생성된 파일에는 이름에 진단 로그이라는 **용어가** 포함되어 있습니다.  

다음 표에서는 다양한 클라이언트 및 관련 로그를 간략하게 설명하고 있습니다. 로그 파일은 클라이언트 및 운영 체제에 특정된 위치에 저장됩니다.


|클라이언트 |디버그|데스크톱|미디어|
|---------|---------|---------|---------|
|웹    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

지원되는 운영 체제 및 브라우저의 전체 목록은 [Microsoft Teams용 클라이언트 다운로드를 참조하세요.](get-clients.md)

<a name="debug-logs"></a>로그 디버그
---------------------------

이러한 로그는 가장 일반적인 로그로, 모든 Microsoft 지원 사례에 필요합니다. 디버그 로그는 Windows 및 Mac 데스크톱 클라이언트뿐만 아니라 브라우저 기반 클라이언트에 의해 생성됩니다. 로그는 텍스트 기반이 며 아래쪽에서 읽습니다. 텍스트 기반 편집기를 사용하여 읽을 수 있으며 클라이언트에 로그인할 때 새 로그가 만들어집니다.

디버그 로그에는 다음과 같은 데이터 흐름이 표시됩니다.

-   로그인

-   중간 계층 서비스에 대한 연결 요청

-   통화/대화

디버그 로그는 다음 OS 관련 메서드를 사용하여 생성됩니다.

-   Windows:

      바로 가기 키: Ctrl+ Alt + Shift + 1

-   Mac OSX:

      바로 가기 키: Option+Command+Shift+1

-   Linux:

      바로 가기 키: Ctrl+ Alt + Shift + 1

디버그 로그는 다음 폴더에 자동으로 다운로드됩니다.

-   Windows: %userprofile% \\ 다운로드

-   Mac OSX: ~/Downloads

-   Linux: ~/Downloads

-   브라우저: 디버그 로그를 기본 저장 위치에 저장하라는 메시지가 표시됩니다.

<a name="media-logs"></a>미디어 로그
---------------------------

미디어 로그에는 Teams 모임에서 오디오, 비디오 및 화면 공유에 대한 진단 데이터가 포함되어 있습니다. 호출 관련 문제에 연결된 지원 사례에 필요합니다.

미디어 로깅은 기본적으로 해제되어 있습니다. Teams 모임에 대한 진단 데이터를 기록하려면 사용자가 Teams 클라이언트에서 옵션을 설정해야 합니다. 설정 **일반으로** 이동하여 모임 진단에 로깅 사용(Teams 다시 시작 필요) 확인란을 선택하고 Teams를 다시 시작하고  >  문제를 재현합니다. 

다음 표에서는 미디어 로그 위치를 간략하게 설명하고 있습니다. Microsoft 지원에 로그 파일을 보낼 때 로그 파일의 타임스탬프를 확인하여 문제를 재현할 때 로그가 시간 프레임을 포함하도록 합니다.

|클라이언트 |위치 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ *.blog         |
|            |%appdata%\Microsoft\Teams\skylib \\ *.blog
|            |%appdata%\Microsoft\Teams\media-stack \\ *.etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/media-stack/*.blog         |
|            |~/Library/Application Support/Microsoft/Teams/skylib/*.blog         |
|Linux       |~/.config/Microsoft/Microsoft Teams/media-stack/*.blog         |
|            |~/.config/Microsoft/Microsoft Teams/skylib/*.blog         |

다음은 생성된 로그 파일 목록과 포함된 정보입니다.

|로그 파일 이름  |설명  |
|---------|---------|
|Teams.msrtc-0-s1039525249.blog     | 미디어 스택과 관련된 정보를 포함 합니다. 여기에는 해상도, 디코더 및 사용된 인코더, 전송 및 수신 프레임 수, 카메라 및 VBSS(비디오 기반 화면 공유) 세션 상태와 같은 채널 상태가 포함됩니다.         |
|rtmcontrol.msrtc-0-2415069487.blog      |컨트롤이 제공된 경우 타임스탬프 및 마우스 포인터 정보와 같은 원격 제어 작업과 관련된 정보를 기록합니다.          |
|Teams_MediaStackETW-2-U-xr-U.etl      |미디어 스택 추적 이벤트를 기록합니다.         |
|Debug-0-s2790420889.blog    | 렌더링 품질을 포함하여 미디어 에이전트와 관련된 정보를 제공합니다.          |
|tscalling-0-2061129496.blog   |ts 호출 API에서 이벤트를 기록합니다.       |

<a name="desktop-logs"></a>데스크톱 로그
---------------------

부트스트래퍼 로그라고도 하는 데스크톱 로그에는 데스크톱 클라이언트와 브라우저 간에 발생하는 로그 데이터가 포함되어 있습니다. 미디어 로그와 마찬가지로 이러한 로그는 Microsoft에서 요청한 경우 필요합니다. 로그는 텍스트 기반이 며 하한 형식의 텍스트 기반 편집기를 사용하여 읽을 수 있습니다.

Windows:

 - 시스템 트레이에서 **Microsoft Teams** 아이콘을 마우스 오른쪽 단추로 클릭하고 로그 **다운로드를 선택합니다.**

Mac OsX:

 - 도움말 **풀다운 메뉴에서** **로그를** 선택합니다.

Linux:

 - 시스템 **트레이에서 Microsoft Teams** 아이콘을 클릭하고 로그 **다운로드를 선택합니다.**

|클라이언트 |위치 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application Support/Microsoft/Teams/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft Teams/logs.txt         |


## <a name="related-topics"></a>관련 항목

[Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
