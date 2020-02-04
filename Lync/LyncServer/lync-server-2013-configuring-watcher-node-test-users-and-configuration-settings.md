---
title: 감시자 노드 테스트 사용자 및 구성 설정 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring watcher node test users and configuration settings
ms:assetid: ab00e9cb-f539-4aa6-bcb4-5533fbe7bc44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205152(v=OCS.15)
ms:contentKeyID: 48185048
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3713844d5d2364459a28c5919bb1d32d421d706
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733668"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 감시자 노드 테스트 사용자 및 구성 설정 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-07-29_

감시자 노드 역할을 하는 컴퓨터를 구성한 후에는 다음을 수행 해야 합니다.

1.  이러한 감시자 노드에서 사용할 테스트 계정을 만듭니다. 협상 인증 방법을 사용 하는 경우 [CsTestUserCredential](https://technet.microsoft.com/en-us/library/JJ205341(v=OCS.15)) cmdlet을 사용 하 여 이러한 테스트 계정을 감시자 노드에서 사용할 수 있도록 설정 해야 합니다.

2.  감시자 노드 구성 설정을 업데이트 합니다.

이 섹션에서는 다음에 대해 설명 합니다.

  - 테스트 사용자 계정 구성

  - 기본 가상 트랜잭션을 사용 하 여 기본 감시자 노드 구성

  - 확장 된 테스트 구성

  - 가상 트랜잭션 추가 및 제거

  - 감시자 노드 구성 보기 및 테스트

<div>

## <a name="configuring-test-user-accounts"></a>테스트 사용자 계정 구성

테스트 사용자는 실제 사용자를 나타낼 필요는 없지만 올바른 Active Directory 도메인 서비스 계정 이어야 합니다. 또한이 계정에는 Lync Server 2013을 사용할 수 있어야 하며, 유효한 SIP 주소가 있어야 하며, 테스트-CsPstnPeerToPeerCall 가상 트랜잭션을 사용 하려면 Enterprise Voice를 사용 하도록 설정 해야 합니다. 로 서버 인증 방법을 사용 하는 경우에는 이러한 계정이 존재 하 고 여기에 지정 된 대로 구성 되어 있는지 확인 해야 합니다. 테스트 하려는 각 풀에 대해 최소 세 개의 테스트 사용자를 할당 해야 합니다.

협상 인증 방법을 사용 하는 경우 **CsTestUserCredential** Cmdlet 및 Lync Server Management Shell을 사용 하 여 이러한 테스트 계정이 가상 트랜잭션과 함께 작동 하도록 설정 해야 합니다. 다음과 같은 명령을 실행 하 여이 작업을 수행할 수 있습니다. 이러한 명령은 세 개의 Active Directory 사용자 계정이 이미 생성 되었고 해당 계정이 Lync Server 2013에 대해 사용 하도록 설정 되어 있다고 가정 합니다.

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

SIP 주소는 물론 사용자 이름 및 암호만 포함 해야 합니다. 암호 집합을 포함 하지 않으면-CsTestUserCredential에서 해당 정보를 입력 하 라는 메시지가 표시 됩니다. 사용자 이름은 위에 표시 된 도메인 이름\\사용자 이름 형식을 사용 하 여 지정 하거나 사용자 name@domain 이름 형식을 사용 하 여 지정할 수 있습니다. 예를 들어:

    -UserName "watcher3@litwareinc.com"

테스트 사용자 자격 증명이 만들어졌는지 확인 하려면 Lync Server Management Shell 내에서 다음 명령을 실행 합니다.

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

각 사용자에 대해 다음과 유사한 정보가 반환 됩니다.

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>기본 가상 트랜잭션을 사용 하 여 기본 감시자 노드 구성

테스트 사용자를 만든 후 다음과 같은 명령을 사용 하 여 감시자 노드를 만들 수 있습니다.

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

이 명령은 기본 설정을 사용 하 고 기본적인 가상 트랜잭션 집합을 실행 하는 새 감시자 노드를 만듭니다. 또한 새 감시자 노드는 테스트 사용자 watcher1@litwareinc.com, watcher2@litwareinc.com 및 watcher3@litwareinc.com를 사용 합니다. 감시자 노드가 개인 서버 인증을 사용 하는 경우, Active Directory 및 Lync Server에 대해 사용할 수 있는 유효한 사용자 계정이 세 가지 테스트 계정 중 하나입니다. 감시자 노드가 협상 인증 방법을 사용 하는 경우 **Set-CsTestUserCredential** cmdlet을 사용 하 여 감시자 노드에 대해 이러한 사용자 계정도 사용 하도록 설정 해야 합니다.

</div>

<div>

## <a name="configuring-extended-tests"></a>확장 된 테스트 구성

공개 전환 전화 네트워크 연결을 확인 하는 PSTN 테스트 (공공 전환 전화 네트워크)를 사용 하도록 설정 하려는 경우 감시자 노드를 설정할 때 몇 가지 추가 구성을 수행 해야 합니다. 먼저 테스트 사용자를 PSTN 테스트 형식과 연결 해야 합니다. 이렇게 하려면 Lync Server 관리 셸에서 다음과 같은 명령을 실행 합니다.

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

이 명령의 결과는 변수에 저장 되어야 한다는 점에 유의 하세요. 이 예제에서는이 변수를 $pstnTest 라고 합니다.

이 시점에서 **CsWatcherNodeConfiguration** cmdlet을 사용 하 여 변수 $pstnTest에 저장 된 테스트 유형을 Lync Server 2013 풀에 연결할 수 있습니다. 예를 들어 다음 명령을 실행 하면 풀 atl-cs-001.litwareinc.com에 대 한 새 감시자 노드 구성이 만들어지고 이전에 만든 세 개의 테스트 사용자가 추가 되며 PSTN 테스트 형식도 추가 됩니다.

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Lync Server core 파일과 감시자 노드 컴퓨터에 RTCLocal 데이터베이스를 설치 하지 않은 경우 앞의 명령은 실패 합니다.

여러 음성 정책을 테스트 하려면 **새 CsExtendedTest** cmdlet을 사용 하 여 각 정책에 대 한 확장 테스트를 만들어야 합니다. 이 테스트에 할당 된 사용자는 원하는 음성 정책으로 구성 해야 합니다. 그런 다음 확장 테스트는 다음과 유사한 명령을 사용 하 여 **CsWatcherNodeConfiguration** cmdlet에 전달 됩니다.

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

테스트 매개 변수를 사용 하지 않고 New-CsWatcherNodeConfiguration가 호출 되는 경우,이는 기본 가상 트랜잭션 (및 지정 된 확장 된 가상 트랜잭션)만 새 감시자 노드에 대해 설정 됨을 의미 합니다. 이것은 감시자 노드가 다음 구성 요소를 테스트 한다는 의미입니다.

  - 등록

  - 메신저

  - GroupIM

  - P2PAV (피어 투 피어 오디오/비디오 세션)

  - AvConference (오디오/회의)

  - 현재 상태

  - ABS (주소록 서비스)

  - ABWQ (주소록 웹 서비스)

  - PSTN (PSTN 게이트웨이 통화, 확장 테스트로 지정 됨) 기본적으로 PSTN은 비활성화 되어 있습니다. 이 경우 명령은 ExtendedTests 매개 변수를 사용 하 여 PSTN을 사용할 수 있기 때문에 테스트를 사용할 수 있습니다.

이는 또한 다음 구성 요소가 기본적으로 테스트 되지 않음을 의미 합니다.

  - AVEdgeConnectivity

  - MCXP2PIM (모바일 장치 인스턴트 메시지)

  - ExumConnectivity (Exchange 통합 메시징)

  - JoinLauncher 관리자

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>가상 트랜잭션 추가 및 제거

감시자 노드가 구성 되 면 **Set-CsWatcherNodeConfiguration** cmdlet을 사용 하 여 노드에서 가상 트랜잭션을 추가 하거나 제거할 수 있습니다. 예를 들어 PersistentChatMessage 테스트를 감시자 노드에 추가 하려면 Add 메서드와 다음과 같은 명령을 사용 합니다.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

여러 테스트는 쉼표를 사용 하 여 테스트 이름을 구분 하 여 추가할 수 있습니다. 예를 들면 다음과 같습니다.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

이러한 테스트 중 하나 이상 (예: DataConference)이 감시자 노드에서 이미 사용 하도록 설정 된 경우 오류가 발생 합니다. 이 경우 다음과 같은 오류 메시지가 표시 됩니다.

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

이 오류가 발생 하면 변경 내용이 적용 되지 않습니다. 중복 테스트가 제거 되 면 명령을 다시 실행 해야 합니다.

감시자 노드에서 가상 트랜잭션을 제거 하려면 Add 메서드 대신 Remove 메서드를 사용 합니다. 예를 들어이 명령은 감시자 노드에서 ABWQ 테스트를 제거 합니다.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Replace 메서드를 사용 하 여 현재 사용 가능한 모든 테스트를 하나 이상의 새 테스트로 바꿀 수도 있습니다. 예를 들어, 감시자 노드만 IM 테스트를 실행 하려면 다음 명령을 사용 하 여이를 구성할 수 있습니다.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

앞의 명령을 실행 하는 경우 IM을 제외한 지정 된 감시자 노드의 모든 가상 트랜잭션을 사용 하지 않도록 설정 됩니다.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>감시자 노드 구성 보기 및 테스트

감시자 노드에 할당 된 테스트를 보려면 다음과 같은 명령을 사용 합니다.

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

앞의 명령은 노드에 할당 된 가상 트랜잭션에 따라 다음과 같은 정보를 반환 합니다.

    Registration
    IM
    GroupIM
    P2PAV
    AvConference
    Presence
    PersistentChatMessage
    DataConference

<div>


> [!TIP]
> 가상 트랜잭션을 알파벳순으로 보려면 다음 명령을 대신 사용 합니다.<BR>Get-CsWatcherNodeConfiguration – Id "atl-cs-001.litwareinc.com" | 선택-개체-ExpandProperty 테스트 | 정렬 개체



</div>

감시자 노드가 만들어졌는지 확인 하려면 Lync Server 관리 셸 내에서 다음 명령을 입력 합니다.

    Get-CsWatcherNodeConfiguration

다음과 같은 정보가 표시 됩니다.

    Identity      : atl-cs-001.litwareinc.com
    TestUsers     : {sip:watcher1@litwareinc.com, sip:watcher2@litwareinc.com ...}
    ExtendedTests : {TestUsers=IList<System.String>;Name=PSTN Test; Te...}
    TargetFqdn    : atl-cs-001.litwareinc.com
    PortNumber    : 5061

감시자 노드가 올바르게 구성 되었는지 확인 하려면 Lync Server 관리 셸 내에서 다음 명령을 입력 합니다.

    Test-CsWatcherNodeConfiguration

앞의 명령은 배포에서 각 감시자 노드를 테스트 하 고 다음과 같은 정보를 알려 줍니다.

  - 필수 등록자 역할이 설치 되었습니다.

  - CsWatcherNodeConfiguration을 (를) 실행할 때 필요한 레지스트리 키가 생성 되었습니다.

  - 서버에서 올바른 버전의 Lync Server를 실행 중입니다.

  - 포트가 올바르게 구성 되었습니다.

  - 지정 된 테스트 사용자에 게 필요한 자격 증명이 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

