---
title: 'Lync Server 2013: 영구 채팅 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing persistent chat
ms:assetid: d351b6f2-bc31-42e0-9e8d-c347713d6b4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727313(v=OCS.15)
ms:contentKeyID: 63969651
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78e756de75dda7d7b0a96d9a49233818a5c86576
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-persistent-chat-in-lync-server-2013"></a>Lync Server 2013에서 영구 채팅 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-11-03_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>확인 일정</p></td>
<td><p>Daily</p></td>
</tr>
<tr class="even">
<td><p>테스트 도구</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>권한이 필요 함</p></td>
<td><p>Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>CsPersistentChatMessage</strong> cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPersistentChatMessage&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**CsPersistentChatMessage** cmdlet은 테스트 사용자 쌍이 영구 채팅 서비스를 사용 하 여 메시지를 교환할 수 있는지 확인 합니다. 이를 위해 cmdlet은 두 사용자를 Lync Server 2013에 기록 하 고, 사용자를 영구 채팅방에 연결 하 고, 한 쌍의 메시지를 교환 한 다음 채팅방을 종료 하 고 두 사용자를 로그 오프 합니다. 채팅방을 만들지 않은 경우 또는 두 테스트 사용자 계정에 영구 채팅 서비스에 대 한 액세스를 제공 하는 영구 채팅 정책이 할당 되지 않은 경우에는이 cmdlet에 대 한 호출이 실패 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

다음 예제에 표시 된 명령은 litwareinc\\pilar 및 litwareinc\\kenmyer) 사용자 쌍을 테스트 하 여 Lync Server 2013에 로그온 한 다음 영구 채팅 서비스를 사용 하 여 메시지를 교환할 수 있습니다. 이렇게 하려면이 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자 Pilar Ackerman의 이름과 암호를 포함 하는 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다. (로그온 이름 litwareinc\\pilar는 매개 변수로 포함 되어 있기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에는 관리자만 Pilar Ackerman 계정에 대 한 암호를 입력 해야 합니다.) 그런 다음 결과 자격 증명 개체가 $cred 1 이라는 변수에 저장 됩니다. 두 번째 명령은: 진구 Myer account에 대 한 credential 개체를 반환 하는 것과 동일한 작업을 수행 합니다.

자격 증명 개체를 사용 하는 경우 세 번째 명령은이 두 사용자가 영구 채팅을 사용 하 여 Lync Server 2013에 로그온 할 수 있는지 여부를 결정 합니다. 이 작업을 수행 하려면 다음 매개 변수를 사용 하 여 **CsPersistentChatMessage** cmdlet을 호출 합니다. targetfqdn (등록자 풀의 FQDN). SenderSipAddress (첫 번째 테스트 사용자의 SIP 주소). SenderCredential (이 사용자에 대 한 자격 증명이 포함 된 Windows PowerShell 개체) ReceiverSipAddress (다른 테스트 사용자의 SIP 주소). 및 ReceiverCredential (다른 테스트 사용자를 위한 자격 증명을 포함 하는 Windows PowerShell 개체).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    
    Test-CsPersistentChatMessage -TargetFqdn atl-persistentchat-001.litwareinc.com -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $cred1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자에 게 유효한 위치 정책이 있는 경우 다음과 유사한 출력을 받고 결과 속성이 **성공**으로 표시 됨:

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:00

오류 메시지:

있게

지정 된 사용자가 영구 채팅 서비스를 사용 하 여 메시지를 교환할 수 없는 경우 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

경고: 정규화 된 정식 #b0에 대 한 등록자 포트 번호를 읽지 못했습니다.

도메인 이름 (FQDN). 기본 등록자 포트 번호를 사용 합니다. 발생

InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

배포자

SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.

일정 시간 후에 제대로 응답 하지 않았거나

연결 된 호스트가 다음 연결에 실패 하 여 성립

2001:4898 \[: e8: f39e: 5c9a: ad83:81b3:9944\]: 5061에 응답 하지 못했습니다.

내부 예외: 다음 이유로 인해 연결 시도가 실패 했습니다.

연결 된 상대방이 일정 기간 후에 적절 하 게 응답 하지 않았습니다.

연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.

님이 응답 하지 못했습니다

\[2001:4898: e8: f39e: 5c9a: ad83:81b3:9944\]: 5061

있게

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

**테스트 CsPersistentChatMessage** 가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 필요한 테스트 계정이 없거나 올바르게 생성 되지 않았을 수 있습니다.

  - 네트워크 문제로 인해 테스트에 시간이 초과 되어 예기치 않은 지연이 발생할 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[부여-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsPersistentChatPolicy)  
[New-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsPersistentChatPolicy)  
[Set-CsPersistentChatPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsPersistentChatPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

