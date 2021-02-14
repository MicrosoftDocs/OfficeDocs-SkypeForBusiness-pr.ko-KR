---
title: Microsoft 365 및 Office 365에서 Skype 룸 시스템 계정 프로비전
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 이 항목을 읽고 Microsoft 365 또는 Office 365에서 Skype 룸 시스템 계정을 프로비전하는 방법을 배워야 합니다.
ms.openlocfilehash: 115dd83751e0da837d9d88351d57a769b7e313da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820848"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Microsoft 365 및 Office 365에서 Skype 룸 시스템 계정 프로비전
 
이 항목을 읽고 Microsoft 365 또는 Office 365에서 Skype 룸 시스템 계정을 프로비전하는 방법을 배워야 합니다.
  
다음 섹션에서는 Skype 룸 시스템 계정 프로비전에 대한 설명을 제공합니다.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365 및 Office 365의 선행 준비

온라인 테넌트는 다음 요구 사항을 충족해야 합니다.
  
- Microsoft 365 또는 Office 365 요금제에는 비즈니스용 Skype Online 계획 2 또는 Office 365 E1, E3 또는 E5가 포함되어야 합니다. <br/>비즈니스용 Skype Online 계획에 대한 자세한 내용은 비즈니스용 [Skype Online 서비스 설명을 참조하세요.](https://technet.microsoft.com/library/jj822172.aspx)
    
- 테넌트에 비즈니스용 Skype의 회의 기능이 활성화되어 있어야 합니다.
    
- 테넌트에서 Exchange Online을 사용하도록 설정해야 합니다. 
    
- 테넌트 원격 관리자에게는 다음 PowerShell 액세스 권한이 있어야 합니다.
    
  - Exchange 원격 PowerShell 액세스
    
  - 비즈니스용 Skype Online 원격 PowerShell 액세스
    
  - Windows Azure Microsoft 365 또는 Office 365 디렉터리 Windows PowerShell 액세스하기 위한 Active Directory 모듈 구성
    
Skype 룸 계정의 경우 다음 라이선스가 필요합니다.
  
- Skype 모임을 사용하도록 설정하려면 비즈니스용 Skype Online 계획 2 또는 Office 365 E1 또는 E3 라이선스가 필요합니다.
    
- 전화 번호로 채팅방을 사용할 수 있도록 Enterprise Voice 기능을 사용하여 방에 자격을 부여하려면 전화 시스템 라이선스가 있는 비즈니스용 Skype Online 계획 2 또는 Office 365 E5가 필요합니다(1).
    
- 모임에서 전화 접속 기능이 필요한 경우 오디오 회의 및 전화 시스템 라이선스가 필요합니다.  모임에서 전화 접속 기능이 필요한 경우 국내 또는 국내 및 국제 통화 플랜이 필요합니다. 
    
- 계정을 리소스 사서함 계정으로 구성해야 한다고 하여 Skype 룸 계정에는 Exchange Online 라이선스가 필요하지 않습니다.
    
## <a name="provisioning-overview"></a>프로비저닝 개요

다음 다이어그램에서는 Skype 룸 시스템 계정 프로비전 흐름에 대한 개요를 제공합니다.
  
![Skype 룸 시스템 프로비전 단계](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>새 회의실 식별

Exchange에 이미 계획 기능을 제공하는 리소스 공간 사서함이 있을 수 있습니다. 또는 Skype 룸 시스템 배포를 용이하게 하기 위해 리소스 사서함을 처음으로 만들 수도 있습니다. 어떤 경우든 테넌트에서 사용할 방 계정을 식별해야 합니다. Exchange Online 프로비전 및 비즈니스용 Skype 프로비전 섹션에서는 두 종류의 계정에 대한 지침을 제공합니다. 예를 들어 다음 두 방이 있으며 이 두 방 모두에 대해 Skype 룸 시스템을 배포하고자 하는 경우를 예로 들어 보겠습니다.
  
- 기존 리소스 사서함 계정: confrm1@contoso.onmicrosoft.com
    
- 새 리소스 사서함 계정: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online 프로비전

먼저 Exchange Online PowerShell에 연결 항목의 지침에 따라 [Exchange Online PowerShell에 연결합니다.](https://go.microsoft.com/fwlink/p/?LinkId=396554)
  
Skype 룸 시스템에 대한 기존 리소스 공간 사서함 계정을 설정하려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Skype 룸 시스템에 대한 새 Exchange 리소스 사서함 계정을 만들하려면 Exchange Online PowerShell에서 다음 명령을 실행합니다.
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

이전 명령은 계정을 사용하도록 설정하여 Skype 룸 시스템 사용에 대한 새 Exchange 리소스 사서함 계정을 설정하거나 생성합니다.
  
사서함을 만들고 나면 Exchange Online PowerShell의 Set-CalendarProcessing cmdlet을 사용하여 사서함을 구성할 수 있습니다. 자세한 내용은 단일 포리스트의 단일 포리스트 배포에서 3-6단계를 참조하세요.

## <a name="assigning-a-skype-for-business-online-license"></a>비즈니스용 Skype Online 라이선스 할당

이제 비즈니스용 Microsoft 365 또는 비즈니스용 Skype 추가 기능 라이선스 할당 또는 제거에 설명된 바와 같이 [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) 관리 포털을 사용하여 비즈니스용 Skype Online(계획 2) 또는 비즈니스용 [Skype](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)Online(계획 3) 라이선스를 할당할 수 있습니다. 
  
비즈니스용 Skype Online에 대한 라이선스를 할당한 후 로그인하고 비즈니스용 Skype 클라이언트를 사용하여 계정이 활성 상태임이 확인될 수 있습니다.
  
## <a name="skype-for-business-online-provisioning"></a>비즈니스용 Skype Online 프로비전

리소스 공간 사서함 계정을 생성하고 사용하도록 설정하고 비즈니스용 Skype Online에 대한 계정에 라이선스를 부여한 후 계정이 Exchange Online 포리스트에서 비즈니스용 Skype Online 포리스트로 동기화될 Windows Azure Active Directory 포리스트를 사용하여 동기화합니다. 비즈니스용 Skype Online 풀에서 Skype 룸 시스템 계정을 프로비전하려면 다음 단계가 필요합니다. 이러한 단계는 기존 리소스 사서함 계정 또는 새로 만든 계정(confrm1 또는 confrm2)에 대해 동일합니다. Exchange Online에서 사용하도록 설정하면 두 계정이 동일한 방식으로 비즈니스용 Skype Online과 동기화됩니다.
  
1. 원격 PowerShell 세션을 만들 수 있습니다. 비즈니스용 Skype Online 커넥터 모듈 및 Microsoft Online Services Sign-In 도우미를 다운로드하고 컴퓨터가 구성되어 있는지 확인합니다. 자세한 내용은 [다음을 위해](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)컴퓨터 Windows PowerShell.
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. 비즈니스용 Skype에 대해 Skype 룸 시스템 계정을 사용하도록 설정하려면 다음 명령을 실행합니다.
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    다음 명령을 사용하여 이 속성을 반환하면 비즈니스용 Skype 사용자가 있는 등록자 주소를 기존 계정 중 하나에서 얻을 수 있습니다.
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Skype 룸 시스템 계정에는 MFA(Multi-Factor Authentication)가 지원되지 않습니다. 

## <a name="password-expiration"></a>암호 만료

Microsoft 365 또는 Office 365에서 다른 암호 만료 정책을 구성하지 않는 한 모든 사용자 계정에 대한 기본 암호 만료 정책은 90일입니다. Skype 채팅방 시스템 계정의 경우 다음 단계에 따라 암호 사용 기간이 만료되지 않는 설정을 선택할 수 있습니다.
  
1. 테넌트 Windows Azure 관리자 자격 증명을 사용하여 Active Directory 세션을 만들 수 있습니다.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 다음 명령을 사용하여 이전에 만든 Skype 채팅방 계정의 암호 사용 기간이 만료되지 않는 설정 설정
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

자세한 내용은 [다음을 위해](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)컴퓨터 Windows PowerShell.
  
## <a name="validate"></a>유효성 검사

유효성 검사를 위해 비즈니스용 Skype 클라이언트를 사용하여 만든 계정에 로그인할 수 있습니다.

