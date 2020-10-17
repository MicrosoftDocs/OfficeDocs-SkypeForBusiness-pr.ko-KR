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
ms.openlocfilehash: 51f728bfb5617185bdd9a1ef3b5f21b3e12ca61f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503935"
---
# <a name="testing-third-party-audio-conferencing-in-lync-server-2013"></a>Lync Server 2013에서 타사 오디오 회의 테스트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-11-01_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsAudioConferencingProvider cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAudioConferencingProvider&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

오디오 회의 공급자는 조직에 회의 서비스를 제공하는 타사입니다. 특히 외부에 있거나 회사 네트워크 또는 인터넷에 연결되지 않은 사용자는 오디오 회의 공급자를 통해 회의 또는 모임의 오디오 부분에 참여할 수 있습니다. 오디오 회의 공급자는 실시간 번역, 기록 및 회의별 실시간 운영자 지원과 같은 고급 서비스를 제공합니다.

**Test-csaudioconferencingprovider** cmdlet은 사용자가 자신의 오디오 회의 공급자에 연결할 수 있는지 확인 하는 데 사용 됩니다. 이 cmdlet은 두 가지 방법 중 하나로 실행할 수 있습니다. 대부분의 관리자는 CsHealthMonitoringConfiguration cmdlet을 사용하여 각각의 해당 등록자 풀에 대해 테스트 사용자를 설정합니다. 이러한 테스트 사용자는 가상 트랜잭션에 사용하도록 미리 구성된 한 쌍의 사용자 계정을 나타냅니다. 일반적으로 테스트 계정이 며 실제 사용자에 게 속하는 계정이 아닙니다. 테스트 사용자가 풀에 대해 구성 된 경우 관리자는 테스트에 포함 된 사용자 계정에 대 한 id를 지정 하지 않고도 해당 풀에 대해 **test-csaudioconferencingprovider** cmdlet을 실행할 수 있습니다.

또는 관리자가 실제 사용자 계정을 사용 하 여 **test-csaudioconferencingprovider** cmdlet을 실행할 수도 있습니다. 실제 사용자 계정을 사용하여 테스트를 수행하려는 경우 해당 계정에 대한 로그온 이름 및 암호를 제공해야 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

예제 1에서는 atl-cs-001.litwareinc.com 풀에 대해 정의된 테스트 사용자가 오디오 회의 공급자에 연결할 수 있는지를 확인합니다. 이 명령을 실행하려면 풀에 대해 테스트 사용자를 한 명 이상 정의해야 합니다. Atl-cs-001.litwareinc.com에 대해 정의 된 테스트 사용자가 없는 경우에는 명령이 실패 합니다. 이는 **test-csaudioconferencingprovider** cmdlet이 테스트에서 어떤 사용자를 사용할 것인지 알 수 없기 때문입니다. 풀에 대해 테스트 사용자를 정의하지 않은 경우에는 오디오 회의 공급자와의 연결을 확인할 때 명령이 사용해야 하는 사용자 계정의 자격 증명과 UserSipAddress 매개 변수를 포함해야 합니다.

    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com 

예제 2에 표시 된 명령은 특정 사용자 (litwareinc \\ kenmyer)가 자신의 오디오 회의 공급자에 연결 하는 기능을 테스트 합니다. 이 작업을 수행 하기 위해이 예제의 첫 번째 명령은 Get-Credential cmdlet을 사용 하 여 사용자 Ken Myer의 이름과 암호가 포함 된 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다. (로그온 이름 litwareinc \\ kenmyer가 매개 변수로 포함 되었기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에는 관리자만 Ken Myer 계정의 암호를 입력 해야 합니다.) 결과 자격 증명 개체는 $credential 라는 변수에 저장 됩니다.

두 번째 명령은 이 사용자가 오디오 회의 공급자에 연결할 수 있는지 확인합니다. 이 작업을 수행 하기 위해 Test-CsAudioConferencingProvider cmdlet은 세 개의 매개 변수, 즉 TargetFqdn (등록자 풀의 FQDN)과 함께 호출 됩니다. UserCredential (Ken Myer의 사용자 자격 증명을 포함 하는 Windows PowerShell 개체) 및 UserSipAddress (제공 된 사용자 자격 증명에 해당 하는 SIP 주소)

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsAudioConferencingProvider -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

오디오 회의 공급자가 올바르게 구성 되 면 다음과 비슷한 출력을 받게 되며 Result 속성은 Success로 표시 됩니다 **.**

대상 Fqdn: atl-sql-001.litwareinc.com

결과: 성공

대기 시간: 00:00:00

오류 메시지:

진단을

지정 된 사용자가 로그온 하거나 로그 오프할 수 없으면 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

대상 Fqdn: atl-sql-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.

일정 시간 후에 올바르게 응답 하지 않았거나

연결 된 호스트에서 연결이 실패 했습니다.

\[2001:4898: e8: f39e: 5c9a: ad83:81b3:9944 \] : 5061을 응답 하지 못했습니다.

내부 예외:

일정 기간 후에 연결 된 파티가 제대로 응답 하지 않음

연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.

응답 하지 못했습니다.

\[2001:4898: e8: f39e: 5c9a: ad83:81b3:9944 \] : 5061

진단을

예를 들어 이전 출력에는 일반적으로에 지 서버에 문제가 있음을 나타내는 "연결 된 당사자가 제대로 응답 하지 않았습니다." 라는 노트가 포함 됩니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

다음은 **test-csaudioconferencingprovider에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 앞의 예제에 나와 있는 것 처럼 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - Test-csaudioconferencingprovider cmdlet을 **사용** 하는 사용자에 게 오디오 회의 공급자가 할당 되지 않은 경우 테스트가 실패 합니다.

  - 에 지 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

