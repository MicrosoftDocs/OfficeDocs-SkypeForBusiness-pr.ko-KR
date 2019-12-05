---
title: Microsoft 팀 용 클라이언트 가져오기
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 사용할 수 있는 다양 한 클라이언트 (웹, 데스크톱 (Windows 및 Mac) 및 모바일 (Android 및 iOS)를 사용 하는 방법에 대해 알아봅니다.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 993b01e1ba362b6990c65f067ff2d63d921a1916
ms.sourcegitcommit: 9d5a83dcb3d86f37cd7714ca92b197696681748b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831601"
---
# <a name="get-clients-for-microsoft-teams"></a>Microsoft 팀 용 클라이언트 가져오기 


Microsoft 팀은 데스크톱 (Windows, Mac, Linux), 웹, 모바일 (Android 및 iOS)에 사용할 수 있는 클라이언트가 있습니다. 이러한 클라이언트는 모두 활성 인터넷 연결이 필요 하며 오프 라인 모드를 지원 하지 않습니다.

> [!NOTE]
> 2018 년 11 월 29 일부 터 Microsoft Store에서 제공 되는 Windows 10 S 용 Microsoft 팀 (Preview) 앱을 더 이상 사용할 수 없게 됩니다. 대신 Windows 10 S 모드를 실행 하는 장치에 팀 데스크톱 클라이언트를 다운로드 하 여 설치할 수 있습니다. 데스크톱 클라이언트를 다운로드 하려면으로 이동 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)합니다. Windows 10 S 모드를 실행 하는 장치에서 팀 데스크톱 클라이언트의 MSI 빌드를 아직 사용할 수 없습니다.
>
> Windows 10 S 모드에 대 한 자세한 내용은 [S 모드에서 Windows 10 소개](https://www.microsoft.com/windows/s-mode)를 참조 하세요. 

## <a name="desktop-client"></a>데스크톱 클라이언트

> [!TIP]
> Windows 데스크톱 클라이언트의 이점과이를 위해 계획 하는 방법 및 배포 하는 방법에 대 한 자세한 내용을 보려면 다음 세션을 시청 하세요. [팀 Windows 데스크톱 클라이언트](https://aka.ms/teams-clients)

Microsoft 팀 데스크톱 클라이언트는 독립 실행형 응용 프로그램이 며 [Office 365 ProPlus 에서도 사용할 수 있습니다](https://docs.microsoft.com/deployoffice/teams-install). 팀은 Windows (7 +), 32 비트 및 64 비트 버전, macOS (10.10 +), Linux (in `.deb` 및 `.rpm` formats)에서 사용할 수 있습니다. Windows에서 팀에는 .NET Framework 4.5 이상이 필요 합니다. 팀 설치 관리자가 없는 경우 설치를 제공 합니다. Linux에서 apt 및 yum과 같은 패키지 관리자는 모든 요구 사항을 설치 하려고 합니다. 그러나이 경우에는 Linux에 팀을 설치 하기 전에 보고 된 요구 사항을 설치 해야 합니다.

데스크톱 클라이언트는 실시간 통신 지원 (오디오, 비디오 및 콘텐츠 공유)을 제공 하 여 팀 모임, 그룹 통화, 개인 일대일 통화를 가능 하 게 합니다.

데스크톱 클라이언트는 최종 사용자가 적절 한 로컬 권한을 갖고 있는 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) 경우 직접 다운로드 및 설치할 수 있습니다 (관리자 권한은 PC에 팀 클라이언트를 설치 하는 데는 필요 하지 않지만 Mac에는 필요 하지 않음).

IT 관리자는 조직의 컴퓨터에 설치 파일을 배포 하는 데 선호 하는 방법을 선택할 수 있습니다. 몇 가지 예로는 System Center Configuration Manager (Windows) 또는 Jamf Pro (macOS)이 있습니다. Windows 배포용 MSI 패키지를 가져오려면 [msi를 사용 하 여 Microsoft 팀 설치](msi-deployment.md)를 참조 하세요.  

> [!NOTE]
> 이러한 메커니즘을 통해 클라이언트를 배포 하는 것은 향후 업데이트에 대 한 것이 아니라 Microsoft 팀 클라이언트의 초기 설치에만 해당 됩니다.

### <a name="windows"></a>창을

Windows 용 Microsoft 팀 설치는 32 비트 및 64 비트 아키텍처에서 다운로드 가능한 설치 관리자를 제공 합니다.

> [!NOTE]
> Microsoft 팀의 아키텍처 (32 비트 대 64 비트)는 설치 되어 있는 Windows 및 Office의 아키텍처와 관계가 없습니다.

Windows 클라이언트는 사용자 프로필에 있는 AppData 폴더에 배포 됩니다. 사용자의 로컬 프로필에 배포 하면 관리자 권한이 필요 하지 않고 클라이언트가 설치 될 수 있습니다. Windows 클라이언트는 다음 위치를 활용 합니다.

- % LocalAppData%\\Microsoft\\팀

- % LocalAppData%\\Microsoft\\TeamsMeetingAddin

- % AppData%\\Microsoft\\팀

- % LocalAppData%\\SquirrelTemp

사용자가 처음 Microsoft 팀 클라이언트를 사용 하 여 전화를 시작 하면 사용자에 게 통신을 허용 하도록 요청 하는 Windows 방화벽 설정에 대 한 경고가 표시 될 수 있습니다. 경고가 해제 된 경우에도 호출이 작동 하기 때문에 사용자가이 메시지를 무시 하도록 지시할 수 있습니다.

![Windows 보안 알림 대화 상자 스크린샷.](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> Windows 방화벽 구성은 "취소"를 선택 하 여 메시지가 해제 되는 경우에도 변경 됩니다. TCP 및 UDP 프로토콜에 대 한 Block 동작을 사용 하 여 cluster.exe에 대 한 두 개의 인바운드 규칙이 생성 됩니다.

### <a name="mac"></a>Ac

Mac 사용자는 macOS 컴퓨터에 INSTALLER.PKG 설치 파일을 사용 하 여 팀을 설치할 수 있습니다. Mac 클라이언트를 설치 하려면 관리자 권한이 필요 합니다. MacOS 클라이언트는/Applications 폴더에 설치 됩니다.

#### <a name="install-teams-by-using-the-pkg-file"></a>INSTALLER.PKG 파일을 사용 하 여 팀 설치

1. [팀 다운로드 페이지](https://teams.microsoft.com/downloads)의 **Mac**에서 **다운로드**를 클릭 합니다.
2. INSTALLER.PKG 파일을 두 번 클릭 합니다.
3. 설치 마법사의 지시에 따라 설치를 완료 합니다.
4. 팀이/Applications 폴더에 설치 됩니다. 시스템 전체에 설치 하는 것입니다.

> [!NOTE]
> 설치 하는 동안 INSTALLER.PKG에서 관리자 자격 증명을 묻는 메시지가 표시 됩니다. 사용자가 관리자 인지 여부에 관계 없이 관리자 자격 증명을 입력 해야 합니다.

사용자가 현재 팀의 DMG 설치를 보유 하 고 INSTALLER.PKG 설치로 대체 하려는 경우 다음을 수행 해야 합니다.

1. 팀 앱을 종료 합니다.
2. 팀 앱을 제거 합니다.
3. INSTALLER.PKG 파일을 설치 합니다.

IT 관리자는 팀의 관리 되는 배포를 사용 하 여 Jamf Pro와 같은 조직의 모든 Mac에 설치 파일을 배포할 수 있습니다.

> [!NOTE]
> INSTALLER.PKG를 설치 하는 중 문제가 발생 하면 알려주세요. 이 문서의 끝부분에 있는 **피드백** 섹션에서 **제품 피드백**을 클릭 합니다.

### <a name="linux"></a>Linux

사용자는 및 `.deb` `.rpm` 형식으로 네이티브 Linux 패키지를 설치할 수 있습니다.
DEB 또는 RPM 패키지를 설치 하면 패키지 리포지토리가 자동으로 설치 됩니다.
- DEB 다운로드`https://packages.microsoft.com/repos/ms-teams stable main`
- RPM`https://packages.microsoft.com/yumrepos/ms-teams` 

시스템의 패키지 관리자를 사용 하 여 자동 업데이트를 사용 하도록 설정 하는 서명 키가 자동으로 설치 됩니다. 그러나 다음https://packages.microsoft.com/keys/microsoft.asc)위치에서 찾을 수도 있습니다. Microsoft 팀은 매달 제공 되 고 리포지토리가 올바르게 설치 된 경우 시스템의 다른 패키지와 같은 방식으로 시스템 패키지 관리자가 자동 업데이트를 처리 해야 합니다.

> [!NOTE] 
> Linux 클라이언트의 팀은 제한 된 미리 보기에서 사용할 수 있습니다. 클라이언트 내에서 `Report a Problem` 를 사용 하 여 버그를 제출 합니다. 알려진 문제는 [알려진 문제점](Known-issues.md)을 참조 하세요.

#### <a name="install-teams-using-deb-package"></a>DEB 패키지를 사용 하 여 팀 설치

1. 에서 https://aka.ms/getteams패키지를 다운로드 합니다. (Linux 클라이언트는 제한 된 미리 보기 상태 이며 곧 시작 됩니다. 다운로드 페이지에 Linux 클라이언트가 표시 되지 않으면 아직 시작 되지 않은 것입니다.
2. 다음 중 하나를 사용 하 여 설치 합니다.  
    - 관련 패키지 관리 도구를 열고 셀프 기반 Linux 앱 설치 프로세스를 진행 합니다.
    - 또는 터미널을 선호 하는 경우 다음을 입력 합니다.`sudo apt install **teams download file**`

를 입력 `Teams`하 여 작업을 통해서나 터미널을 통해 팀을 시작할 수 있습니다. 

#### <a name="install-teams-using-rpm-package"></a>RPM 패키지를 사용 하 여 팀 설치

1. 에서 https://aka.ms/getteams패키지를 다운로드 합니다. (Linux 클라이언트는 제한 된 미리 보기 상태 이며 곧 시작 됩니다. 다운로드 페이지에 Linux 클라이언트가 표시 되지 않으면 아직 시작 되지 않은 것입니다.
2. 다음 중 하나를 사용 하 여 설치 합니다.
    - 관련 패키지 관리 도구를 열고 셀프 기반 Linux 앱 설치 프로세스를 진행 합니다.
    - 또는 터미널을 선호 하는 경우 다음을 입력 합니다.`sudo yum install **teams download file**`

를 입력 `Teams`하 여 작업을 통해서나 터미널을 통해 팀을 시작할 수 있습니다.

## <a name="web-client"></a>웹 클라이언트 

웹 클라이언트 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753))는 다양 한 브라우저에서 사용할 수 있는 완전 한 기능적 클라이언트입니다. 웹 클라이언트는 webRTC를 사용 하 여 통화 및 모임을 지원 하므로 웹 브라우저에서 팀을 실행 하는 데 필요한 플러그 인 또는 다운로드가 필요 하지 않습니다. 타사 쿠키를 허용 하도록 브라우저를 구성 해야 합니다. 

[!INCLUDE [browser-support](includes/browser-support.md)]

웹 클라이언트는 연결 시 브라우저 버전 검색을 [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)수행 합니다. 지원 되지 않는 브라우저 버전이 발견 되 면 웹 인터페이스에 대 한 액세스를 차단 하 고 사용자가 데스크톱 클라이언트 또는 모바일 앱을 다운로드 하는 것이 좋습니다.

## <a name="mobile-clients"></a>모바일 클라이언트

Microsoft 팀 모바일 앱은 Android 및 iOS에서 사용할 수 있으며 채팅 기반 대화에 참여 하는 사용자에 게 전달 되며 피어 투 피어 오디오 통화를 허용 합니다. 모바일 앱의 경우 관련 모바일 스토어 Google Play 및 Apple App Store로 이동 합니다. Windows Phone 앱은 2018 년 7 월 20 일에 만료 되었으며 더 이상 작동 하지 않을 수 있습니다. 

Microsoft 팀을 위한 지원 되는 모바일 플랫폼 모바일 앱은 다음과 같습니다.

-   **Android**: 5.0 이상

-   **iOS**: 10.0 이상

> [!NOTE]
> 팀이 예상 대로 작동 하도록 하려면 모바일 버전을 공용에서 사용할 수 있어야 합니다.

모바일 앱은 해당 모바일 플랫폼의 앱 스토어를 통해 배포 되 고 업데이트 됩니다. MDM 또는 사이드 로딩을 통해 모바일 앱을 배포 하는 것은 Microsoft에서 지원 되지 않습니다. 모바일 앱이 지원 되는 모바일 플랫폼에 설치 된 후에는 버전이 현재 릴리스의 3 개월 이내에 제공 되는 경우 팀 모바일 앱이 지원 됩니다.


| | | |
|---------|---------|---------|
|![결정 지점을 가리키는 아이콘](media/Get_clients_for_Microsoft_Teams_image4.png)      |판단 요점         |사용자가 장치에 적절 한 Microsoft 팀 클라이언트를 설치 하는 것을 막는 제한 사항이 있나요?         |
|![다음 단계를 묘사하는 아이콘](media/Get_clients_for_Microsoft_Teams_image5.png)     |다음 단계         |조직이 소프트웨어 설치를 제한 하는 경우 해당 프로세스가 Microsoft 팀과 호환 되는지 확인 합니다. 참고: PC 클라이언트 설치에는 관리자 권한이 필요 하지 않지만 Mac에 설치 하는 데는 필요 합니다.         |

## <a name="client-update-management"></a>클라이언트 업데이트 관리

클라이언트가 현재 Microsoft 팀 서비스에 의해 자동으로 업데이트 되므로 IT 관리자의 개입 없이도 필요 합니다. 업데이트를 사용할 수 있는 경우 클라이언트는 업데이트를 자동으로 다운로드 하 고 앱에 특정 기간 동안 idled가 있는 경우 업데이트 프로세스가 시작 됩니다.

## <a name="client-side-configurations"></a>클라이언트측 구성

현재 테 넌 트 관리자, PowerShell, 그룹 정책 개체 또는 레지스트리를 통해 클라이언트를 구성 하는 데 사용할 수 있는 지원 되는 옵션이 없습니다.

## <a name="notification-settings"></a>알림 설정

현재 IT 관리자가 클라이언트 쪽 알림 설정을 구성할 수 있는 옵션이 없습니다. 모든 알림 옵션은 사용자가 설정 합니다. 아래 그림에서는 기본 클라이언트 설정을 간략하게 보여 줍니다.

![알림 설정 스크린샷.](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a>샘플 PowerShell 스크립트

관리자 권한 administrator 계정의 컨텍스트에서 클라이언트 컴퓨터에 실행 해야 하는이 예제 스크립트는 c:\users.에 있는 각 사용자 폴더에 대 한 새 인바운드 방화벽 규칙을 만듭니다. 팀에서이 규칙을 발견 하면 팀 응용 프로그램에서 사용자가 팀 으로부터 처음 통화를 할 때 방화벽 규칙을 만들지 못하게 됩니다. 

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
