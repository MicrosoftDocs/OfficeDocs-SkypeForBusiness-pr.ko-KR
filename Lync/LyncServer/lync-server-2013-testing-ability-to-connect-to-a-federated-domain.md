---
title: 'Lync Server 2013: 페더레이션 도메인에 연결 하는 기능 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a565c09e09e10eeb160b1d0514c89499427d1283
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532925"
---
# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Lync Server 2013에서 페더레이션 도메인에 연결 하는 기능 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsFederatedPartner cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Test-CsFederatedPartner는 페더레이션 파트너의 도메인에 연결할 수 있는지 확인합니다. 도메인에 대 한 연결을 확인 하려면 해당 도메인이 허용 (페더레이션) 도메인 컬렉션에 나열 되어 있어야 합니다. 다음 명령을 사용 하 여 허용 도메인 목록에 있는 도메인 목록을 검색할 수 있습니다.

    Get-CsAllowedDomain

자세한 내용은 [test-csfederatedpartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

Test-FederatedPartner cmdlet에는에 지 서버의 FQDN과 페더레이션 파트너의 FQDN 이라는 두 가지 정보가 필요 합니다. 예를 들어 다음 명령은 contoso.com 도메인에 연결 하는 기능을 테스트 합니다.

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

이 명령을 사용 하면 현재 허용 된 도메인 목록에 있는 모든 도메인에 대 한 연결을 테스트할 수 있습니다.

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

자세한 내용은 [test-csfederatedpartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 도메인에 연결할 수 있으면 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:00

오류

진단을

지정 된 도메인에 연결할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 504, 서버 제한 시간

진단: ErrorCode = 2, Source = atl-cs-litwareinc, Reason = 참고

응답 코드 및 이유 구입니다.

Microsoft DiagnosticHeader

예를 들어, 위의 출력에서는 서버 제한 시간 오류로 인해 테스트가 실패 했다는 것을 나타냅니다. 일반적으로 네트워크 연결에 문제가 있거나에 지 서버에 연결 하는 데 문제가 있는 경우를 나타냅니다.

Test-CsFederatedPartner 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Test-CsFederatedPartner 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 에 지 서버를 사용 하지 못할 수 있습니다. 다음 명령을 사용 하 여에 지 서버의 Fqdn을 사용할 수 있습니다.
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    그런 다음 각에 지 서버에 대해 ping을 수행 하 여 네트워크를 통해 액세스할 수 있는지 확인할 수 있습니다. 예제:
    
        ping atl-edge-001.litwareinc.com

  - 지정한 도메인이 허용 된 도메인 목록에 표시 되지 않을 수 있습니다. 허용 도메인 목록에 추가 된 도메인을 확인 하려면 다음 명령을 사용 합니다.
    
        Get-CsAllowedDomain
    
    사용자가 통신 하지 못하도록 차단 된 도메인 목록을 보려면 다음 명령을 사용 합니다.
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

