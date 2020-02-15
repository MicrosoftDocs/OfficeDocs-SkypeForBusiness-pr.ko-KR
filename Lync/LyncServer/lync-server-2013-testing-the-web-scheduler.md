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
ms.openlocfilehash: 8bc3d93e1e4a08575119031471863dad817f3e80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>Lync Server 2013에서 웹 스케줄러 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-11-03_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 <strong>CsWebScheduler</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**테스트-CsWebScheduler** cmdlet을 사용 하 여 특정 사용자가 웹 스케줄러를 사용 하 여 모임을 예약할 수 있는지 여부를 확인할 수도 있습니다. 웹 스케줄러를 사용 하면 Outlook을 실행 하 고 있지 않은 사용자가 온라인 모임을 예약할 수 있습니다. 특히 Microsoft Lync Server 2010 resource kit에 포함 된 웹 스케줄러 도구에서 제공 하는 기능을 통합 하는이 새로운 기능을 사용 하면 다음과 같은 작업을 수행할 수 있습니다.

  - 새 온라인 모임 예약

  - 사용자가 예약한 모든 모임의 목록 표시

  - 기존 모임 보기/수정

  - 기존 모임 삭제

  - 미리 구성된 SMTP 메일 서버를 사용하여 모임 참가자에게 전자 메일 초대 보내기

  - 기존 전화 회의에 참가

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

다음 예에서는 atl-cs-001.litwareinc.com 풀에 대 한 웹 스케줄러를 확인 합니다. 이 명령은 atl-cs-001.litwareinc.com 풀에 대해 테스트 사용자가 정의 된 경우에만 작동 합니다. 이러한 경우에는 명령에 따라 첫 번째 테스트 사용자가 웹 스케줄러를 사용 하 여 온라인 모임을 예약할 수 있는지 여부가 결정 됩니다.

테스트 사용자가 정의 되어 있지 않으면 어떤 사용자로 로그온 하는지 알 수 없으므로 명령이 실패 합니다. 풀에 대해 테스트 사용자를 정의 하지 않은 경우에는 UserSipAddress 매개 변수 및 명령에 로그온을 시도할 때 사용할 사용자의 자격 증명을 포함 해야 합니다.

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

다음 예에 표시 된 명령은 특정 사용자 (litwareinc\\kenmeyer)가 웹 스케줄러를 사용 하 여 온라인 모임을 예약 하도록 하는 기능을 테스트 합니다. 이 작업을 수행 하기 위해이 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자 Ken 구 지 후의 이름과 암호가 포함 된 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다. (로그온 이름 litwareinc\\kenmeyer는 매개 변수로 포함 되므로 Windows PowerShell 자격 증명 요청 대화 상자에는 관리자만 Ken 구 지 후 계정의 암호를 입력 해야 합니다.) 그런 다음 결과 credential 개체는 $cred 1 이라는 변수에 저장 됩니다.

두 번째 명령은이 사용자가 atl-cs-001.litwareinc.com 풀에 로그온 하 고 온라인 모임을 예약할 수 있는지 여부를 확인 합니다. 이 작업을 실행 하기 위해 **테스트-CsWebScheduler** cmdlet은 세 개의 매개 변수, 즉 Targetfqdn (등록자 풀의 FQDN)과 함께 호출 됩니다. UserCredential (Pilar Ackerman의 사용자 자격 증명을 포함 하는 Windows PowerShell 개체) 및 UserSipAddress (제공 된 사용자 자격 증명에 해당 하는 SIP 주소)

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

웹 스케줄러가 올바르게 구성 된 경우 결과 속성이 **Success**로 표시 된 것과 비슷한 출력을 받게 됩니다.

대상 Fqdn: atl-cs-001.litwareinc.com

대상 Uri: https://atl-cs-001.litwareinc.com.

litwareinc.com:443/Scheduler

결과: 성공

대기 시간: 00:00:00

오류 메시지:

진단을

웹 스케줄러가 제대로 구성 되어 있지 않으면 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

경고: 지정한 정규화 된 자격에 대 한 등록자 포트 번호를 읽지 못했습니다.

FQDN (도메인 이름) 기본 등록자 포트 번호 사용 오류

InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

구독자

SyntheticTransactions SipSyntheticTransaction TryRetri를 관리 합니다.

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

대상 Fqdn: atl-cs-001.litwareinc.com

대상 Uri:

결과: 실패

대기 시간: 00:00:00

오류 메시지: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

진단을

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

**테스트-CsWebScheduler** 가 실패할 수 있는 일반적인 이유는 다음과 같습니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

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

