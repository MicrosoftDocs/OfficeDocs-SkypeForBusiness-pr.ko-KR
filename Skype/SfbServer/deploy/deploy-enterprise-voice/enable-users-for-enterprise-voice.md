---
title: 사용자가 Enterprise Voice 사용하도록 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: '요약: 사용자가 이 문서에서 를 사용하여 전화를 걸고 Enterprise Voice 수 비즈니스용 Skype 서버.'
ms.openlocfilehash: 3dab9488b1d184f5d3dd215f4012933de1ca0245
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864345"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>사용자가 Enterprise Voice 사용하도록 비즈니스용 Skype 서버
 
**요약:** 사용자가 2016년 8월 2일부로 전화 걸고 받을 수 있도록 설정하는 Enterprise Voice 비즈니스용 Skype 서버.
  
사용자 Enterprise Voice 또는 업무를 통해 전화 걸기 기능을 배포한 후 다음 절차에 따라 다음 절차를 사용하여 사용자가 다음 절차를 사용하여 전화를 걸 수 Enterprise Voice.
  
> [!NOTE]
> 다음 절차 중 첫 번째 절차만 제어판을 사용하여 비즈니스용 Skype 서버 있습니다. 나머지 절차에서는 관리 셸에서만 비즈니스용 Skype 서버 있습니다. 
  
- 사용자 계정을 사용자 계정으로 Enterprise Voice.
    
- (선택 사항) 사용자 계정에 사용자별 음성 정책을 할당합니다.
    
- (선택 사항) 사용자 계정에 사용자별 다이얼 플랜을 할당합니다.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>사용자 계정을 사용하도록 설정하려면 Enterprise Voice

1. RTCUniversalServerAdmins 그룹의 구성원이나 **CsVoiceAdministrator, CsServerAdministrator** 또는 **CsAdministrator** 관리  역할의 구성원으로 컴퓨터에 로그온합니다.
    
2. 제어판을 비즈니스용 Skype 서버 를 니다.
    
3. 왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.
    
4. **사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.
    
5. 표에서 사용자 계정에서 사용하도록 설정할 사용자 계정을 Enterprise Voice.
    
6. **편집** 메뉴에서 **자세한 정보 표시** 를 클릭합니다.
    
7. 사용자 **비즈니스용 Skype 서버 편집** 페이지의 전화 통신에서 를 **Enterprise Voice.**
    
8. 줄 **URI를 클릭한** 다음 고유한 정규화된 전화 번호(예: )를 입력합니다. `tel:+14255550200`
    
9. **커밋** 을 클릭합니다.
    
사용자가 기본 설정을 사용할 수 있도록 Enterprise Voice 전역(기본적으로 할당) 또는 사용자 관련 다이얼 플랜을 사용자에게 할당해야 합니다. 기본적으로 모든 사용자에게는 전역 음성 정책 및 다이얼 플랜이 할당됩니다. 음성 정책 또는 다이얼 플랜이 사용자 계정이 있는 사이트의 사이트 수준에 있는 경우 해당 사이트 정책이 사용자에게 자동으로 적용됩니다. 사용자당 음성 정책 또는 다이얼 플랜을 사용자에게 적용하려면 **Grant-CsVoicePolicy** 및 **Grant-CsDialPlan** cmdlet을 실행해야 합니다. 자세한 내용은 이 항목의 다음 절차를 참조하십시오.
## <a name="voice-policy-assignment"></a>음성 정책 할당

전역 및 사이트 수준 음성 정책은 전역 및 사이트 수준 음성 정책에 대해 사용하도록 설정된 모든 사용자 계정에 Enterprise Voice. 특정 사용자 또는 그룹에 적용되는 음성 정책을 만들 수도 있습니다. 이러한 사용자당 정책은 사용자 또는 그룹에 명시적으로 할당해야 합니다. 전역 또는 사이트 음성 정책을 사용하도록 설정된 모든 사용자에 대해 Enterprise Voice 이 섹션을 건너뛰고 이 항목의 뒤부분에 있는 [다이얼](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) 플랜 할당 섹션을 계속 진행할 수 있습니다.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>사용자별 음성 정책을 할당하기 위해

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 기존 사용자 음성 정책을 사용자에게 할당하려면 명령 프롬프트에서 다음을 실행합니다.
    
   ```powershell
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    이 예에서는 표시 이름이 Bob Kelly인 사용자에게 **VoicePolicyJapan** 으로 음성 정책이 할당됩니다.
    
## <a name="dial-plan-assignment"></a>다이얼 플랜 할당
<a name="BKMK_DialPlanAssignment"> </a>

Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대한 사용자 계정 구성을 완료하려면 사용자에게 다이얼 플랜이 할당되어 있어야 합니다. 사용자 계정은 기존 사용자당 다이얼 플랜을 명시적으로 할당하지 않는 경우 전역 다이얼 플랜을 자동으로 사용하거나 사이트 수준 다이얼 플랜을 사용하게 됩니다. 전역 또는 사이트 다이얼 플랜을 사용하도록 설정된 모든 사용자에 대해 전역 Enterprise Voice 이 섹션을 건너뛰어도 됩니다.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>사용자별 다이얼 플랜을 할당하기 위해

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.
    
2. 비즈니스용 Skype 서버 시작: **시작,** 모든 프로그램, 비즈니스용 Skype **2015를** 클릭한 다음 관리 **비즈니스용 Skype 서버 를 클릭합니다.**
    
3. 사용자별 다이얼 플랜을 할당하려면 명령 프롬프트에서 다음을 실행합니다.
    
   ```powershell
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    예를 들면 다음과 같습니다.
    
   ```powershell
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    이 예에서는 표시 이름이 Bob Kelly인 사용자에게 **이름이 DialPlanJapan인** 사용자 다이얼 플랜이 할당됩니다.
    

