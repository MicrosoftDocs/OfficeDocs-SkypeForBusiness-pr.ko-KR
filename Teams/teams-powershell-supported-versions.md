---
title: Teams PowerShell 모듈 - 지원되는 버전
author: pbafna03
ms.author: pbafna
ms.reviewer: pbafna
manager: sshastri
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Microsoft Teams 관리에 사용되는 Teams PowerShell 모듈에서 지원되는 버전에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d28e16c248957518ca16eb3eff7e082ebe6bd9bd
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590325"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 모듈 - 지원되는 버전

4.x.x 시리즈 이상의 Microsoft Teams TPM(PowerShell 모듈) 버전은 현재 지원되는 유일한 버전입니다. 이전 버전은 모두 2022년 6월 15일 & 이후 상용 환경에서 완전히 사용 중지됩니다(참조용 메시지 센터 게시물 - MC350371). 

최신 Teams PowerShell 모듈 버전으로 업데이트하는 것이 좋습니다.


## <a name="important-notes"></a>중요 참고 사항

- 모든 Teams PowerShell 모듈 버전에 대한 릴리스 정보는 [Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)에서 확인할 수 있습니다.

- PowerShell 모듈을 업데이트하려면 모듈을 설치하는 데 사용되는 것과 동일한 방법을 사용해야 합니다. 예를 들어 원래 Install-Module을 사용한 경우 [Update-Module](/powershell/module/powershellget/update-module) 을 사용하여 최신 버전을 가져와야 합니다.

  ```powershell
  Update-Module MicrosoftTeams
  ```

- Teams PowerShell 모듈 버전 1.1.6에서 업데이트하는 경우 대신 `New-CsOnlineSession`사용하도록 `Connect-MicrosoftTeams` 스크립트를 업데이트합니다.

- 업데이트하는 동안 3.0.0 이전 버전과 함께 TPM 4.x.x/3.x.x를 사용하지 않는 것이 좋습니다. 예를 들어 동일한 조직의 다양한 관리 작업에 대해 버전 4.x.x & 2.6.0을 함께 사용하는 것은 권장되지 않습니다.

- 관련 변경 내용
  - TPM 3.x.x 이상에서 Get-CsOnlineUser & Get-CsOnlineVoiceUser 업데이트 - [Get-CsOnlineUser](/powershell/module/skype/get-csonlineuser) & [Get-CsOnlineVoiceUser](/powershell/module/skype/get-csonlinevoiceuser)(메시지 센터 게시물 – MC340774)에서 자세한 내용을 참조하세요.

  - 전화 번호 할당에 대한 변경 내용 - [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance)[Set-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlinevoiceapplicationinstance) & 의 자세한 내용(메시지 센터 게시물 – MC316139).

  - Get-CsTenant 매개 변수 변경 - [Get-CsTenant](/powershell/module/skype/get-cstenant) 의 자세한 내용(메시지 센터 게시물 – MC365397).
  
  - 스크립트에서 PSListModifier 형식 매개 변수와 함께 New/Set of Policy 또는 Configuration cmdlet을 사용하는 경우 최신 버전(4.2.0 이상)을 사용하는 것이 좋습니다. 참조용 메시지 센터 게시물 - MC397428.

  - [새로 만들기| Get]-CsCloudCallDataConnection cmdlet은 이제 버전 4.6.0 이상에서 지원됩니다(메시지 센터 게시물 - MC408993).

- TPM 4.x.x 이상을 사용하는 동안 [아래에](#deprecated-cmdlets) 언급된 사용되지 않거나 지원되지 않는 cmdlet을 사용하지 않는 것이 좋습니다.

## <a name="deprecated-cmdlets"></a>사용되지 않는 cmdlet

- 최근에 사용되지 않는 cmdlet 중 일부는 아래에 나열되어 있습니다. 자세한 내용은 해당 공개 설명서에서 확인할 수 있습니다.
  - [Get-CsOnlineTelephoneNumber](/powershell/module/skype/get-csonlinetelephonenumber)
  - [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
  - [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
  - [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
  - [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint), Switch-CsOnlineApplicationEndpoint
  - [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)
  - [Set-CsTeamsAppSetupPolicy](/powershell/module/skype/set-csteamsappsetuppolicy), [New-CsTeamsAppSetupPolicy](/powershell/module/skype/new-csteamsappsetuppolicy), [Set-CsTeamsAppPermissionPolicy](/powershell/module/skype/set-csteamsapppermissionpolicy), [New-CsTeamsAppPermissionPolicy](/powershell/module/skype/new-csteamsapppermissionpolicy)
  - [Test-CsOnlineLisCivicAddress](/powershell/module/skype/test-csonlineliscivicaddress)

- Microsoft Teams 시나리오에 대해 지원되지 않거나 관련되지 않는 Cmdlet은 아래에 나열되어 있습니다.
  - [Get| Set]-CsUserPstnSettings
  - [Get| 설정| 사용| Disable]-CsMeetingRoom
  - [Grant| 가져오기| 설정| 새로 만들기| Remove]-CsConferencingPolicy
  - [Grant| 가져오기| 설정| 새로 만들기| Remove]-CsClientPolicy
  - [Grant| Get]-CsHostedVoicemailPolicy
  - [Grant| 가져오기| 설정| 새로 만들기| Remove]-CsMobilityPolicy
  - [Grant| Get]-CsVoiceRoutingPolicy
  - [Grant| Get]-CsBroadcastMeetingPolicy
  - [Grant| Get]-CsCloudMeetingPolicy
  - [Grant| Get]-CsGraphPolicy
  - [Grant| 가져오기| 설정| 새로 만들기| Remove]-CsExternalUserCommunicationPolicy
  - [Grant| 가져오기| Set]-CsIPPhonePolicy
  - Get-CsUserServicesPolicy
  - [Get| Set]-CsBroadcastMeetingConfiguration
  - [Get| Set]-CsOAuthConfiguration
  - [Get| Set]-CsMeetingConfiguration
  - [Get| Set]-CsTenantHybridConfiguration
  - [Get| Set]-CsPushNotificationConfiguration
  - [Get| Set]-CsUCPhoneConfiguration
  - Get-CsImFilterConfiguration
  - Get-CsAudioConferencingProvider
  - [Get| Set]-CsTenantPublicProvider
  - Get-CsHostingProvider
  - [Get| 설정| 등록| 등록 취소]-CsHybridPSTNAppliance
  - [Get| 설정| 새로 만들기| Remove]-CsHybridPSTNSite
  - [Get| Set]-CsHybridMediationServer
  - [Get| 설정| 새로 만들기| Remove]-CsTenantUpdateTimeWindow
  - Get-CsUserLocationStatus
  - Invoke-CsUcsRollback
  - [Get| 설정| 새로 만들기| Remove]-CsTeamsPinnedApp
  - [Get| 설정| 새로 만들기| Remove]-CsTenantCatalogApp
  - [Get| 설정| 새로 만들기| Remove]-CsGlobalCatalogApp
  - [Get| 설정| 새로 만들기| Remove]-CsDefaultCatalogApp
  - [Get| 설정| 새로 만들기| Remove]-CsTeamsAppPreset
  - Invoke-CsUserPreferredDataLocationSync
  - [Get| Set]-CsTeamsUpgradeStatus
  - Grant-CsPolicy
  - Set-CsOnlineDirectoryUser

## <a name="related-topics"></a>관련 주제

[Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)

[Microsoft Teams PowerShell 설치](teams-powershell-install.md)

[Teams PowerShell을 사용하여 Teams 관리](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 참조](/powershell/module/teams)

[비즈니스용 Skype cmdlet 참조](/powershell/module/skype)
