---
title: PowerShell을 사용하여 팀에 대한 액세스 권한 제어
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: PowerShell을 사용 하 여 Microsoft 팀의 팀에 대 한 게스트 액세스를 허용 하거나 차단 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c91d64973c97ce358741874ba45c1d6338915264
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834028"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>PowerShell을 사용하여 팀에 대한 액세스 권한 제어
================================================

Microsoft 365 관리 센터 및 azure AD (Active Directory) 포털을 사용 하는 것 외에도 Windows PowerShell을 사용 하 여 게스트 액세스를 제어할 수 있습니다. PowerShell을 사용 하 여 다음을 수행할 수 있습니다.
  
- 모든 팀 및 Office 365 그룹에 대 한 게스트 액세스 허용 또는 차단

- 모든 팀 및 Office 365 그룹에 게스트를 추가할 수 있도록 허용

- 특정 팀 또는 Office 365 그룹의 게스트 사용자 허용 또는 차단

자세한 내용은 [Office 365 그룹의 게스트 액세스 관리](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access)에서 PowerShell을 사용 하 여 게스트 액세스 제어 "를 참조 하세요.

  
PowerShell을 사용 하 여 해당 도메인에 따라 게스트 사용자를 허용 하거나 차단할 수도 있습니다. 예를 들어, 회사 (Contoso)에 다른 비즈니스 (Fabrikam)와의 파트너 관계가 있다고 가정해 보겠습니다. 사용자가 그룹에 해당 게스트를 추가할 수 있도록 허용 목록에 Fabrikam을 추가할 수 있습니다. 자세한 내용은 [Office 365 그룹에 대 한 게스트 액세스 허용/차단](https://go.microsoft.com/fwlink/?linkid=854001)을 참조 하세요.
  
팀에서 게스트를 차단 하 고 SharePoint 사이트에 대 한 액세스를 허용 하려는 경우 Azure AD Powershell cmdlet을 사용 하 여 SharePoint 사이트에 대 한 외부 공유가 설정 되어 있다고 가정 하 고 회사 개체의 AllowGuestsToAccessGroups 매개 변수를 사용 하지 않도록 설정할 수 있습니다. .

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a>PowerShell을 사용 하 여 게스트 액세스 설정 또는 해제

1.  에서 비즈니스용 Skype Online PowerShell 모듈 다운로드https://www.microsoft.com/en-us/download/details.aspx?id=39366
 
2.  비즈니스용 Skype Online 끝점에 PowerShell 세션을 연결 합니다.

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
3.  구성을 확인 하 고, `AllowGuestUser` 설정 `$False`된 경우 [CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet을 사용 하 여 설정 `$True`합니다.

    ```PowerShell
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
이제 조직의 팀에서 게스트 사용자를 가질 수 있습니다.


## <a name="guest-access-vs-external-access"></a>게스트 액세스와 외부 액세스 비교

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
