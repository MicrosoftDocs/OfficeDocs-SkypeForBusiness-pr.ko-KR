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
description: Microsoft Teams를 관리하는 PowerShell 컨트롤을 사용하는 방법을 배우세요.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 966dd62a9917c616c53fc57e13ca468e64acf218
ms.sourcegitcommit: bb5229c9f7999358dcf0ba185ecfd7c881627a38
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46824939"
---
# <a name="install-microsoft-teams-powershell"></a>Microsoft Teams PowerShell 설치

이 문서에서는 PowerShellGet을 사용하여 Microsoft Teams PowerShell 모듈을 설치하는 [방법을 설명합니다.](/powershell/scripting/gallery/installing-psget) 다음 지침은 [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS 및 Windows 플랫폼에서 작동합니다.

## <a name="requirements"></a>요구 사항

Teams PowerShell을 사용하려면 모든 플랫폼에서 PowerShell 5.1 이상이 필요합니다. 사용 중인 [운영 체제에서 사용할 수 있는](/powershell/scripting/install/installing-powershell) 최신 버전의 PowerShell을 설치합니다.

> [!WARNING]
> PowerShell 7 및 Teams PowerShell에는 알려진 문제가 있습니다. 최상의 환경을 위해 PowerShell 5.1을 사용하는 것이 좋습니다.

## <a name="install-the-teams-powershell-module"></a>Teams PowerShell 모듈을 설치하세요.

> [!NOTE]
> 최상의 환경을 위해 둘 다 일반 가용성(GA) 또는 공개 미리 보기 모듈을 사용하세요. 이러한 문서는 공동 작업할 수 는 개의 없습니다.


**PowerShellGet** cmdlet을 사용하여 Teams PowerShell 모듈을 설치합니다. 시스템의 모든 사용자에게 모듈을 설치하려면 관리자 권한이 필요합니다. Windows에서 관리자 권한으로 실행을 사용하거나 macOS 또는 **Run as administrator** `sudo` Linux에서 명령을 사용하여 PowerShell 세션을 시작합니다.

```powershell
Install-Module MicrosoftTeams
```

기본적으로 PowerShell 갤러리(PSGallery)는 **PowerShellGet에**대해 신뢰할 수 있는 리포지토리로 구성되지 않습니다. PSGallery를 처음 사용하는 경우 다음 메시지가 표시됩니다.

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

설치를 **계속하려면** **모두에** 예 또는 예로 답변하세요.


## <a name="install-teams-powershell-public-preview"></a>Teams PowerShell 공개 미리 보기 설치

> [!NOTE]
> 공개 미리 보기 버전의 Teams PowerShell을 사용하는 경우 먼저 비즈니스용 Skype Online 커넥터를 제거하는 것이 좋습니다.

시스템의 모든 사용자에게 Teams PowerShell 공용 미리 보기 모듈을 설치하려면 관리자 권한이 필요합니다. Windows에서 관리자 권한으로 실행을 **사용하거나** macOS 또는 `sudo` Linux에서 명령을 사용하여 PowerShell 세션을 시작합니다.

PowerShell 5.1을 사용하는 경우 미리 **PowerShellGet 모듈을** 업데이트해야 합니다. **PowerShellGet을 업데이트한 후에**관리자가 수행한 PowerShell 세션을 닫았다가 다시 열어 **최신 PowerShellGet이** 로드되는지 확인합니다.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Teams PowerShell 공개 미리 보기를 설치하려면 아래의 PowerShell 명령을 실행합니다.

> [!NOTE]
> "Find-Module MicrosoftTeams -AllowPrerelease"를 실행하여 최신 미리 보기 버전을 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 갤러리 또는 PowerShell에서 찾을 수 있습니다.

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.3-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>비즈니스용 Skype Online Connector 설치

> [!WARNING]
> 비즈니스용 Skype Online Connector는 현재 Teams PowerShell 공용 미리 보기에 있습니다. 이 기능을 Teams PowerShell의 GA 릴리스에 롤아아가면 비즈니스용 Skype Online 커넥터를 더 이상 사용할 수 없습니다.

비즈니스용 Skype [PowerShell 모듈을 다운로드하여 설치하고](https://www.microsoft.com/download/details.aspx?id=39366)PowerShell에서 다음 실행하세요.

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>서명하세요

Teams PowerShell로 작업을 시작하려면 Azure 자격 증명으로 로그인합니다.

> [!NOTE]
> 최신 Teams PowerShell 공개 미리 [보기 릴리스를 사용 중인 경우](https://www.powershellgallery.com/packages/MicrosoftTeams/)비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Teams PowerShell 업데이트

Teams PowerShell을 업데이트하려면 새로운 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Teams PowerShell을 이미 PowerShell 세션으로 가져온 경우, 모듈을 업데이트할 수 없습니다. PowerShell을 닫고 새 PowerShell 세션을 다시 엽니다.


## <a name="uninstall-teams-powershell"></a>Teams 제거 PowerShell



Teams PowerShell을 제거하려면 새로운 관리자 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Teams PowerShell을 이미 PowerShell 세션으로 가져온 경우 모듈을 제거하면 실패합니다. PowerShell을 닫고 새 PowerShell 세션을 다시 엽니다.

## <a name="next-steps"></a>다음 단계

이제 Teams PowerShell을 사용하여 Teams를 관리할 준비가 되었습니다. Microsoft [Teams PowerShell로 Teams 관리를 확인하여](teams-powershell-managing-teams.md) 시작하세요.

## <a name="related-topics"></a>관련 항목

[Teams PowerShell로 Teams 관리](teams-powershell-managing-teams.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
