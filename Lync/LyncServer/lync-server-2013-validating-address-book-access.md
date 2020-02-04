---
title: 'Lync Server 2013: 주소록 액세스 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book access
ms:assetid: 630682c6-9262-46c5-9af1-6193db70374b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720916(v=OCS.15)
ms:contentKeyID: 63969611
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96fe45f1491ca518a6985b0c15f8bcc229bd7f8c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763672"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-access-in-lync-server-2013"></a>Lync Server 2013에서 주소록 액세스 확인

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자는 테스트-CsAddressBookService cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookService&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsAddressBookService cmdlet은 사용자가 주소록 다운로드 웹 서비스에 연결할 수 있는지 확인 하는 방법을 제공 합니다. Cmdlet을 실행 하면 테스트-CsAddressBookService가 지정 된 풀의 주소록 다운로드 웹 서비스에 연결 하 고 주소록 파일의 위치를 요청 합니다. 주소록 다운로드 웹 서비스에서 해당 위치를 제공 하는 경우 테스트가 성공한 것으로 간주 됩니다. 요청이 거부 되 면 테스트를 실패로 간주 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsAddressBookService cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN (정규화 된 도메인 이름)을 지정 하기만 하면 됩니다. 예를 들면 다음과 같습니다.

    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다. 그런 다음 테스트-CsAddressBookService를 호출할 때 해당 자격 증명 개체와 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookService -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

자세한 내용은 [CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 주소록 서비스에 연결할 수 있으면 결과 속성이 **성공**으로 표시 된 것과 비슷한 출력이 반환 됩니다.

TargetUri :https://lync-se.fabrikam.com:443/abs/handler

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.2260399

오류

있게

지정 된 사용자가이 연결을 할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetUri :

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,

이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음

존재.

Microsoft DiagnosticHeader

예를 들어 앞의 출력에는 지정 된 사용자 (즉, "대상 URI")가 없거나 Lync Server에 대해 사용 하도록 설정 되어 있지 않아 테스트가 실패 했음을 알리는 메시지가 나와 있습니다. 사용자 계정이 유효한 지 여부를 확인 하 고, 다음과 같은 명령을 실행 하 여 올바른 SIP 주소를 입력 했는지 확인 합니다.

Get-CsUser-Id "sip:kenmyer@litwareinc.com" | 선택-개체 SipAddress, 사용

테스트-CsAddressBookService가 실패 하는 경우 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

테스트-CsAddressBookService-TargetFqdn "atl-cs-001.litwareinc.com"-Verbose

Verbose 매개 변수를 포함 하는 경우 테스트-CsAddressBookService는 지정 된 사용자가 Lync Server에 로그온 하는 기능을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 다음은이 예제에 있는 테스트 CsAddressBookService가 주소록 파일을 다운로드할 수 있다는 것을 보여 주는 예제 출력입니다.

Http GET 요청을 보내는 중입니다.

파일 경로 =https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

시도 번호 = 1

TimeOut (msec) = 6만

ABS 파일을 다운로드 했습니다.https://atl-cs-001.litwareinc.com:443/abs/handler/f-1299.lsabs

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트-CsAddressBookService 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 현재 Lync Server에 계정이 설정 되어 있지 않습니다. Lync Server에 대해 사용자 계정이 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Test-CsAddressBookService](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

