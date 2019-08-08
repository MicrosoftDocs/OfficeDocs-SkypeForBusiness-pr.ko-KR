---
title: SCCM을 통해 MSI를 사용 하 여 Microsoft 팀 설치
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 관리자는 팀 MSI를 사용 하 여 Microsoft 팀을 대량 배포 하 여 사용자 또는 컴퓨터를 선택할 수 있습니다.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6e2354c28916af3c1c0be47848ee7bd2a72bf278
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239244"
---
<a name="install-microsoft-teams-using-msi"></a>MSI를 사용 하 여 Microsoft 팀 설치
=================================

> [!Tip]
> Windows 데스크톱 클라이언트의 이점,이를 위해 계획 하는 방법 및 배포 하는 방법에 대해 알아보려면 다음 세션을 시청 하세요. [팀 Windows 데스크톱 클라이언트](https://aka.ms/teams-clients)

System Center Configuration Manager 또는 그룹 정책 또는 광범위 한 배포에 대 한 타사 배포 메커니즘을 사용 하기 위해 Microsoft는 관리자가 선택 하도록 팀을 대량으로 배포 하는 데 사용할 수 있는 MSI 파일 ( [32 비트](https://aka.ms/teams32bitmsi) 및 [64 비트](https://aka.ms/teams64bitmsi))을 제공 했습니다. 사용자 또는 컴퓨터. 관리자는 이러한 파일을 사용 하 여 사용자가 팀 앱을 수동으로 다운로드할 필요가 없도록 팀을 원격으로 배포할 수 있습니다. 배포 되는 경우 해당 컴퓨터에 로그인 하는 모든 사용자에 대해 팀이 자동으로 실행 됩니다. (앱을 설치한 후 자동 시작을 사용 하지 않도록 설정할 수 있습니다. [아래를 참조](#disable-auto-launch-for-the-msi-installer)하세요.) 컴퓨터에 패키지를 배포 하는 것이 좋으며,이는 컴퓨터의 모든 새 사용자도이 배포를 활용할 수 있도록 하는 것이 좋습니다. 

팀은 Office 365 ProPlus 배포에도 포함 될 수 있습니다. 자세한 내용은 [Office 365 ProPlus를 사용 하 여 Microsoft 팀 배포](https://docs.microsoft.com/deployoffice/teams-install)를 참조 하세요.
 
> [!Note] 
> SCCM에 대해 자세히 알아보려면 [System Center Configuration Manager 소개](https://docs.microsoft.com/sccm/core/understand/introduction)를 참조 하세요.

## <a name="deployment-procedure-recommended"></a>배포 절차 (권장)
1. 최신 패키지를 검색 합니다.
2. MSI에서 미리 채워 온 기본값을 사용 합니다.
3. 가능 하면 컴퓨터에 배포 합니다.

## <a name="how-the-microsoft-teams-msi-package-works"></a>Microsoft 팀 MSI 패키지가 작동 하는 방식

### <a name="pc-installation"></a>PC 설치

> [!Note] 
> Vdi (가상 데스크톱 인프라) 환경에 팀을 배포 하는 방법에 대 한 지침은 [vdi 설치](#vdi-installation) 를 참조 하세요.

팀 MSI는 프로그램 파일에 설치 관리자를 배치 합니다. 사용자가 새 Windows 사용자 프로필에 로그인 할 때마다 설치 프로그램이 시작 되 고 팀 앱의 복사본이 해당 사용자의 appdata 폴더에 설치 됩니다. Appdata 폴더에 팀 앱이 이미 설치 되어 있는 경우 MSI 설치 관리자가 해당 사용자에 대 한 프로세스를 건너뜁니다.

MSI를 사용 하 여 업데이트를 배포 하는 경우 클라이언트는 서비스에서 새 버전이 제공 될 때 자동으로 업데이트 됩니다. 최신 설치 관리자를 다시 배포 하려면 아래 설명 된 MSI 재배포 프로세스를 사용 합니다.이전 버전의 MSI 패키지를 배포 하는 경우 클라이언트는 사용자에 대해 가능 하면 VDI 환경에서 제외 하 고 자동으로 업데이트 됩니다. 오래 된 버전이 배포 되는 경우 MSI는 사용자가 팀을 사용할 수 있도록 앱 업데이트를 트리거합니다. 

> [!Important] 
> 기본 설치 위치를 변경 하는 것은 업데이트 흐름이 중단 될 수 있으므로 권장 하지 않습니다. 오래 된 버전을 보유 하면 결국 사용자가 서비스에 액세스 하지 못하도록 차단 됩니다. 

#### <a name="target-computer-requirements"></a>대상 컴퓨터 요구 사항

- .NET framework 4.5 이상
- Windows 7 이상
- 각 사용자 프로필에 대해 3gb의 디스크 공간 (권장)

### <a name="vdi-installation"></a>VDI 설치

팀 데스크톱 앱을 배포 하는 프로세스는 다음과 같습니다. 자세한 지침은 [가상화 된 데스크톱 인프라에 대 한 팀](teams-for-vdi.md)을 참조 하세요.

1. 환경에 따라 다음 링크 중 하나를 사용 하 여 팀 MSI 패키지를 다운로드 합니다. 64 비트 운영 체제와 함께 VDI VM에 대 한 64 비트 버전을 사용 하는 것이 좋습니다.

    - [32 비트 버전](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [64 비트 버전](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. 다음 명령을 실행 하 여 VDI VM에 MSI를 설치 하거나 업데이트를 완료 합니다.

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    이렇게 하면 프로그램 파일에 팀이 설치 됩니다. 이 시점에서 골든 이미지 설정이 완료 되었습니다.

    다음 대화형 로그온 세션에서 팀을 시작 하 고 자격 증명을 요청 합니다. ALLUSER 속성을 사용 하 여 VDI에 팀을 설치할 때는 팀의 자동 실행을 해제할 수 없습니다.

3. 다음 명령을 실행 하 여 VDI VM에서 MSI를 제거 하거나 업데이트 준비를 합니다.

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    이렇게 하면 프로그램 파일에서 팀이 제거 됩니다.

## <a name="clean-up-and-redeployment-procedure"></a>정리 및 다시 배포 절차

사용자가 사용자 프로필에서 팀을 제거 하는 경우 MSI 설치 관리자는 사용자가 팀 앱을 제거 하 고 더 이상 해당 사용자 프로필에 대 한 팀을 설치 하지 않은 것을 추적 합니다. 제거 된 특정 컴퓨터에서이 사용자의 팀을 다시 배포 하려면 다음을 수행 합니다.

1. 모든 사용자 프로필에 대해 팀 앱을 설치 제거 합니다. 
2. 제거 후%localappdata%\Microsoft\Teams\.에서 디렉터리를 재귀적으로 삭제 합니다.
3. 해당 특정 컴퓨터에 MSI 패키지를 다시 배포 합니다.

> [!TIP] 
> [Microsoft 팀 배포 정리](scripts/Powershell-script-teams-deployment-clean-up.md) 스크립트를 사용 하 여 SCCM을 통해 1 단계 및 2 단계를 수행할 수 있습니다.

## <a name="disable-auto-launch-for-the-msi-installer"></a>MSI 설치 관리자에 대 한 자동 시작 사용 안 함

MSI의 기본 동작은 사용자가 로그인 하는 즉시 팀 클라이언트를 설치한 다음 팀을 자동으로 시작 하는 것입니다. 다음과 같이 아래 매개 변수를 사용 하 여이 동작을 수정할 수 있습니다.

- 사용자가 Windows에 로그인 하면 팀이 MSI와 함께 설치 됩니다.
- 그러나 사용자가 팀을 수동으로 시작할 때까지 팀 클라이언트는 시작 되지 않습니다.
- 팀 시작에 대 한 바로 가기가 사용자의 데스크톱에 추가 됩니다.
- 수동으로 시작 되 면 사용자가 로그인 할 때마다 팀이 자동으로 시작 됩니다.

32 비트 버전
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
64 비트 버전
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  MSI를 수동으로 실행 하는 경우 관리자 권한으로 실행 해야 합니다. 관리자 권한으로 실행 하는 경우에도 권한 상승으로이를 실행 하지 않으면 설치 관리자가 자동 시작을 사용 하지 않도록 설정 하는 옵션을 구성할 수 없게 됩니다.
