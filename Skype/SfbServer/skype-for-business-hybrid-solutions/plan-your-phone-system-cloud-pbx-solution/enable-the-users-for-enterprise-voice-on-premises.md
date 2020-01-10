---
title: 온-프레미스 Enterprise Voice 사용자 설정
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 4598565a-c228-4265-ad03-d2aef95b31a0
description: 사용자가 Office 365 (클라우드 PBX)에서 전화 시스템을 사용 하는 경우 먼저 엔터프라이즈 음성에 대해 사용 하도록 설정 하 고 전화 번호를 할당 해야 합니다. 사용자가 온-프레미스 배포에 남아 있는 동안 온-프레미스 배포를 사용 하 여이 작업을 수행 합니다.
ms.openlocfilehash: 8bf8720896aa8115cb24d3b632b4ae576f466bcc
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003478"
---
# <a name="enable-the-users-for-enterprise-voice-on-premises"></a>온-프레미스 Enterprise Voice 사용자 설정
 
사용자가 Office 365 (클라우드 PBX)에서 전화 시스템을 사용 하는 경우 먼저 엔터프라이즈 음성에 대해 사용 하도록 설정 하 고 전화 번호를 할당 해야 합니다. 사용자가 온-프레미스 배포에 남아 있는 동안 온-프레미스 배포를 사용 하 여이 작업을 수행 합니다.
  
### <a name="to-enable-a-user-for-enterprise-voice-on-premises-and-assign-a-phone-number"></a>사용자가 온-프레미스 Enterprise Voice를 사용 하도록 설정 하 고 전화 번호를 할당 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 시작 메뉴 또는 바탕 화면 바로 가기를 사용 하 여 비즈니스용 Skype 서버 제어판을 엽니다.
    
    브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype Server 제어판을 열 수도 있습니다.
    
3. 왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.
    
4. **사용자 검색** 상자에 표시 이름, 성, 이름, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 사용 하도록 설정할 사용자 계정의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 **찾기를**클릭 합니다.
    
5. 표에서 Enterprise Voice에 사용할 비즈니스용 Skype Online 사용자 계정을 클릭 합니다.
    
6. **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.
    
7. **전화 통신**에서 **엔터프라이즈 음성을**클릭 합니다.
    
8. **줄 URI**를 클릭 하 고 고유한 정규화 된 전화 번호를 입력 합니다 (예: tel: + 14255550200). 그런 다음 **커밋을**클릭 합니다.
    
## <a name="special-considerations-when-enabling-users-for-enterprise-voice-on-premises"></a>온-프레미스에서 엔터프라이즈 음성을 사용할 때의 특별 고려 사항

경우에 따라 엔터프라이즈 음성에 대 한 사용자가 전화를 걸고 받을 수 있도록 하는 방법을 수정 해야 할 수 있습니다. 배포에 다음 조건을 충족 하는 사용자가 있는 경우 엔터프라이즈 음성에 대 한 사용자를 사용 하도록 설정 된 단계를 수행 합니다.
  
- 온-프레미스 광고에서 사용자를 만든 다음 비즈니스용 skype 또는 엔터프라이즈 음성에 대해 사용 하도록 설정 하지 않고 비즈니스용 skype Online과 동기화 하는 경우, 각 영향을 받는 각 사용자에 대해 다음 cmdlet을 실행 하 여 환경의 값 \< \> 을 실제 값으로 바꿉니다.
    
  ```powershell
  Enable-CsUser $username -HostingProvider sipfed.online.lync.com -SipAddress sip:<UserName>@<SIP Domain>
  ```

  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 사용자가 온-프레미스 비즈니스용 Skype를 이미 사용 하도록 설정 되어 있지만 Enterprise Voice에 대해 사용 하도록 설정 되지 않았거나, 비즈니스용 Skype Online으로 이동 하기 전에 LineURI를 할당 하지 않은 경우 각 사용자에 대해 다음 cmdlet을 실행 합니다.
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true -LineUri "tel:+<Telephone Number>"
  ```

- 온-프레미스 비즈니스용 Skype에서 사용자를 이미 사용 하도록 설정 했지만 Enterprise Voice에서 사용할 수 없는 경우에도 해당 사용자에 대해 다음 cmdlet을 실행 합니다.
    
  ```powershell
  Set-CsUser $username -EnterpriseVoiceEnabled $true
  ```


