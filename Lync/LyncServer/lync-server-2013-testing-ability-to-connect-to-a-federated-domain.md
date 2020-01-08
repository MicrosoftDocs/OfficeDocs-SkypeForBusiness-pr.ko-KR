---
title: 'Lync Server 2013: 페더레이션 도메인에 연결 하는 기능 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to connect to a federated domain
ms:assetid: d8ccfade-ef54-47a4-9f87-36213a635ce5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743840(v=OCS.15)
ms:contentKeyID: 63969653
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2176008e3e941068f61a2fb385fa6230df6b25dd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-connect-to-a-federated-domain-from-lync-server-2013"></a>Lync Server 2013에서 페더레이션 도메인에 연결 하는 기능 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsFederatedPartner cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsFederatedPartner&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

CsFederatedPartner는 페더레이션 파트너의 도메인에 연결 하는 기능을 확인 합니다. 도메인에 대 한 연결을 확인 하려면 해당 도메인이 허용 (페더레이션된) 도메인 모음에 나열 되어야 합니다. 다음 명령을 사용 하 여 허용 된 도메인 목록에 있는 도메인 목록을 검색할 수 있습니다.

    Get-CsAllowedDomain

자세한 내용은 [테스트 CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

FederatedPartner cmdlet에는 두 가지 정보, 즉 Edge 서버의 FQDN과 페더레이션 파트너의 FQDN이 필요 합니다. 예를 들어이 명령은 도메인 contoso.com에 연결 하는 기능을 테스트 합니다.

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com"

이 명령을 사용 하면 현재 허용 된 도메인 목록에 있는 모든 도메인에 대 한 연결을 테스트할 수 있습니다.

    Get-CsAllowedDomain | ForEach-Object {Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain $_.Identity}

자세한 내용은 [테스트 CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 도메인에 연결할 수 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:00

오류

있게

지정 된 도메인에 연결할 수 없는 경우에는 결과가 실패로 표시 되 고 다음과 같은 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 504, 서버 시간 초과

진단: ErrorCode = 2, 원본 = atl-cs-001. litwareinc, Reason = 참조

응답 코드 및 이유 구.

Microsoft DiagnosticHeader

예를 들어 이전 출력은 서버 시간 초과 오류로 인해 테스트가 실패 했다는 것을 보여 줍니다. 이는 일반적으로 네트워크 연결 문제나 Edge 서버에 연결 하는 데 문제가 있음을 나타냅니다.

테스트-CsFederatedPartner 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsFederatedPartner -TargetFqdn "atl-edge-001.litwareinc.com" -Domain "contoso.com" -Verbose

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트 CsFederatedPartner가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - Edge 서버를 사용할 수 없는 경우일 수 있습니다. 다음 명령을 사용 하 여 Edge 서버의 Fqdn을 사용할 수 있습니다.
    
        Get-CsService -EdgeServer | Select-Object PoolFqdn
    
    그런 다음 각 Edge 서버에 ping을 수행 하 여 네트워크를 통해 액세스할 수 있는지 확인할 수 있습니다. 예를 들면 다음과 같습니다.
    
        ping atl-edge-001.litwareinc.com

  - 지정 된 도메인이 허용 된 도메인 목록에 나열 되지 않을 수 있습니다. 허용 되는 도메인 목록에 추가 된 도메인을 확인 하려면 다음 명령을 사용 합니다.
    
        Get-CsAllowedDomain
    
    사용자가 통신을 차단 하는 도메인 목록을 보려면 다음 명령을 사용 합니다.
    
        Get-CsBlockedDomain

</div>

</div>

<span> </span>

</div>

</div>

</div>

