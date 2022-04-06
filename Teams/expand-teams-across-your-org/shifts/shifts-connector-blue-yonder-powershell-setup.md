---
title: PowerShell을 사용하여 Shifts를 Blue Yonder Workforce Management에 연결
author: LanaChin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: PowerShell을 사용하여 Shifts를 Blue Yonder Workforce Management와 통합하는 방법을 알아보고자 합니다.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9b78f45919649fda29f09ea338a160c2ab376c1a
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593711"
---
# <a name="use-powershell-to-connect-shifts-to-blue-yonder-workforce-management"></a>PowerShell을 사용하여 Shifts를 Blue Yonder Workforce Management에 연결

## <a name="overview"></a>개요

Blue [Yonder용 Microsoft Teams Shifts](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder) 커넥터를 사용하여 Blue Yonder WFM(Blue Yonder Workforce Management)Microsoft Teams Shifts 앱을 통합합니다. 연결이 설정된 후 프런트라인 작업자는 Shifts 내에서 Blue Yonder WFM에서 일정을 원활하게 보고 관리할 수 있습니다.

이 문서에서는 PowerShell을 사용하여 Shifts를 Blue Yonder WFM과 통합하도록 커넥터를 설정하고 구성하는 방법을 제공합니다.

연결을 설정하기 위해 PowerShell 스크립트를 실행합니다. 스크립트는 커넥터를 구성하고, 동기화 설정을 적용하고, 연결을 만들고, Blue Yonder WFM 사이트를 팀에 매핑합니다. 동기화 설정은 Shifts에서 사용하도록 설정된 기능과 Blue Yonder WFM과 Shifts 간에 동기화되는 일정 정보를 확인합니다. 매핑은 Blue Yonder WFM 사이트와 팀 간의 동기화 관계를 Teams. 기존 팀 및 새 팀에 매핑할 수 있습니다.

두 개의 스크립트를 제공합니다. 기존 팀에 매핑할지 아니면 매핑할 새 팀을 만들지 여부에 따라 스크립트를 사용할 수 있습니다.

서로 다른 동기화 설정을 사용하여 여러 연결을 설정할 수 있습니다. 예를 들어 조직에 일정 요구 사항이 서로 다른 여러 위치가 있는 경우 각 위치에 대해 고유한 동기화 설정이 있는 연결을 만들 수 있습니다. Blue Yonder WFM 사이트는 주어진 시간의 한 팀에만 매핑될 수 있습니다. 사이트가 팀에 이미 매핑된 경우 다른 팀에 매핑할 수 없습니다.

Blue Yonder WFM을 레코드 시스템으로 사용하여 일선 작업자는 교대 근무를 보고 교환하고, 가용성을 관리하며, 디바이스의 Shifts에서 시간을 요청할 수 있습니다. 프런트라인 관리자는 Blue Yonder WFM을 사용하여 일정을 설정할 수 있습니다.

> [!NOTE]
> 또한 이동 커넥터 마법사를 사용하여 [Microsoft 365 관리 센터](shifts-connector-wizard.md) WFM에 Shifts를 연결할 수 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

### <a name="prerequisites"></a>필수 구성 요소

[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

### <a name="admin-role-to-manage-the-connector-using-powershell"></a>PowerShell을 사용하여 커넥터를 관리하는 관리자 역할

[!INCLUDE [shifts-connector-admin-role](../../includes/shifts-connector-admin-role.md)]

## <a name="set-up-your-environment"></a>환경 설정

[!INCLUDE [shifts-connector-set-up-environment](../../includes/shifts-connector-set-up-environment.md)]

## <a name="identify-the-teams-you-want-to-map"></a>매핑할 팀 식별

> [!NOTE]
> Blue Yonder WFM 사이트를 기존 팀에 매핑하는 경우 이 단계를 완료합니다. 매핑할 새 팀을 만드는 경우 이 단계를 건너뛸 수 있습니다.

Azure Portal 모든 그룹 페이지로 이동하여 조직의 TeamsIds 목록을 얻습니다.[](https://ms.portal.azure.com/#blade/Microsoft_AAD_IAM/GroupsManagementMenuBlade/AllGroups)

매핑하려는 팀의 TeamId를 메모합니다. 이 정보를 입력하라는 메시지가 스크립트에 표시됩니다.

> [!NOTE]
> 하나 이상의 팀에 기존 일정이 있는 경우 스크립트는 해당 팀에서 일정을 제거합니다. 그렇지 않으면 중복된 교대 근무가 표시됩니다.

## <a name="run-the-script"></a>스크립트 실행

스크립트를 실행합니다.

- 연결을 설정하고 매핑할 새 팀을 만들 경우 이 [스크립트를 실행합니다](#set-up-a-connection-and-create-new-teams-to-map).
- 연결을 설정하고 기존 팀에 매핑하기 위해 이 [스크립트를 실행합니다](#set-up-a-connection-and-map-to-existing-teams).

스크립트는 다음 작업을 수행합니다. 설정 및 구성 세부 정보를 입력하라는 메시지가 표시됩니다.

1. 입력한 Blue Yonder WFM 서비스 계정 자격 증명 및 서비스 URL을 사용하여 Blue Yonder WFM에 대한 연결을 테스트하고 확인합니다.
1. Shifts 커넥터를 구성합니다.
1. 동기화 설정을 적용합니다. 이러한 설정에는 동기화 빈도(분) 및 Blue Yonder WFM과 Shifts 간에 동기화되는 일정 데이터가 포함됩니다. 일정 데이터는 다음 매개 변수에 정의됩니다.

    - **enabledConnectorScenarios 매개** 변수는 Blue Yonder WFM에서 Shifts로 동기화되는 데이터를 정의합니다. `Shift`옵션은 , `UserShiftPreferences``SwapRequest`, `OpenShift`, `OpenShiftRequest`, , `TimeOff`입니다`TimeOffRequest`.
    - **enabledWfiScenarios 매개 변수** 는 Shifts에서 Blue Yonder WFM으로 동기화된 데이터를 정의합니다. `SwapRequest`옵션은 , `OpenShiftRequest`, `TimeOffRequest`입니다`UserShiftPreferences`.

    자세한 내용은 [New-CsTeamsShiftsConnectionInstance를 참조합니다](/powershell/module/teams/new-csteamsshiftsconnectioninstance?view=teams-ps). 각 매개 변수에 대해 지원되는 동기화 옵션 목록을 표시하기 위해 [Get-CsTeamsShiftsConnectionConnector를 실행합니다](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps).

    > [!IMPORTANT]
    > 스크립트를 사용하면 이러한 모든 옵션에 대해 동기화할 수 있습니다. 동기화 설정을 변경하려면 연결이 설정된 후에 변경할 수 있습니다. 자세한 내용은 [PowerShell을 사용하여 Blue Yonder Workforce Management에 대한 Shifts 연결을 관리합니다](shifts-connector-powershell-manage.md).

1. 연결을 만듭니다.
1. 지도 Blue Yonder WFM 사이트를 팀에 제공합니다. 매핑은 실행되는 스크립트에 따라 입력하거나 만든 새 팀에 입력하는 Blue Yonder WFM 사이트 아이디 및 TeamId를 기반으로 합니다. 팀에 기존 일정이 있는 경우 스크립트는 지정한 날짜 및 시간 범위에 대한 일정 데이터를 제거합니다.

화면의 성공 메시지는 연결이 성공적으로 설정되어 있는 것을 나타냅니다.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>연결을 변경해야 하는 경우

설정한 후 연결을 변경하기 위해 [PowerShell을 사용하여 Blue Yonder Workforce Management에 대한 Shifts 연결을 관리합니다](shifts-connector-powershell-manage.md). 예를 들어 동기화 설정을 업데이트하고, 팀 매핑을 업데이트하고, 연결에 대한 동기화를 사용하지 않도록 설정할 수 있습니다.

## <a name="scripts"></a>스크립트

### <a name="set-up-a-connection-and-create-new-teams-to-map"></a>연결 설정 및 매핑할 새 팀 만들기

```powershell
#Map WFM sites to teams script
Write-Host "Map WFM sites to teams"
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
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM super user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName 
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create an instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Enter your Microsoft 365's user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency"

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
$InstanceResponse = New-CsTeamsShiftsConnectionInstance -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -DesignatedActorId $teamsUserId -EnabledConnectorScenario $enabledConnectorScenario -EnabledWfiScenario $wfiSupportedScenario -SyncFrequencyInMin $syncFreq -ConnectorAdminEmail $AdminEmailList
$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Suceess"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of sites
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if ($WfmTeamIds -ne $NULL && $WfmTeamIds.Count -gt 0){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles 
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

#Create a new Teams team with owner set to system account and name set to the site name
Write-Host "Creating a Teams team"
$teamsTeamName = Read-Host -Prompt "Input the Teams team name"
$Team = New-Team -DisplayName $teamsTeamName -Visibility "Public" -Owner $teamsUserId
Write-Host "Success"
$TeamsTeamId=$Team.GroupId

#add users to the Team for Shifts
Write-Host "Adding users to Teams team"
$currentUser = Read-Host -Prompt "Input the current user's user name or ID"
Add-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
$failedWfmUsers=@()
foreach ($user in $WFMUsers) {
    try {
    $userEmail = $user.Name + "@" +$domain
    Add-TeamUser -GroupId $TeamsTeamId -User $userEmail
    } catch {
        $failedWfmUsers+=$user
    }
}
if($failedWfmUsers.Count -gt 0){
    Write-Host "There are WFM users not existed in Teams tenant:"
    write $failedWfmUsers
}

#Enable scheduling in the group
$RequestBody = @{
    Enabled = $true
    TimeZone = "America/Los_Angeles"
}
$teamUpdateUrl="https://graph.microsoft.com/v1.0/teams/"+$TeamsTeamId+"/schedule"
$Schedule = Invoke-MgGraphRequest -Uri $teamUpdateUrl -Method PUT -Body $RequestBody

#Create a mapping of the new team to the site 
Write-Host "Create a mapping of the new team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"

$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}

#The Teams admin was set as an owner directly when creating a new team, removing it from owners
Remove-TeamUser -GroupId $TeamsTeamId -User $currentUser -Role Owner
Disconnect-MgGraph
Disconnect-MicrosoftTeams
```

### <a name="set-up-a-connection-and-map-to-existing-teams"></a>기존 팀에 연결 및 매핑 설정

```powershell
#Map WFM sites to existing teams script
Write-Host "Map WFM sites to existing teams"
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
$enabledConnectorScenario = $blueYonder.SupportedScenario
$wfiSupportedScenario = $blueYonder.wfiSupportedScenario

#Prompt for entering of WFM username and password 
$WfmUserName = Read-Host -Prompt 'Input your WFM super user name'
$WfmPwd = Read-Host -Prompt 'Input your WFM password' -AsSecureString
$plainPwd =[Runtime.InteropServices.Marshal]::PtrToStringAuto([Runtime.InteropServices.Marshal]::SecureStringToBSTR($WfmPwd))

#Test connection settings
Write-Host "Testing connection settings"
$InstanceName = Read-Host -Prompt 'Input connection instance name'
$adminApiUrl = Read-Host -Prompt 'Input admin api url'
$cookieAuthUrl = Read-Host -Prompt 'Input cookie authorization url'
$essApiUrl = Read-Host -Prompt 'Input ess api url'
$federatedAuthUrl = Read-Host -Prompt 'Input federated authorization url'
$retailWebApiUrl = Read-Host -Prompt 'Input retail web api url'
$siteManagerUrl = Read-Host -Prompt 'Input site manager url'
$testResult = Test-CsTeamsShiftsConnectionValidate -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName 
if ($testResult.Code -ne $NULL) {
    write $testResult
    throw "Validation failed, conflict found"
}
Write-Host "Test complete, no conflicts found"

#Create an instance (includes WFM site team ids)
Write-Host "Creating a connection instance"
$designatorName = Read-Host -Prompt "Enter your Microsoft 365 user name"
$domain = $designatorName.Split("@")[1]
$designator = Get-MgUser -UserId $designatorName
$teamsUserId = $designator.Id
$syncFreq = Read-Host -Prompt "Input sync frequency in minutes. Value should be equal to or more than 10."

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
$InstanceResponse = New-CsTeamsShiftsConnectionInstance -Name $InstanceName -ConnectorId $BlueYonderId -ConnectorSpecificSettingAdminApiUrl $adminApiUrl -ConnectorSpecificSettingCookieAuthUrl $cookieAuthUrl -ConnectorSpecificSettingEssApiUrl $essApiUrl -ConnectorSpecificSettingFederatedAuthUrl $federatedAuthUrl -ConnectorSpecificSettingRetailWebApiUrl $retailWebApiUrl -ConnectorSpecificSettingSiteManagerUrl $siteManagerUrl -ConnectorSpecificSettingLoginPwd $plainPwd -ConnectorSpecificSettingLoginUserName $WfmUserName -DesignatedActorId $teamsUserId -EnabledConnectorScenario $enabledConnectorScenario -EnabledWfiScenario $wfiSupportedScenario -SyncFrequencyInMin $syncFreq -ConnectorAdminEmail AdminEmailList

$InstanceId = $InstanceResponse.id
$Etag = $InstanceResponse.etag
if ($InstanceId -ne $null){
    Write-Host "Success"
} else {
    throw "Connector instance creation failed"
}

#Retrieve the list of sites
Write-Host "Listing the WFM team sites"
$WfmTeamIds = Get-CsTeamsShiftsConnectionWfmTeam -ConnectorInstanceId $InstanceId
write $WfmTeamIds
if ($WfmTeamIds -ne $NULL && $WfmTeamIds.Count -gt 0){
    [System.String]$WfmTeamId = Read-Host -Prompt "Input the ID of WFM team you want to map"
}
else {
    throw "The WfmTeamId list is null or empty"
}

#Retrieve the list of WFM users and their roles 
Write-Host "Listing WFM users and roles"
$WFMUsers = Get-CsTeamsShiftsConnectionWfmUser -ConnectorInstanceId $InstanceId -WfmTeamId $WfmTeamId
write $WFMUsers

#Keep mapping teams until user stops it
while ($true)
{

$TeamsTeamId = Read-Host -Prompt "Input the ID of the Teams team to be mapped"
#Clear schedule of the Teams team
Write-Host "Clear schedule of the existing team"
$startTime = Read-Host -Prompt "Input the start time of clear schedule"
$endTime = Read-Host -Prompt "Input the end time of clear schedule"

$entityTypeString = Read-Host -Prompt 'Input the entity types of clear schedule'
$Delimiters = ",", ".", ":", ";", " ", "`t"
$entityType = $entityTypeString -Split {$Delimiters -contains $_}
$entityType = $entityType.Trim()
$entityType = $entityType.Split('',[System.StringSplitOptions]::RemoveEmptyEntries)
Remove-CsTeamsShiftsScheduleRecord -TeamId $TeamsTeamId -DateRangeStartDate $startTime -DateRangeEndDate $endTime -ClearSchedulingGroup:$True -EntityType $entityType -DesignatedActorId $$teamsUserId

#Create a mapping of the new team to the site 
Write-Host "Create a mapping of the existing team to the site"
$TimeZone = Read-Host -Prompt "Input the time zone of team mapping"
$teamMappingResult = New-CsTeamsShiftsConnectionTeamMap -ConnectorInstanceId $InstanceId -TeamId $TeamsTeamId -TimeZone $TimeZone -WfmTeamId $WfmTeamId
Write-Host "Success"


$title    = 'Connecting another team'
$question = 'Would you like to connect another team?'
$choices  = '&Yes', '&No'

$decision = $Host.UI.PromptForChoice($title, $question, $choices, 1)
if ($decision -eq 1) {
    break
}
}
Disconnect-MgGraph
Disconnect-MicrosoftTeams
```

## <a name="shifts-connector-cmdlets"></a>Shifts 커넥터 cmdlet

스크립트에 사용되는 cmdlet을 포함하여 Shifts 커넥터 cmdlet에 대한 도움말을 원하면 [PowerShell cmdlet](/powershell/teams/intro?view=teams-ps) 참조에서 **CsTeamsShiftsConnection** 을 Teams 검색합니다. 다음은 일반적으로 사용되는 몇 가지 cmdlet에 대한 링크입니다.

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
- [PowerShell을 사용하여 Blue Yonder Workforce Management에 대한 Shifts 연결을 관리합니다.](shifts-connector-powershell-manage.md)
- [Shifts 앱 관리](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Teams PowerShell 개요](../../teams-powershell-overview.md)
- [Teams PowerShell cmdlet 참조](/powershell/teams/intro?view=teams-ps)