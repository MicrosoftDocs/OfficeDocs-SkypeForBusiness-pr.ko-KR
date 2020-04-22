---
title: Microsoft Teams용 클라이언트 다운로드
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: 웹, 데스크톱(Windows 및 Mac), 모바일(Android 및 iOS)을 비롯하여 Microsoft Teams에서 사용할 수 있는 다양한 클라이언트를 사용하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a3425ca19ded72f814e8f81252b7224c2c08a42
ms.sourcegitcommit: 48f64fa38509cf7141b944cd3da60409ec51860b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43749496"
---
# <a name="get-clients-for-microsoft-teams"></a>Microsoft Teams용 클라이언트 다운로드 


Microsoft Teams에는 데스크톱(Windows, Mac, Linux), 웹, 모바일(Android 및 iOS)에서 사용할 수 있는 클라이언트가 있습니다. 이 클라이언트에는 모두 활성 인터넷 연결이 필요하며 오프라인 모드를 지원하지 않습니다.

> [!NOTE]
> 2018년 11월 29일부터 더 이상 Microsoft Store에서 제공하는 Windows 10 S(미리 보기)용 Microsoft Teams 앱을 사용할 수 없습니다. 대신 이제는 Windows 10 S 모드를 실행하는 장치에 Teams 데스크톱 클라이언트를 다운로드하고 설치할 수 있습니다. 데스크톱 클라이언트를 다운로드하려면 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)로 이동합니다. Teams 데스크톱 클라이언트의 MSI 빌드는 아직 Windows 10 S 모드를 실행하는 장치에서 사용할 수 없습니다.
>
> Windows 10 S 모드에 대한 자세한 내용은 [Windows 10 S 모드 소개](https://www.microsoft.com/windows/s-mode)를 참조하세요. 

## <a name="desktop-client"></a>데스크톱 클라이언트

> [!TIP]
> 다음 세션에서 Windows 데스크톱 클라이언트의 장점과 해당 클라이언트를 계획하고 배포하는 방법에 대해 알아보세요. [Teams Windows 데스크톱 클라이언트](https://aka.ms/teams-clients)

Microsoft Teams 데스크톱 클라이언트는 독립 실행형 응용 프로그램이며 [Office 365 ProPlus에서도 사용](https://docs.microsoft.com/deployoffice/teams-install)할 수 있습니다. Teams는 Windows(8.1 이상)와 Windows Server(2012 R2 이상)의 32비트 및 64비트 버전뿐 아니라 macOS(10.10 이상) 및 Linux(`.deb` 및 `.rpm` 형식)에서도 사용할 수 있습니다. Windows에서 Teams는 .NET Framework 4.5 이상이 필요하며, 설치되어 있지 않으면 Teams 설치 관리자가 설치를 제안합니다. Linux에서 `apt`, `yum` 등의 패키지 관리자가 모든 요구 사항을 설치하려고 시도합니다. 하지만 그렇지 않을 경우에는 Linux에 Teams를 설치하기 전에 보고된 모든 요구 사항을 설치해야 합니다.

데스크톱 클라이언트는 팀 모임, 그룹 통화 및 비공개 일대일 통화를 위한 실시간 통신 지원(오디오, 비디오, 콘텐츠 공유)을 제공합니다.

사용자가 적합한 로컬 권한(PC에서 Teams 클라이언트를 설치하는 데 관리 권한은 필요하지 않지만 Mac에서는 필요함)을 가지고 있는 경우 최종 사용자는 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)에서 직접 데스크톱 클라이언트를 다운로드하고 설치할 수 있습니다.

> [!NOTE]
> Chromebook에 팀을 설치 하는 방법에 대 한 자세한 내용은 [Chromebook에서 Microsoft Office를 설치 하 고 실행 하는 방법을](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)참조 하세요.

IT 관리자는 조직의 컴퓨터에 설치 파일을 배포하기 위해 원하는 방법을 선택할 수 있습니다. 예로는 Microsoft Endpoint Configuration Manager(Windows) 또는 Jamf Pro(macOS) 등이 있습니다. Windows 배포용 MSI 패키지를 다운로드하려면 [MSI를 사용하여 Microsoft Teams 설치](msi-deployment.md)를 참조하세요.  

> [!NOTE]
> 이러한 메커니즘을 통한 클라이언트 배포는 Microsoft Teams 클라이언트를 초기에 설치하는 경우에만 사용할 수 있으며 추후 업데이트에는 사용할 수 없습니다.

### <a name="windows"></a>Windows

Windows용 Microsoft Teams 설치에서는 다운로드 가능한 설치 관리자를 32비트 및 64비트 아키텍처로 제공합니다.

> [!NOTE]
> Microsoft Teams의 아키텍처(32비트와 64비트)는 설치되는 Windows 및 Office 아키텍처와 관계없이 작동합니다.

Windows 클라이언트는 사용자 프로필에 있는 AppData 폴더에 배포됩니다. 사용자의 로컬 프로필로 배포하면 강화된 권한 없이 클라이언트를 설치할 수 있습니다. Windows 클라이언트는 다음 위치를 활용합니다.

- %LocalAppData%\\Microsoft\\Teams

- %LocalAppData%\\Microsoft\\TeamsMeetingAddin

- %AppData%\\Microsoft\\Teams

- %LocalAppData%\\SquirrelTemp

사용자가 처음 Microsoft Teams 클라이언트를 사용하여 통화를 시작하면 사용자에게 통신을 허용하도록 요청하는 Windows 방화벽 설정에 대한 경고가 표시될 수 있습니다. 경고가 해제된 경우에도 호출은 작동하므로 사용자에게 이 메시지를 무시하라는 지시가 있을 수 있습니다.

![Windows 보안 경고 대화 상자의 스크린샷입니다.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> "취소"를 선택하여 메시지를 해제해도 Windows 방화벽 구성이 변경됩니다. TCP 및 UDP 프로토콜에 대한 차단 동작으로 teams.exe에 대한 두 개의 인바운드 규칙이 만들어집니다.

사용자가 팀에서 첫 번째 통화를 할 때 팀에서 방화벽 규칙을 만들지 못하게 하려면 아래 [샘플 PowerShell 스크립트-인바운드 방화벽 규칙](#sample-powershell-script---inbound-firewall-rule) 을 사용 합니다. 

### <a name="mac"></a>Mac

Mac 사용자는 macOS 컴퓨터에 PKG 설치 파일을 사용하여 Teams를 설치할 수 있습니다. Mac 클라이언트를 설치하려면 관리자 액세스가 필요합니다. MacOS 클라이언트가 /Applications 폴더로 설치됩니다.

#### <a name="install-teams-by-using-the-pkg-file"></a>PKG 파일을 사용하여 Teams 설치

1. [Teams 다운로드 페이지](https://teams.microsoft.com/downloads)의 **Mac**에서 **다운로드**를 클릭합니다.
2. PKG 파일을 두 번 클릭합니다.
3. 설치 마법사에 따라 설치를 완료합니다.
4. Teams가 /Applications 폴더에 설치됩니다. 컴퓨터 전체에 설치됩니다.

> [!NOTE]
> 설치하는 도중 PKG에 관리자 자격 증명이 필요하다는 메시지가 표시됩니다. 사용자가 관리자인지에 상관없이 사용자는 관리자 자격 증명을 입력해야 합니다.

사용자가 현재 DMG 파일을 통해 Teams를 설치한 경우 PKG 파일로 설치하려면 사용자는 다음을 수행해야 합니다.

1. Teams 앱을 종료합니다.
2. Teams 앱을 제거합니다.
3. PKG 파일을 설치합니다.

IT 관리자는 Teams의 관리 배포를 사용하여 설치 파일을 조직의 모든 Macs(예: Jamf Pro)에 배포할 수 있습니다.

> [!NOTE]
> PKG 설치에 문제가 발생한 경우 의견을 보내주세요. 이 문서의 끝에 있는 **피드백** 섹션에서 **제품 피드백**을 클릭합니다.

### <a name="linux"></a>Linux

사용자가 전용 Linux 패키지를 `.deb` 및 `.rpm` 형식으로 설치할 수 있습니다.
DEB 또는 RPM 패키지를 설치 하면 패키지 리포지토리가 자동으로 설치 됩니다.
- DEB `https://packages.microsoft.com/repos/ms-teams stable main`
- RPM `https://packages.microsoft.com/yumrepos/ms-teams` 

시스템 패키지 관리자를 사용하여 자동 업데이트를 가능하게 하는 서명 키가 자동으로 설치됩니다. 그러나 (https://packages.microsoft.com/keys/microsoft.asc)에서도 찾을 수 있습니다. Microsoft Teams는 매달 출하되며 리포지토리가 제대로 설치되면 시스템 패키지 관리자는 시스템의 다른 패키지와 같은 방식으로 자동 업데이트를 처리해야 합니다.

> [!NOTE] 
> 버그를 찾았으면 클라이언트에서 `Report a Problem`를 사용하여 제출합니다. 알려진 문제는 [알려진 문제](Known-issues.md)를 참조하세요.
> Linux용 Teams 지원의 경우 [Microsoft Q&A의 Linux 포럼 지원 채널](https://docs.microsoft.com/answers/topics/teams.html)을 사용할 수 있습니다. 질문을 게시하려면 `teams-linux` 태그를 사용하세요. 

#### <a name="install-teams-using-deb-package"></a>DEB 패키지를 사용하여 Teams 설치

1. https://aka.ms/getteams에서 패키지를 다운로드합니다.
2. 다음 중 하나를 사용하여 로그인합니다.  
    - 관련 패키지 관리 도구를 열고 셀프 가이드 Linux 앱 설치 프로세스를 진행합니다.
    - 또는 터미널을 좋아하는 경우 다음을 입력합니다. `sudo apt install **teams download file**`

`Teams`를 입력하여 터미널 또는 활동을 통해 Teams를 실행할 수 있습니다. 

#### <a name="install-teams-using-rpm-package"></a>RPM 패키지를 사용하여 Teams 설치

1. https://aka.ms/getteams에서 패키지를 다운로드합니다.
2. 다음 중 하나를 사용하여 로그인합니다.
    - 관련 패키지 관리 도구를 열고 셀프 가이드 Linux 앱 설치 프로세스를 진행합니다.
    - 또는 터미널을 좋아하는 경우 다음을 입력합니다. `sudo yum install **teams download file**`

`Teams`를 입력하여 터미널 또는 활동을 통해 Teams를 실행할 수 있습니다.

#### <a name="install-manually-from-the-command-line"></a>명령줄에서 수동으로 설치

Debian 및 Ubuntu 배포에 수동으로 설치:
```
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
 
sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'
 
sudo apt update
sudo apt install teams
```

RHEL, Fedora 및 CentOS 기반 배포에 수동으로 설치:
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'
 
sudo dnf check-update
sudo dnf install teams
```

또는 dnf가 아닌 yum을 사용하려면 다음을 수행합니다.
```
yum check-update
sudo yum install teams
```

OpenSUSE 기반 배포에 수동으로 설치:
```
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
 
sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'
 
sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a>웹 클라이언트 

웹 클라이언트([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753))는 다양한 브라우저에서 사용할 수 있는 완전한 기능을 갖춘 클라이언트입니다. 웹 클라이언트에서는 webRTC를 사용하여 통화와 모임을 지원하므로 웹 브라우저에서 Teams를 실행할 플러그인 또는 다운로드가 필요하지 않습니다. 브라우저가 타사 쿠키를 허용하도록 구성되어 있어야 합니다. 

[!INCLUDE [browser-support](includes/browser-support.md)]

웹 클라이언트는 [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)에 연결되면 브라우저 버전 탐색을 수행합니다. 지원되지 않는 브라우저 버전이 검색되면 웹 인터페이스에 대한 액세스를 차단하고 사용자가 데스크톱 클라이언트 또는 모바일 앱을 다운로드하도록 권장합니다.

## <a name="mobile-clients"></a>모바일 클라이언트

Microsoft Teams 모바일 앱은 Android 및 iOS에서 사용할 수 있고 이동하면서 채팅 기반 대화에 참여하는 사용자에게 적합하며 피어-투-피어 오디오 통화를 허용합니다. 모바일 앱의 경우 관련 모바일 스토어 Google Play와 Apple App Store로 이동합니다. Windows Phone 앱은 2018년 7월 20일에 종료되었으며 더 이상 작동하지 않을 수 있습니다. 

중국에서 [Android용 Teams](get-teams-android-in-china.md)를 다운로드하는 방법에 대해 알아봅니다. 

Microsoft Teams 모바일 앱에 지원되는 모바일 플랫폼은 다음과 같습니다.

-   **Android**: 최근 네 개의 주 버전 Android로 지원이 제한됩니다. 신규 주 버전의 Android가 릴리스될 때 새 버전과 이전 세 가지 버전이 공식적으로 지원됩니다.

-   **iOS**: 최근 두 개의 주 버전 iOS로 지원이 제한됩니다. 신규 주 버전의 iOS가 릴리스될 때 iOS 새 버전과 이전 버전이 공식적으로 지원 됩니다.

> [!NOTE]
> Teams가 예상대로 작동하도록 하려면 모바일 버전을 공용에서 사용할 수 있어야 합니다.

모바일 앱은 해당 모바일 플랫폼의 앱 스토어를 통해 배포 및 업데이트됩니다. MDM 또는 테스트용 로드를 통한 모바일 앱 배포는 Microsoft에서 지원되지 않습니다. 모바일 앱이 지원되는 모바일 플랫폼에 설치되면 버전이 현재 릴리스의 3개월 이내에 있는 경우 Teams 모바일 앱 자체가 지원됩니다.


| | | |
|---------|---------|---------|
|![의사 결정 지점을 묘사하는 아이콘](media/Get_clients_for_Microsoft_Teams_image4.png)      |의사 결정 지점         |사용자가 장치에서 적합한 Microsoft Teams 클라이언트를 설치하지 못하도록 하는 제한이 있나요?         |
|![다음 단계를 묘사하는 아이콘](media/Get_clients_for_Microsoft_Teams_image5.png)     |다음 단계         |조직이 소프트웨어 설치를 제한하는 경우 프로세스가 Microsoft Teams와 호환되는지 확인합니다. 메모: PC 클라이언트 설치에는 관리자 권한이 필요하지 않지만 Mac 설치에는 필요합니다.         |

## <a name="client-update-management"></a>클라이언트 업데이트 관리

현재 클라이언트는 IT 관리자의 개입 없이도 Microsoft Teams 서비스에서 자동으로 업데이트됩니다. 업데이트를 사용할 수 있는 경우 앱이 일정 기간 유휴 상태였으면 클라이언트가 자동으로 업데이트를 다운로드하고 업데이트 프로세스가 시작됩니다.

## <a name="client-side-configurations"></a>클라이언트 쪽 구성

현재 테넌트 관리, PowerShell, 그룹 정책 객체 또는 레지스트리를 통해 클라이언트를 구성할 수 있는 옵션이 지원되지 않습니다.

## <a name="notification-settings"></a>알림 설정

현재 IT 관리자가 클라이언트 쪽 알림 설정을 구성할 수 있는 옵션이 없습니다. 모든 알림 옵션은 사용자가 설정합니다. 아래 그림에서는 기본 클라이언트 설정을 간략하게 설명합니다.

![알림 설정의 스크린샷입니다.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a>샘플 PowerShell 스크립트-인바운드 방화벽 규칙

강화된 관리자 계정 컨텍스트로 클라이언트 컴퓨터에서 실행해야 하는 이 예제 스크립트는 c:\users에 있는 각 사용자 폴더에 새 인바운드 방화벽 규칙을 만듭니다. Teams에서 이 규칙을 찾으면 Teams 응용 프로그램이 사용자가 Teams에서 처음 통화를 할 때 방화벽 규칙을 만들라는 메시지를 표시하지 못하도록 합니다. 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
