---
title: 커넥트 SBC(세션 테두리 컨트롤러)를 직접 라우팅에 연결
ms.reviewer: ''
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
description: SBC를 구성하고 연결하여 직접 라우팅을 전화 시스템 방법을 배워야 합니다.
ms.openlocfilehash: d18ff8a8f0c398979a2c04d3aca1ff69b8bdc8f1
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726127"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>커넥트 SBC(세션 테두리 컨트롤러)를 직접 라우팅에 연결

이 문서에서는 SBC(세션 테두리 컨트롤러)를 구성하고 직접 라우팅에 전화 시스템 방법을 설명합니다.  직접 라우팅을 구성하는 다음 단계의 1단계입니다.

- **1단계. 커넥트 SBC를 전화 시스템** 연결의 유효성을 검사합니다(이 문서)
- 2단계. [직접 라우팅에 대한 사용자 사용](direct-routing-enable-users.md)
- 3단계. [호출 라우팅 구성](direct-routing-voice-routing.md)
- 4단계. [숫자를 대체 형식으로 변환](direct-routing-translate-numbers.md)

직접 라우팅을 설정하는 데 필요한 모든 단계에 대한 자세한 내용은 직접 라우팅 [구성 을 참조하세요.](direct-routing-configure.md)

관리자 센터 또는 [Microsoft Teams](#using-the-microsoft-teams-admin-center) [PowerShell을](#using-powershell) 사용하여 SBC를 구성하고 직접 라우팅에 연결할 수 있습니다.

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색에서 Voice   >  **Direct 라우팅으로** 이동한 다음 **SBC 탭을 클릭합니다.**
2. **추가** 를 클릭합니다.
3. SBC에 대한 FQDN을 입력합니다. <br><br>FQDN의 도메인 이름 부분이 테넌트에 등록된 도메인과 일치하는지 확인하고 도메인 이름이 SBC FQDN 도메인 이름에 지원되지 `*.onmicrosoft.com` 않습니다. 예를 들어 도메인 이름이 2개인 경우 `contoso.com` `contoso.onmicrosoft.com` 를 `sbc.contoso.com` SBC 이름으로 사용할 수 있습니다. 하위 종을 사용하는 경우 이 하위 토마인도 테넌트에 등록되어 있는지 확인 합니다. 예를 들어 를 사용하려는 경우 `sbc.service.contoso.com` `service.contoso.com` 등록해야 합니다.
4. 조직의 요구에 따라 SBC에 대한 다음 설정을 구성합니다. 이러한 각 설정에 대한 자세한 내용은 SBC 설정 [을 참조하세요.](#sbc-settings)

    ![관리 센터의 SBC Microsoft Teams 스크린샷.](media/direct-routing-add-sbc.png)

5. 모두 마쳤으면 **저장** 을 클릭합니다.

## <a name="using-powershell"></a>PowerShell 사용

SBC를 직접 라우팅에 연결하려면 다음이 필요합니다.

1. [PowerShell을 사용하여 커넥트 비즈니스용 Skype 온라인을 사용할 수 있습니다.](#connect-to-skype-for-business-online-by-using-powershell)
2. [커넥트 SBC를 테넌트에](#connect-the-sbc-to-the-tenant)
3. [SBC 연결 을 확인합니다.](#verify-the-sbc-connection)

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>커넥트 PowerShell을 사용하여 비즈니스용 Skype 온라인을 사용할 수 있습니다.

테넌트에 연결된 PowerShell 세션을 사용하여 직접 라우팅 인터페이스에 SBC를 페어링할 수 있습니다. PowerShell 세션을 열기 위해 컴퓨터 설정 에 설명된 단계를 [Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
원격 PowerShell 세션을 설정한 후 SBC를 관리하는 명령을 볼 수 있는지 확인해야 합니다. 명령을 확인하기 위해 PowerShell 세션에서 다음 명령을 입력하거나 복사하여 붙여넣은 다음 Enter를 누를 수 있습니다. 

```PowerShell
Get-Command *onlinePSTNGateway*
```

명령은 여기에 표시된 4개의 함수를 반환하여 SBC를 관리할 수 있습니다.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>커넥트 SBC를 테넌트에

[New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용하여 SBC를 테넌트에 연결합니다. PowerShell 세션에서 다음을 입력한 다음 Enter를 누를 수 있습니다.

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. SBC 설명서에서 찾을 수 있는 정보를 사용하여 SBC에서 최대 호출 제한을 설정하는 것이 좋습니다. 제한은 SBC가 용량 수준에 있는 경우 알림을 트리거합니다.
  > 2. FQDN의 도메인 부분이 .onmicrosoft.com 제외한 테넌트에 등록된 도메인 중 하나와 일치하는 경우 SBC를 \* 연결할 수 onmicrosoft.com. .onmicrosoft.com 도메인 이름을 \* 사용하는 것은 SBC FQDN 이름에 지원되지 않습니다. 예를 들어 **contoso**.com 및 **contoso**.onmicrosoft.com 두 개의 도메인 이름이 있는 경우 SBC sbc.contoso.com 사용할 수 있습니다. sbc.contoso.abc와 같은 이름으로 SBC를 연결하려고 하는 경우 도메인이 이 테넌트에 의해 소유되지 않습니다.<br/>
  > 테넌트에 등록된 도메인 외에도 해당 도메인과 할당된 E3 또는 E5 라이선스가 있는 사용자가 있는 것이 중요합니다. 그렇지 않은 경우 다음 오류가 표시됩니다.<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

다음은 예제입니다.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

반환되는:

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
> 이 예제에서는 필요한 최소 매개 변수만 보여줍니다. 연결 프로세스 중에 [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용하여 설정할 수 있는 추가 매개 변수가 있습니다. 자세한 내용은 SBC 설정을 [참조하세요.](#sbc-settings)
 
### <a name="verify-the-sbc-connection"></a>SBC 연결 확인

연결을 확인:

- [SBC가](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)페어링된 SBC 목록에 있는지 여부를 검사합니다.
- [SIP 옵션의 유효성을 검사합니다.](#validate-sip-options)
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>SBC가 페어링된 SBC 목록에 있는지 확인

SBC를 연결한 후 [Get-CsOnlinePSTNGateway](/powershell/module/skype/get-csonlinepstngateway) cmdlet을 사용하여 SBC가 페어링된 SBC 목록에 있는지 확인할 수 있습니다. 원격 PowerShell 세션에서 다음을 입력한 다음 Enter를 누를 수 있습니다.

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

페어링된 게이트웨이는 아래 예제와 같이 목록에 표시해야 합니다. 사용 가능 매개 변수는 True 의 값을 **표시해야 합니다.** 

반환되는:

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

발신 SIP 옵션을 사용하여 페어링의 유효성을 검사하기 위해 SBC 관리 인터페이스를 사용하고 SBC가 발신 옵션 메시지에 대해 200개 확인 응답을 수신하는지 확인합니다.

직접 라우팅에서 들어오는 옵션을 볼 때 들어오는 옵션 메시지의 연락처 헤더 필드에 구성된 SBC FQDN에 보내는 SIP 옵션 메시지를 보내기 시작합니다. 

들어오는 SIP 옵션을 사용하여 페어링의 유효성을 검사하기 위해 SBC 관리 인터페이스를 사용하고 SBC가 직접 라우팅에서 들어오는 OPTIONS 메시지에 대한 회신을 보내고 보내는 응답 코드가 200 확인이 됐는지 확인할 수 있습니다.

## <a name="sbc-settings"></a>SBC 설정

이 표에는 새 [CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용하여 Microsoft Teams 관리 센터에서 SBC에 대해 설정할 수 있는 옵션을 나열합니다.

|필수?|Microsoft Teams 관리 센터 설정|PowerShell 매개 변수|설명|기본값|가능한 값|형식 및 제한 사항|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|예|**SBC에 대한 FQDN 추가**|FQDN |없음|FQDN 이름, 63자 제한|문자열, 컴퓨터, 도메인, 사이트 및 [OUS용 Active Directory의](https://support.microsoft.com/help/909264) 명명 규칙에서 허용 및 허용되지 않습니다 문자 목록을 참조하세요.|
|아니요|**사용 가능**|사용 가능|아웃바운드 호출에 대해 SBC를 켜는 데 사용할 수 있습니다. 이 기능을 사용하여 업데이트되는 동안 또는 유지 관리 중에 서비스에서 SBC를 일시적으로 제거할 수 있습니다. |False|True<br/>False|부울|
|예|**SIP 신호 포트**|SipSignalingPort |TLS(전송 계층) 프로토콜을 사용하여 직접 라우팅과 통신하는 데 사용되는 수신 수신 포트입니다.|없음|모든 포트|0~65535 |
|아니요|**SIP 옵션 보내기**|SendSIPOptions |SBC에서 SIP 옵션 메시지를 보낼지 여부를 정의합니다. 이 설정을 설정하는 것이 좋습니다. 이 설정이 해제된 경우 모니터링 및 경고 시스템에서 SBC가 제외됩니다.|True|True<br/>False|부울|
|아니요|**전달 통화 기록**|ForwardCallHistory |통화 기록 정보가 트렁크를 통해 전달인지 여부를 나타냅니다. 이 기능을 설정하면 Microsoft 365 또는 Office 365 프록시에서 기록 정보 및 추천 헤더를 전송합니다. |False|True<br/>False|부울|
|아니요|**PAI(전달 P-Asserted-identity) 헤더**|ForwardPAI|호출과 함께 PAI 헤더를 전달할지 여부를 나타냅니다. PAI 헤더를 사용하면 발신자 번호를 확인할 수 있습니다. 이 설정이 설정되어 있는 경우 Privacy:ID 헤더도 전송됩니다.|False|True<br/>False|부울|
|아니요|**동시 호출 용량**|MaxConcurrentSessions |값을 설정하면 동시 세션 수가 이 값보다 90% 이상이면 경고 시스템이 사용자에게 알릴 것입니다. 값을 설정하지 않은 경우 경고가 생성되지 않습니다. 그러나 모니터링 시스템은 24시간마다 동시 세션 수를 보고합니다. |Null|Null<br/>1~100,000 ||
|아니요|**장애 조치(Failover) 응답 코드**|FailoverResponseCodes<br>|직접 라우팅이 발신 초대에 대한 응답으로 4xx 또는 6xx SIP 오류 코드를 수신하는 경우 호출은 기본적으로 완료된 것으로 간주됩니다. 발신은 트래픽 흐름을 Teams 클라이언트 -Teams > -> SBC -전화 통신 네트워크)를 > 호출을 의미합니다. 장애 조치(failover) 응답 코드를 지정하면 SBC가 네트워크 또는 기타 문제로 호출할 수 없는 경우 지정한 코드를 수신할 때 직접 라우팅이 다른 SBC를 시도하도록 강제합니다(사용자의 음성 라우팅 정책에 다른 SBC가 있는 경우). 자세한 내용은 SBC(세션 경계 컨트롤러)에서 받은 특정 SIP 코드의 [장애 조치(Failover)를 참조합니다.](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|아니요|**장애 조치 시간(초)**|FailoverTimeSeconds |값을 설정하면 설정한 시간 내에 게이트웨이에서 응답하지 않는 아웃바운드 호출이 사용 가능한 다음 트렁크로 라우팅됩니다. 추가 트렁크가 없는 경우 호출이 자동으로 삭제됩니다. 기본값은 10초입니다. 네트워크 및 게이트웨이 응답이 느린 조직에서 이로 인해 호출이 불필요하게 삭제될 수 있습니다.|10|번호|Int|
|아니요|**미디어 트래픽에 대한 기본 설정 국가 또는 지역**|MediaRelayRoutingLocationOverride |미디어 트래픽에 대해 선호하는 국가 또는 지역을 수동으로 설정하는 데 사용하세요. 호출 로그가 미디어 경로에 대한 데이터 센터의 기본 할당이 SBC 데이터 센터에 가장 가까운 경로를 사용하지 않는다는 것을 명확하게 나타내는 경우 이 설정을 사용하는 것이 좋습니다. 기본적으로 직접 라우팅은 SBC의 공용 IP 주소를 기반으로 데이터 센터를 할당하고 항상 SBC 데이터 센터에 가장 가까운 경로를 선택합니다. 그러나 경우에 따라 기본 경로가 최적의 경로가 아 아를 수 있습니다. 이 매개 변수를 사용하면 미디어 트래픽에 대해 기본 설정 지역을 수동으로 설정할 수 있습니다. |없음|ISO 형식의 국가 코드||
|아니요|**SBC는 긴급 통화에 대한 PIDF/LO를 지원합니다.**|PidfloSupported|SBC가 긴급 통화에 대해 PIDF/LO(현재 상태 정보 데이터 형식 위치 개체)를 지원하는지 여부를 지정합니다.||||
|아니요| - |MediaBypass|이 설정은 SBC가 미디어 우회를 지원하는지 여부와 이 SBC에 사용할지 여부를 나타냅니다. |없음|True<br/>False|부울|

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)

[Teams PowerShell 개요](teams-powershell-overview.md)