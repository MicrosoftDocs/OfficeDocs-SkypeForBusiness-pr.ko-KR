---
title: 'Lync Server 2013: 사용자 현재 상태 게시 및 구독 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d506ed0115fd5346048ff8870763a7ffc888a69
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745298"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a>Lync Server 2013에서 사용자 현재 상태 게시 및 구독 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-06-05_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 테스트-CsPresence을 실행할 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsPresence 테스트 사용자 쌍이 Lync Server에 로그온 할 수 있는지 여부와 exchange 현재 상태 정보를 확인 하는 데 사용 됩니다. 이를 위해 cmdlet은 먼저 두 사용자를 시스템에 기록 합니다. 두 로그온이 모두 성공한 경우 첫 번째 테스트 사용자는 두 번째 사용자에 게 현재 상태 정보를 수신 하도록 요청 합니다. 두 번째 사용자는이 정보를 게시 하 고 테스트-CsPresence 정보가 첫 번째 사용자에 게 성공적으로 전송 되었는지 확인 합니다. 현재 상태 정보를 교환 한 후에는 Lync Server에서 두 테스트 사용자가 로그 오프 됩니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsPresence cmdlet은 한 쌍의 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예를 들면 다음과 같습니다.

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호를 포함 하는 개체)를 만들어야 합니다. 그런 다음 테스트를 호출할 때 다음과 같은 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

자세한 내용은 [테스트-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 현재 상태 정보를 교환할 수 있는 경우 다음과 유사한 출력을 받고 결과 속성이 성공으로 표시 됨 **:**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.3280315

오류

있게

두 명의 사용자가 현재 상태 정보를 교환할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 404, 찾을 수 없음

진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,

이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음

존재.

Microsoft DiagnosticHeader

예를 들어 이전 출력은 두 사용자 계정 중 적어도 하나가 유효 하지 않기 때문에 테스트가 실패 했음을 의미 합니다. 계정이 없거나 Lync Server에 대해 사용 하도록 설정 되지 않은 상태입니다. 계정이 있는지 확인 하 고 다음과 같은 명령을 실행 하 여 Lync Server에 대해 사용 하도록 설정 했는지 여부를 확인할 수 있습니다.

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

테스트-CsPresence이 실패할 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수가 포함 된 경우 테스트-CsPresence 지정 된 사용자가 Lync Server에 로그온 하는 기능을 확인할 때 시도한 각 작업에 대 한 단계별 계정을 반환 합니다. 예를 들면 다음과 같습니다.

등록 요청이 알 수 없는 것으로 적중 됨

' 등록 ' 활동이 완료 되었습니다 (' 0.0345791 ' 초).

' SelfSubscribeActivity ' 활동이 시작 되었습니다.

' SelfSubscribeActivity ' 활동이 ' 0.0041174 ' 초 후에 완료 되었습니다.

' SubscribePresence ' 활동이 시작 되었습니다.

' SubscribePresence ' 활동이 ' 0.0038764 ' 초 후에 완료 되었습니다.

' 없음 현재 상태 ' 활동이 시작 되었습니다.

예외 ' 현재 알림 '은 25 초 내에 수신 되지 않습니다. 워크플로 Microsoft SyntheticTransactions. STPresenceWorkflow 실행이 발생 했습니다.

현재 상태 알림이 25 초 내에 수신 되지 않은 경우 네트워크 문제로 인해 정보가 교환 되지 않는 것을 나타낼 수 있습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트 CsPresence 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다. Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

