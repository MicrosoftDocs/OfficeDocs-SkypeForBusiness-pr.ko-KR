---
title: Microsoft Teams 룸 비즈니스용 Skype 서버
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
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 이 항목을 참조하여 Microsoft Teams 룸 배포하는 방법에 비즈니스용 Skype 서버.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2990e1314ee851156bc11430ecf933fe31552117
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615194"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Microsoft Teams 룸 비즈니스용 Skype 서버
  
이 항목에서는 단일 포리스트, Microsoft Teams 룸 배포할 때 디바이스 계정을 추가하는 방법을 설명합니다.
  
2013 SP1 이상 및 2013 SP1 이상 및 2015년 비즈니스용 Skype 서버 있는 단일 포리스트, Windows PowerShell 배포가 있는 경우 디바이스 계정을 만들 수 있습니다. Exchange 다중 포리스트 배포를 사용하는 경우 동일한 결과를 생성하는 동등한 cmdlet을 사용할 수 있습니다. 이러한 cmdlet은 이 섹션에 설명되어 있습니다.

  
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

   $strExchangeServer 서버의 FQDN(완전 자격을 갖춘 도메인 이름)은 Exchange $strLyncFQDN 배포의 FQD 비즈니스용 Skype 서버N입니다.

2. 세션을 설정한 후 새 사서함을 만들고 RoomMailboxAccount로 사용하도록 설정하거나 기존 방 사서함에 대한 설정을 변경합니다. 이렇게 하면 계정이 인증할 수 Microsoft Teams 룸.

    기존 리소스 사서함을 변경하는 경우:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   새 리소스 사서함을 만드는 경우:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 디바이스 계정에 다양한 Exchange 속성을 설정하여 사용자에 대한 모임 환경을 개선할 수 있습니다. 속성 섹션에서 어떤 속성을 설정해야 Exchange 수 있습니다.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. 암호가 만료되지 않는 경우 cmdlet을 사용하여 Windows PowerShell 수 있습니다. 자세한 내용은 암호 관리를 참조하세요.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Active Directory에서 계정을 사용하도록 설정하면 계정이 인증되어 Microsoft Teams 룸.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. 다음 풀에서 비즈니스용 Skype 서버 Active Directory 계정을 Microsoft Teams 룸 사용하여 디바이스 계정을 비즈니스용 Skype 서버 있습니다.

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    SIP(세션 시작 프로토콜) 주소 및 도메인 컨트롤러를 사용하여 Project

7. **선택 사항입니다.** 또한 계정에 대한 Microsoft Teams 룸 사용하도록 설정하여 PSTN(공용 전환 전화 네트워크) 전화 통화를 Enterprise Voice 수 있습니다. Enterprise Voice 클라이언트에 대한 PSTN Microsoft Teams 룸 필요는 없지만 클라이언트에 대한 PSTN Microsoft Teams 룸하려면 다음을 사용하도록 설정하는 방법에 대해 다음과 같습니다.

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   또한 제공된 도메인 컨트롤러 및 전화 번호 예제를 사용자만의 정보로 바야 합니다. 매개 변수 $true 동일하게 유지됩니다.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>샘플: Exchange 및 비즈니스용 Skype 서버 룸 계정 설정

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

## <a name="related-topics"></a>관련 주제

[Microsoft Teams 룸](rooms-configure-accounts.md)

[Microsoft Teams 룸 계획](rooms-plan.md)
  
[Microsoft Teams 룸 배포](rooms-deploy.md)
  
[Microsoft Teams 룸 콘솔 구성](console.md)
  
[Microsoft Teams 룸 관리](rooms-manage.md)
