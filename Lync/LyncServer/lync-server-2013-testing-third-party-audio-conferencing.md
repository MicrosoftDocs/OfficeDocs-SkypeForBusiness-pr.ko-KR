---
title: 'Lync Server 2013: 타사 오디오 회의 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing third-party audio conferencing
ms:assetid: 0428eb2f-a5ce-47e5-9ea4-383965dfc1e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727299(v=OCS.15)
ms:contentKeyID: 63969576
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a90aab3b0aec4fce46b311baccd0f28f2e7101b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745448"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Lync Server 2013에서 타사 오디오 회의 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-11-01_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsAudioConferencingProvider cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

오디오 회의 공급자는 조직에서 회의 서비스를 제공 하는 타사 회사입니다. 다른 요인 중에서 오디오 회의 공급자는 사용자를 사이트 외부에 배치 하 고 회사 네트워크나 인터넷에 연결 되지 않은 상태에서 컨퍼런스 또는 모임의 오디오 부분에 참가할 수 있도록 합니다. 오디오 회의 공급자는 live 번역, 기록, 실시간 컨퍼런스 연산자 지원과 같은 고급 서비스를 제공 하는 경우가 많습니다.

**CsAudioConferencingProvider** cmdlet은 사용자가 자신의 오디오 회의 공급자에 연결할 수 있는지 여부를 확인 하는 데 사용 됩니다. 이 cmdlet은 다음 두 가지 방법 중 하나로 실행할 수 있습니다. 대부분의 관리자는 CsHealthMonitoringConfiguration cmdlet을 사용 하 여 각 등록자 풀에 대 한 테스트 사용자를 설정 합니다. 이러한 테스트 사용자는 가상 트랜잭션과 함께 사용 하도록 미리 구성한 사용자 계정 쌍을 나타냅니다. 일반적으로 이러한 계정은 테스트 계정이 며 실제 사용자에 속하는 계정이 아닙니다. 테스트 사용자가 풀에 대해 구성 되어 있는 경우 관리자는 테스트에 관련 된 사용자 계정에 대 한 id를 지정 (및 자격 증명 제공) 할 필요 없이 해당 풀에 대해 **CsAudioConferencingProvider** cmdlet을 실행할 수 있습니다.

또는 관리자가 실제 사용자 계정을 사용 하 여 **CsAudioConferencingProvider** cmdlet을 실행할 수 있습니다. 실제 사용자 계정을 사용 하 여 테스트를 수행 하기로 결정 한 경우 해당 계정에 대 한 로그온 이름과 암호를 제공 해야 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

예제 1에서는 풀 atl-cs-001.litwareinc.com에 대해 정의 된 테스트 사용자가 자신의 오디오 회의 공급자에 연결할 수 있는지 확인 합니다. 이 명령을 사용 하려면 풀에 대해 하나 이상의 테스트 사용자를 정의 해야 합니다. Atl-cs-001.litwareinc.com에 대해 정의 된 테스트 사용자가 없는 경우 명령이 실패 합니다. 이는 테스트에서 **CsAudioConferencingProvider** cmdlet이 테스트에 어떤 사용자를 사용 해야 하는지 알 수 없기 때문입니다. 풀에 대 한 테스트 사용자를 정의 하지 않은 경우 오디오 회의 공급자와의 연결을 확인할 때 명령에 사용할 사용자 계정의 자격 증명과 UserSipAddress 매개 변수를 포함 해야 합니다.

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

예제 2에 표시 된 명령은 특정 사용자 (litwareinc\\kenmyer)가 자신의 오디오 회의 공급자에 연결 하는 기능을 테스트 합니다. 이렇게 하려면이 예제의 첫 번째 명령은 Get-Credential cmdlet을 사용 하 여 사용자: 진구 Myer의 이름 및 암호를 포함 하는 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다. (로그온 이름 litwareinc\\kenmyer 매개 변수로 포함 되어 있기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에는 관리자만: 진구 Myer 계정에 대 한 암호를 입력 해야 합니다.) 결과 자격 증명 개체는 $credential 라는 변수에 저장 됩니다.

두 번째 명령은이 사용자가 오디오 회의 공급자에 연결할 수 있는지 여부를 확인 합니다. 이 작업을 수행 하기 위해 CsAudioConferencingProvider cmdlet이 세 가지 매개 변수 (TargetFqdn (등록자 풀의 FQDN)와 함께 호출 됩니다. UserCredential (: 진구 Myer의 사용자 자격 증명을 포함 하는 Windows PowerShell 개체) 및 UserSipAddress (제공 된 사용자 자격 증명에 해당 하는 SIP 주소).

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

오디오 회의 공급자가 올바르게 구성 되 면 다음과 비슷한 출력이 표시 되 고 결과 속성이 성공으로 표시 됩니다 **.**

대상 Fqdn: atl-sql-001.litwareinc.com

결과: 성공

대기 시간: 00:00:00

오류 메시지:

있게

지정 된 사용자가 로그온 하거나 로그 오프할 수 없는 경우에는 결과가 **오류로**표시 되 고 다음과 같은 오류 및 진단 속성에 추가 정보가 기록 됩니다.

대상 Fqdn: atl-sql-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.

일정 시간 후에 제대로 응답 하지 않았거나

연결 된 호스트가 다음 연결에 실패 하 여 성립

2001:4898 \[: e8: f39e: 5c9a: ad83:81b3:9944\]: 5061에 응답 하지 못했습니다.

내부 예외: 다음 이유로 인해 연결 시도가 실패 했습니다.

연결 된 상대방이 일정 기간 후에 적절 하 게 응답 하지 않았습니다.

연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.

님이 응답 하지 못했습니다

\[2001:4898: e8: f39e: 5c9a: ad83:81b3:9944\]: 5061

있게

예를 들어 이전 출력에는 일반적으로 Edge 서버에 문제가 있음을 나타내는 "연결 된 파티가 제대로 응답 하지 않았습니다." 메모가 포함 됩니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

**테스트 CsAudioConferencingProvider** 가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 앞의 예제에서와 같이 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - CsAudioConferencingProvider cmdlet이 **사용** 하는 사용자에 게 오디오 회의 공급자가 지정 되지 않은 경우 테스트에 실패 합니다.

  - Edge 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

