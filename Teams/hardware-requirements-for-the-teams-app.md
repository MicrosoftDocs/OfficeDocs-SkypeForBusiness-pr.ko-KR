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
description: 이 문서에서는 Microsoft Teams를 설치하고 실행하기 위해 필요한 하드웨어 요구 사항에 대해 배웠습니다.
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
|컴퓨터 및 프로세서    | 최소 1.6GHz(이상), 2코어        |
|메모리     |    4.0GB RAM     |
|하드 디스크    | 3.0GB의 사용 가능한 디스크 공간        |
|디스플레이    |   화면 해상도 1024x768 |
|그래픽 하드웨어 |  Windows OS: 그래픽 하드웨어 가속에는 Windows 10용 WDDM 2.0 이상(또는 Windows 10 Fall Creators Update의 경우 WDDM 1.3 이상)이 있는 DirectX 9 이상이 필요합니다.
|운영 체제  |    Windows 10, Windows 10 on ARM, Windows 8.1, Windows Server 2019, Windows Server 2016|
|.NET 버전    |  .NET 4.5 CLR 이상 필요       |
|비디오    |  USB 2.0 비디오 카메라       |
|장치    |   표준 노트북 카메라, 마이크 및 스피커    |
|화상 통화 및 모임|<ul><li>2코어 프로세서가 필요합니다. 더 높은 비디오/화면 공유 해상도 및 프레임 속도의 경우 4코어 프로세서 이상을 권장합니다.</li> <li>배경 비디오 효과에는 Windows 10 또는 AVX2 명령 집합이 있는 프로세서가 필요 합니다.</li> <li>지원되지 않는 디코더 및 인코더 목록은 [하드웨어 디코더 및 인코더 드라이버 권장 사항](hardware-decoders-and-encoders.md)을 참조합니다.</li><li>Microsoft Teams 회의실에서 근접 검색을 사용하여 모임에 참가하려면 Bluetooth LE가 필요하며, 클라이언트 장치에서 Bluetooth 사용하도록 설정해야 합니다. Windows 클라이언트의 경우 64비트 Teams 클라이언트도 필요합니다. 이 기능은 32비트 Teams 클라이언트에서 사용할 수 없습니다.</li></ul> |
|Teams 라이브 이벤트 | Teams 라이브 이벤트를 생성하는 경우 코어 i5 Kaby Lake 프로세서, 4.0GB RAM(이상) 및 하드웨어 인코더가 있는 컴퓨터를 사용하는 것이 좋습니다. 지원되지 [않는 디코더](hardware-decoders-and-encoders.md) 및 인코더  목록에 대한 하드웨어 디코더 및 인코더 드라이버 권장 사항을 참조하세요. |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Mac용 Teams의 하드웨어 요구 사항

| 구성 요소 | 요구 사항 |
|---------|---------|
|컴퓨터 및 프로세서    | Intel Core Duo 프로세서 |
|메모리     |   4.0GB RAM      |
|하드 디스크    |   1.5GB의 사용 가능한 디스크 공간      |
|디스플레이    | 모니터 해상도 1280x800 이상    |
|운영 체제  |    macOS의 최신 버전 3개 중 하나. 최신 macOS 버전 및 macOS 버전을 업그레이드하는 방법에 대한 정보는 여기에서 찾을 수 [있습니다.](https://support.apple.com/en-us/HT201260) 예를 들어 새 버전의 macOS가 릴리스될 때 새 버전과 바로 앞에 있는 두 버전이 지원되는 버전이 됩니다.      |
|비디오  |    호환되는 웹캠     |
|음성    |  호환되는 마이크 및 스피커, 마이크가 장착된 헤드셋 또는 동급 장치.       |
|화상 통화 및 모임 | <ul><li>2코어 프로세서가 필요합니다. 더 높은 비디오/화면 공유 해상도 및 프레임 속도의 경우 4코어 프로세서 이상을 권장합니다. </li><li>Microsoft Teams 회의실에서 근접 검색을 사용하여 모임에 참가하는 것은 macOS에서 사용할 수 없습니다.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Linux용 Teams의 하드웨어 요구 사항

| 구성 요소 | 요구 사항 |
|---------|---------|
|컴퓨터 및 프로세서    | 1.6GHz 이상(32비트 또는 64비트), 2코어        |
|메모리     |    4.0GB RAM     |
|하드 디스크    | 3.0GB의 사용 가능한 디스크 공간        |
|디스플레이    |   화면 해상도 1024x768 |
|그래픽 하드웨어 |  128MB 그래픽 메모리
|운영 체제  | DEB 또는 RPM을 설치할 수 있는 Linux 배포판 |
|비디오    |  USB 2.0 비디오 카메라       |
|장치    |   표준 노트북 카메라, 마이크 및 스피커    |
|음성    |  호환되는 마이크 및 스피커, 마이크가 장착된 헤드셋 또는 동급 장치.       |
|화상 통화 및 모임 | <ul><li>2코어 프로세서가 필요합니다. 더 높은 비디오/화면 공유 해상도 및 프레임 속도의 경우 4코어 프로세서 이상을 권장합니다.</li><li>Linux에서는 Microsoft Teams 대화방에서 주변 검색을 사용하여 모임에 참가할 수 없습니다.</li></ul>
|지원되는 Linux 배포판 | Ubuntu 18.04 LTS, 20.04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8       |
|지원되는 데스크톱 환경 | GNOME, KDE       |
|지원되는 디스플레이 서버 | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>모바일 장치용 Teams의 하드웨어 요구 사항

다음 모바일 플랫폼에서 Teams를 사용할 수 있습니다.

- Android: Android 휴대폰 및 태블릿과 호환됩니다.

  지원은 Android의 마지막 **네** 가지 주요 버전으로 제한됩니다. 예를 들어 새로운 주 버전의 Android가 릴리스될 때 Android 요구 사항은 새 버전과 그 앞에 있는 최신 버전 3개입니다.

- iOS: iPhone, iPad 및 iPod touch와 호환됩니다.

  지원은 **iOS의** 가장 최근 두 가지 주요 버전으로 제한됩니다. 예를 들어, 새로운 주 버전의 iOS가 릴리스될 때 iOS 요구 사항은 새 버전 및 이전의 최신 버전입니다. iOS에서 배경 비디오 효과를 선택적으로 흐리게 하려면 iOS 12 이상 운영 체제가 필요하며, iPhone 7 이상, iPad 2018(6세대) 이상 및 iPod touch 2019(7세대)와 호환됩니다. 

> [!Note]
> Teams에서 최상의 환경을 활용하려면 최신 버전의 iOS 및 Android를 사용하세요.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>VDI(가상 데스크톱 인프라) 환경에서 Teams의 하드웨어 요구 사항

가상화된 환경에서 Teams를 실행하기 위한 요구 사항은 [가상화된 데스크톱 인프라용 Teams](teams-for-vdi.md)를 참조하세요.

### <a name="related-topics"></a>관련 항목

- [Teams 앱 받기](get-clients.md)
- [모바일 장치용 Microsoft Teams](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [MSI를 사용하여 Microsoft Teams 앱 설치](msi-deployment.md)
- [Microsoft Teams의 제한 사항 및 사양](limits-specifications-teams.md)
