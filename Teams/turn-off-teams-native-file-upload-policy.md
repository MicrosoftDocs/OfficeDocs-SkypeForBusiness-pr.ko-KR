---
title: Teams 네이티브 파일 업로드 정책 끄기
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: PowerShell을 사용하여 Teams 파일 정책을 만들고, 설정하고, 할당하고, 조정하는 방법을 알아봅니다.
audience: admin
ms.localizationpriority: medium
appliesto:
- Microsoft Teams
ms.collection:
- M365-collaboration
ms.openlocfilehash: 1993371099d0712d21106987f21575e85e181ad7
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268930"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>Teams 네이티브 파일 업로드 정책 끄기

Microsoft Teams는 OneDrive 및 SharePoint를 사용하여 콘텐츠를 저장하고 공유하지만 일부 조직과 사용자는 타사 스토리지 공급자를 사용하는 것을 선호할 수 있습니다.  

조직에서 콘텐츠 스토리지에 대한 타사로 선택하는 경우 Teams 파일 정책에서 매개 변수를 해제 `NativeFileEntryPoints` 해야 합니다. 이 매개 변수는 기본적으로 사용하도록 설정되며 OneDrive 또는 SharePoint에서 Teams 채팅 또는 채널로 콘텐츠를 업로드하는 옵션을 보여 줍니다.

이 문서는 PowerShell을 사용하여 매개 변수를 `NativeFileEntryPoints` 만들고, 설정하고, 할당하고, 제거하는 데 도움이 됩니다.

>[!NOTE]
>Teams 파일 정책이 꺼지면 Teams에서 OneDrive 및 SharePoint에 대한 액세스 지점이 표시되지 않지만 새 팀과 채널을 만들면 일치하는 SharePoint 라이브러리 생성이 계속 트리거됩니다.

## <a name="prepare-to-update-the-teams-files-policy"></a>Teams 파일 정책 업데이트 준비

### <a name="set-up-microsoft-powershell"></a>Microsoft PowerShell 설정

현재 Teams 관리 센터에서는 이 정책을 변경할 수 없습니다. 조직의 Microsoft 365 테넌트 관리자는 이 문서의 뒷부분에 설명된 PowerShell cmdlet을 사용하여 변경해야 합니다.

Microsoft Teams PowerShell 모듈 설치를 읽어 PowerShell 갤러리 사용하여 [PowerShell Teams 모듈을 설치하는](teams-powershell-install.md) 방법을 알아봅니다.

Teams PowerShell 모듈을 설치하거나 다운로드하려면 [Microsoft Teams용 PowerShell 갤러리 참조하세요](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0).

Teams 관리를 위해 PowerShell을 설정하는 방법에 대한 자세한 내용은 [Microsoft Teams PowerShell을 사용하여 Teams 관리를](teams-powershell-managing-teams.md) 참조하세요.

### <a name="allow-third-party-apps-in-teams-admin-center"></a>Teams 관리 Center에서 타사 앱 허용

이 단계는 Teams 파일 정책을 변경하는 데 필요하지 않지만 사용자의 Teams 환경에 타사 스토리지 공급자를 통합할 준비가 되면 필요합니다.

Microsoft 365 테넌트 관리자는 Teams 관리 센터에서 "타사 앱 허용" 정책을 사용하도록 설정해야 합니다.

타사 또는 사용자 지정 앱을 허용하는 방법을 알아보려면 [Microsoft Teams 관리 센터의 앱 관리에서](/microsoftteams/manage-apps#manage-org-wide-app-settings) 조직 전체 앱 설정 관리를 참조하세요.

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>전체 테넌트에 대해 NativeFileEntryPoints 끄기

매개 변수를 `-Identity` 설정하면 `Global` 조직의 모든 사용자에게 정책 설정이 적용됩니다.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>전체 테넌트에 대한 샘플 PowerShell 정책 cmdlet

이 샘플 PowerShell 명령은 전체 테넌트에`NativeFileEntryPoints` 대한 매개 변수를 `Disabled` 설정합니다.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>테넌트 상태 확인  

테넌트의 Teams 파일 정책의 현재 상태를 보려면 cmdlet을 `Get-CsTeamsFilesPolicy` 사용합니다.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>네이티브 파일 업로드 지점 켜기 또는 끄기

To turn on or turn off the native file upload point for your entire tenant, set the `NativeFileEntryPoints` parameter to either `Enabled` or `Disabled`.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>사용자에 대한 정책 제거

사용자에 대한 Teams 파일 정책을 제거하려면 cmdlet을 `Remove-CsTeamsFilesPolicy` 사용합니다.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>특정 사용자에 대한 NativeFileEntryPoints 끄기

새 Teams 파일 정책 문자열을 만들고 새로 만든 정책을 사용자에게 할당하여 특정 사용자에 대한 Teams 파일 정책을 `-Identity` 업데이트할 수도 있습니다.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>특정 사용자에 대한 샘플 PowerShell 정책 cmdlet

이 샘플 PowerShell 명령은 명명된 이름으로 새 명령을 만들고 `CsTeamsFilesPolicy` `-Identity` 매개 변수를 `NativeFileEntryPoints` .로 `UserPolicy` `Disabled`설정합니다.

사용자에게 with`-Identity UserPolicy`가 `CsTeamsFilesPolicy` 할당되면 네이티브 파일 진입점이 꺼집니다.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>사용자에게 정책 할당

새 정책을 만든 후에는 cmdlet을 사용하여 `Grant-CsTeamsFilesPolicy` 사용자에게 해당 정책을 할당할 수 있습니다.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>정책 업데이트

새 Teams 파일 정책 `UserPolicy`의 설정을 변경해야 하는 경우 cmdlet을 `Set-CsTeamsFilePolicy` 사용합니다.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>전체 사용자 목록에 대한 정책 제거

Teams 파일 정책에 할당된 모든 사용자에서 정책을 `UserPolicy`제거하려면 cmdlet을 `Remove-CsTeamsFilesPolicy` 사용합니다.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> 정책을 변경한 후에는 변경 내용이 사용자의 Teams 클라이언트에 표시되도록 최대 12시간을 허용합니다.
