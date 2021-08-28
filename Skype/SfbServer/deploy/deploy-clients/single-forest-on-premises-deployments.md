---
title: Skype Room System 단일 포리스트 사내 배포
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
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 이 항목을 통해 단일 포리스트 Skype 환경에서 룸 시스템을 배포하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 7a68171ebf8d56b61ed77c6cef9739b701a0c07e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58591942"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype Room System 단일 포리스트 사내 배포
 
이 항목을 통해 단일 포리스트 Skype 환경에서 룸 시스템을 배포하는 방법에 대해 자세히 알아보습니다.
  
이 섹션에서는 단일 포리스트 Skype 배포에서 호스팅되는 Exchange Server 비즈니스용 Skype 서버 룸 시스템 계정을 프로비전하는 단계를 간략하게 설명합니다.
  
## <a name="single-forest-on-premises-deployments"></a>단일 포리스트 온-프레미스 배포

회의 공간에 대한 리소스 사서함 계정이 이미 있는 경우 사용할 수 있습니다. 그렇지 않으면 새 계정을 만들어야 합니다. PowerShell(Exchange 관리 셸)을 사용하여 새 리소스 Exchange 관리 콘솔 만들 수 있습니다. Room System에 새(이전 사서함 삭제 및 다시 만들기) 리소스 사서함을 Skype 좋습니다. 사서함 데이터를 삭제하기 전에 백업한 다음 Outlook 클라이언트를 사용하여 다시 만든 사서함으로 내보낼 수 있습니다(자세한 내용은 메시지, 일정, 작업 및 연락처 내보내기 또는 백업 참조). 사서함을 삭제하여 손실된 모임을 복원하려면 [삭제된 커넥트 복원을 참조합니다.](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help) 
  
기존 리소스 사서함 계정(예: LRS-01)을 사용하려면 다음 단계를 따릅니다.
  
1. 다음 관리 powerShell Exchange 실행합니다.
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. 새 사서함을 만들 계획인 경우 단일 포리스트 Exchange 조직에 대해 다음 명령을 실행합니다.
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   위의 예에서는 Active Directory에 사용 가능한 사용자 계정을 만들고 조직 내 회의실에 대한 회의실 사서함을 Exchange 있습니다. RoomMailboxPassword 매개 변수는 사용자 계정에 대한 암호를 지정합니다.
    
3. 모임을 수락/거부하여 충돌을 자동으로 해결하도록 계정을 구성합니다. Skype Exchange 회의실 계정은 개인이 관리할 수 있지만 개인이 모임을 수락할 때까지는 Skype 시스템 홈 화면 일정에 나타나지 않습니다.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   사용 가능한 전체 명령 집합은 Set-CalendarProcessing을 참조하세요.
    
   모임 이끌이가 모임을 비즈니스용 Skype 온라인 모임으로 Outlook 다음 명령을 실행하여 새 계정에 대한 메일 설명을 설정합니다. 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. 다음 명령을 사용하여 지역화된 문자열을 구성합니다. 조직에서 필요한 경우 사용자 지정 번역을 추가할 수도 있습니다. 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. 선택 사항: 사용자에게 모임 예약 및 참가 시 예상되는 비즈니스용 Skype 미팅룸 정보를 제공하는 모임 수락 텍스트를 구성합니다. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Active Directory에서 리소스 사서함 계정 확인

위의 1단계에서 Exchange 사용자가 만든 회의실 사서함 계정은 Active Directory에서 사용하지 않도록 설정한 사용자 개체일 수 있습니다. Skype Active Directory에서 계정을 사용하지 않도록 설정한 경우 방 시스템은 Kerberos/NTLM 인증을 사용하여 로그인하거나 인증할 수 없습니다. Skype Room System 클라이언트는 일정 설정을 검색하기 위해 Exchange 웹 서비스에 대해 인증할 수 있어야 합니다. 또한 화이트보드 콘텐츠가 있는 전자 메일을 보낼 수도 있어야 합니다. 
  
따라서 계정을 사용하지 않도록 설정한 경우 다음을 수행하여 Active Directory에서 이 계정을 사용하도록 설정해야 합니다. 
  
1. Active Directory에서 다음 명령을 실행하여 계정 로그온을 사용하도록 설정합니다. 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   이 명령을 실행하면 현재 암호를 입력하라는 메시지가 표시되고 확인을 위해 암호를 두 번 다시 입력합니다.
    
2. 암호를 설정한 후 다음 명령을 실행하여 계정을 사용하도록 설정합니다. 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>사용자 Skype 룸 시스템 계정 사용 비즈니스용 Skype

이 섹션에서는 회의실 시스템에서 구성되는 회의실 계정에 대해 비즈니스용 Skype 설정하는 데 필요한 단계를 Skype 설명합니다. 
  
회의 회의실에 대한 리소스 사서함 계정을 만든 후 비즈니스용 Skype 서버 관리 셸을 사용하여 Skype 서비스용 회의실 시스템 계정을 비즈니스용 Skype 합니다.
  
> [!NOTE]
> 다음 절차에서는 Active Directory에서 Skype 계정을 사용하도록 설정했다고 가정합니다. 
  
1. 다음 명령을 실행하여 Skype 풀에서 비즈니스용 Skype 서버 실행합니다.
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. 선택 사항: 이 계정에서 사용자 계정을 사용하도록 설정하여 PSTN 전화 통화를 걸고 받을 수 Enterprise Voice. Enterprise Voice Room System에는 Skype 필요하지 않지만 Enterprise Voice 사용하도록 설정하지 않은 경우 Skype 룸 시스템 클라이언트는 PSTN 전화 걸기 기능을 제공할 수 없습니다.
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Enterprise Voice 회의실 Skype 사용하도록 설정하는 경우 조직에 적합한 제한된 음성 정책을 구성해야 합니다. 이 비즈니스용 Skype 미팅룸 공개적으로 사용할 수 있는 리소스인 경우 누구나 이 리소스를 사용하여 예약된 모임 또는 애드 호를 통해 모임에 참가할 수 있습니다. 모임에 참가한 후 어떤 번호로도 전화를 걸 수 있습니다. 비즈니스용 Skype 서버 전화 접속 기능은 사용자의 음성 정책을 사용(이 경우 모임에 참가하는 데 Skype 회의실 시스템 계정)을 사용하게 됩니다. 이전 버전의 Lync Server에서는 이끌이의 음성 정책이 사용됩니다. 따라서 이전 버전의 Lync Server 사용자가 회의실을 예약하고 Skype 회의실 계정을 초대하는 경우 이끌이가 해당 번호로 전화를 걸 수 있는 한 누구나 비즈니스용 Skype 미팅룸 사용하여 모임에 참가하고 모든 국가/지역 또는 국제 전화 번호로 전화를 걸 수 있습니다. 
