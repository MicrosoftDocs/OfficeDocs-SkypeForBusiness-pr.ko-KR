---
title: 감시자 노드 테스트 사용자 및 구성 설정 구성
description: 감시자 노드 테스트 사용자 및 구성 설정 구성
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
ms.openlocfilehash: e39a35d3db6ed80c715c706f4b5766e4b684e39e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542184"
---
# <a name="configuring-watcher-node-test-users-and-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 감시자 노드 테스트 사용자 및 구성 설정 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-07-29_

감시자 노드로 작동할 컴퓨터를 구성한 후에는 다음을 수행 해야 합니다.

1.  다음 감시자 노드에 사용할 테스트 계정을 만듭니다. 협상 인증 방법을 사용 하는 경우에는 [get-cstestusercredential](https://technet.microsoft.com/library/JJ205341(v=OCS.15)) cmdlet을 사용 하 여 이러한 테스트 계정을 감시자 노드에서 사용할 수 있도록 설정 해야 합니다.

2.  감시자 노드 구성 설정을 업데이트 합니다.

이 섹션에서는 다음 내용을 다룹니다.

  - 테스트 사용자 계정 구성

  - 기본 가상 트랜잭션을 사용 하 여 기본 감시자 노드 구성

  - 확장 테스트 구성

  - 가상 트랜잭션 추가 및 제거

  - 감시자 노드 구성 보기 및 테스트

<div>

## <a name="configuring-test-user-accounts"></a>테스트 사용자 계정 구성

테스트 사용자는 실제 사용자를 나타낼 필요가 없지만 유효한 Active Directory 도메인 서비스 계정 이어야 합니다. 또한 Lync Server 2013에 대해 이러한 계정을 사용 하도록 설정 해야 하 고, 유효한 SIP 주소가 있어야 하며, Test-CsPstnPeerToPeerCall 가상 트랜잭션을 사용 하기 위해 Enterprise Voice를 사용 하도록 설정 해야 합니다. 로 서버 인증 방법을 사용 하는 경우에는 이러한 계정이 있고 여기에서 지정한 대로 구성 되었는지 확인 해야 합니다. 테스트할 각 풀에 대해 테스트 사용자를 세 명 이상 할당 해야 합니다.

협상 인증 방법을 사용 하는 경우에는 **get-cstestusercredential** Cmdlet 및 Lync Server 관리 셸을 사용 하 여 이러한 테스트 계정이 가상 트랜잭션과 함께 작동 하도록 해야 합니다. 다음과 같은 명령을 실행 하 여이 작업을 수행할 수 있습니다. 이러한 명령은 세 개의 Active Directory 사용자 계정이 이미 만들어졌고 해당 계정이 Lync Server 2013에 대해 사용 하도록 설정 되어 있다고 가정 합니다.

    Set-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com" -UserName "litwareinc\watcher1" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com" -UserName "litwareinc\watcher2" -Password "P@ssw0rd"
    Set-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com" -UserName "litwareinc\watcher3" -Password "P@ssw0rd"

SIP 주소 뿐만 아니라 사용자 이름과 암호를 포함 해야 합니다. 암호를 포함 하지 않으면 Set-CsTestUserCredential에 게 해당 정보를 입력 하 라는 메시지가 표시 됩니다. 사용자 이름은 위에 나와 있는 도메인 이름 \\ 사용자 이름 형식을 사용 하거나 사용자 name@domain 이름 형식을 사용 하 여 지정할 수 있습니다 (예:

    -UserName "watcher3@litwareinc.com"

테스트 사용자 자격 증명이 만들어졌는지 확인 하려면 Lync Server 관리 셸 내에서 다음 명령을 실행 합니다.

    Get-CsTestUserCredential -SipAddress "sip:watcher1@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher2@litwareinc.com"
    Get-CsTestUserCredential -SipAddress "sip:watcher3@litwareinc.com"

각 사용자에 대해 다음과 같은 정보가 반환 됩니다.

    UserName                        Password
    --------                        --------
    Litwareinc\watcher1              System.Security.SecureString

</div>

<div>

## <a name="configuring-a-basic-watcher-node-with-the-default-synthetic-transactions"></a>기본 가상 트랜잭션을 사용 하 여 기본 감시자 노드 구성

테스트 사용자를 만든 후에는 다음과 같은 명령을 사용 하 여 감시자 노드를 만들 수 있습니다.

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"}

이 명령은 기본 설정을 사용 하 고 기본 트랜잭션 집합을 실행 하는 새 감시자 노드를 만듭니다. 또한 새 감시자 노드는 test users watcher1@litwareinc.com, watcher2@litwareinc.com 및 watcher3@litwareinc.com를 사용 합니다. 감시자 노드에서가 중 서버 인증을 사용 하는 경우에는 세 가지 테스트 계정이 Active Directory 및 Lync Server에 대해 사용 가능한 유효한 사용자 계정이 될 수 있습니다. 감시자 노드가 협상 인증 방법을 사용 하는 경우 **get-cstestusercredential** cmdlet을 사용 하 여이 사용자 계정도 감시자 노드에 대해 사용 하도록 설정 해야 합니다.

</div>

<div>

## <a name="configuring-extended-tests"></a>확장 테스트 구성

공용 전환 전화 네트워크와의 연결을 확인 하는 공중 전화망 (PSTN 테스트)을 사용 하도록 설정 하려는 경우에는 감시자 노드를 설정할 때 추가 구성을 수행 해야 합니다. 먼저 테스트 사용자를 PSTN 테스트 유형에 연결 해야 합니다. 이렇게 하려면 Lync Server 관리 셸에서와 비슷한 명령을 실행 합니다.

    $pstnTest = New-CsExtendedTest -TestUsers "sip:watcher1@litwareinc.com", "sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"  -Name "Contoso Provider Test" -TestType PSTN

이 명령의 결과는 변수에 저장 해야 합니다. 이 예제에서는 이름이 $pstnTest 이라는 변수입니다.

이제 **get-cswatchernodeconfiguration** cmdlet을 사용 하 여 $pstnTest 변수에 저장 된 테스트 유형을 Lync Server 2013 풀에 연결할 수 있습니다. 예를 들어 다음 명령은 atl-cs-001.litwareinc.com 풀에 대 한 새 감시자 노드 구성을 만들고 이전에 만든 세 가지 테스트 사용자를 추가한 다음 PSTN 테스트 종류를 추가 합니다.

    New-CsWatcherNodeConfiguration -TargetFqdn "atl-cs-001.litwareinc.com" -PortNumber 5061 -TestUsers @{Add= "sip:watcher1@litwareinc.com","sip:watcher2@litwareinc.com", "sip:watcher3@litwareinc.com"} -ExtendedTests @{Add=$pstnTest}

Lync Server core 파일 및 RTCLocal 데이터베이스를 감시자 노드 컴퓨터에 설치 하지 않은 경우에는 위의 명령이 실패 합니다.

여러 음성 정책을 테스트 하려면 **new-csextendedtest** cmdlet을 사용 하 여 각 정책에 대 한 확장 테스트를 만들어야 합니다. 이 테스트에 할당 된 사용자는 원하는 음성 정책을 사용 하 여 구성 해야 합니다. 그런 다음 확장 테스트는 다음과 같은 명령을 사용 하 여 **get-cswatchernodeconfiguration** cmdlet으로 전달 됩니다.

    -ExtendedTests @{Add=$pstnTest1,$pstnTest2,$pstnTest3}

테스트 매개 변수를 사용 하지 않고 New-CsWatcherNodeConfiguration를 호출 하면 새 감시자 노드에 기본 가상 트랜잭션과 지정 된 확장 가상 트랜잭션만 사용할 수 있습니다. 즉, 감시자 노드는 다음과 같은 구성 요소를 테스트 합니다.

  - 등록

  - 메시징을

  - GroupIM

  - P2PAV (피어 투 피어 오디오/비디오 세션)

  - AvConference (오디오/회의)

  - 이들의

  - ABS (주소록 서비스)

  - ABWQ (주소록 웹 서비스)

  - PSTN (PSTN 게이트웨이 통화, 확장 된 테스트로 지정) 기본적으로 PSTN은 사용 하지 않도록 설정 되어 있습니다. 이 경우에는 명령이 ExtendedTests 매개 변수를 사용 하 여 PSTN을 사용 하도록 설정 되어 있기 때문에 테스트가 사용 되도록 설정 됩니다.

또한 다음과 같은 구성 요소가 기본적으로 테스트 되지 않습니다.

  - AVEdgeConnectivity

  - MCXP2PIM (모바일 장치 인스턴트 메시징)

  - ExumConnectivity (Exchange 통합 메시징)

  - JoinLauncher 관리자

  - PersistentChatMessage

  - DataConference

  - XmppIM

  - UnifiedContactStore

</div>

<div>

## <a name="adding-and-removing-synthetic-transactions"></a>가상 트랜잭션 추가 및 제거

감시자 노드를 구성한 후에는 **get-cswatchernodeconfiguration** cmdlet을 사용 하 여 노드에서 가상 트랜잭션을 추가 하거나 제거할 수 있습니다. 예를 들어 PersistentChatMessage 테스트를 감시자 노드에 추가 하려면 Add 메서드와 다음과 같은 명령을 사용 합니다.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage"}

테스트 이름을 쉼표로 구분 하 여 여러 테스트를 추가할 수 있습니다. 예제:

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Add="PersistentChatMessage","DataConference","UnifiedContactStore"}

이러한 테스트 (예: DataConference) 중 하나 이상이 이미 감시자 노드에 대해 사용 하도록 설정 되어 있으면 오류가 발생 합니다. 이 경우 다음과 같은 오류 메시지가 표시 됩니다.

    Set-CsWatcherNodeConfiguration : There is a duplicate key sequence 'DataConference' for the 'urn:schema:Microsoft.Rtc.Management.Settings.WatcherNode.2010:TestName' key or unique identity constraint.

이 오류가 발생 하면 변경 내용이 적용 되지 않습니다. 중복 된 테스트를 제거 하 고 명령을 다시 실행 해야 합니다.

감시자 노드에서 가상 트랜잭션을 제거 하려면 Add 메서드 대신 Remove 메서드를 사용 합니다. 예를 들어이 명령은 감시자 노드에서 ABWQ 테스트를 제거 합니다.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Remove="ABWQ"}

Replace 메서드를 사용 하 여 현재 사용 가능한 모든 테스트를 하나 이상의 새 테스트로 바꿀 수도 있습니다. 예를 들어 감시자 노드만 IM 테스트를 실행 하려면 다음 명령을 사용 하 여 해당 노드를 구성 하면 됩니다.

    Set-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" -Tests @{Replace="IM"}

위의 명령을 실행 하면 IM을 제외한 지정 된 감시자 노드의 모든 가상 트랜잭션이 사용 하지 않도록 설정 됩니다.

</div>

<div>

## <a name="viewing-and-testing-the-watcher-node-configuration"></a>감시자 노드 구성 보기 및 테스트

감시자 노드에 할당 된 테스트를 보려면 다음과 같은 명령을 사용 합니다.

    Get-CsWatcherNodeConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object -ExpandProperty Tests

위의 명령은 노드에 할당 된 가상 트랜잭션에 따라 다음과 같은 정보를 반환 합니다.

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
> 사전순으로 가상 트랜잭션을 보려면 다음 명령을 대신 사용 합니다.<BR>Get-CsWatcherNodeConfiguration-Id "atl-cs-001.litwareinc.com" | Select-Object-ExpandProperty 테스트 | Sort-Object



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

위의 명령은 배포의 각 감시자 노드를 테스트 하 고 다음을 비롯 한 정보를 설명 합니다.

  - 필요한 등록자 역할이 설치 되었습니다.

  - Get-cswatchernodeconfiguration를 실행할 때 필요한 레지스트리 키를 만들었습니다.

  - 서버에서 올바른 버전의 Lync Server를 실행 하 고 있습니다.

  - 포트가 올바르게 구성 되어 있습니다.

  - 할당 된 테스트 사용자에 게 필요한 자격 증명이 있어야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

