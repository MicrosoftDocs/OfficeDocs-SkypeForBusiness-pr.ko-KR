---
title: Microsoft 팀 PowerShell 설치
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
description: PowerShell 컨트롤을 사용 하 여 Microsoft 팀을 관리 하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 849b22d09c79e97c5eaaeab4dee96b1d432970cb
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "44944109"
---
# <a name="install-microsoft-teams-powershell"></a>Microsoft 팀 PowerShell 설치

이 문서에서는 [PowerShellGet](/powershell/scripting/gallery/installing-psget)을 사용 하 여 Microsoft 팀 PowerShell 모듈을 설치 하는 방법을 설명 합니다. 이러한 지침은 [Azure 클라우드 셸](/azure/cloud-shell/overview), Linux, Macos, Windows 플랫폼에서 작동 합니다.

## <a name="requirements"></a>요구 사항

팀 PowerShell은 모든 플랫폼에서 PowerShell 6.2.4 이상에서 작동 합니다. Windows의 PowerShell 5.1 에서도 지원 됩니다. 운영 체제에 사용할 수 있는 [최신 버전의 PowerShell](/powershell/scripting/install/installing-powershell) 을 설치 합니다. PowerShell 6.2.4 이상에서 실행 되는 경우 팀 PowerShell에는 추가 요구 사항이 없습니다.

> [!WARNING]
> PowerShell 7 및 팀 PowerShell에 알려진 문제가 있습니다. 최상의 환경을 위해서는 PowerShell 5.1를 사용 하는 것이 좋습니다.

## <a name="install-the-teams-powershell-module"></a>팀 PowerShell 모듈 설치

> [!NOTE]
> 최상의 환경을 위해서는 일반 가용성 (GA) 또는 공개 미리 보기 모듈을 사용 합니다. 공동 작업을 위한 것이 아닙니다.


**PowerShellGet** cmdlet을 사용 하 여 팀 PowerShell 모듈을 설치 합니다. 시스템의 모든 사용자에 대해 모듈을 설치 하려면 관리자 권한이 필요 합니다. Windows에서 **관리자 권한으로 실행** 을 사용 하 여 PowerShell 세션을 시작 하거나 `sudo` Macos 또는 Linux의 명령을 사용 합니다.

```powershell
Install-Module MicrosoftTeams
```

기본적으로 PowerShell 갤러리 (PSGallery)는 **PowerShellGet**에 대해 신뢰할 수 있는 리포지토리로 구성 되어 있지 않습니다. 처음으로 PSGallery를 사용 하는 경우 다음 메시지가 표시 됩니다.

```output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

설치를 응답 `Yes` 하거나 `Yes to All` 계속 합니다.


## <a name="install-teams-powershell-public-preview"></a>팀 PowerShell 공용 미리 보기 설치

> [!NOTE]
> 팀 PowerShell의 공용 Preview 버전을 사용 하는 경우 먼저 비즈니스용 Skype Online Connector를 제거 하는 것이 좋습니다.

시스템의 모든 사용자에 대해 팀 PowerShell 공용 미리 보기 모듈을 설치 하려면 관리자 권한이 필요 합니다. Windows에서 **관리자 권한으로 실행** 을 사용 하 여 PowerShell 세션을 시작 하거나 `sudo` Macos 또는 Linux의 명령을 사용 합니다.

PowerShell 5.1를 사용 중인 경우에는 **PowerShellGet** 모듈을 미리 업데이트 해야 합니다. **PowerShellGet**을 업데이트 한 후에는 관리자 권한 PowerShell 세션을 닫았다가 다시 열어 최신 **PowerShellGet** 이 로드 되었는지 확인 합니다.

```powershell
Install-Module PowerShellGet -Force -AllowClobber
```

팀 Powershell 공개 미리 보기를 설치 하려면 아래에서 PowerShell 명령을 실행 합니다.

```powershell
Install-Module MicrosoftTeams -AllowPrerelease
```

## <a name="install-the-skype-for-business-online-connector"></a>비즈니스용 Skype Online 커넥터 설치

> [!WARNING]
> 비즈니스용 Skype Online 커넥터는 현재 팀 PowerShell 공개 미리 보기의 일부입니다. 이 기능을 팀 PowerShell의 GA 릴리스에 겹쳐서 표시 하면 비즈니스용 Skype Online 커넥터를 더 이상 사용할 수 없습니다.

[비즈니스용 Skype PowerShell 모듈](https://www.microsoft.com/download/details.aspx?id=39366)을 다운로드 하 여 설치한 후 PowerShell에서 다음을 실행 합니다.

```powershell
Import-Module SkypeOnlineConnector
$userCredential = Get-Credential
$sfbSession = New-CsOnlineSession -Credential $userCredential
Import-PSSession $sfbSession
```

## <a name="sign-in"></a>서명하세요

팀 PowerShell 작업을 시작 하려면 Azure 자격 증명을 사용 하 여 로그인 합니다.

> [!NOTE]
> 최신 [팀 PowerShell 공용 preview 릴리스](https://www.powershellgallery.com/packages/MicrosoftTeams/)를 사용 하는 경우 비즈니스용 Skype Online 커넥터를 설치할 필요가 없습니다.

```powershell
$credential = Get-Credentials

#Connect to Microsoft Teams
Connect-MicrosoftTeams -Credentials $credential

#Connection to Skype for Business Online and import into Ps session
$session = New-CsOnlineSession -Credentials $credential
Import-PsSession $session
```

## <a name="update-teams-powershell"></a>팀 업데이트 PowerShell

팀 PowerShell을 업데이트 하려면 새 관리자 권한 PowerShell 명령 프롬프트를 열고 다음을 실행 합니다.

```powershell
Update-Module MicrosoftTeams
```

> [!WARNING]
> 팀 PowerShell을 이미 PowerShell 세션으로 가져온 경우 모듈 업데이트는 실패 합니다. PowerShell을 닫고 새 관리자 권한 PowerShell 세션을 다시 엽니다.


## <a name="uninstall-teams-powershell"></a>팀 제거 PowerShell



팀 PowerShell을 제거 하려면 새 관리자 권한 PowerShell 명령 프롬프트를 열고 다음을 실행 합니다.

```powershell
Uninstall-Module MicrosoftTeams
```
> [!WARNING]
> 팀 PowerShell을 이미 PowerShell 세션으로 가져온 경우 모듈을 제거 하지 못합니다. PowerShell을 닫고 새 관리자 권한 PowerShell 세션을 다시 엽니다.

## <a name="next-steps"></a>다음 단계

이제 팀 PowerShell을 사용 하 여 팀을 관리할 준비가 완료 되었습니다. 시작 하려면 [팀 PowerShell을 사용 하 여 팀 관리](teams-powershell-managing-teams.md) 를 참조 하세요.

## <a name="related-topics"></a>관련 항목

[팀을 사용 하 여 팀 관리 PowerShell](teams-powershell-managing-teams.md)

[팀 PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft 팀 cmdlet 참조](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[비즈니스용 Skype cmdlet 참조](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
