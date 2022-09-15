---
title: Microsoft Teams용 클라이언트 다운로드
author: dstrome
ms.author: dstrome
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
ms.localizationpriority: high
search.appverid: MET150
description: Microsoft Teams에서 사용할 수 있는 다양한 클라이언트를 PC, Mac 및 모바일 디바이스에 설치하는 방법에 대해 알아 보세요.
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: f53dd50f78afa2d85c4858e2d98170b3dc044f55
ms.sourcegitcommit: 44d9f15f7f7c00b3651a11ff1e8b37dda1716a52
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2022
ms.locfileid: "67732317"
---
# <a name="get-clients-for-microsoft-teams"></a>Microsoft Teams용 클라이언트 다운로드

> [!TIP]
> **PC, Mac 또는 모바일 디바이스에 Teams를 설치하시겠습니까?** [Teams 클라이언트](https://go.microsoft.com/fwlink/?linkid=855754) 설치를 확인하세요.

Microsoft Teams는 PC, Mac 및 모바일 장치에 설치할 수 있으며 웹 브라우저를 통해 액세스할 수도 있습니다. 대부분의 최종 사용자는 직접 [클라이언트를 설치](https://go.microsoft.com/fwlink/?linkid=855754)하여 Teams 사용을 시작할 수 있습니다. Teams 클라이언트를 설치한 후에는 사용자 이름과 암호로 로그인하기만 하면 됩니다.

IT 전문가이고 Teams 설치 환경과 해당 요구 사항에 대해 자세히 알고 싶다면 이 문서에서 클라이언트 운영 체제를 선택하여 자세한 내용을 확인하세요.

서로 다른 플랫폼에서 각 클라이언트의 기능에 대한 자세한 내용은 [플랫폼별 Teams 기능](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)을 참조하세요.

## <a name="desktop-clients"></a>데스크톱 클라이언트

Teams 데스크톱 클라이언트는 다음 운영 체제에서 독립 실행형 애플리케이션과 [엔터프라이즈용 Microsoft 365 앱](/deployoffice/teams-install)의 일부로 사용할 수 있습니다.

- 32비트 및 64비트 버전의 Windows(Windows 10 LTSC를 제외한 8.1 이상) 
- ARM의 Windows 10용 ARM64 
- Windows 서버(2012 R2 이상)
- macOS
- Linux(`.deb` 및 `.rpm` 형식)
- Chrome OS(자세한 내용은 [Chromebook에서 Microsoft Office를 사용하는 방법](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad) 참조)

적합한 로컬 권한을 가지고 있는 경우 최종 사용자는 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)에서 직접 데스크톱 클라이언트를 다운로드하고 설치할 수 있습니다. Windows PC에서는 Teams 클라이언트를 설치하는 데 관리 권한이 필요하지 않지만 Mac에서는 필요합니다.

IT 전문가는 선호하는 방법을 선택하여 조직의 컴퓨터에 설치 파일을 배포할 수 있습니다. 예로는 Microsoft Endpoint Configuration Manager(Windows) 또는 Jamf Pro(macOS) 등이 있습니다. Teams 배포에 대한 자세한 내용은 다음을 참조하세요.

- **Windows** [Endpoint Configuration Manager를 사용하여 Teams 설치](msi-deployment.md)
- **MacOS** [Jamf Pro](https://www.jamf.com/products/jamf-pro/)

> [!NOTE]
> 이러한 메커니즘을 통한 클라이언트 배포는 Teams 클라이언트의 초기 설치에만 해당되며 향후 업데이트에는 적용되지 않습니다. Teams 업데이트 프로세스에 대한 자세한 내용은 [Teams 업데이트 프로세스](teams-client-update.md)를 참조하세요.

### <a name="windows"></a>[Windows](#tab/Windows)

> [!TIP]
> 다음 세션에서 Windows 데스크톱 클라이언트의 장점과 해당 클라이언트를 계획하고 배포하는 방법에 대해 알아보세요. [Teams Windows 데스크톱 클라이언트](https://aka.ms/teams-clients)

Windows의 Teams는 [32비트](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true), [64비트](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true) 및 [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) 아키텍처에서 다운로드 가능한 MSI 설치 프로그램을 제공합니다. Teams의 x86 아키텍처(32비트 및 64비트)는 설치된 Windows 및 Office 아키텍처에 영향을 받지 않습니다. 64비트 시스템에서는 64비트 버전의 Teams를 사용하는 것이 좋습니다.

Teams에는 .NET Framework 4.5 이상이 필요합니다. .NET Framework 이상이 설치되어 있지 않으면 Teams 설치 프로그램이 설치를 제안합니다.

Windows 클라이언트는 사용자 프로필에 있는 AppData 폴더에 배포됩니다. 사용자의 로컬 프로필로 배포하면 강화된 권한 없이 클라이언트를 설치할 수 있습니다. Windows 클라이언트는 다음 위치를 활용합니다.

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

사용자가 Teams 클라이언트를 사용하여 처음으로 호출을 시작하면 사용자에게 통신을 허용하도록 요청하는 Windows 방화벽 설정에 대한 경고가 표시될 수 있습니다. 경고가 해제된 경우에도 호출은 작동하므로 사용자에게 이 메시지를 무시하라는 지시가 있을 수 있습니다.

![Windows 보안 경고 대화 상자의 스크린샷입니다.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> "취소"를 선택하여 메시지를 해제해도 Windows 방화벽 구성이 변경됩니다. TCP 및 UDP 프로토콜에 대한 허용 동작으로 teams.exe에 대한 두 개의 인바운드 규칙이 만들어집니다.

사용자가 Teams에서 처음 호출할 때 Teams에서 사용자에게 방화벽 규칙을 생성하라는 메시지를 표시하지 않도록 하려면 [샘플 스크립트 - Microsoft Teams 방화벽 PowerShell 스크립트](client-firewall-script.md)에서 PowerShell 스크립트를 사용하세요.

### <a name="mac"></a>[Mac](#tab/Mac)

Mac 사용자는 macOS 컴퓨터에 PKG 설치 파일을 사용하여 Teams를 설치할 수 있습니다. Mac 클라이언트를 설치하려면 관리자 액세스가 필요합니다. MacOS 클라이언트가 /Applications 폴더로 설치됩니다.

1. [Teams 다운로드 페이지](https://teams.microsoft.com/downloads)의 **Mac** 에서 **다운로드** 를 클릭합니다.
2. PKG 파일을 두 번 클릭합니다.
3. 설치 마법사에 따라 설치를 완료합니다.
4. Teams가 /Applications 폴더에 설치됩니다. 컴퓨터 전체에 설치됩니다.

> [!NOTE]
> 설치하는 도중 PKG에 관리자 자격 증명이 필요하다는 메시지가 표시됩니다. 사용자가 관리자인지에 상관없이 사용자는 관리자 자격 증명을 입력해야 합니다.

사용자가 현재 DMG 파일을 통해 Teams를 설치한 경우 PKG 파일로 설치하려면 사용자는 다음을 수행해야 합니다.

1. Teams 앱을 종료합니다.
2. Teams 앱을 제거합니다.
3. PKG 파일을 설치합니다.

IT 전문가는 Jamf Pro와 같은 관리 배포 솔루션을 사용하여 조직의 모든 Mac에 Teams 설치 파일을 배포할 수 있습니다.

### <a name="linux"></a>[Linux](#tab/Linux)

Linux에서 `apt`, `yum` 등의 패키지 관리자가 모든 요구 사항을 설치하려고 시도합니다. 하지만 그렇지 않을 경우에는 Linux에 Teams를 설치하기 전에 보고된 모든 요구 사항을 설치해야 합니다.

사용자가 전용 Linux 패키지를 `.deb` 및 `.rpm` 형식으로 설치할 수 있습니다. DEB 또는 RPM 패키지를 설치하면 자동으로 패키지 리포지토리가 설치됩니다.

- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams`

시스템 패키지 관리자를 사용하여 자동 업데이트를 가능하게 하는 서명 키가 자동으로 설치됩니다. 그러나 <https://packages.microsoft.com/keys/microsoft.asc>에서도 찾을 수 있습니다. Teams는 매월 배송되며 리포지토리가 올바르게 설치된 경우 시스템 패키지 관리자는 시스템의 다른 패키지와 동일한 방식으로 자동 업데이트를 처리해야 합니다.

#### <a name="install-teams-using-deb-package"></a>DEB 패키지를 사용하여 Teams 설치

1. <https://aka.ms/getteams>에서 패키지를 다운로드합니다.
2. 다음 중 하나를 사용하여 로그인합니다.
    - 관련 패키지 관리 도구를 열고 셀프 가이드 Linux 앱 설치 프로세스를 진행합니다.
    - 또는 터미널을 좋아하는 경우 다음을 입력합니다. `sudo dpkg -i **teams download file**`

`teams`를 입력하여 터미널 또는 활동을 통해 Teams를 실행할 수 있습니다.

#### <a name="install-teams-using-rpm-package"></a>RPM 패키지를 사용하여 Teams 설치

1. <https://aka.ms/getteams>에서 패키지를 다운로드합니다.
2. 다음 중 하나를 사용하여 로그인합니다.
    - 관련 패키지 관리 도구를 열고 셀프 가이드 Linux 앱 설치 프로세스를 진행합니다.
    - 또는 터미널을 좋아하는 경우 다음을 입력합니다. `sudo yum install **teams download file**`

`teams`를 입력하여 터미널 또는 활동을 통해 Teams를 실행할 수 있습니다.

#### <a name="install-manually-from-the-command-line"></a>명령줄에서 수동으로 설치

Debian 및 Ubuntu 배포에 수동으로 설치:

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor -o /usr/share/keyrings/microsoft-archive-keyring.gpg

sudo sh -c 'echo "deb [arch=amd64 signed-by=/usr/share/keyrings/microsoft-archive-keyring.gpg] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'

sudo apt update
sudo apt install teams
```

RHEL, Fedora 및 CentOS 기반 배포에 수동으로 설치:

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'

sudo dnf check-update
sudo dnf install teams
```

또는 dnf가 아닌 yum을 사용하려면 다음을 수행합니다.

```bash
yum check-update
sudo yum install teams
```

OpenSUSE 기반 배포에 수동으로 설치:

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'

sudo zypper refresh
sudo zypper install teams
```

---

## <a name="mobile-clients"></a>모바일 클라이언트

Teams 모바일 앱은 Android 및 iOS에서 사용할 수 있으며 채팅 기반 대화에 참여하고 P2P 음성 통화를 허용하는 이동 중인 사용자를 위해 설계되었습니다. 모바일 앱의 경우 관련 모바일 스토어 Google Play와 Apple App Store로 이동합니다.

Teams 모바일 앱에 지원되는 모바일 플랫폼은 다음과 같습니다.

- **Android**: 최근 네 개의 주 버전 Android로 지원이 제한됩니다. 신규 주 버전의 Android가 릴리스될 때 새 버전과 이전 세 가지 버전이 공식적으로 지원됩니다.

- **iOS**: 최근 두 개의 주 버전 iOS로 지원이 제한됩니다. 신규 주 버전의 iOS가 릴리스될 때 iOS 새 버전과 이전 버전이 공식적으로 지원 됩니다.

> [!NOTE]
> Teams가 예상대로 작동하도록 하려면 모바일 버전을 공용에서 사용할 수 있어야 합니다.

모바일 앱은 해당 모바일 플랫폼의 앱 스토어를 통해 배포 및 업데이트됩니다. MDM 또는 테스트용 로드를 통한 모바일 앱 배포는 Microsoft에서 지원되지 않습니다. 모바일 앱이 지원되는 모바일 플랫폼에 설치되면 버전이 현재 릴리스의 3개월 이내에 있는 경우 Teams 모바일 앱 자체가 지원됩니다.

중국에 있는 경우 다음 앱 스토어에서 Teams를 설치할 수 있습니다.

- **Xiaomi** <https://aka.ms/TeamsXiaomi>
- **Huawei** <https://aka.ms/TeamsHuawei>
- **Oppo** Oppo 스토어에서 "Teams"를 검색합니다.
- **Baidu** <https://aka.ms/teams_baidu_direct_dl>

> [!NOTE]
> 사용자가 중국 기반 Android 앱 스토어 중 하나에서 Teams를 설치하고 Teams에 푸시 알림을 사용하도록 설정하면 Microsoft는 중국 기반 푸시 알림 서비스를 통해 Teams 푸시 알림을 제공합니다.

## <a name="browser-client"></a>브라우저 클라이언트

브라우저 클라이언트([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753))는 다양한 브라우저에서 사용할 수 있는 완전한 기능의 클라이언트입니다. 브라우저 클라이언트는 webRTC를 사용하여 통화 및 모임을 지원하므로 브라우저에서 Teams를 실행하는 데 플러그인이나 다운로드가 필요하지 않습니다. 브라우저가 타사 쿠키를 허용하도록 구성되어 있어야 합니다.

[!INCLUDE [browser-support](includes/browser-support.md)]

[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)에 연결할 때 브라우저 클라이언트에서 브라우저 버전 검색을 수행합니다. 지원되지 않는 브라우저 버전이 감지되면 브라우저 인터페이스에 대한 액세스를 차단하고 사용자가 데스크톱 클라이언트 또는 모바일 앱을 다운로드하도록 권장합니다.
