---
title: 'Lync Server 2013: 사용자가 Lync Server에 로그온 할 수 있는지 테스트'
description: 'Lync Server 2013: 사용자가 Lync Server에 로그온 할 수 있는지 여부를 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b86ae3e490af0b361799ed5fb3f56ed4de42c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556214"
---
# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Lync Server 2013에 로그온 하는 사용자 기능 테스트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsRegistration cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Test-CsRegistration cmdlet을 사용 하 여 조직의 사용자가 Lync Server에 로그온 할 수 있는지 확인 합니다. 테스트-CsRegistration을 실행할 때 cmdlet은 테스트 사용자에 게 Lync Server에 로그인을 시도 하 고 성공한 경우 시스템에서 해당 테스트 사용자의 연결을 끊습니다. 이 작업은 모두 사용자 상호 작용 없이, 실제 사용자에게 영향을 미치지 않고 수행됩니다. 예를 들어 테스트 계정 sip:kenmyer@litwareinc.com 실제 Lync Server 계정을 가진 실제 사용자에 해당 한다고 가정 합니다. 이 경우 실제 Ken Myer를 방해하지 않고 테스트가 수행됩니다. Ken Myer 테스트 계정이 시스템에서 로그오프해도 사람 Ken Myer는 계속 로그온 상태로 남아 있게 됩니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Test-CsRegistration cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 등록자 풀의 FQDN만 지정 하면 됩니다. 예제:

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호가 포함 된 Windows PowerShell 자격 증명 개체를 만들어야 합니다. 그런 다음 테스트-CsRegistration을 호출할 때 해당 자격 증명 개체와 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

자세한 내용은 [테스트-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 Lync Server에 로그온 한 다음 로그 오프할 수 있는 경우 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.8630376

오류

진단을

지정 된 사용자가 로그인 하거나 로그 아웃할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 404, 찾을 수 없음

진단: ErrorCode = 1003, source = atl-cs-litwareinc, 이유 = 사용자가 수행 합니다.

존재 하지 않음

Microsoft DiagnosticHeader

예를 들어 위의 출력에서는 지정 된 사용자를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 나타냅니다. 다음 명령을 실행 하 여 SIP 주소가 유효한 지 여부와 해당 SIP 주소를 할당 한 사용자가 Lync Server에 대해 사용 되는지 여부를 확인할 수 있습니다.

    Get-CsUser "sip:kenmyer@litwareinc.com"

Test-CsRegistration 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수를 포함 하면 Test-CsRegistration는 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예제:

VERBOSE: ' 등록 ' 활동이 시작 되었습니다.

등록 요청을 보내는 중:

대상 Fqdn = atl-cs-011.litwareinc.com

사용자 Sip 주소 = sip:kenmyer@litwareinc.com

등록자 포트 = 5061.

' 신뢰할 수 있음 ' 인증 유형을 선택 합니다.

' 끝점이 등록할 수 없습니다. ' 예외가 발생 했습니다. SyntheticTransactions 실행 중에 특정 이유로 인해 발생 한 오류에 대 한 ErrorCode를 참조 하세요.

예외 호출 스택: SipAsyncResult'1에서 ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Test-CsRegistration 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다. 사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.

  - 잘못 된 등록자 풀을 지정 했습니다. 다음 명령을 사용 하 여 등록자 풀의 Fqdn을 반환할 수 있습니다.
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - 등록자 풀은 현재 사용할 수 없습니다. 풀에 ping을 사용해 서 응답 하는지 확인 합니다.
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

