---
title: 사용자가 비즈니스용 Skype Enterprise Voice 사용하도록 설정
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: '요약: 사용자가 비즈니스용 Skype 서버에서 사용자를 사용하여 전화를 걸고 Enterprise Voice 방법을 설명하는 정보를 제공합니다.'
ms.openlocfilehash: 3c18836f1c2b03d2c6d50712f33d9e3a900b43b3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830878"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>사용자가 비즈니스용 Skype Enterprise Voice 사용하도록 설정
 
**요약:** 사용자가 비즈니스용 Skype 서버에서 전화를 걸고 받을 수 있도록 하는 Enterprise Voice 방법을 배워야 합니다.
  
사용자 Enterprise Voice 또는 직장을 통해 전화 기능을 배포한 후 다음 절차에 따라 사용자가 다음 절차를 사용하여 다음 절차를 사용하여 전화를 걸 수 Enterprise Voice.
  
> [!NOTE]
> 다음 절차 중 첫 번째 절차만 비즈니스용 Skype 서버 제어판을 사용하여 수행할 수 있습니다. 나머지 절차에서는 비즈니스용 Skype 서버 관리 셸만 사용할 수 있습니다. 
  
- 사용자 계정에서 사용자 계정을 Enterprise Voice.
    
- (선택 사항) 사용자 계정에 사용자별 음성 정책을 할당합니다.
    
- (선택 사항) 사용자 계정에 사용자별 다이얼 플랜을 할당합니다.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>사용자 계정에서 사용자 계정을 사용하도록 설정하려면 Enterprise Voice

1. RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator,** **CsServerAdministrator 또는 CsAdministrator** 관리  역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 제어판을 니다.
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.
    
4. **사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.
    
5. 표에서 사용자 계정에서 사용하도록 설정할 사용자 계정을 Enterprise Voice.
    
6. **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.
    
7. 비즈니스용 **Skype 서버** 사용자 편집 페이지의 전화 **통신에서** **Enterprise Voice.**
    
8. 줄 **URI를** 클릭한 다음 정규화된 고유한 전화 번호(예: tel:+14255550200)를 입력합니다.
    
9. **커밋** 을 클릭합니다.
    
사용자에 대한 사용자 Enterprise Voice 설정이 끝나면 사용자에게 음성 정책 및 다이얼 플랜(기본적으로 할당)이나 사용자별이 할당되어 있는지를 확인해야 합니다. 기본적으로 모든 사용자에게는 전역 음성 정책 및 다이얼 플랜이 할당됩니다. 음성 정책 또는 다이얼 플랜이 사용자 계정이 있는 사이트의 사이트 수준에 있는 경우 해당 사이트 정책이 사용자에게 자동으로 적용됩니다. 사용자당 음성 정책 또는 다이얼 플랜을 사용자에게 적용하려면 **Grant-CsVoicePolicy** 및 **Grant-CsDialPlan** cmdlet을 실행해야 합니다. 자세한 내용은 이 항목의 다음 절차를 참조하십시오.
## <a name="voice-policy-assignment"></a>음성 정책 할당

전역 및 사이트 수준 음성 정책은 전역 및 사이트 수준 음성 정책에 대해 사용하도록 설정된 모든 사용자 계정에 Enterprise Voice. 특정 사용자 또는 그룹에 적용되는 음성 정책을 만들 수도 있습니다. 이러한 사용자당 정책은 사용자 또는 그룹에 명시적으로 할당해야 합니다. 전역 또는 사이트 음성 정책을 사용하도록 설정된 모든 사용자에 대해 전역 Enterprise Voice 사용하려는 경우 이 [](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) 섹션을 건너뛰고 이 항목의 부분에 있는 다이얼 플랜 할당 섹션을 계속 진행하면 됩니다.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>사용자별 음성 정책을 할당하기 위해

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
3. 기존 사용자 음성 정책을 사용자에게 할당하려면 명령 프롬프트에서 다음을 실행합니다.
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    이 예에서는 표시 이름이 Bob Kelly인 사용자에게 **VoicePolicyJapan** 이름이 지정된 음성 정책이 할당됩니다.
    
## <a name="dial-plan-assignment"></a>다이얼 플랜 할당
<a name="BKMK_DialPlanAssignment"> </a>

Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대한 사용자 계정 구성을 완료하려면 사용자에게 다이얼 플랜이 할당되어 있어야 합니다. 사용자 계정은 기존 사용자당 다이얼 플랜을 명시적으로 할당하지 않을 때 전역 다이얼 플랜 또는 사이트 수준 다이얼 플랜이 있는 경우 자동으로 사용하게 됩니다. 전역 또는 사이트 다이얼 플랜을 사용하도록 설정된 모든 사용자에 대해 전역 또는 사이트 Enterprise Voice 이 섹션을 건너뛰어도 됩니다.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>사용자별 다이얼 플랜을 할당하기 위해

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
3. 사용자별 다이얼 플랜을 할당하려면 명령 프롬프트에서 다음을 실행합니다.
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    이 예에서는 표시 이름이 Bob Kelly인 사용자에게 **DialPlanJapan** 이름이 지정된 사용자 다이얼 플랜이 할당됩니다.
    

