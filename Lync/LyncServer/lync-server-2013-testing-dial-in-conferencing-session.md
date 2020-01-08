---
title: 'Lync Server 2013: 전화 접속 회의 세션 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing dial-in conferencing session
ms:assetid: 6c505be5-5af7-450c-b3ca-10d9122bee5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743834(v=OCS.15)
ms:contentKeyID: 63969613
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: efcc6d9277f7333989c59b812ed76087b9b6ca9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983484"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-dial-in-conferencing-session-in-lync-server-2013"></a>Lync Server 2013에서 전화 접속 회의 세션 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsDialInConferencing cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDialInConferencing&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트 CsDialInConferencing cmdlet은 사용자가 전화 접속 회의에 참가할 수 있는지 여부를 확인 합니다. 테스트 사용자는 시스템에 로그인 하 여 CsDialInConferencing 작동 합니다. 로그온에 성공 하면 cmdlet은 사용자의 자격 증명과 사용 권한을 사용 하 여 사용 가능한 모든 전화 접속 회의 액세스 번호를 사용해 봅니다. 각 전화 접속 시도의 성공 또는 실패에 대 한 설명이 표시 되 면 테스트 사용자는 Lync Server에서 로그 오프 됩니다. CsDialInConferencing는 적절 한 연결을 설정할 수 있는지만 확인 합니다. Cmdlet은 실제로 전화를 걸거나 다른 사용자가 참가할 수 있는 전화 접속 회의를 만들지 않습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트 CsDialInConferencing cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예를 들면 다음과 같습니다.

    Test-CsDialInConferencing -TargetFqdn "atl-cs-001.litwareinc.com" 

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 계정 이름과 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다. 그런 다음 해당 자격 증명 개체를 포함 하 고 계정 SIP는 호출 테스트-CsDialInConferencing에 대해 다음을 처리 해야 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsDialInConferencing -TargetFqdn atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

자세한 내용은 [테스트 CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/Test-CsDialInConferencing) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 Lync Server에 로그온 한 다음 사용 가능한 전화 접속 회의 액세스 번호 중 하나를 사용 하 여 연결할 수 있는 경우 다음과 유사한 출력을 받고 결과 속성이 성공으로 표시 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.8630376

오류

있게

지정 된 사용자가이 연결을 설정할 수 없는 경우에는 결과가 실패로 표시 되 고 다음과 같은 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 로그온이 거부 되었습니다. 적절 한 자격 증명이 있는지 확인 합니다.

사용 중이 고 계정이 활성 상태입니다.

내부 예외: NegotiateSecurityAssociation 실패, 오류:-

2146893044

있게

이전 출력은 테스트 사용자에 게 Lync Server 자체에 대 한 액세스가 거부 되었음을 나타냅니다. 이는 일반적으로 Test-CsDialInConferencing에 전달 된 사용자 자격 증명이 유효 하지 않음을 의미 합니다. 그런 다음 Windows PowerShell 자격 증명 개체를 다시 만들어야 합니다. 사용자 계정에 대 한 암호를 검색할 수 있지만 다음과 같은 명령을 사용 하 여 SIP 주소를 확인할 수 있습니다.

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트 CsDialInConferencing가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 유효 하지 않은 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다. Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.

  - 전화 접속 회의 액세스 번호가 올바르지 않을 수 있습니다. 다음 명령을 사용 하 여 현재 구성 된 전화 접속 회의 액세스 번호 목록을 반환할 수 있습니다.
    
        Get-CsDialConferencingAccessNumber

</div>

</div>

<span> </span>

</div>

</div>

</div>

