---
title: 'Lync Server 2013: PSTN 피어 통화 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61c172ea79e646e9deec1c56e792d4e7c4df3a26
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050240"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Lync Server 2013에서 PSTN 피어 통화 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우에는 사용자에 게 테스트-CsPstnPeerToPeerCall cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할을 할당 받아야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsPstnPeerToPeerCall cmdlet은 사용자 쌍이 공중 전화망 (PSTN) 게이트웨이에서 피어 투 피어 통화를 수행 해야 하는 기능을 확인 합니다. 테스트-CsPstnPeerToPeerCall을 호출 하면 cmdlet은 먼저 두 테스트 사용자의 로그온을 Lync Server에 시도 합니다. 로그온이 성공 했다고 가정 하면 cmdlet은 사용자 1이 PSTN 게이트웨이를 통해 사용자 2에 게 전화를 걸기를 시도 합니다. 테스트-Cspstnpeertop이 통화는 다이얼 플랜, 음성 정책 및 테스트 사용자에 게 할당 된 기타 정책 및 구성 설정을 사용 하 여이 통화를 수행 합니다. 테스트를 계획 한 대로 진행 하는 경우 cmdlet은 사용자 2가 통화에 응답할 수 있는지 확인 한 다음 시스템에서 두 테스트 계정을 모두 로그 오프 합니다.

테스트-CsPstnPeerToPeerCall은 연결을 설정할 수 있는지 확인 하 고 네트워크를 통해 DTMF 코드를 전송 하 여 연결을 통해 미디어를 전송할 수 있는지 여부를 확인 하는 실제 전화 통화를 수행 합니다. 이 호출은 cmdlet 자체에 의해 응답 되며, 통화를 수동으로 종료 해야 하는 것은 아닙니다. 즉, 아무도 전화를 받은 다음 통화를 중단 해야 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsPstnPeerToPeerCall cmdlet은 미리 구성 된 테스트 계정 쌍 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예:

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다. 그런 다음 테스트-CsPstnPeerToPeerCall을 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

자세한 내용은 [테스트-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) cmdlet에 대 한 도움말 설명서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 피어 투 피어 통화를 완료할 수 있으면 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.8630376

오류

진단을

지정 된 사용자가 피어 투 피어 통화를 완료할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:0182361

오류: 403, 금지 됨

진단: ErrorCode = 12001, Source = atl-cs-001.litwareinc.com

이유 = 사용자 정책에 전화 경로 사용이 포함 되지 않음

이전 출력에서는 지정 된 사용자 중 하나 이상에 게 할당 된 음성 정책에 전화 사용이 포함 되지 않아 테스트가 실패 했다는 것을 나타냅니다. 전화 용도가 음성 경로에 음성 정책을 연결 합니다. 음성 정책 및 해당 하는 음성 경로를 모두 사용 하지 않으면 PSTN을 통해 전화를 걸 수 없습니다.

테스트-CsPstnPeerToPeerCall에 실패 한 경우 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수가 포함 된 경우 테스트-CsPstnPeerToPeerCall은 지정 된 사용자가 Lync Server에 로그온 할 수 있는 기능을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 다음 출력은 네트워크 문제로 인해 PSTN과의 연결이 차단 됨을 나타냅니다.

오디오 화상 통화를 ' sip: + 12065551219@litwareinc .com, user = phone '으로 설정 합니다.

네트워크에서 404 (찾을 수 없음) 응답이 수신 되었으며 작업에 실패 했습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

테스트-CsPstnPeerToPeerCall이 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다. 사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.

  - 지정 된 사용자에 게 할당 된 음성 정책에 유효한 PSTN 사용이 없습니다. 다음과 같은 명령을 사용 하 여 사용자에 게 할당 된 음성 정책을 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    그런 다음 사용자별 음성 정책 RedmondVoicePolicy에 대 한 정보를 검색 하는 다음과 같은 명령을 사용 하 여 해당 정책에 할당 된 PSTN 사용 (있는 경우)을 확인할 수 있습니다.
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

