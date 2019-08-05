---
title: 비즈니스용 Skype 서버의 E9-1-1 음성 경로 구성
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
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 비즈니스용 Skype Server Enterprise Voice에서 E9 구성-1 ~ 1 개의 음성 경로
ms.openlocfilehash: 0ef8b1ba2b64c74cb2166c90dfdccf134df42252
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197439"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 E9-1-1 음성 경로 구성
 
비즈니스용 Skype Server Enterprise Voice에서 E9 구성-1 ~ 1 개의 음성 경로 
  
E9-1-1을 배포 하려면 먼저 긴급 통화 음성 경로를 구성 해야 합니다. 음성 경로를 만드는 방법에 대 한 자세한 내용은 비즈니스용 [Skype에서 음성 경로 만들기 또는 수정을](create-or-modify-a-voice-route.md)참조 하세요. 예를 들어 배포에 기본 SIP 트렁크 및 보조 SIP 트렁크가 포함 되어 있는 경우 둘 이상의 경로를 정의할 수 있습니다. 
  
> [!NOTE]
> E9-1-1 초대에 위치 정보를 포함 하려면 E9-1 서비스 공급자에 연결 된 SIP 트렁크를 구성 하 여 게이트웨이를 통해 비상 전화를 경로를 설정 해야 합니다. 이렇게 하려면 **집합-set-cstrunkconfiguration** Cmdlet의 EnablePIDFLOSupport 플래그를 True로 설정 합니다. EnablePIDFLOSupport의 기본 값은 False입니다. 예를 들어 `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` , 대체 PSTN (공개 통신 네트워크) 게이트웨이와 긴급 위치 id 번호 (elin) 게이트웨이에서는 위치를 수신할 필요는 없습니다.
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>E9-1-1 음성 경로를 구성 하려면

1. RTCUniversalServerAdmins 그룹의 구성원 인 계정이 나 CsVoiceAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온 합니다.
    
2.  비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype 2015**을 차례로 클릭 한 다음 비즈니스용 **skype Server management Shell**을 클릭 합니다.
    
3. 다음 cmdlet을 실행 하 여 새 PSTN 사용 레코드를 만듭니다. 
    
    이 이름은 위치 정책의 **PSTN** 설정에 사용 하는 이름과 같아야 합니다. 배포에 여러 개의 전화 사용 레코드가 있지만, 다음 예에서는 사용 가능한 PSTN 사용량의 현재 목록에 "비상 사용량"을 추가 합니다. 자세한 내용은 [비즈니스용 Skype에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성을](voice-and-pstn.md)참조 하세요.
    
   ```
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. 다음 cmdlet을 실행 하 여 이전 단계에서 만든 PSTN 사용 레코드를 사용 하 여 새 음성 경로를 만듭니다.
    
    번호 패턴은 위치 정책의 **긴급 전화 걸기 문자열** 설정에 사용 되는 번호 패턴을 동일 하 게 입력 해야 합니다. 비즈니스용 Skype가 긴급 통화에 "+"를 추가 하기 때문에 "+" 기호가 필요 합니다. "Co1-pstngateway-1"은 E9-1-1 서비스 공급자의 SIP 트렁크 서비스 ID 이거나 게이트웨이 서비스 ID의 ELIN입니다. 다음 예에서는 "EmergencyRoute"를 음성 경로의 이름으로 사용 합니다.
    
   ```
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. 선택적으로 SIP 트렁크 연결에 대해 다음 cmdlet을 실행 하 여 E9-1 서비스 공급자의 SIP 트렁크에서 처리 되지 않는 통화에 대 한 로컬 경로를 만드는 것이 좋습니다. 이 경로는 E9 서비스 공급자에 대 한 연결을 사용할 수 없는 경우에 사용 됩니다. 
    
    다음 예제에서는 사용자가 음성 정책에 "로컬"을 사용 하는 것으로 가정 합니다.
    
   ```
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


