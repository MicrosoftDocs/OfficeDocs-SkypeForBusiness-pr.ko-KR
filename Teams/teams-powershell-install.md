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
description: Microsoft Teams를 관리하기 위해 PowerShell 컨트롤을 사용하는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd5b38dd3a43a405794209a9dc7ac4a4468386ef
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662023"
---
# <a name="install-microsoft-teams-powershell"></a>Microsoft Teams PowerShell 설치

이 문서에서는 [PowerShellGet을](/powershell/scripting/gallery/installing-psget)사용하여 Microsoft Teams PowerShell 모듈을 설치하는 방법을 설명하고 있습니다. 이러한 지침은 [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS 및 Windows 플랫폼에서 적용됩니다.

## <a name="requirements"></a>요구 사항

Teams PowerShell에는 모든 플랫폼에서 PowerShell 5.1 이상이 필요합니다. 운영 체제에 사용할 수 있는 [최신 버전의 PowerShell을](/powershell/scripting/install/installing-powershell) 설치합니다.

> [!WARNING]
> PowerShell 7 및 Teams PowerShell에는 알려진 문제가 있습니다. 최상의 환경을 위해 PowerShell 5.1을 사용하는 것이 좋습니다.

## <a name="install-the-teams-powershell-module"></a>Teams PowerShell 모듈 설치

> [!NOTE]
> 최상의 환경을 위해 GA(일반 공급) 또는 공개 미리 보기 모듈을 모두 사용하지 않습니다. 함께 작업할 수 없습니다.


**PowerShellGet** cmdlet을 사용하여 Teams PowerShell 모듈을 설치합니다. 시스템에 모든 사용자에 대한 모듈을 설치하려면 상승된 권한이 필요합니다. Windows에서 관리자 권한으로 실행을 사용하여 PowerShell 세션을 **시작하거나** macOS 또는 Linux에서 명령을 `sudo` 사용 합니다.

```powershell
Install-Module MicrosoftTeams
```

기본적으로 PSGallery(PowerShell 갤러리)는 **PowerShellGet에** 대한 신뢰할 수 있는 리포지토리로 구성되지 않습니다. PSGallery를 처음 사용하면 다음 메시지가 표시됩니다.

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

설치를 계속 진행하기 **위해 모두에 예** 또는 예로 응답합니다. 


## <a name="install-teams-powershell-public-preview"></a>Teams PowerShell 공개 미리 보기 설치

> [!NOTE]
> 공개 미리 보기 버전의 Teams PowerShell을 사용하는 경우 먼저 비즈니스용 Skype Online Connector를 제거하는 것이 좋습니다.

시스템의 모든 사용자에 대해 Teams PowerShell 공개 미리 보기 모듈을 설치하려면 상승된 권한이 필요합니다. Windows에서 관리자 권한으로 실행을 사용하여 PowerShell 세션을 **시작하거나** macOS 또는 Linux에서 명령을 `sudo` 사용 합니다.

PowerShell 5.1을 사용하는 경우 **PowerShellGet** 모듈을 먼저 업데이트해야 합니다. **PowerShellGet을** 업데이트한 후 상승된 PowerShell 세션을 닫았다가 다시 열고 최신 **PowerShellGet이** 로드되도록 합니다.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Teams PowerShell 공개 미리 보기를 설치하려면 아래 PowerShell 명령을 실행합니다.

> [!NOTE]
> "Find-Module MicrosoftTeams -AllowPrerelease"를 실행하여 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 갤러리 또는 PowerShell에서 최신 미리 보기 버전을 찾을 수 있습니다.

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>비즈니스용 Skype Online Connector 설치

> [!NOTE]
>
> 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.
> 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.

```powershell
Import-Module -Name MicrosoftTeams
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>서명하세요

Teams PowerShell 작업을 시작하고 Azure 자격 증명으로 로그인합니다.

> [!NOTE]
> 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 미리 보기 릴리스를 사용하는 경우 비즈니스용 Skype Online Connector를 설치할 필요가 없습니다.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Teams PowerShell 업데이트

Teams PowerShell을 업데이트하기 위해 상승된 새 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Teams PowerShell을 PowerShell 세션으로 이미 가져온 경우 모듈 업데이트가 실패합니다. PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 열 수 있습니다.


## <a name="uninstall-teams-powershell"></a>Teams PowerShell 제거



Teams PowerShell을 제거하기 위해 상승된 새 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Teams PowerShell을 PowerShell 세션으로 이미 가져온 경우 모듈을 삭제하지 못합니다. PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 열 수 있습니다.

## <a name="next-steps"></a>다음 단계

이제 Teams PowerShell을 사용하여 Teams를 관리할 준비가 완료되었습니다. 시작은 [Teams PowerShell을](teams-powershell-managing-teams.md) 통해 Teams 관리를 참조합니다.

## <a name="related-topics"></a>관련 항목

[Teams PowerShell을 통해 Teams 관리](teams-powershell-managing-teams.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
