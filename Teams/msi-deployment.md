---
title: MSI(Windows Installer)를 사용하여 Teams 대량 설치
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: MSI(Windows Installer) 파일을 사용하여 Teams 클라이언트를 여러 사용자 및 컴퓨터에 배포합니다.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b8c8521aa5e19abe59aa9e4c60fcc41eff9b1c7
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713326"
---
# <a name="bulk-install-teams-using-windows-installer-msi"></a>MSI(Windows Installer)를 사용하여 Teams 대량 설치

> [!Tip]
> Windows 데스크톱 클라이언트의 이점, 계획 방법 및 배포 방법에 대해 알아보려면 다음 세션을 시청하세요. [Teams Windows 데스크톱 클라이언트](https://aka.ms/teams-clients).

Microsoft는 Microsoft Teams를 대량 배포하여 사용자 및 컴퓨터를 선택하는 데 사용할 수 있는 32비트, 64비트 및 ARM64 MSI 파일을 제공합니다. [MSI 파일은 Microsoft Endpoint Configuration Manager](/configmgr/core/understand/introduction), [그룹 정책](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) 또는 타사 배포 소프트웨어와 함께 사용하여 Teams를 조직에 배포할 수 있습니다. 대량 배포는 사용자가 Teams 클라이언트를 수동으로 다운로드하고 설치할 필요가 없기 때문에 유용합니다. 대신 Teams가 컴퓨터에 배포된 다음 사용자가 처음으로 컴퓨터에 로그인할 때 자동으로 시작됩니다.

특정 사용자가 아닌 컴퓨터에 패키지를 배포하는 것이 좋습니다. 컴퓨터를 대상으로 지정하면 해당 컴퓨터의 모든 새 사용자가 이 배포의 이점을 얻을 수 있습니다.

>[!NOTE]
> 엔터프라이즈용 Microsoft 365 앱 일환으로 Teams를 조직에 배포할 수도 있습니다. 자세한 내용은 [엔터프라이즈용 Microsoft 365 앱 사용하여 Microsoft Teams 배포](/deployoffice/teams-install)를 참조하세요.

## <a name="msi-files"></a>MSI 파일

아래 표에서는 Teams용 32비트, 64비트 및 ARM64 MSI 파일에 대한 링크를 제공합니다. 조직의 컴퓨터에 설치하려는 MSI를 다운로드합니다. Teams에서 지원하는 x86 아키텍처(32비트 또는 64비트)는 컴퓨터에 설치된 다른 Office 앱과는 독립적입니다.

64비트 컴퓨터가 있는 경우 컴퓨터가 32비트 버전의 Office를 실행하는 경우에도 64비트 Teams MSI를 설치하는 것이 좋습니다. ARM64 MSI는 Surface Pro X와 같은 ARM 아키텍처를 사용하는 컴퓨터에만 설치할 수 있습니다.

> [!IMPORTANT]
> 64비트 버전의 Teams만 64비트 운영 체제에 설치합니다. 32비트 운영 체제에 64비트 버전의 Teams를 설치하려고 하면 설치에 성공하지 못하며 오류 메시지가 표시되지 않습니다.

|엔터티  |32비트      |64비트      | ARM64 |
|---------|---------|---------|-----------|
|상업     | [32비트](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64비트](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|미국 정부 - GCC     | [32비트](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64비트](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|미국 정부 - GCC High    | [32비트](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64비트](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|미국 정부 - DoD     | [32비트](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64비트](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

## <a name="how-the-microsoft-teams-msi-file-works"></a>Microsoft Teams MSI 파일의 작동 방식

### <a name="pc-installation"></a>PC 설치

Teams MSI는 32비트 Windows 및 `%SystemDrive%\Program Files (x86)\Teams Installer` 64비트 Windows에 설치 관리자 `%SystemDrive%\Program Files\Teams Installer` 를 배치합니다. 사용자가 새 Windows 사용자 프로필에 로그인할 때마다 설치 관리자가 시작되고 Teams 앱의 복사본이 해당 사용자의 `%LocalAppData%\Microsoft\Teams` 폴더에 설치됩니다. 사용자에게 이미 Teams 앱이 폴더에 `%LocalAppData%\Microsoft\Teams` 설치된 경우 MSI 설치 관리자는 해당 사용자에 대한 프로세스를 건너뜁니다.

MSI 파일을 사용하여 업데이트를 배포할 수 없습니다. Teams 클라이언트는 서비스에서 사용할 수 있는 새 버전을 감지하면 자동으로 업데이트됩니다. 최신 설치 관리자를 다시 배포하려면 아래에 설명된 MSI를 다시 배포하는 프로세스를 사용합니다. 이전 버전의 MSI 파일을 배포하는 경우 클라이언트는 가능하면 자동으로 업데이트됩니다(VDI 환경 제외). 아주 오래된 버전이 배포되면 MSI는 사용자가 Teams를 사용하기 전에 앱 업데이트를 트리거합니다.

> [!IMPORTANT]
> 업데이트 흐름을 중단시킬 수 있으므로 기본 설치 위치를 변경하지 않는 것이 좋습니다. 버전이 너무 오래되면 결국 사용자가 서비스에 액세스하지 못하게 됩니다.

#### <a name="target-computer-requirements"></a>대상 컴퓨터 요구 사항

Microsoft Teams의 [하드웨어 요구](hardware-requirements-for-the-teams-app.md) 사항에 나열된 요구 사항을 충족할 때 Teams를 설치하는 컴퓨터가 있는지 확인합니다.

### <a name="vdi-installation"></a>VDI 설치

VDI에서 Teams 데스크톱 앱을 배포하는 방법에 대한 전체 지침은 [가상화된 데스크톱 인프라용 Teams](teams-for-vdi.md)를 참조하세요.

## <a name="clean-up-and-redeployment-procedure"></a>정리 및 재배포 프로시저

사용자가 사용자 프로필에서 Teams를 제거하는 경우 MSI 설치 관리자는 사용자가 Teams 앱을 제거했으며 해당 사용자 프로필에 대한 Teams를 더 이상 설치하지 않는지 추적합니다. 제거된 특정 컴퓨터에서 이 사용자에 대한 Teams를 다시 배포하려면 다음을 수행합니다.

> [!IMPORTANT]
> 다음 단계에는 레지스트리를 수정하는 방법에 대한 정보가 포함되어 있습니다. 레지스트리를 수정하기 전에 백업하고 문제가 발생할 경우 레지스트리를 복원하는 방법을 알고 있는지 확인합니다. 레지스트리를 백업, 복원 및 수정하는 방법에 대한 자세한 내용은 [고급 사용자에 대한 Windows 레지스트리 정보를 참조하세요](https://support.microsoft.com/help/256986).

1. 모든 사용자 프로필에 대해 설치된 Teams 앱을 제거합니다. 자세한 내용은 [Microsoft Teams 제거](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)를 참조하세요.
2. 각 사용자 프로필에 `%LocalAppData%\Microsoft\Teams\` 대해 디렉터리를 재귀적으로 삭제합니다.
3. 각 사용자 프로필에 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 대한 레지스트리 값을 삭제합니다.
4. MSI 파일을 해당 특정 컴퓨터에 다시 배포합니다.

> [!TIP]
> [Teams 배포 정리 스크립트](scripts/powershell-script-deployment-cleanup.md)를 사용하여 1단계와 2단계를 완료할 수도 있습니다.  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>설치 후 Teams가 자동으로 시작되지 않도록 방지

MSI의 기본 동작은 사용자가 로그인하는 즉시 Teams 앱을 설치한 다음 자동으로 Teams를 시작하는 것입니다. Teams를 설치한 후 사용자를 위해 Teams를 자동으로 시작하지 않으려면 그룹 정책 사용하여 정책 설정을 설정하거나 MSI 설치 관리자에 대한 자동 시작을 사용하지 않도록 설정할 수 있습니다.

### <a name="use-group-policy-recommended"></a>그룹 정책 사용(권장)

설치 [그룹 정책](/troubleshoot/windows-server/group-policy/use-group-policy-to-install-software) 설정 **후 Microsoft Teams가 자동으로 시작되지 않도록** 설정합니다. 사용자 **구성**\\ 정책 **관리 템플릿****Microsoft Teams** 에서 이 **정책**\\ 설정을 찾을 수 있습니다\\. 조직의 요구에 따라 정책 설정을 끄거나 켤 수 있으므로 이 방법이 권장됩니다.

Teams를 설치하기 전에 이 정책 설정을 사용하도록 설정하면 사용자가 Windows에 로그인할 때 Teams가 자동으로 시작되지 않습니다. 사용자가 처음으로 Teams에 로그인하면 다음에 사용자가 로그인할 때 Teams가 자동으로 시작됩니다.

자세한 내용은 [그룹 정책 사용하여 설치 후 Teams가 자동으로 시작되지 않도록 합니다](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).

> [!CAUTION]
> Teams를 이미 배포했으며 Teams 자동 시작을 사용하지 않도록 이 정책을 설정하려면 먼저 그룹 정책 설정을 원하는 값으로 설정한 다음 사용자별로 [Teams 자동 시작 재설정 스크립트](scripts/powershell-script-teams-reset-autostart.md)를 실행합니다.

### <a name="disable-auto-launch-for-the-msi-installer"></a>MSI 설치 관리자에 대한 자동 시작 사용 안 함

다음과 같이 매개 변수를 사용하여 `OPTIONS="noAutoStart=true"` MSI 설치 관리자에 대한 자동 시작을 사용하지 않도록 설정할 수 있습니다.  

32비트 버전의 경우:

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

64비트 버전의 경우:

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

사용자가 Windows에 로그인하면 MSI와 함께 Teams가 설치됩니다. 사용자가 수동으로 Teams를 시작할 때까지 Teams가 시작되지 않습니다. 사용자가 수동으로 Teams를 시작하면 사용자가 로그인할 때마다 Teams가 자동으로 시작됩니다.

이러한 예제에서는 **ALLUSERS=1** 매개 변수도 사용합니다. 이 매개 변수를 설정하면 Teams Machine-Wide Installer가 제어판 프로그램 및 기능 및 Windows 설정의 앱 & 기능에 컴퓨터의 모든 사용자에 대해 표시됩니다. 그러면 컴퓨터에 관리자 자격 증명이 있는 경우 모든 사용자가 Teams를 제거할 수 있습니다.

> [!Note]
> MSI를 수동으로 실행하는 경우 관리자 권한으로 실행해야 합니다. 관리자 권한으로 실행하더라도 관리자 권한으로 실행하지 않으면 설치 관리자는 자동 시작을 사용하지 않도록 설정하는 옵션을 구성할 수 없습니다.
