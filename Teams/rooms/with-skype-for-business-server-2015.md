---
title: 비즈니스용 Skype 서버 사용하여 Microsoft Teams 룸 배포
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Rooms
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 비즈니스용 Skype 서버 사용하여 Microsoft Teams 룸 배포하는 방법에 대한 자세한 내용은 이 항목을 참조하세요.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 53903052efe28a85400ba8b418bd8869ef2dec4e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271683"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>비즈니스용 Skype 서버 사용하여 Microsoft Teams 룸 배포
  
이 항목에서는 단일 포리스트 온-프레미스 배포가 있는 경우 Microsoft Teams 룸 리소스 계정을 추가하는 방법을 설명합니다.
  
Exchange 2013 SP1 이상 및 2015 이상 비즈니스용 Skype 서버 단일 포리스트 온-프레미스 배포가 있는 경우 제공된 Windows PowerShell 스크립트를 사용하여 디바이스 계정을 만들 수 있습니다. 다중 포리스트 배포를 사용하는 경우 동일한 결과를 생성하는 동일한 cmdlet을 사용할 수 있습니다. 이러한 cmdlet은 이 섹션에서 설명합니다.
  
Microsoft Teams 룸 배포를 시작하기 전에 연결된 cmdlet을 실행할 수 있는 권한이 있는지 확인합니다.
  

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

   $strExchangeServer Exchange 서버의 FQDN(정규화된 도메인 이름)이며 $strLyncFQDN 비즈니스용 Skype 서버 배포의 FQDN입니다.

2. 세션을 설정한 후 새 사서함을 만들어 RoomMailboxAccount로 사용하도록 설정하거나 기존 회의실 사서함에 대한 설정을 변경합니다. 이렇게 하면 계정이 Microsoft Teams 룸 인증할 수 있습니다.

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

3. Teams 룸 리소스 계정에서 다양한 Exchange 속성을 설정하여 사용자 모임 환경을 개선할 수 있습니다. Exchange 속성 섹션에서 설정해야 하는 속성을 확인할 수 있습니다.

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. 리소스 계정에서 암호 만료를 해제합니다.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. Active Directory에서 리소스 계정을 사용하도록 설정하여 Microsoft Teams 룸 인증합니다.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. 비즈니스용 Skype 서버 풀에서 Microsoft Teams 룸 Active Directory 계정을 사용하도록 설정하여 비즈니스용 Skype 서버 리소스 계정을 사용하도록 설정합니다.

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    `-DomainController` 사용자 환경에 적합한 값으로 및 `-RegistrarPool` 특성을 변경합니다.

7. **선택적.** 계정에 Enterprise Voice 사용하도록 설정하여 Microsoft Teams 룸 PSTN(공중 전화망) 전화 통화를 만들고 받을 수 있도록 허용할 수도 있습니다. Enterprise Voice Microsoft Teams 룸 대한 요구 사항은 아니지만 Microsoft Teams 룸 대한 PSTN 전화 걸기 기능을 원하는 경우 사용하도록 설정하는 방법은 다음과 같습니다.

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   또한 제공된 도메인 컨트롤러 및 전화 번호 예제를 사용자 고유의 정보로 바꿔야 합니다. $true 매개 변수 값은 동일하게 유지됩니다. 또한 음성 정책을 바꾸고 플랜 정책 이름을 전화 접속해야 합니다.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>샘플: Exchange의 회의실 계정 설정 및 온-프레미스 비즈니스용 Skype 서버

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

[Microsoft Teams 룸 대한 계정 구성](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
