---
title: Exchange와 함께 Microsoft 팀 대화방 배포 (온-프레미스)
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: Exchange 온-프레미스를 사용 하는 하이브리드 환경에서 Microsoft 팀 대화방을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: 7e855ece643d3412047b4d01a9250b17f699ac98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182321"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>Exchange와 함께 Microsoft 팀 대화방 배포 (온-프레미스)

온-프레미스와 Microsoft 팀 또는 비즈니스용 Skype Online을 사용 하는 하이브리드 환경에서 Microsoft 팀 대화방을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
  
조직에서 서비스를 혼합 하 여 온-프레미스 호스트와 일부 온라인 상태를 갖춘 경우 각 서비스가 호스팅되는 위치에 따라 구성이 달라 집니다. 이 항목에서는 구내에 호스팅되는 Exchange를 사용 하 여 Microsoft 팀 회의실을 위한 하이브리드 배포에 대해 설명 합니다. 이러한 유형의 배포에는 다양 한 변형이 있기 때문에 모든 방법에 대 한 자세한 지침을 제공 하는 것은 불가능 합니다. 다음 프로세스는 여러 구성에서 작동 합니다. 프로세스가 설정에 적합 하지 않은 경우에는 Windows PowerShell을 사용 하 여 여기에 명시 된 것과 다른 배포 옵션에 대 한 동일한 최종 결과를 얻을 것을 권장 합니다.

Microsoft는 새 사용자 계정을 만들거나, 호환 되는 Microsoft 팀 대화방 사용자 계정으로 전환 하는 데 도움을 주는 기존 리소스 계정이 있는지 확인 하는 데 도움이 되는 [SkypeRoomProvisioningScript. ps1을 제공 합니다.](https://go.microsoft.com/fwlink/?linkid=870105) 원하는 경우 아래 단계에 따라 Microsoft 팀 대화방 장치에서 사용할 계정을 구성할 수 있습니다.
  
## <a name="requirements"></a>요구 사항

Exchange와 함께 Microsoft 팀 대화방을 구내에 배포 하기 전에 요구 사항을 충족 해야 합니다. 자세한 내용은 [Microsoft 팀 공간 요구 사항을](requirements.md)참조 하세요.
  
Exchange를 사용 하 여 Microsoft 팀 회의실을 구내에 배포 하는 경우 Active Directory 관리 도구를 사용 하 여 온-프레미스 도메인 계정의 전자 메일 주소를 추가 합니다. 이 계정은 Office 365와 동기화 됩니다. 다음을 수행 해야 합니다.
  
- 계정을 만들고 Active Directory와 계정을 동기화 합니다.

- 원격 사서함을 사용 하도록 설정 하 고 속성을 설정 합니다.

- Office 365 라이선스를 할당 합니다.

- 비즈니스용 Skype 서버에서 디바이스 계정을 사용 하도록 설정 합니다. 디바이스 계정을 사용 하도록 설정 하려면 환경이 다음 선행 조건을 충족 해야 합니다.

  - Office 365 요금제에는 비즈니스용 Skype Online (요금제 2) 이상이 필요 합니다. 요금제는 회의 기능을 지원 해야 합니다.
  
  - - Microsoft 팀 대화방에 대 한 전화 통신 서비스 공급자를 사용 하 여 엔터프라이즈 음성 (PSTN 전화 통신)이 필요한 경우 비즈니스용 Skype Online이 필요 합니다 (계획 3).
  
  - - 테 넌 트 사용자에 게 Exchange 사서함이 있어야 합니다.
  
  - - Microsoft 팀 대화방 계정에는 비즈니스용 Skype Online (계획 2) 또는 비즈니스용 Skype Online (계획 3) 라이선스가 필요 하지만 Exchange Online 라이선스는 필요 하지 않습니다.

- Microsoft 팀 대화방 계정에 비즈니스용 Skype 서버 라이선스를 할당 합니다.

### <a name="create-an-account-and-synchronize-with-active-directory"></a>계정 만들기 및 Active Directory와 동기화

1. **Active Directory 사용자 및 컴퓨터** 도구에서 Microsoft 팀 대화방 계정이 생성 될 폴더 또는 조직 구성 단위를 마우스 오른쪽 단추로 클릭 하 고 **새로 만들기**를 클릭 한 다음 **사용자**를 클릭 합니다.

2. 이전 cmdlet의 표시 이름을 **전체 이름** 상자에 입력 하 고 별칭을 **사용자 로그온 이름** 상자에 입력 합니다. **다음**을 클릭 합니다.

3. 이 계정에 대 한 암호를 입력 합니다. 확인을 위해 암호를 다시 입력 해야 합니다. **암호 사용 기간 제한 없음** 확인란이 선택 되어 있는지 확인 합니다.

    > [!NOTE]
    > **암호 사용 기간 제한 없음** 선택은 Microsoft 팀 대화방의 비즈니스용 Skype 서버에 대 한 요구 사항입니다. 도메인 규칙에 따라 만료 되지 않는 암호가 금지 될 수 있습니다. 그렇다면 각 Microsoft 팀 공간 디바이스 계정에 대 한 예외를 만들어야 합니다.
  
4. 계정을 만든 후 디렉터리 동기화를 실행 합니다. 완료 되 면 Microsoft 365 관리 센터의 사용자 페이지로 이동 하 여 이전 단계에서 만든 계정이 온라인에 병합 되었는지 확인 합니다.

### <a name="enable-the-remote-mailbox-and-set-properties"></a>원격 사서함을 사용 하도록 설정 하 고 속성 설정

1. [Exchange 관리 셸을 열거나](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell) [원격 PowerShell을 사용 하 여 exchange 서버에 연결](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)합니다.

2. Exchange PowerShell에서 다음 명령을 실행 하 여 계정에 대 한 사서함 (사서함 사용이 허용 되는 계정)을 상자에 만듭니다.

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   자세한 구문 및 매개 변수 정보는 [사서함 사용](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)을 참조 하세요.

3. Exchange PowerShell에서 회의실 사서함에 다음 설정을 구성 하 여 모임 환경을 개선 합니다.

   - AutomateProcessing: AutoAccept (모임 이끌이는 사용자 간섭 없이 직접 회의실 예약 결정을 받습니다: 무료 = 수락; 사용 중 = 거절).

   - AddOrganizerToSubject: $false (모임 이끌이는 모임 요청의 제목에 추가 되지 않습니다.)

   - Deletecomdea: $false (받는 모임 요청의 메시지 본문에 있는 텍스트는 유지 합니다.)

   - DeleteSubject: $false (들어오는 모임 요청의 주제를 보관 합니다.)

   - RemovePrivateProperty: $false (원래 모임 이끌이가 보낸 개인 플래그가 지정 된 대로 유지 되도록 합니다.)

   - AddAdditionalResponse: $true (AdditionalResponse 매개 변수에서 지정한 텍스트가 모임 요청에 추가 됩니다.)

   - AdditionalResponse: "Skype 회의실입니다!" (모임 요청에 추가 하는 추가 텍스트입니다.)

   이 예제에서는 Rigel-01 이라는 대화방 사서함에서 이러한 설정을 구성 합니다.

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   자세한 구문 및 매개 변수 정보는 [설정-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)를 참조 하세요.

### <a name="assign-an-office-365-license"></a>Office 365 라이선스 할당

1. Azure Active Directory에 연결 합니다. Active Directory에 대 한 자세한 내용은 [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)을 참조 하세요. 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) 는 지원 되지 않습니다. 

2. 장치 계정에 유효한 Office 365 라이선스가 필요 하거나 Exchange 및 Microsoft 팀이 작동 하지 않습니다. 라이선스가 있는 경우 사용 위치를 디바이스 계정에 할당 해야 하며,이는 계정에 사용할 수 있는 라이선스 Sku를 결정 하는 것입니다. 사용할 수 있는`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 사용 가능한 Sku 목록을 검색 합니다.

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 다음으로, 다음을 사용 하 여 라이선스를 추가할 수 있습니다.`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> 은. 이 경우 $strLicense는 사용자에 게 표시 되는 SKU 코드입니다 (예: contoso: STANDARDPACK).

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

   자세한 지침은 [Office 365 PowerShell을 사용 하 여 사용자 계정에 라이선스 할당](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)을 참조 하세요.

### <a name="enable-the-device-account"></a>디바이스 계정 사용

비즈니스용 skype Online PowerShell은 Microsoft 팀과 비즈니스용 Skype Online에 대 한 서비스를 관리 하는 데 사용 됩니다.

1. PC에서 원격 Windows PowerShell 세션을 다음과 같이 만듭니다.

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. Microsoft 팀 대화방 계정을 사용 하도록 설정 하려면 다음 명령을 실행 합니다.

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   환경에서 RegistrarPool 매개 변수에 어떤 값을 사용 해야 하는지 확실 하지 않은 경우이 명령을 사용 하 여 기존 사용자의 값을 가져올 수 있습니다.

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>Microsoft 팀원에 게 라이선스 할당 공간 계정

1. 테 넌 트 관리자로 로그인 하 고, Office 365 관리 포털을 열고, 관리 앱을 클릭 합니다.
2. **사용자 및 그룹** 을 클릭 한 다음 **사용자 추가, 암호 다시 설정**등을 클릭 합니다.
3. Microsoft 팀 대화방 계정을 클릭 한 다음 펜 아이콘을 클릭 하 여 계정 정보를 편집 합니다.
4. **라이선스**를 클릭 합니다.
5. 라이선스 **할당**에서 라이선스 및 엔터프라이즈 음성 요구 사항에 따라 비즈니스용 Skype (계획 2) 또는 비즈니스용 Skype (계획 3)를 선택 합니다. Microsoft 팀 방에 Enterprise Voice를 사용 하려면 요금제 3 라이선스를 사용 해야 합니다.
6. **저장**을 클릭 합니다.

유효성 검사를 위해 모든 클라이언트를 사용 하 여이 계정에 로그인 할 수 있습니다.
  
## <a name="see-also"></a>참고 항목

[Microsoft 팀 대화방 계정 구성](room-systems-v2-configure-accounts.md)

[Microsoft 팀 회의실 계획](skype-room-systems-v2-0.md)
  
[Microsoft 팀 대화방 배포](room-systems-v2.md)
  
[Microsoft 팀 대화방 콘솔 구성](console.md)
  
[Microsoft 팀 대화방 관리](skype-room-systems-v2.md)
