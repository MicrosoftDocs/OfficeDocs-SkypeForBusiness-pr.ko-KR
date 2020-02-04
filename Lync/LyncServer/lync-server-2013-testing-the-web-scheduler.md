---
title: 'Lync Server 2013: 웹 스케줄러 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65d7dc70bad90dc4e4c94e2db273f44ed20c50ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745418"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>Lync Server 2013에서 웹 스케줄러 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-11-03_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 <strong>테스트 CsWebScheduler</strong> cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**테스트-CsWebScheduler** cmdlet을 사용 하면 특정 사용자가 웹 스케줄러를 사용 하 여 모임을 예약할 수 있는지 여부를 확인할 수 있습니다. 웹 스케줄러에서는 Outlook을 실행 하지 않는 사용자가 온라인 모임을 예약할 수 있습니다. 그 외에, Microsoft Lync Server 2010 리소스 키트에 포함 된 웹 스케줄러 도구에서 발견 된 기능을 통합 하는이 새로운 기능은 다음과 같은 사용자를 위해 사용할 수 있습니다.

  - 새 온라인 모임 예약

  - 자신이 예약한 모든 모임을 나열 합니다.

  - 기존 모임을 보거나 수정 합니다.

  - 기존 모임을 삭제 합니다.

  - 미리 구성 된 SMTP 메일 서버를 사용 하 여 모임 참가자에 게 전자 메일 초대를 보냅니다.

  - 기존 회의에 참가 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

다음 예제에서는 풀 atl-cs-001.litwareinc.com에 대 한 웹 스케줄러를 확인 합니다. 이 명령은 풀 atl-cs-001.litwareinc.com에 대해 테스트 사용자가 정의 된 경우에만 작동 합니다. 그렇지 않은 경우이 명령은 첫 번째 테스트 사용자가 웹 스케줄러를 사용 하 여 온라인 모임을 예약할 수 있는지 여부를 결정 합니다.

테스트 사용자가 정의 되지 않은 경우에는 어떤 사용자로 로그온 해야 하는지 알 수 없기 때문에 명령이 실패 하 게 됩니다. 풀에 대해 테스트 사용자를 정의 하지 않은 경우에는 UserSipAddress 매개 변수와이 명령을 사용 하 여 로그온 할 때 사용할 사용자의 자격 증명을 포함 해야 합니다.

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

다음 예제에 표시 된 명령은 특정 사용자 (litwareinc\\kenmeyer)의 기능을 테스트 하 여 웹 스케줄러를 사용 하 여 온라인 모임을 예약 합니다. 이렇게 하려면이 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자: 진구 Meyer의 이름 및 암호를 포함 하는 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다. (로그온 이름 litwareinc\\kenmeyer는 매개 변수로 포함 되어 있기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에는 관리자만: 진구 Meyer 계정에 대 한 암호를 입력 해야 합니다.) 그런 다음 결과 credential 개체는 $cred 1 이라는 변수에 저장 됩니다.

두 번째 명령은이 사용자가 풀 atl-cs-001.litwareinc.com에 로그온 할 수 있는지 여부를 확인 하 고 온라인 모임을 예약 합니다. 이 작업을 실행 하려면 다음 세 개의 매개 변수 (예: TargetFqdn (등록자 풀의 FQDN)를 사용 하 여 **테스트 CsWebScheduler** cmdlet이 호출 됩니다. UserCredential (Pilar Ackerman의 사용자 자격 증명을 포함 하는 Windows PowerShell 개체)입니다. 및 UserSipAddress (제공 된 사용자 자격 증명에 해당 하는 SIP 주소).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

웹 스케줄러가 올바르게 구성 되어 있는 경우 결과 속성이 **성공**으로 표시 된 것과 비슷한 출력을 받게 됩니다.

대상 Fqdn: atl-cs-001.litwareinc.com

대상 Uri: https://atl-cs-001.litwareinc.com.

litwareinc.com:443/Scheduler

결과: 성공

대기 시간: 00:00:00

오류 메시지:

있게

웹 스케줄러가 올바르게 구성 되어 있지 않으면 결과가 **실패로**표시 되 고 다음과 같은 오류 및 진단 속성에 추가 정보가 기록 됩니다.

경고: 정규화 된 정식 #b0에 대 한 등록자 포트 번호를 읽지 못했습니다.

도메인 이름 (FQDN). 기본 등록자 포트 번호를 사용 합니다. 발생

InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

배포자

SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

대상 Fqdn: atl-cs-001.litwareinc.com

대상 Uri:

결과: 실패

대기 시간: 00:00:00

오류 메시지: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

있게

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

**테스트-CsWebScheduler에서** 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 사용 하는 경우 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - 웹 스케줄러가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Set-CsWebServer](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

