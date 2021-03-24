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
description: Microsoft Teams를 관리하는 데 PowerShell 컨트롤을 사용하는 방법을 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: e5526a7a7d782b8a30edd5b5169c3ba78953cc7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094158"
---
# <a name="install-microsoft-teams-powershell"></a>Microsoft Teams PowerShell 설치

이 문서에서는 [PowerShellGet](/powershell/scripting/gallery/installing-psget)를 사용하여 Microsoft Teams PowerShell 모듈을 설치하는 방법을 설명합니다. 이러한 지침은 [Azure Cloud Shell,](/azure/cloud-shell/overview)Linux, macOS 및 Windows 플랫폼에서 작동합니다.

## <a name="requirements"></a>요구 사항

Teams PowerShell에는 모든 플랫폼에서 PowerShell 5.1 이상이 필요합니다. 운영 체제에 사용할 수 있는 [최신 버전의 PowerShell을](/powershell/scripting/install/installing-powershell) 설치합니다.

> [!WARNING]
> PowerShell 7 및 Teams PowerShell에 알려진 문제가 있습니다. 최상의 환경을 위해 PowerShell 5.1을 사용하는 것이 좋습니다.

## <a name="install-the-teams-powershell-module"></a>Teams PowerShell 모듈 설치

> [!NOTE]
> 최상의 환경을 위해 GA(일반 가용성) 또는 공용 미리 보기 모듈을 모두 사용하지 않습니다. 함께 작동할 수 없습니다.


**PowerShellGet** cmdlet을 사용하여 Teams PowerShell 모듈을 설치합니다. 시스템에 있는 모든 사용자에 대해 모듈을 설치하려면 높은 권한이 필요합니다. Windows에서 관리자 권한으로  실행을 사용하여 PowerShell 세션을 시작하거나 macOS 또는 Linux에서 명령을 `sudo` 사용할 수 있습니다.

```powershell
Install-Module MicrosoftTeams
```

기본적으로 PSGallery(PowerShell 갤러리)는 **PowerShellGet의** 신뢰할 수 있는 리포지토리로 구성되지 않습니다. PSGallery를 처음 사용할 때 다음 메시지가 표시됩니다.

```console
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

설치를 계속 진행하기 위해 **모두에** 예 또는 **예에** 대답합니다.


## <a name="install-teams-powershell-public-preview"></a>Teams PowerShell 공개 미리 보기 설치

> [!NOTE]
> Teams PowerShell의 공개 미리 보기 버전을 사용하는 경우 먼저 비즈니스용 Skype Online 커넥터를 제거하는 것이 좋습니다.

시스템의 모든 사용자에 대해 Teams PowerShell 공개 미리 보기 모듈을 설치하려면 높은 권한이 필요합니다. Windows에서 관리자 권한으로  실행을 사용하여 PowerShell 세션을 시작하거나 macOS 또는 Linux에서 명령을 `sudo` 사용할 수 있습니다.

PowerShell 5.1을 사용하는 경우 **PowerShellGet** 모듈을 먼저 업데이트해야 합니다. **PowerShellGet를** 업데이트한 후 상승된 PowerShell 세션을 닫고 다시 열고 최신 **PowerShellGet가** 로드되도록 합니다.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

Teams PowerShell 공개 미리 보기를 설치하려면 아래 PowerShell 명령을 실행합니다.

> [!NOTE]
> "Find-Module MicrosoftTeams -AllowPrerelease -AllVersions"를 실행하여 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) 갤러리 또는 PowerShell에서 최신 미리 보기 버전을 찾을 수 있습니다.

```powershell
Install-Module MicrosoftTeams -AllowPrerelease -RequiredVersion "1.1.9-preview"
```

## <a name="install-the-skype-for-business-online-connector"></a>비즈니스용 Skype Online 커넥터 설치

> [!NOTE]
>
> 비즈니스용 Skype Online 커넥터는 현재 최신 Teams PowerShell 모듈의 일부입니다.
> 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.


```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="sign-in"></a>서명하세요

Teams PowerShell 작업을 시작하고 Azure 자격 증명으로 로그인합니다.

> [!NOTE]
> 최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)공개 미리 보기 릴리스를 사용하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.

```powershell
$credential = Get-Credential

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credential $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credential $credential
Import-PsSession $session
```

## <a name="sign-in-using-mfa-and-modern-authentication"></a>MFA 및 최신 인증을 사용하여 로그인

 계정에서 다단계 인증을 사용하는 경우 이 섹션의 단계를 사용하세요.

```powershell
#Connect to Microsoft Teams
Connect-MicrosoftTeams -AccountId <UPN>

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>Teams PowerShell 업데이트

Teams PowerShell을 업데이트하기 위해 새 상승된 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> Teams PowerShell이 PowerShell 세션으로 이미 가져온 경우 모듈 업데이트가 실패합니다. PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 를 를 열 수 있습니다.


## <a name="uninstall-teams-powershell"></a>Teams PowerShell 제거



Teams PowerShell을 제거하기 위해 상승된 새 PowerShell 명령 프롬프트를 열고 다음을 실행합니다.

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> Teams PowerShell이 PowerShell 세션으로 이미 가져온 경우 모듈을 삭제하지 못합니다. PowerShell을 닫고 상승된 새 PowerShell 세션을 다시 를 를 열 수 있습니다.

## <a name="next-steps"></a>다음 단계

이제 Teams PowerShell을 사용하여 Teams를 관리할 준비가 완료되었습니다. 시작은 [Teams PowerShell을 통해 팀](teams-powershell-managing-teams.md) 관리 를 참조합니다.

## <a name="related-topics"></a>관련 항목

[Teams PowerShell을 통해 Teams 관리](teams-powershell-managing-teams.md)

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft Teams cmdlet 참조](/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](/powershell/skype/intro?view=skype-ps)