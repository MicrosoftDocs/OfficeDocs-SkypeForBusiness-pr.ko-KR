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
ms.openlocfilehash: afcf12b50a1284a7218789c5964ce714a3a4bdd7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41983143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a>Lync Server 2013에서 사용자 현재 상태 게시 및 구독 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-06-05_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우에는 사용자에 게 해당 cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsPresence 테스트 사용자 쌍이 Lync Server에 로그온 하 여 현재 상태 정보를 교환할 수 있는지 여부를 확인 하는 데 사용 됩니다. 이 작업을 위해 cmdlet은 먼저 두 사용자를 시스템에 로그온시킵니다. 두 로그온이 모두 성공하면 첫 번째 테스트 사용자가 두 번째 사용자로부터 현재 상태 정보를 받기 위해 요청합니다. 두 번째 사용자가 이 정보를 게시한 다음 Test-CsPresence는 정보가 첫 번째 사용자에게 성공적으로 전송되었는지 확인합니다. 현재 상태 정보를 교환 한 후에는 두 테스트 사용자가 Lync Server에서 로그 오프 됩니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsPresence은 미리 구성 된 테스트 계정 쌍 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예:

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다. 그런 다음 테스트-CsPresence 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

자세한 내용은 [테스트-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) 에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 현재 상태 정보를 교환할 수 있으면 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.3280315

오류

진단을

두 사용자가 현재 상태 정보를 교환할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 404, 찾을 수 없음

진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com

이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음

가.

Microsoft DiagnosticHeader

예를 들어 위의 출력에서는 두 사용자 계정 중 하나 이상이 올바르지 않아 테스트가 실패 했음을 나타냅니다. 계정이 없거나 Lync Server에 대해 사용 하도록 설정 되지 않았습니다. 다음과 같은 명령을 실행 하 여 해당 계정이 있는지 확인 하 고 Lync Server에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

테스트-CsPresence 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수가 포함 된 경우 테스트-CsPresence 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예:

알 수 없는 등록 요청 적중률

' 등록 ' 활동이 완료 되었습니다 (' 0.0345791 ' 초).

' SelfSubscribeActivity ' 활동이 시작 되었습니다.

' SelfSubscribeActivity ' 작업이 ' 0.0041174 ' 초에 완료 되었습니다.

' SubscribePresence ' 활동이 시작 되었습니다.

' SubscribePresence ' 작업이 ' 0.0038764 ' 초에 완료 되었습니다.

' 임-현재 상태 ' 활동이 시작 되었습니다.

예외 ' 현재 알림 '은 25 초 이내에 수신 되지 않습니다. SyntheticTransactions에서 STPresenceWorkflow 실행을 수행 했습니다.

현재 상태 알림이 25 초 이내에 수신 되지 않았다는 사실은 네트워크 문제로 인해 정보 교환이 차단 되는 것을 나타낼 수 있습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

다음은 테스트-CsPresence 발생할 수 있는 몇 가지 일반적인 이유입니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다. 사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

