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
ms.openlocfilehash: c9eb6754a9fa89d1298e22f6c713e8c4d28d5861
ms.sourcegitcommit: 708b489a7dca7fd9e5e9b1ec88c9aba79ecafe5f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2022
ms.locfileid: "64712962"
---
# <a name="teams-powershell-module---supported-versions"></a>Teams PowerShell 모듈 - 지원되는 버전

Microsoft Teams 4.x.x 시리즈 이상의 TPM(PowerShell 모듈) 버전은 앞으로 지원되는 유일한 버전입니다. 모든 이전 버전은 사용 중지 경로에 있습니다. Teams PowerShell 모듈을 최신 버전으로 업데이트하는 것이 좋습니다.



## <a name="new-organizations"></a>새 조직

Teams 새로 온보딩하는 조직은 2022년 4월 1일부터 4.x.x 시리즈 이상에서만 Teams PowerShell 모듈을 사용할 수 있습니다.



## <a name="current-organizations-non-tpm-active"></a>현재 조직(TPM이 아닌 활성)

지난 3개월 동안 Teams PowerShell 모듈을 사용하지 않은 조직(1월 22일 ~ 3월 22일)은 2022년 4월 1일부터 4.x.x 시리즈 이상에서만 Teams PowerShell 모듈을 사용할 수 있습니다.



## <a name="current-organizations-tpm-active"></a>현재 조직(TPM 활성)

지난 3개월 동안 Teams PowerShell 모듈을 사용한 조직(1월 22일 ~ 3월 22일)은 2022년 6월 15일부터 4.x.x 시리즈 이상에서만 Teams PowerShell 모듈을 사용할 수 있습니다. 참조용 메시지 센터 게시물 - MC350371. 



## <a name="important-notes"></a>중요 참고 사항

- 모든 Teams PowerShell 모듈 버전에 대한 릴리스 정보는 [Teams PowerShell 릴리스 정보](teams-powershell-release-notes.md)에서 확인할 수 있습니다.

- PowerShell 모듈을 업데이트하려면 모듈을 설치하는 데 사용되는 것과 동일한 방법을 사용해야 합니다. 예를 들어 원래 Install-Module을 사용한 경우 [Update-Module](/powershell/module/powershellget/update-module) 을 사용하여 최신 버전을 가져와야 합니다.  

  ```powershell
  Update-Module MicrosoftTeams
  ```

-   Teams PowerShell 모듈 버전 1.1.6에서 업데이트하는 경우 대신 사용하도록 `Connect-MicrosoftTeams` `New-CsOnlineSession`스크립트를 업데이트합니다.

-   업데이트하는 동안 3.0.0 이전 버전과 함께 TPM 4.x.x/3.x.x를 사용하지 않는 것이 좋습니다. 예를 들어 동일한 조직의 다양한 관리 작업에 대해 버전 4.x.x & 2.6.0을 함께 사용하는 것은 권장되지 않습니다. 

- 관련 변경 내용
  * TPM 3.x.x 이상에서 Get-CsOnlineUser & Get-CsOnlineVoiceUser 대한 업데이트 - [Get-CsOnlineUserGet-CsOnlineVoiceUser](/powershell/module/skype/get-csonlineuser) & (메시지 센터 게시물 – MC340774)의 자세한 내용입니다.[](/powershell/module/skype/get-csonlinevoiceuser)

  * 전화 번호 할당에 대한 변경 내용 - [Set-CsUser](/powershell/module/skype/set-csuser), [Set-CsOnlineVoiceUser](/powershell/module/skype/set-csonlinevoiceuser), [Set-CsOnlineApplicationInstanceSet-CsOnlineVoiceApplicationInstance](/powershell/module/skype/set-csonlineapplicationinstance) & 의 자세한 내용(메시지 센터 게시물 – MC316139)[](/powershell/module/skype/set-csonlinevoiceapplicationinstance)



## <a name="deprecated-cmdlets"></a>사용되지 않는 cmdlet

최근에 사용되지 않거나 Microsoft Teams 시나리오에서 지원되지 않는 cmdlet 중 일부는 아래에 나열되어 있습니다. 자세한 내용은 해당 공개 설명서에서 확인할 수 있습니다. 

- [Get-CsUserPstnSettings](/powershell/module/skype/get-csuserpstnsettings), [Set-CsUserPstnSettings](/powershell/module/skype/set-csuserpstnsettings)
- [Get-CsOnlineDialInConferencingUserInfo](/powershell/module/skype/get-csonlinedialinconferencinguserinfo), [Get-CsOnlineDialInConferencingUserState](/powershell/module/skype/get-csonlinedialinconferencinguserstate), [Enable-CsOnlineDialInConferencingUser](/powershell/module/skype/enable-csonlinedialinconferencinguser), [Disable-CsOnlineDialInConferencingUser](/powershell/module/skype/disable-csonlinedialinconferencinguser)
- [Get-CsMeetingRoom](/powershell/module/skype/get-csmeetingroom), [Set-CsMeetingRoom](/powershell/module/skype/set-csmeetingroom), [Enable-CsMeetingRoom](/powershell/module/skype/enable-csmeetingroom), [Disable-CsMeetingRoom](/powershell/module/skype/disable-csmeetingroom)
- [Get-CsOnlineDirectoryTenant](/powershell/module/skype/get-csonlinedirectorytenant)
- [New-CsOnlineAudioFile](/powershell/module/skype/new-csonlineaudiofile)
- [Get-CsOnlineApplicationEndpoint](/powershell/module/skype/get-csonlineapplicationendpoint), [Set-CsOnlineApplicationEndpoint](/powershell/module/skype/set-csonlineapplicationendpoint), [New-CsOnlineApplicationEndpoint](/powershell/module/skype/new-csonlineapplicationendpoint), [Remove-CsOnlineApplicationEndpoint](/powershell/module/skype/remove-csonlineapplicationendpoint)
- [Get-CsOnlineTelephoneNumberInventoryCities](/powershell/module/skype/get-csonlinetelephonenumberinventorycities), [Get-CsOnlineTelephoneNumberInventoryAreas](/powershell/module/skype/get-csonlinetelephonenumberinventoryareas), [Get-CsOnlineTelephoneNumberInventoryCountries](/powershell/module/skype/get-csonlinetelephonenumberinventorycountries), [Get-CsOnlineTelephoneNumberInventoryRegions](/powershell/module/skype/get-csonlinetelephonenumberinventoryregions), [Get-CsOnlineTelephoneNumberInventoryTypes](/powershell/module/skype/get-csonlinetelephonenumberinventorytypes), [Search-CsOnlineTelephoneNumberInventory](/powershell/module/skype/search-csonlinetelephonenumberinventory), [Select-CsOnlineTelephoneNumberInventory](/powershell/module/skype/select-csonlinetelephonenumberinventory), [Get-CsOnlineTelephoneNumberAvailableCount](/powershell/module/skype/get-csonlinetelephonenumberavailablecount), [ Clear-CsOnlineTelephoneNumberReservation](/powershell/module/skype/clear-csonlinetelephonenumberreservation), [Get-CsOnlineTelephoneNumberReservationsInformation](/powershell/module/skype/get-csonlinetelephonenumberreservationsinformation), [Get-CsOnlineDirectoryTenantNumberCities](/powershell/module/skype/get-csonlinedirectorytenantnumbercities)  



## <a name="related-topics"></a>관련 주제

[PowerShell 릴리스 정보 Teams](teams-powershell-release-notes.md)

[Microsoft Teams PowerShell 설치](teams-powershell-install.md)

[Teams PowerShell을 사용하여 Teams 관리](teams-powershell-managing-teams.md)

[Microsoft Teams cmdlet 참조](/powershell/module/teams) 

[비즈니스용 Skype cmdlet 참조](/powershell/module/skype) 
