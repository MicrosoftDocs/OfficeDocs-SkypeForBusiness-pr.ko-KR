---
title: 'Lync Server 2013: Exchange UM 보이스 메일에 대 한 사용자 연결 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing user connection to Exchange UM voicemail
ms:assetid: 574da104-8823-4061-9fb6-353639f1884d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727305(v=OCS.15)
ms:contentKeyID: 63969604
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f09921d62eddb1f1b426e0e3b1fc4984a0987a8e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983747"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-user-connection-to-exchange-um-voicemail-in-lync-server-2013"></a>Lync Server 2013에서 Exchange UM 보이스 메일에 대 한 사용자 연결 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 <strong>테스트-CsExUMVoiceMail 메일</strong> cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExUMVoiceMail&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

관리자는 사용자가 Microsoft Exchange Server 2013 통합 메시징 서비스에 액세스 하 여 사용할 수 있는지 여부를 **테스트** 합니다. 이렇게 하려면 cmdlet이 통합 메시징 서비스에 연결 하 고 지정 된 사서함에 음성 메일을 남겨 둡니다. 시스템에서 제공 하는 음성 메일 또는 사용자 지정이 될 수 있습니다. WAV 파일을 직접 녹음/녹화할 수 있습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

다음 예에서는 풀 atl-cs-001.litwareinc.com에 대 한 Exchange 통합 메시징 음성 메일 연결을 테스트 합니다. 이 명령은 풀 atl-cs-001.litwareinc.com에 대해 테스트 사용자가 정의 된 경우에만 작동 합니다. 그렇지 않은 경우 명령에서 첫 번째 테스트 사용자가 통합 메시징 음성 메일을 사용할 수 있는지 여부를 확인 합니다. 테스트 사용자가 풀에 대해 구성 되지 않은 경우에는 명령이 실패 합니다.

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" 

다음 예제에 나와 있는 명령은 사용자 litwareinc\\kenmyer에 대 한 Exchange 통합 메시징 음성 메일 연결을 테스트 합니다. 이렇게 하려면 예제의 첫 번째 명령은 **Get-Credential** cmdlet을 사용 하 여 사용자 litwareinc\\Kenmyer에 대 한 Windows PowerShell 명령줄 인터페이스 자격 증명 개체를 만듭니다. 유효한 자격 증명 개체를 만들기 위해이 계정에 대 한 암호를 제공 하 고 **테스트-CsExUMVoiceMail 메일** cmdlet이 검사를 실행할 수 있도록 해야 합니다.

이 예제의 두 번째 명령은 제공 된 자격 증명 개체 ($x)와 사용자 litwareinc\\KENMYER의 SIP 주소를 사용 하 여이 사용자가 Exchange 통합 메시징 음성 메일에 연결할 수 있는지 여부를 결정 합니다.

    $credential = Get-Credential "litwareinc\pilar" 
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential 

다음 예제에 표시 되는 명령은 예제 1에 표시 된 명령의 변형입니다. 이 경우 OutLoggerVariable 매개 변수는 **테스트-c** ...의 모든 단계에 대 한 자세한 로그를 생성 하는 데 포함 되며, 이러한 각 단계의 성공 또는 실패입니다. 이렇게 하려면 OutLoggerVariable 매개 변수를 매개 변수 값으로 ExumText와 함께 추가 합니다. 이렇게 하면 자세한 로깅 정보가 $ExumTest 라는 변수에 저장 됩니다. 예제의 마지막 명령에서 ToXML () 메서드를 사용 하 여 로그 정보를 XML 형식으로 변환 합니다. 그런 다음 VoicemailTest cmdlet을 사용 하 여 XML 데이터를 C:\\Logs\\라는 파일에 기록 합니다.

    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -OutLoggerVariable VoicemailTest 
     
    $VoicemailTest.ToXML() | Out-File C:\Logs\VoicemailTest.xml

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

Exchange 통합이 올바르게 구성 되 면 다음과 비슷한 출력이 표시 되 고 결과 속성이 **성공**으로 표시 됩니다.

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:02.9911345

오류 메시지:

있게

지정 된 사용자가 보이스 메일에 연결할 수 없는 경우 결과가 **실패로**표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

경고: 정규화 된 정식 #b0에 대 한 등록자 포트 번호를 읽지 못했습니다.

도메인 이름 (FQDN). 기본 등록자 포트 번호를 사용 합니다. 발생

InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

배포자

SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.

일정 시간 후에 제대로 응답 하지 않았거나

연결 된 호스트가 다음 연결에 실패 하 여 성립

10.188.116.96에 응답 하지 못했습니다: 5061

내부 예외: 다음 이유로 인해 연결 시도가 실패 했습니다.

연결 된 상대방이 일정 기간 후에 적절 하 게 응답 하지 않았습니다.

연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.

님이 10.188.116.96에 응답 하지 못했습니다: 5061

있게

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

다음은 **테스트-CsExUMVoiceMail 메일이** 실패할 수 있는 몇 가지 일반적인 이유입니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 사용 하는 경우 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - Exchange 서버가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

