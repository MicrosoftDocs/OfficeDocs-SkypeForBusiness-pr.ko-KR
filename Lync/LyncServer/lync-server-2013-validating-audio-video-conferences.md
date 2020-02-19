---
title: 'Lync Server 2013: 오디오/비디오 회의 확인'
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
ms.openlocfilehash: babd9ce23a9d7e80875fc455e92c51ea9bd47493
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42113431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>Lync Server 2013에서 오디오/비디오 회의 확인

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
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>확인 일정</p></td>
<td><p>매일</p></td>
</tr>
<tr class="odd">
<td><p>테스트 도구</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>필요한 권한</p></td>
<td><p>Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 CsAVConference cmdlet을 실행 하는 권한이 있는 RBAC 역할이 할당 되어야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsAVConference cmdlet은 두 테스트 사용자가 A/V (오디오/비디오) 회의에 참가할 수 있는지 여부를 확인 합니다. cmdlet이 실행되면 두 사용자가 시스템에 로그온됩니다. 로그온 한 후에는 첫 번째 사용자가 A/V 회의를 만든 다음 두 번째 사용자가 해당 회의에 참가 하는 것을 기다립니다. 간단한 데이터 교환 후 전화 회의가 삭제되고 두 테스트 사용자가 로그오프됩니다.

CsAVConference는 두 테스트 사용자 간의 실제 A/V 회의를 수행 하지 않습니다. 대신, cmdlet은 두 사용자가 이러한 회의를 수행 하는 데 필요한 모든 연결을 수행할 수 있는지 확인 합니다.

이 명령에 대 한 추가 예는 [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)에서 찾을 수 있습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

CsAVConference cmdlet은 미리 구성 된 테스트 계정 쌍 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다. 그런 다음 이러한 자격 증명 개체와 두 계정의 SIP 주소를 테스트-CsAVConference를 호출할 때 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

자세한 내용은 [CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 A/V 회의를 성공적으로 완료할 수 있으면 다음과 비슷한 출력을 받게 되며 Result 속성은 Success로 표시 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:02.6841765

오류

진단을

사용자가 회의를 완료할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 404, 찾을 수 없음

진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com

이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음

가.

Microsoft DiagnosticHeader

예를 들어 이전 출력은 계정이 없거나 Lync Server에 대해 계정이 사용 하도록 설정 되지 않았으므로 두 사용자 계정 중 하나 이상이 올바르지 않아 테스트가 실패 했음을 나타냅니다. 다음과 같은 명령을 실행 하 여 두 테스트 계정이 있는지, 그리고 Lync Server에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

테스트-CsAVConference 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수를 포함 하는 경우-CsAVConference는 지정 된 사용자가 AV 회의에 참가 하는 기능을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 테스트가 실패 하 고 다음과 같은 진단이 수신 된다고 가정해 봅니다.

ErrorCode = 1008, Source = accessproxy litwareinc, Reason = DNS SRV 레코드를 확인할 수 없음

Verbose 매개 변수를 사용 하 여 테스트를 다시 실행 하면 반환 되는 단계별 정보는 다음과 같습니다.

VERBOSE: ' 등록 ' 활동이 시작 되었습니다.

등록 요청을 보내는 중:

대상 Fqdn = atl-cs-001.litwareinc.com

사용자 Sip 주소 = sip:davidlongmire@litwareinc.com

등록자 포트 = 5061.

' 신뢰할 수 있음 ' 인증 유형을 선택 합니다.

' 등록 ' 활동이 시작 되었습니다.

등록 요청을 보내는 중:

대상 Fqdn = atl-cs-001.litwareinc.com

사용자 Sip 주소 = sip:kenmyer@litwareinc.com

등록자 포트 = 5061.

' 신뢰할 수 있음 ' 인증 유형을 선택 합니다.

' 끝점을 등록할 수 없습니다. 구체적인 이유로 ErrorCode를 참조 하세요. ' 워크플로 도중 발생 함

이 출력에서 마지막 줄은 사용자 sip:kenmyer@litwareinc.com이 Lync Server에 등록할 수 없음을 나타냅니다. 즉, SIP 주소 sip:kenmyer@litwareinc.com가 유효 하며 연결 된 사용자가 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 해야 합니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Test-CsAVConference 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

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

