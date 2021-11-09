---
title: Skype 룸 시스템 하이브리드 배포
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 이 항목을 읽고 하이브리드 환경에서 룸 Skype 배포하는 방법을 배워야 합니다.
ms.openlocfilehash: caebf77f0ef5abb2b56c64446ad04a052d8f98f9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841950"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype 룸 시스템 하이브리드 배포

이 항목을 읽고 하이브리드 환경에서 룸 Skype 배포하는 방법을 배워야 합니다.
  
## <a name="hybrid-deployments"></a>하이브리드 배포

토폴로지에서 비즈니스용 Skype 서버 및 Exchange Online 사서함을 호스팅하고 Skype Room System 리소스 사서함을 호스트하려는 경우 Exchange Online. 또한 이 섹션에서는 배포된 하이브리드 시나리오에 대해 Exchange Online Exchange Server 설명합니다.
  
자세한 정보를 위해 LyncSample.com 도메인에 대해 LyncSample.ccstp.net 도메인을 사용할 수 있습니다.
  
1. Exchange 프로비전에 설명된 Exchange Online 관리 셸에 연결하여 LyncSample.ccsctp.net 관리 센터(Exchange Online)에서 리소스 사서함을 만들 수 있습니다.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    로그인할 때 OWA 연결을 lrstest5@LyncSample.ccsctp.net 있습니다.
    
2. Microsoft 365 Office 365 Exchange 관리 센터에서 전자 메일 주소 lrstest5@LyncSample.com(프레미스 도메인)를 추가하고 회신 주소로 설정합니다.
    
3. 프레미스 Active Directory 사용자 lrstest5@LyncSample.com 전자 메일 주소를 lrstest5@LyncSample.com 설정하고 대상 주소를 lrstest5@LyncSample.com.
    
4. 디렉터리 동기화를 트리거하고 동기화가 완료된 후 사용자가 AAD 센터에서 병합하고 Microsoft 365 또는 Office 365 Exchange 관리 센터의 받는 사람 리소스에서 속성을 변경할 수 없는지 확인합니다.
    
5. OWA 연결을 사용하여 lrstest5@LyncSample.com. (앞에서 온라인 도메인을 사용하여 OWA 연결을 확인했습니다.)
    
    사서함을 만들고 나면 사서함 관리 셸의 Set-CalendarProcessing 사용하여 Exchange Online 구성할 수 있습니다. 자세한 내용은 Single Forest On-prem Deployments에서 3~6단계를 참조하세요.
    
   > [!NOTE]
   > Exchange Server 및 Exchange Online 환경이 있는 경우 Exchange 관리 셸로 이동하고 -Enable-RemoteMailbox lrstest5@LyncSample.com -Room Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net 합니다. 그런 다음 디렉터리 동기화를 트리거합니다. 
  
    Skype Room System 사서함을 Exchange Online 이러한 Exchange 관리 셸 단계는 필요하지 않습니다. 6단계로 진행할 수 있습니다.
    
6. Skype 셸에서 비즈니스용 Skype cmdlet을 실행하여 비즈니스용 Skype 계정으로 사용하도록 설정할 수 있습니다.
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 위의 시나리오에서 비즈니스용 Skype 대신 비즈니스용 Skype 서버 비즈니스용 Skype Online이 있는 경우 Exchange 리소스 사서함을 프로비전한 후 비즈니스용 Skype 비즈니스용 Skype Online 프로비전에 설명된 대로 비즈니스용 Skype 계정을 프로비전합니다. 
  

