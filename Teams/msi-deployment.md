---
title: Microsoft Endpoint Configuration Manager를 사용하여 Teams 설치
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jhreddy
audience: admin
description: Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Teams를 대량으로 배포하여 사용자 또는 컴퓨터를 선택합니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 23bec0ff2e320da917fbdde122913a56f31b6d1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802328"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager를 사용하여 Microsoft Teams 설치

> [!Tip]
> Windows 데스크톱 클라이언트의 이점, 이를 계획하는 방법 및 배포하는 방법에 대해 알아보는 다음 세션을 [시청합니다. Teams Windows 데스크톱 클라이언트.](https://aka.ms/teams-clients)

Microsoft Endpoint Configuration Manager 또는 그룹 정책 또는 광범위한 배포를 위해 타사 배포 메커니즘을 사용하기 위해 Microsoft는 관리자가 Teams를 대량으로 배포하는 데 사용할 수 있는 MSI 파일(32비트 및 64비트 모두)을 제공하여 사용자 또는 컴퓨터를 선택했습니다. 관리자는 이러한 파일을 사용하여 Teams를 원격으로 배포할 수 있으므로 사용자가 Teams 앱을 수동으로 다운로드할 수 없습니다. 배포되면 해당 머신에 로그인하는 모든 사용자에 대해 Teams가 자동으로 실행됩니다. (앱을 설치한 후 자동 실행을 사용하지 않도록 설정할 수 있습니다. [아래를 참조하세요.)](#disable-auto-launch-for-the-msi-installer) 컴퓨터에 패키지를 배포하는 것이 좋습니다. 따라서 컴퓨터의 모든 새 사용자도 이 배포의 이점을 하게 됩니다.

다음은 MSI 파일에 대한 링크입니다.

|엔터티  |32비트      |64비트      | ARM64 |
|---------|---------|---------|-----------|
|상용     | [32비트](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64비트](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|Federal Government - GCC     | [32비트](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [64비트](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|Federal Government - GCC High    | [32비트](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [64비트](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|연방 정부 - DoD     | [32비트](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [64비트](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [ARM64](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

**성공적인 배포를 보장하기 위해 다음에 유의해야 합니다.**

- 64비트 운영 체제에 64비트 버전의 Teams를 설치합니다. 32비트 운영 체제에 64비트 버전의 Teams를 설치하려고 시도하면 설치에 성공하지 못하며 현재 오류 메시지가 수신되지 않습니다.

- 고객 테넌트가 GCCH 또는 DoD 클라우드에 있는 경우 고객은 **CloudType** 값을 레지스트리의HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams키에 추가하여 레지스트리의 초기 **엔드포인트를** 설정해야 합니다. **CloudType의** 형식은 **DWORD가고** 값은 (0 = Unset, 1 = commercial, 2 = GCC, 3 = GCCH, 4 = DOD)입니다. 레지스트리 키로 엔드포인트를 설정하면 Teams가 Teams와의 로그인 전 연결을 위해 올바른 클라우드 엔드포인트에 연결하도록 제한됩니다.

- Teams는 엔터프라이즈용 Microsoft 365 앱 배포에도 포함될 수 있습니다. 자세한 내용은 [엔터프라이즈용 Microsoft 365 앱을 사용하여 Microsoft Teams 배포를 참조하세요.](https://docs.microsoft.com/deployoffice/teams-install)

- Microsoft Endpoint Configuration Manager에 대한 자세한 내용은 [구성 관리자란?](https://docs.microsoft.com/configmgr/core/understand/introduction)

## <a name="deployment-procedure-recommended"></a>배포 절차(권장)

1. 최신 패키지를 검색합니다.
2. MSI에서 미리 채우는 기본값을 사용 합니다.
3. 가능한 경우 컴퓨터에 배포합니다.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft Teams MSI 패키지의 작동 방식

### <a name="pc-installation"></a>PC 설치

Teams MSI는 프로그램 파일에 설치 관리자를 설치합니다. 사용자가 새 Windows 사용자 프로필에 로그인할 때마다 설치 관리자를 시작하고 Teams 앱의 복사본이 해당 사용자의 폴더에 `AppData` 설치됩니다. 사용자가 폴더에 Teams 앱을 이미 설치한 경우 MSI 설치 관리자에서 해당 사용자에 대한 프로세스를 `AppData` 건너뜁습니다.

클라이언트가 서비스에서 새 버전을 사용할 수 있는 것으로 감지되면 자동으로 업데이트하기 때문에 MSI를 사용하여 업데이트를 배포하지 않습니다. 최신 설치 관리자를 다시 배포하려면 아래에 설명된 MSI를 다시 배포하는 프로세스를 사용하세요. 이전 버전의 MSI 패키지를 배포하는 경우 클라이언트는 가능한 경우(VDI 환경 제외) 자동으로 업데이트합니다. 매우 오래된 버전이 배포되면 사용자가 Teams를 사용하기 전에 MSI에서 앱 업데이트를 트리거합니다.

> [!IMPORTANT]
> 기본 위치는 64비트 운영 체제의 C:\Program Files (x86)\Teams Installer, 32비트 운영 체제의 C:\Program Files\Teams Installer입니다.
> 업데이트 흐름이 중단될 수 있는 경우 기본 설치 위치를 변경하지 않는 것이 좋습니다. 버전이 너무 오래된 경우 결국 사용자가 서비스에 액세스하지 못하게 됩니다.

#### <a name="target-computer-requirements"></a>대상 컴퓨터 요구 사항

- .NET Framework 4.5 이상
- Windows 8.1 이상
- Windows Server 2012 R2 이상
- 각 사용자 프로필에 대해 3GB의 디스크 공간(권장)

### <a name="vdi-installation"></a>VDI 설치

VDI에서 Teams 데스크톱 앱을 배포하는 방법에 대한 전체 지침은 가상화된 데스크톱 인프라용 [Teams를 참조하세요.](teams-for-vdi.md)

## <a name="clean-up-and-redeployment-procedure"></a>정리 및 재배포 절차

사용자가 사용자 프로필에서 Teams를 제거하면 MSI 설치 관리자에서 사용자가 Teams 앱을 제거하고 해당 사용자 프로필에 대해 Teams를 더 이상 설치하지 않은지 추적합니다. 제거된 특정 컴퓨터에서 이 사용자에 대한 Teams를 다시 재배포하려면 다음을 실행합니다.

> [!IMPORTANT]
> 다음 단계에서는 레지스트리를 수정하는 방법에 대한 정보가 포함되어 있습니다. 레지스트리를 수정하기 전에 백업하고 문제가 발생하면 레지스트리를 복원하는 방법을 알고 있는지를 확인해야 합니다. 레지스트리를 백업, 복원 및 수정하는 방법에 대한 자세한 내용은 고급 사용자의 Windows 레지스트리 [정보를 참조하세요.](https://support.microsoft.com/help/256986)

1. 모든 사용자 프로필에 대해 설치된 Teams 앱을 제거합니다. 자세한 내용은 [Microsoft Teams 제거를 참조하세요.](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)
2. .에서 디렉터리를 재발적으로 `%localappdata%\Microsoft\Teams\` 삭제합니다.
3. 레지스트리 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 값을 삭제합니다.
4. MSI 패키지를 해당 특정 컴퓨터에 다시 배포합니다.

> [!TIP]
> Teams 배포 정리 [](scripts/powershell-script-deployment-cleanup.md) 스크립트를 사용하여 1단계와 2단계를 완료할 수도 있습니다.  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a>설치 후 Teams가 자동으로 시작되지 않도록 방지

MSI의 기본 동작은 사용자가 로그인하는 즉시 Teams 앱을 설치한 다음 자동으로 Teams를 시작하는 것입니다. Teams를 설치한 후 사용자를 위해 Teams를 자동으로 시작하지 않도록 하려는 경우 그룹 정책을 사용하여 MSI 설치 관리자에 대한 정책 설정을 설정하거나 자동 실행을 사용하지 않도록 설정할 수 있습니다.

### <a name="use-group-policy-recommended"></a>그룹 정책 사용(권장)

설치 그룹 정책 설정 후 **Microsoft Teams가** 자동으로 시작되지 않도록 합니다. 이 정책 설정은 User Configuration\Policies\Administrative Templates\Microsoft Teams에서 찾을 수 있습니다. 조직의 요구에 따라 정책 설정을 해제하거나 설정할 수 있기 때문에 권장되는 방법입니다.

Teams를 설치하기 전에 이 정책 설정을 사용하도록 설정하면 사용자가 Windows에 로그인할 때 Teams가 자동으로 시작되지 않습니다. 사용자가 Teams에 처음으로 로그인하면 다음에 사용자가 로그인할 때 Teams가 자동으로 시작됩니다.

자세한 내용은 그룹 정책을 사용하여 설치 후 Teams가 자동으로 [시작되지 않도록 합니다.](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)

> [!CAUTION]
> Teams를 이미 배포하고 Teams 자동 시작을 사용하지 않도록 이 정책을 설정하려는 경우 먼저 그룹 정책 설정을 원하는 값으로 설정한 다음 사용자 기준으로 [Teams](scripts/powershell-script-teams-reset-autostart.md) 자동 시작 재설정 스크립트를 실행합니다.

### <a name="disable-auto-launch-for-the-msi-installer"></a>MSI 설치 관리자에 대해 자동 실행 사용 안 하도록 설정

다음과 같이 **OPTIONS="noAutoStart=true"** 매개 변수를 사용하여 MSI 설치 관리자에 대한 자동 실행을 사용하지 않도록 설정할 수 있습니다.  

32비트 버전의 경우:

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

64비트 버전의 경우:

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

사용자가 Windows에 로그인하면 Teams가 MSI와 함께 설치됩니다. Teams를 시작하는 바로 가기가 사용자의 바탕 화면에 추가됩니다. 사용자가 Teams를 수동으로 시작할 때까지 Teams가 시작되지 않습니다. 사용자가 Teams를 수동으로 시작하면 사용자가 로그인할 때마다 Teams가 자동으로 시작됩니다.

이러한 예제에서는 **ALLUSERS=1 매개 변수도** 사용합니다. 이 매개 변수를 설정하면 Teams Machine-Wide 설치 관리자가 제어판의 프로그램 및 기능에 나타나고 앱에는 컴퓨터의 모든 & Windows 설정의 기능이 표시됩니다. 그러면 모든 사용자가 컴퓨터에 관리자 자격 증명이 있는 경우 Teams를 제거합니다.

> [!Note]
> MSI를 수동으로 실행하는 경우 상승된 권한으로 실행해야 합니다. 관리자 권한으로 실행한 경우에도 관리자 권한으로 실행하지 않고도 설치 관리자는 자동 시작을 사용하지 않도록 설정하는 옵션을 구성할 수 없습니다.
