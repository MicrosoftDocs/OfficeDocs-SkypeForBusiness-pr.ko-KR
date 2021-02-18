---
title: 직접 라우팅에 SBC(세션 테두리 컨트롤러) 연결
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
description: SBC를 구성하고 전화 시스템 직접 라우팅에 연결하는 방법을 배워야 합니다.
ms.openlocfilehash: 4240eb4000e813df51b2678ad2e9c37f6bc0c2ac
ms.sourcegitcommit: 414d077b16a0ae4ea6a49e3b3d0082858174cacb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "50278708"
---
# <a name="connect-your-session-border-controller-sbc-to-direct-routing"></a>직접 라우팅에 SBC(세션 테두리 컨트롤러) 연결

이 문서에서는 SBC(세션 테두리 컨트롤러)를 구성하고 전화 시스템 직접 라우팅에 연결하는 방법을 설명하고 있습니다.  직접 라우팅을 구성하는 다음 단계의 1단계입니다.

- **1단계. 휴대폰 시스템과 SBC 연결 및** 연결 유효성 검사(이 문서)
- 2단계. [직접 라우팅에 대해 사용자 사용](direct-routing-enable-users.md)
- 3단계. [호출 라우팅 구성](direct-routing-voice-routing.md)
- 4단계. [숫자를 대체 형식으로 변환](direct-routing-translate-numbers.md)

직접 라우팅을 설정하는 데 필요한 모든 단계에 대한 자세한 내용은 직접 라우팅 [구성을 참조하세요.](direct-routing-configure.md)

[Microsoft Teams](#using-the-microsoft-teams-admin-center) 관리 센터 또는 [PowerShell을](#using-powershell) 사용하여 SBC를 구성하고 직접 라우팅에 연결할 수 있습니다.

## <a name="using-the-microsoft-teams-admin-center"></a>Microsoft Teams 관리 센터 사용

1. 왼쪽 탐색 창에서 **음성** 직접 라우팅으로 이동한 다음  >   **SBC 탭을** 클릭합니다.
2. **추가** 를 클릭합니다.
3. SBC에 대한 FQDN을 입력합니다. <br><br>FQDN의 도메인 이름 부분이 테넌트에 등록된 도메인과 일치하는지 확인한 후 도메인 이름은 SBC FQDN 도메인 이름에 지원되지 `*.onmicrosoft.com` 않습니다. 예를 들어 두 개의 도메인 이름이 있는 경우 `contoso.com` `contoso.onmicrosoft.com` `sbc.contoso.com` SBC 이름으로 사용 합니다. 하위omain을 사용하는 경우 이 하위도 테넌트에 등록되어 있는지를 확인 합니다. 예를 들어 사용하려는 경우 `sbc.service.contoso.com` `service.contoso.com` 등록해야 합니다.
4. 조직의 요구에 따라 SBC에 대해 다음 설정을 구성합니다. 이러한 각 설정에 대한 자세한 내용은 [SBC 설정을 참조하세요.](#sbc-settings)

    ![Microsoft Teams 관리 센터에서 SBC 페이지 추가 스크린샷](media/direct-routing-add-sbc.png)

5. 모두 마쳤으면 **저장** 을 클릭합니다.

## <a name="using-powershell"></a>PowerShell 사용

SBC를 직접 라우팅에 연결하려면 다음을 해야 합니다.

1. [PowerShell을 사용하여 비즈니스용 Skype Online에 연결합니다.](#connect-to-skype-for-business-online-by-using-powershell)
2. [SBC를 테넌트에 연결합니다.](#connect-the-sbc-to-the-tenant)
3. [SBC 연결을 확인합니다.](#verify-the-sbc-connection)

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>PowerShell을 사용하여 비즈니스용 Skype Online에 연결

테넌트에 연결된 PowerShell 세션을 사용하여 SBC를 직접 라우팅 인터페이스와 페어링할 수 있습니다. PowerShell 세션을 열기 위해 컴퓨터 설정에 설명된 단계를 [Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
 
원격 PowerShell 세션을 설정한 후 SBC를 관리하는 명령을 볼 수 있는지 확인해야 합니다. 명령을 확인하기 위해 PowerShell 세션에서 다음 명령을 입력하거나 복사하여 붙여넣은 다음 Enter를 누르기만 합니다. 

```PowerShell
Get-Command *onlinePSTNGateway*
```

이 명령은 SBC를 관리할 수 있도록 여기에 표시된 4개의 함수를 반환합니다.

<pre>
CommandType    Name                       Version    Source 
-----------    ----                       -------    ------ 
Function       Get-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       New-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt 
Function       Remove-CsOnlinePSTNGateway 1.0        tmp_v5fiu1no.wxt 
Function       Set-CsOnlinePSTNGateway    1.0        tmp_v5fiu1no.wxt
</pre>

### <a name="connect-the-sbc-to-the-tenant"></a>테넌트에 SBC 연결

[New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용하여 SBC를 테넌트에 연결합니다. PowerShell 세션에서 다음을 입력한 다음 Enter를 누르고 있습니다.

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignalingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true
```

  > [!NOTE]
  > 1. SBC 설명서에서 찾을 수 있는 정보를 사용하여 SBC에서 최대 호출 제한을 설정하는 것이 좋습니다. 이 제한은 SBC가 용량 수준에 있는 경우 알림을 트리거합니다.
  > 2. FQDN의 도메인 부분이 .onmicrosoft.com 제외한 테넌트에 등록된 도메인 중 하나와 일치하는 경우 SBC를 \* 연결할 수 onmicrosoft.com. \*.onmicrosoft.com 도메인 이름은 SBC FQDN 이름에 지원되지 않습니다. 예를 들어 **contoso**.com 및 **contoso**.onmicrosoft.com 두 개의 도메인 이름이 있는 경우 SBC 이름에 sbc.contoso.com 수 있습니다. sbc.contoso.abc와 같은 이름으로 SBC를 연결하려고 시도하면 도메인이 이 테넌트에서 소유하지 않는 것이기 때문에 시스템에서는 사용자가 사용할 수 없습니다.<br/>
  > 테넌트에 등록된 도메인 외에도 해당 도메인 및 할당된 E3 또는 E5 라이선스가 있는 사용자가 있는 것이 중요합니다. 그렇지 않은 경우 다음 오류가 표시됩니다.<br/>
  `Can not use the "sbc.contoso.com" domain as it was not configured for this tenant`.

예제는 다음과 같습니다.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignalingPort 5067 -MaxConcurrentSessions 100 
```

반환되는 사항:

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
> 이 예제에서는 최소 필수 매개 변수만 보여줍니다. 연결 프로세스 중에 [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet으로 설정할 수 있는 추가 매개 변수가 있습니다. 자세한 내용은 [SBC 설정을 참조하세요.](#sbc-settings)
 
### <a name="verify-the-sbc-connection"></a>SBC 연결 확인

연결을 확인:

- [SBC가 쌍을 이르는 SBC 목록에 있는지 여부를 검사합니다.](#check-whether-the-sbc-is-on-the-list-of-paired-sbcs)
- [SIP 옵션의 유효성을 검사합니다.](#validate-sip-options)
 
#### <a name="check-whether-the-sbc-is-on-the-list-of-paired-sbcs"></a>SBC가 쌍을 이르는 SBC 목록에 있는지 확인

SBC를 연결한 후 [Get-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/get-csonlinepstngateway) cmdlet을 사용하여 SBC가 쌍을 이은 SBC 목록에 있는지를 확인할 수 있습니다. 원격 PowerShell 세션에서 다음을 입력한 다음 Enter를 누르기

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```

쌍을 이루는 게이트웨이는 아래 예제와 같이 목록에 나타나야 합니다. **Enabled** 매개 변수는 True 값을 **표시해야 합니다.**

반환되는 사항:

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

발신 SIP 옵션을 사용하여 페어링의 유효성을 검사하기 위해 SBC 관리 인터페이스를 사용하고 SBC가 발신 OPTIONS 메시지에 대해 200 OK 응답을 수신하는지 확인합니다.

직접 라우팅에 들어오는 옵션이 표시되면 들어오는 OPTIONS 메시지의 연락처 헤더 필드에 구성된 SBC FQDN으로 보내는 SIP 옵션 메시지를 보내기 시작하게 됩니다. 

들어오는 SIP 옵션을 사용하여 페어링의 유효성을 검사하기 위해 SBC 관리 인터페이스를 사용하고 SBC가 직접 라우팅에서 들어오는 OPTIONS 메시지에 회신을 보내고 보내는 응답 코드가 200 OK입니다.

## <a name="sbc-settings"></a>SBC 설정

이 표에는 Microsoft Teams 관리 센터에서 [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet을 사용하여 SBC에 설정할 수 있는 옵션이 나열되어 있습니다.

|필수?|Microsoft Teams 관리 센터 설정|PowerShell 매개 변수|설명|기본값|가능한 값|유형 및 제한 사항|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|예|**SBC용 FQDN 추가**|FQDN |없음|FQDN 이름, 63자 제한|문자열, 컴퓨터, 도메인, 사이트 및 OW에 대한 [Active Directory의](https://support.microsoft.com/help/909264) 명명 규칙에서 허용 및 허용되지 않습니다 문자 목록을 참조하세요.|
|아니요|**사용**|사용|아웃바운드 호출에 대해 SBC를 켜는 데 사용 이 기능을 사용하여 업데이트되는 동안 또는 유지 관리 중에 서비스에서 SBC를 일시적으로 제거할 수 있습니다. |False|True<br/>False|부울|
|예|**SIP 신호 포트**|SipSignalingPort |TLS(전송 계층) 프로토콜을 사용하여 직접 라우팅과 통신하는 데 사용되는 수신 포트입니다.|없음|모든 포트|0 ~ 65535 |
|아니요|**SIP 옵션 보내기**|SendSIPOptions |SBC에서 SIP 옵션 메시지를 보낼지 여부를 정의합니다. 이 설정을 설정하는 것이 좋습니다. 이 설정이 해제된 경우 SBC는 모니터링 및 경고 시스템에서 제외됩니다.|True|True<br/>False|부울|
|아니요|**통화 기록 전달**|ForwardCallHistory |통화 기록 정보가 트렁크를 통해 전달할지 여부를 나타냅니다. 이 기능을 설정하면 Microsoft 365 또는 Office 365 프록시에서 기록 정보 및 추천 헤더를 전송합니다. |False|True<br/>False|부울|
|아니요|**PAI(Forward P-Asserted-identity) 헤더**|ForwardPAI|호출과 함께 PAI 헤더를 전달할지 여부를 나타냅니다. PAI 헤더를 사용하면 발신자 번호를 확인할 수 있습니다. 이 설정이 설정되어 있는 경우 Privacy:ID 헤더도 전송됩니다.|False|True<br/>False|부울|
|아니요|**동시 호출 용량**|MaxConcurrentSessions |값을 설정하면 동시 세션 수가 이 값보다 90% 이상일 때 경고 시스템에서 알릴 수 있습니다. 값을 설정하지 않은 경우 경고가 생성되지 않습니다. 그러나 모니터링 시스템은 24시간마다 동시 세션 수를 보고합니다. |Null|Null<br/>1~ 100,000 ||
|아니요|**장애 조치(failover) 응답 코드**|FailoverResponseCodes<br>|직접 라우팅이 발신 초대에 대한 응답으로 4xx 또는 6xx SIP 오류 코드를 수신하는 경우 호출은 기본적으로 완료된 것으로 간주됩니다. 발신은 트래픽 흐름이 있는 Teams 클라이언트에서 PSTN으로의 통화를 의미합니다. Teams 클라이언트 -> 직접 라우팅 -> SBC -> 전화 통신 네트워크). 장애 조치(failover) 응답 코드를 지정하면 SBC가 네트워크 또는 기타 문제로 호출할 수 없는 경우 지정한 코드를 수신할 때 직접 라우팅에서 다른 SBC(사용자의 음성 라우팅 정책에 다른 SBC가 있는 경우)를 시도하도록 강제합니다. 자세한 내용은 SBC(세션 테두리 컨트롤러)에서 받은 특정 SIP 코드의 장애 [조치(Failover)를 참조합니다.](direct-routing-trunk-failover-on-outbound-call.md)|408, 503, 504||Int|
|아니요|**장애 조치(failover) 시간(초)**|FailoverTimeSeconds |값을 설정하면 설정한 시간 내에 게이트웨이에서 응답하지 않는 아웃바운드 호출이 사용 가능한 다음 트렁크로 라우팅됩니다. 추가 트렁크가 없는 경우 호출이 자동으로 삭제됩니다. 기본값은 10초입니다. 느린 네트워크 및 게이트웨이 응답이 있는 조직에서 이로 인해 호출이 불필요하게 삭제될 수 있습니다.|10|숫자|Int|
|아니요|**미디어 트래픽에 대한 기본 설정 국가 또는 지역**|MediaRelayRoutingLocationOverride |미디어 트래픽에 대해 선호하는 국가 또는 지역을 수동으로 설정하는 데 사용하세요. 호출 로그가 미디어 경로에 대한 데이터 센터의 기본 할당이 SBC 데이터 센터에 가장 가까운 경로를 사용하지 않는다고 명확하게 나타내는 경우 이를 설정하는 것이 좋습니다. 기본적으로 직접 라우팅은 SBC의 공용 IP 주소를 기반으로 데이터 센터를 할당하고 항상 SBC 데이터 센터에 가장 가까운 경로를 선택합니다. 그러나 경우에 따라 기본 경로가 최적 경로가 아 될 수 있습니다. 이 매개 변수를 사용하면 미디어 트래픽에 대한 기본 지역을 수동으로 설정할 수 있습니다. |없음|ISO 형식의 국가 코드||
|아니요|**SBC는 긴급 통화에 대해 PIDF/LO를 지원**|PidfloSupported|SBC가 긴급 통화에 대해 PIDF/LO(현재 상태 정보 데이터 형식 위치 개체)를 지원하는지 여부를 지정합니다.||||
|아니요|**사용자를 찾으려고 하는 동안 전화 벨 울리기**|GenerateRingingWhileLocatingUser|발신자에 오디오 신호가 재생되어 Teams가 통화를 설정하고 있는지를 나타냅니다. 이 설정은 미디어 우회 모드가 아닌 직접 라우팅에만 적용됩니다. 경우에 따라 PSTN에서 Teams 클라이언트로의 인바운드 호출을 설정하는 데 예상보다 오래 걸릴 수 있습니다. 이 경우 발신자가 아무 소리도 들리지 않을 수 있으며 Teams 클라이언트는 벨이 울리지 않습니다. 일부 통신 공급자가 통화를 취소할 수 있습니다. 이 설정은 이러한 시나리오에서 발생할 수 있는 예기치 않은 묵음을 방지하는 데 도움이 됩니다.|True|True<br/>False|부울|
|아니요| - |MediaBypass|이 설정은 SBC가 미디어 우회를 지원하는지 여부와 이 SBC에 사용할지 여부를 나타냅니다. |없음|True<br/>False|부울|

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)

[직접 라우팅 구성](direct-routing-configure.md)

[Teams PowerShell 개요](teams-powershell-overview.md)
