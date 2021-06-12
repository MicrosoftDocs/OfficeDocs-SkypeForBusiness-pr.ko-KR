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
localization_priority: Priority
search.appverid: MET150
description: 이 문서에서는 Microsoft Teams를 설치하고 실행하는 데 필요한 하드웨어 요구 사항에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ed6ad995cd0a1624171396b68bec3355fc05f559
ms.sourcegitcommit: 2419348e964cfe97b72d533f267c5d7055d5366f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2021
ms.locfileid: "52909950"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Microsoft Teams의 하드웨어 요구 사항

다음 섹션의 모든 요구 사항은 Microsoft Teams 데스크톱 앱과 Teams 웹 앱 모두에 적용됩니다.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Windows PC용 Teams의 하드웨어 요구 사항

| 구성 요소 | 요구 사항 |
|---------|---------|
|컴퓨터 및 프로세서    | 최소 1.1 GHz 이상, 2코어<br><br>참고: Intel 프로세서의 경우 Intel Turbo Boost 기술(최대 터보 빈도)을 사용하여 달성하는 최대 속도를 고려해야 합니다.         |
|메모리     |    4.0GB RAM(Teams에는 다른 시스템 요구 사항보다 전용 4GB RAM 이상이 필요)    |
|하드 디스크    | 3.0GB의 사용 가능한 디스크 공간        |
|디스플레이    |   화면 해상도 1024x768 |
|그래픽 하드웨어 |  Windows OS: 그래픽 하드웨어 가속화에는 Windows 10용 WDDM 2.0 이상(또는 Windows 10 Fall Creators Update의 경우 WDDM 1.3 이상)을 포함하는 DirectX 9 이상이 필요합니다.
|운영 체제  |    Windows 10, ARM의 Windows 10, Windows 8.1, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2. 참고: 사용 가능한 최신 Windows 버전 및 보안 패치를 사용하는 것이 좋습니다.|
|.NET 버전    |  .NET 4.5 CLR 이상 필요       |
|비디오    |  USB 2.0 비디오 카메라       |
|장치    |   표준 노트북 카메라, 마이크 및 스피커    |
|화상 통화 및 모임|<ul><li>2코어 프로세서가 필요합니다. 비디오/화면 공유 해상도 및 프레임 속도를 높이려면 4코어 프로세서 이상을 사용하는 것이 좋습니다.</li> <li>배경 비디오 효과에는 Windows 10 또는 AVX2 명령 집합이 있는 프로세서가 필요합니다.</li> <li>지원되지 않는 디코더 및 인코더 목록은 [하드웨어 디코더 및 인코더 드라이버 권장 사항](hardware-decoders-and-encoders.md)을 참조하세요.</li><li>Microsoft Teams 룸에서 주변 검색을 사용하여 모임에 참가하려면 클라이언트 장치에서 Bluetooth의 활성화가 요구되는 Bluetooth LE가 필요하고 Windows 클라이언트의 경우 64비트 Teams 클라이언트도 필요합니다. 이 기능은 32비트 Teams 클라이언트에서는 이용할 수 없습니다.</li></ul> |
|Teams 라이브 이벤트 | Teams 라이브 이벤트를 생성하는 경우 Core i5 Kaby Lake 프로세서, 4.0GB RAM 이상 및 하드웨어 인코더가 있는 컴퓨터를 사용하는 것이 좋습니다. **지원되지 않는** 디코더 및 인코더 목록은 [하드웨어 디코더 및 인코더 드라이버 권장 사항](hardware-decoders-and-encoders.md)을 참조하세요. |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Mac용 Teams 하드웨어 요구 사항

| 구성 요소 | 요구 사항 |
|---------|---------|
|컴퓨터 및 프로세서    | Intel Core Duo 프로세서 |
|메모리     |   4.0GB RAM(Teams에는 다른 시스템 요구 사항보다 전용 4GB RAM 이상이 필요)     |
|하드 디스크    |   1.5GB의 사용 가능한 디스크 공간      |
|디스플레이    | 모니터 해상도 1280x800 이상    |
|운영 체제  |    가장 최근 세 가지 macOS 버전 중 하나. 최신 macOS 버전에 대한 정보와 macOS 버전을 업그레이드하는 방법에 대한 정보를 찾을 수 있습니다. [여기](https://support.apple.com/ko-KR/HT201260). 예를 들어 새 버전의 macOS가 릴리스된 경우 새 버전과 바로 이전 두 버전이 지원되는 버전이 됩니다.      |
|비디오  |    호환되는 웹캠     |
|음성    |  호환되는 마이크 및 스피커, 마이크가 장착된 헤드셋 또는 동급 장치.       |
|화상 통화 및 모임 | <ul><li>2코어 프로세서가 필요합니다. 비디오/화면 공유 해상도 및 프레임 속도를 높이려면 4코어 프로세서 이상을 사용하는 것이 좋습니다. </li><li>macOS에서는 Microsoft Teams 룸에서 주변 검색을 사용하여 모임에 참가할 수 없습니다.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Linux용 Teams 하드웨어 요구 사항

| 구성 요소 | 요구 사항 |
|---------|---------|
|컴퓨터 및 프로세서    | 1.6GHz 이상(32비트 또는 64비트), 2코어        |
|메모리     |    4.0GB RAM(Teams에는 다른 시스템 요구 사항보다 전용 4GB RAM 이상이 필요)   |
|하드 디스크    | 3.0GB의 사용 가능한 디스크 공간        |
|디스플레이    |   화면 해상도 1024x768 |
|그래픽 하드웨어 |  128MB의 그래픽 메모리
|운영 체제  | DEB 또는 RPM을 설치할 수 있는 Linux 배포판 |
|비디오    |  USB 2.0 비디오 카메라       |
|장치    |   표준 노트북 카메라, 마이크 및 스피커    |
|음성    |  호환되는 마이크 및 스피커, 마이크가 장착된 헤드셋 또는 동급 장치.       |
|화상 통화 및 모임 | <ul><li>2코어 프로세서가 필요합니다. 비디오/화면 공유 해상도 및 프레임 속도를 높이려면 4코어 프로세서 이상을 사용하는 것이 좋습니다.</li><li>Linux에서는 Microsoft Teams 대화방에서 주변 검색을 사용하여 모임에 참가할 수 없습니다.</li></ul>
|지원되는 Linux 배포판 | Ubuntu 18.04 LTS, 20.04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8       |
|지원되는 데스크톱 환경 | GNOME, KDE       |
|지원되는 디스플레이 서버 | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>모바일 장치용 Teams의 하드웨어 요구 사항

다음 모바일 플랫폼에서 Teams를 사용할 수 있습니다.

- Android: Android 휴대폰 및 태블릿과 호환됩니다.

  Android의 **최근 네 개** 의 주 버전으로 지원이 제한됩니다. 예를 들어 Android의 새로운 주 버전이 릴리스된 경우 Android 요구 사항은 새 버전과 그 이전의 최신 버전 3개입니다.

- iOS: iPhone, iPad 및 iPod touch와 호환됩니다.

  iOS의 최신 주 버전 **두 개** 로 지원이 제한됩니다. 예를 들어 iOS의 새로운 주 버전이 릴리스된 경우 iOS 요구 사항은 새 버전과 그 이전의 최신 버전입니다. iOS에서 선택 사항인 **내 배경 흐리기** 비디오 효과에는 iOS 12 이상의 운영 체제가 필요하며, iPhone 7 이상, iPad 2018(6세대) 이상 및 iPod touch 2019(7세대)와 호환됩니다.

> [!Note]
> Teams에서 최상의 환경을 활용하려면 최신 버전의 iOS 및 Android를 사용하세요.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>VDI(가상 데스크톱 인프라) 환경에서 Teams의 하드웨어 요구 사항

가상화된 환경에서 Teams를 실행하기 위한 요구 사항은 [가상화된 데스크톱 인프라용 Teams](teams-for-vdi.md)를 참조하세요.

### <a name="related-topics"></a>관련 항목

- [Teams 앱 받기](get-clients.md)
- [모바일 장치용 Microsoft Teams](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [MSI를 사용하여 Microsoft Teams 앱 설치](msi-deployment.md)
- [Microsoft Teams의 제한 사항 및 사양](limits-specifications-teams.md)
