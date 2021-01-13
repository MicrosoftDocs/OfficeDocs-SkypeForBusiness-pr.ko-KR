---
title: Skype 룸 시스템 하이브리드 배포
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
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: 이 항목을 읽고 하이브리드 환경에서 Skype 룸 시스템을 배포하는 방법을 배워 읽습니다.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805898"
---
# <a name="skype-room-system-hybrid-deployments"></a>Skype 룸 시스템 하이브리드 배포

이 항목을 읽고 하이브리드 환경에서 Skype 룸 시스템을 배포하는 방법을 배워 읽습니다.
  
## <a name="hybrid-deployments"></a>하이브리드 배포

토폴로지의 비즈니스용 Skype 서버 및 Exchange Online이 있으며 Exchange Online에서 Skype 룸 시스템 리소스 사서함을 호스트하려는 경우 다음 단계를 수행합니다. 이 섹션에서는 Exchange Online과 Exchange Online을 모두 배포한 하이브리드 시나리오에 Exchange Server 설명합니다.
  
예를 들어, LyncSample.com 도메인에 대해 LyncSample.ccstp.net 도메인을 사용하는 것이 좋습니다.
  
1. Exchange Online 프로비전에 설명된 LyncSample.ccsctp.net Exchange 관리 셸에 연결하여 Exchange 관리 센터(LyncSample.ccsctp.net)에서 리소스 사서함을 만들 수 있습니다.
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    로그인할 때 OWA 연결을 lrstest5@LyncSample.ccsctp.net 수 있습니다.
    
2. Microsoft 365 또는 Office 365 Exchange 관리 센터에서 전자 메일 주소(lrstest5@LyncSample.com 도메인)를 추가하고 회신 주소로 설정합니다.
    
3. 프레미스 Active Directory 사용자 lrstest5@LyncSample.com 전자 메일 주소를 lrstest5@LyncSample.com 주소로 설정하고 대상 주소를 lrstest5@LyncSample.com.
    
4. 디렉터리 동기화를 트리거하고 동기화가 완료된 후 사용자가 AAD에서 병합하는지와 Microsoft 365 또는 Office 365 Exchange 관리 센터의 받는 사람 리소스에서 속성을 변경할 수 없는지 확인합니다.
    
5. 다음을 사용하여 OWA 연결을 lrstest5@LyncSample.com. (앞에서 온라인 도메인을 사용하여 OWA 연결을 확인했습니다.)
    
    사서함을 만들고 나면 Exchange Online Set-CalendarProcessing 셸에서 사서함을 구성할 수 있습니다. 자세한 내용은 단일 포리스트 On-prem 배포에서 3-6단계를 참조하세요.
    
   > [!NOTE]
   > Exchange Server 및 Exchange Online이 있는 하이브리드 환경인 경우 Exchange 관리 셸로 이동하여 Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room으로 이동하십시오. 그런 다음 디렉터리 동기화를 트리거합니다. 
  
    Exchange Online에서 Skype 채팅방 시스템 사서함을 호스트하려는 경우 이러한 Exchange 관리 셸 단계가 필요하지 않습니다. 6단계로 진행할 수 있습니다.
    
6. 비즈니스용 Skype 관리 셸에서 다음 cmdlet을 실행하여 비즈니스용 Skype에 대해 Skype 채팅방 시스템 계정을 사용하도록 설정합니다.
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> 위의 시나리오에서 비즈니스용 Skype 서버 대신 비즈니스용 Skype Online이 있는 경우 Exchange 리소스 사서함을 프로비전한 후 비즈니스용 Skype Online 프로비전에 설명된 대로 비즈니스용 Skype 계정을 프로비전합니다. 
  

