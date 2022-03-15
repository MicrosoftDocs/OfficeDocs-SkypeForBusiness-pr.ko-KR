---
title: Microsoft Teams 룸 비즈니스용 Skype 서버
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
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 이 항목을 참조하여 Microsoft Teams 룸 배포하는 방법에 비즈니스용 Skype 서버.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 358fa9295ec150f9c57a18252c76d309078b8e29
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503485"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Microsoft Teams 룸 비즈니스용 Skype 서버
  
이 항목에서는 단일 포리스트, Microsoft Teams 룸 배포할 때 리소스 계정을 추가하는 방법을 설명합니다.
  
2013 SP1 이상 및 2013 SP1 이상 및 2015년 비즈니스용 Skype 서버 있는 단일 포리스트, 프레미스 배포가 있는 경우 제공된 Windows PowerShell 스크립트를 사용하여 디바이스 계정을 만들 수 있습니다. Exchange 다중 포리스트 배포를 사용하는 경우 동일한 결과를 생성하는 동등한 cmdlet을 사용할 수 있습니다. 이러한 cmdlet은 이 섹션에 설명되어 있습니다.
  
배포를 시작하기 전에 Microsoft Teams 룸 cmdlet을 실행할 수 있는 올바른 권한이 있는지 확인해야 합니다.
  

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

   $strExchangeServer 서버의 FQDN(완전 자격을 갖춘 도메인 이름)은 Exchange 및 $strLyncFQDN 배포의 FQDN 비즈니스용 Skype 서버 있습니다.

2. 세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 방 사서함에 대한 설정을 변경합니다. 이렇게 하면 계정이 인증할 수 Microsoft Teams 룸.

    기존 리소스 사서함을 변경하는 경우:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoome01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   새 리소스 사서함을 만드는 경우:

   ``` Powershell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Alias ConferenceRoom01 -Name "Conference Room 01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 사용자에 대한 모임 환경을 개선하기 위해 Exchange 리소스 계정에 다양한 Teams 룸 속성을 설정할 수 있습니다. 속성 섹션에서 어떤 속성을 설정해야 Exchange 수 있습니다.

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. 리소스 계정에서 암호 만료를 해제합니다.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. Active Directory에서 리소스 계정을 사용하도록 설정하면 리소스 계정이 인증되어 Microsoft Teams 룸.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. 다음 풀에서 비즈니스용 Skype 서버 Active Directory 계정을 Microsoft Teams 룸 사용하여 리소스 계정을 비즈니스용 Skype 서버 있습니다.

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    및 특성을 `-DomainController` `-RegistrarPool` 환경에 적합한 값으로 변경합니다.

7. **선택 사항입니다.** 또한 계정에 대한 Microsoft Teams 룸 사용하도록 설정하여 PSTN(공용 전환 전화 네트워크) 전화 통화를 Enterprise Voice 수 있습니다. Enterprise Voice 필요는 없지만 Microsoft Teams 룸 PSTN 전화 걸기 기능을 Microsoft Teams 룸 사용하려면 다음을 사용할 수 있습니다.

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   또한 제공된 도메인 컨트롤러 및 전화 번호 예제를 사용자만의 정보로 바야 합니다. 매개 변수 $true 동일하게 유지됩니다. 음성 정책을 바꾸고 요금제 정책 이름을 다이얼로 연결해야 합니다.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>샘플: Exchange 및 비즈니스용 Skype 서버 룸 계정 설정

``` Powershell
New-Mailbox -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) -UserPrincipalName ConferenceRoom01@contoso.com

Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"

Enable-CsMeetingRoom -Identity ConferenceRoom01@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity ConferenceRoom01 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName dk
Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName e15dp2.contoso.com
```

## <a name="related-topics"></a>관련 항목

[Microsoft Teams 룸](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
