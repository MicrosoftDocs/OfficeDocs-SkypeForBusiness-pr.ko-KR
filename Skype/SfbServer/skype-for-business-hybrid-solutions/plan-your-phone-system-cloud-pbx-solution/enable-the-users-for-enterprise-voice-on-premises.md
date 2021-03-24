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
description: 사용자가 전화 시스템(클라우드 PBX)을 사용하려면 먼저 해당 사용자를 사용하도록 설정하고 Enterprise Voice 번호를 할당해야 합니다. 사용자가 여전히 사내 배포에 있는 동안에는 이 작업을 위해 사내 배포를 사용할 수 있습니다.
ms.openlocfilehash: b26e51ba316c63e0f992b843a7763586d7e9b575
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098594"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>사용자가 프레미스에서 Enterprise Voice 사용하도록 설정
 
사용자가 전화 시스템(클라우드 PBX)을 사용하려면 먼저 해당 사용자를 사용하도록 설정하고 Enterprise Voice 번호를 할당해야 합니다. 사용자가 여전히 사내 배포에 있는 동안에는 이 작업을 위해 사내 배포를 사용할 수 있습니다.

> [!Important]
> 비즈니스용 Skype Online은 2021년 7월 31에 서비스가 더 이상 액세스할 수 없습니다.  또한 비즈니스용 Skype 서버 또는 클라우드 커넥터 버전과 비즈니스용 Skype Online을 통해 지원되지 않는 모든 사내 환경 간의 PSTN 연결도 더 이상 지원되지 않습니다.  직접 라우팅을 사용하여 프레미스 전화 통신 네트워크를 Teams에 연결하는 [방법을 학습합니다.](/MicrosoftTeams/direct-routing-landing-page)
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>사용자가 프레미스에서 Enterprise Voice 번호를 할당할 수 있도록 설정하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 시작 메뉴 또는 데스크톱 바로 가기를 사용하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다.
    
    브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 열 수 있습니다.
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.
    
4. **사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.
    
5. 표에서 비즈니스용 Skype Online 사용자 계정을 클릭하여 비즈니스용 Skype를 Enterprise Voice.
    
6. 편집 **메뉴에서** 자세한 정보 **표시를 클릭합니다.**
    
7. 전화 **통신에서** 에서 를 **Enterprise Voice.**
    
8. 줄 **URI를 클릭하고** 고유한 정규화된 전화 번호(예: tel:+14255550200)를 입력합니다. 그런 다음 **커밋을 클릭합니다.**
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>사용자가 Enterprise Voice 때의 특별한 고려 사항

경우에 따라 사용자가 전화를 걸고 받을 수 있도록 사용자를 Enterprise Voice 방법을 수정해야 할 수 있습니다. 배포에 다음 조건을 충족하는 사용자가 있는 경우 사용자가 다음 조건을 충족할 수 있도록 하는 단계를 Enterprise Voice.
  
- 사용자가 비즈니스용 Skype 또는 비즈니스용 Skype를 사용하도록 설정되지 않고 비즈니스용 Skype Online과 동기화된 후Enterprise Voice LineURI 집합이 없는 경우 영향을 받는 각 사용자에 대해 다음 cmdlet을 실행하여 해당 환경의 값을 실제 값으로 \< \> 바니다.
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 사용자가 비즈니스용 Skype Online으로 이동하기 전에 이미 비즈니스용 Skype를 사용할 수 있지만 Enterprise Voice 사용할 수 없는 경우 각 사용자에 대해 다음 cmdlet을 실행합니다.
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 사용자가 이미 비즈니스용 Skype on premises에서 사용하도록 설정되어 있지만 Enterprise Voice LineURI가 이미 할당된 경우에도 영향을 받는 각 사용자에 대해 다음 cmdlet을 실행합니다.
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```