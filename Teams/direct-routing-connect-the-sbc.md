---
title: SBC(세션 테두리 컨트롤러)를 직접 라우팅에 연결
ms.reviewer: fillipse
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: SBC를 구성하고 Teams Phone 시스템 직접 라우팅에 연결하는 방법을 알아봅니다.
ms.openlocfilehash: e33f9538fdf69696e0a87da84dc5aec8e8d304af
ms.sourcegitcommit: f2253162a23d0683e7424211da1a0a8760c8a91b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2022
ms.locfileid: "66241107"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>SBC(세션 테두리 컨트롤러)를 직접 라우팅에 연결

이 문서에서는 SBC(세션 테두리 컨트롤러)를 구성하고 직접 라우팅에 연결하는 방법을 설명합니다.  직접 라우팅을 구성하는 다음 단계 중 1단계입니다.

- **1단계. SBC를 전화 시스템에 연결하고 연결의 유효성을 검사** 합니다(이 문서).
- 2단계. [직접 라우팅에 대한 사용자 사용](direct-routing-enable-users.md)
- 3단계. [통화 라우팅 구성](direct-routing-voice-routing.md)
- 4단계. [숫자를 대체 형식으로 변환](direct-routing-translate-numbers.md)

직접 라우팅을 설정하는 데 필요한 모든 단계에 대한 자세한 내용은 [직접 라우팅 구성을 참조하세요](direct-routing-configure.md).

[Microsoft Teams 관리 센터](#using-the-microsoft-teams-admin-center) 또는 [PowerShell](#using-powershell)을 사용하여 SBC를 구성하고 직접 라우팅에 연결할 수 있습니다.

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 영역에서 **음성** > **직접 라우팅** 으로 이동한 다음 **SCC** 탭을 클릭합니다.

2. **추가** 를 클릭합니다.

3. SBC에 대한 FQDN을 입력합니다. <br><br>FQDN의 도메인 이름 부분이 테넌트에 등록된 도메인과 일치하는지 확인하고 도메인 이름이 SBC FQDN 도메인 이름에 대해 지원되지 않는다는 점을 `*.onmicrosoft.com` 명심하세요. 예를 들어 도메인 이름이 `contoso.com` 두 개 있는 `contoso.onmicrosoft.com`경우 SBC 이름으로 사용합니다 `sbc.contoso.com` . 하위 도메인을 사용하는 경우 이 하위 도메인도 테넌트에 등록되어 있는지 확인합니다. 예를 들어 사용 `sbc.service.contoso.com``service.contoso.com` 하려는 경우 등록해야 합니다.

4. 조직의 요구 사항에 따라 SBC에 대해 다음 설정을 구성합니다. 이러한 각 설정에 대한 자세한 내용은 [SBC 설정을 참조하세요](#sbc-settings).

    ![Microsoft Teams 관리 센터의 SBC 추가 페이지 스크린샷](media/direct-routing-add-sbc.png)

5. 모두 마쳤으면 **저장** 을 클릭합니다.

## <a name="using-powershell"></a>PowerShell 사용

SBC를 직접 라우팅에 연결하려면 다음을 수행해야 합니다.

1. [PowerShell을 사용하여 비즈니스용 Skype Online에 연결](#connect-to-skype-for-business-online-by-using-powershell)합니다.

2. [테넌트에 SBC를 연결합니다](#connect-the-sbc-to-the-tenant).

3. [SBC 연결을 확인](#verify-the-sbc-connection)합니다.

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>PowerShell을 사용하여 비즈니스용 Skype Online에 연결

SBC를 직접 라우팅 인터페이스에 페어링하려면 테넌트에 연결된 PowerShell 세션을 사용합니다. PowerShell 세션을 열려면 [Windows PowerShell 컴퓨터 설정](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)에 설명된 단계를 수행합니다.
 
원격 PowerShell 세션을 설정한 후 SBC를 관리하는 명령을 볼 수 있는지 확인합니다. 명령을 확인하려면 PowerShell 세션에서 다음 명령을 입력하거나 복사하여 붙여넣은 다음 Enter 키를 누릅니다. 

```PowerShell
Get-Command *onlinePSTNGateway*
```

이 명령은 SBC를 관리할 수 있는 4개의 함수를 반환합니다.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>테넌트에 SBC 연결

SBC를 테넌트에 연결하려면 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용합니다. PowerShell 세션에서 다음을 입력한 다음 Enter 키를 누릅니다.

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. SBC 설명서에서 찾을 수 있는 정보를 사용하여 SBC에서 최대 통화 제한을 설정하는 것이 좋습니다. 제한은 SBC가 용량 수준에 있는 경우 알림을 트리거합니다.
  > 2. FQDN의 도메인 부분이 .onmicrosoft.com 제외하고 \*테넌트에 등록된 도메인 중 하나와 일치하는 경우에만 SBC를 연결할 수 있습니다. SBC FQDN 이름에는 .onmicrosoft.com 도메인 이름을 사용할 \*수 없습니다. 예를 들어 **contoso.com과 contoso.onmicrosoft.com** 두 개의 도메인 이름이 있는 경우 SBC 이름에 sbc.contoso.com 사용할 수 있습니다. sbc.contoso.abc와 같은 이름으로 SBC를 연결하려고 하면 도메인이 이 테넌트가 소유하지 않으므로 시스템에서 허용하지 않습니다.<br/>
  > 테넌트에 등록된 도메인 외에도 해당 도메인을 가진 사용자와 할당된 E3 또는 E5 라이선스가 있어야 합니다. 그렇지 않으면 다음 오류가 표시됩니다.<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.
  > 3. SBC 쪽에서 동일한 FQDN으로 매핑된 여러 IP는 지원되지 않습니다.

예제는 다음과 같습니다.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

다음을 반환합니다.

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

> [!NOTE]
> 이 예제에서는 필요한 최소 매개 변수만 보여줍니다. 연결 프로세스 중에 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용하여 설정할 수 있는 추가 매개 변수가 있습니다. 자세한 내용은 [SBC 설정을 참조하세요](#sbc-settings).
 
### <a name="verify-the-sbc-connection"></a>SBC 연결 확인

연결을 확인하려면 다음을 수행합니다.

- [SBC가 쌍을 이루는 SBC 목록에 있는지 확인합니다](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs).
- [SIP 옵션의 유효성을 검사합니다](#validate-sip-options).
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>SBC가 쌍을 이루는 SBC 목록에 있는지 확인합니다.

SBC를 연결한 후 [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) cmdlet을 사용하여 SBC가 쌍을 이루는 SBC 목록에 있는지 확인합니다. 원격 PowerShell 세션에서 다음을 입력한 다음 Enter 키를 누릅니다.

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

쌍을 이루는 게이트웨이는 아래 예제와 같이 목록에 표시되어야 하며 **Enabled** 매개 변수는 **True** 값을 표시해야 합니다.

다음을 반환합니다.

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

#### <a name="validate-sip-options"></a>SIP 옵션 유효성 검사

나가는 SIP 옵션을 사용하여 페어링의 유효성을 검사하려면 SBC 관리 인터페이스를 사용하고 SBC가 나가는 OPTIONS 메시지에 대해 200 OK 응답을 받는지 확인합니다.

직접 라우팅에 들어오는 옵션이 표시되면 들어오는 OPTIONS 메시지의 연락처 헤더 필드에 구성된 SBC FQDN으로 나가는 SIP 옵션 메시지를 보내기 시작합니다. 

들어오는 SIP 옵션을 사용하여 페어링의 유효성을 검사하려면 SBC 관리 인터페이스를 사용하고 SBC가 직접 라우팅에서 들어오는 OPTIONS 메시지에 회신을 보내고 보내는 응답 코드가 200 OK인지 확인합니다.

## <a name="sbc-settings"></a>SBC 설정

이 표에는 Microsoft Teams 관리 센터 및 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용하여 SBC에 대해 설정할 수 있는 옵션이 나열되어 있습니다.

|필수?|Teams 관리 센터 설정|PowerShell 매개 변수|설명|기본|가능한 값|형식 및 제한 사항|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|예|**SBC에 대한 FQDN 추가**|FQDN |없음|FQDN 이름, 63자 제한|문자열, [컴퓨터, 도메인, 사이트 및 OU에 대한 Active Directory의 명명 규칙에 허용되는 문자 및](https://support.microsoft.com/help/909264) 허용되지 않는 문자 목록을 참조하세요.|
|아니요|**사용**|사용|아웃바운드 호출에 대해 SBC를 켜는 데 사용합니다. SBC가 업데이트되는 동안 또는 유지 관리 중에 서비스에서 SBC를 일시적으로 제거하는 데 사용할 수 있습니다. |False|사실<br/>False|부울|
|예|**SIP 신호 포트**|SipSignalingPort |TLS(전송 계층) 프로토콜을 사용하여 직접 라우팅과 통신하는 데 사용되는 수신 대기 포트입니다.|없음|모든 포트|0에서 65535까지 |
|아니요|**SIP 옵션 보내기**|SendSIPOptions |SBC에서 SIP 옵션 메시지를 보낼지 여부를 정의합니다. 이 설정을 켜는 것이 좋습니다. 이 설정이 꺼져 있으면 SBC는 모니터링 및 경고 시스템에서 제외됩니다.|사실|사실<br/>False|부울|
|아니요|**착신 전환 기록**|ForwardCallHistory |통화 기록 정보가 트렁크를 통해 전달되는지 여부를 나타냅니다. 이 기능을 켜면 Microsoft 365 프록시가 기록 정보 및 참조 헤더를 보냅니다. |False|사실<br/>False|부울|
|아니요|**P-Asserted-identity(PAI) 헤더 전달**|ForwardPAI|호출과 함께 PAI 헤더가 전달되는지 여부를 나타냅니다. PAI 헤더를 사용하면 발신자 번호를 확인할 수 있습니다. 이 설정이 설정되면 Privacy:ID 헤더도 전송됩니다.|False|사실<br/>False|부울|
|아니요|**동시 호출 용량**|MaxConcurrentSessions |값을 설정하면 동시 세션 수가 이 값보다 90% 이상일 때 경고 시스템이 사용자에게 알립니다. 값을 설정하지 않으면 경고가 생성되지 않습니다. 그러나 모니터링 시스템은 24시간마다 동시 세션 수를 보고합니다. |Null|Null<br/>1에서 100,000까지 ||
|아니요|**장애 조치(failover) 응답 코드**|FailoverResponseCodes<br>|직접 라우팅이 나가는 초대에 대한 응답으로 4xx 또는 6xx SIP 오류 코드를 수신하는 경우 호출은 기본적으로 완료된 것으로 간주됩니다. 나가는 것은 트래픽 흐름이 있는 Teams 클라이언트에서 PSTN으로의 호출을 의미합니다. Teams 클라이언트 -> 직접 라우팅 -> SBC -> 전화 통신 네트워크). 장애 조치(failover) 응답 코드를 지정하면 네트워크 또는 기타 문제로 인해 SBC가 전화를 걸 수 없는 경우 지정된 코드를 받을 때 직접 라우팅이 다른 SBC(사용자의 음성 라우팅 정책에 있는 경우)를 강제로 시도합니다. 자세한 내용은 [SBC(세션 테두리 컨트롤러)에서 받은 특정 SIP 코드의 장애 조치(failover)](direct-routing-trunk-failover-on-outbound-call.md)를 참조하세요.|408, 503, 504||Int|
|아니요|**장애 조치(failover) 시간(초)**|FailoverTimeSeconds |값을 설정하면 설정한 시간 내에 게이트웨이에서 응답하지 않는 아웃바운드 호출이 사용 가능한 다음 트렁크로 라우팅됩니다. 추가 트렁크가 없으면 호출이 자동으로 삭제됩니다. 기본값은 10초입니다. 네트워크 및 게이트웨이 응답이 느린 조직에서는 이로 인해 호출이 불필요하게 삭제될 수 있습니다.|10|수|Int|
|아니요|**미디어 트래픽에 대한 기본 국가 또는 지역**|MediaRelayRoutingLocationOverride | 직접 라우팅에 적용되지 않습니다. 이 매개 변수는 통화 플랜에서 관리되는 이동 통신 사업자와 함께 사용하도록 예약되어 있습니다. |없음|||
|아니요|**SBC는 긴급 통화에 대한 PIDF/LO를 지원합니다.**|PidfloSupported|SBC에서 긴급 통화에 대해 현재 상태 정보 PIDF/LO(데이터 형식 위치 개체)를 지원하는지 여부를 지정합니다.||||
|아니요| - |MediaBypass|이 설정은 SBC에서 미디어 바이패스를 지원하는지 여부와 이 SBC에 사용할지 여부를 나타냅니다. |없음|사실<br/>False|부울|

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)

[Teams PowerShell 개요](teams-powershell-overview.md)
