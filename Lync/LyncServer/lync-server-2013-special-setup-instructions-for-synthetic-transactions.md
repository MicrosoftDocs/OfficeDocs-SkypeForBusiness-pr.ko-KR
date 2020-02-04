---
title: 'Lync Server 2013: 종합 거래에 대 한 특별 한 설정 지침'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Special setup instructions for synthetic transactions
ms:assetid: 694cbe05-5dba-4035-a01c-c87ebfb0478b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688080(v=OCS.15)
ms:contentKeyID: 49733676
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a15177a3c4548b235bf01a10274168e4a830fad3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731908"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013의 종합 거래에 대 한 특별 한 설정 지침

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-11-16_

대부분의 가상 트랜잭션은 있는 그대로 감시자 노드에서 실행할 수 있습니다. 즉, 가상 트랜잭션이 감시자 노드 구성 설정에 추가 되는 즉시 감시자 노드는 해당 테스트를 통과 하는 동안 가상 트랜잭션을 사용 하 여 시작할 수 있습니다. 그러나 모든 가상 거래에는 적용 되지 않습니다. 특별 한 설정 지침이 필요한 가상 트랜잭션은 다음 섹션에서 설명 합니다.

<div>

## <a name="dealing-with-server-timeout-errors"></a>서버 시간 초과 오류 처리

경우에 따라 가상 트랜잭션이 서버 시간 초과 오류로 인해 실패 하는 경우가 있을 수 있습니다 (오류 코드 504). 이러한 오류는 일반적으로 방화벽 문제 때문에 발생 합니다. 가상 트랜잭션을 실행할 때 해당 트랜잭션은 MonitoringHost 프로세스에서 실행 됩니다. MonitoringHost는 debug.exe 프로세스의 인스턴스를 시작 합니다. MonitoringHost 또는 PowerShell이 방화벽에 의해 차단 되는 경우 가상 트랜잭션은 실패 하 고 504 오류가 생성 됩니다.

이 문제를 해결 하려면 로컬 컴퓨터에서 MonitoringHost 및 debug.exe 모두에 대해 수동으로 인바운드 방화벽 규칙을 만들어야 합니다. 이 작업은 서버의 기존 구성에 따라 Windows 방화벽이 나 타사 로컬 방화벽 소프트웨어를 통해 수행할 수 있습니다.

가상 트랜잭션 호스트 컴퓨터와 모니터링 하려는 Lync 서버 간에 네트워크 방화벽 장치를 채택 하는 경우 호스트를 클라이언트 컴퓨터로 처리 하 고 [Lync Server 2013의 내부 서버에 대 한 포트 및 프로토콜](lync-server-2013-ports-and-protocols-for-internal-servers.md)의 모든 방화벽 포트 요구 사항을 관찰자에 게 전송 해야 합니다.

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>데이터 회의 가상 트랜잭션

감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우 먼저 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 사용 하지 않도록 설정 하지 않는 한 데이터 회의 가상 트랜잭션을 실행할 수 없습니다. 이 서비스에 대 한 프록시 설정을 사용 하지 않으려면 다음 절차를 완료 합니다.

1.  감시자 노드 컴퓨터에서 **시작**, **모든 프로그램**, **액세서리**를 차례로 클릭 하 고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.

2.  콘솔 창에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

명령 창에 다음 메시지가 표시 됩니다.

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

이 메시지는 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 사용 하지 않도록 설정 했다는 의미입니다.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Exchange 통합 메시징 종합 트랜잭션

UM (통합 메시징) 통합 트랜잭션은 테스트 사용자가 Exchange의 보이스 메일 계정에 연결할 수 있는지 여부를 확인 합니다. 이러한 테스트 사용자는 Exchange UM 테스트를 사용 하기 전에 먼저 보이스 메일 계정을 사용 하 여 미리 구성 해야 합니다.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>영구 채팅 종합 거래

영구 채팅 종합 트랜잭션을 사용 하려면 관리자가 먼저 채널을 만들고 사용자에 게이를 사용할 수 있는 권한을 테스트 해야 합니다. [테스트 CsPersistentChatMessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet을 사용 하 여 이러한 테스트 사용자를 올바르게 구성할 수 있습니다.

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

이 설치 작업은 엔터프라이즈 내에서 실행 해야 합니다.

  - Nonserver 컴퓨터에서 실행 하는 경우 cmdlet을 실행 하는 사용자는 RBAC (역할 기반 액세스 제어)에 대해 PersistentChatAdministrators 역할의 구성원 이어야 합니다.

  - 서버 자체에서 실행 되는 경우 cmdlet을 실행 하는 사용자는 RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.

위의 명령에서 Setup 매개 변수를 포함 하 고 True ($True)로 설정 했습니다. 설치 매개 변수를 포함 하는 경우 CsPersistentChatMessage에서 특수 영구 채팅방을 만들고 해당 룸을 테스트 사용자에 게 채웁니다. 이는 테스트 목적으로 실제로 채팅방을 사용할 수 있도록 하는 데 도움이 됩니다. 설치 매개 변수는 프런트 엔드 서버 에서만 실행 되어야 합니다.

CsPersistentChatMessage에서 생성 되는 채팅방은 관리자만 삭제할 수 있습니다.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>PSTN 피어 투 피어 호출 종합 트랜잭션

[테스트-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) 합성 트랜잭션은 PSTN (공용 전환 통신 네트워크)을 통해 전화를 걸고 받는 기능을 확인 합니다.

이 가상 트랜잭션을 실행 하려면 관리자가 다음을 구성 해야 합니다.

  - 두 개의 테스트 사용자 (호출자와 받는 사람이 엔터프라이즈 음성에 대해 사용 하도록 설정 됨)

  - 각 사용자 계정에 대 한 직접 안쪽 전화 걸기 (번호)

  - 전화 번호를 통해 PSTN 게이트웨이에 연결할 수 있는 음성 정책 및 음성 경로

  - 통화를 수락 하는 PSTN 게이트웨이 및 통화를 라우팅하는 미디어는 전화를 건 번호를 기준으로 받는 사람의 홈 풀로 백업 됩니다.

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>통합 된 연락처 저장소 종합 트랜잭션

통합 된 연락처 저장소 가상 트랜잭션은 Lync Server 2013에서 Microsoft Exchange Server 2013의 사용자를 대신 하 여 연락처를 검색할 수 있는지 확인 합니다.

이 가상 트랜잭션을 사용 하려면 다음 조건을 충족 해야 합니다.

  - Lync server [2013의 OAuth (서버 간 인증) 및 파트너 응용 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 는 lync server 2013 및 Exchange 2013 간에 구성 되어야 합니다.

  - 테스트 사용자는 유효한 Exchange 2013 사서함이 있어야 합니다.

이러한 조건이 충족 되 면 관리자는 다음 명령을 실행 하 여 SIP 주소 kenmyer@litwareinc.com를 가진 사용자가 통합 대화 상대 저장소에서 해당 연락처를 검색할 수 있는지 확인할 수 있습니다.

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

앞의 명령에 사용 된 Setup 매개 변수의 사용을 확인 합니다. Test-CsUnifiedContactStore를 실행할 때 Setup 매개 변수가 포함 된 경우 지정 된 사용자의 연락처 (이 예에서는 sip:kenmyer@litwareinc.com)가 통합 연락처 저장소로 이동 됩니다. (물론, 사용자의 연락처가 이미 통합 된 연락처 저장소에 있는 경우에는 이동할 필요가 없습니다.) Setup 매개 변수는 일반적으로 한 번만 사용 되며 (테스트 CsUnifiedContactStore가 실행 되는 경우)에만 테스트 사용자와 함께 사용 해야 합니다. 즉, 사용자 계정이 Lync Server에 실제로 로그온 되지 않습니다. 테스트 사용자를 통합 대화 상대 저장소로 마이그레이션한 후에는 Setup 매개 변수 없이 CsUnifiedContactStore를 호출 하 여 사용자의 연락처를 검색할 수 있는지 확인할 수 있습니다.

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>XMPP 가상 트랜잭션

XMPP (확장할 수 있는 메시징 및 현재 상태 프로토콜) IM 가상 트랜잭션을 사용 하려면 XMPP 기능을 하나 이상의 페더레이션 도메인으로 구성 해야 합니다.

XMPP 가상 트랜잭션을 사용 하도록 설정 하려면 XmppTestReceiverMailAddress 매개 변수를 라우팅할 수 있는 XMPP 도메인의 사용자 계정으로 제공 해야 합니다. 예를 들면 다음과 같습니다.

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

이 예제에서는 litwareinc.com에 대 한 메시지를 XMPP 게이트웨이로 라우팅하기 위해 Lync Server 2013 규칙이 있어야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

