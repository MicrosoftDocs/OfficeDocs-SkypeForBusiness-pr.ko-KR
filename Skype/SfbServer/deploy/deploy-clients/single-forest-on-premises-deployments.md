---
title: Skype 채팅방 시스템 단일 포리스트 온-프레미스 배포
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: 이 항목을 읽으면 단일 포리스트 온-프레미스 환경에서 Skype 대화방 시스템을 배포 하는 방법을 알아보세요.
ms.openlocfilehash: 107d4724defa11cbe506dcfa1b4f3c4725ee9910
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245870"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype 채팅방 시스템 단일 포리스트 온-프레미스 배포
 
이 항목을 읽으면 단일 포리스트 온-프레미스 환경에서 Skype 대화방 시스템을 배포 하는 방법을 알아보세요.
  
이 섹션에서는 단일 포리스트 온-프레미스 배포에서 호스팅되는 Exchange Server 및 비즈니스용 Skype 서버에서 Skype 채팅방 시스템 계정을 프로 비전 하는 단계에 대해 간략하게 설명 합니다.
  
## <a name="single-forest-on-premises-deployments"></a>단일 포리스트 온-프레미스 배포

회의실에 대 한 리소스 사서함 계정이 이미 있는 경우이를 사용할 수 있습니다. 그렇지 않은 경우에는 새 항목을 만들어야 합니다. Exchange Management Shell (PowerShell) 또는 Exchange 관리 콘솔을 사용 하 여 새 리소스 사서함 계정을 만들 수 있습니다. Skype 대화방 시스템용 새 (이전 사서함 삭제 및 다시 만들기) 리소스 사서함을 사용 하는 것이 좋습니다. 사서함 데이터를 삭제 한 다음 Outlook 클라이언트를 사용 하 여 다시 만드는 사서함으로 다시 내보내야 합니다 (자세한 내용은 메시지, 일정, 작업 및 연락처 내보내기 또는 백업 참조). 사서함을 삭제 하 여 손실 된 모임을 복원 하려면 [삭제 된 사서함 연결 또는 복원을](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)참조 하세요. 
  
기존 리소스 사서함 계정 (예: LRS-01)을 사용 하려면 아래 단계를 따르세요.
  
1. 다음 Exchange 관리 PowerShell 명령을 실행 합니다.
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. 새 사서함을 만들려는 경우에는 단일 포리스트 온-프레미스 Exchange 조직의 경우 다음 명령을 실행 합니다.
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   위 예제에서는 Active Directory에서 사용 하도록 설정 된 사용자 계정과 온-프레미스 Exchange 조직에서 회의실 사서함을 만듭니다. RoomMailboxPassword 매개 변수는 사용자 계정에 대 한 암호를 지정 합니다.
    
3. 모임을 수락/거절 하 여 충돌을 자동으로 해결 하도록 계정을 구성 합니다. Skype 실 시스템-Exchange의 회의실 계정은 개인이 관리할 수 있지만, 개인이 모임을 수락 하기 전에는 Skype 채팅방 시스템 홈 화면 일정에 표시 되지 않습니다.
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   사용할 수 있는 전체 명령 집합은 설정-CalendarProcessing를 참조 하세요.
    
   Outlook에서 모임 이끌이가 온라인 비즈니스용 Skype 모임을 하도록 하려면 다음 명령을 실행 하 여 새 계정의 메일 설명을 설정 합니다. 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. 다음 명령을 사용 하 여 지역화 된 문자열을 구성 합니다. 조직에서 요구 하는 경우 사용자 지정 번역을 추가할 수도 있습니다. 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. 선택 사항: 사용자에 게 비즈니스용 Skype 회의실에 대 한 정보를 제공 하는 모임 수락 텍스트와 모임 일정을 예약 하 고 참가할 때 기대할 수 있는 항목을 구성 합니다. 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Active Directory에서 리소스 사서함 계정 확인

위의 1 단계에서 Exchange에서 만든 회의실 사서함 계정이 Active Directory의 비활성 사용자 개체 일 수 있습니다. Active Directory에서 계정을 사용 하지 않도록 설정한 경우, Skype 채팅방 시스템에서 Kerberos/NTLM 인증을 사용 하 여 로그인 하거나 인증할 수 없습니다. Skype 대화방 시스템 클라이언트는 일정 설정을 검색 하기 위해 Exchange 웹 서비스에 대해 인증할 수 있어야 하며, 화이트 보드 내용으로 전자 메일을 보낼 수도 있어야 합니다. 
  
따라서 계정을 사용할 수 없는 경우 Active Directory에서 다음을 수행 하 여이 계정을 사용 하도록 설정 해야 합니다. 
  
1. Active Directory에서 다음 명령을 실행 하 여 계정 로그온을 사용 하도록 설정 합니다. 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   이 명령을 실행 하면 현재 암호를 입력 하 라는 메시지가 표시 되 고 확인을 위해 암호를 두 번 다시 입력 합니다.
    
2. 비밀 번호가 설정 되 면 다음 명령을 실행 하 여 계정을 사용 하도록 설정 합니다. 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>비즈니스용 Skype의 Skype 대화방 시스템 계정 사용

이 섹션에서는 Skype 대화방 시스템에 구성 되는 비즈니스용 Skype를 사용 하도록 설정 하는 데 필요한 단계에 대해 간략하게 설명 합니다. 
  
회의 방에 대 한 리소스 사서함 계정을 만든 후 비즈니스용 skype Server Management Shell을 사용 하 여 비즈니스용 skype 서비스에 대 한 Skype 대화방 시스템 계정을 사용 하도록 설정 합니다.
  
> [!NOTE]
> 다음 절차에서는 Active Directory에서 Skype 대화방 시스템 계정을 사용 하도록 설정 했다고 가정 합니다. 
  
1. 다음 명령을 실행 하 여 비즈니스용 Skype 서버 풀에서 Skype 대화방 시스템 계정을 사용 하도록 설정 합니다.
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. 선택 사항:이 계정에서 엔터프라이즈 음성에 대 한 계정을 사용 하도록 설정 하 여 PSTN 전화를 걸고 받을 수 있도록 허용 합니다. Skype 채팅방 시스템에는 엔터프라이즈 음성이 필요 하지 않지만, 엔터프라이즈 음성에 대해이 기능을 사용 하도록 설정 하지 않으면, Skype 채팅방 시스템 클라이언트는 PSTN 전화 접속 기능을 제공할 수 없게 됩니다.
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Skype 채팅방 시스템 회의실 계정에 대해 Enterprise Voice를 사용 하도록 설정 하는 경우 조직에 적합 한 제한 된 음성 정책을 구성 하 고 있는지 확인 합니다. 비즈니스용 Skype 회의실을 공개적으로 사용할 수 있는 경우 다른 사용자가이 리소스를 사용 하 여 예약 또는 임시 모임에 참가할 수 있습니다. 모임에 참가 한 후에는 상대방이 모든 번호로 전화를 걸 수 있습니다. 비즈니스용 Skype Server에서 전화 걸기 기능에는 사용자의 음성 정책 (이 경우 모임에 참가 하는 데 사용 되는 Skype 대화방 시스템 계정)이 사용 됩니다. 이전 버전의 Lync Server에는 이끌이의 음성 정책이 사용 됩니다. 따라서 이전 버전의 Lync Server 사용자가 회의실을 예약 하 고 Skype 채팅방 시스템 룸 계정을 초대 하는 경우 모든 사용자가 비즈니스용 Skype 회의실을 사용 하 여 모임에 참가 하 고 모든 국내/지역 또는 국제 전화를 걸 수 있습니다. 번호 (이끌이는 해당 번호로 전화를 걸 수 있는 한) 
  

