---
title: 직접 라우팅 구성
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
description: Microsoft 전화 시스템 다이렉트 라우팅을 구성 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 40439fd31db458f8cb306c0e3dbd456aa59a7a21
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111732"
---
# <a name="configure-direct-routing"></a>직접 라우팅 구성

> [!Tip]
> 직접적인 라우팅, 계획 방법 및 배포 방법에 대 한 자세한 내용은 다음 세션을 시청 하세요. [Microsoft 팀의 직접 라우팅](https://aka.ms/teams-direct-routing)

아직 수행 하지 않은 경우에는 필수 구성 요소에 대 한 [직접 라우팅 계획](direct-routing-plan.md) 을 읽고 Microsoft 전화 시스템 네트워크를 구성 하기 전에 수행 해야 하는 다른 단계를 검토 합니다. 

이 문서에서는 Microsoft 전화 시스템 다이렉트 라우팅을 구성 하는 방법에 대해 설명 합니다. SBC (지원 되는 세션 경계 컨트롤러)를 연결 하는 방법에 대해 설명 하 고, Microsoft 팀 사용자가 PSTN (공개 교환 전화 네트워크)에 연결 하기 위해 직접 라우팅을 사용 하도록 구성 하는 방법에 대해 자세히 알아보세요. 이 문서에서 설명 하는 단계를 완료 하려면 관리자가 PowerShell cmdlet에 대해 잘 알고 있어야 합니다. PowerShell을 사용 하는 방법에 대 한 자세한 내용은 [Windows PowerShell 용 컴퓨터 설정을](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)참조 하세요. 

Sbc 공급 업체에서 권장 하는 바와 같이 SBC가 이미 구성 되어 있는지 확인 하는 것이 좋습니다. 

- [오디오 코드 배포 설명서](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [Oracle 배포 문서](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [리본 커뮤니케이션 배포 문서](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [TE-시스템 (anynode) 배포 문서](https://www.anynode.de/anynode-and-microsoft-teams/)

Microsoft 전화 시스템을 구성 하 고 사용자가 직접 라우팅을 사용 하도록 설정한 다음 다음 절차를 완료 하 여 기본 통화 클라이언트로 Microsoft 팀을 설정할 수 있습니다. 

- [Microsoft 전화 시스템을 사용 하 여 SBC 쌍을 연결 하 고 페어링의 유효성을 검사 합니다.](#pair-the-sbc-to-the-direct-routing-service-of-phone-system)
- [사용자가 직접 라우팅 서비스를 사용 하도록 설정](#enable-users-for-direct-routing-service)
- Microsoft 팀이 사용자를 위한 기본 통화 클라이언트 인지 확인

## <a name="pair-the-sbc-to-the-direct-routing-service-of-phone-system"></a>전화 시스템의 다이렉트 라우팅 서비스에 SBC 쌍을 연결 합니다. 

다음은 직접 라우팅 인터페이스에 SBC를 연결 하거나 연결할 수 있도록 하는 세 가지 상위 수준 단계입니다. 

- PowerShell을 사용 하 여 **비즈니스용 Skype Online** 관리 센터에 연결 
- SBC 쌍 
- 페어링의 유효성을 검사 합니다. 

### <a name="connect-to-skype-for-business-online-by-using-powershell"></a>PowerShell을 사용 하 여 비즈니스용 Skype Online에 연결 

테 넌 트에 연결 된 PowerShell 세션을 사용 하 여 SBC를 직접 라우팅 인터페이스에 쌍으로 연결할 수 있습니다. PowerShell 세션을 열려면 [Windows powershell 용 컴퓨터 설정](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)에 설명 된 단계를 따르세요. 
 
원격 PowerShell 세션을 설정한 후 SBC 관리 명령을 볼 수 있는지 확인 하세요. 명령에 대 한 유효성을 검사 하려면 PowerShell 세션에서 다음을 입력 하거나 복사/붙여넣고 enter 키를 누릅니다. 

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


### <a name="pair-the-sbc-to-the-tenant"></a>SBC와 테 넌 트를 쌍으로 연결 

SBC와 테 넌 트를 쌍으로 연결 하려면 PowerShell 세션에서 다음을 입력 하 고 enter 키를 누릅니다. 

```PowerShell
New-CsOnlinePSTNGateway -Fqdn <SBC FQDN> -SipSignallingPort <SBC SIP Port> -MaxConcurrentSessions <Max Concurrent Sessions the SBC can handle> -Enabled $true 
```
  > [!NOTE]
  > 1. SBC 문서에서 찾을 수 있는 정보를 사용 하 여 SBC의 최대 통화 제한 값을 설정할 것을 적극 권장 합니다. 이 제한은 SBC이 용량 수준에 있는 경우 알림을 트리거합니다.
  > 2. FQDN의 도메인 부분이 onmicrosoft.com를 제외 \*하 고 테 넌 트에서 등록 된 도메인 중 하 나와 일치 하는 경우에만 SBC를 쌍으로 연결할 수 있습니다. Onmicrosoft.com \*도메인 이름을 사용 하는 것은 SBC FQDN 이름에 대해 지원 되지 않습니다. 예를 들어 도메인 이름이 두 개 있는 경우:<br/><br/>
  > **contoso**. c a m<br/>**contoso**. onmicrosoft.com<br/><br/>
  > SBC 이름에는 이름 sbc.contoso.com를 사용할 수 있습니다. Sbc와 이름 sbc를 쌍으로 연결 하려고 하면이 테 넌 트가 도메인을 소유 하지 않으므로 시스템에서 사용자를 허용 하지 않습니다.<br/>
  > 테 넌 트에 등록 된 도메인 외에도 해당 도메인 및 할당 된 E3 또는 E5 라이선스를 가진 사용자가 있어야 합니다. 그렇지 않으면 다음 오류가 표시 됩니다.<br/>
  `Can not use the “sbc.contoso.com” domain as it was not configured for this tenant`.

```PowerShell
New-CsOnlinePSTNGateway -Identity sbc.contoso.com -Enabled $true -SipSignallingPort 5067 -MaxConcurrentSessions 100 
```
구합니다
<pre>
Identity              : sbc.contoso.com 
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True   
</pre>
페어링 프로세스 중에 설정할 수 있는 추가 옵션이 있습니다. 그러나 앞의 예제에서는 필요한 최소 매개 변수만 표시 합니다. 
 
다음 표에는 매개 변수를 ```New-CsOnlinePstnGateway```설정 하는 데 사용할 수 있는 추가 매개 변수가 나와 있습니다.

|필수?|이름|설명|기본값|사용할 수 있는 값|유형 및 제한 사항|
|:-----|:-----|:-----|:-----|:-----|:-----|
|예|Q|SBC의 FQDN 이름입니다. |없음|비 Efqdn 이름, 63 문자 제한|[Active Directory에서 컴퓨터, 도메인, 사이트 및 ou에 대 한 명명 규칙](https://support.microsoft.com/help/909264) 의 허용 및 허용 되지 않는 문자 목록 문자열|
|아니요|MediaBypass |SBC로 표시 된 매개 변수는 미디어 바이패스를 지원 하 고 관리자가이를 사용 하려고 합니다.|없음|False<br/>해제|부울|
|예|SipSignallingPort |TLS (전송 계층 보안) 프로토콜을 사용 하 여 직접 라우팅 서비스와 통신 하는 데 사용 되는 수신 대기 포트입니다.|없음|모든 포트|0 ~ 65535 |
|아니요|FailoverTimeSeconds |10으로 설정 된 경우 (기본값), 게이트웨이에서 응답 하지 않은 아웃 바운드 호출은 10 초 이내에 사용 가능한 다음 트렁크로 라우팅됩니다. 추가 trunks 없으면 통화가 자동으로 삭제 됩니다. 느린 네트워크 및 게이트웨이 응답을 사용 하는 조직에서 호출이 불필요 하 게 손실 될 수 있습니다. 기본값은 10입니다.|1천만|숫자로|Int|
|아니요|ForwardCallHistory |트렁크를 통해 통화 기록 정보를 전달할지 여부를 나타냅니다. 이 기능을 사용 하도록 설정 하면 Office 365 PSTN 프록시가 두 가지 헤더 인 기록 정보 및 참조 하는 사람을 보냅니다. 기본값은 **False** ($False)입니다. |해제|False<br/>해제|부울|
|아니요|ForwardPAI|PAI(P-Asserted-Identity) 헤더를 통화와 함께 전달할지 여부를 나타냅니다. PAI 헤더를 사용하면 발신자 번호를 확인할 수 있습니다. 사용 하도록 설정한 경우 개인 정보 취급 방침: ID 헤더만 전송 됩니다. 기본값은 **False** ($False)입니다.|해제|False<br/>해제|부울|
|아니요|SendSIPOptions |SBC가 SIP 옵션을 보내지 않을 지 여부를 정의 합니다. 이 기능을 사용 하지 않도록 설정 하면 SBC이 모니터링 및 경고 시스템에서 제외 됩니다. SIP 옵션을 사용 하도록 설정 하는 것이 좋습니다. 기본값은 **True**입니다. |False|False<br/>해제|부울|
|아니요|MaxConcurrentSessions |경고 시스템에서 사용 합니다. 값이 설정 되 면 경고 시스템에서는 동시 세션 수가이 값 보다 90% 이상일 때 테 넌 트 관리자에 게 알림을 생성 합니다. 매개 변수를 설정 하지 않으면 경고가 생성 되지 않습니다. 그러나 모니터링 시스템에서는 24 시간 마다 동시 세션의 수를 보고 합니다. |L|L<br/>1 ~ 10만 ||
|아니요|MediaRelayRoutingLocationOverride |수동으로 미디어 경로를 선택할 수 있습니다. 직접 라우팅은 미디어 경로에 대 한 데이터 센터에 SBC의 공용 IP를 기반으로 할당 합니다. 항상 SBC 데이터 센터에 가장 가까운 위치를 선택 합니다. 그러나 경우에 따라 미국 범위에 있는 공용 IP를 유럽의 SBC에 할당할 수 있습니다. 이 경우 최적이 아닌 미디어 경로를 사용 하 게 됩니다. 이 매개 변수를 사용 하면 미디어 트래픽에 대 한 기본 설정 영역을 수동으로 설정할 수 있습니다. 미디어 경로에 대 한 데이터 센터의 자동 할당이 SBC 데이터 센터에 가장 근접 하 게 할당 되지 않는다는 것을 호출 로그가 명확 하 게 나타내는 경우에만이 매개 변수를 설정 하는 것이 좋습니다. |없음|ISO 형식의 국가 코드||
|아니요|수|이 SBC를 발신 전화에 사용 하도록 설정 합니다. 은 SBC, 업데이트 중이거나 유지 관리 중에 일시적으로 제거 하는 데 사용할 수 있습니다. |해제|False<br/>해제|부울|
 
### <a name="verify-the-sbc-pairing"></a>SBC 페어링 확인 

연결 확인: 
- SBC가 쌍의 SBCs 목록에 있는지 확인 합니다. 
- SIP 옵션의 유효성을 검사 합니다. 
 
#### <a name="validate-if-the-sbc-is-on-the-list-of-paired-sbcs"></a>SBC이 쌍의 SBCs 목록에 있는지 확인 합니다. 

SBC 쌍을 곱한 후 원격 PowerShell 세션에서 다음 명령을 실행 하 여 해당 SBC가 쌍을 이루는 SBCs 목록에 있는지 확인 합니다.`Get-CSOnlinePSTNGateway`

쌍으로 연결 된 게이트웨이는 아래 예제에 표시 된 대로 목록에 표시 되어야 하며 **Enabled** 매개 변수에 **True**값이 표시 되는지 확인 합니다. 입력

```PowerShell
Get-CsOnlinePSTNGateway -Identity sbc.contoso.com  
```
반환 되는 결과:
<pre>
Identity              : sbc.contoso.com  
Fqdn                  : sbc.contoso.com 
SipSignallingPort     : 5067 
CodecPriority         : SILKWB,SILKNB,PCMU,PCMA 
ExcludedCodecs        :  
FailoverTimeSeconds   : 10 
ForwardCallHistory    : False 
ForwardPai            : False 
SendSipOptions        : True 
MaxConcurrentSessions : 100 
Enabled               : True 
</pre>

#### <a name="validate-sip-options-flow"></a>SIP 옵션 흐름의 유효성 검사 

나가는 SIP 옵션을 사용 하 여 페어링의 유효성을 검사 하려면 SBC 관리 인터페이스를 사용 하 고 SBC가 보내는 옵션 메시지에 대 한 200 OK 응답을 수신 하는지 확인 합니다.

직접적인 라우팅이 수신 옵션을 인식 하는 경우 수신 옵션 메시지의 대화 상대 헤더 필드에 구성 된 SBC FQDN으로 보내는 SIP 옵션 메시지를 전송 하기 시작 합니다. 

들어오는 SIP 옵션을 사용 하 여 페어링의 유효성을 검사 하려면 SBC 관리 인터페이스를 사용 하 여 SBC가 직접 라우팅에서 들어오는 옵션 메시지에 대 한 응답을 보내고, 전송 하는 응답 코드는 200 OK를 참조 합니다.

## <a name="enable-users-for-direct-routing-service"></a>사용자가 직접 라우팅 서비스를 사용 하도록 설정 

직접 라우팅 서비스에 대해 사용자를 사용할 준비가 되 면 다음 단계를 수행 합니다. 

1. Office 365에서 사용자를 만들고 전화 시스템 라이선스를 할당 합니다. 
2. 사용자가 비즈니스용 Skype Online에 있는지 확인 합니다. 
3. 전화 번호를 구성 하 고 엔터프라이즈 음성 및 보이스 메일을 사용 하도록 설정 합니다. 
4. 음성 라우팅을 구성 합니다. 경로는 자동으로 유효성이 검사 됩니다.

### <a name="create-a-user-in-office-365-and-assign-the-license"></a>Office 365에서 사용자를 만들고 라이선스를 할당 합니다. 

Office 365에서 새 사용자를 만드는 두 가지 옵션이 있습니다. 그러나 라우팅 문제를 방지 하기 위해 조직에서 하나의 옵션을 선택 하 고 사용 하는 것이 좋습니다. 

- 온-프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드와 동기화 합니다. [Azure Active Directory와 온-프레미스 디렉터리 통합](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)을 참조 하세요.
- Office 365 관리자 포털에서 직접 사용자를 만듭니다. [Office 365에 개별적으로 또는 대량으로 사용자 추가-관리자 도움말을](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)참조 하세요. 

비즈니스용 skype Online 배포에 비즈니스용 Skype 2015 또는 Lync 2010/2013 온-프레미스가 있는 경우 유일 하 게 지원 되는 옵션은 온-프레미스 Active Directory에서 사용자를 만들고 사용자를 클라우드와 동기화 (옵션 1) 하는 것입니다. 

라이선스 요구 사항에 대 한 자세한 내용은 [직접 라우팅 계획](direct-routing-plan.md)의 [라이선스 및 기타 요구 사항을](direct-routing-plan.md#licensing-and-other-requirements) 참조 하세요.

### <a name="ensure-that-the-user-is-homed-in-skype-for-business-online"></a>사용자가 비즈니스용 Skype Online에 있는지 확인 

직접 라우팅에는 사용자가 비즈니스용 Skype Online에 있어야 합니다. RegistrarPool 매개 변수를 살펴보면이를 확인할 수 있습니다. Infra.lync.com 도메인에 값이 있어야 합니다.

1. 원격 PowerShell에 연결 합니다.
2. 다음 명령을 실행 합니다. 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool
    ``` 

### <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a>전화 번호를 구성 하 고 엔터프라이즈 음성 및 보이스 메일 사용 

사용자를 만들고 라이선스를 할당 한 후 다음 단계는 전화 번호와 보이스 메일을 구성 하는 것입니다. 이 작업을 한 번에 수행할 수 있습니다. 

전화 번호를 추가 하 고 보이스 메일을 사용 하도록 설정 하려면:
 
1. 원격 PowerShell 세션에 연결 합니다. 
2. 명령 입력: 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<E.164 phone number>
    ```

예를 들어 "Spencer Low" 사용자의 전화 번호를 추가 하려면 다음을 입력 합니다. 

```PowerShell
Set-CsUser -Identity "Spencer Low" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
```

사용 된 전화 번호는 국가 코드를 사용 하 여 전체 전자 164 자로 구성 되어야 합니다. 

  > [!NOTE]
  > 사용자의 전화 번호가 온-프레미스에서 관리 되는 경우 온-프레미스 Skype for Business 관리 셸 또는 제어판을 사용 하 여 사용자의 전화 번호를 구성 합니다. 

### <a name="configure-voice-routing"></a>음성 라우팅 구성 

Microsoft 휴대폰 시스템에는 다음을 기준으로 특정 SBC로 전화를 보낼 수 있는 라우팅 메커니즘이 있습니다. 

- 전화 번호 패턴 
- 전화 번호 패턴 호출을 하는 특정 사용자
 
SBCs는 활성 및 백업으로 지정 될 수 있습니다. 즉,이 번호 패턴에 대해 활성으로 구성 된 SBC 또는 번호 패턴 + 특정 사용자를 사용할 수 없는 경우에는 통화가 백업 SBC로 라우팅됩니다.
 
통화 라우팅은 다음 요소로 구성 됩니다. 
- 음성 라우팅 정책 – PSTN 사용을 위한 컨테이너 사용자 또는 여러 사용자에 게 할당할 수 있습니다. 
- PSTN 사용 – 음성 경로 및 PSTN 사용량을 위한 컨테이너 다른 음성 라우팅 정책에서 공유 가능 
- 음성 경로 – 호출 번호가 패턴과 일치 하는 호출에 사용할 온라인 PSTN 게이트웨이 집합 및 번호 패턴 
- 온라인 PSTN 게이트웨이-SBC에 대 한 포인터는 호출이 SBC를 통해 호출 될 때 적용 되는 구성 (예: 정방향 P-어설션된-Id (PAI) 또는 기본 설정 코덱)도 저장 합니다. 음성 경로에 추가할 수 있습니다. 

#### <a name="creating-a-voice-routing-policy-with-one-pstn-usage"></a>하나의 PSTN 용도를 사용 하 여 음성 라우팅 정책 만들기 

다음 다이어그램은 통화 흐름에서 음성 라우팅 정책의 두 가지 예를 보여줍니다.

**통화 흐름 1 (왼쪽):** 사용자가 + 1 425 XXX XX xx 또는 + 1 206 XXX XX XX에 전화를 거는 경우, 통화는 SBC sbc1.contoso.biz 또는 sbc2.contoso.biz로 라우팅됩니다. Sbc1.contoso.biz 나 sbc2.contoso.biz 모두 사용할 수 없는 경우에는 통화가 손실 됩니다. 

**통화 흐름 2 (오른쪽):** 사용자가 + 1 425 XXX XX xx 또는 + 1 206 XXX XX XX에 전화를 거는 경우, 통화는 먼저 SBC sbc1.contoso.biz 또는 sbc2.contoso.biz로 라우팅됩니다. 두 SBC를 모두 사용할 수 없는 경우 우선 순위가 낮은 경로 (sbc3.contoso.biz 및 sbc4.contoso.biz)가 시도 됩니다. 사용할 수 있는 SBCs 장치가 없으면 통화가 끊깁니다. 

![음성 라우팅 정책 예제 표시](media/ConfigDirectRouting-VoiceRoutingPolicyExamples.png)

두 예제에서 음성 경로에 우선 순위를 할당 하는 동안 경로의 SBCs는 임의 순서 대로 시도 됩니다.

  > [!NOTE]
  > 사용자에 게 Microsoft 통화 계획 라이선스가 없는 경우 예제 구성의 패턴 + 1 425 XXX XX xx 또는 + 1 206 XXX XX XX와 일치 하는 숫자를 제외한 모든 번호로 거는 호출이 삭제 됩니다. 사용자에 게 통화 요금제 라이선스가 있는 경우이 통화는 Microsoft 호출 계획의 정책에 따라 자동으로 라우팅됩니다. 

Microsoft 통화 요금제는 Microsoft 통화 계획 라이선스를 사용 하 여 모든 사용자의 마지막 경로에 자동으로 적용 되며 추가 통화 라우팅 구성이 필요 하지 않습니다.

다음 다이어그램에 표시 된 예제에서는 다른 모든 미국 및 캐나다 번호 (호출 되는 번호 패턴 + 1 XXX XXX XX XX으로 이동 하는 호출)에 대 한 통화 보내기를 위해 음성 경로를 추가 합니다.

![세 번째 경로가 있는 음성 라우팅 정책 표시](media/ConfigDirectRouting-VoiceRoutingPolicywith3rdroute.png)

다른 모든 통화에 대해 사용자에 게 라이선스 (Microsoft 전화 시스템 및 Microsoft 호출 계획)가 둘 다 있는 경우 자동 경로가 사용 됩니다. 관리자가 만든 온라인 음성 경로의 숫자 패턴과 일치 하는 항목이 없는 경우 Microsoft 통화 요금제를 통해 라우팅합니다.

사용자에 게 Microsoft 전화 시스템만 있는 경우에는 일치 하는 규칙이 없기 때문에 통화가 끊깁니다.

  > [!NOTE]
  > 패턴 + 1 XXX XXX XX XX와 일치 하는 경로만 있으므로이 경우 경로 "Other + 1"에 대 한 우선 순위 값은 중요 하지 않습니다. 사용자가 + 1 324 567 89 89를 호출 하 고 sbc5.contoso.biz 및 sbc6.contoso.biz를 모두 사용할 수 없는 경우 통화가 삭제 됩니다.

다음 표에는 세 가지 음성 경로를 사용 하는 구성이 요약 되어 있습니다. 이 예제에서는 세 개의 경로가 모두 동일한 PSTN 사용 인 "미국 및 캐나다"의 일부입니다.

|**PSTN 사용**|**음성 경로**|**번호 패턴**|**중요도**|**하더라도**|**설명**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|미국만|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|호출 되는 번호 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX의 활성 경로|
|미국만|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|호출 되는 번호에 대 한 백업 경로 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX|
|미국만|"기타 + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6.contoso.biz|호출 되는 번호에 대 한 경로 + 1 XXX XXX XX XX (+ 1 425 XXX xx xx 또는 + 1 206 XXX XX xx 제외)|
|||||||

모든 경로는 PSTN 사용 "미국 및 캐나다"와 연결 되며, PSTN 사용은 음성 라우팅 정책 "미국 전용"과 연결 됩니다. 이 예제에서는 음성 라우팅 정책이 사용자 Spencer Low에 할당 됩니다.

#### <a name="examples-of-call-routes"></a>통화 경로의 예

다음 예제에서는 경로, PSTN 용도 및 라우팅 정책을 구성 하는 방법을 설명 하 고 정책을 사용자에 게 할당 합니다.

**1 단계:** PSTN 사용량 "미국 및 캐나다"를 만듭니다.

비즈니스용 Skype 원격 PowerShell 세션에 다음을 입력 합니다.

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="US and Canada"}
```

다음을 입력 하 여 사용이 생성 되었는지 확인 합니다. 
```PowerShell
Get-CSOnlinePSTNUsage
``` 
다음은 잘릴 수 있는 이름 목록을 반환 하는 것입니다.
```output
Identity    : Global
Usage       : {testusage, US and Canada, International, karlUsage. . .}
```
아래 예제에서는 전체 이름을 표시 하는 PowerShell 명령을 `(Get-CSOnlinePSTNUsage).usage` 실행 한 결과를 볼 수 있습니다 (잘리지 않음).

<pre>
 testusage
 US and Canada
 International
 karlUsage
 New test env
 Tallinn Lab Sonus
 karlUsage2
 Unrestricted
 Two trunks
</pre>

**2 단계:** 비즈니스용 Skype Online의 PowerShell 세션에서 3 개 경로 (Redmond 1, 레드먼드 2, 기타 + 1)를 만들어 앞의 표에 자세히 설명 되어 있습니다. 

"Redmond 1" 경로를 만들려면 다음을 입력 합니다.

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 1" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```

반환 되는 결과:
<pre>
Identity                : Redmond 1
Priority                : 1
Description             :
NumberPattern           : ^\+1(425|206) (\d{7})$
OnlinePstnUsages        : {US and Canada}
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name                    : Redmond 1
</pre>
Redmond 2 경로를 만들려면 다음을 입력 합니다.

```PowerShell
New-CsOnlineVoiceRoute -Identity "Redmond 2" -NumberPattern "^\+1(425|206)
(\d{7})$" -OnlinePstnGatewayList sbc3.contoso.biz, sbc4.contoso.biz -Priority 2 -OnlinePstnUsages "US and Canada"
```

다른 + 1 경로를 만들려면 다음을 입력 합니다.

```PowerShell
New-CsOnlineVoiceRoute -Identity "Other +1" -NumberPattern "^\+1(\d{10})$"
-OnlinePstnGatewayList sbc5.contoso.biz, sbc6.contoso.biz -OnlinePstnUsages "US and Canada"
```

  > [!CAUTION]
  > 번호 패턴 특성의 정규식이 유효한 식 인지 확인 합니다. 이 웹 사이트를 사용 하 여 테스트할 수 있습니다.[https://www.regexpal.com](https://www.regexpal.com)

일부 경우에는 동일한 SBC에 대 한 모든 통화를 라우팅할 필요가 있습니다. -번호를 사용 하세요 (". *").

모든 통화를 동일한 SBC로 라우팅합니다.

```PowerShell
Set-CsOnlineVoiceRoute -id "Redmond 1" -NumberPattern ".*" -OnlinePstnGatewayList sbc1.contoso.biz
```

다음과 같이 옵션을 사용 하 여 `Get-CSOnlineVoiceRoute` PowerShell 명령을 실행 하 여 경로를 올바르게 구성 했는지 확인 합니다.

```PowerShell
Get-CsOnlineVoiceRoute | Where-Object {($_.priority -eq 1) -or ($_.priority -eq 2) or ($_.priority -eq 4) -Identity "Redmond 1" -NumberPattern "^\+1(425|206) (\d{7})$" -OnlinePstnGatewayList sbc1.contoso.biz, sbc2.contoso.biz -Priority 1 -OnlinePstnUsages "US and Canada"
```
다음을 반환 합니다.
<pre>
Identity            : Redmond 1 
Priority            : 1
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc1.contoso.biz, sbc2.contoso.biz}
Name            : Redmond 1
Identity        : Redmond 2 
Priority            : 2
Description     : 
NumberPattern       : ^\+1(425|206) (\d{7})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc3.contoso.biz, sbc4.contoso.biz}
Name            : Redmond 2
    
Identity        : Other +1 
Priority            : 4
Description     : 
NumberPattern       : ^\+1(\d{10})$
OnlinePstnUsages    : {US and Canada}    
OnlinePstnGatewayList   : {sbc5.contoso.biz, sbc6.contoso.biz}
Name            : Other +1
</pre>

이 예제에서 경로 "Other + 1"에 우선 순위 4가 자동으로 할당 되었습니다. 

**3 단계:** 음성 라우팅 정책 "미국 전용"을 만들고 PSTN 사용량 "미국 및 캐나다"를 정책에 추가 합니다.

비즈니스용 Skype Online의 PowerShell 세션에서 다음을 입력 합니다.

```PowerShell
New-CsOnlineVoiceRoutingPolicy "US Only" -OnlinePstnUsages "US and Canada"
```

결과는 다음 예제에 나와 있습니다.

<pre>
Identity            : Tag:US only
OnlinePstnUsages    : {US and Canada}
Description         :
RouteType           : BYOT
</pre>

**4 단계:** PowerShell을 사용 하 여 사용자 Spencer 낮은 음성 라우팅 정책에 게 부여 합니다.

비즈니스용 Skype Online의 PowerShell 세션에서 다음을 입력 합니다.

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "Spencer Low" -PolicyName "US Only"
```

다음 명령을 입력 하 여 정책 할당의 유효성을 검사 합니다.

```PowerShell
Get-CsOnlineUser "Spencer Low" | select OnlineVoiceRoutingPolicy
```

반환 되는 결과:
<pre>
OnlineVoiceRoutingPolicy
---------------------
US Only
</pre>

#### <a name="creating-a-voice-routing-policy-with-several-pstn-usages"></a>여러 PSTN 용도를 사용 하 여 음성 라우팅 정책 만들기

이전에 만든 음성 라우팅 정책은 Microsoft 통화 계획 라이선스가 사용자에 게 할당 되지 않는 이상 미국 및 캐나다의 전화 번호로만 통화 하도록 허용 합니다.

다음 예제에서는 음성 라우팅 정책 "제한 없음"을 만들 수 있습니다. 이 정책은 이전 예제에서 만든 PSTN 사용량 "미국 및 캐나다"와 새로운 PSTN 사용량 "국제"를 함께 재사용 합니다. 

이렇게 하면 SBCs sbc2.contoso.biz 및 sbc5.contoso.biz에 대 한 다른 모든 통화가 라우팅됩니다. 표시 되는 예제는 사용자 "Spencer Low"에 미국 전용 정책만 할당 하 고 "John 숲" 사용자에 게는 제한 사항에 대해 설명 합니다.

Spencer Low – 미국 및 캐나다 번호로만 허용 되는 통화. Redmond 번호 범위로 호출 하는 경우 특정 SBC 집합을 사용 해야 합니다. 통화 요금제 라이선스가 사용자에 게 할당 되지 않으면 미국 이외의 번호는 라우팅되지 않습니다.

John 숲 – 모든 번호로 전화를 걸 수 있습니다. Redmond 번호 범위로 호출 하는 경우 특정 SBC 집합을 사용 해야 합니다. 미국 이외의 번호는 sbc2.contoso.biz 및 sbc5.contoso.biz를 통해 라우팅됩니다.

![사용자 Spencer 낮음으로 지정 된 음성 라우팅 정책을 표시 합니다.](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoSpencerLow.png)

다른 모든 통화에 대해 사용자에 게 라이선스 (Microsoft 전화 시스템 및 Microsoft 호출 계획)가 둘 다 있는 경우 자동 경로가 사용 됩니다. 관리자가 만든 온라인 음성 경로의 숫자 패턴과 일치 하는 항목이 없는 경우 Microsoft 통화 요금제를 통해 라우팅합니다.

사용자에 게 Microsoft 전화 시스템만 있는 경우에는 일치 하는 규칙이 없기 때문에 통화가 끊깁니다.

![사용자에 게 할당 된 음성 라우팅 정책 표시, John 숲](media/ConfigDirectRouting-VoiceRoutingPolicyAssignedtoJohnWoods.png)

다음 표에서는 라우팅 정책 "제한 없음" 사용 현황 및 음성 경로를 요약 하 여 설명 합니다. 

|**PSTN 사용**|**음성 경로**|**번호 패턴**|**중요도**|**하더라도**|**설명**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|미국만|"Redmond 1"|^\\+ 1 (425\|206) (\d{7}) $|1|sbc1.contoso.biz<br/>sbc2.contoso.biz|호출 수신자 번호 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX의 활성 경로|
|미국만|"Redmond 2"|^\\+ 1 (425\|206) (\d{7}) $|2|sbc3.contoso.biz<br/>sbc4.contoso.biz|호출 수신자 번호 + 1 425 XXX XX XX 또는 + 1 206 XXX XX XX에 대 한 백업 경로|
|미국만|"기타 + 1"|^\\+ 1 (\d{10}) $|3|sbc5.contoso.biz<br/>sbc6>. contoso.biz|호출 수신자 번호 + 1 XXX XXX XX XX (+ 1 425 XXX xx xx 또는 + 1 206 XXX XX xx 제외)의 경로|
|국제화|국제화|\d +|4(tcp/ipv4)|sbc2.contoso.biz<br/>sbc5.contoso.biz|임의의 숫자 패턴에 대 한 라우팅 |


  > [!NOTE]
  > - 음성 라우팅 정책의 PSTN 사용량 순서는 중요 합니다. 용도는 순서 대로 적용 되며 첫 번째 사용에서 일치 하는 항목을 찾은 경우 다른 용도는 계산 되지 않습니다. Pstn 사용 "국제"는 PSTN 사용량 "미국 전용" 뒤에 배치 해야 합니다. PSTN 사용량의 순서를 변경 하려면 `Set-CSOnlineVoiceRoutingPolicy` 명령을 실행 합니다. <br/>예를 들어 "미국 및 캐나다"의 순서와 역순으로 "국제" 초를 순서 대로 변경 하려면 다음을 실행 합니다.<br/> `Set-CsOnlineVoiceRoutingPolicy -id tag:"no Restrictions" -OnlinePstnUsages @{Replace="International", "US and Canada"}`
 > - "기타 + 1" 및 "국제" 음성 경로에 대 한 우선 순위는 자동으로 지정 됩니다. "Redmond 1" 및 "Redmond 2" 보다 우선 순위가 낮은 경우에는 중요 하지 않습니다.

#### <a name="example-of-voice-routing-policy-for-user-john-woods"></a>사용자 John 숲에 대 한 음성 라우팅 정책의 예

PSTN 사용 "국제", 음성 경로 "국제" 음성 라우팅 정책 "제한 사항 없음"을 만들고 "John 숲" 사용자에 게 할당 하는 단계는 다음과 같습니다.   


**1 단계**: PSTN 사용량 "국제"를 만듭니다. 

비즈니스용 Skype Online의 원격 PowerShell 세션에서 다음을 입력 합니다.

```PowerShell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

**2 단계**: "국제" 새 음성 경로 만들기

```PowerShell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern ".*" -OnlinePstnGatewayList sbc2.contoso.biz, sbc5.contoso.biz -OnlinePstnUsages "International"
```
반환 되는 결과:

<pre>
Identity                  : International
Priority                  : 5
Description               :
NumberPattern             : .*
OnlinePstnUsages          : {International}
OnlinePstnGatewayList     : {sbc2.contoso.biz, sbc5.contoso.biz}
Name                      : International
</pre>

**3 단계**: 음성 라우팅 정책 "제한 없음"을 만듭니다. 

PSTN 사용 "Redmond 1" 및 "Redmond"는 전화 번호 "+ 1 425 XXX xx" 및 "+ 1 206 XXX XX XX"를 로컬 또는 온-프레미스 통화로 하는 특별 한 처리를 유지 하기 위해이 음성 라우팅 정책에 재사용 됩니다.

   ```PowerShell
   New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
   ```

PSTN 사용 순서를 기록해 둡니다.

에서. 다음 예제와 같이 구성 된 사용량으로 "+ 1 425 XXX XX"로 전화를 걸고 나면 통화는 "미국 및 캐나다" 사용에 설정 된 경로를 따르고 특별 한 라우팅 논리가 적용 됩니다. 즉, 통화가 먼저 sbc1.contoso.biz 및 sbc2.contoso.biz를 사용 하 여 라우팅된 다음 백업 경로로 sbc3.contoso.biz 및 sbc4.contoso.biz 됩니다.

b. "국제" PSTN 사용이 "미국 및 캐나다" 보다 앞에 있는 경우 + 1 425 XXX XX XX로 거는 호출은 라우팅 논리의 일부로 sbc2.contoso.biz 및 sbc5.contoso.biz로 라우팅됩니다. 명령 입력:

```PowerShell
New-CsOnlineVoiceRoutingPolicy "No Restrictions" -OnlinePstnUsages "US and Canada", "International"
```

반환 하는

<pre>
Identity              : International 
OnlinePstnUsages : {US and Canada, International}    
Description      :  
RouteType             : BYOT
</pre>

**4 단계**: 다음 명령을 사용 하 여 사용자 "John 숲"에 음성 라우팅 정책을 할당 합니다.

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity "John Woods" -PolicyName "No Restrictions”
```

그런 다음 명령을 사용 하 여 과제를 확인 합니다. 

```PowerShell
Get-CsOnlineUser "John Woods" | Select OnlineVoiceRoutingPolicy
```

반환 되는 결과:

<pre>
OnlineVoiceRoutingPolicy
------------------------
No Restrictions
</pre>

결과적으로 John 숲의 통화에 적용 되는 음성 정책에는 제한이 없으며 미국, 캐나다, 국제 통화를 위해 제공 되는 통화 라우팅의 논리에 따라 진행 됩니다.

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a>Microsoft 팀에서 전화를 걸 수 있도록 사용자에 게 팀 전용 모드 할당

다이렉트 라우팅은 팀 클라이언트에서 수신 전화를 받을 수 있도록 사용자가 팀 전용 모드에 있어야 합니다. 사용자를 팀 전용 모드로 전환 하려면 TeamsUpgradePolicy의 "UpgradeToTeams" 인스턴스를 할당 합니다. 조직에서 비즈니스용 skype Server 또는 비즈니스용 Skype Online을 사용 하는 경우 비즈니스용 [skype로 팀을 함께 사용 하는 조직의 마이그레이션 및 상호 운용성 지침](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)에 대 한 다음 문서를 참조 하세요. 

## <a name="configuring-sending-calls-directly-to-voicemail"></a>전화를 음성 메일로 바로 보내는 방법 구성

직접 라우팅을 사용 하면 사용자에 대 한 통화를 종료 하 고 사용자의 음성 메일로 바로 보낼 수 있습니다. 전화를 음성 메일로 바로 보내려면 불투명 = 앱: 보이스 메일을 요청 URI 헤더에 첨부 하세요. 예를 들어 "sip: user@yourdomain .com, 불투명 = 앱: 보이스".
이 경우 팀 사용자는 호출 알림을 받지 않게 되며, 통화는 사용자의 보이스 메일에 직접 연결 됩니다.

## <a name="translate-caller-and-callee-numbers-for-outbound-and-inbound-calls-to-an-alternate-format"></a>대체 형식에 대 한 아웃 바운드 및 인바운드 호출에 대 한 호출자 및 호출 수신자 번호를 변환 합니다.

때때로 테 넌 트 관리자가 SBCs와의 상호 운용성을 보장 하기 위해 만든 패턴에 따라 아웃 바운드 및/또는 인바운드 호출에 대 한 호출 수신자 또는 발신자 번호를 변경 하려고 할 수 있습니다. 호출 수신자 또는 발신자 번호를 대체 형식으로 변환 하도록 번호 번역 규칙 정책을 설정할 수 있습니다. 정책을 사용 하 여 다음에 대 한 숫자를 번역할 수 있습니다.

- 인바운드 통화: PSTN 끝점 (호출자)에서 팀 클라이언트 (피호출자)로 호출 합니다.
- 아웃 바운드 통화: 팀 클라이언트 (호출자)에서 PSTN 끝점 (호출 수신자)으로 호출 합니다.

정책은 SBC 수준에서 적용 됩니다. 여러 번역 규칙을 사용자가 PowerShell에 나열할 때 표시 되는 순서 대로 적용 되는 SBC에 할당할 수 있습니다. 또한 정책에서 규칙의 순서를 변경할 수 있습니다.

번호 조작 규칙을 만들고, 수정 하 고, 보고, 삭제 하려면 [New-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/new-csteamstranslationrule), [Set-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/set-csteamstranslationrule), [CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/get-csteamstranslationrule)및 [Remove-CsTeamsTranslationRule](https://docs.microsoft.com/powershell/module/skype/remove-csteamstranslationrule) cmdlet을 사용 합니다.

SBCs에 번호 조작 규칙을 할당, 구성 및 나열 하려면 [CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) 및 [Set-CSOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) ```InboundTeamsNumberTranslationRules```cmdlet을, ```InboundPSTNNumberTranslationRules``` ```OutboundTeamsNumberTranslationRules``` ```OutboundPSTNNumberTranslationRules``` ```InboundTeamsNumberTranslationRulesList``` ```InboundPSTNNumberTranslationRulesList``` ```OutboundTeamsNumberTranslationRulesList```,,,,,, ```OutboundPSTNNumberTranslationRulesList``` 매개 변수와 함께 사용 합니다.

### <a name="examples"></a>예제

#### <a name="example-sbc-configuration"></a>예제 SBC 구성

예제 시나리오의 경우 ```New-CsOnlinePSTNGateway``` cmdlet을 실행 하 여 다음 SBC 구성을 만듭니다.

```PowerShell
New-CSOnlinePSTNGateway -Identity sbc1.contoso.com -SipSignallingPort 5061 –InboundTeamsNumberTranslationRulesList ‘AddPlus1’, ‘AddE164SeattleAreaCode’ -InboundPSTNNumberTranslationRulesList ‘AddPlus1’ -OnboundPSTNNumberTranslationRulesList ‘AddSeattleAreaCode’,  -OutboundTeamsNumberTranslationRulesList ‘StripPlus1’
```

SBC에 할당 된 번역 규칙은 다음 표에 요약 되어 있습니다.

|이름  |패턴이 |변환용  |
|---------|---------|---------|
|AddPlus1     |^ (\d{10}) $          |+ 1 $1          |
|AddE164SeattleAreaCode      |^ (\d{4}) $          | + 1206555 $1         |
|AddSeattleAreaCode    |^ (\d{4}) $          | 425555 $1         |
|StripPlus1    |^ + 1 (\d{10}) $          | $1         |

이 예제 시나리오에는 Alice와 Bob 두 명의 사용자가 있습니다. Alice는 팀 사용자이 고 번호는 + 1 206 555 0100입니다. Bob은 PSTN 사용자이 고 해당 번호는 + 1 425 555 0100입니다.

#### <a name="example-1-inbound-call-to-a-ten-digit-number"></a>예제 1:10 자리 숫자에 대 한 인바운드 호출

Bob은 E 10의 164 자리 숫자를 사용 하 여 Alice를 호출 합니다. Bob이 2065550100으로 전화를 걸어 Alice에 도달 합니다.
SBC는 Urirequesturi에서 2065550100을 사용 하 고 From 헤더에는 To 헤더 및 4255550100를 사용 합니다.

|헤더  |원문 언어 |번역 된 헤더 |매개 변수 및 규칙이 적용 됨  |
|---------|---------|---------|---------|
|Urirequesturi  |Sip:2065550100@sbc.contoso.com 초대|Sip:+12065550100@sbc.contoso.com 초대|InboundTeamsNumberTranslationRulesList 'AddPlus1'|
|받는 사람    |TO: \<sip:2065550100@sbc.contoso.com>|TO: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddPlus1'|
|보낸 사람   |보낸 사람 \<: sip:4255550100@sbc.contoso.com>|보낸 사람 \<: sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranslationRulesList 'AddPlus1'|

#### <a name="example-2-inbound-call-to-a-four-digit-number"></a>예제 2:4 자리 숫자에 대 한 인바운드 호출

Bob은 네 자리 숫자를 사용 하 여 Alice를 호출 합니다. Bob이 0100으로 전화를 걸어 Alice에 도달 합니다.
SBC는 Urirequesturi에서 0100을 사용 하 고 From 헤더에는 To 헤더 및 4255550100를 사용 합니다.

|헤더  |원문 언어 |번역 된 헤더 |매개 변수 및 규칙이 적용 됨  |
|---------|---------|---------|---------|
|Urirequesturi  |Sip:0100@sbc.contoso.com 초대          |Sip:+12065550100@sbc.contoso.com 초대           |InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'        |
|받는 사람    |TO: \<sip:0100@sbc.contoso.com>|TO: \<sip:+12065550100@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList 'AddE164SeattleAreaCode'         |
|보낸 사람   |보낸 사람 \<: sip:4255550100@sbc.contoso.com>|보낸 사람 \<: sip:+14255550100@sbc.contoso.com>|InboundPSTNNumberTranlationRulesList 'AddPlus1'        |

#### <a name="example-3-outbound-call-using-a-ten-digit-non-e164-number"></a>예제 3:10 자리 비 E 1-64 번호를 사용 하는 아웃 바운드 통화

Alice가 10 자리 숫자를 사용 하 여 Bob을 호출 합니다. Alice는 425 555 0100으로 Bob에 게 전화를 겁니다.
SBC는 팀과 PSTN 사용자 모두에 대해 비 E 164 10 자리 숫자를 사용 하도록 구성 되어 있습니다.

이 시나리오에서 다이얼 플랜은 직접 라우팅 인터페이스에 전송 하기 전에 번호를 변환 합니다. Alice가 팀 클라이언트에 425 555 0100를 입력 하면 해당 번호는 국가 다이얼 플랜에 따라 + 14255550100로 변환 됩니다. 결과 번호는 다이얼 플랜 규칙 및 팀 번역 규칙의 누적 정규화입니다. 팀 번역 규칙은 다이얼 플랜에 추가 된 "+ 1"을 제거 합니다.

|헤더  |원문 언어 |번역 된 헤더 |매개 변수 및 규칙이 적용 됨  |
|---------|---------|---------|---------|
|Urirequesturi  |Sip:+14255550100@sbc.contoso.com 초대          |Sip:4255550100@sbc.contoso.com 초대       |OutboundPSTNNumberTranlationRulesList 'StripPlus1'         |
|받는 사람    |TO: \<sip:+14255550100@sbc.contoso.com>|TO: \<sip:4255555555@sbc.contoso.com>|OutboundPSTNNumberTranlationRulesList 'StripPlus1'       |
|보낸 사람   |보낸 사람 \<: sip:+12065550100@sbc.contoso.com>|보낸 사람 \<: sip:2065550100@sbc.contoso.com>|OutboundTeamsNumberTranlationRulesList 'StripPlus1'         |

#### <a name="example-4-outbound-call-using-a-four-digit-non-e164-number"></a>예제 4:4 자리 비 E 1-64 번호를 사용 하는 아웃 바운드 통화

Alice는 네 자리 숫자를 사용 하 여 Bob을 호출 합니다. Alice는 0100을 사용 하 여 Bob이 통화를 하거나 연락처를 사용 하 여 연락을 주고 받을 수 있습니다.
SBC 사용자의 경우 팀 사용자 및 10 자리 숫자에 대해 비 E 164 개의 4 자리 숫자를 사용 하도록 SBC를 구성 합니다. 다이얼 플랜은이 시나리오에서 적용 되지 않습니다.

|헤더  |원문 언어 |번역 된 헤더 |매개 변수 및 규칙이 적용 됨  |
|---------|---------|---------|---------|
|Urirequesturi  |Sip:0100@sbc.contoso.com 초대           |Sip:4255550100@sbc.contoso.com 초대       |InboundTeamsNumberTranlationRulesList ' AddSeattleAreaCode '         |
|받는 사람    |TO: \<sip:0100@sbc.contoso.com>|TO: \<sip:4255555555@sbc.contoso.com>|InboundTeamsNumberTranlationRulesList ' AddSeattleAreaCode '       |
|보낸 사람   |보낸 사람 \<: sip:+12065550100@sbc.contoso.com>|보낸 사람 \<: sip:2065550100@sbc.contoso.com>| InboundPSTNNumberTranlationRulesList 'StripPlus1' |

## <a name="see-also"></a>참고 항목

[직접 라우팅 계획](direct-routing-plan.md)
