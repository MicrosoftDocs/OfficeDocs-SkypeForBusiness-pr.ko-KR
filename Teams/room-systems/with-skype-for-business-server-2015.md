---
title: 비즈니스용 Skype 서버를 사용 하 여 Microsoft 팀 회의실 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 비즈니스용 Skype 서버를 사용 하 여 Microsoft 팀 회의실을 배포 하는 방법에 대 한 자세한 내용은이 항목을 참조 하세요.
ms.openlocfilehash: 0c970adeae5531b76b1ebfe55ab750efe8bd3ba3
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427767"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>비즈니스용 Skype 서버를 사용 하 여 Microsoft 팀 회의실 배포
  
이 항목에서는 단일 포리스트, 온-프레미스 배포를 사용 하는 경우 Microsoft 팀 대화방에 대 한 디바이스 계정을 추가 하는 방법에 대해 설명 합니다.
  
Exchange 2013 SP1 이상 및 비즈니스용 Skype Server 2015 이상에서 단일 포리스트, 온-프레미스 배포를 사용 하는 경우 제공 된 Windows PowerShell 스크립트를 사용 하 여 디바이스 계정을 만들 수 있습니다. 다중 포리스트 배포를 사용 하는 경우 동일한 결과를 생성 하는 동일한 cmdlet을 사용할 수 있습니다. 이 섹션에서는 이러한 cmdlet에 대해 설명 합니다.

  
Microsoft 팀 회의실 배포를 시작 하기 전에 연결 된 cmdlet을 실행할 수 있는 권한이 있는지 확인 합니다.
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   $StrExchangeServer는 Exchange server의 FQDN (정규화 된 도메인 이름)이 고 $strLyncFQDN는 비즈니스용 Skype 서버 배포의 FQDN입니다.

2. 세션을 설정한 후 새 사서함을 만들고이를 RoomMailboxAccount 사용 하도록 설정 하거나 기존 회의실 사서함에 대 한 설정을 변경할 수 있습니다. 이렇게 하면 계정이 Microsoft 팀 방에 대 한 인증을 받을 수 있습니다.

    기존 리소스 사서함을 변경 하려면 다음을 수행 합니다.

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   새 리소스 사서함을 만드는 경우:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 디바이스 계정에서 다양 한 Exchange 속성을 설정 하 여 사용자의 모임 환경을 향상 시킬 수 있습니다. Exchange 속성 섹션에서 설정 해야 하는 속성을 확인할 수 있습니다.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. 암호가 만료 되지 않도록 결정 한 경우에는 Windows PowerShell cmdlet을 사용 하 여 설정할 수 있습니다. 자세한 내용은 암호 관리를 참조 하세요.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Active Directory에서 계정을 사용 하도록 설정 하 여 Microsoft 팀 대화방에 인증 합니다.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. 비즈니스용 Skype 서버 풀에서 Microsoft 팀 회의실 Active Directory 계정을 사용 하도록 설정 하 여 비즈니스용 Skype 서버에서 디바이스 계정을 사용 하도록 설정 합니다.

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    프로젝트에 대 한 SIP (세션 시작 프로토콜) 주소 및 도메인 컨트롤러를 사용 해야 합니다.

7. **).** 또한 Microsoft 팀 대화방에서 계정에 엔터프라이즈 음성을 사용 하도록 설정 하 여 일반 PSTN (교환 전화 네트워크) 전화를 걸고 받을 수 있습니다. 엔터프라이즈 음성은 Microsoft 팀 방에 대 한 요구 사항이 아니지만 Microsoft 팀원에 게 PSTN 전화 접속 기능을 설정 하려면 다음 방법을 사용 하세요.

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   또한 제공 된 도메인 컨트롤러 및 전화 번호 예제를 자신의 정보로 바꿔야 합니다. 매개 변수 값 $true 동일 하 게 유지 됩니다.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>샘플: Exchange 및 비즈니스용 Skype Server (온-프레미스)의 채팅방 계정 설정

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="see-also"></a>참고 항목

[Microsoft 팀 대화방 계정 구성](room-systems-v2-configure-accounts.md)

[Microsoft 팀 회의실 계획](skype-room-systems-v2-0.md)
  
[Microsoft 팀 대화방 배포](room-systems-v2.md)
  
[Microsoft 팀 대화방 콘솔 구성](console.md)
  
[Microsoft 팀 대화방 관리](skype-room-systems-v2.md)
