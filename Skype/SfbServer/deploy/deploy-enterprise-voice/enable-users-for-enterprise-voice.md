---
title: 비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 사용자 활성화
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f252b23b-9641-4160-aa81-bf06dc2eced3
description: '요약: 비즈니스용 Skype 서버에서 엔터프라이즈 음성을 사용 하 여 사용자가 전화를 걸고 받을 수 있도록 하는 방법에 대해 알아봅니다.'
ms.openlocfilehash: 8a94fe28cc492cdeac5eee476d6886fc8674ae13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197428"
---
# <a name="enable-users-for-enterprise-voice-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 엔터프라이즈 음성에 대 한 사용자 활성화
 
**요약:** 비즈니스용 Skype 서버에서 엔터프라이즈 음성을 사용 하 여 사용자가 전화를 걸고 받을 수 있도록 하는 방법에 대해 알아봅니다.
  
회사 음성 또는 업무를 통해 전화를 건 후 다음 절차를 사용 하 여 사용자가 엔터프라이즈 음성을 사용 하 여 전화를 걸 수 있습니다.
  
> [!NOTE]
> 다음 절차 중 첫 번째는 비즈니스용 Skype Server 제어판을 사용 하 여 수행할 수 있습니다. 나머지 절차에서는 비즈니스용 Skype Server Management Shell만 사용할 수 있습니다. 
  
- 엔터프라이즈 음성에 대 한 사용자 계정을 사용 하도록 설정 합니다.
    
- ) 사용자 계정에 사용자 특정 음성 정책을 할당 합니다.
    
- ) 사용자 계정에 사용자 특정 다이얼 플랜을 할당 합니다.
    
### <a name="to-enable-a-user-account-for-enterprise-voice"></a>엔터프라이즈 음성에 대 한 사용자 계정을 사용 하도록 설정 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 또는 **CsVoiceAdministrator**, **Csserveradministrator**또는 **csadministrator** 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype Server 제어판을 엽니다.
    
3. 왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.
    
4. **사용자 검색** 상자에 설정 하려는 사용자 계정의 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 줄의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음을 클릭 합니다. **찾습니다**.
    
5. 표에서 Enterprise Voice에 사용할 사용자 계정을 클릭 합니다.
    
6. **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.
    
7. **비즈니스용 Skype 서버 사용자 편집** 페이지의 **전화 통신**에서 **엔터프라이즈 음성을**클릭 합니다.
    
8. **줄 URI**를 클릭 한 다음 고유한 정규화 된 전화 번호를 입력 합니다 (예: tel: + 14255550200).
    
9. **커밋**을 클릭합니다.
    
사용자가 엔터프라이즈 음성을 사용할 수 있도록 설정 하려면 사용자에 게 음성 정책 및 다이얼 플랜 (전역 (기본적으로 할당 됨) 인지 여부) 또는 사용자 관련 기능을 지정 해야 합니다. 기본적으로 모든 사용자에 게는 전역 음성 정책 및 다이얼 플랜을 할당 합니다. 사용자 계정이 속한 사이트의 사이트 수준에 음성 정책 또는 다이얼 플랜이 있는 경우 해당 사이트 정책이 사용자에 게 자동으로 적용 됩니다. 사용자 단위 음성 정책 또는 다이얼 플랜을 사용자에 게 적용 하려면 **CsVoicePolicy** 및 **부여-csdialplan 다이얼** cmdlet을 실행 해야 합니다. 자세한 내용은이 항목의 다음 절차를 참조 하세요.
## <a name="voice-policy-assignment"></a>음성 정책 할당

전역 및 사이트 수준 음성 정책은 Enterprise Voice에 대해 사용 하도록 설정 된 모든 사용자 계정에 자동으로 할당 됩니다. 특정 사용자 또는 그룹에 적용 되는 음성 정책을 만들 수도 있습니다. 이러한 사용자별 정책은 사용자 또는 그룹에 명시적으로 할당 되어야 합니다. Enterprise Voice를 사용 하도록 설정 된 모든 사용자에 대해 전역 또는 사이트 음성 정책을 사용 하려는 경우이 섹션을 건너뛰고이 항목의 뒷부분에 나오는 [다이얼 플랜 할당](enable-users-for-enterprise-voice.md#BKMK_DialPlanAssignment) 섹션을 계속할 수 있습니다.
  
### <a name="to-assign-a-user-specific-voice-policy"></a>사용자 관련 음성 정책 지정

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 사용자에 게 기존 사용자 음성 정책을 할당 하려면 명령 프롬프트에서 다음을 실행 합니다.
    
   ```
   Grant-CsVoicePolicy -Identity <UserIdParameter> -PolicyName <String>
   ```

    예를 들면 다음과 같습니다.
    
   ```
   Grant-CsVoicePolicy -Identity "Bob Kelly" -PolicyName VoicePolicyJapan
   ```

    이 예제에서 표시 이름이 Bob 최소라 인 사용자에 게는 이름 **VoicePolicyJapan**음성 정책이 할당 됩니다.
    
## <a name="dial-plan-assignment"></a>다이얼 플랜 배정
<a name="BKMK_DialPlanAssignment"> </a>

Enterprise Voice 사용자 또는 전화 접속 회의 사용자에 대 한 사용자 계정 구성을 완료 하려면 사용자에 게 다이얼 플랜을 할당 해야 합니다. 사용자 계정에 글로벌 다이얼 플랜 (있는 경우)이 자동으로 사용 되며, 기존 사용자 단위 다이얼 플랜을 명시적으로 할당 하지 않은 경우에는 사이트 수준 다이얼 플랜입니다. Enterprise Voice를 사용 하도록 설정 된 모든 사용자에 대해 전역 또는 사이트 다이얼 플랜을 사용 하려는 경우이 섹션을 건너뛸 수 있습니다.
  
### <a name="to-assign-a-user-specific-dial-plan"></a>사용자 지정 다이얼 플랜을 할당 하려면

1. CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.
    
2. 비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 사용자 지정 다이얼 플랜을 할당 하려면 명령 프롬프트에서 다음을 실행 합니다.
    
   ```
   Grant-CsDialPlan -Identity <UserIdParameter> -PolicyName <String>
   ```

    예를 들면 다음과 같습니다.
    
   ```
   Grant-CsDialPlan -Identity "Bob Kelly" -PolicyName DialPlanJapan
   ```

    이 예제에서 표시 이름이 Bob 최소라 인 사용자는 이름 **DialPlanJapan**를 사용 하 여 사용자 다이얼 플랜을 할당 합니다.
    

