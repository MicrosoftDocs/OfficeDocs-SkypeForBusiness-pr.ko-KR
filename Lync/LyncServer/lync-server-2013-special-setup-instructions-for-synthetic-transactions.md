---
title: 'Lync Server 2013: 가상 트랜잭션에 대 한 특별 설치 지침'
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
ms.openlocfilehash: a749e4349f6dae6ab7cae079af443734f9cfbc15
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41985053"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="special-setup-instructions-for-synthetic-transactions-in-lync-server-2013"></a>Lync Server 2013의 가상 트랜잭션에 대 한 특별 설치 지침

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-11-16_

대부분의 가상 트랜잭션은 감시자 노드에서 있는 그대로 실행됩니다. 즉, 가상 트랜잭션이 감시자 노드 구성 설정에 추가되는 즉시, 감시자 노드가 테스트 진행 중 가상 트랜잭션을 즉시 사용할 수 있습니다. 하지만 이러한 방식이 모든 가상 트랜잭션에 적용되는 것은 아닙니다. 이러한 예외적인 특별한 설치 지침이 필요한 가상 트랜잭션은 다음 섹션에서 자세히 설명합니다.

<div>

## <a name="dealing-with-server-timeout-errors"></a>서버 시간 제한 오류 처리

경우에 따라 가상 트랜잭션이 서버 시간 제한 오류 (오류 코드 504)와 함께 실패 하는 경우가 있습니다. 이러한 오류는 일반적으로 방화벽 문제로 인해 발생 합니다. 가상 트랜잭션이 실행 되 면 해당 트랜잭션은 MonitoringHost 프로세스에서 실행 되 고, MonitoringHost는 debug.exe 프로세스의 인스턴스를 시작 합니다. MonitoringHost 또는 debug.exe가 방화벽에 의해 차단 되 면 가상 트랜잭션이 실패 하 고 504 오류가 발생 합니다.

이 문제를 해결 하려면 로컬 컴퓨터에서 MonitoringHost 및 debug.exe 둘 다에 대해 인바운드 방화벽 규칙을 수동으로 만들어야 합니다. 이 작업은 서버의 기존 구성에 따라 Windows 방화벽이 나 타사 로컬 방화벽 소프트웨어를 통해 수행 될 수 있습니다.

가상 트랜잭션 호스트 컴퓨터와 모니터링 하려는 Lync 서버 간에 네트워크 방화벽 장치를 사용할 경우에는 호스트를 클라이언트 컴퓨터로 취급 하 고 모든 방화벽 포트 요구 사항을 [Lync Server 2013의 내부 서버에 대 한 포트 및 프로토콜](lync-server-2013-ports-and-protocols-for-internal-servers.md)에서 관찰자로 다루어야 합니다.

</div>

<div>

## <a name="data-conferencing-synthetic-transactions"></a>데이터 회의 가상 트랜잭션

감시자 노드 컴퓨터가 경계 네트워크 외부에 있는 경우에는 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 먼저 사용 하지 않도록 설정 하지 않는 한 데이터 회의 가상 트랜잭션을 실행할 수 없게 됩니다. 이 서비스에 대해 프록시 설정을 사용하지 않도록 설정하려면 다음 절차를 수행합니다.

1.  감시자 노드 컴퓨터에서 **시작**, **모든 프로그램**, **보조프로그램**을 차례로 클릭하고 **명령 프롬프트**를 마우스 오른쪽 단추로 클릭한 후 **관리자로 실행**을 클릭합니다.

2.  콘솔 창에 다음 명령을 입력한 다음 Enter 키를 누릅니다.
    
        bitsadmin /util /SetIEProxy NetworkService NO_PROXY

명령 창에 다음 메시지가 표시됩니다.

    BITSAdmin is deprecated and is not guaranteed to be available in future versions of Windows. Administration tools for the BITS service are now provided by BITS PowerShell cmdlets.
    
    Internet proxy settings for account NetworkService set to NO_PROXY. 
    (connection = default)

이 메시지는 네트워크 서비스 계정에 대 한 Internet Explorer 프록시 설정을 사용 하지 않도록 설정 했음을 의미 합니다.

</div>

<div>

## <a name="exchange-unified-messaging-synthetic-transactions"></a>Exchange 통합 메시징 가상 트랜잭션

Exchange UM (통합 메시징) 가상 트랜잭션은 테스트 사용자가 Exchange에서 홈에 있는 음성 메일 계정에 연결할 수 있는지 확인 합니다. 이러한 테스트 사용자는 Exchange UM 테스트를 사용하기 전에 음성 메일 계정으로 미리 구성되어 있어야 합니다.

</div>

<div>

## <a name="persistent-chat-synthetic-transactions"></a>영구 채팅 가상 트랜잭션

영구 채팅 가상 트랜잭션을 사용 하려면 관리자가 먼저 채널을 만들고 사용자에 게이를 사용 하기 위한 권한을 부여 해야 합니다. [Test-cspersistentchatmessage](https://docs.microsoft.com/powershell/module/skype/Test-CsPersistentChatMessage) cmdlet은 이러한 테스트 사용자를 올바르게 구성 하는 데 사용할 수 있습니다.

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-cs-001.litwareinc.com -SenderSipAddress sip:kenmyer@litwareinc.com -SenderCredential $cred1 -ReceiverSipAddress sip:pilar@litwareinc.com -ReceiverCredential $cred2 -TestUser1SipAddress sip:kenmyer@litwareinc.com -TestUser2SipAddress sip:pilar@litwareinc.com -Setup $True

이 설정 작업은 엔터프라이즈 내부에서 실행해야 합니다.

  - 서버가 아닌 컴퓨터에서 실행할 경우 cmdlet을 실행하는 사용자는 RBAC(역할 기반 액세스 제어)에 대한 PersistentChatAdministrators 역할의 구성원이어야 합니다.

  - 서버 자체에서 실행할 경우 cmdlet을 실행하는 사용자는 RTCUniversalServerAdmins 그룹의 구성원이어야 합니다.

위 명령에서는 Setup 매개 변수가 포함되었으며 True($True)로 설정되었습니다. Setup 매개 변수를 포함 하면 Test-cspersistentchatmessage에서 특수 영구 대화방을 만들고 해당 대화방을 테스트 사용자에 게 채웁니다. 이러한 방식은 테스트 목적으로 사용할 수 있는 채팅방을 실제로 만드는 데 도움이 됩니다. Setup 매개 변수는 프런트 엔드 서버 에서만 실행 해야 합니다.

Test-CsPersistentChatMessage로 만든 채팅방은 관리자만 삭제할 수 있습니다.

</div>

<div>

## <a name="pstn-peer-to-peer-call-synthetic-transactions"></a>PSTN 피어 투 피어 통화 가상 트랜잭션

[테스트-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) 가상 트랜잭션은 공중 전화망 (PSTN)을 통해 통화를 배치 하 고 수신 하는 기능을 확인 합니다.

이 가상 트랜잭션을 실행하려면 관리자가 다음을 구성해야 합니다.

  - Enterprise Voice에 대해 두 개의 테스트 사용자 (발신자 및 수신자)가 사용 하도록 설정 되어 있어야 합니다.

  - 각 사용자 계정에 대한 DID(Direct Inward Dialing) 번호

  - 수신자 번호에 대한 통화가 PSTN 게이트웨이에 연결되도록 하는 음성 정책 및 음성 경로

  - 통화를 허용하는 PSTN 게이트웨이 및 사용된 번호를 기반으로 수신자의 홈 풀로 통화를 라우팅하는 미디어

</div>

<div>

## <a name="unified-contact-store-synthetic-transactions"></a>통합 연락처 저장소 가상 트랜잭션

통합 연락처 저장소 가상 트랜잭션은 Lync Server 2013이 Microsoft Exchange Server 2013에서 사용자를 대신 하 여 연락처를 검색할 수 있는지 확인 합니다.

이 가상 트랜잭션을 사용하려면 다음 조건을 충족해야 합니다.

  - Lync server 2013 및 Exchange 2013 간에 [서버 간 인증 (OAuth) 및 파트너 응용 2013 프로그램 관리](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) 를 구성 해야 합니다.

  - 테스트 사용자에 게 유효한 Exchange 2013 사서함이 있어야 합니다.

이러한 조건이 충족되었으면 관리자가 다음 명령을 실행하여 SIP 주소 kenmyer@litwareinc.com의 사용자가 통합 연락처 저장소에서 자신의 연락처를 검색할 수 있는지 확인할 수 있습니다.

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer -Setup

이전 명령에서는 Setup 매개 변수가 사용되었습니다. Test-CsUnifiedContactStore를 실행할 때 Setup 매개 변수가 포함되었으면 지정된 사용자의 연락처(이 경우 sip:kenmyer@litwareinc.com)가 통합 연락처 저장소로 이동됩니다. 물론, 사용자의 연락처가 통합 연락처 저장소에 이미 있는 경우에는 이동할 필요가 없습니다. Setup 매개 변수는 일반적으로 한 번만 사용 되며 (첫 번째 테스트-Test-csunifiedcontactstore 실행), 테스트 사용자 에게만 사용 해야 합니다. 즉, 사용자 계정을 사용 하 여 Lync Server에 실제로 로그온 하지 않을 수 있습니다. 테스트 사용자가 통합 연락처 저장소로 마이그레이션된 후에는 Setup 매개 변수 없이 Test-CsUnifiedContactStore를 호출하여 사용자의 연락처를 검색할 수 있는지 확인할 수 있습니다.

    Test-CsUnifiedContactStore -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -RegistrarPort 5061 -Authentication TrustedServer

</div>

<div>

## <a name="xmpp-synthetic-transactions"></a>XMPP 가상 트랜잭션

XMPP(Extensible Messaging and Presence Protocol) IM 가상 트랜잭션을 사용하려면 하나 이상의 페더레이션 도메인에 XMPP 기능이 구성되어 있어야 합니다.

XMPP 가상 트랜잭션을 사용하도록 설정하려면 라우팅 가능한 XMPP 도메인의 사용자 계정을 XmppTestReceiverMailAddress 매개 변수에 제공해야 합니다. 예:

    Set-CsWatcherNodeConfiguration -Identity pool0.contoso.com -Tests @{Add="XmppIM"} -XmppTestReceiverMailAddress user1@litwareinc.com

이 예에서는 litwareinc.com에 대 한 메시지를 XMPP 게이트웨이로 라우팅하도록 Lync Server 2013 규칙을 만들어야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

