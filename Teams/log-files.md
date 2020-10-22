---
title: Microsoft 팀 문제 해결에서 로그 파일 사용
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
description: Microsoft 팀에서 생성 하는 디버그, 미디어, 데스크톱 로그, 찾을 수 있는 위치, 문제 해결에 도움이 되는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2ff24ddb8aaf63b539959119138aebf2f5d4e81f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650831"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a>Microsoft 팀 문제 해결에서 로그 파일 사용
=================================================

Microsoft 팀의 문제 해결을 지원 하기 위해 사용할 수 있는 세 가지 유형의 로그 파일이 클라이언트에서 자동으로 생성 됩니다.

-   디버그 로그

-   미디어 로그

-   데스크톱 로그

Microsoft 지원으로 지원 요청을 만들 때 지원 엔지니어에 게 디버그 로그가 필요 합니다. 지원 요청을 만들기 전에 이러한 로그에 로그인 하면 Microsoft에서 문제 해결을 빠르게 시작할 수 있습니다. Microsoft에서 요청 하는 경우에만 미디어 또는 데스크톱 로그가 필요 합니다.

다음 표에서는 다양 한 클라이언트 및 관련 로그에 대해 간략하게 설명 합니다. 로그 파일은 클라이언트 및 운영 체제와 관련 된 위치에 저장 됩니다.


|클라이언트 |디버깅이|데스크톱이|미디어|
|---------|---------|---------|---------|
|웹    |X         |-         |-         |
|Windows     |X         |X         |X         |
|Mac OSX     |X         |X         |X         |
|Linux     |X         |X         |X         |
|iOS     |-         |-         |-         |
|Android     |-         |-         |-         |

지원 되는 운영 체제 및 브라우저의 전체 목록은 [Microsoft 팀 용 클라이언트 가져오기를](get-clients.md)참조 하세요.

<a name="debug-logs"></a>디버그 로그
---------------------------

가장 일반적인 로그가 며 모든 Microsoft 지원 사례에 필요 합니다. 디버그 로그는 브라우저 기반 클라이언트를 비롯 하 여 Windows 및 Mac 데스크톱 클라이언트에 의해 생성 됩니다. 로그는 텍스트 기반 이며 아래쪽에서 읽습니다. 모든 텍스트 기반 편집기를 사용 하 여 읽을 수 있으며, 클라이언트에 로그인 할 때 새 로그가 만들어집니다.

디버그 로그에는 다음과 같은 데이터 흐름이 표시 됩니다.

-   로그인

-   중앙 계층 서비스에 대 한 연결 요청

-   통화/대화

디버그 로그는 다음 OS 관련 메서드를 사용 하 여 생성 됩니다.

-   창을

      바로 가기 키: Ctrl + Alt + Shift + 1

-   Mac OSX:

      바로 가기 키: Option + Command + Shift + 1

-   Linux

      바로 가기 키: Ctrl + Alt + Shift + 1

디버그 로그는 다음 폴더에 자동으로 다운로드 됩니다.

-   Windows:% userprofile% \\ 다운로드

-   Mac OSX: ~/다운로드

-   Linux: ~/다운로드

-   브라우저: 디버그 로그를 기본 저장 위치에 저장 하 라는 메시지가 표시 됩니다.

<a name="media-logs"></a>미디어 로그
---------------------------

미디어 로그에는 팀 모임에서 오디오, 비디오, 화면 공유에 대 한 진단 데이터가 포함 됩니다. 통화 관련 문제에 연결 된 지원 사례에 필요 합니다.

미디어 로깅은 기본적으로 꺼져 있습니다. 팀 모임에 대 한 진단 데이터를 기록 하려면 사용자가 팀 클라이언트에서 옵션을 설정 해야 합니다. **설정**  >  **일반**으로 이동 하 여 **모임 진단 로깅 사용 (팀 다시 시작 필요**) 확인란을 선택한 다음 팀을 다시 시작 하 고 문제를 재현해 보세요. 

다음 표에서는 미디어 로그 위치에 대해 간략하게 설명 합니다. Microsoft 지원에 로그 파일을 보낼 때 로그 파일의 타임 스탬프를 확인 하 여 문제를 재현할 때 로그가 시간 프레임을 포함 하는지 확인 하십시오.

|클라이언트 |위치 |
|---------|---------|
|Windows     |%appdata%\Microsoft\Teams\media-stack \\ * 블로그         |
|            |%appdata%\Microsoft\Teams\skylib \\ * 블로그
|            |%appdata%\Microsoft\Teams\media-stack \\ * .etl         |
|Mac OSX     |~/Library/Application Support/Microsoft/팀/media-stack/* 블로그         |
|            |~/Library/Application Support/Microsoft/팀/skylib/* 블로그         |
|Linux       |~/.config/Microsoft/Microsoft 팀/media-stack/*-블로그         |
|            |~/.config/Microsoft/Microsoft 팀/skylib/*-블로그         |

생성 되는 로그 파일과 해당 파일에 포함 된 정보 목록은 다음과 같습니다.

|로그 파일 이름  |설명  |
|---------|---------|
|팀. msrtc-0-s1039525249. 블로그     | 미디어 스택과 관련 된 정보를 포함 합니다. 여기에는 해상도, 디코더 및 인코더와 같은 채널 상태, 보내고 받은 프레임 수, 카메라 및 비디오 기반 화면 공유 (VBSS) 세션 상태 등이 포함 됩니다.         |
|rtmcontrol-msrtc-0-2415069487. 블로그      |컨트롤을 지정 하는 경우의 타임 스탬프 및 마우스 포인터 정보 등 원격 제어 작업과 관련 된 정보를 기록 합니다.          |
|Teams_MediaStackETW -2-U-xr-U .etl      |미디어 스택 추적 이벤트를 기록 합니다.         |
|디버그-0-s2790420889    | 미디어 에이전트와 관련 된 정보 (렌더링 품질 포함)를 포함 합니다.          |
|tscalling-0-2061129496-블로그   |Ts 호출 API의 이벤트를 기록 합니다.       |

<a name="desktop-logs"></a>데스크톱 로그
---------------------

데스크톱 로그 (부트스트래퍼 로그 라고도 함)는 데스크톱 클라이언트와 브라우저 간에 발생 하는 로그 데이터를 포함 합니다. 이 로그는 미디어 로그와 마찬가지로, Microsoft에서 요청 하는 경우에만 필요 합니다. 로그는 텍스트 기반 이며, 텍스트 기반 편집기를 사용 하 여 하향식 형식으로 읽을 수 있습니다.

창을

1.  시스템 트레이에서 **Microsoft 팀** 아이콘을 마우스 오른쪽 단추로 클릭 하 고 **로그 가져오기를** 선택 합니다.

Mac OsX:

1.  **도움말** 풀 다운 메뉴에서 **로그 가져오기를** 선택 합니다.

Linux

1.  시스템 트레이에서 **Microsoft 팀** 아이콘을 클릭 하 고 **로그 가져오기를** 선택 합니다.

|클라이언트 |위치 |
|---------|---------|
|Windows     |% appdata% \Microsoft\Teams\logs.txt         |
|Mac OSX     |~/Library/Application 지원/Microsoft/팀/logs.txt         |
|Linux       |~/.config/Microsoft/Microsoft 팀/logs.txt         |


## <a name="related-topics"></a>관련 항목

[Teams 문제 해결](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
