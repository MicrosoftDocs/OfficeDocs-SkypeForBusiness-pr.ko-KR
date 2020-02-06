---
title: 감시자 노드 테스트 사용자 및 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: '요약: 비즈니스용 Skype 서버 가상 거래에 대 한 테스트 사용자 계정 및 감시자 노드 설정을 구성 합니다.'
ms.openlocfilehash: ce0c82f6f850c7a2b632c828f938979747d99e97
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816117"
---
# <a name="configure-watcher-node-test-users-and-settings"></a>감시자 노드 테스트 사용자 및 설정 구성
 
**요약:** 비즈니스용 Skype 서버 가상 거래에 대 한 테스트 사용자 계정 및 감시자 노드 설정을 구성 합니다.
  
감시자 노드 역할을 하는 컴퓨터를 구성한 후에는 다음을 수행 해야 합니다.
  
1. 이러한 감시자 노드에서 사용할 [테스트 사용자 계정을 구성](test-users-and-settings.md#testuser) 합니다. 협상 인증 방법을 사용 하는 경우 **CsTestUserCredential** cmdlet을 사용 하 여 이러한 테스트 계정을 감시자 노드에서 사용할 수 있도록 설정 해야 합니다.
    
2. 감시자 노드 구성 설정을 업데이트 합니다.
    
## <a name="configure-test-user-accounts"></a>테스트 사용자 계정 구성
<a name="testuser"> </a>

테스트 계정은 실제 사용자를 나타낼 필요는 없지만 유효한 Active Directory 계정 이어야 합니다. 또한 이러한 계정은 비즈니스용 Skype Server에 대해 사용 하도록 설정 되어야 하 고, 유효한 SIP 주소가 있어야 하며, Enterprise Voice에서 사용할 수 있어야 합니다 (테스트-CsPstnPeerToPeerCall 가상 트랜잭션을 사용 하려면). 
  
(가) 서버 인증 방법을 사용 하는 경우에는 이러한 계정이 존재 하는지 확인 하 고 별도로 구성 해야 합니다. 테스트 하려는 각 풀에 대해 최소 두 개의 테스트 사용자를 할당 해야 합니다. 협상 인증 방법을 사용 하는 경우 CsTestUserCredential cmdlet 및 비즈니스용 Skype Server Management Shell을 사용 하 여 이러한 테스트 계정이 가상 트랜잭션과 함께 작동 하도록 설정 해야 합니다. 다음과 같은 명령을 실행 하 여이 작업을 수행 합니다 (이러한 명령은 두 Active Directory 사용자 계정이 생성 되 고이 계정이 비즈니스용 Skype Server에 대해 사용 하도록 설정 되었다고 가정).
  
```PowerShell
Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
```

SIP 주소는 물론 사용자 이름 및 암호만 포함 해야 합니다. 암호를 포함 하지 않으면 CsTestUserCredential cmdlet에서 해당 정보를 입력 하 라는 메시지를 표시 합니다. 사용자 이름은 앞의 코드 블록에 표시 된 domain name\user name 형식을 사용 하 여 지정할 수 있습니다.
  
테스트 사용자 자격 증명이 만들어졌는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 실행 합니다.
  
```PowerShell
Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
```

다음과 유사한 정보가 각 사용자에 대해 반환 됩니다.
  
|**사용자**|**입력**|
|:-----|:-----|
|Litwareinc\watcher1  <br/> |System.webserver  <br/> |
   
### <a name="configure-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>기본 가상 트랜잭션을 사용 하 여 기본 감시자 노드 구성

테스트 사용자를 만든 후 다음과 같은 명령을 사용 하 여 감시자 노드를 만들 수 있습니다.
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

이 명령은 기본 설정을 사용 하 고 기본적인 가상 트랜잭션 집합을 실행 하는 새 감시자 노드를 만듭니다. 또한 새 감시자 노드는 테스트 사용자 watcher1@litwareinc.com 및 watcher2@litwareinc.com를 사용 합니다. 감시자 노드가 있는 서버 인증을 사용 하는 경우 두 개의 테스트 계정이 Active Directory 및 비즈니스용 Skype Server에 대해 사용할 수 있는 유효한 사용자 계정이 될 수 있습니다. 감시자 노드가 협상 인증 방법을 사용 하는 경우 Set-CsTestUserCredential cmdlet을 사용 하 여 감시자 노드에 대해 이러한 사용자 계정도 사용할 수 있어야 합니다.
  
풀을 직접 대상으로 지정 하는 대신 로그인에 대 한 대상 풀의 자동 검색이 올바르게 구성 되어 있는지 확인 하려면 다음 단계를 대신 사용 합니다.
  
```PowerShell
New-CsWatcherNodeConfiguration -UseAutoDiscovery $true -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"}
```

### <a name="configuring-extended-tests"></a>확장 된 테스트 구성

공용 전환 전화 네트워크 연결을 확인 하는 PSTN 테스트를 사용 하도록 설정 하려는 경우 감시자 노드를 설정할 때 몇 가지 추가 구성을 수행 해야 합니다. 먼저 비즈니스용 Skype 서버 관리 셸에서와 유사한 명령을 실행 하 여 테스트 사용자를 PSTN 테스트 형식과 연결 해야 합니다.
  
```PowerShell
$pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com" -Name "Contoso Provider Test" -TestType PSTN
```

> [!NOTE]
> 이 명령의 결과는 변수에 저장 해야 합니다. 이 예제에서 변수 이름은 $pstnTest입니다. 
  
그런 다음 **CsWatcherNodeConfiguration** cmdlet을 사용 하 여 변수 $pstnTest에 저장 된 테스트 유형을 비즈니스용 Skype 서버 풀에 연결할 수 있습니다. 예를 들어 다음 명령은 풀 atl-cs-001.litwareinc.com에 대 한 새 감시자 노드 구성을 만들고, 이전에 만든 두 개의 테스트 사용자를 추가 하 고, PSTN 테스트 형식을 추가 합니다.
  
```PowerShell
New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}
```

비즈니스용 Skype Server core 파일과 감시자 노드 컴퓨터에 RTCLocal 데이터베이스를 설치 하지 않은 경우에는 앞의 명령이 실패 합니다. 
  
여러 음성 정책을 테스트 하기 위해 **새로운 CsExtendedTest** cmdlet을 사용 하 여 각 정책에 대 한 확장 테스트를 만들 수 있습니다. 제공 된 사용자는 원하는 음성 정책으로 구성 해야 합니다. 확장 된 테스트는 다음과 같이 쉼표 구분 기호를 사용 하 여 **새 CsWatcherNodeConfiguration** cmdlet에 전달 됩니다.
  
-ExtendedTests @ {Add = $pstnTest 1, $pstnTest 2, $pstnTest 3}
  
**CsWatcherNodeConfiguration** Cmdlet은 테스트 매개 변수를 사용 하지 않고 호출 했기 때문에 새 감시자 노드에는 기본 가상 트랜잭션과 지정 된 확장 가상 트랜잭션만 설정 됩니다. 따라서 감시자 노드는 다음 구성 요소를 테스트 합니다.
  
- 등록
    
- 메신저
    
- GroupIM
    
- P2PAV (피어 투 피어 오디오/비디오 세션)
    
- AvConference (오디오/회의)
    
- 현재 상태
    
- ABS (주소록 서비스)
    
- ABWQ (주소록 웹 서비스)
    
다음 구성 요소는 기본적으로 테스트 되지 않습니다.
  
- ASConference
    
- AVEdgeConnectivity
    
- DataConference
    
- DialinConferencing
    
- ExumConnectivity (Exchange 통합 메시징)
    
- JoinLauncher 관리자
    
- MCXP2PIM (레거시 모바일 장치 인스턴트 메시지)
    
- P2PVideoInteropServerSipTrunkAV
    
- PersistentChatMessage
    
- PSTN (PSTN 게이트웨이 통화, 확장 된 테스트로 지정 됨)
    
- UcwaConference
    
- UnifiedContactStore
    
- XmppIM
    
### <a name="adding-and-removing-synthetic-transactions"></a>가상 트랜잭션 추가 및 제거

감시자 노드가 구성 되 면 Set-CsWatcherNodeConfiguration cmdlet을 사용 하 여 노드에서 가상 트랜잭션을 추가 하거나 제거할 수 있습니다. 예를 들어 PersistentChatMessage 테스트를 감시자 노드에 추가 하려면 Add 메서드와 다음과 같은 명령을 사용 합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}
```

여러 테스트는 쉼표를 사용 하 여 테스트 이름을 구분 하 여 추가할 수 있습니다. 예를 들면 다음과 같습니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}
```

이러한 테스트 중 하나 이상 (예: DataConference)이 감시자 노드에 이미 사용 하도록 설정 되어 있으면 오류가 발생 합니다. 이 경우 다음과 같은 오류 메시지가 표시 됩니다.
  
CsWatcherNodeConfiguration: ' urn: schema: WatcherNode: TestName ' 키 또는 고유 id 제약 조건에 대 한 중복 키 시퀀스 ' DataConference '가 있습니다.
  
이 오류가 발생 하면 변경 내용이 적용 되지 않습니다. 중복 테스트가 제거 되 면 명령이 다시 실행 되어야 합니다.
  
감시자 노드에서 가상 트랜잭션을 제거 하려면 Remove 메서드를 사용 합니다. 예를 들어이 명령은 감시자 노드에서 ABWQ 테스트를 제거 합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}
```

Replace 메서드를 사용 하 여 현재 사용 가능한 모든 테스트를 하나 이상의 새 테스트로 바꿀 수 있습니다. 예를 들어 감시자 노드만 IM 테스트를 실행 하도록 하려면 다음 명령을 사용 하 여이를 구성할 수 있습니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}
```

이 명령을 실행 하면 IM을 제외한 지정 된 감시자 노드의 모든 가상 트랜잭션을 사용할 수 없게 됩니다.
  
### <a name="viewing-and-testing-the-watcher-node-configuration"></a>감시자 노드 구성 보기 및 테스트

감시자 노드에 할당 된 테스트를 보려면 다음과 같은 명령을 사용 합니다.
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests
```

이 명령은 노드에 할당 된 가상 트랜잭션에 따라 다음과 같은 정보를 반환 합니다.
  
등록 메신저 GroupIM P2PAV AvConference 현재 상태 PersistentChatMessage DataConference
> [!TIP]
> 가상 트랜잭션을 알파벳순으로 보려면 다음 명령을 대신 사용 합니다. 
  
```PowerShell
Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests | Sort-Object
```

감시자 노드가 만들어졌는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 합니다.
  
```PowerShell
Get-CsWatcherNodeConfiguration
```

다음과 같은 정보가 다시 표시 됩니다.
  
Id: atl-cs-001.litwareinc.com <br/>
TestUsers: {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}<br/>
ExtendedTests: {TestUsers = IList<System.webserver>; Name = PSTN 테스트; Te ...}<br/>
TargetFqdn: atl-cs-001.litwareinc.com<br/>
PortNumber: 5061<br/>

감시자 노드가 올바르게 구성 되었는지 확인 하려면 비즈니스용 Skype 서버 관리 셸에서 다음 명령을 입력 합니다.
  
```PowerShell
Test-CsWatcherNodeConfiguration
```

이 명령은 배포에서 각 감시자 노드를 테스트 하 고 다음 작업이 완료 되었는지 확인 합니다.
  
- 필수 등록자 역할이 설치 되어 있습니다.
    
- 필수 레지스트리 키가 생성 됩니다 (Set-CsWatcherNodeConfiguration cmdlet을 실행할 때 완료 됨).
    
- 서버에서 올바른 버전의 비즈니스용 Skype 서버를 실행 하 고 있습니다.
    
- 포트가 올바르게 구성 되어 있는지 확인 합니다.
    
- 지정 된 테스트 사용자에 게 필요한 자격 증명이 있습니다.
    
## <a name="managing-watcher-nodes"></a>감시자 노드 관리
<a name="testuser"> </a>

감시자 노드에서 실행 되는 가상 트랜잭션을 수정 하는 것 외에도 **CsWatcherNodeConfiguration** cmdlet을 사용 하 여 감시자 노드의 사용 여부를 설정 하거나 해제 하 고 해당 테스트를 실행할 때 내부 웹 url 또는 외부 웹 url을 사용 하도록 감시자 노드를 구성할 수 있습니다.
  
기본적으로 감시자 노드는 사용 하도록 설정 된 모든 가상 트랜잭션을 정기적으로 실행 하도록 디자인 되었습니다. 그러나 때로는 해당 트랜잭션을 일시 중단할 수 있습니다. 예를 들어 감시자 노드가 네트워크에서 일시적으로 연결이 끊어지면 가상 트랜잭션을 실행할 이유가 없습니다. 네트워크에 연결 되지 않은 경우 해당 트랜잭션은 실패 하 게 됩니다. 감시자 노드를 일시적으로 사용 하지 않도록 설정 하려면 비즈니스용 Skype 서버 관리 셸에서 다음과 같은 명령을 실행 합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False
```

이 명령은 감시자 노드 atl 감시자 001.litwareinc.com에서 가상 트랜잭션의 실행을 사용 하지 않도록 설정 합니다. 가상 트랜잭션의 실행을 다시 시작 하려면 Enabled 속성을 다시 True ($True)로 설정 합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True
```

> [!NOTE]
> Enabled 속성을 사용 하 여 감시자 노드를 켜거나 끌 수 있습니다. 감시자 노드를 영구적으로 삭제 하려면 **Remove-CsWatcherNodeConfiguration** cmdlet을 사용 합니다.
  
```PowerShell
Remove-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com"
```

이 명령은 지정 된 컴퓨터에서 모든 감시자 노드 구성 설정을 제거 하 여 해당 컴퓨터가 가상 트랜잭션을 자동으로 실행 하지 못하도록 합니다. 그러나이 명령은 System Center 에이전트 파일 또는 비즈니스용 Skype 서버 시스템 파일을 제거 하지 않습니다.
  
기본적으로 감시자 노드는 테스트를 수행할 때 조직의 외부 웹 Url을 사용 합니다. 그러나 조직의 내부 웹 Url을 사용 하도록 감시자 노드를 구성할 수도 있습니다. 이렇게 하면 관리자가 경계 네트워크 내에 있는 사용자의 URL 액세스를 확인할 수 있습니다. 외부 Url 대신 내부 Url을 사용 하도록 감시자 노드를 구성 하려면 UseInternalWebURls 속성을 True ($True)로 설정 합니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True
```

이 속성을 False ($False)로 다시 설정 하면 감시자가 다시 한 번 외부 Url을 사용 하 게 됩니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False
```

## <a name="special-setup-instructions-for-synthetic-transactions"></a>종합 거래에 대 한 특별 한 설정 지침
<a name="special_synthetictrans"> </a>

대부분의 가상 트랜잭션은 있는 그대로 감시자 노드에서 실행할 수 있습니다. 대부분의 경우, 가상 트랜잭션이 감시자 노드 구성 설정에 추가 되는 즉시 감시자 노드는 해당 테스트를 통과 하는 동안 해당 가상 트랜잭션을 사용 하 여 시작할 수 있습니다. 그러나 다음 섹션에서 설명 하는 것 처럼 특별 한 설정 지침이 필요한 몇 가지 가상 트랜잭션도 있습니다.
  
### <a name="data-conferencing-synthetic-transaction"></a>데이터 회의 가상 트랜잭션

감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 먼저 Windows Internet® Explorer를 사용 하지 않도록 설정 하 고 네트워크에 대 한 인터넷 브라우저 프록시 설정을 사용할 수 없는 경우에만 데이터 회의 종합 트랜잭션을 실행 하는 것이 좋습니다. 서비스 계정으로 다음 단계를 완료 합니다.
  
1. 감시자 노드 컴퓨터에서 **시작**, **모든 프로그램**, **액세서리**를 차례로 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.
    
2. 콘솔 창에서 다음 명령을 입력 한 다음 enter 키를 누릅니다. 
    
```console
bitsadmin /util /SetIEProxy NetworkService NO_PROXY
```

명령 창에 다음 메시지가 표시 됩니다.
  
BITSAdmin은 더 이상 사용 되지 않으며 이후 버전의 Windows에서 사용할 수 없는 것으로 보장 되지 않습니다. Bits 서비스에 대 한 관리 도구가 이제 BITS PowerShell cmdlet에서 제공 됩니다.
  
계정 NetworkService에 대 한 인터넷 프록시 설정이 NO_PROXY으로 설정 되었습니다. 
  
(connection = default)
  
이 메시지는 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 사용 하지 않도록 설정 했음을 나타냅니다.
  
### <a name="exchange-unified-messaging-synthetic-transaction"></a>Exchange 통합 메시징 가상 트랜잭션

UM (통합 메시징) 통합 트랜잭션은 테스트 사용자가 Exchange의 보이스 메일 계정에 연결할 수 있는지 여부를 확인 합니다.
  
테스트 사용자는 보이스 메일 계정을 사용 하 여 미리 구성 해야 합니다. 
  
### <a name="persistent-chat-synthetic-transaction"></a>영구 채팅 종합 트랜잭션

영구 채팅 종합 트랜잭션을 사용 하려면 먼저 채널을 만들고 사용자에 게이를 사용 권한을 부여 해야 합니다.
  
영구 채팅 종합 트랜잭션을 사용 하 여이 채널을 구성할 수 있습니다. 
  
```
$cred1 = Get-Credential "contoso\testUser1"
$cred2 = Get-Credential "contoso\testUser2"

Test-CsPersistentChatMessage -TargetFqdn pool0.contoso.com -SenderSipAddress sip:testUser1@contoso.com -SenderCredential $cred1 -ReceiverSipAddress sip:testUser2@contoso.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:testUser1@contoso.com -TestUser2SipAddress sip:testUser2@contoso.com -Setup $true
```

엔터프라이즈 내에서 실행 되어야 하는 설치 작업을 실행 해야 합니다.
  
- 서버 이외의 컴퓨터에서 실행 하는 경우 cmdlet을 실행 하는 사용자는 RBAC (역할 기반 액세스 제어)에 대 한 CsPersistentChatAdministrators 역할의 구성원 이어야 합니다.
    
- 서버 자체에서 실행 되는 경우 cmdlet을 실행 하는 사용자는 RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.
    
### <a name="pstn-peer-to-peer-call-synthetic-transaction"></a>PSTN 피어 투 피어 통화 가상 트랜잭션

테스트-CsPstnPeerToPeerCall 합성 트랜잭션은 PSTN (공개 교환 전화 네트워크)을 통해 전화를 걸고 받는 기능을 확인 합니다.
  
이 가상 트랜잭션을 실행 하려면 다음을 구성 해야 합니다.
  
- UC를 사용 하는 두 테스트 사용자 (호출자와 받는 사람)
    
- 각 사용자 계정에 대 한 직접 안쪽 전화 걸기 (번호)
    
- VoIP 정책 및 음성 경로-수신자의 번호로 전화를 걸어 PSTN 게이트웨이에 연결할 수 있습니다.
    
- 전화를 건 번호에 기반 하 여 전화를 받는 사람의 홈 풀로 다시 라우팅하는 통화와 미디어를 수락 하는 PSTN 게이트웨이.
    
### <a name="unified-contact-store-synthetic-transaction"></a>통합 된 대화 상대 저장소 가상 트랜잭션

통합 된 연락처 저장소 가상 트랜잭션은 Exchange에서 사용자를 대신 하 여 연락처를 검색 하는 비즈니스용 Skype 서버의 기능을 확인 합니다.
  
이 가상 트랜잭션을 사용 하려면 다음 조건을 충족 해야 합니다.
  
- Lyss-Exchange server에서 서버 인증을 구성 해야 합니다.
    
- 테스트 사용자는 유효한 Exchange 사서함이 있어야 합니다.
    
이러한 조건이 충족 되 면 다음 Windows PowerShell cmdlet을 실행 하 여 테스트 사용자의 연락처 목록을 Exchange로 마이그레이션할 수 있습니다.
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer -Setup
```

테스트 사용자 연락처 목록을 Exchange로 마이그레이션하는 데 시간이 걸릴 수 있습니다. 마이그레이션 진행 상황을 모니터링 하기 위해-설치 플래그 없이 같은 명령줄을 실행할 수 있습니다.
  
```PowerShell
Test-CsUnifiedContactStore -TargetFqdn pool0.contoso.com -UserSipAddress sip:testUser1@contoso.com -RegistrarPort 5061 -Authentication TrustedServer
```

이 명령줄은 마이그레이션이 완료 된 후에 성공 합니다.
  
### <a name="xmpp-synthetic-transaction"></a>XMPP 가상 트랜잭션

XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) IM 가상 트랜잭션을 사용 하려면 하나 이상의 페더레이션 도메인으로 XMPP 기능을 구성 해야 합니다.
  
XMPP 가상 트랜잭션을 사용 하도록 설정 하려면 라우팅할 수 있는 XMPP 도메인의 사용자 계정에 XmppTestReceiverMailAddress 매개 변수를 제공 해야 합니다. 예를 들면 다음과 같습니다.
  
```PowerShell
Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com
```

이 예제에서는 비즈니스용 Skype 서버 규칙이 있어야 litwareinc.com에 대 한 메시지를 XMPP 게이트웨이로 라우팅합니다.

> [!NOTE]
> XMPP 게이트웨이 및 프록시는 비즈니스용 Skype 서버 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2019에서는 더 이상 지원 되지 않습니다. 자세한 내용은 [XMPP 페더레이션 마이그레이션을](../../../SfBServer2019/migration/migrating-xmpp-federation.md) 참조 하세요. 
  
### <a name="video-interop-server-vis-synthetic-transaction"></a>VIS (비디오 Interop 서버) 가상 트랜잭션

VIS (동영상 Interop 서버) 가상 트랜잭션은 가상 트랜잭션 지원 파일 ([VISSTSupportPackage](https://www.microsoft.com/en-us/download/details.aspx?id=46921))을 다운로드 하 고 설치 해야 합니다. 
  
VISSTSupportPackage를 설치 하려면 msi에 대 한 종속성 (시스템 요구 사항 아래)이 이미 설치 되어 있는지 확인 합니다. 간단한 설치를 수행 하려면 VISSTSupportPackage를 실행 합니다. .Msi는 "%ProgramFiles%\VIS 가상 트랜잭션 지원 패키지" 경로의 모든 파일을 설치 합니다.
  
VIS 가상 트랜잭션을 실행 하는 방법에 대 한 자세한 내용은 [테스트-CsP2PVideoInteropServerSipTrunkAV](https://technet.microsoft.com/en-us/library/dn985894.aspx) cmdlet에 대 한 설명서를 참조 하세요.
  
## <a name="changing-the-run-frequency-for-synthetic-transactions"></a>가상 트랜잭션의 실행 빈도 변경
<a name="special_synthetictrans"> </a>

기본적으로 가상 트랜잭션은 구성 된 사용자와 15 분 마다 실행 됩니다. 가상 트랜잭션은 두 가지 가상 트랜잭션이 서로 충돌 하지 않도록 사용자 집합 내에서 순차적으로 실행 됩니다. 모든 가상 트랜잭션을 완료 하는 데 걸리는 시간을 제공 하기 위해 간격이 더 길게 필요 합니다.
  
가상 트랜잭션을 더 자주 실행 하는 것이 바람직한 경우 특정 사용자 집합을 사용 하 여 실행 되는 가상 트랜잭션의 수를 줄여야 하 여 테스트를 원하는 시간 범위에서 가끔씩 네트워크 지연에 대 한 버퍼와 함께 완료할 수 있도록 해야 합니다. 더 많은 가상 트랜잭션을 실행 하는 것이 바람직한 경우 추가 가상 트랜잭션을 실행 하기 위해 더 많은 사용자 집합을 만듭니다.
  
가상 트랜잭션을 실행 하는 빈도를 변경 하려면 다음 단계를 따릅니다.
  
1. System Center Operations Manager를 엽니다. 제작 섹션을 클릭 합니다. 규칙 섹션 (작성 중)을 클릭 합니다.
    
2. 규칙 섹션에서 "기본 종합 트랜잭션 러너 성과 수집 규칙"이 포함 된 규칙을 찾습니다.
    
3. 규칙을 마우스 오른쪽 단추로 클릭 하 고 재정의를 선택한 다음 규칙 재정의를 선택 하 고 "class: Pool 감시자"의 모든 개체에 대해 "를 선택 합니다.
    
4. 속성 재정의 창에서 매개 변수 이름 "Frequency"를 선택 하 고 재정의 값을 원하는 1로 설정 합니다.
    
5. 동일한 창에서이 재정의를 적용 해야 하는 관리 팩을 선택 합니다.
    
## <a name="using-rich-logging-for-synthetic-transactions"></a>종합 거래에 대 한 풍부한 로깅 사용
<a name="special_synthetictrans"> </a>

가상 트랜잭션은 시스템의 문제를 식별 하는 데 매우 유용 합니다. 예를 들어 테스트-CsRegistration cmdlet은 사용자가 비즈니스용 Skype Server에 등록 하는 데 어려움을 겪고 있다는 사실을 관리자에 게 알릴 수 있습니다. 그러나 실패의 실제 원인을 확인 하려면 추가 세부 정보가 필요할 수 있습니다.
  
이러한 이유로 가상 트랜잭션은 풍부한 로깅을 제공 합니다. 다양 한 로깅 기능을 통해 가상 트랜잭션을는 하는 각 활동에 대해 다음 정보가 기록 됩니다.
  
- 활동이 시작 된 시간입니다.
    
- 작업이 완료 된 시간입니다.
    
- 수행 된 작업 (예: 회의 만들기, 참가 또는 종료, 비즈니스용 Skype Server에 로그인, 인스턴트 메시지 보내기)
    
- 활동이 실행 될 때 생성 되는 정보, 세부 정보, 경고 또는 오류 메시지
    
- SIP 등록 메시지.
    
- 활동이 실행 될 때 생성 되는 예외 레코드 또는 진단 코드입니다.
    
- 활동 실행의 순 결과입니다.
    
이 정보는 가상 트랜잭션을 실행할 때마다 자동으로 생성 되지만 자동으로 표시 되거나 로그 파일에 저장 되지 않습니다. 가상 트랜잭션을 수동으로 실행 하는 경우 OutLoggerVariable 매개 변수를 사용 하 여 정보가 저장 되는 Windows PowerShell 변수를 지정할 수 있습니다. 여기서는 두 가지 방법 중 하나를 사용 하 여 XML 또는 HTML 형식의 풍부한 로그에서 오류 메시지를 저장 및/또는 볼 수 있습니다. 
  
문제 해결 정보를 검색 하려면 OutLoggerVariable 매개 변수를 지정 하 고 다음을 선택 하는 변수 이름을 입력 합니다.
  
```PowerShell
Test-CsRegistration -TargetFqdn atl-cs-001.litwareinc.com -OutLoggerVariable RegistrationTest
```

> [!NOTE]
> 변수 이름 앞에 $ 문자를 사용 하지 마세요. RegistrationTest ($RegistrationTest 아님) 등의 변수 이름을 사용 합니다. 
  
이 명령을 실행 하면 다음과 같은 출력이 표시 됩니다.
  
대상 Fqdn: atl-cs-001.litwareinc.com Result: 실패 한 지연: 00:00:00 오류 메시지:이 컴퓨터에는 할당 된 인증서가 없습니다. 진단:이 오류 메시지에 대 한 자세한 내용은 여기에 표시 된 것 보다 더 자세히 액세스할 수 있습니다.

HTML 형식으로이 정보에 액세스 하려면 다음과 유사한 명령을 사용 하 여 가변 RegistrationTest에 저장 된 정보를 HTML 파일에 저장 합니다.
  
```PowerShell
$RegistrationTest.ToHTML() | Out-File C:\Logs\Registration.html
```

또는 ToXML () 메서드를 사용 하 여 데이터를 XML 파일에 저장할 수 있습니다.
  
```PowerShell
$RegistrationTest.ToXML() | Out-File C:\Logs\Registration.xml
```

Windows Internet Explorer, Microsoft Visual Studio 또는 HTML/XML 파일을 열 수 있는 다른 응용 프로그램을 사용 하 여 이러한 파일을 볼 수 있습니다.
  
System Center 내에서 실행 되는 가상 트랜잭션은 오류에 대 한 이러한 로그 파일을 자동으로 생성 합니다. 비즈니스용 Skype Server PowerShell이 가상 트랜잭션을 로드 하 고 실행할 수 있으려면 실행이 실패 하는 경우 이러한 로그가 생성 되지 않습니다. 
  
> [!IMPORTANT]
> 기본적으로 비즈니스용 Skype 서버는 공유 되지 않는 폴더에 로그 파일을 저장 합니다. 이러한 로그에 쉽게 액세스할 수 있게 하려면이 폴더를 공유 해야 합니다. 예: \\atl-감시자-litwareinc. com\WatcherNode. 
