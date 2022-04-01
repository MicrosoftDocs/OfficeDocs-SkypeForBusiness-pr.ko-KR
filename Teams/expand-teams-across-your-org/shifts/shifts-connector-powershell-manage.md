---
title: PowerShell을 사용하여 Blue Yonder Workforce Management에 대한 Shifts 연결을 관리합니다.
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: PowerShell을 사용하여 Blue Yonder Workforce Management에 대한 Shifts 연결을 관리하는 방법에 대해 자세히 알아보습니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: e666117b31064697f9ef41299574935109015aba
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593693"
---
# <a name="use-powershell-to-manage-your-shifts-connection-to-blue-yonder-workforce-management"></a>PowerShell을 사용하여 Blue Yonder Workforce Management에 대한 Shifts 연결을 관리합니다.

## <a name="overview"></a>개요

Blue [Yonder용 Microsoft Teams Shifts](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) 커넥터를 사용하면 Blue Yonder WFM(Blue Yonder Workforce Management)Microsoft Teams Shifts 앱을 통합할 수 있습니다. 연결을 설정한 후 프런트라인 작업자는 Shifts 내에서 Blue Yonder WFM에서 일정을 원활하게 보고 관리할 수 있습니다.

연결 또는 [PowerShell](shifts-connector-blue-yonder-powershell-setup.md)의 [Shifts](shifts-connector-wizard.md) 커넥터 Microsoft 365 관리 센터 사용하여 연결을 설정할 수 있습니다. 연결이 설정된 후 [Shifts 커넥터 PowerShell cmdlet](#shifts-connector-cmdlets)을 사용하여 관리합니다.

이 문서에서는 PowerShell을 사용하여 다음을 하는 방법을 설명합니다.

- [연결 설정 상태 확인](#check-connection-setup-status)
- [연결에 대한 오류 보고서 보기](#view-an-error-report-for-a-connection)
- [연결 오류 해결](#resolve-connection-errors)
- [연결 설정 변경](#change-connection-settings)
- [한 연결에서 팀 매핑을 끊고 다른 연결에 매핑](#unmap-a-team-from-one-connection-and-map-it-to-another-connection)
- [연결에 대한 동기화 사용 안 하여](#disable-sync-for-a-connection)

> [!NOTE]
> 이 문서에서는 마법사 또는 PowerShell을 사용하여 Blue Yonder WFM에 대한 연결을 이미 설정했다고 가정합니다.

## <a name="before-you-begin"></a>시작하기 전에

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>환경 설정

> [!NOTE]
> 이 문서에서 명령 또는 스크립트를 실행하기 전에 다음 단계를 수행하여 환경을 설정해야 합니다.

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="check-connection-setup-status"></a>연결 설정 상태 확인
<a name="setup_status"> </a>

전자 메일로 받은 작업 ID를 사용하여 설정한 연결 상태를 확인하면 다음을 수행하세요.

1. [환경을 설정](#set-up-your-environment) 합니다(아직 없는 경우).
1. 다음 명령을 실행합니다. 이 명령은 연결에 대한 팀 매핑의 전체 상태를 제공합니다.

    ``` powershell
    Get-CsTeamsShiftsConnectionOperation -OperationId <YourOperationId>
    ```

자세한 내용은 [Get-CsTeamsShiftsConnectionOperation을 참조합니다](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps).

## <a name="view-an-error-report-for-a-connection"></a>연결에 대한 오류 보고서 보기
<a name="error_report"> </a>

연결에 대한 오류 세부 정보를 표시하는 보고서를 실행할 수 있습니다. 보고서에는 성공 및 실패한 팀 및 사용자 매핑이 나열됩니다. 또한 연결과 연결된 계정과 관련된 문제에 대한 정보도 제공합니다.

1. [환경을 설정](#set-up-your-environment) 합니다(아직 없는 경우).
1. 연결에 대한 오류 보고서 목록을 확인합니다.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ConnectorInstanceId <ConnectorInstanceId>
    ```

1. 특정 오류 보고서를 보기 위해 다음 명령을 실행합니다.

    ``` powershell
    Get-CsTeamsShiftsConnectionErrorReport -ErrorReportId <ErrorReportId>
    ```

자세한 내용은 [Get-CsTeamsShiftsConnectionErrorReport를 참조합니다](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps).

## <a name="resolve-connection-errors"></a>연결 오류 해결

### <a name="user-mapping-errors"></a>사용자 매핑 오류

Blue Yonder WFM 사이트의 하나 이상의 사용자가 매핑된 팀의 구성원이 아닌 경우 사용자 매핑 오류가 Teams. 이 문제를 해결하기 위해 매핑된 팀의 사용자가 Blue Yonder WFM 사이트의 사용자와 일치하는지 확인하세요.

매핑되지 않은 사용자의 세부 정보를 보기 위해 환경을 설정한 [다음(아직](#set-up-your-environment) 없는 경우) 다음 스크립트를 실행합니다.

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

Blue Yonder WFM 서비스 계정 또는 시스템 Microsoft 365 자격 증명이 올바르지 않거나 필요한 권한이 없는 경우 계정 권한 부여 오류가 발생할 수 있습니다.

Blue Yonder WFM 서비스 계정을 변경하거나 Microsoft 365 시스템 계정 자격 증명을 변경하려면 [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) cmdlet을 실행하거나 이 문서의 연결 설정 변경 섹션에서 PowerShell 스크립트를 사용할 수 [](#change-connection-settings) 있습니다.

## <a name="change-connection-settings"></a>연결 설정 변경
<a name="change_settings"> </a>

이 스크립트를 사용하여 연결 설정을 변경합니다. 설정 변경하려면 Blue Yonder WFM 서비스 계정 및 암호, 시스템 계정, Microsoft 365 매핑 및 동기화 설정이 포함됩니다.

동기화 설정에는 동기화 빈도(분) 및 Blue Yonder WFM과 Shifts 간에 동기화되는 일정 데이터가 포함됩니다. 일정 데이터는 [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)를 실행하여 볼 수 있는 다음 매개 변수에 정의됩니다.

- **enabledConnectorScenarios 매개** 변수는 Blue Yonder WFM에서 Shifts로 동기화되는 데이터를 정의합니다. `Shift`옵션은 , `UserShiftPreferences``SwapRequest`, `OpenShift`, `OpenShiftRequest`, , `TimeOff`입니다`TimeOffRequest`.
- **enabledWfiScenarios 매개 변수** 는 Shifts에서 Blue Yonder WFM으로 동기화된 데이터를 정의합니다. `SwapRequest`옵션은 , `OpenShiftRequest`, `TimeOffRequest`입니다`UserShiftPreferences`.

    > [!NOTE]
    > Shifts와 Blue Yonder WFM 간에 열린 교대 근무, 열기 요청, 교환 요청 또는 시간 해제 요청을 동기화하지 않는 경우 Shifts에서 기능을 숨기기 위해 해야 할 또 다른 단계가 있습니다. 이 스크립트를 실행한 후 이 문서의 1부에서 열린 교대 근무 사용 안 의 단계를 수행하고, 교대 근무 요청을 열 [고,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) 요청 교환 및 시간 해제 요청 섹션을 수행해야 합니다.

> [!IMPORTANT]
> 변경하지 않는 설정의 경우 스크립트의 메시지가 표시될 때 원래 설정을 다시 입력해야 합니다.

[환경을 설정](#set-up-your-environment) 한 다음(아직 없는 경우) 다음 스크립트를 실행합니다.

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>열려 있는 교대 근무를 사용하지 않도록 설정, 교대 근무 요청 열기, 요청 교환 및 시간 해제 요청

> [!IMPORTANT]
> 이 문서의 앞부분에 있는 연결 설정 변경 섹션에서 스크립트를 사용하여 또는 [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps) cmdlet을 사용하여 열기 교대 근무, 교대 근무 요청 열기, 요청 교환 또는 시간 해제 요청을 사용하지 않도록 선택한 경우만 다음 단계를 수행합니다.[](#change-connection-settings) 이 단계를 완료하면 Shifts의 기능이 숨겨지게됩니다. 이 두 번째 단계가 없는 경우 사용자는 Shifts의 기능을 계속 볼 수 있으며, 이를 사용하려고 하면 "지원되지 않는 작업" 오류 메시지가 표시됩니다.

Shifts에서 열린 교대 근무, 요청 [교환 및 시간](/graph/api/resources/schedule?view=graph-rest-1.0) 해제 요청을 숨기기 위해 ```false``` Graph API 예약 리소스 유형을 사용하여 Blue Yonder WFM 사이트에 매핑한 각 팀에 대해 다음 매개 변수를 설정합니다.

- 교대 근무 열기: ```openShiftsEnabled```
- 교환 요청:  ```swapShiftsRequestsEnabled```
- 시간 해제 요청: ```timeOffRequestsEnabled```

Shifts에서 열기 **교** 대 근무 요청을 숨기기 위해 shifts에서 설정 이동한 다음, 열기 교대 근무 **설정을 해제합니다**.

## <a name="unmap-a-team-from-one-connection-and-map-it-to-another-connection"></a>한 연결에서 팀 매핑을 끊고 다른 연결에 매핑

> [!NOTE]
> Microsoft 365 시스템 계정은 두 연결에 대해 동일해야 합니다. 그렇지 않은 경우 "이 지정된 액터 프로필에 팀 소유권 권한이 없습니다" 오류 메시지가 표시됩니다.

한 연결에서 팀의 매핑을 끊고 다른 연결에 매핑하려는 경우:

1. [환경을 설정](#set-up-your-environment) 합니다(아직 없는 경우).
1. 연결에 대한 모든 팀 매핑 목록을  확인합니다.

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

자세한 내용은 [Get-CsTeamsShiftsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps), [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps) 및 [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)을 참조합니다.

## <a name="disable-sync-for-a-connection"></a>연결에 대한 동기화 사용 안 하여

이 스크립트를 사용하여 연결에 대한 동기화를 사용하지 않도록 설정합니다. 이 스크립트는 연결을 제거하거나 삭제하지 않습니다. 지정한 연결에 대해 Shifts와 Blue Yonder WFM 간에 데이터가 동기화되지 않습니다.

[환경을 설정](#set-up-your-environment) 한 다음(아직 없는 경우) 다음 스크립트를 실행합니다.

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

#Authenticate with powershell as to the authorization capabilities of the caller. 
#Connect to Teams
Write-Host "Connecting to Teams"
Connect-MicrosoftTeams
Write-Host "Connected"

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

Shifts 커넥터 cmdlet에 대한 도움말은 [PowerShell cmdlet](/powershell/teams/intro?view=teams-ps) 참조에서 **CsTeamsShiftsConnection** 을 Teams 검색합니다. 다음은 일반적으로 사용되는 몇 가지 cmdlet에 대한 링크입니다.

- [Get-CsTeamsShiftsConnectionOperation](/powershell/module/teams/get-csteamsshiftsconnectionoperation?view=teams-ps)
- [New-CsTeamsShiftsConnectionInstance](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps)
- [Get-CsTeamsShiftsConnectionInstance](/powershell/module/teams/get-csteamsshiftsconnectioninstance?view=teams-ps)
- [Set-CsTeamsShiftsConnectionInstance](/powershell/module/teams/set-csteamsshiftsconnectioninstance?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionInstance](/powershell/module/teams/remove-csteamsshiftsconnectioninstance?view=teams-ps)
- [Test-CsTeamsShiftsConnectionValidate](/powershell/module/teams/test-csteamsshiftsconnectionvalidate?view=teams-ps)
- [New-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/new-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/get-csteamsshiftsconnectionteammap?view=teams-ps)
- [Remove-CsTeamsShiftsConnectionTeamMap](/powershell/module/teams/remove-csteamsshiftsconnectionteammap?view=teams-ps)
- [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps)
- [Get-CsTeamsShiftsConnectionSyncResult](/powershell/module/teams/get-csteamsshiftsconnectionsyncresult?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmUser](/powershell/module/teams/get-csteamsshiftsconnectionwfmuser?view=teams-ps)
- [Get-CsTeamsShiftsConnectionWfmTeam](/powershell/module/teams/get-csteamsshiftsconnectionwfmteam?view=teams-ps)
- [Get-CsTeamsShiftsConnectionErrorReport](/powershell/module/teams/get-csteamsshiftsconnectionerrorreport?view=teams-ps)
- [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps)

## <a name="related-articles"></a>관련 기사

- [Shifts 커넥터](shifts-connectors.md)
- [Shifts 커넥터 마법사를 사용하여 Shifts를 Blue Yonder Workforce Management에 연결](shifts-connector-wizard.md)
- [PowerShell을 사용하여 Shifts를 Blue Yonder Workforce Management에 연결](shifts-connector-blue-yonder-powershell-setup.md)
- [Shifts 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 개요](../../teams-powershell-overview.md)