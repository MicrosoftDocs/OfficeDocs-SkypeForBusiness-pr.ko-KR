---
title: Microsoft Teams PowerShell 설치
ms.reviewer: brandber
author: brandber
ms.author: brandber
manager: kojiko
ms.date: 06/30/2020
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: powerShell 컨트롤을 사용하여 Microsoft Teams 관리하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58d64a64fd7c9714e84042e4e1aa1be3eb4505db
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65682009"
---
# <a name="install-microsoft-teams-powershell-module"></a>Microsoft Teams PowerShell 모듈 설치

이 문서에서는 PowerShell 갤러리 사용하여 Microsoft Teams PowerShell 모듈을 설치하는 방법을 설명합니다. Microsoft Teams PowerShell 모듈은 모든 Windows 플랫폼에서 지원됩니다. Mac 및 Linux는 지원되지 않습니다.

## <a name="requirements"></a>요구 사항

Microsoft Teams PowerShell 모듈에는 모든 플랫폼에서 PowerShell 5.1 이상이 필요합니다. 운영 체제에 사용할 수 있는 [최신 버전의 PowerShell](/powershell/scripting/install/installing-powershell) 을 설치합니다.

PowerShell 버전을 확인하려면 PowerShell 세션 내에서 다음 명령을 실행합니다.

```powershell
$PSVersionTable.PSVersion
```

Install-Module cmdlet을 사용하여 Microsoft Teams PowerShell 모듈을 설치하는 것이 좋습니다.

PowerShell 갤러리(PSGallery)가 **PowerShellGet** 에 대한 신뢰할 수 있는 리포지토리로 구성되지 않은 경우 PSGallery를 처음 사용할 때 다음 메시지가 표시됩니다.

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

설치를 계속 **하려면** **모두 예** 또는 예(예)라고 대답합니다.

## <a name="installing-using-the-powershellgallery"></a>PowerShellGallery를 사용하여 설치

Microsoft Teams PowerShell 모듈은 현재 Windows PowerShell 5.1에서 사용할 수 있습니다. 다음 단계에 따라 모듈을 설치합니다.

- [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell)로 업데이트합니다. Windows 10 버전 1607 이상인 경우 PowerShell 5.1이 이미 설치되어 있습니다.
- [.NET Framework 4.7.2](/dotnet/framework/install) 이상을 설치합니다.
- 다음 명령을 실행하여 최신 PowerShellGet을 설치합니다.

  ```powershell
  Install-Module -Name PowerShellGet -Force -AllowClobber
  ```

- Teams PowerShell 모듈을 설치합니다.

  ```powershell
  Install-Module -Name MicrosoftTeams -Force -AllowClobber
  ```

## <a name="offline-installation"></a>오프라인 설치

일부 환경에서는 PowerShell 갤러리 연결할 수 없습니다. 이러한 상황에서는 [이러한 수동 설치 단계를](https://aka.ms/psgallery-manualdownload) 수행하세요.

## <a name="sign-in"></a>서명하세요

Microsoft Teams PowerShell 모듈 작업을 시작하려면 Azure 자격 증명으로 로그인합니다.

```PowerShell
Connect-MicrosoftTeams
```

## <a name="update-teams-powershell-module"></a>PowerShell 모듈 Teams 업데이트

PowerShell 모듈을 업데이트하려면 모듈을 설치하는 데 사용되는 것과 동일한 방법을 사용해야 합니다. 예를 들어 원래 Install-Module을 사용한 경우 [Update-Module](/powershell/module/powershellget/update-module) 을 사용하여 최신 버전을 가져와야 합니다.

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Teams PowerShell을 PowerShell 세션으로 이미 가져온 경우 모듈을 업데이트하지 못합니다. PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 엽니다.

## <a name="uninstall-teams-powershell"></a>PowerShell Teams 제거

Microsoft Teams PowerShell을 제거하려면 새 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions
```

## <a name="next-steps"></a>다음 단계

이제 Microsoft Teams PowerShell을 사용하여 Microsoft Teams 관리할 준비가 되었습니다. 시작하려면 [Teams PowerShell을 사용하여 Teams 관리를](teams-powershell-managing-teams.md) 참조하세요.

## <a name="related-topics"></a>관련 항목

[Teams PowerShell을 사용하여 Teams 관리](teams-powershell-managing-teams.md)

[PowerShell 릴리스 정보 Teams](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](/powershell/teams/)

[비즈니스용 Skype cmdlet 참조](/powershell/skype/intro)
