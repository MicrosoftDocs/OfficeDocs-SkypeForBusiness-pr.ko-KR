---
title: 'Lync Server 2013: XMPP를 사용 하 여 메시징 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing messaging using XMPP
ms:assetid: ae5305ba-e5fc-4ca0-a805-872b4ebaf981
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727312(v=OCS.15)
ms:contentKeyID: 63969641
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3ee4dc939ae0fbc1e62c30bb7dd431d3d940f6c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-messaging-using-xmpp-in-lync-server-2013"></a>Lync Server 2013에서 XMPP를 사용 하 여 메시징 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-11-03_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>확인 일정</p></td>
<td><p>매일</p></td>
</tr>
<tr class="even">
<td><p>테스트 도구</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>필요한 권한</p></td>
<td><p>Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우에는 사용자에 게 <strong>CsXmppIM</strong> 을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsXmppIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

XMPP(Extensible Messaging and Presence Protocol)는 인터넷에서 메시지를 보내는 데 사용되는 XML 기반 표준 통신 프로토콜입니다. XMPP는 원래 Jabber로 명명 되었으며, 여러 인터넷 메시징 및 정보 교환 프로그램 (예: Google 대화 및 Facebook 채팅)에서 지원 됩니다. **테스트-CsXmppIM** cmdlet은 사용자가 xmpp 네트워크에 있는 사용자와 인스턴트 메시지를 교환할 수 있는지 확인 합니다. 이 테스트를 제대로 수행 하려면 XMPP 사용자에 대 한 유효한 SIP 주소가 있어야 하며 허용 되는 XMPP 파트너로 구성 된 네트워크에 해당 SIP 주소가 있어야 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

다음 예에서는 atl-cs-001.litwareinc.com 풀에 대 한 XMPP 인스턴트 메시징 기능을 확인 합니다. 이 명령은 atl-cs-001.litwareinc.com 풀에 대해 테스트 사용자가 정의 된 경우에만 작동 합니다. 이러한 경우에는 첫 번째 테스트 사용자가 SIP 주소 adelaney@contoso.com을 가진 사용자에 게 XMPP 인스턴트 메시지를 보낼 수 있는지 여부를 확인 합니다.

테스트 사용자가 정의 되어 있지 않으면 어떤 사용자로 로그온 하는지 알 수 없으므로 명령이 실패 합니다. 풀에 대해 테스트 사용자를 정의 하지 않은 경우에는 UserSipAddress 매개 변수 및 해당 명령을 사용 하 여 로그온 할 때 사용할 사용자의 자격 증명을 포함 해야 합니다.

    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com"

다음 예에 표시 된 명령은 특정 사용자 (litwareinc\\pilar)가 로그온 하 여 사용자 adelaney@contoso.com에 xmpp 인스턴트 메시지를 보내는 기능을 테스트 합니다. 이 작업을 수행 하기 위해이 예제의 첫 번째 명령은 Get-Credential cmdlet을 사용 하 여 user Pilar Ackerman의 이름과 암호가 포함 된 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다. (로그온 이름 litwareinc\\pilar는 매개 변수로 포함 되었기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에만 관리자가 Pilar Ackerman 계정의 암호를 입력 하면 됩니다.) 그런 다음 결과 credential 개체는 $cred 1 이라는 변수에 저장 됩니다.

두 번째 명령은이 사용자가 atl-cs-001.litwareinc.com 풀에 로그온 하 여 XMPP 인스턴트 메시지를 보낼 수 있는지 여부를 확인 합니다. 이 작업을 실행 하기 위해 **테스트-CsXmppIm** cmdlet은 네 개의 매개 변수와 함께 targetfqdn (등록자 풀의 FQDN)과 함께 호출 됩니다. 수신자 (메시지를 보내는 사용자의 SIP 주소)입니다. UserCredential (Pilar Ackerman의 사용자 자격 증명을 포함 하는 Windows PowerShell 개체) 및 UserSipAddress (제공 된 사용자 자격 증명에 해당 하는 SIP 주소)

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsXmppIM -TargetFqdn "atl-cs-001.litwareinc.com" -Receiver "adelany@contoso.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

XMPP 인스턴트 메시징이 올바르게 구성 된 경우 결과 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:02.5361946

오류 메시지:

진단을

지정 된 사용자가 XMPP 인스턴트 메시징을 사용할 수 없으면 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

경고: 지정한 정규화 된 자격에 대 한 등록자 포트 번호를 읽지 못했습니다.

FQDN (도메인 이름) 기본 등록자 포트 번호 사용 오류

InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

구독자

SyntheticTransactions SipSyntheticTransaction TryRetri를 관리 합니다.

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.

일정 시간 후에 올바르게 응답 하지 않았거나

연결 된 호스트에서 연결이 실패 했습니다.

10.188.116.96에 응답 하지 못했습니다. 5061

내부 예외:

일정 기간 후에 연결 된 파티가 제대로 응답 하지 않음

연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.

에서 10.188.116.96에 응답 하지 못했습니다. 5061

진단을

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

**Test-CsXmppIM** 이 실패할 수 있는 일반적인 이유는 다음과 같습니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - XMPP 게이트웨이 구성이 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[설정-CsXmppGatewayConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsXmppGatewayConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

