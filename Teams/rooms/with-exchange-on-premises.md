---
title: Microsoft Teams 룸 Exchange 배포
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: 이 항목을 참조하여 Microsoft Teams 룸 하이브리드 환경에서 배포하는 방법에 Exchange 있습니다.
ms.openlocfilehash: 96d8a49cd75e3413739d36a3c86a91daa72b22e6
ms.sourcegitcommit: 115e44f33fc7993f6eb1bc781f83eb02a506e29b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60909539"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Microsoft Teams 룸 Exchange 배포

이 항목을 참조하여 Microsoft Teams 룸 및 Exchange 하이브리드 환경에서 배포하는 방법에 Microsoft Teams.
  
조직에 여러 서비스가 혼합되어 있으며, 일부 호스팅된 온라인 및 일부 호스팅된 온라인 서비스가 있는 경우 구성은 각 서비스가 호스트되는 위치에 따라 다릅니다. 이 항목에서는 호스트된 Microsoft Teams 룸 Exchange 하이브리드 배포에 대해 설명합니다. 이 유형의 배포에는 다양한 변형이 있으므로 모든 배포에 대한 자세한 지침을 제공할 수 없습니다. 다음 프로세스는 여러 구성에 대해 작동할 것입니다. 프로세스가 설정에 맞지 않는 경우 여기에서 설명한 Windows PowerShell 및 다른 배포 옵션에 대해 동일한 최종 결과를 달성하기 위해 이 프로세스를 사용하는 것이 좋습니다.

Microsoft는 [ ](https://go.microsoft.com/fwlink/?linkid=870105)SkypeRoomProvisioningScript.ps1사용자 계정으로 전환할 수 있도록 새 사용자 계정을 만들거나 기존 리소스 계정의 유효성을 검사하는 데 도움이 되는 Microsoft Teams 룸 제공합니다. 원하는 경우 아래 단계를 수행하여 디바이스에서 사용할 계정을 Microsoft Teams 룸 수 있습니다.
  
## <a name="requirements"></a>요구 사항

Microsoft Teams 룸 Exchange 배포하기 전에 요구 사항을 충족해야 합니다. 자세한 내용은 요구 사항 [Microsoft Teams 룸 참조하세요.](requirements.md)
  
모든 Microsoft Teams 룸 Exchange 배포하는 경우 Active Directory 관리 도구를 사용하여 프레미스 도메인 계정에 대한 전자 메일 주소를 추가합니다. 이 계정은 Microsoft 365 또는 Office 365. 다음이 필요합니다.
  
- 계정을 만들고 계정을 Azure Active Directory.

- 원격 사서함을 사용하도록 설정하고 속성을 설정합니다.

- 라이선스 또는 Microsoft 365 Office 365 할당합니다.

### <a name="create-an-account-and-synchronize-with-azure-active-directory"></a>계정을 만들고 계정과 Azure Active Directory

1. Active **Directory** 사용자 및 컴퓨터 도구에서 사용자 계정이 생성될 폴더 또는 조직 단위를 마우스 오른쪽 단추로 클릭하고 Microsoft Teams 룸 클릭한 다음 사용자 를 **클릭합니다.**

2. 표시 이름을 전체 이름 상자에 **입력하고** 별칭을 사용자 로그온 이름 상자에 **입력합니다.** 다음 **을 클릭합니다.**

3. 이 계정에 대한 암호를 입력합니다. 확인을 위해 다시 타이프해야 합니다. 암호가 **만료되지** 않는지 확인란만 선택해야 합니다.

    > [!NOTE]
    > 암호가 **만료되지** 않는 경우 암호를 선택하는 것이 Microsoft Teams 룸. 도메인 규칙은 만료되지 않는 암호를 금지할 수 있습니다. 그렇다면 각 디바이스 계정에 대한 예외를 Microsoft Teams 룸 합니다.
  
4. 계정을 만든 후 디렉터리 동기화를 실행합니다. 완료되면 사용자의 사용자 페이지로 이동하여 Microsoft 365 관리 센터 만든 계정이 온라인에 병합되어 있는지 확인해야 합니다.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>원격 사서함 사용 및 속성 설정

1. [원격 PowerShell을](/powershell/exchange/exchange-server/open-the-exchange-management-shell) 사용하여 Exchange 관리 셸을 열거나 Exchange 서버에 [연결합니다.](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)

2. PowerShell의 Exchange 다음 명령을 실행하여 계정에 대한 사서함(사서함 사용 계정)을 생성합니다.

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   자세한 구문 및 매개 변수 정보는 [사용-사서함 을 참조하세요.](/powershell/module/exchange/mailboxes/enable-mailbox)

3. PowerShell의 Exchange 회의실 사서함에서 다음 설정을 구성하여 모임 환경을 개선합니다.

   - AutomateProcessing: AutoAccept(모임 이끌이는 사용자 개입 없이 직접 회의실 예약 결정을 수신합니다. 무료 = 수락, 사용 중 = 거부).)

   - AddOrganizerToSubject: $false(모임 이끌이가 모임 요청의 제목에 추가되지 않습니다.)

   - DeleteComments: $false(들어오는 모임 요청의 메시지 본문에 텍스트를 보관합니다.)

   - DeleteSubject: $false(들어오는 모임 요청의 제목 유지)입니다.

   - RemovePrivateProperty: $false(원래 모임 요청에서 모임 이끌이가 보낸 개인 플래그가 지정된 상태로 유지되도록 합니다.)

   - AddAdditionalResponse: $true(AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가됩니다.)

   - 추가Response: "이 회의실은 Microsoft Teams 있습니다!" (모임 요청에 추가할 추가 텍스트입니다.)

   이 예제에서는 Project-Rigel-01이라는 방 사서함에서 이러한 설정을 구성합니다.

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   자세한 구문 및 매개 변수 정보는 [Set-CalendarProcessing 을 참조하세요.](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>라이선스 Microsoft 365 또는 Office 365 할당

1. 커넥트 Azure Active Directory. 자세한 Azure Active Directory [MSOnline( Azure ActiveDirectory) 1.0 을 참조하세요.](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0은](/powershell/azure/active-directory/overview?view=azureadps-2.0) 지원되지 않습니다. 

2. 디바이스 계정에 유효한 Microsoft 365 Office 365 라이선스가 있어야 Exchange Microsoft Teams 작동하지 않습니다. 라이선스가 있는 경우 디바이스 계정에 사용 위치를 할당해야 합니다. 그러면 계정에 사용할 수 있는 라이선스 SKUS가 결정됩니다. 사용할 수 있습니다. `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 를 사용하여 사용 가능한 SKUS 목록을 검색합니다.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 다음으로, `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet입니다. 이 경우 $strLicense SKU 코드입니다(예: contoso:STANDARDPACK).

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   자세한 지침은 PowerShell을 통해 사용자 계정에 라이선스 [할당을 Office 365 참조하세요.](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)

유효성 검사의 경우 클라이언트를 사용하여 이 계정에 로그인할 수 있습니다.
  
## <a name="related-topics"></a>관련 항목

[Microsoft Teams 룸](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
