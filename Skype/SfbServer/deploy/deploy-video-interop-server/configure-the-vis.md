---
title: 비즈니스용 Skype 서버에서 비디오 Interop 서버 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: '요약: 비즈니스용 Skype 서버에서 VIS (비디오 Interop Server) 역할을 구성 합니다.'
ms.openlocfilehash: 2618a7829fde79bd63eb2c3c91dbe921530e3b04
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798065"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 비디오 Interop 서버 구성
 
**요약:** 비즈니스용 Skype 서버에서 VIS (영상 Interop 서버) 역할을 구성 합니다.
  
 Windows PowerShell을 사용 하 여 VIS에서 비디오 trunks 연결 하는 설정을 구성 합니다. VIS 서비스가 설치 되 면 전역 범위를 포함 하는 비디오 트렁크 구성이 만들어집니다. 이 비디오 트렁크 구성은 더 구체적인 범위를 사용 하 여 영상 트렁크 구성이 없는 모든 trunks에 VIS에 의해 적용 됩니다. 비디오 트렁크 구성은 비디오 trunks 적용 되는 설정 모음입니다.
  
## <a name="configure-video-trunk-and-dial-plan"></a>비디오 트렁크 및 다이얼 플랜 구성

다음 Windows PowerShell 명령을 사용 하 여 VIS 및 모든 비디오 게이트웨이 간의 토폴로지 문서에 정의 된 새로 정의 된 트렁크와 연결할 비디오 트렁크 구성 및 다이얼 플랜을 지정 합니다. 이러한 모든 설정은 전역, 사이트 또는 서비스 (비디오 게이트웨이) 수준에서 설정할 수 있습니다. 
  
전역 범위를 사용 하는 다이얼 플랜은 비즈니스용 Skype 서버 배포 별로 생성 됩니다. 이 다이얼 플랜은 보다 구체적인 범위를 포함 하는 다이얼 플랜이 없는 모든 trunks에 VIS 하 여 적용 됩니다. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>Windows PowerShell을 사용 하 여 VIS 구성

1. 다음 Windows PowerShell cmdlet을 사용 하 여 VIS 및 Cisco 통합 커뮤니케이션 관리자 (CallManager 또는 CUCM) 간 트렁크에서 사용할 새 비디오 트렁크 구성 (설정 모음)을 만듭니다.
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    수정 해야 하는 기존 비디오 트렁크가 있는 경우 다음 Windows PowerShell cmdlet을 사용 합니다.
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    특정 비디오 트렁크 구성과 관련 된 설정을 보려면 다음 Windows PowerShell cmdlet을 사용 합니다.
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    특정 비디오 트렁크 구성을 제거 하려면 다음 Windows PowerShell cmdlet을 사용 하세요 (특정 트렁크에 대 한 보다 구체적으로 범위가 지정 된 비디오 트렁크 구성이 없는 경우 전역으로 범위를 설정한 비디오 트렁크 구성이 적용 됨).
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 다음 Windows PowerShell cmdlet을 사용 하 여 트렁크와 연결할 다이얼 플랜을 설정 합니다.
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

**CsVoiceNormalizationRule** 명령은 예상 VIS 및 CUCM 조작에 방해가 되는 기본 규칙을 재정의 하는 데 필요 합니다.
> [!NOTE]
> [제거-csdialplan 다이얼](https://docs.microsoft.com/powershell/module/skype/remove-csdialplan?view=skype-ps) 플랜을 제거 하는 데 사용 될 수 있습니다.
  
요청 URI에 VIS가 아닌 번호를 포함 하는 비디오 게이트웨이에서의 영상 SIP 트렁크 전화의 경우, 연결 된 트렁크와 연결 된 다이얼 플랜의 이름을 읽고 해당 하는 경우 요청 URI의 휴대폰 컨텍스트 부분에 다이얼 플랜 이름을 포함 합니다. 님이 프론트 엔드에 전송 합니다. 그러면 프런트 엔드에서 번역 응용 프로그램이 다이얼 플랜에 연결 된 정규화 규칙을 추출 하 여 요청 URI에 적용 합니다.
## <a name="trunk-configuration-options"></a>트렁크 구성 옵션

앞에서 설명한 비디오 트렁크 용 Windows PowerShell cmdlet은 이전에 비즈니스용 Skype 서버 2015에서 새롭게 발표 되었습니다. 영상 트렁크 구성과 관련 된 설정에 대 한 간략 한 설명이 필요 합니다.
  
 **GatewaySendsRtcpForActiveCalls** 이 매개 변수는 활성 통화에 대 한 RTCP 패킷을 VTC에서 VIS로 보낼지 여부를 결정 합니다. 여기서 활성 통화란 미디어가 하나 이상의 방향으로 흐르도록 허용되는 통화를 의미합니다. GatewaySendsRtcpForActiveCalls가 True로 설정 된 경우 30 초를 초과 하는 기간 동안 RTCP 패킷을 받지 못하면 VIS에서 통화를 종료할 수 있습니다. 기본값은 **True**입니다.
  
 **GatewaySendsRtcpForCallsOnHold** 이 매개 변수는 대기 중인 통화에 대해 RTCP 패킷을 계속 보낼지 여부를 결정 하 고 어느 방향으로도 이동할 수 있는 미디어 패킷이 없습니다. 통화가 대기 중인 동안 VTC에서 RTCP packets가 VIS 되지 않는 경우 VIS에서 통화를 종료할 수 있습니다. 기본값은 **True**입니다. SIPTransport 프로토콜이 TCP로 설정 되 면이 설정은 무시 됩니다.
  
 **EnableMediaEncryptionForSipOverTls** 이 매개 변수는 SIPTransport 프로토콜이 TLS로 설정 된 경우 미디어 SRTP를 사용 하거나 사용 하지 않도록 합니다. 기본값은 **True**입니다. SIPTransport 프로토콜이 TCP로 설정 되 면이 설정은 무시 됩니다.
  
 **Enablesessiontimer** 이 매개 변수는 비디오 SIP 트렁크에 연결 된 각 SIP 대화 상자의 VIS 측면에서 세션 타이머를 사용 하거나 사용 하지 않도록 설정 합니다. 기본값은 **False**입니다.
  
 **ForwardErrorCorrectionType** 이 매개 변수는 비디오 스트림에 대 한 FEC (정방향 오류 수정)가 비디오 Interop 서버와 비디오 게이트웨이 간의 레그에 적용 되는지 여부를 결정 하는 데 사용 됩니다. ForwardErrorCorrectionType를 "없음"으로 설정 하는 것은 VIS와 비디오 게이트웨이/r e t e r t e r t e t/ ForwardErrorCorrectionType를 "Cisco"로 설정 하면 cisco의 비디오 게이트웨이와 FEC 호환 됩니다 (예: Cisco 통합 커뮤니케이션 관리자 (CUCM)). 기본값은 **없음**입니다.
  
## <a name="see-also"></a>참고 항목

[비즈니스용 Skype 서버와 상호 운용할 CUCM 구성](configure-cucm-for-interoperation.md)
