---
title: 감시자 노드 테스트 사용자 및 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: '요약: 비즈니스용 Skype 서버 가상 트랜잭션에 대 한 테스트 사용자 계정 및 감시자 노드 설정을 구성 합니다.'
ms.openlocfilehash: bfbad6fbeb68100adaaee781c135531d226f43bb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150499"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>감시자 노드 테스트 사용자 및 설정 구성
 
**요약:** 비즈니스용 Skype 서버 가상 트랜잭션에 대 한 테스트 사용자 계정 및 감시자 노드 설정을 구성 합니다.
  
감시자 노드로 작동할 컴퓨터를 구성한 후에는 다음을 수행 해야 합니다.
  
1. 다음 감시자 노드에 사용할 [테스트 사용자 계정을 구성](test-users-and-settings-2019.md#testuser) 합니다. 협상 인증 방법을 사용 하는 경우에는 **get-cstestusercredential** cmdlet을 사용 하 여 이러한 테스트 계정을 감시자 노드에서 사용할 수 있도록 설정 해야 합니다.
    
2. 감시자 노드 구성 설정을 업데이트 합니다.
    
## <a name="configure-test-user-accounts"></a>테스트 사용자 계정 구성
<a name="testuser"> </a>

테스트 계정은 실제 사용자를 나타낼 필요가 없지만 유효한 Active Directory 계정 이어야 합니다. 또한 비즈니스용 Skype 서버에서 이러한 계정을 사용 하도록 설정 해야 하 고, 유효한 SIP 주소가 있어야 하며, Enterprise Voice를 사용 하도록 설정 해야 합니다 (테스트-CsPstnPeerToPeerCall 가상 트랜잭션을 사용 하는 경우). 
  
가 중 서버 인증 방법을 사용 하는 경우에는 이러한 계정이 존재 하는지 확인 하 고 별도로 구성 해야 합니다. 테스트할 각 풀에 대해 테스트 사용자를 세 명 이상 할당 해야 합니다. 협상 인증 방법을 사용 하는 경우에는 Get-cstestusercredential cmdlet 및 비즈니스용 Skype 서버 관리 셸을 사용 하 여 이러한 테스트 계정이 가상 트랜잭션과 함께 작동 하도록 해야 합니다. 다음과 같은 명령을 실행 하 여이 작업을 수행 합니다 (이러한 명령은 세 개의 Active Directory 사용자 계정이 만들어져 있고 비즈니스용 Skype 서버에 대해 이러한 계정을 사용 하도록 설정 했다고 가정 합니다.)
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"
```

SIP 주소 뿐만 아니라 사용자 이름 및 암호를 포함 해야 합니다. 암호를 포함 하지 않으면 Get-cstestusercredential cmdlet은 해당 정보를 입력 하 라는 메시지를 표시 합니다. 사용자 이름은 앞의 코드 블록에 표시 된 domain 이름 \ 사용자 name 형식을 사용 하 여 지정할 수 있습니다.
  
테스트 사용자 자격 증명이 만들어졌는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다.
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"
```

각 사용자에 대해 다음과 같은 정보가 반환 됩니다.
  
|**UserName**|**Password**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.object.  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>기본 가상 트랜잭션을 사용 하 여 기본 감시자 노드 구성

테스트 사용자를 만든 후에는 다음과 같은 명령을 사용 하 여 감시자 노드를 만들 수 있습니다.
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

이 명령은 기본 설정을 사용 하 고 기본 트랜잭션 집합을 실행 하는 새 감시자 노드를 만듭니다. 또한 새 감시자 노드는 test users watcher1@litwareinc.com, watcher2@litwareinc.com 및 watcher3@litwareinc.com를 사용 합니다. 감시자 노드가로 서버 인증을 사용 하는 경우 세 가지 테스트 계정은 Active Directory 및 비즈니스용 Skype 서버에 대해 사용 가능한 모든 유효한 사용자 계정이 될 수 있습니다. 감시자 노드가 Negotiate authentication 메서드를 사용 하는 경우에는 Get-cstestusercredential cmdlet을 사용 하 여이 사용자 계정도 감시자 노드에 대해 사용 하도록 설정 해야 합니다.
  
풀을 직접 대상으로 지정 하는 대신 대상 풀의 자동 검색이 올바르게 구성 되었는지 확인 하려면 대신 다음 단계를 사용 합니다.
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>확장 테스트 구성

공중 전화망과의 연결을 확인 하는 PSTN 테스트를 사용 하도록 설정 하려는 경우에는 감시자 노드를 설정할 때 추가 구성을 수행 해야 합니다. 먼저 비즈니스용 Skype 서버 관리 셸에서와 비슷한 명령을 실행 하 여 테스트 사용자를 PSTN 테스트 유형에 연결 해야 합니다.
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> 이 명령의 결과는 변수에 저장 해야 합니다. 이 예제에서 변수 이름은 $pstnTest입니다. 
  
다음으로, **get-cswatchernodeconfiguration** cmdlet을 사용 하 여 $pstnTest 변수에 저장 된 테스트 유형을 비즈니스용 Skype 서버 풀에 연결할 수 있습니다. 예를 들어 다음 명령은 atl-cs-001.litwareinc.com 풀에 대 한 새 감시자 노드 구성을 만들고 이전에 만든 3 개의 테스트 사용자를 추가한 다음 PSTN 테스트 유형을 추가 합니다.
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

감시자 노드 컴퓨터에 비즈니스용 Skype 서버 코어 파일과 RTCLocal 데이터베이스를 설치 하지 않은 경우에는 위의 명령이 실패 합니다. 
  
여러 음성 정책을 테스트 하려면 **new-csextendedtest** cmdlet을 사용 하 여 각 정책에 대 한 확장 테스트를 만들 수 있습니다. 제공 된 사용자는 원하는 음성 정책을 사용 하 여 구성 해야 합니다. 확장 된 테스트는 다음과 같은 쉼표 구분 기호를 사용 하 여 **get-cswatchernodeconfiguration** cmdlet으로 전달 됩니다.
  
-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}
  
**Get-cswatchernodeconfiguration** Cmdlet은 테스트 매개 변수를 사용 하지 않고 호출 했기 때문에 새 감시자 노드에 기본 가상 트랜잭션과 지정 된 확장 가상 트랜잭션만 사용할 수 있도록 설정 됩니다. 따라서 감시자 노드는 다음과 같은 구성 요소를 테스트 합니다.
  
- 등록
    
- 메시징을
    
- GroupIM
    
- P2PAV (피어 투 피어 오디오/비디오 세션)
    
- AvConference (오디오/회의)
    
- 이들의
    
- ABS (주소록 서비스)
    
- ABWQ (주소록 웹 서비스)
    
다음 구성 요소는 기본적으로 테스트 되지 않습니다.
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Exchange 통합 메시징)
    
- JoinLauncher 관리자
    
- MCXP2PIM (레거시 모바일 장치 인스턴트 메시징)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (PSTN 게이트웨이 호출, 확장 된 테스트로 지정)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>가상 트랜잭션 추가 및 제거

감시자 노드를 구성한 후에는 Get-cswatchernodeconfiguration cmdlet을 사용 하 여 노드에서 가상 트랜잭션을 추가 하거나 제거할 수 있습니다. 예를 들어 PersistentChatMessage 테스트를 감시자 노드에 추가 하려면 Add 메서드와 다음과 같은 명령을 사용 합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

테스트 이름을 쉼표로 구분 하 여 여러 테스트를 추가할 수 있습니다. 예:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

이러한 테스트 (예: DataConference) 중 하나 이상이 이미 감시자 노드에 대해 사용 하도록 설정 되어 있으면 오류가 발생 합니다. 이 경우 다음과 같은 오류 메시지가 표시 됩니다.
  
Get-cswatchernodeconfiguration: ' urn: schema: DataConference ' 키 또는 고유 id 제약 조건에 중복 된 키 시퀀스 ' Watchernode.msi executable '이 있습니다.
  
이 오류가 발생 하면 변경 내용이 적용 되지 않습니다. 이 명령은 중복 된 테스트를 제거한 후 다시 실행 해야 합니다.
  
감시자 노드에서 가상 트랜잭션을 제거 하려면 Remove 메서드를 사용 합니다. 예를 들어이 명령은 감시자 노드에서 ABWQ 테스트를 제거 합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Replace 메서드를 사용 하 여 현재 사용 가능한 모든 테스트를 하나 이상의 새 테스트로 바꿀 수 있습니다. 예를 들어 감시자 노드가 IM 테스트만 실행 하도록 하려면 다음 명령을 사용 하 여 해당 노드를 구성 하면 됩니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

이 명령을 실행 하면 IM을 제외한 지정 된 감시자 노드의 모든 가상 트랜잭션이 사용 하지 않도록 설정 됩니다.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>감시자 노드 구성 보기 및 테스트

감시자 노드에 할당 된 테스트를 보려면 다음과 같은 명령을 사용 합니다.
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

이 명령은 노드에 할당 된 가상 트랜잭션에 따라 다음과 같은 정보를 반환 합니다.
  
등록 메신저 GroupIM P2PAV AvConference 현재 상태 PersistentChatMessage DataConference
> [!TIP]
> 사전순으로 가상 트랜잭션을 보려면 다음 명령을 대신 사용 합니다. 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

감시자 노드가 만들어졌는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 합니다.
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

그러면 다음과 같은 정보가 반환 됩니다.
  
Id: atl-cs-001.litwareinc.com TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...} ExtendedTests: {TestUsers = IList<System.string>; 이름 = PSTN 테스트; Te ...} TargetFqdn: atl-cs-001.litwareinc.com PortNumber: 5061To 노드가 올바르게 구성 되었는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 합니다.
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

이 명령은 배포의 각 감시자 노드를 테스트 하 고 다음 작업이 완료 되었는지 확인 합니다.
  
- 필요한 등록자 역할이 설치 되어 있습니다.
    
- 필요한 레지스트리 키가 만들어집니다 (Get-cswatchernodeconfiguration cmdlet을 실행할 때 완료 됨).
    
- 서버에서 비즈니스용 Skype 서버의 올바른 버전을 실행 중입니다.
    
- 포트가 올바르게 구성 되어 있습니다.
    
- 할당 된 테스트 사용자에 게 필요한 자격 증명이 있습니다.
    
## <a name="managing-watcher-nodes"></a>감시자 노드 관리
<a name="testuser"> </a>

감시자 노드에서 실행 되는 가상 트랜잭션을 수정 하는 것 외에도 **get-cswatchernodeconfiguration** cmdlet을 사용 하 여 감시자 노드를 설정 및 해제 하 고, 테스트를 실행할 때 내부 웹 url 또는 외부 웹 url 중 하나를 사용 하도록 감시자 노드를 구성 하는 두 가지 중요 한 작업을 수행할 수 있습니다.
  
기본적으로 감시자 노드는 설정된 모든 가상 트랜잭션을 주기적으로 실행하도록 디자인되었습니다. 그러나 때때로 이러한 트랜잭션을 일시 중단할 수도 있습니다. 예를 들어 감시자 노드가 일시적으로 네트워크에서 연결이 해제된 경우에는 가상 트랜잭션을 실행할 이유가 없습니다. 네트워크 연결이 없으면 이러한 트랜잭션이 실패 합니다. 감시자 노드를 일시적으로 사용 하지 않도록 설정 하려면 비즈니스용 Skype 서버 관리 셸에서와 비슷한 명령을 실행 합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

이 명령은 감시자 노드 atl 감시자 001.litwareinc.com에서 가상 트랜잭션의 실행을 사용 하지 않도록 설정 합니다. 가상 트랜잭션 실행을 다시 시작하려면 Enabled 속성을 다시 True($True)로 설정합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled 속성을 사용하면 감시자 노드를 설정하거나 해제할 수 있습니다. 감시자 노드를 영구적으로 삭제하려면 **Remove-CsWatcherNodeConfiguration** cmdlet을 사용합니다.
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

이 명령은 지정 된 컴퓨터에서 모든 감시자 노드 구성 설정을 제거 하 여 해당 컴퓨터에서 가상 트랜잭션을 자동으로 실행 하지 않도록 합니다. 그러나이 명령은 System Center 에이전트 파일 또는 비즈니스용 Skype 서버 시스템 파일은 제거 하지 않습니다.
  
기본적으로 감시자 노드는 테스트를 수행할 때 조직의 외부 웹 Url을 사용 합니다. 그러나 조직의 내부 웹 Url을 사용 하도록 감시자 노드를 구성할 수도 있습니다. 이렇게 하면 관리자가 경계 네트워크 내부에 있는 사용자에 대한 URL 액세스를 확인할 수 있습니다. 외부 Url 대신 내부 Url을 사용 하도록 감시자 노드를 구성 하려면 UseInternalWebURls 속성을 True ($True)로 설정 합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

이 속성을 False ($False)로 다시 설정 하면 감시자가 다음에 외부 Url을 다시 사용 하 게 됩니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>가상 트랜잭션에 대한 특별 설치 지침
<a name="special_synthetictrans"> </a>

대부분의 가상 트랜잭션은 감시자 노드에서 그대로 실행 될 수 있습니다. 대부분의 경우에는 가상 트랜잭션이 감시자 노드 구성 설정에 추가 되는 즉시, 감시자 노드는 해당 테스트 가공 패스 중에 해당 가상 트랜잭션을 사용 하 여 시작할 수 있습니다. 그러나 다음 섹션에서 설명 하는 것 처럼 특별 한 설치 지침이 필요한 몇 가지 가상 트랜잭션이 있습니다.
  
### <a name="data-conferencing-synthetic-transaction"></a>데이터 회의 가상 트랜잭션

감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 먼저 Windows Internet Explorer를 사용 하지 않도록 설정 하 고 네트워크에 대 한 Internet browser 프록시 설정® 않으면 데이터 회의 가상 트랜잭션을 실행할 수 없게 됩니다. 서비스 계정 다음 단계를 완료 합니다.
  
1. 감시자 노드 컴퓨터에서 **시작**, **모든 프로그램**, **보조 프로그램**을 차례로 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.
    
2. 콘솔 창에서 다음 명령을 입력 하 고 enter 키를 누릅니다. 
    
```PowerShell
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

명령 창에 다음과 같은 메시지가 표시 됩니다.
  
BITSAdmin은 더 이상 사용 되지 않으며 향후 버전의 Windows에서 사용할 수 없습니다. Bits 서비스용 관리 도구가 이제 BITS PowerShell cmdlet에 의해 제공 됩니다.
  
계정 NetworkService에 대 한 인터넷 프록시 설정이 NO_PROXY로 설정 됩니다. 
  
(connection = default)
  
이 메시지는 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 사용 하지 않도록 설정 했음을 나타냅니다.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange 통합 메시징 가상 트랜잭션

Exchange UM (통합 메시징) 가상 트랜잭션은 테스트 사용자가 Exchange에서 홈에 있는 음성 메일 계정에 연결할 수 있는지 확인 합니다.
  
테스트 사용자는 음성 메일 계정을 사용 하 여 미리 구성 해야 합니다. 
  
### <a name="persistent-chat-synthetic-transaction"></a>영구 채팅 가상 트랜잭션

영구 채팅 가상 트랜잭션을 사용 하려면 먼저 채널을 만들고 사용자에 게이를 사용 하기 위한 권한을 부여 해야 합니다.
  
영구 채팅 가상 트랜잭션을 사용 하 여이 채널을 구성할 수 있습니다. 
  
```PowerShell
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

이 설치 작업을 실행 해야 하는 경우 엔터프라이즈 내에서 실행 해야 합니다.
  
- 서버 이외의 시스템에서 실행 하는 경우 cmdlet을 실행 하는 사용자는 RBAC (역할 기반 액세스 제어)에 대 한 CsPersistentChatAdministrators 역할의 구성원 이어야 합니다.
    
- 서버 자체에서 실행 하는 경우 cmdlet을 실행 하는 사용자는 RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN 피어 투 피어 통화 가상 트랜잭션

테스트-CsPstnPeerToPeerCall 가상 트랜잭션은 공중 전화망 (PSTN)을 통해 전화를 걸거나 받을 수 있는지 확인 합니다.
  
이 가상 트랜잭션을 실행 하려면 다음을 구성 해야 합니다.
  
- UC를 사용 하는 두 테스트 사용자 (발신자 및 수신자)
    
- 각 사용자 계정에 대한 DID(Direct Inward Dialing) 번호
    
- 전화 번호에 대 한 통화가 PSTN 게이트웨이에 도달할 수 있도록 하는 VoIP 정책 및 음성 경로
    
- 전화를 건 번호에 따라 통화를 수신자의 홈 풀로 다시 라우팅하는 통화 및 미디어를 허용 하는 PSTN 게이트웨이
    
### <a name="unified-contact-store-synthetic-transaction"></a>통합 연락처 저장소 가상 트랜잭션

통합 연락처 저장소 가상 트랜잭션은 Exchange에서 사용자를 대신 하 여 연락처를 검색 하는 비즈니스용 Skype 서버의 기능을 확인 합니다.
  
이 가상 트랜잭션을 사용하려면 다음 조건을 충족해야 합니다.
  
- Lyss-Exchange server to server authentication을 구성 해야 합니다.
    
- 테스트 사용자에 게 유효한 Exchange 사서함이 있어야 합니다.
    
이러한 조건이 충족 되 면 다음 Windows PowerShell cmdlet을 실행 하 여 테스트 사용자의 연락처 목록을 Exchange로 마이그레이션할 수 있습니다.
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

테스트 사용자 연락처 목록을 Exchange로 마이그레이션하는 데 다소 시간이 걸릴 수 있습니다. 마이그레이션 진행 상황을 모니터링 하기 위해-Setup 플래그 없이도 동일한 명령줄을 실행할 수 있습니다.
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

마이그레이션이 완료 된 후이 명령줄은 성공 합니다.
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 가상 트랜잭션

XMPP (Extensible Messaging and 현재 상태 프로토콜) IM 가상 트랜잭션을 사용 하려면 하나 이상의 페더레이션 도메인을 사용 하 여 XMPP 기능을 구성 해야 합니다.
  
XMPP 가상 트랜잭션을 사용 하도록 설정 하려면 라우팅 가능한 XMPP 도메인에서 사용자 계정에 XmppTestReceiverMailAddress 매개 변수를 제공 해야 합니다. 예:
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

이 예에서는 litwareinc.com에 대 한 메시지를 XMPP 게이트웨이로 라우팅하기 위해 비즈니스용 Skype 서버 규칙이 있어야 합니다.

> [!NOTE]
> XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만 비즈니스용 Skype 서버 2019에서는 더 이상 지원 되지 않습니다. 자세한 내용은 [XMPP 페더레이션 마이그레이션을](../migration/migrating-xmpp-federation.md) 참조 하세요.
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>VIS (동영상 Interop 서버) 가상 트랜잭션

VIS (동영상 Interop 서버) 가상 트랜잭션을 사용 하려면 가상 트랜잭션 지원 파일 ([VISSTSupportPackage](https://www.microsoft.com/download/details.aspx?id=46921))을 다운로드 하 여 설치 해야 합니다. 
  
VISSTSupportPackage을 설치 하려면 msi에 대 한 종속성 (시스템 요구 사항에 따라)이 이미 설치 되어 있는지 확인 합니다. VISSTSupportPackage를 실행 하 여 단순 설치를 수행 합니다. .Msi는 "%ProgramFiles%\VIS 가상 트랜잭션 지원 패키지" 경로의 모든 파일을 설치 합니다.
  
VIS 가상 트랜잭션을 실행 하는 방법에 대 한 자세한 내용은 [CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/library/dn985894.aspx) cmdlet에 대 한 설명서를 참조 하십시오.
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>가상 트랜잭션에 대 한 실행 빈도 변경
<a name="special_synthetictrans"> </a>

기본적으로 구성 된 사용자가 15 분 마다 가상 트랜잭션이 실행 됩니다. 가상 트랜잭션은 사용자 집합 내에서 순차적으로 실행 되어 두 가상 트랜잭션이 서로 충돌 하지 않도록 합니다. 모든 가상 트랜잭션이 완료 될 때 까지의 시간을 제공 하기 위해 더 긴 간격이 필요 합니다.
  
가상 트랜잭션을 더 자주 실행 하는 것이 바람직한 경우에는 지정 된 사용자 집합을 사용 하 여 실행 되는 가상 트랜잭션 수를 줄여야 하 여 테스트를 가끔씩 발생 하는 네트워크 지연에 대 한 일부 버퍼와 함께 원하는 시간 범위에서 완료할 수 있도록 해야 합니다. 더 많은 가상 트랜잭션을 실행 하는 것이 바람직한 경우 추가 가상 트랜잭션을 실행할 사용자 집합을 더 많이 만듭니다.
  
가상 트랜잭션을 실행 하는 빈도를 변경 하려면 다음 단계를 수행 합니다.
  
1. System Center Operations Manager를 엽니다. 제작 섹션을 클릭 합니다. 규칙 섹션 (제작 중)을 클릭 합니다.
    
2. 규칙 섹션에서 이름이 "Main 종합 Transaction 러너 성능 수집 규칙" 인 규칙을 찾습니다.
    
3. 규칙을 마우스 오른쪽 단추로 클릭 하 고 재정의를 선택한 다음 규칙 재정의를 선택 하 고, "클래스의 모든 개체: 풀 감시자"를 선택 합니다.
    
4. 속성 재정의 창에서 매개 변수 이름 "Frequency"를 선택 하 고 재정의 값을 원하는 항목으로 설정 합니다.
    
5. 같은 창에서이 재정의를 적용 해야 하는 관리 팩을 선택 합니다.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>가상 트랜잭션에 고급 로깅 사용
<a name="special_synthetictrans"> </a>

가상 트랜잭션은 시스템에서 발생 하는 문제를 파악 하는 데 매우 유용 합니다. 예를 들어, 테스트-CsRegistration cmdlet은 사용자가 비즈니스용 Skype 서버에 등록 하는 데 어려움을 겪고 있음을 관리자에 게 알릴 수 있습니다. 그러나 실제 실패 원인을 확인 하려면 추가 정보가 필요할 수도 있습니다.
  
따라서 가상 트랜잭션은 다양 한 로깅을 제공 합니다. 가상 트랜잭션이 undertakes 하는 각 활동에 대해 풍부한 로깅을 사용 하면 다음과 같은 정보가 기록 됩니다.
  
- 활동이 시작 된 시간입니다.
    
- 활동을 완료 한 시간입니다.
    
- 수행 된 작업 (예: 회의 만들기, 참가 또는 탈퇴, 비즈니스용 Skype 서버에 로그인, 인스턴트 메시지 보내기)
    
- 활동 실행 시 생성된 정보, 자세한 정보, 경고 또는 오류 메시지
    
- SIP 등록 메시지입니다.
    
- 활동을 실행할 때 생성 되는 예외 레코드 또는 진단 코드입니다.
    
- 활동을 실행 했을 때의 네트워크 결과입니다.
    
이 정보는 가상 트랜잭션을 실행할 때마다 자동으로 생성 되지만 로그 파일에 자동으로 표시 되거나 저장 되지 않습니다. 가상 트랜잭션을 수동으로 실행 하는 경우에는 OutLoggerVariable 매개 변수를 사용 하 여 정보가 저장 될 Windows PowerShell 변수를 지정할 수 있습니다. 여기서는 두 가지 방법 중 하나를 사용 하 여 XML 또는 HTML 형식의 리치 로그에서 오류 메시지를 저장 및/또는 볼 수 있습니다. 
  
문제 해결 정보를 검색 하려면 OutLoggerVariable 매개 변수를 지정한 다음 선택한 변수 이름을 입력 합니다.
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> : 변수 이름 앞에 $ 문자를 사용 하지 않습니다. $RegistrationTest 아닌 RegistrationTest와 같은 변수 이름을 사용 합니다. 
  
이 명령을 실행 하면 다음과 같은 출력이 표시 됩니다.
  
대상 Fqdn: atl-cs-001.litwareinc.com Result: 실패 한 대기 시간: 00:00:00 오류 메시지:이 컴퓨터에는 할당 된 인증서가 없습니다. 진단:이 오류에 대 한 보다 자세한 정보는 여기에 표시 된 것 처럼 액세스할 수 있습니다. HTML 형식으로이 정보에 액세스 하려면 다음과 비슷한 명령을 사용 하 여 변수 RegistrationTest에 저장 된 정보를 HTML 파일에 저장 합니다.
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

또는 ToXML() 메서드를 사용하여 데이터를 XML 파일에 저장할 수도 있습니다.
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Windows Internet Explorer, Microsoft Visual Studio 또는 HTML/XML 파일을 열 수 있는 기타 응용 프로그램을 사용 하 여 이러한 파일을 볼 수 있습니다.
  
System Center Operations Manager 내부에서 실행 되는 가상 트랜잭션은 오류에 대 한 이러한 로그 파일을 자동으로 생성 합니다. 비즈니스용 Skype 서버 PowerShell에서 가상 트랜잭션을 로드 하 고 실행할 수 있으려면 실행이 실패 하는 경우이 로그가 생성 되지 않습니다. 
  
> [!IMPORTANT]
> 기본적으로 비즈니스용 Skype 서버는 공유 되지 않는 폴더에 로그 파일을 저장 합니다. 이러한 로그에 쉽게 액세스할 수 있도록 하려면이 폴더를 공유 해야 합니다. 예: \\atl-litwareinc. com\WatcherNode. 
