---
title: 사용자가 프레미스에서 Enterprise Voice 사용하도록 설정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 사용자가 전화 시스템(클라우드 PBX)를 사용하려면 먼저 해당 사용자를 사용하도록 설정하고 Enterprise Voice 번호를 할당해야 합니다. 사용자가 여전히 사내 배포에 있는 동안에는 이 작업을 위해 사내 배포를 사용할 수 있습니다.
ms.openlocfilehash: aef74877d1a12d136bddc7eedc2a414dfad100830a88bb9a21695004be91d1a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54289086"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>사용자가 프레미스에서 Enterprise Voice 사용하도록 설정
 
사용자가 전화 시스템(클라우드 PBX)를 사용하려면 먼저 해당 사용자를 사용하도록 설정하고 Enterprise Voice 번호를 할당해야 합니다. 사용자가 여전히 사내 배포에 있는 동안에는 이 작업을 위해 사내 배포를 사용할 수 있습니다.

> [!Important]
> 비즈니스용 Skype 온라인은 2021년 7월 31에 사용 중지된 후 더 이상 서비스에 액세스할 수 없습니다.  또한 비즈니스용 Skype 서버 Cloud Connector Edition과 비즈니스용 Skype Online을 통한 PSTN 연결은 더 이상 지원되지 않습니다.  직접 라우팅 을 사용하여 프레미스 전화 통신 Teams [방법을 학습합니다.](/MicrosoftTeams/direct-routing-landing-page)
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>사용자가 프레미스에서 Enterprise Voice 번호를 할당할 수 있도록 설정하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 화면 시작 메뉴 또는 데스크톱 바로 가기를 사용하여 비즈니스용 Skype 서버 를 열 수 있습니다.
    
    브라우저 창을 연 다음 관리자 URL을 입력하여 관리자 URL을 비즈니스용 Skype 서버 있습니다.
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.
    
4. **사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.
    
5. 표에서 비즈니스용 Skype 사용하도록 설정할 온라인 사용자 계정을 Enterprise Voice.
    
6. 편집 **메뉴에서** 자세한 정보 **표시를 클릭합니다.**
    
7. 전화 **통신에서** 에서 를 **Enterprise Voice.**
    
8. 줄 **URI를 클릭하고** 고유한 정규화된 전화 번호(예: tel:+14255550200)를 입력합니다. 그런 다음 **커밋을 클릭합니다.**
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>사용자가 프레미스에서 사용자를 사용하도록 설정하는 경우의 Enterprise Voice 고려 사항

경우에 따라 사용자가 전화를 걸고 받을 수 있도록 Enterprise Voice 방법을 수정해야 할 수 있습니다. 배포에 다음 조건을 충족하는 사용자가 있는 경우 사용자가 다음 조건을 충족할 수 있도록 하는 단계를 Enterprise Voice.
  
- 사용자가 비즈니스용 Skype 또는 Enterprise Voice에 대해 사용하도록 설정되지 않고 사용자를 만든 다음 비즈니스용 Skype Online과 동기화한 경우 영향을 받는 각 사용자에 대해 다음 cmdlet을 실행하여 해당 환경의 값을 실제 값으로 바니다. \< \>
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 사용자가 이미 비즈니스용 Skype 사용하도록 설정되어 있지만 Enterprise Voice Online으로 이동하기 전에 LineURI를 사용하도록 설정하지 않은 경우 비즈니스용 Skype Online으로 이동하기 전에 각 사용자에 대해 다음 cmdlet을 실행합니다.
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 사용자가 이미 비즈니스용 Skype 활성화되어 있지만 Enterprise Voice 활성화되어 있지 않은 경우, LineURI가 이미 할당된 경우에도 영향을 받는 각 사용자에 대해 다음 cmdlet을 실행합니다.
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```