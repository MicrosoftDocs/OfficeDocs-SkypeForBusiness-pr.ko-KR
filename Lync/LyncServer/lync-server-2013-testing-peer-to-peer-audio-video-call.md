---
title: 'Lync Server 2013: 피어 투 피어 오디오/비디오 통화 테스트'
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
ms.openlocfilehash: e319ace4ee4cc6613ac5ed29659ac14c5853d7b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Lync Server 2013에서 피어 투 피어 오디오/비디오 통화 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsP2PAV cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

CsP2PAV 테스트 사용자 쌍이 피어 투 피어 A/V 대화에 참여할 수 있는지 여부를 결정 하는 데 사용 됩니다. 이 시나리오를 테스트 하기 위해 두 사용자를 Lync Server에 로그인 하 여 cmdlet이 시작 됩니다. 두 번의 로그온이 성공할 경우 첫 번째 사용자는 두 번째 사용자를 초대 하 여 A/V 통화에 참가 합니다. 두 번째 사용자가 통화를 수락 하 고 두 사용자 간의 연결이 테스트 된 다음 통화가 종료 되 고 테스트 사용자가 시스템에서 로그 오프 됩니다.

테스트-CsP2PAV는 실제로 A/V 통화를 수행 하지 않습니다. 테스트 사용자 간에는 멀티미디어 정보가 교환 되지 않습니다. 대신 cmdlet은 적절 한 연결을 설정할 수 있고 두 사용자가 이러한 통화를 수행할 수 있다는 것만 확인 합니다.

자세한 내용은 [테스트 CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트 CsP2PAV cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예를 들면 다음과 같습니다.

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대 한 두 개의 Lync Server 자격 증명 개체 (계정 이름과 암호를 포함 하는 개체)를 만들어야 합니다. 그런 다음 Test-CsP2PAV를 호출할 때 두 계정의 SIP 주소와 이러한 자격 증명 개체를 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

두 테스트 사용자가 피어 투 피어 A/V 통화를 완료할 수 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.8630376

오류

있게

테스트 사용자가 통화를 완료할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 480, 일시적으로 사용할 수 없음

진단: ErrorCode = 15030, Source = atl-cs-001. litwareinc, 이유 = 실패

Exchange Server로 라우팅

Microsoft DiagnosticHeader

예를 들어 이전 출력은 Microsoft Exchange Server에 연결할 수 없기 때문에 테스트가 실패 했다는 것을 의미 합니다. 이 오류 메시지는 일반적으로 Exchange 통합 메시징의 구성 문제를 나타냅니다.

테스트-CsP2PAV 실패 한 경우에는 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

테스트-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

Verbose 매개 변수가 포함 된 경우 테스트-CsP2PAV는 지정 된 사용자가 Lync Server에 로그온 하는 기능을 확인 하 여 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 다음 진단으로 테스트가 실패 했다고 가정해 보겠습니다.

ErrorCode = 6003, Source = atl-cs-001. litwareinc, 이유 = 대화 상자 요청이 지원 되지 않음

Test-CsP2PAV를 다시 실행 하 고 Verbose 매개 변수를 포함 하면 다음과 유사한 출력이 표시 됩니다.

자세한 정보: ' Register ' 활동을 시작 했습니다.

등록 요청 전송 중:

대상 Fqdn = atl-cs-011.litwareinc.com

사용자 Sip 주소 = sip:kenmyer@litwareinc.com

등록자 포트 = 5062.

' IWA ' 인증 유형이 선택 되었습니다.

' 끝점을 등록할 수 없는 ' 예외입니다. 특정 이유는 ErrorCode를 참조 하세요. ' SyntheticTransactions STP2PAVWorkflow 실행 중에 발생 했습니다.

즉시 알 수 없는 경우 출력을 주의 깊게 살펴보면 잘못 된 등록자 포트 (포트 5062)가 지정 되었음을 알 수 있습니다. 결과적으로 테스트가 실패 합니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트 CsP2PAV가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

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

