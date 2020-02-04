---
title: 'Lync Server 2013: 오디오/비디오 회의의 유효성 검사'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89bb8f38ea650bf64179b917b227d7ccaaf10791
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763652"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>Lync Server 2013에서 오디오/비디오 회의의 유효성 검사

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
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>확인 일정</p></td>
<td><p>Daily</p></td>
</tr>
<tr class="odd">
<td><p>테스트 도구</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>권한이 필요 함</p></td>
<td><p>Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자는 테스트-CsAVConference cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsAVConference cmdlet은 두 테스트 사용자가 오디오/비디오 (A/V) 회의에 참가할 수 있는지 여부를 확인 합니다. Cmdlet이 실행 되 면 두 사용자가 시스템에 로그온 됩니다. 성공적으로 로그인 한 후에는 첫 번째 사용자가 A/V 회의를 만든 다음 두 번째 사용자가 해당 회의에 참가할 때까지 기다립니다. 간단한 데이터 교환 후 회의가 삭제 되 고 두 테스트 사용자가 로그 오프 됩니다.

테스트-CsAVConference는 두 테스트 사용자 간의 실제 A/V 회의를 수행 하지 않습니다. 대신, cmdlet은 두 사용자가 이러한 회의를 수행 하는 데 필요한 모든 연결을 수행할 수 있는지 확인 합니다.

이 명령에 대 한 추가 예제는 [테스트-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)에서 찾을 수 있습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 두 명의 사용자 계정 중 하나를 사용 하 여 CsAVConference cmdlet을 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예를 들면 다음과 같습니다.

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호를 포함 하는 개체)를 만들어야 합니다. 그런 다음 해당 자격 증명 개체와 두 계정의 SIP 주소를 테스트-CsAVConference를 호출할 때 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

자세한 내용은 [CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 A/V 회의를 성공적으로 완료할 수 있는 경우 다음과 비슷한 출력이 표시 되 고 결과 속성이 성공으로 표시 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:02.6841765

오류

있게

사용자가 회의를 완료할 수 없는 경우에는 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 404, 찾을 수 없음

진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,

이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음

존재.

Microsoft DiagnosticHeader

예를 들어 이전 출력에서는 두 사용자 계정 중 적어도 하나가 유효 하지 않기 때문에 (계정이 없거나 해당 계정이 Lync Server에 대해 사용 하도록 설정 되지 않았기 때문에) 테스트가 실패 했음을 명시 합니다. 다음과 같은 명령을 실행 하 여 두 개의 테스트 계정이 있는지, Lync Server에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

테스트-CsAVConference에 오류가 발생 하면 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수를 포함 하는 경우 테스트-CsAVConference는 지정 된 사용자가 AV 회의에 참여 하는 기능을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 테스트에 실패 하 고 다음 진단이 표시 된다고 가정 합니다.

ErrorCode = 1008, Source = accessproxy. litwareinc, Reason = DNS SRV 레코드를 확인할 수 없습니다.

Verbose 매개 변수를 사용 하 여 테스트를 다시 실행 하는 경우 반환 되는 단계별 정보에는 다음과 같은 출력이 포함 됩니다.

자세한 정보: ' Register ' 활동을 시작 했습니다.

등록 요청 전송 중:

대상 Fqdn = atl-cs-001.litwareinc.com

사용자 Sip 주소 = sip:davidlongmire@litwareinc.com

등록자 포트 = 5061.

인증 유형 ' 신뢰 됨 '이 선택 되었습니다.

' 등록 ' 활동이 시작 되었습니다.

등록 요청 전송 중:

대상 Fqdn = atl-cs-001.litwareinc.com

사용자 Sip 주소 = sip:kenmyer@litwareinc.com

등록자 포트 = 5061.

인증 유형 ' 신뢰 됨 '이 선택 되었습니다.

' 끝점을 등록할 수 없는 ' 예외입니다. 특정 이유는 ErrorCode를 참조 하세요. ' 워크플로 중 발생

해당 출력의 마지막 줄은 사용자 sip:kenmyer@litwareinc.com Lync Server를 사용 하 여 등록할 수 없음을 나타냅니다. 즉, SIP 주소 sip:kenmyer@litwareinc.com이 유효한 지, 그리고 연결 된 사용자가 Lync Server에 대해 설정 되어 있는지 확인 해야 합니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트-CsAVConference가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 유효 하지 않은 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
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

