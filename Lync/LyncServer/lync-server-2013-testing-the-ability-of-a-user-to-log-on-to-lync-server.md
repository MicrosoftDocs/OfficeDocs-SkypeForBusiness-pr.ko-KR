---
title: 'Lync Server 2013: 사용자가 Lync Server에 로그온 하는 기능 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: adf6cae2899d08765faf5d605ea20ae111f395ce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>사용자의 Lync Server 2013 로그온 기능 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 테스트 CsRegistration cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsRegistration cmdlet을 사용 하 여 조직의 사용자가 Lync Server에 로그온 할 수 있는지 확인 합니다. 테스트-CsRegistration을 실행할 때 cmdlet이 테스트 사용자에 게 Lync Server에 로그인 한 다음 성공한 경우 시스템에서 해당 테스트 사용자의 연결을 끊습니다. 이러한 모든 작업은 사용자 개입 없이, 실제 사용자에 게는 영향을 주지 않습니다. 예를 들어 테스트 계정 sip:kenmyer@litwareinc.com 실제 Lync Server 계정이 있는 실제 사용자에 해당 한다고 가정 합니다. 이 경우 실제: 진구 Myer에 대 한 장애 없이 테스트를 수행 합니다. : 진구 Myer 테스트 계정이 시스템에서 로그 오프할 때: 진구 Myer 해당 사용자는 로그온 된 상태로 유지 됩니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsRegistration cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 등록자 풀의 FQDN만 지정 하면 됩니다. 예를 들면 다음과 같습니다.

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다. 그런 다음 테스트-CsRegistration을 호출할 때 해당 자격 증명 개체와 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

자세한 내용은 [테스트 CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 Lync Server에 로그온 한 다음 로그 오프할 수 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.8630376

오류

있게

지정 된 사용자가 로그인 하거나 로그 아웃할 수 없는 경우에는 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 404, 찾을 수 없음

진단: ErrorCode = 1003, source = atl-cs-001. litwareinc, 이유 = 사용자가 없습니다.

없음

Microsoft DiagnosticHeader

예를 들어 이전 출력은 지정 된 사용자를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 보여 줍니다. 이 명령을 실행 하 여 SIP 주소가 유효한 지 (그리고 sip 주소를 사용 하도록 설정 된 사용자에 게 있는지 여부)를 확인할 수 있습니다.

    Get-CsUser "sip:kenmyer@litwareinc.com"

테스트-CsRegistration이 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수를 포함 하는 경우 테스트-CsRegistration은 지정 된 사용자가 Lync Server에 로그온 하는 기능을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들면 다음과 같습니다.

자세한 정보: ' Register ' 활동을 시작 했습니다.

등록 요청 전송 중:

대상 Fqdn = atl-cs-011.litwareinc.com

사용자 Sip 주소 = sip:kenmyer@litwareinc.com

등록자 포트 = 5061.

인증 유형 ' 신뢰 됨 '이 선택 되었습니다.

' 종점이 등록할 수 없는 ' 예외입니다. 워크플로 SyntheticTransactions가 실행 되는 동안 특정 이유로 인해 ErrorCode에 대 한 오류 발생을 확인 하세요.

예외 호출 스택: Microsoft SipAsyncResult'1. ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트-CsRegistration이 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다. Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.

  - 잘못 된 등록자 풀을 지정 했습니다. 다음 명령을 사용 하 여 등록자 풀의 Fqdn을 반환할 수 있습니다.
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - 현재 등록자 풀을 사용할 수 없습니다. 풀을 ping 하 여 응답 여부를 확인 하세요.
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

