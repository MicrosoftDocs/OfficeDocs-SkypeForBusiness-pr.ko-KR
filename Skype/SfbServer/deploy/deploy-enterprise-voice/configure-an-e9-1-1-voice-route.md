---
title: 비즈니스용 Skype 서버에서 E9-1-1 음성 경로 구성
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
ms.assetid: 6933b840-0e7b-4509-ae43-bc9065677547
description: 비즈니스용 Skype 서버에서 E9-1-1 음성 Enterprise Voice.
ms.openlocfilehash: b5f3d12bb586a65fc1c553a021c1a27efb0c7f77
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804178"
---
# <a name="configure-an-e9-1-1-voice-route-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 E9-1-1 음성 경로 구성
 
비즈니스용 Skype 서버에서 E9-1-1 음성 Enterprise Voice. 
  
E9-1-1을 배포하려면 먼저 긴급 통화 음성 경로를 구성해야 합니다. 음성 경로를 만드는 데 대한 자세한 내용은 비즈니스용 Skype에서 음성 경로 만들기 또는 [수정을 참조하세요.](create-or-modify-a-voice-route.md) 예를 들어 배포에 기본 SIP 트렁크와 보조 SIP 트렁크가 포함된 경우 두 개 이상의 경로를 정의할 수 있습니다. 
  
> [!NOTE]
> E9-1-1 INVITE에 위치 정보를 포함하려면 게이트웨이를 통해 긴급 통화를 라우팅하도록 E9-1-1 서비스 공급자에 연결하는 SIP 트렁크를 구성해야 합니다. 이렇게하려면 **Set-CsTrunkConfiguration** cmdlet에서 EnablePIDFLOSupport 플래그를 True로 설정합니다. EnablePIDFLOSupport의 기본값은 False입니다. 예를 들어 PSTN(Public Switched Telephone Network) 게이트웨이 및 ELIN(Emergency Location Identification Number) 게이트웨이에 대해 수신 위치를 사용하도록 설정할 `Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.` 필요는 없습니다.
  
### <a name="to-configure-an-e9-1-1-voice-route"></a>E9-1-1 음성 경로를 구성하는 경우

1. RTCUniversalServerAdmins 그룹의 구성원인 계정 또는 CsVoiceAdministrator 관리 역할의 구성원으로 컴퓨터에 로그온합니다.
    
2.  비즈니스용 Skype 서버 관리 셸 시작: **시작,** **모든** 프로그램, 비즈니스용 **Skype 2015,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**
    
3. 다음 cmdlet을 실행하여 새 PSTN 사용 레코드를 만들 수 있습니다. 
    
    위치 정책의 **PSTN** 설정에 사용할 이름과 같아야 합니다. 배포에 여러 전화 사용 레코드가 사용 가능하기는 하지만 다음 예제에서는 사용 가능한 PSTN 사용법의 현재 목록에 "긴급 사용"을 추가합니다. 자세한 내용은 [비즈니스용 Skype에서 음성 정책, PSTN](voice-and-pstn.md)사용 레코드 및 음성 경로 구성을 참조하세요.
    
   ```powershell
   Set-CsPstnUsage -Usage @{add='EmergencyUsage'}
   ```

4. 다음 cmdlet을 실행하여 이전 단계에서 만든 PSTN 사용 레코드를 사용하여 새 음성 경로를 만들 수 있습니다.
    
    번호 패턴은 위치 정책의 긴급 전화  문자열 설정에 사용되는 번호 패턴과 같아야 합니다. 비즈니스용 Skype가 긴급 통화에 "+"를 추가하기 때문에 "+" 기호가 필요합니다. "Co1-pstngateway-1"은 E9-1-1 서비스 공급자 또는 ELIN 게이트웨이 서비스 ID의 SIP 트렁크 서비스 ID입니다. 다음 예에서는 음성 경로의 이름으로 "EmergencyRoute"를 사용 합니다.
    
   ```powershell
   New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}
   ```

5. SIP 트렁크 연결의 경우 다음 cmdlet을 실행하여 E9-1-1 서비스 공급자의 SIP 트렁크에서 처리되지 않는 통화에 대한 로컬 경로를 만드는 것이 좋습니다. E9-1-1 서비스 공급자에 대한 연결을 사용할 수 없는 경우 이 경로가 사용됩니다. 
    
    다음 예에서는 사용자가 음성 정책에 "로컬" 사용법을 사용했다고 가정합니다.
    
   ```powershell
   New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}
   ```


