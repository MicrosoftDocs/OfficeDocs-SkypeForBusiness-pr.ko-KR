---
title: Skype 및 Skype Microsoft 365 룸 시스템 계정 프로비전 Office 365
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 이 항목을 통해 Skype 또는 Microsoft 365 시스템 계정의 프로비전에 대해 Office 365.
ms.openlocfilehash: d1b116308f091c535beceb5a82994ee155507548
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58585952"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Skype 및 Skype Microsoft 365 룸 시스템 계정 프로비전 Office 365
 
이 항목을 통해 Skype 또는 Microsoft 365 시스템 계정의 프로비전에 대해 Office 365.
  
다음 섹션에서는 Skype 계정 프로비전에 대해 설명합니다.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365 및 Office 365 전제

온라인 테넌트는 다음 요구 사항을 충족해야 합니다.
  
- Microsoft 365 또는 Office 365 계획에는 온라인 비즈니스용 Skype 2 또는 Office 365 E1 E3 또는 E5가 포함되어야 합니다. <br/>온라인 계획에 비즈니스용 Skype 자세한 내용은 비즈니스용 Skype [서비스 설명을 참조하세요.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)
    
- 테넌트의 회의 기능이 비즈니스용 Skype 있어야 합니다.
    
- 테넌트에 사용 가능한 Exchange Online 있어야 합니다. 
    
- 테넌트 원격 관리자에게는 다음 PowerShell 액세스 권한이 있어야 합니다.
    
  - Exchange 원격 PowerShell 액세스
    
  - 비즈니스용 Skype 온라인 원격 PowerShell 액세스
    
  - Windows Azure Active Directory 디렉터리 액세스 Windows PowerShell 액세스하기 위한 Microsoft 365 Office 365 모듈
    
Skype Room 계정의 경우 다음 라이선스가 필요합니다.
  
- 온라인 비즈니스용 Skype 2 또는 Office 365 E1 또는 E3 라이선스를 사용하려면 Skype 필요합니다.
    
- 전화 번호로 방을 사용할 수 있도록 Enterprise Voice 기능을 사용하여 방에 권한을 부여하려면 전화 시스템 또는 Office 365 E5 있는 비즈니스용 Skype Online 계획 2가 필요합니다(1).
    
- 모임에서 전화 접속 기능이 필요한 경우 오디오 회의 및 전화 시스템 필요합니다.  모임에서 전화 접속 기능이 필요한 경우 국내 또는 국내 및 국제 통화 플랜이 필요합니다. 
    
- 이 Exchange Online 리소스 사서함 계정으로 구성해야 Skype Room 계정에는 Skype 라이선스가 필요하지 않습니다.
    
## <a name="provisioning-overview"></a>프로비저닝 개요

다음 다이어그램에서는 룸 시스템 계정 프로비전 흐름의 Skype 개요를 제공합니다.
  
![Skype 룸 시스템 프로비전 단계](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>새 회의실 식별

이미 Exchange 기능을 제공하는 리소스 공간 사서함이 있는 경우도 있습니다. 또는 리소스 사서함을 처음으로 만들어서 룸 시스템 배포를 Skype 있습니다. 어떤 경우든 테넌트에서 사용할 방 계정을 식별해야 합니다. Exchange Online 및 비즈니스용 Skype 프로비전 섹션에서는 두 종류의 계정에 대한 지침을 제공합니다. 예를 들어 다음 두 개의 방이 있으며 두 방 모두에 대해 Skype 회의실 시스템을 배포할 수 있습니다.
  
- 기존 리소스 사서함 계정: confrm1@contoso.onmicrosoft.com
    
- 새 리소스 사서함 계정: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online 프로비전

먼저 powerShell을 Exchange Online 항목의 지침에 따라 커넥트 [PowerShell에 Exchange Online 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)
  
기존 리소스 공간 사서함 계정을 Skype PowerShell에서 다음 Exchange Online 실행합니다.
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Room System에 Exchange 리소스 사서함 계정을 Skype PowerShell에서 다음 Exchange Online 실행합니다.
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

이전 명령은 계정을 사용하도록 설정하여 Exchange Room System Skype 새 리소스 사서함 계정을 설정하거나 만들 수 있습니다.
  
사서함을 만들고 나면 PowerShell에서 Set-CalendarProcessing cmdlet을 사용하여 Exchange Online 구성할 수 있습니다. 자세한 내용은 단일 포리스트의 3-6단계를 참조하세요.

## <a name="assigning-a-skype-for-business-online-license"></a>온라인 비즈니스용 Skype 할당

이제 비즈니스용 Microsoft 365 라이선스 할당 또는 제거 또는 비즈니스용 Skype 추가 기능 라이선스에 설명된 Microsoft 365 관리 포털을 사용하여 비즈니스용 Skype [](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) Online(계획 2) 또는 비즈니스용 Skype Online(계획 3) 라이선스를 할당할 수 [있습니다.](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7) 
  
비즈니스용 Skype Online에 대한 라이선스를 할당한 후 모든 클라이언트를 사용하여 계정이 활성 상태인지 비즈니스용 Skype 있습니다.
  
## <a name="skype-for-business-online-provisioning"></a>비즈니스용 Skype 온라인 프로비전

리소스 공간 사서함 계정을 만들어 이전에와 같이 사용하도록 설정한 후 Skype For Business Online에 대한 계정에 라이선스를 부여하면 계정이 Exchange Online 포리스트에서 비즈니스용 Skype Windows Azure Active Directory Online 포리스트로 동기화됩니다. 온라인 풀에서 Skype 룸 시스템 계정을 프로비전하려면 비즈니스용 Skype 단계를 따라야 합니다. 이러한 단계는 기존 리소스 사서함 계정 또는 새로 만든 계정(confrm1 또는 confrm2)에 대해 동일합니다. 이러한 계정이 Exchange Online 사용하도록 설정되면 두 계정이 동일한 방식으로 비즈니스용 Skype Online에 동기화됩니다.
  
1. 원격 PowerShell 세션을 만들 수 있습니다. [PowerShell](/microsoftteams/teams-powershell-install)모듈 을 다운로드해야 Teams 있습니다.
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. 사용자에 대해 Skype Room System 계정을 비즈니스용 Skype 다음 명령을 실행합니다.
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    다음 명령을 사용하여 비즈니스용 Skype 사용자가 있는 RegistrarPool 주소를 얻을 수 있습니다.
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>MFA(Multi-Factor Authentication)는 룸 시스템 계정에 Skype 지원되지 않습니다. 

## <a name="password-expiration"></a>암호 만료

모든 Microsoft 365 Office 365 암호 만료 정책을 구성하지 않는 한 모든 사용자 계정에 대한 기본 암호 만료 정책은 90일입니다. 룸 Skype 계정의 경우 다음 단계에 따라 암호 사용 기간 미정 설정을 선택할 수 있습니다.
  
1. 테넌트 Windows Azure Active Directory 관리자 자격 증명을 사용하여 새 세션을 만들 수 있습니다.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 다음 명령을 사용하여 이전에 만든 Skype 방 계정의 암호 사용 기간이 만료되지 않는 설정 설정
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

자세한 내용은 [Set up your computer for Windows PowerShell.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="validate"></a>유효성 검사

유효성 검사를 위해 모든 비즈니스용 Skype 클라이언트를 사용하여 만든 계정에 로그인할 수 있습니다.