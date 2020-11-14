---
title: Microsoft Teams의 하드웨어 요구 사항
ms.reviewer: microthk, sthurlow
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
localization_priority: Normal
search.appverid: MET150
description: 이 문서에서는 Microsoft 팀을 설치 하 고 실행 하는 데 필요한 하드웨어 요구 사항에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 90d59bb7753cfd26cf6d0b90835cf8cf27661641
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030274"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Microsoft Teams의 하드웨어 요구 사항

다음 섹션의 모든 요구 사항은 Microsoft Teams 데스크톱 앱과 Teams 웹 앱 모두에 적용됩니다.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Windows PC용 Teams의 하드웨어 요구 사항

| 구성 요소 | 요구 사항 |
|---------|---------|
|컴퓨터 및 프로세서    | 최소 1.6 GHz 이상, 코어 2 개        |
|메모리     |    4.0 GB RAM     |
|하드 디스크    | 3.0GB의 사용 가능한 디스크 공간        |
|디스플레이    |   화면 해상도 1024x768 |
|그래픽 하드웨어 |  Windows OS: 그래픽 하드웨어 가속에는 Windows 10 용 WDDM 2.0 이상에는 DirectX 9 이상이 필요 합니다 (또는 Windows 10이 하 작성자 용 WDDM 1.3 이상).
|운영 체제  |    Windows 10, ARM의 Windows 10, Windows 8.1, Windows Server 2019, Windows Server 2016|
|.NET 버전    |  .NET 4.5 CLR 이상 필요       |
|비디오    |  USB 2.0 비디오 카메라       |
|장치    |   표준 노트북 카메라, 마이크 및 스피커    |
|화상 통화 및 모임|<ul><li>2-코어 프로세서가 필요 합니다. 비디오/화면 공유 해상도와 프레임 속도를 높이는 경우에는 4-코어 프로세서를 더 잘 활용 하는 것이 좋습니다.</li> <li>배경 영상 효과에는 Windows 10 또는 AVX2 명령 집합이 있는 프로세서가 필요 합니다.</li> <li>지원되지 않는 디코더 및 인코더 목록은 [하드웨어 디코더 및 인코더 드라이버 권장 사항](hardware-decoders-and-encoders.md)을 참조합니다.</li><li>Microsoft 팀 대화방에서 근접 검색을 사용 하 여 모임에 참가 하려면 bluetooth LE가 필요 하며,이 경우 클라이언트 장치에서 블루투스를 사용 하도록 설정 해야 하며, Windows 클라이언트의 경우에는 64 비트 팀 클라이언트만 필요 합니다. 32 비트 팀 클라이언트에서는이 기능을 사용할 수 없습니다.</li></ul> |
|Teams 라이브 이벤트 | 팀 live 이벤트를 생성 하는 경우 코어 i5 Kaby 호수 프로세서, 4.0 GB RAM (또는 그 이상) 및 하드웨어 인코더가 있는 컴퓨터를 사용 하는 것이 좋습니다. **지원 되지 않는** 디코더 및 인코더 목록은 [하드웨어 디코더 및 인코더 드라이버 권장 사항을](hardware-decoders-and-encoders.md) 참조 하세요. |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Mac용 Teams의 하드웨어 요구 사항

| 구성 요소 | 요구 사항 |
|---------|---------|
|컴퓨터 및 프로세서    | 인텔 코어 듀오 프로세서 |
|메모리     |   4.0 GB RAM      |
|하드 디스크    |   1.5GB의 사용 가능한 디스크 공간      |
|디스플레이    | 모니터 해상도 1280x800 이상    |
|운영 체제  |    세 가지 최신 버전의 macOS 중 하나입니다. 최신 macOS 버전 및 macOS 버전을 업그레이드 하는 방법에 대 한 자세한 내용은 [여기](https://support.apple.com/en-us/HT201260)에서 확인할 수 있습니다. 예를 들어 새 버전의 macOS가 릴리스되면 새 버전과 그 바로 앞의 두 가지가 지원 되는 버전이 됩니다.      |
|비디오  |    호환되는 웹캠     |
|음성    |  호환되는 마이크 및 스피커, 마이크가 장착된 헤드셋 또는 동급 장치.       |
|화상 통화 및 모임 | <ul><li>2-코어 프로세서가 필요 합니다. 비디오/화면 공유 해상도와 프레임 속도를 높이는 경우에는 4-코어 프로세서를 더 잘 활용 하는 것이 좋습니다. </li><li>MacOS에서는 Microsoft 팀 대화방에서 근접 검색을 사용 하 여 모임에 참가할 수 없습니다.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Linux용 Teams의 하드웨어 요구 사항

| 구성 요소 | 요구 사항 |
|---------|---------|
|컴퓨터 및 프로세서    | 1.6 GHz (또는 그 이상) (32 비트 또는 64 비트), 코어 2 개        |
|메모리     |    4.0 GB RAM     |
|하드 디스크    | 3.0GB의 사용 가능한 디스크 공간        |
|디스플레이    |   화면 해상도 1024x768 |
|그래픽 하드웨어 |  128 MB 그래픽 메모리
|운영 체제  | DEB 또는 RPM을 설치할 수 있는 Linux 배포판 |
|비디오    |  USB 2.0 비디오 카메라       |
|장치    |   표준 노트북 카메라, 마이크 및 스피커    |
|음성    |  호환되는 마이크 및 스피커, 마이크가 장착된 헤드셋 또는 동급 장치.       |
|화상 통화 및 모임 | <ul><li>2-코어 프로세서가 필요 합니다. 비디오/화면 공유 해상도와 프레임 속도를 높이는 경우에는 4-코어 프로세서를 더 잘 활용 하는 것이 좋습니다.</li><li>Linux에서는 Microsoft Teams 대화방에서 주변 검색을 사용하여 모임에 참가할 수 없습니다.</li></ul>
|지원되는 Linux 배포판 | Ubuntu 18.04 LTS, 20.04 LTS, Fedora 30 워크스테이션, RHEL 8 Workstation, CentOS 8       |
|지원 되는 데스크톱 환경 | GNOME, KDE       |
|지원 되는 디스플레이 서버 | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>모바일 장치용 Teams의 하드웨어 요구 사항

다음 모바일 플랫폼에서 Teams를 사용할 수 있습니다.

- Android: Android 휴대폰 및 태블릿과 호환됩니다.

  지원은 Android의 **마지막 네 가지** 주요 버전으로 제한 됩니다. 예를 들어 Android의 새 주요 버전이 릴리스되면 Android 요구 사항은 새 버전과 그 이전의 세 가지 최신 버전입니다.

- iOS: iPhone, iPad 및 iPod touch와 호환됩니다.

  IOS의 최신 주 버전 **두 개** 에 대 한 지원이 제한 됩니다. 예를 들어 iOS의 새 주요 버전이 릴리스되면 iOS 요구 사항은 새 버전과 그 앞에 있는 최신 버전입니다. 선택적 **흐림** 효과에는 ios 12 이상의 운영 체제, iPhone 7 이상, iPad 2018 (6 세대) 이상, iPod touch 2019 (일곱 세대) 등의 장치를 사용 하는 것이 필요 합니다.

> [!Note]
> Teams에서 최상의 환경을 활용하려면 최신 버전의 iOS 및 Android를 사용하세요.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>VDI(가상 데스크톱 인프라) 환경에서 Teams의 하드웨어 요구 사항

가상화된 환경에서 Teams를 실행하기 위한 요구 사항은 [가상화된 데스크톱 인프라용 Teams](teams-for-vdi.md)를 참조하세요.

### <a name="related-topics"></a>관련 항목

- [Teams 앱 받기](get-clients.md)
- [모바일 장치용 Microsoft Teams](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [MSI를 사용하여 Microsoft Teams 앱 설치](msi-deployment.md)
- [Microsoft Teams의 제한 사항 및 사양](limits-specifications-teams.md)
