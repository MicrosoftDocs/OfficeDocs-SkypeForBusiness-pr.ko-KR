---
title: 'Lync Server 2013: 웹 앱 액세스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test Web App access
ms:assetid: 17d67ea3-f74d-4952-ac2b-92c0dacc8014
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767944(v=OCS.15)
ms:contentKeyID: 63969584
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7618bcc9a69d177950bae64354106a67721e822a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746008"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-web-app-access-in-lync-server-2013"></a>Lync Server 2013에서 웹 앱 액세스 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>확인 일정</p></td>
<td><p>월간</p></td>
</tr>
<tr class="even">
<td><p>테스트 도구</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>권한이 필요 함</p></td>
<td><p>Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsWebApp cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebApp&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

CsWebApp cmdlet은 인증 된 사용자가 Lync Web App을 사용 하 여 Lync Server 컨퍼런스에 참가할 수 있는지 확인 합니다. Cmdlet을 실행할 때 CsWebApp에서 웹 티켓 서비스에 연결 하 여 지정 된 사용자에 대 한 웹 티켓을 가져옵니다. 이러한 티켓은 Lync 서버 회의에 대 한 ' 허용 티켓 '으로 효과적으로 작동 합니다. 티켓을 검색할 수 있고 사용자를 인증할 수 있는 경우 테스트-CsWebApp는 Lync Server에 연결 하 고 인스턴트 메시지, 응용 프로그램 공유 및 데이터 공동 작업을 위한 별도의 회의를 설정 하려고 시도 합니다.

이 회의를 만드는 데 사용 되는 Api 및 연결을 확인 하는 것은 테스트 CsWebApp 뿐입니다. 이 cmdlet은 Lync Web App을 사용 하 여 회의를 만들고 참가할 수 있는지 확인 하도록 디자인 되었습니다. 그러나 실제로 회의를 만들고 진행 하는 것은 아닙니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트 CsWebApp cmdlet은 미리 구성 된 테스트 계정 쌍 또는 Lync Server에 대해 사용 하도록 설정 된 두 명의 사용자 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync 서버 풀의 정규화 된 도메인 이름을 지정 하기만 하면 됩니다. 예를 들면 다음과 같습니다.

    Test-CsWebApp -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호를 포함 하는 개체)를 만들어야 합니다. 그런 다음 Test-CsWebApp를 호출할 때 두 계정의 SIP 주소와 이러한 자격 증명 개체를 포함 해야 합니다.

    $cred1 = Get-Credential "litwareinc\kenmyer"
    $cred2 = Get-Credential "litwareinc\pilar"
    
    Test-CsWebApp -TargetFqdn atl-cs-001.litwareinc.com -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $cred1 -User2SipAddress "sip:pilar@litwareinc.com" -User2Credential $cred2

자세한 내용은 [테스트 CsWebApp](https://docs.microsoft.com/powershell/module/skype/Test-CsWebApp) cmdlet에 대 한 도움말 항목을 참조 하세요. CsWebApp는 Lync Server 2013에서 사용 하지 않는 것이 좋습니다.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

테스트-CsWebApp에서 사용자에 게 회의에 참가할 수 있는 경우 cmdlet은 테스트 결과 성공을 반환 합니다.

대상 Fqdn:

결과: 성공

대기 시간: 00:00:00

오류 메시지:

있게

사용자가 필요한 회의에 참가할 수 없는 경우 테스트 결과가 실패로 표시 됩니다. 일반적으로 테스트 CsWebApp는 자세한 오류 메시지 및 진단도 보고 합니다.

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류 메시지: 웹 티켓 서비스에 대 한 응답이 수신 되지 않았습니다.

진단: HTTP 요청은 클라이언트를 사용 하 여 승인 되지 않습니다.

' Ntlm ' 인증 체계. 인증

서버에서 받은 헤더가 ' 협상, NTLM '입니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

일반적으로 CsWebApp 오류는 사용자 인증 오류와 관련이 있습니다. 테스트-CsWebApp가 실패 하는 경우 먼저 지정 된 사용자에 게 유효한 사용자 계정이 있고 Lync Server에 대 한 사용이 설정 되어 있는지 확인 해야 합니다. 다음과 같은 명령을 사용 하 여 계정 정보를 검색할 수 있습니다.

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Enabled 속성이 True가 아니거나 명령이 실패 한 경우에는 사용자에 게 유효한 Lync Server 계정이 없음을 의미 합니다. 또한 cmdlet에 제공한 암호가 유효한 지 확인 해야 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

