---
title: PowerShell Microsoft Teams 설치
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
description: PowerShell 컨트롤을 사용하여 데이터 관리에 Microsoft Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99af6bc71bdd25375f6165f1e645bf4626dd3123
ms.sourcegitcommit: 2044fdcb0c5db10dbc77c5d66e382c1b927ccdc4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2022
ms.locfileid: "63039976"
---
# <a name="install-microsoft-teams-powershell-module"></a>PowerShell Microsoft Teams 설치

이 문서에서는 PowerShell 갤러리를 사용하여 Microsoft Teams PowerShell 모듈을 설치하는 방법을 설명합니다. PowerShell Microsoft Teams 모든 플랫폼에서 지원되는 Windows 있습니다. Mac 및 Linux는 지원되지 않습니다.

## <a name="requirements"></a>요구 사항

Microsoft Teams PowerShell 모듈에는 모든 플랫폼에서 PowerShell 5.1 이상이 필요합니다. 운영  [체제에 대해 PowerShellavailable](/powershell/scripting/install/installing-powershell) 의 가장 최신 버전을 설치합니다. 

PowerShell 버전을 확인한 후 PowerShell 세션 내에서 다음 명령을 실행합니다. 

```powershell
$PSVersionTable.PSVersion 
```
Install-Module cmdlet을 사용하여 powerShell 모듈을 Microsoft Teams 것이 좋습니다. 
 
PowerShell 갤러리(PSGallery)가 **PowerShellGet** 에 대한 신뢰할 수 있는 리포지토리로 구성되지 않은 경우 PSGallery를 처음 사용할 때 다음 메시지가 표시됩니다.

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

설치 **를** 계속 진행하기 위해 모두 **에 예 또는 예** 에 대답합니다.

## <a name="installing-using-the-powershellgallery"></a>PowerShellGallery를 사용하여 설치

Microsoft Teams PowerShell 모듈은 현재 PowerShell 5.1에서 사용할 수 Windows. 다음 단계를 수행하여 모듈을 설치합니다. 

- [5.1 Windows PowerShell 업데이트합니다](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell). 버전 1607 이상에 Windows 10 PowerShell 5.1이 이미 설치되어 있습니다. 
- [4.7.2](/dotnet/framework/install) .NET Framework 설치합니다. 
- 다음 명령을 실행하여 최신 PowerShellGet를 설치합니다.
 
```powershell
Install-Module -Name PowerShellGet -Force -AllowClobber
```
- PowerShell Teams 설치합니다.

```powershell
Install-Module -Name MicrosoftTeams -Force -AllowClobber
```

## <a name="offline-installation"></a>오프라인 설치 

일부 환경에서는 PowerShell 갤러리에 연결할 수 없습니다. 이러한 상황에서는 다음 수동 설치 [단계를 따르세요](https://aka.ms/psgallery-manualdownload).  

## <a name="sign-in"></a>서명하세요

PowerShell 모듈을 사용하여 Microsoft Teams Azure 자격 증명으로 로그인합니다.

```PowerShell
Connect-MicrosoftTeams 
``` 

## <a name="update-teams-powershell-module"></a>PowerShell Teams 업데이트

PowerShell 모듈을 업데이트하려면 모듈을 설치하는 데 사용되는 동일한 방법을 사용해야 합니다. 예를 들어 처음 설치 모듈을 사용했다면 [Update-Module](/powershell/module/powershellget/update-module) 을 사용하여 최신 버전을 제공해야 합니다.  

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> PowerShell Teams PowerShell이 이미 PowerShell 세션으로 가져오면 모듈 업데이트가 실패합니다. PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 를 를 열 수 있습니다.


## <a name="uninstall-teams-powershell"></a>PowerShell Teams 제거

PowerShell을 Microsoft Teams 새 PowerShell 명령 프롬프트를 열고 다음을 실행합니다. 

```powershell
Uninstall-Module MicrosoftTeams

# Uninstall all versions of the module
Uninstall-Module MicrosoftTeams -Allversions 
```

## <a name="next-steps"></a>다음 단계 

이제 PowerShell을 사용하여 Microsoft Teams 관리할 Microsoft Teams 있습니다. [PowerShell을 Teams Teams 관리](teams-powershell-managing-teams.md) 를 참조합니다. 

## <a name="related-topics"></a>관련 항목

[PowerShell을 Teams Teams 관리](teams-powershell-managing-teams.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](/powershell/skype/intro?view=skype-ps)
