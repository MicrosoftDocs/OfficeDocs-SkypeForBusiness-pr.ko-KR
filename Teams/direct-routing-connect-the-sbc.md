---
title: 직접 라우팅에 SBC (세션 경계 컨트롤러) 연결
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Microsoft 전화 시스템 다이렉트 라우팅을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e86b0397e4c00b892d99a0814579f20ba14e8b59
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157998"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>직접 라우팅에 SBC (세션 경계 컨트롤러) 연결 

이 문서에서는 SBC (세션 경계 컨트롤러)를 전화 시스템 다이렉트 라우팅에 연결 하는 방법을 설명 합니다.  직접 라우팅 구성에 대 한 단계 1 단계는 다음과 같습니다.

- **1 단계. 전화 시스템을 사용 하 여 SBC 연결 및 연결 확인** (이 문서)
- 2 단계. [사용자가 직접 라우팅 하도록 설정](direct-routing-enable-users.md)
- 3 단계. [통화 라우팅 구성](direct-routing-voice-routing.md)
- 4 단계. [숫자를 대체 형식으로 번역](direct-routing-translate-numbers.md) 

직접 라우팅을 설정 하는 데 필요한 모든 단계에 대 한 자세한 내용은 [직접 라우팅 구성을](direct-routing-configure.md)참조 하세요.

SBC를 직접 라우팅에 연결 하려면 다음을 수행 해야 합니다. 

1. PowerShell을 사용 하 여 **비즈니스용 Skype Online** 관리 센터에 연결 합니다.            
2. 테 넌 트에 SBC를 연결 합니다.
3. 연결의 유효성을 검사 합니다. 

## <a name="connect-to-skype-for-business-online-by-using-powershell"></a>PowerShell을 사용 하 여 비즈니스용 Skype Online에 연결 

테 넌 트에 연결 된 PowerShell 세션을 사용 하 여 SBC를 직접 라우팅 인터페이스에 쌍으로 연결할 수 있습니다. PowerShell 세션을 열려면 [Windows powershell 용 컴퓨터 설정](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)에서 설명 하는 단계를 따릅니다. 
 
원격 PowerShell 세션을 설정한 후 SBC를 관리 하는 명령을 볼 수 있는지 확인 합니다. 명령에 대 한 유효성을 검사 하려면 PowerShell 세션에 다음 명령을 입력 하거나 복사 하 여 붙여 넣은 다음 enter 키를 누릅니다. 

```PowerShell
Get-Command *onlinePSTNGateway*
```

이 명령은 SBC를 관리할 수 있도록 여기에 나와 있는 네 개의 함수를 반환 합니다. 

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>   


## <a name="connect-the-sbc-to-the-tenant"></a>테 넌 트에 SBC 연결 

테 넌 트에 SBC를 연결 하려면 PowerShell 세션에서 다음을 입력 하 고 enter 키를 누릅니다. 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. SBC 설명서에 나와 있는 정보를 사용 하 여 SBC에서 최대 통화 제한을 설정 하는 것이 좋습니다. 이 제한은 SBC이 용량 수준에 있는 경우 알림을 트리거합니다.
  > 2. FQDN의 도메인 부분이 onmicrosoft.com를 제외 \*하 고 테 넌 트에서 등록 된 도메인 중 하 나와 일치 하는 경우에만 SBC를 쌍으로 연결할 수 있습니다. Onmicrosoft.com \*도메인 이름을 사용 하는 것은 SBC FQDN 이름에 대해 지원 되지 않습니다. 예를 들어 도메인 이름이 두 개 있는 경우:<br/><br/>
  > **contoso**. c a m<br/>**contoso**. onmicrosoft.com<br/><br/>
  > SBC 이름에는 이름 sbc.contoso.com를 사용할 수 있습니다. Sbc와 이름 sbc를 쌍으로 연결 하려고 하면이 테 넌 트가 도메인을 소유 하지 않으므로 시스템에서 사용자를 허용 하지 않습니다.<br/>
  > 테 넌 트에 등록 된 도메인 외에도 해당 도메인 및 할당 된 E3 또는 E5 라이선스를 가진 사용자가 있어야 합니다. 그렇지 않으면 다음 오류가 표시 됩니다.<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```
구합니다
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
연결 프로세스 중에 설정할 수 있는 추가 옵션이 있습니다. 그러나 앞의 예제에서는 필요한 최소 매개 변수만 표시 합니다. 
 
다음 표에는 매개 변수를 ```New-CsOnlinePstnGateway```설정 하는 데 사용할 수 있는 추가 매개 변수가 나와 있습니다.

|필수?|이름|설명|기본값|사용할 수 있는 값|유형 및 제한 사항|
|:-----|:-----|:-----|:-----|:-----|:-----|
|예|Q|SBC의 FQDN 이름입니다. |없음|비 Efqdn 이름, 63 문자 제한|[Active Directory에서 컴퓨터, 도메인, 사이트 및 ou에 대 한 명명 규칙](https://support.microsoft.com/help/909264) 의 허용 및 허용 되지 않는 문자 목록 문자열|
|아니요|MediaBypass |SBC로 표시 된 매개 변수는 미디어 바이패스를 지원 하 고 관리자가이를 사용 하려고 합니다.|없음|False<br/>해제|부울|
|예|SipSignalingPort |TLS (전송 계층 보안) 프로토콜을 사용 하 여 직접 라우팅 서비스와 통신 하는 데 사용 되는 수신 대기 포트입니다.|없음|모든 포트|0 ~ 65535 |
|아니요|FailoverTimeSeconds |10으로 설정 된 경우 (기본값), 게이트웨이에서 응답 하지 않은 아웃 바운드 호출은 10 초 이내에 사용 가능한 다음 트렁크로 라우팅됩니다. 추가 trunks 없으면 통화가 자동으로 삭제 됩니다. 느린 네트워크 및 게이트웨이 응답을 사용 하는 조직에서 호출이 불필요 하 게 손실 될 수 있습니다. 기본값은 10입니다.|1천만|숫자로|Int|
|아니요|ForwardCallHistory |트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다. 이 기능을 사용 하도록 설정 하면 Office 365 PSTN 프록시가 두 가지 헤더 인 기록 정보 및 참조 하는 사람을 보냅니다. 기본값은 **False** ($False)입니다. |해제|False<br/>해제|부울|
|아니요|ForwardPAI|PAI(P-Asserted-Identity) 헤더를 통화와 함께 전달할지 여부를 나타냅니다. PAI 헤더를 사용하면 발신자 번호를 확인할 수 있습니다. 사용 하도록 설정한 경우 개인 정보 취급 방침: ID 헤더만 전송 됩니다. 기본값은 **False** ($False)입니다.|해제|False<br/>해제|부울|
|아니요|SendSIPOptions |SBC가 SIP 옵션을 보내지 않을 지 여부를 정의 합니다. 이 기능을 사용 하지 않도록 설정 하면 SBC이 모니터링 및 경고 시스템에서 제외 됩니다. SIP 옵션을 사용 하도록 설정 하는 것이 좋습니다. 기본값은 **True**입니다. |False|False<br/>해제|부울|
|아니요|MaxConcurrentSessions |경고 시스템에서 사용 합니다. 값이 설정 되 면 경고 시스템에서는 동시 세션 수가이 값 보다 90% 이상일 때 테 넌 트 관리자에 게 알림을 생성 합니다. 매개 변수가 설정 되지 않은 경우에는 경고가 생성 되지 않습니다. 그러나 모니터링 시스템에서는 24 시간 마다 동시 세션의 수를 보고 합니다. |L|L<br/>1 ~ 10만 ||
|아니요|MediaRelayRoutingLocationOverride |수동으로 미디어 경로를 선택할 수 있습니다. 직접 라우팅은 미디어 경로에 대 한 데이터 센터에 SBC의 공용 IP를 기반으로 할당 합니다. 항상 SBC 데이터 센터에 가장 가까운 위치를 선택 합니다. 그러나 일부 경우에는 미국 범위를 유럽에 위치한 SBC에 할당할 수 있습니다. 이 경우 최적화 되지 않은 미디어 경로를 사용 하 게 됩니다. 이 매개 변수를 사용 하면 미디어 트래픽에 대 한 기본 설정 영역을 수동으로 설정할 수 있습니다. Microsoft는 미디어 경로에 대 한 데이터 센터의 자동 할당이 SBC 데이터 센터에 가장 가까운 것을 할당 하지 않는다는 것을 호출 로그가 명확 하 게 표시 하는 경우에만이 매개 변수 설정을 권장 합니다. |없음|ISO 형식의 국가 코드||
|아니요|수|이 SBC를 발신 전화에 사용 하도록 설정 합니다. 업데이트 중이거나 유지 관리 하는 동안 SBC를 일시적으로 제거 하는 데 사용할 수 있습니다. |해제|False<br/>해제|부울|
 
## <a name="verify-the-sbc-connection"></a>SBC 연결 확인 

연결을 확인 하려면 다음을 수행 합니다. 
- SBC가 쌍의 SBCs 목록에 있는지 확인 합니다. 
- SIP 옵션의 유효성을 검사 합니다. 
 
### <a name="check-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>SBC가 쌍의 SBCs 목록에 있는지 확인 합니다. 

SBC에 연결한 후 원격 PowerShell 세션에서 다음 명령을 실행 하 여 해당 SBC가 쌍을 이루는 SBCs 목록에 있는지 확인 합니다. 

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

쌍으로 연결 된 게이트웨이는 아래 예제에 표시 된 대로 목록에 표시 되어야 하 고, **Enabled** 매개 변수는 **True**값을 표시 해야 합니다. 


반환 되는 결과:
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignalingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

### <a name="validate-sip-options-flow"></a>SIP 옵션 흐름의 유효성 검사 

나가는 SIP 옵션을 사용 하 여 페어링의 유효성을 검사 하려면 SBC 관리 인터페이스를 사용 하 고 SBC가 보내는 옵션 메시지에 대 한 200 OK 응답을 수신 하는지 확인 합니다.

직접적인 라우팅이 수신 옵션을 인식 하는 경우 수신 옵션 메시지의 대화 상대 헤더 필드에 구성 된 SBC FQDN으로 보내는 SIP 옵션 메시지를 전송 하기 시작 합니다. 

들어오는 SIP 옵션을 사용 하 여 페어링의 유효성을 검사 하려면 SBC 관리 인터페이스를 사용 하 여 SBC가 직접 라우팅에서 들어오는 옵션 메시지에 대 한 응답을 보내고, 전송 하는 응답 코드는 200 OK를 참조 합니다.


## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)
