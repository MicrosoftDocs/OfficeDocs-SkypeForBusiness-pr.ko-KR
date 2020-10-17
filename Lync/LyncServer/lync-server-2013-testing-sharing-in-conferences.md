---
title: 'Lync Server 2013: 회의에서 공유 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing sharing in conferences
ms:assetid: e6021d70-6ed9-414d-954c-06eef397dc1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727314(v=OCS.15)
ms:contentKeyID: 63969660
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36cf05d0d3d5cce13a100d23cb541eb5aa186ef7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530495"
---
# <a name="testing-sharing-in-conferences-in-lync-server-2013"></a>Lync Server 2013에서 회의의 공유 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>test-csdataconference</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDataConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Lync Server 2013에서는 화이트 보드와 같은 공동 작업을 사용 하는 모든 회의를 데이터 회의 라고 합니다. **Test-csdataconference** cmdlet을 사용 하면 한 쌍의 사용자가 데이터 회의에 참가할 수 있는지 확인할 수 있습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

예제 1에 표시 된 명령은 atl-cs-001.litwareinc.com 풀에서 데이터 회의를 수행할 수 있는지 확인 합니다. 이 명령은 지정된 풀에 대해 테스트 사용자 한 쌍이 구성되었다고 가정합니다. 테스트 사용자가 없으면 명령은 실패합니다.

    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" 

예제 2에 표시 된 명령은 litwareinc \\ pilar 및 litwareinc \\ kenmyer)에서 Lync Server 2013에 로그온 한 후 데이터 회의를 수행 하는 기능을 테스트 합니다. 이 작업을 수행 하기 위해이 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 User Pilar Ackerman의 이름과 암호가 포함 된 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다. (로그온 이름, litwareinc pilar가 \\ 매개 변수로 포함 되었기 때문에 Windows PowerShell 자격 증명 요청 대화 상자에만 관리자가 Pilar Ackerman 계정의 암호를 입력 하면 됩니다.) 그런 다음 결과 credential 개체는 $cred 1 이라는 변수에 저장 됩니다. 두 번째 명령도 같은 작업을 수행하지만 이번에는 Ken Myer 계정의 자격 증명 개체를 반환합니다.

자격 증명 개체를 사용 하는 경우 세 번째 명령은 이러한 두 사용자가 Lync Server 2013에 로그온 하 고 데이터 전화 회의를 수행할 수 있는지 여부를 결정 합니다. 이 작업을 수행 하기 위해 **test-csdataconference** Cmdlet은 targetfqdn (등록자 풀의 fqdn)과 함께 다음 매개 변수와 함께 호출 됩니다. SenderSipAddress (첫 번째 테스트 사용자의 SIP 주소) SenderCredential (이 사용자에 대 한 자격 증명이 포함 된 Windows PowerShell 개체) ReceiverSipAddress (다른 테스트 사용자의 SIP 주소); 및 변수와 (다른 테스트 사용자에 대 한 자격 증명이 포함 된 Windows PowerShell 개체)

    $credential1 = Get-Credential "litwareinc\pilar" 
    $credential2 = Get-Credential "litwareinc\kenmyer" 
    Test-CsDataConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

데이터 회의가 올바르게 구성 되 면 다음과 비슷한 출력을 받게 되며 Result 속성은 Success로 표시 됩니다 **.**

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:00

오류 메시지:

진단을

지정 된 사용자가 데이터 공유를 사용할 수 없는 경우 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

대상 Fqdn: atl-cs-001.litwareinc.com

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

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

다음은 **test-csdataconference에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - 데이터 회의를 수행 하는 기능은 회의를 구성한 사용자에 게 할당 된 회의 정책 ( **test-csdataconference** cmdlet의 경우 "sender")에 따라 달라 집니다. 이끌이가 자신의 모임에 공동 작업을 포함할 수 없는 경우 (예: 해당 회의 정책에서 EnableDataCollaboration 속성을 False로 설정한 경우) **test-csdataconference** cmdlet이 실패 합니다.

  - 에 지 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

