---
title: 사용자에 대해 통화 파크를 사용하도록 비즈니스용 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: 사용자가 2016년 8월에 통화 파크에 비즈니스용 Skype 서버 Enterprise Voice.
ms.openlocfilehash: 84a37ad9e3b77042c1c2c04d1d6562b3bb780ee2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386347"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>사용자에 대해 통화 파크를 사용하도록 비즈니스용 Skype
 
사용자가 2016년 8월에 통화 파크에 비즈니스용 Skype 서버 Enterprise Voice.
  
기본적으로 모든 사용자에 대해 통화 파크는 사용하지 않도록 설정됩니다. 사용자는 음성 정책에서 통화 파크를 사용하도록 설정해야 통화를 보거나 통화를 다시 검색할 수 있습니다.
  
전역 범위 또는 사이트 범위 또는 사용자 범위에서 통화 파크를 사용하도록 설정할 수 있습니다. 사용자 범위는 사이트 범위보다 우선하고 사이트 범위는 전역 범위보다 우선합니다. 음성 정책이 여러 개 있는 경우 전역 정책이 아닌 모든 정책을 검토하여 통화 파크를 사용하도록 설정합니다.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>사용자에 비즈니스용 Skype 서버 제어판을 사용하여 통화 파크를 사용하도록 설정하려면

1. **RTCUniversalServerAdmins** 그룹의 구성원이나 **CsVoiceAdministrator**, **CsServerAdministrator** 또는 **CsAdministrator** 관리 역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **음성 라우팅** 을 클릭합니다.
    
4. **음성 정책** 탭을 클릭합니다.
    
5. 기존 음성 정책을 두 번 클릭하여 **음성 정책 편집** 대화 상자를 엽니다.
    
6. **전화 걸기 기능** 에서 **통화 대기 사용** 을 선택합니다.
    
7. **확인** 을 클릭하여 음성 정책을 저장합니다.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Cmdlet을 사용하여 사용자에 대해 통화 파킹을 사용하도록 설정하려면

1. RTCUniversalServerAdmins 그룹의 구성원이나 CsVoiceAdministrator, CsServerAdministrator 또는 CsAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작 **: 시작,** 모든 **프로그램, 비즈니스용 Skype** **2015** 를 클릭한 다음 관리 **비즈니스용 Skype 서버 클릭합니다**.
    
3. 실행:
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    예를 들어 기본 전역 음성 정책에 대해 통화 파크를 사용하도록 설정하려면
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>참고 항목



[음성 정책 만들기 또는 수정 및 PSTN 사용 레코드 비즈니스용 Skype](voice-policy-and-pstn-usage-records.md)

