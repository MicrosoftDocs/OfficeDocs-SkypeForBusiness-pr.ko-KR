---
title: 'Lync Server 2013: 피어-투-피어 오디오/비디오 통화 테스트'
description: 'Lync Server 2013: 피어-투-피어 오디오/비디오 통화를 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03bab69d926a99c091a510ce64b78dbf505d4cbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556294"
---
# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Lync Server 2013에서 피어 투 피어 오디오/비디오 통화 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsP2PAV cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Test-CsP2PAV은 테스트 사용자 쌍이 피어 투 피어 A/V 대화에 참가할 수 있는지 여부를 확인 하는 데 사용 됩니다. 이 시나리오를 테스트 하기 위해 두 사용자에 게 Lync Server에 로그온 하 여 cmdlet이 해제 됩니다. 두 사용자 모두 로그온에 성공하면 첫 번째 사용자가 두 번째 사용자를 A/V 통화에 참가하도록 초대합니다. 두 번째 사용자가 통화를 수락하고, 두 사용자 간에 연결이 테스트되고, 통화가 종료된 후 테스트 사용자가 시스템에서 로그오프됩니다.

Test-CsP2PAV는 실제로 A/V 통화를 수행 하지 않습니다. 테스트 사용자 간에는 멀티미디어 정보가 교환 되지 않습니다. 대신, cmdlet은 적절 한 연결이 가능 하며 두 사용자가 이러한 통화를 수행할 수 있는지 확인 하기만 합니다.

자세한 내용은 [test-csp2pav](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Test-CsP2PAV cmdlet은 미리 구성 된 테스트 계정 쌍 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예제:

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 Lync Server 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다. 그런 다음 Test-csp2pav를 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

두 테스트 사용자가 피어 투 피어 A/V 통화를 완료할 수 있으면 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.8630376

오류

진단을

테스트 사용자가 통화를 완료할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 480, 일시적으로 사용할 수 없음

진단: ErrorCode = 15030, Source = atl-cs-001. litwareinc, 이유 = 실패

Exchange Server로 경로를 조정 하려면

Microsoft DiagnosticHeader

예를 들어 위의 출력에서는 Microsoft Exchange 서버에 연결할 수 없기 때문에 테스트가 실패 했다는 것을 나타냅니다. 이 오류 메시지는 일반적으로 Exchange 통합 메시징의 구성에 문제가 있음을 나타냅니다.

Test-CsP2PAV 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

Verbose 매개 변수를 포함 하면 Test-CsP2PAV에서 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인 한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 다음과 같은 진단으로 테스트가 실패 했다고 가정해 보겠습니다.

ErrorCode = 6003, Source = atl-cs-litwareinc, Reason = dialog 요청이 지원 되지 않음

Test-CsP2PAV를 다시 실행 하 고 Verbose 매개 변수를 포함 하면 다음과 같은 출력을 얻게 됩니다.

VERBOSE: ' 등록 ' 활동이 시작 되었습니다.

등록 요청을 보내는 중:

대상 Fqdn = atl-cs-011.litwareinc.com

사용자 Sip 주소 = sip:kenmyer@litwareinc.com

등록자 포트 = 5062.

인증 유형 ' IWA '이 선택 됩니다.

' 끝점을 등록할 수 없습니다. 구체적인 이유로 ErrorCode를 참조 하세요. ' SyntheticTransactions을 STP2PAVWorkflow 실행 하는 동안 발생 합니다.

즉시 확인 하지 못할 수도 있지만 출력을 주의 깊게 살펴보면 잘못 된 등록자 포트 (포트 5062)가 지정 되었음을 알 수 있습니다. 이로 인해 테스트가 실패 합니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Test-CsP2PAV 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

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

