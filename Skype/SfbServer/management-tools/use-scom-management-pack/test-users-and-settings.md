---
title: 감시자 노드 테스트 사용자 및 설정을 구성하는 방법
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ab2e0d93-cf52-4a4e-b5a4-fd545df7a1a9
description: 가상 트랜잭션에 대한 테스트 사용자 계정 및 감시자 노드 비즈니스용 Skype 서버 방법
ms.openlocfilehash: 2be4b8aef73def9f9fee11e3469eae93b83393ff
ms.sourcegitcommit: f3c2559a89e1c4b3514e102cf94c38a697b4bc57
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2021
ms.locfileid: "53724781"
---
# <a name="how-to-configure-watcher-node-test-users-and-settings"></a>감시자 노드 테스트 사용자 및 설정을 구성하는 방법
 
**요약:** 가상 트랜잭션에 대한 테스트 사용자 계정 및 감시자 비즈니스용 Skype 서버 구성합니다.
  
감시자 노드로 사용할 컴퓨터를 구성한 후 다음을 해야 합니다.
  
1. [이러한 감시자 노드에서](test-users-and-settings.md#testuser) 사용할 테스트 사용자 계정을 구성합니다. 협상 인증 방법을 사용하는 경우 **Set-CsTestUserCredential** cmdlet을 사용하여 이러한 테스트 계정을 감시자 노드에서 사용할 수 있도록 설정해야 합니다.
    
2. 감시자 노드 구성 설정을 업데이트합니다.
    
## <a name="configure-test-user-accounts"></a>테스트 사용자 계정 구성
<a name="testuser"> </a>

테스트 계정은 실제 사용자만 나타내는 것은 아니며 유효한 Active Directory 계정이 되어야 합니다. 또한 이러한 계정은 비즈니스용 Skype 서버 사용할 수 있어야 합니다. 또한 유효한 SIP 주소가 있어야 합니다. 가상 트랜잭션을 사용하려면 Enterprise Voice 사용하도록 설정해야 Test-CsPstnPeerToPeerCall 있습니다. 
  
TrustedServer 인증 방법을 사용하는 경우 이러한 계정이 있는지 확인하여 다음에 따라 구성하기만하면 됩니다. 테스트할 각 풀에 대해 두 개 이상의 테스트 사용자를 할당합니다. 협상 인증 방법을 사용하는 경우 Set-CsTestUserCredential 및 비즈니스용 Skype 서버 관리 셸을 사용하여 이러한 테스트 계정이 가상 트랜잭션에서 작동하도록 해야 합니다. 이 작업을 실행하기 위해 다음과 같은 명령을 실행합니다. 이 명령은 두 개의 Active Directory 사용자 계정이 만들어졌다고 가정하며 이러한 계정이 비즈니스용 Skype 서버.
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

SIP 주소뿐만 아니라 사용자 이름과 암호도 포함해야 합니다. 암호를 포함하지 않는 경우 Set-CsTestUserCredential cmdlet에 해당 정보를 입력하라는 메시지가 나타날 수 있습니다. 이전 코드 블록에 표시된 도메인 이름\사용자 이름 형식을 사용하여 사용자 이름을 지정할 수 있습니다.
  
테스트 사용자 자격 증명이 만들어졌다는 확인을 위해 관리 셸의 비즈니스용 Skype 서버 실행합니다.
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

각 사용자에 대해 다음과 비슷한 정보가 반환됩니다.
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.Security.SecureString  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>기본 가상 트랜잭션을 통해 기본 감시자 노드 구성

테스트 사용자를 만든 후 다음 명령과 유사한 명령을 사용하여 감시자 노드를 만들 수 있습니다.
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

이 명령은 기본 설정을 사용하는 새 감시자 노드를 만들고 기본 가상 트랜잭션 집합을 실행합니다. 또한 새 감시자 노드는 테스트 사용자 및 watcher1@litwareinc.com watcher2@litwareinc.com. 감시자 노드에서 TrustedServer 인증을 사용하는 경우 두 테스트 계정은 Active Directory 및 Active Directory에 대해 사용하도록 설정된 유효한 사용자 계정이 비즈니스용 Skype 서버. 감시자 노드에서 협상 인증 방법을 사용하는 경우 감시자 노드에 대해 이러한 사용자 계정도 이 cmdlet을 사용하여 Set-CsTestUserCredential 합니다.
  
풀을 직접 대상으로 지정하는 대신 로그인할 대상 풀의 자동 검색이 올바르게 구성되어 있는지 확인하려면 다음 단계를 대신 사용합니다.
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>확장 테스트 구성

PSTN 테스트를 사용하도록 설정하여 공용 전화망과의 연결을 확인하려면 감시자 노드를 설정할 때 몇 가지 추가 구성을 해야 합니다. 먼저 사용자 관리 셸에서 이와 유사한 명령을 실행하여 테스트 사용자를 PSTN 테스트 유형과 비즈니스용 Skype 서버 합니다.
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> 이 명령의 결과는 변수에 저장해야 합니다. 이 예제에서는 변수의 이름이 $pstnTest. 
  
그런 다음 **New-CsWatcherNodeConfiguration** cmdlet을 사용하여 테스트 유형(변수 $pstnTest에 저장)을 비즈니스용 Skype 서버 있습니다. 예를 들어 다음 명령은 이전에 만든 두 테스트 사용자를 추가하고 atl-cs-001.litwareinc.com PSTN 테스트 유형을 추가하는 풀 풀에 대한 새 감시자 노드 구성을 만듭니다.
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

감시자 노드 컴퓨터에 비즈니스용 Skype 서버 RTCLocal 데이터베이스를 설치하지 않은 경우 위의 명령이 실패합니다. 
  
여러 음성 정책을 테스트하기 위해 **New-CsExtendedTest** cmdlet을 사용하여 각 정책에 대한 확장 테스트를 만들 수 있습니다. 제공된 사용자는 원하는 음성 정책으로 구성해야 합니다. 확장 테스트는 **New-CsWatcherNodeConfiguration** cmdlet에 comma-delimiters를 사용하여 다음을 통해 전달됩니다.
  
-ExtendedTests @{Add=$pstnTest 1,$pstnTest 2,$pstnTest 3}
  
Tests 매개 변수를 사용하지 않고 **New-CsWatcherNodeConfiguration** cmdlet을 호출하기 때문에 새 감시자 노드에 대해 기본 가상 트랜잭션 및 지정된 확장 가상 트랜잭션만 사용하도록 설정됩니다. 따라서 감시자 노드는 다음 구성 요소를 테스트합니다.
  
- 등록
    
- IM
    
- GroupIM
    
- P2PAV(피어 투 피어 오디오/비디오 세션)
    
- AvConference(오디오/회의)
    
- 현재 상태
    
- ABS(주소장 서비스)
    
- ABWQ(주소 예약 웹 서비스)
    
다음 구성 요소는 기본적으로 테스트되지 않습니다.
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity(Exchange 통합 메시징)
    
- JoinLauncher
    
- MCXP2PIM(레거시 모바일 장치 인스턴트 메시징)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN(확장 테스트로 지정된 PSTN 게이트웨이 통화)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>가상 트랜잭션 추가 및 제거

감시자 노드를 구성한 후 Set-CsWatcherNodeConfiguration cmdlet을 사용하여 노드에서 가상 트랜잭션을 추가하거나 제거할 수 있습니다. 예를 들어 PersistentChatMessage 테스트를 감시자 노드에 추가하기 위해 Add 메서드 및 다음과 같은 명령을 사용합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

테스트 이름을 콤보로 구분하여 여러 테스트를 추가할 수 있습니다. 예를 들면
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

이러한 테스트 중 하나 이상(예: DataConference)이 감시자 노드에서 이미 활성화된 경우 오류가 발생합니다. 이 경우 다음과 같은 오류 메시지가 표시됩니다.
  
Set-CsWatcherNodeConfiguration : 'urn:schema:Microsoft.Rtc.Management'에 대한 중복 키 시퀀스 'DataConference'가 있습니다. 설정. WatcherNode.2010:TestName' 키 또는 고유 ID 제약 조건입니다.
  
이 오류가 발생하면 변경 내용이 적용되지 않습니다. 중복 테스트를 제거한 후 명령을 다시 실행해야 합니다.
  
감시자 노드에서 가상 트랜잭션을 제거하려면 Remove 메서드를 사용합니다. 예를 들어 다음 명령은 감시자 노드에서 ABWQ 테스트를 제거합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Replace 메서드를 사용하여 현재 사용하도록 설정된 모든 테스트를 하나 이상의 새 테스트로 바꿀 수 있습니다. 예를 들어 감시자 노드가 IM 테스트만 실행하도록 하려는 경우 다음 명령을 사용하여 구성할 수 있습니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

이 명령을 실행하면 지정된 감시자 노드의 모든 가상 트랜잭션이 IM을 제외하고 사용하지 않도록 설정됩니다.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>감시자 노드 구성 보기 및 테스트

감시자 노드에 할당된 테스트를 확인하려는 경우 다음 명령을 사용 합니다.
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

이 명령은 노드에 할당된 가상 트랜잭션에 따라 이와 유사한 정보를 반환합니다.
  
Registration IM GroupIM P2PAV AvConference Presence PersistentChatMessage DataConference
> [!TIP]
> 가상 트랜잭션을 사전순으로 보시다가 다음 명령을 대신 사용합니다. 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

감시자 노드가 만들어졌다는 확인을 위해 관리 셸의 비즈니스용 Skype 서버 입력합니다.
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

이와 유사한 정보를 얻게 됩니다.
  
ID : atl-cs-001.litwareinc.com <br/>
TestUsers : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}<br/>
ExtendedTests : {TestUsers=IList<System.String>; Name=PSTN Test; Te...}<br/>
TargetFqdn : atl-cs-001.litwareinc.com<br/>
PortNumber : 5061<br/>

감시자 노드가 올바르게 구성되어 있는지 확인하려면 관리 셸의 비즈니스용 Skype 서버 입력합니다.
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

이 명령은 배포의 각 감시자 노드를 테스트하고 다음 작업이 완료된지 여부를 검사합니다.
  
- 필수 등록자 역할이 설치됩니다.
    
- 필수 레지스트리 키가 만들어집니다(cmdlet을 Set-CsWatcherNodeConfiguration 완료).
    
- 서버에서 올바른 버전의 클라이언트를 비즈니스용 Skype 서버.
    
- 포트가 올바르게 구성되었습니다.
    
- 할당된 테스트 사용자에게는 필수 자격 증명이 있습니다.
    
## <a name="managing-watcher-nodes"></a>감시자 노드 관리
<a name="testuser"> </a>

감시자 노드에서 실행되는 가상 트랜잭션을 수정하는 것 외에도 **Set-CsWatcherNodeConfiguration** cmdlet을 사용하여 감시자 노드를 설정 및 사용하지 않습니다. 그리고 테스트를 실행할 때 내부 웹 URL 또는 외부 웹 URL을 사용하도록 감시자 노드를 구성하는 등 두 가지 중요한 작업을 수행할 수 있습니다.
  
기본적으로 감시자 노드는 설정된 모든 가상 트랜잭션을 주기적으로 실행하도록 디자인되었습니다. 그러나 이러한 트랜잭션을 일시 중단할 수도 있습니다. 예를 들어 감시자 노드가 일시적으로 네트워크에서 연결이 해제된 경우에는 가상 트랜잭션을 실행할 이유가 없습니다. 네트워크 연결이 없는 경우 해당 트랜잭션이 실패합니다. 감시자 노드를 일시적으로 사용하지 않도록 설정하기 위해 관리 셸에서 비즈니스용 Skype 서버 실행합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

이 명령은 감시자 노드 atl 감시자 노드에서 가상 트랜잭션을 실행하지 않도록 001.litwareinc.com. 가상 트랜잭션 실행을 다시 시작하려면 Enabled 속성을 다시 True($True)로 설정합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled 속성을 사용하면 감시자 노드를 설정하거나 해제할 수 있습니다. 감시자 노드를 영구적으로 삭제하려면 **Remove-CsWatcherNodeConfiguration** cmdlet을 사용합니다.
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

이 명령은 지정된 컴퓨터에서 모든 감시자 노드 구성 설정을 제거하여 해당 컴퓨터가 가상 트랜잭션을 자동으로 실행하지 못하게 합니다. 그러나 이 명령은 System Center 파일 또는 시스템 비즈니스용 Skype 서버 않습니다.
  
기본적으로 감시자 노드는 테스트를 수행 할 때 조직의 외부 웹 URL을 사용 합니다. 그러나 조직의 내부 웹 URL을 사용하도록 감시자 노드를 구성할 수도 있습니다. 이렇게 하면 관리자가 경계 네트워크 내부에 있는 사용자에 대한 URL 액세스를 확인할 수 있습니다. 외부 URL 대신 내부 URL을 사용하도록 감시자 노드를 구성하기 위해 UseInternalWebURls 속성을 True($True) 설정하세요.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

이 속성을 기본값 False($False)로 다시 설정하면 감시자는 외부 URL을 다시 사용하게 됩니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>가상 트랜잭션에 대한 특별 설치 지침
<a name="special_synthetictrans"> </a>

대부분의 가상 트랜잭션은 감시자 노드에서 있는 동안 실행할 수 있습니다. 대부분의 경우 가상 트랜잭션이 감시자 노드 구성 설정에 추가되는 즉시 감시자 노드는 테스트 통과 중에 해당 가상 트랜잭션 사용을 시작할 수 있습니다. 그러나 다음 섹션에 설명된 특정 설치 지침이 필요한 일부 가상 트랜잭션이 있습니다.
  
### <a name="data-conferencing-synthetic-transaction"></a>데이터 회의 가상 트랜잭션

감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 다음 단계를 완료하여 네트워크 서비스 계정에 대한 Windows Internet Explorer® 인터넷 브라우저 프록시 설정을 먼저 사용하지 않도록 설정하지 않는 한 데이터 회의 가상 트랜잭션을 실행할 수 없습니다.
  
1. 감시자 노드 컴퓨터에서 **시작**, **모든 프로그램**, **보조프로그램** 을 차례로 클릭하고 **명령 프롬프트** 를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행** 을 클릭합니다.
    
2. 콘솔 창에서 다음 명령을 입력하고 Enter를 클릭합니다. 
    
    ```console
    bitsadmin /util /SetIEProxy NetworkService NO_PROXY
    ```

    명령 창에 다음 메시지가 표시됩니다.

    ```console
    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
  
    Internet proxy settings for account NetworkService set to NO_PROXY. 
      
    (connection = default)
    ```
      
    이 메시지는 네트워크 서비스 계정에 대한 Internet Explorer 프록시 설정을 사용하지 않도록 설정했다는 메시지를 나타냅니다.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange 통합 메시징 가상 트랜잭션

Exchange UM(통합 메시징) 가상 트랜잭션은 테스트 사용자가 UM에 있는 음성메일 계정에 연결할 수 Exchange.
  
테스트 사용자는 음성메일 계정으로 미리 구성해야 합니다. 
  
### <a name="persistent-chat-synthetic-transaction"></a>영구 채팅 가상 트랜잭션

영구 채팅 가상 트랜잭션을 사용하려면 먼저 채널을 만들고 테스트 사용자에게 해당 트랜잭션을 사용할 수 있는 권한을 부여해야 합니다.
  
영구 채팅 가상 트랜잭션을 사용하여 이 채널을 구성할 수 있습니다. 
  
```powershell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

이 설치 작업을 실행하려면 엔터프라이즈 내에서 실행해야 합니다.
  
- 서버가 아닌 컴퓨터로부터 실행되는 경우 cmdlet을 실행하는 사용자는 RBAC(액세스 제어)에 대한 CsPersistentChatAdministrators 역할의 Role-Based 있어야 합니다.
    
- 서버 자체에서 실행하는 경우 cmdlet을 실행하는 사용자는 RTCUniversalServerAdmins 그룹의 구성원이 되어야 합니다.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN 피어 투 피어 통화 가상 트랜잭션

가상 Test-CsPstnPeerToPeerCall PSTN(전화망)을 통해 통화를 걸고 받을 수 있는 기능을 확인합니다.
  
이 가상 트랜잭션을 실행하려면 다음을 구성해야 합니다.
  
- UC 사용 테스트 사용자 2명(발신자 및 수신자)
    
- 각 사용자 계정에 대한 DID(Direct Inward Dialing) 번호
    
- 수신자 번호로 걸린 통화가 PSTN 게이트웨이에 연결될 수 있도록 하는 VoIP 정책 및 음성 경로입니다.
    
- 전화를 거는 번호를 기준으로 수신자 홈 풀로 통화를 다시 라우팅하는 통화 및 미디어를 허용하는 PSTN 게이트웨이입니다.
    
### <a name="unified-contact-store-synthetic-transaction"></a>통합 연락처 저장소 가상 트랜잭션

통합 연락처 저장소 가상 트랜잭션은 사용자 대신 비즈니스용 Skype 서버 연락처를 검색할 수 있는 기능을 Exchange.
  
이 가상 트랜잭션을 사용하려면 다음 조건을 충족해야 합니다.
  
- Lyss-Exchange 서버 인증을 구성해야 합니다.
    
- 테스트 사용자는 사서함에 유효한 Exchange 있어야 합니다.
    
이러한 조건이 충족된 후 다음 Windows PowerShell cmdlet을 실행하여 테스트 사용자의 연락처 목록을 Exchange.
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

테스트 사용자 연락처 목록이 사용자 연락처 목록으로 마이그레이션되는 데 다소 시간이 걸릴 Exchange. 마이그레이션 진행률을 모니터링하기 위해 -Setup 플래그 없이 동일한 명령줄을 실행할 수 있습니다.
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

이 명령줄은 마이그레이션이 완료된 후에 성공합니다.
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 가상 트랜잭션

XMPP(Extensible Messaging and Presence Protocol) IM 가상 트랜잭션을 사용하려면 하나 이상의 페더럴 도메인으로 XMPP 기능을 구성해야 합니다.
  
XMPP 가상 트랜잭션을 사용하도록 설정하려면 라우팅 가능한 XMPP 도메인의 사용자 계정으로 XmppTestReceiverMailAddress 매개 변수를 제공해야 합니다. 예를 들면
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

이 예에서는 비즈니스용 Skype 서버 대한 메시지를 XMPP 게이트웨이로 litwareinc.com 규칙이 존재해야 합니다.

> [!NOTE]
> XMPP 게이트웨이 및 xxies는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서 더 이상 지원되지 않습니다. 자세한 내용은 [Migrating XMPP federation 을 참조하십시오.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>VIS(Video Interop Server) 가상 트랜잭션

VIS(Video Interop Server) 가상 트랜잭션을 사용하려면 가상 트랜잭션 지원[ 파일(VISSTSupportPackage.msi)을 다운로드하여 설치해야 ](https://www.microsoft.com/download/details.aspx?id=46921)합니다. 
  
이 VISSTSupportPackage.msi msi에 대한 종속성(시스템 요구 사항 아래)이 이미 설치되어 있는지 확인합니다. 간단한 VISSTSupportPackage.msi 실행합니다. 이 .msi 경로에 있는 모든 파일을 설치합니다. "%ProgramFiles%\VIS Synthetic Transaction Support Package".
  
VIS 가상 트랜잭션을 실행하는 방법에 대한 자세한 내용은 [Test-CsP2PVideoInteropServerSipTrunkAV](/powershell/module/skype/Test-CsP2PVideoInteropServerSipTrunkAV) cmdlet에 대한 설명서를 참조하십시오.
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>가상 트랜잭션의 실행 빈도 변경
<a name="special_synthetictrans"> </a>

기본적으로 가상 트랜잭션은 구성된 사용자와 15분마다 실행됩니다. 가상 트랜잭션은 사용자 집합 내에서 시차적으로 실행되어 두 가상 트랜잭션이 서로 충돌하지 않도록 합니다. 모든 가상 트랜잭션이 완료될 시간을 제공하려면 더 긴 간격이 필요합니다.
  
가상 트랜잭션을 더 자주 실행하는 것이 바람직한 경우 특정 사용자 집합과 함께 실행되는 가상 트랜잭션 수를 줄이면 테스트가 필요한 시간 범위에서 일부 버퍼로 완료되어 네트워크 지연이 발생하는 경우도 있습니다. 더 많은 가상 트랜잭션을 실행하는 것이 바람직한 경우 더 많은 사용자 집합을 만들어 추가 가상 트랜잭션을 실행합니다.
  
가상 트랜잭션이 실행되는 빈도를 변경하기 위해 다음 단계를 수행합니다.
  
1. Operations Manager를 System Center 을 열 수 있습니다. 작성 섹션을 클릭합니다. 규칙 섹션(제작 아래)을 클릭합니다.
    
2. 규칙 섹션에서 이름이 "Main Synthetic Transaction Runner Performance Collection Rule"인 규칙을 찾아보세요.
    
3. 규칙을 마우스 오른쪽 단추로 클릭하고 다시버전을 선택하고 규칙 다시 우회를 선택한 다음 "클래스의 모든 개체: 풀 감시자"를 선택합니다.
    
4. 속성 오버라이드 창에서 매개 변수 이름 "Frequency"를 선택하고 값 1회를 원하는 값으로 설정합니다.
    
5. 같은 창에서 이 오버라이드를 적용해야 하는 관리 팩을 선택합니다.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>가상 트랜잭션에 고급 로깅 사용
<a name="special_synthetictrans"> </a>

가상 트랜잭션은 시스템 문제를 식별하는 데 매우 유용합니다. 예를 들어 Test-CsRegistration cmdlet은 사용자에게 사용자 등록에 문제가 있다는 사실을 관리자에게 비즈니스용 Skype 서버. 그러나 오류의 실제 원인을 확인하려면 더 많은 세부 정보가 필요할 수 있습니다.
  
이러한 이유로 가상 트랜잭션은 풍부한 로깅을 제공합니다. 다양한 로깅을 통해 가상 트랜잭션이 진행하는 각 활동에 대해 다음 정보가 기록됩니다.
  
- 활동이 시작된 시간입니다.
    
- 활동이 완료된 시간입니다.
    
- 수행된 작업(예: 회의 만들기, 참가 또는 나가기, 비즈니스용 Skype 서버 로그인, 인스턴트 메시지 보내기)
    
- 활동이 시작될 때 생성되는 정보, 자세한 정보, 경고 또는 오류 메시지입니다.
    
- SIP 등록 메시지입니다.
    
- 예외 레코드 또는 활동이 실행될 때 생성된 진단 코드입니다.
    
- 활동 실행의 결과입니다.
    
이 정보는 가상 트랜잭션이 실행될 때마다 자동으로 생성되지만 로그 파일에 자동으로 표시되거나 저장되지는 않습니다. 가상 트랜잭션을 수동으로 실행하는 경우 OutLoggerVariable 매개 변수를 사용하여 정보를 저장할 Windows PowerShell 변수를 지정할 수 있습니다. 두 가지 방법 중 하나를 사용하여 XML 또는 HTML 형식으로 서식 있는 로그에 오류 메시지를 저장 및/또는 볼 수 있습니다. 
  
문제 해결 정보를 검색하기 위해 OutLoggerVariable 매개 변수를 지정하고 그 다음에 선택한 변수 이름을 지정합니다.
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> 변수 이름 앞에 $ 문자를 붙이지 마십시오. RegistrationTest와 같은 변수 이름을 $RegistrationTest. 
  
이 명령을 실행하면 출력은 다음과 유사합니다.
  
대상 Fqdn : atl-cs-001.litwareinc.com 결과 : 오류 대기 시간 : 00:00:00 오류 메시지: 이 컴퓨터의 인증서가 할당되지 않았습니다. 진단 : 여기에 표시된 오류 메시지보다 이 오류에 대한 훨씬 자세한 정보에 액세스할 수 있습니다.

이 정보에 HTML 형식으로 액세스하려면 이 명령과 유사한 명령을 사용하여 RegistrationTest 변수에 저장된 정보를 HTML 파일에 저장합니다.
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

또는 ToXML() 메서드를 사용하여 데이터를 XML 파일에 저장할 수도 있습니다.
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

HTML/XML 파일을 열 수 있는 Windows Internet Explorer, Microsoft Visual Studio 응용 프로그램을 사용하여 이러한 파일을 볼 수 있습니다.
  
가상 트랜잭션은 System Center 오류에 대해 이러한 로그 파일을 자동으로 생성합니다. PowerShell에서 가상 트랜잭션을 로드하고 실행할 수 비즈니스용 Skype 서버 실행에 실패하면 이러한 로그가 생성되지 않습니다. 
  
> [!IMPORTANT]
> 기본적으로 비즈니스용 Skype 서버 공유되지 않는 폴더에 로그 파일을 저장합니다. 이러한 로그에 쉽게 액세스할 수 있도록 이 폴더를 공유해야 합니다. 예: \\ atl-watcher-001.litwareinc.com\WatcherNode.
