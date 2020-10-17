---
title: 'Lync Server 2013: Lync 클라이언트 인증 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Client authentication
ms:assetid: e22114cb-4456-4e5f-93ab-51592c4a8209
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689120(v=OCS.15)
ms:contentKeyID: 63969659
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 308bb50e5365cd45c993875ea503b33b32617397
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519035"
---
# <a name="testing-lync-client-authentication-in-lync-server-2013"></a>Lync Server 2013에서 Lync 클라이언트 인증 테스트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsClientAuth cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsClientAuth&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Test-CsClientAuth cmdlet을 사용 하면 사용자가 클라이언트 인증서를 사용 하 여 Lync Server에 로그온 할 수 있는지 여부를 확인할 수 있으며, Test-CsClientAuth cmdlet을 실행할 수도 있습니다. 테스트-CsClientAuth를 호출한 후 cmdlet은 인증서 프로 비전 서비스에 연결 하 고 지정 된 사용자에 대 한 클라이언트 인증서의 복사본을 다운로드 합니다. 클라이언트 인증서를 찾아서 다운로드할 수 있으면 Test-CsClientAuth에서 해당 인증서를 사용 하 여 로그온을 시도 합니다. 로그온이 성공 하면 Test-CsClientAuth가 로그 오프 되 고 테스트가 성공 했음을 보고 합니다. 인증서를 찾거나 다운로드할 수 없거나 해당 인증서를 사용하여 로그온할 수 없는 경우 Test-CsClientAuth는 테스트 실패를 보고합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Test-CsClientAuth cmdlet은 Lync Server를 사용할 수 있는 사용자의 계정을 사용 하 여 실행 됩니다. 실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호가 포함 된 Windows PowerShell 자격 증명 개체를 만들어야 합니다. 그런 다음 시스템에서 Test-CsClientAuth를 호출 하면 해당 자격 증명 개체와 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

자세한 내용은 [CsClientAuth](https://technet.microsoft.com/library/gg398712\(v=ocs.14\).aspx) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 클라이언트 인증서를 사용 하 여 Lync Server에 로그온 할 수 있으면 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.8630376

오류

진단을

지정 된 사용자가 로그온 할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:03.3645259

오류: 지정 된 사용자에 대 한 CS 인증서를 다운로드할 수 없습니다. 다음을 확인 합니다.

제공 된 uri 및 자격 증명이 올바릅니다.

진단을

예를 들어 이전 출력에서는 지정 된 사용자에 대해 유효한 클라이언트 인증서를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 나타냅니다. 다음과 같이 명령을 실행 하 여 사용자에 게 발급 된 클라이언트 인증서의 목록을 반환할 수 있습니다.

    Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

Test-CsClientAuth 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsClientAuth -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential -Verbose

Verbose 매개 변수를 포함 하면 Test-CsClientAuth는 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예제:

사용자: kenmyer@litwareinc.com endpoint: Stid에 대 한 CS 인증서를 다운로드 하려고 합니다.

웹 서비스 url: https://atl-cs-001.litwareinc.com:443/CertProv/CertprovisioningService.svc

웹 서비스에서 CS 인증서를 다운로드할 수 없습니다.

되었는지

\- 웹 서비스 url이 유효 하며 웹 서비스가 작동 하 고 있습니다.

\-PhoneNo Pin을 사용 하 여 인증 하는 경우 \\ \\ 사용자 uri와 일치 하는지 확인 합니다.

\- NTLM \\ Kerberos 인증을 사용 하는 경우 유효한 자격 증명을 제공 했는지 확인 합니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Test-CsClientAuth 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다. 사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.

  - 테스트 사용자에 게 유효한 클라이언트 인증서가 없을 수 있습니다. 다음과 같은 명령을 사용 하 여 사용자에 게 할당 된 클라이언트 인증서에 대 한 정보를 반환할 수 있습니다.
    
        Get-CsClientCertificate -Identity "sip:kenmyer@litwareinc.com"

</div>

</div>

<span> </span>

</div>

</div>

</div>

