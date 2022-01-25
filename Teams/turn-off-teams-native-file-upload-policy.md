---
title: 네이티브 Teams 파일 업로드 해제
author: danieasmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
search.appverid: ''
description: PowerShell을 사용하여 파일 Teams 만들기, 설정, 할당 및 조정하는 방법에 대해 자세히 알아보습니다.
audience: admin
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64bd9d23527ef1a63df4f258e89de5e60862a878
ms.sourcegitcommit: 9ef6e36eeba7db70971f4eb1a45f0ded394b1fe6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2022
ms.locfileid: "62192508"
---
# <a name="turn-off-teams-native-file-upload-policy"></a>네이티브 Teams 파일 업로드 해제

Microsoft Teams ONEDRIVE 및 SharePoint(ODSP)를 사용하여 콘텐츠를 저장하고 공유하지만 일부 조직 및 사용자는 타사 저장소 공급자를 사용하는 것을 선호할 수 있습니다.  

조직에서 콘텐츠 저장소에 대한 타사를 선택하는 경우 파일 정책에서 매개 ``NativeFileEntryPoints`` 변수를 Teams 합니다. 이 매개 변수는 기본적으로 사용하도록 설정되어, ODSP에서 채팅 또는 채널에 콘텐츠를 업로드하는 Teams 보여줍니다.

이 문서에서는 PowerShell을 사용하여 매개 변수를 만들고, 설정하고, 할당하고, ``NativeFileEntryPoints`` 제거하는 데 도움이 됩니다.

>[!NOTE]
>파일 Teams 정책이 해제되면 사용자는 OneDrive 및 ODSP(SharePoint)에 대한 액세스 지점을 Teams 있지만 새 팀 및 채널을 만들면 계속 SharePoint 트리거됩니다.

## <a name="prepare-to-update-the-teams-files-policy"></a>파일 Teams 업데이트 준비

### <a name="set-up-microsoft-powershell"></a>Microsoft PowerShell 설정

현재 이 정책은 관리 센터에서 변경할 수 Teams 없습니다. 조직의 Microsoft 365 테넌트 관리자는 이 문서의 나중에 자세히 설명된 PowerShell cmdlet을 사용하여 변경해야 합니다.

PowerShell 모듈 설치 를 Teams PowerShell 갤러리를 사용하여 [PowerShell Microsoft Teams 방법을 알아보십시오.](teams-powershell-install.md)

PowerShell Teams 설치하거나 다운로드하려면 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/3.0.0)Microsoft Teams.

관리용 PowerShell을 설정하는 방법에 대한 자세한 내용은 Teams [PowerShell을](teams-powershell-managing-teams.md)사용하여 Teams Microsoft Teams 참조하세요.

### <a name="allow-third-party-apps-in-teams-admin-center"></a>관리 센터에서 타사 Teams 허용

이 단계에서는 파일 Teams 변경하지는 않지만 사용자의 사용자 경험에 타사 저장소 공급자를 통합할 준비가 Teams 필요합니다.

Microsoft 365 테넌트 관리자는 관리 센터에서 "타사 앱 허용" 정책을 사용하도록 Teams 합니다.

타사 또는 사용자 지정 앱을 허용하는 방법에 대한 자세한 내용은 관리 센터의 앱 관리에서 Microsoft Teams [참조하세요.](/microsoftteams/manage-apps#manage-org-wide-app-settings)

## <a name="turn-off-nativefileentrypoints-for-your-entire-tenant"></a>전체 테넌트에 대한 NativeFileEntryPoints 해제

매개 변수를 설정하면 조직의 모든 사용자에게 정책 ``-Identity`` ``Global`` 설정을 적용합니다.

### <a name="sample-powershell-policy-cmdlet-for-entire-tenant"></a>전체 테넌트에 대한 샘플 PowerShell 정책 cmdlet

이 샘플 PowerShell 명령은 전체 테넌트에 대한 매개 ``NativeFileEntryPoints`` ``Disabled`` 변수를 설정합니다.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="check-the-status-of-your-tenant"></a>테넌트의 상태 확인  

테넌트의 파일 Teams 현재 상태를 확인하려면 ``Get-CsTeamsFilesPolicy`` cmdlet을 사용 합니다.

```powershell
Get-CsTeamsFilesPolicy -Identity Global
```

### <a name="turn-on-or-turn-off-native-file-upload-point"></a>네이티브 파일 업로드 지점을 켜거나 끄기

전체 테넌트에 대한 네이티브 파일 업로드 지점을 켜거나 해제하려면 매개 변수를 또는 ``NativeFileEntryPoints`` ``Enabled`` 로 ``Disabled`` 설정합니다.

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Enabled
```

```powershell
Set-CsTeamsFilesPolicy -Identity Global -NativeFileEntryPoints Disabled
```

### <a name="remove-the-policy-for-your-users"></a>사용자에 대한 정책 제거

사용자에 대한 Teams 파일 정책을 제거하려면 ``Remove-CsTeamsFilesPolicy`` cmdlet을 사용 합니다.

```powershell
Remove-CsTeamsFilesPolicy -Identity Global
```

## <a name="turn-off-nativefileentrypoints-for-specific-users"></a>특정 사용자에 대한 NativeFileEntryPoints 해제

또한 새 파일 Teams 정책 문자열을 만들고 새로 만든 정책을 사용자에게 할당하여 특정 Teams 파일 정책을 업데이트할 ``-Identity`` 수도 있습니다.

### <a name="sample-powershell-policy-cmdlet-for-specific-users"></a>특정 사용자에 대한 샘플 PowerShell 정책 cmdlet

이 샘플 PowerShell 명령은 로 명명된 새 및 매개 변수가 ``CsTeamsFilesPolicy`` ``-Identity`` 로 ``UserPolicy`` ``NativeFileEntryPoints`` 설정되어 ``Disabled`` 있습니다.

를 할당하면 해당 네이티브 파일 진입점이 ``CsTeamsFilesPolicy`` ``-Identity UserPolicy`` 해제됩니다.

```powershell
New-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Disabled
```

### <a name="assign-a-policy-to-user"></a>사용자에게 정책 할당

새 정책을 만든 후 cmdlet을 사용하여 사용자에게 해당 정책을 ``Grant-CsTeamsFilesPolicy`` 할당할 수 있습니다.

```powershell
Grant-CsTeamsFilesPolicy  -identity "user email id" -PolicyName UserPolicy
```

### <a name="update-the-policy"></a>정책 업데이트

새 파일 정책의 설정을 변경해야 Teams 경우 ``UserPolicy`` ``Set-CsTeamsFilePolicy`` cmdlet을 사용 합니다.

```powershell
Set-CsTeamsFilesPolicy -Identity UserPolicy -NativeFileEntryPoints Enabled
```

### <a name="remove-the-policy-for-the-complete-list-of-users"></a>전체 사용자 목록에 대한 정책 제거

파일 정책에 할당된 모든 Teams 제거하려면 ``UserPolicy`` ``Remove-CsTeamsFilesPolicy`` cmdlet을 사용 합니다.

```powershell
Remove-CsTeamsFilesPolicy -Identity UserPolicy
```
>[!NOTE]
> 정책을 변경한 후 변경 내용이 사용자의 클라이언트에 표시하도록 최대 12시간 동안 Teams.
