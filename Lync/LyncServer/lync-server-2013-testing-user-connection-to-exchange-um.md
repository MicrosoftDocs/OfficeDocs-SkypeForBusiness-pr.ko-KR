---
title: 'Lync Server 2013: Exchange UM에 대 한 사용자 연결을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user connection to Exchange UM
ms:assetid: 0b83fbf4-e124-4efd-a0a9-202eb849af82
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727300(v=OCS.15)
ms:contentKeyID: 63969573
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87b6fd59ed0efb3a775017af1effd7bd022071fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503875"
---
# <a name="testing-user-connection-to-exchange-um-in-lync-server-2013"></a>Lync Server 2013에서 Exchange UM에 대 한 사용자 연결 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>test-csexumconnectivity</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMConnectivity&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**Test-csexumconnectivity** cmdlet은 지정 된 사용자가 Microsoft Exchange Server 2013 통합 메시징 서비스에 연결할 수 있는지 확인 합니다. 이 cmdlet은 서비스에 대 한 연결이 가능한 지 확인 합니다. 서비스 자체를 테스트 하지는 않습니다. 사용자 사서함에 실제로 음성 메일 메시지를 남기는 가상 트랜잭션 cmdlet을 사용하여 통합 메시징 서비스를 테스트하려면 Test-CsExUMVoiceMail cmdlet을 사용하십시오.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

다음 예에서는 atl-cs-001.litwareinc.com 풀에 대 한 Exchange 통합 메시징 연결을 테스트 합니다. 이 명령은 atl-cs-001.litwareinc.com 풀에 대해 테스트 사용자가 정의 된 경우에만 작동 합니다. 이러한 경우에는 명령에 따라 첫 번째 테스트 사용자가 통합 메시징에 연결할 수 있는지 여부가 결정 됩니다. 테스트 사용자가 풀에 대해 구성 되지 않은 경우이 명령은 실패 합니다.

    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" 

다음 예에 나와 있는 명령은 사용자 litwareinc kenmyer에 대 한 Exchange 통합 메시징 연결을 테스트 합니다 \\ . 이 작업을 수행 하기 위해 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자 litwareinc kenmyer에 대 한 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다 \\ . 유효한 자격 증명 개체를 만들 수 있도록이 계정의 암호를 입력 하 고 **test-csexumconnectivity** cmdlet이 검사를 실행 하도록 해야 합니다.

예제의 두 번째 명령은 제공 된 자격 증명 개체 ($x)와 사용자 litwareinc kenmyer의 SIP 주소 \\ 를 사용 하 여이 사용자가 Exchange 통합 메시징에 연결할 수 있는지 여부를 결정 합니다.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

다음 예제에 표시 된 명령은 방금 표시 된 명령의 변형입니다. 이 경우에는 OutLoggerVariable 매개 변수를 포함 하 여 **test-csexumconnectivity** cmdletand 수행한 모든 단계의 자세한 로그와 이러한 각 단계의 성공 또는 실패를 생성 합니다. 이렇게 하려면 OutLoggerVariable 매개 변수 값이 ExumText와 함께 추가 됩니다. 이로 인해 자세한 로깅 정보가 $ExumTest 라는 변수에 저장 됩니다. 예제의 마지막 명령에서 ToXML () 메서드를 사용 하 여 로그 정보를 XML 형식으로 변환 합니다. 이 XML 데이터는 Out-File cmdlet을 사용 하 여 이름이 C: Logs 인 파일에 기록 됩니다 \\ \\ExumTest.xml.

    $credential = Get-Credential "litwareinc\kenmyer" 
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -OutLoggerVariable ExumTest 
    $ExumTest.ToXML() | Out-File C:\Logs\ExumTest.xml 

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

Exchange 통합이 올바르게 구성 되 면 다음과 비슷한 출력을 받게 되며 Result 속성은 **Success**로 표시 됩니다.

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:00

오류 메시지:

진단을

지정 된 사용자가 알림을 받을 수 없는 경우 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.

일정 시간 후에 올바르게 응답 하지 않았거나

연결 된 호스트에서 연결이 실패 했습니다.

10.188.116.96에 응답 하지 못했습니다. 5061

내부 예외:

일정 기간 후에 연결 된 파티가 제대로 응답 하지 않음

연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.

에서 10.188.116.96에 응답 하지 못했습니다. 5061

진단을

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

다음은 **test-csexumconnectivity에서** 오류가 발생할 수 있는 몇 가지 일반적인 이유입니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - Exchange 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.

  - 네트워크를 통해 Exchange 서버에 연결할 수 없으면이 명령은 실패 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[테스트-CsExUMVoiceMail 메일](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

