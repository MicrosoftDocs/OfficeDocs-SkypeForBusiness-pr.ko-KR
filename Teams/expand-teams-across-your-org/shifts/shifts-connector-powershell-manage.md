---
title: PowerShell을 사용하여 Blue Yonder Workforce Management 대한 Shifts 연결 관리
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: PowerShell을 사용하여 Blue Yonder Workforce Management 대한 Shifts 연결을 관리하는 방법을 알아봅니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4edf815a3ce21a820fa292a06d41275c97d78a5
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647814"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>PowerShell을 사용하여 Blue Yonder Workforce Management 대한 Shifts 연결 관리

## <a name="overview"></a>개요

[Blue Yonder용 Microsoft Teams Shifts 커넥터](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder)를 사용하면 Microsoft Teams의 Shifts 앱을 Blue Yonder Workforce Management(Blue Yonder WFM)와 통합할 수 있습니다. 연결을 설정한 후 일선 작업자는 Shifts 내에서 Blue Yonder WFM 일정을 원활하게 보고 관리할 수 있습니다.

Microsoft 365 관리 센터 또는 [PowerShell](shifts-connector-blue-yonder-powershell-setup.md)에서 [Shifts 커넥터 마법사](shifts-connector-wizard.md)를 사용하여 연결을 설정할 수 있습니다. 연결이 설정되면 [Shifts 커넥터 PowerShell cmdlet을](#shifts-connector-cmdlets) 사용하여 관리합니다.

이 문서에서는 PowerShell을 사용하여 다음을 수행하는 방법을 설명합니다.

- [연결 설정 상태 확인](#check-connection-setup-status)
- [연결에 대한 오류 보고서 보기](#view-an-error-report-for-a-connection)
- [연결 오류 해결](#resolve-connection-errors)
- [연결 설정 변경](#change-connection-settings)
- [한 연결에서 팀 매핑 해제 및 다른 연결에 매핑](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [연결에 동기화 사용 안 함](#disable-sync-for-a-connection)

> [!NOTE]
> 이 문서에서는 마법사 또는 PowerShell을 사용하여 Blue Yonder WFM 대한 연결을 이미 설정했음을 가정합니다.

## <a name="before-you-begin"></a>시작하기 전에

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>환경 설정

> [!NOTE]
> 이 문서의 명령 또는 스크립트를 실행하기 전에 다음 단계에 따라 환경을 설정해야 합니다.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

7. Teams에 연결합니다.

    ```powershell
    Connect-MicrosoftTeams
    ```

    메시지가 표시되면 관리자 자격 증명을 사용하여 로그인합니다. 이제 이 문서 및 Shifts 커넥터 cmdlet의 스크립트를 실행하도록 설정되었습니다.

## <a name="check-connection-setup-status"></a>연결 설정 상태 확인

<a name="setup_status"> </a>

전자 메일에서 받은 작업 ID를 사용하여 설정한 연결 상태를 확인하려면 다음을 수행합니다.

1. [환경을 설정합니다](#set-up-your-environment) (아직 설정하지 않은 경우).
1. 다음 명령을 실행합니다. 이 명령은 연결에 대한 팀 매핑의 전반적인 상태를 제공합니다.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

자세한 내용은 [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)을 참조하세요.

## <a name="view-an-error-report-for-a-connection"></a>연결에 대한 오류 보고서 보기

<a name="error_report"> </a>

연결에 대한 오류 세부 정보를 표시하는 보고서를 실행할 수 있습니다. 보고서에는 성공하고 실패한 팀 및 사용자 매핑이 나열됩니다. 또한 연결과 연결된 계정과 관련된 문제에 대한 정보도 제공합니다.

1. [환경을 설정합니다](#set-up-your-environment) (아직 설정하지 않은 경우).
1. 연결에 대한 오류 보고서 목록을 가져옵니다.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 특정 오류 보고서를 보려면 다음 명령을 실행합니다.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

자세한 내용은 [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)를 참조하세요.

## <a name="resolve-connection-errors"></a>연결 오류 해결

### <a name="user-mapping-errors"></a>사용자 매핑 오류

Blue Yonder WFM 인스턴스에 있는 하나 이상의 사용자가 Teams에서 매핑된 팀의 구성원이 아닌 경우 사용자 매핑 오류가 발생할 수 있습니다. 이 문제를 해결하려면 매핑된 팀의 사용자가 Blue Yonder WFM 인스턴스의 사용자와 일치하는지 확인합니다.

매핑되지 않은 사용자의 세부 정보를 보려면 [환경을 설정한](#set-up-your-environment) 다음(아직 없는 경우) 다음 스크립트를 실행합니다.

```powershell
#View sync errors script
Write-Host "View sync errors"
Start-Sleep 1

#Ensure Teams module is of version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to retrieve user sync results from'
}
else {
    throw "Instance list is empty"
}

#Get a list of the mappings
Write-Host "Listing team mappings"
$mappings = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $mappings

#For each mapping, retrieve the failed mappings
ForEach ($mapping in $mappings){
    $teamsTeamId = $mapping.TeamId
    $wfmTeamId = $mapping.WfmTeamId
    Write-Host "Failed mapped users in the mapping of ${teamsTeamId} and ${wfmTeamId}:"
    $userSyncResult = Get-CsTeamsShiftsConnectionSyncResult -ConnectorInstanceId $InstanceId -TeamId $teamsTeamId
    Write-Host "Failed AAD users:"
    write $userSyncResult.FailedAadUser
    Write-Host "Failed WFM users:"
    write $userSyncResult.FailedWfmUser
}
```

### <a name="account-authorization-errors"></a>계정 권한 부여 오류

Blue Yonder WFM 서비스 계정 또는 Microsoft 365 시스템 계정 자격 증명이 잘못되었거나 필요한 권한이 없는 경우 계정 권한 부여 오류가 발생할 수 있습니다.

연결에 대한 Blue Yonder WFM 서비스 계정 또는 Microsoft 365 시스템 계정 자격 증명을 변경하려면 [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) cmdlet을 실행하거나 이 문서의 [연결 설정 변경](#change-connection-settings) 섹션에서 PowerShell 스크립트를 사용할 수 있습니다.

## <a name="change-connection-settings"></a>연결 설정 변경
<a name="change_settings"> </a>

이 스크립트를 사용하여 연결 설정을 변경합니다. 변경할 수 있는 설정에는 Blue Yonder WFM 서비스 계정 및 암호, Microsoft 365 시스템 계정, 팀 매핑 및 동기화 설정이 포함됩니다.

동기화 설정에는 동기화 빈도(분)와 Blue Yonder WFM 및 Shifts 간에 동기화되는 일정 데이터가 포함됩니다. 일정 데이터는 [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)를 실행하여 볼 수 있는 다음 매개 변수에 정의되어 있습니다.

- **enabledConnectorScenarios** 매개 변수는 Blue Yonder WFM Shifts로 동기화되는 데이터를 정의합니다. 옵션은 ,, `SwapRequest`, `UserShiftPreferences``OpenShift``OpenShiftRequest`, `TimeOff`, `TimeOffRequest`입니다.`Shift`
- **enabledWfiScenarios** 매개 변수는 Shifts에서 Blue Yonder WFM 동기화되는 데이터를 정의합니다. `SwapRequest`옵션은 , `OpenShiftRequest`, `TimeOffRequest``UserShiftPreferences`.

    > [!NOTE]
    > 교대 근무 열기, 교대 근무 요청 열기, 교환 요청 또는 Shifts와 Blue Yonder WFM 간의 시간 쉬는 요청을 동기화하지 않도록 선택하는 경우 Shifts에서 기능을 숨기기 위해 수행해야 하는 또 다른 단계가 있습니다. 이 스크립트를 실행한 후 이 문서의 뒷부분에 있는 [열린 교대 근무 사용 안 함, 교대 근무 요청 열기, 요청 교환 및 시간 끄기 요청](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) 섹션의 단계를 수행해야 합니다.

> [!IMPORTANT]
> 변경하지 않으려는 설정의 경우 스크립트에서 메시지가 표시되면 원래 설정을 다시 입력해야 합니다.

[환경을 설정한](#set-up-your-environment) 다음(아직 설치하지 않은 경우) 다음 스크립트를 실행합니다.

```powershell
#Update connector instance and mapping script
Write-Host "Update connector instance and mapping"
Start-Sleep 1

#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#Connect to MS Graph
Connect-MgGraph -Scopes "User.Read.All","Group.ReadWrite.All"

#List connector types available (comment out if not implemented for preview)
Write-Host "Listing connector types available"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$connectors = Get-CsTeamsShiftsConnectionConnector
write $connectors
$blueYonder = $connectors | where {$_.Id -match $BlueYonderId}

#List connection instances available
Write-Host "Listing connection instances available"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Prompt for the WFM username and password
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Get the instance ID
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$InstanceId = Read-Host -Prompt 'Input the instance ID that you want to update'
$Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
$Etag = $Instance.etag

#Change sync setting
$designatorName = Read-Host -Prompt "Input designated actor's user name"
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$UpdatedInstanceName = Read-Host -Prompt 'Input new connection instance name'
$updatedConnectorScenarioString = Read-Host -Prompt 'Input new enabled connector scenarios'
$updatedWfiScenarioString = Read-Host -Prompt 'Input new enabled WFI scenarios'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$updatedConnectorScenario = $updatedConnectorScenarioString -Split {$Delimiters -contains $_}
$updatedConnectorScenario = $updatedConnectorScenario.Trim()
$updatedConnectorScenario = $updatedConnectorScenario.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
$updatedWfiScenario = $updatedWfiScenarioString -Split {$Delimiters -contains $_}
$updatedWfiScenario = $updatedWfiScenario.Trim()
$updatedWfiScenario = $updatedWfiScenario.Split('', [System.StringSplitOptions]::RemoveEmptyEntries)
$adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
$cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
$essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
$federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
$retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
$siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
$syncFreq = Read-Host -Prompt 'Input new sync frequency'

#Read admin email list
[psobject[]]$AdminEmailList = @()
while ($true){
$AdminEmail = Read-Host -Prompt "Enter admin's email to receive error report"
$AdminEmailList += $AdminEmail
$title    = 'Adding another email'
$question = 'Would you like to add another admin email?'
$choices  = '&Yes', '&No'
$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $teamsUserId -EnabledConnectorScenario $updatedConnectorScenario -EnabledWfiScenario $updatedWfiScenario -Name $UpdatedInstanceName -SyncFrequencyInMin $syncFreq -IfMatch $Etag -ConnectorAdminEmail $AdminEmailList

#Get a list of the mappings
Write-Host "Listing mappings"
$TeamMaps = Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId
write $TeamMaps

#Modify a mapping
#Remove a mapping
Write-Host "Removing a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to unlink'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to unlink'
Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId
Write-Host "Success"

#Add a mapping
Write-Host "Adding a mapping"
$TeamsTeamId = Read-Host -Prompt 'Input the Teams team ID that you want to link'
$WfmTeamId = Read-Host -Prompt 'Input the WFM team ID that you want to link'
New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone "America/Los_Angeles" -WfmTeamId $WfmTeamId
Write-Host "Success"
```

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>열린 교대 근무를 사용하지 않도록 설정, 교대 근무 요청 열기, 요청 교환 및 쉬는 시간 요청

> [!IMPORTANT]
> 이 문서의 앞부분에 있는 [연결 설정 변경](#change-connection-settings) 섹션의 스크립트를 사용하거나 [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance) cmdlet을 사용하여 열린 교대 근무를 사용하지 않도록 설정하거나, 교대 근무 요청을 열거나, 요청을 교환하거나, 쉬는 시간 요청을 사용하지 않도록 선택한 경우에만 다음 단계를 수행합니다. 이 단계를 완료하면 Shifts의 기능이 숨겨지게 됩니다. 이 두 번째 단계가 없으면 사용자는 Shifts의 기능을 계속 볼 수 있으며 이를 사용하려고 하면 "지원되지 않는 작업" 오류 메시지가 표시됩니다.

Shifts에서 열린 교대 근무, 교환 요청 및 시간 쉬는 요청을 숨기려면 Graph API [일정 리소스 유형을](/graph/api/resources/schedule) 사용하여 Blue Yonder WFM 인스턴스에 매핑한 각 팀에 대해 다음 매개 변수 ```false``` 를 설정합니다.

- 교대 근무 열기: ```openShiftsEnabled```
- 교환 요청:  ```swapShiftsRequestsEnabled```
- 시간 제한 요청: ```timeOffRequestsEnabled```

Shifts에서 열린 교대 근무 요청을 숨기려면 Shifts의 **설정** 으로 이동한 다음 **교대 근무 열기** 설정을 해제합니다.

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>한 연결에서 팀 매핑 해제 및 다른 연결에 매핑

> [!NOTE]
> Microsoft 365 시스템 계정은 두 연결 모두에 대해 동일해야 합니다. 그렇지 않은 경우 "지정된 행위자 프로필에 팀 소유권 권한이 없습니다." 오류 메시지가 표시됩니다.

한 연결에서 팀 매핑을 해제하고 다른 연결에 매핑하려면 다음을 수행합니다.

1. [환경을 설정합니다](#set-up-your-environment) (아직 설정하지 않은 경우).
1. 연결에 대한 모든 팀 매핑 목록을 봅니다.

    ```powershell
    Get-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 연결에서 팀 매핑을 제거합니다.

    ```powershell
    Remove-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId>
    ```

1. 팀을 다른 연결에 매핑합니다.

    ```powershell
    New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId <ConnectorInstanceId> -TeamId <TeamId> -WfmTeamId <SiteId> -TimeZone <TimeZone>
    ```

자세한 내용은 [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap) 및 [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)을 참조하세요.

## <a name="disable-sync-for-a-connection"></a>연결에 동기화 사용 안 함

이 스크립트를 사용하여 연결에 대한 동기화를 사용하지 않도록 설정합니다. 이 스크립트는 연결을 제거하거나 삭제하지 않습니다. 지정한 연결에 대해 Shifts와 Blue Yonder WFM 간에 데이터가 동기화되지 않도록 동기화를 해제합니다.

[환경을 설정한](#set-up-your-environment) 다음(아직 설치하지 않은 경우) 다음 스크립트를 실행합니다.

```powershell
#Disable sync script
Write-Host "Disable sync"
#Ensure Teams module is at least version x
Write-Host "Checking Teams module version"
try {
    Get-InstalledModule -Name "MicrosoftTeams" -MinimumVersion 4.1.0
} catch {
    throw
}

#List connection instances available
Write-Host "Listing connection instances"
$InstanceList = Get-CsTeamsShiftsConnectionInstance
write $InstanceList

#Get an instance
if ($InstanceList.Count -gt 0){
    $InstanceId = Read-Host -Prompt 'Input the instance ID that you want to disable sync'
    $Instance = Get-CsTeamsShiftsConnectionInstance -ConnectorInstanceId $InstanceId
    $Etag = $Instance.etag
    $InstanceName = $Instance.Name
    $DesignatedActorId = $Instance.designatedActorId
    $adminApiUrl = $Instance.ConnectorSpecificSettingAdminApiUrl
    $cookieAuthUrl = $Instance.ConnectorSpecificSettingCookieAuthUrl
    $essApiUrl = $Instance.ConnectorSpecificSettingEssApiUrl
    $federatedAuthUrl = $Instance.ConnectorSpecificSettingFederatedAuthUrl
    $retailWebApiUrl = $Instance.ConnectorSpecificSettingRetailWebApiUrl
    $siteManagerUrl = $Instance.ConnectorSpecificSettingSiteManagerUrl
    $ConnectorAdminEmail = $Instance.ConnectorAdminEmail
}
else {
    throw "Instance list is empty"
}

#Remove scenarios in the mapping
Write-Host "Disabling scenarios in the team mapping"
$UpdatedInstanceName = $InstanceName + " - Disabled"
$BlueYonderId = "6A51B888-FF44-4FEA-82E1-839401E9CD74"
$WfmUserName = Read-Host -Prompt 'Input your WFM user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

$UpdatedInstance = Set-CsTeamsShiftsConnectionInstance -ConnectorId $BlueYonderId -ConnectorInstanceId $InstanceId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -DesignatedActorId $DesignatedActorId -EnabledConnectorScenario @() -EnabledWfiScenario @() -Name $UpdatedInstanceName -SyncFrequencyInMin 60 -IfMatch $Etag -ConnectorAdminEmail $ConnectorAdminEmail

if ($UpdatedInstance.Id -ne $null) {
    Write-Host "Success"
}
else {
    throw "Update instance failed"
}
```

## <a name="shifts-connector-cmdlets"></a>Shifts 커넥터 cmdlet

Shifts 커넥터 cmdlet에 대한 도움말을 보려면 [Teams PowerShell cmdlet 참조](/powershell/teams/intro)에서 **CsTeamsShiftsConnection** 을 검색합니다. 다음은 일반적으로 사용되는 몇 가지 cmdlet에 대한 링크입니다.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord)

## <a name="related-articles"></a>관련 기사

- [Shifts 커넥터](shifts-connectors.md)
- [Shifts 커넥터 마법사를 사용하여 Shifts를 Blue Yonder Workforce Management 연결](shifts-connector-wizard.md)
- [PowerShell을 사용하여 Shifts를 Blue Yonder Workforce Management 연결](shifts-connector-blue-yonder-powershell-setup.md)
- [Shifts 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 개요](../../teams-powershell-overview.md)
