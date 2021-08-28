---
title: 비디오 Interop 서버에서 비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0fde142b-70b1-46c6-b1f9-f9d70115371d
description: '요약: 2016에서 VIS(Video Interop Server) 역할을 비즈니스용 Skype 서버.'
ms.openlocfilehash: cebfb35f740a0060a22bd125ccc2448c0092e87c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58595982"
---
# <a name="configure-the-video-interop-server-in-skype-for-business-server"></a>비디오 Interop 서버에서 비즈니스용 Skype 서버
 
**요약:** VIS(Video Interop Server) 역할을 구성하여 비즈니스용 Skype 서버.
  
 VIS에서 비디오 트렁크를 사용하여 비디오 트렁크와 연결되는 설정을 Windows PowerShell. VIS 서비스가 설치되면 전역 범위가 있는 비디오 트렁크 구성이 만들어집니다. 이 비디오 트렁크 구성은 VIS에서 보다 구체적인 범위의 비디오 트렁크 구성이 없는 모든 트렁크에 적용됩니다. 비디오 트렁크 구성은 비디오 트렁크에 적용할 수 있는 설정 모음입니다.
  
## <a name="configure-video-trunk-and-dial-plan"></a>비디오 트렁크 및 다이얼 플랜 구성

다음 Windows PowerShell 명령을 사용하여 VIS와 모든 비디오 게이트웨이 간에 토폴로지 문서에 정의된 새로 정의된 트렁크와 연결될 비디오 트렁크 구성 및 다이얼 플랜을 지정합니다. 이러한 모든 설정은 전역, 사이트 또는 서비스(비디오 게이트웨이) 수준에서 설정할 수 있습니다. 
  
전역 범위가 있는 다이얼 플랜은 배포당 비즈니스용 Skype 서버 생성됩니다. 이 다이얼 플랜은 VIS에서 더 구체적인 범위의 다이얼 플랜이 없는 모든 트렁크에 적용됩니다. 
  
### <a name="configure-the-vis-using-windows-powershell"></a>VIS를 사용하여 Windows PowerShell

1. 다음 cmdlet을 사용하여 VIS와 Cisco Unified Communications Manager(CallManager 또는 CUCM) 간의 트렁크에 사용할 새 비디오 트렁크 구성(설정 컬렉션)을 Windows PowerShell.
    
   ```powershell
   New-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls $true(or $false)
   ```

    수정해야 하는 기존 비디오 트렁크가 있는 경우 다음 cmdlet을 Windows PowerShell 합니다.
    
   ```powershell
   Set-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -GatewaySendsRtcpForActiveCalls $false -GatewaySendsRtcpForCallsOnHold $false -EnableMediaEncryptionForSipOverTls  $true(or $false)
   ```

    특정 비디오 트렁크 구성과 연결된 설정을 확인하려면 다음 Windows PowerShell 사용합니다.
    
   ```powershell
   Get-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

    특정 비디오 트렁크 구성을 제거하려면 다음 Windows PowerShell cmdlet을 사용하십시오(특정 트렁크에 대해 더 구체적으로 범위가 지정되는 비디오 트렁크 구성이 없는 경우 전역 범위 비디오 트렁크 구성이 적용됩니다).
    
   ```powershell
   Remove-CsVideoTrunkConfiguration -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com"
   ```

2. 다음 cmdlet을 사용하여 트렁크와 연결하기 위한 다이얼 Windows PowerShell 수립합니다.
    
   ```powershell
   New-CsDialPlan -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com" -SimpleName "TrunkTestDialPlan" 
   New-CsVoiceNormalizationRule -Identity "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/SevenDigitRule" -Pattern '^(\d{7})$' -Translation '+1425$1' 
   Get-CsDialPlan -Identity "Service:CUCMVIS1.CUCMInterop.contoso.com"
   Remove-CsVoiceNormalizationRule -Identity  "Service:VideoGateway:CUCMVIS1.CUCMInterop.contoso.com/Keep All"
   ```

**Remove-CsVoiceNormalizationRule** 명령은 예상된 VIS 및 CUCM 조작을 방해하는 기본 규칙을 다시 설정하는 데 필요합니다.
> [!NOTE]
> [Remove-CsDialPlan을](/powershell/module/skype/remove-csdialplan?view=skype-ps) 사용하여 다이얼 플랜을 제거할 수 있습니다.
  
해당 요청 URI에 E.164 번호가 아닌 번호가 포함된 비디오 게이트웨이의 비디오 SIP 트렁크 통화의 경우 VIS는 연결된 트렁크와 연결된 다이얼 플랜의 이름을 읽고 VIS가 프런트 엔드로 보내는 초대의 요청 URI의 전화 컨텍스트 부분에 다이얼 플랜 이름을 포함합니다. 그러면 프런트 엔드의 번역 응용 프로그램이 다이얼 플랜과 연결된 정규화 규칙을 추출하여 요청 URI에 적용합니다.
## <a name="trunk-configuration-options"></a>트렁크 구성 옵션

이전에 Windows PowerShell 트렁크 구성에 대한 비즈니스용 Skype 서버 cmdlet이 추가되었습니다. 비디오 트렁크 구성과 연결된 설정에 대한 간략한 설명이 필요합니다.
  
 **GatewaySendsRtcpForActiveCalls** 이 매개 변수는 활성 통화를 위해 VTC에서 VIS로 RTCP 패킷을 보낼지 여부를 지정합니다. 여기서 활성 통화란 미디어가 하나 이상의 방향으로 흐르도록 허용되는 통화를 의미합니다. GatewaySendsRtcpForActiveCalls를 True로 설정하면 VIS에서 30초를 초과하는 기간 동안 RTCP 패킷을 받지 못하면 통화를 종료할 수 있습니다. 기본값은 **True** 입니다.
  
 **GatewaySendsRtcpForCallsOnHold** 이 매개 변수는 보류된 통화에 대해 트렁크를 통해 RTCP 패킷을 계속 전송할지 여부를 결정하며 미디어 패킷이 어느 방향으로도 흐르지 않습니다. 통화가 보류 중일 때 VTC에서 VIS로 흐르는 RTCP 패킷이 없는 경우 VIS에서 통화를 종료할 수 있습니다. 기본값은 **True** 입니다. SIPTransport 프로토콜이 TCP로 설정되어 있는 경우 이 설정은 무시됩니다.
  
 **EnableMediaEncryptionForSipOverTls** 이 매개 변수는 SIPTransport 프로토콜이 TLS로 설정된 경우 미디어에 대해 SRTP를 활성화 또는 비활성화합니다. 기본값은 **True** 입니다. SIPTransport 프로토콜이 TCP로 설정되어 있는 경우 이 설정은 무시됩니다.
  
 **EnableSessionTimer** 이 매개 변수는 비디오 SIP 트렁크와 연결된 각 SIP 대화 상자에 대해 VIS 쪽 세션 Timers를 활성화하거나 사용하지 않도록 설정합니다. 기본값은 **False** 입니다.
  
 **ForwardErrorCorrectionType** 이 매개 변수는 비디오 스트림에 대한 FEC(정방 오류 수정)를 비디오 Interop 서버와 비디오 게이트웨이 사이의 다리에 적용할지 여부를 확인하는 데 사용됩니다. ForwardErrorCorrectionType을 "None"으로 설정하면 VIS와 비디오 게이트웨이/VTC 간에 FEC가 해제됩니다. ForwardErrorCorrectionType을 "Cisco"로 설정하면 FEC가 Cisco CUCM(Unified Communications Manager)과 같은 Cisco의 비디오 게이트웨이와 호환될 수 있습니다. 기본값은 **None입니다.**
  
## <a name="see-also"></a>참고 항목

[사용자와의 상호 연결에 대해 CUCM 비즈니스용 Skype 서버](configure-cucm-for-interoperation.md)