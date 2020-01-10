---
title: Office 365에서 Skype 대화방 시스템 계정 프로 비전
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 이 항목에서는 Office 365에서 Skype 대화방 시스템 계정을 구축 하는 방법에 대해 자세히 알아보세요.
ms.openlocfilehash: 66686af36e3f71f91114d10eb448dd0a77ad1a57
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003018"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Office 365에서 Skype 대화방 시스템 계정 프로 비전
 
이 항목에서는 Office 365에서 Skype 대화방 시스템 계정을 구축 하는 방법에 대해 자세히 알아보세요.
  
다음 섹션에서는 Office 365 테 넌 트에 대 한 Skype 대화방 시스템 계정 프로비저닝에 대해 설명 합니다.
  
## <a name="office-365-prerequisites"></a>Office 365 필수 조건

온라인 테 넌 트가 다음 요구 사항을 충족 해야 합니다.
  
- Office 365 요금제에는 비즈니스용 Skype Online 요금제 2 또는 Office 365 E1, E3 또는 E5가 포함 되어 있어야 합니다. <br/>비즈니스용 Skype Online 요금제에 대 한 자세한 내용은 [비즈니스용 Skype Online 서비스 설명을](https://technet.microsoft.com/library/jj822172.aspx)참조 하세요.
    
- 테 넌 트에 비즈니스용 Skype의 회의 기능이 설정 되어 있어야 합니다.
    
- 테 넌 트가 Exchange Online을 사용 하도록 설정 되어 있어야 합니다. 
    
- 테 넌 트 원격 관리자에 게는 다음과 같은 PowerShell 액세스가 있어야 합니다.
    
  - Exchange 원격 PowerShell 액세스
    
  - 비즈니스용 Skype Online 원격 PowerShell 액세스
    
  - Windows PowerShell 용 windows Azure Active Directory 모듈을 사용 하 여 Office 365 디렉터리 액세스 액세스
    
Skype 채팅방 계정의 경우 다음 라이선스가 필요 합니다.
  
- Skype 모임을 활성화 하려면 비즈니스용 Skype Online 계획 2 또는 Office 365 E1 또는 E3 라이선스가 필요 합니다.
    
- 전화 번호를 사용 하 여 공간을 사용할 수 있도록 엔터프라이즈 음성 기능을 사용 하 여 공간을 entitle 전화 시스템 라이선스가 있는 비즈니스용 Skype Online 계획 2 또는 Office 365 E5가 필요 합니다 (1).
    
- 모임에서 전화 접속 기능이 필요한 경우에는 오디오 회의 및 전화 시스템 라이선스가 필요 합니다.  모임에서 전화 접속 기능이 필요한 경우 국내 또는 국내 및 국제 통화 요금제가 필요 합니다. 
    
- 계정을 리소스 사서함 계정으로 구성 해야 하기 때문에 Skype 대화방 계정에 Exchange Online 라이선스가 필요 하지 않습니다.
    
## <a name="provisioning-overview"></a>프로 비전 개요

다음 다이어그램은 Office 365의 Skype 대화방 시스템 계정 프로비저닝 흐름에 대 한 개요를 제공 합니다.
  
![O365 용 Skype 채팅방 시스템 프로비저닝 단계](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>새 회의실 식별

Exchange에 일정 기능을 제공 하는 리소스 공간 사서함이 이미 있거나 Skype 대화방 시스템 배포를 용이 하 게 하기 위해 처음으로 리소스 사서함을 만들 수 있습니다. 어떤 경우 든 테 넌 트에서 사용할 룸 계정을 식별 해야 합니다. Exchange Online 제공 및 비즈니스용 Skype 프로 비전 섹션에서는 두 가지 계정에 대 한 지침을 제공 합니다. 예를 들어 다음 두 채팅방을 사용 하 고 있으며 두 가지 모두에 대해 Skype 채팅방 시스템을 배포 하 고 싶습니다.
  
- 기존 리소스 사서함 계정: confrm1@contoso.onmicrosoft.com
    
- 새 리소스 사서함 계정: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online 프로비저닝

먼저, [Exchange Online powershell에 연결](https://go.microsoft.com/fwlink/p/?LinkId=396554)항목의 지침에 따라 Exchange online powershell에 연결 합니다.
  
Skype 채팅방 시스템의 기존 리소스 공간 사서함 계정을 설정 하려면 Exchange Online PowerShell에서 다음 명령을 실행 합니다.
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Skype 대화방 시스템용 새 Exchange 리소스 사서함 계정을 만들려면 Exchange Online PowerShell에서 다음 명령을 실행 합니다.
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

이전 명령은 계정을 사용 하 여 Skype 룸 시스템 사용에 대 한 새 Exchange 리소스 사서함 계정을 설정 하거나 만듭니다.
  
사서함을 만든 후 Exchange Online PowerShell의 집합-CalendarProcessing cmdlet을 사용 하 여 사서함을 구성할 수 있습니다. 자세한 내용은 단일 포리스트 온-프레미스 배포의 3 ~ 6 단계를 참조 하세요.

## <a name="assigning-a-skype-for-business-online-license"></a>비즈니스용 Skype Online 라이선스 할당

이제 비즈니스용 [office 365에 라이선스 할당 또는 제거](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) 또는 비즈니스용 [skype 추가 기능 라이선스](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)에 설명 된 대로 Office 365 관리 포털을 사용 하 여 비즈니스용 skype online (계획 2) 또는 비즈니스용 skype online (계획 3) 라이선스를 할당할 수 있습니다. 
  
비즈니스용 Skype Online에 대 한 라이선스를 할당 한 후에는 로그인 하 고 비즈니스용 Skype 클라이언트를 사용 하 여 계정이 활성 상태 인지 확인할 수 있습니다.
  
## <a name="skype-for-business-online-provisioning"></a>비즈니스용 Skype Online 프로 비전

이전에 표시 된 대로 리소스 공간 사서함 계정을 생성 하 고 사용 하도록 설정 하 고 비즈니스용 Skype Online에 대 한 계정을 사용 하도록 허가 받은 후에는이 계정이 Exchange Online 포리스트에서 비즈니스용 Skype Online 포리스트와 동기화 합니다. Windows Azure Active Directory 포리스트. 다음 단계는 비즈니스용 Skype Online 풀에서 Skype 채팅방 시스템 계정을 구축 하는 데 필요 합니다. 이러한 단계는 Exchange Online에서 사용 하도록 설정 된 경우와 동일한 방식으로 기존 리소스 사서함 계정 또는 새로 만든 계정 (confrm1 또는 confrm2) 모두에 대해 동일 합니다. 이러한 두 계정은 모두 비즈니스용 Skype Online에 동기화 됩니다.
  
1. 원격 PowerShell 세션을 만듭니다. 비즈니스용 Skype Online 커넥터 모듈 및 Microsoft Online Services 로그인 도우미를 다운로드 하 고 컴퓨터가 구성 되어 있는지 확인 합니다. 자세한 내용은 [Windows PowerShell 용 컴퓨터 설정을](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하세요.
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. 비즈니스용 Skype에 대해 Skype 대화방 시스템 계정을 사용 하도록 설정 하려면 다음 명령을 실행 합니다.
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    다음 명령을 사용 하 여이 속성을 반환 하 여 기존 계정 중 하나에서 비즈니스용 Skype 사용자가 속한 RegistrarPool 주소를 가져올 수 있습니다.
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>Skype 대화방 시스템 계정에는 MFA (다단계 인증)가 지원 되지 않습니다. 

## <a name="password-expiration"></a>비밀 번호 만료

Office 365에서 다른 암호 만료 정책을 구성 하지 않는 한 모든 사용자 계정에 대 한 기본 암호 만료 정책은 90 일입니다. Skype 대화방 시스템 계정의 경우 다음 단계에 따라 암호 사용 기간 제한 없음 설정을 선택할 수 있습니다.
  
1. 테 넌 트 전역 관리자 자격 증명을 사용 하 여 Windows Azure Active Directory 세션을 만듭니다.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. 다음 명령을 사용 하 여 이전에 만든 Skype 채팅방 시스템 룸 계정에 대 한 암호 사용 기간 제한 없음 설정을 설정 합니다.
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

자세한 내용은 [Windows PowerShell 용 컴퓨터 설정을](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하세요.
  
## <a name="validate"></a>Validate

유효성 검사를 위해 Skype for Business 클라이언트를 사용 하 여 만든 계정에 로그인 할 수 있습니다.

