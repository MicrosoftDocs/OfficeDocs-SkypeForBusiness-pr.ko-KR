---
title: 'Lync Server 2013: 주소록 웹 쿼리 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validating address book web query
ms:assetid: e6ae0a5a-e131-4cfe-9a33-6e611831072d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720925(v=OCS.15)
ms:contentKeyID: 63969662
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31d6a38c0c1d8a67977f9dd66da2a94b51a4f9ab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-address-book-web-query-in-lync-server-2013"></a>Lync Server 2013에서 주소록 웹 쿼리 확인

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 테스트-CsAddressBookWebQuery cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAddressBookWebQuery&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

관리자는 테스트-CsAddressBookWebQuery cmdlet을 통해 사용자가 주소록 웹 쿼리 서비스를 사용 하 여 특정 연락처를 검색할지 확인할 수 있습니다. Cmdlet을 실행할 때 테스트-CsAddressBookWebQuery는 먼저 인증 받을 웹 티켓 서비스에 연결 합니다. 인증에 성공 하면 cmdlet이 주소록 웹 쿼리 서비스에 연결 하 고 지정 된 연락처를 검색 합니다. 해당 연락처가 발견 되 면 cmdlet이 해당 정보를 로컬 컴퓨터로 반환 하려고 시도 합니다. 해당 단계가 모두 완료 될 수 있는 경우에만 테스트가 성공으로 표시 됩니다.

자세한 내용은 [테스트-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsAddressBookWebQuery cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 Lync Server 풀의 FQDN과 검색 대상으로 작동 하는 사용자의 SIP 주소를 지정 하기만 하면 됩니다. 예를 들면 다음과 같습니다.

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 유효한 사용자 이름 및 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다. 그런 다음 코드에서 테스트-CsAddressBookWebQuery를 호출할 때 계정에 할당 된 해당 자격 증명 개체와 SIP 주소를 포함 해야 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

자세한 내용은 [테스트-CsAddressBookWebQuery](https://docs.microsoft.com/powershell/module/skype/Test-CsAddressBookWebQuery) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 주소록 서비스에 연결 하 고 대상 사용자 주소를 검색할 수 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 반환 합니다.

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.2611356

오류

있게

지정 된 사용자가 연결할 수 없거나 대상 사용자 주소를 검색할 수 없는 경우에는 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 응답 코드와 함께 주소록 웹 서비스 요청이 실패 했습니다.

NoEntryFound.

있게

이전 출력에서는 대상 사용자를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 설명 합니다. 다음과 같은 명령을 실행 하 여 유효한 SIP 주소가 테스트-CsAddressBookWebQuery에 전달 되었는지 여부를 확인할 수 있습니다.

    Get-CsUser | Where-Object {$_.SipAddress -eq "sip:davidlongmire@litwareinc.com"

테스트-CsAddressBookWebQuery가 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsAddressBookWebQuery -TargetFqdn "atl-cs-001.litwareinc.com" -TargetSipAddress "sip:davidlongmire@litwareinc.com" -Verbose

Verbose 매개 변수가 포함 된 경우 테스트-CsAddressBookWebQuery는 지정 된 사용자가 Lync Server에 로그온 하는 기능을 확인 하는 동안 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어이 출력은 테스트-CsAddressBookWebQuery가 주소록 서비스에 연결할 수 있었지만 대상 SIP 주소를 찾을 수 없음을 나타냅니다.

' QueryAddressBookWebService ' 활동이 시작 되었습니다.

호출 주소록 웹 쿼리 서비스 ABWS URL =

https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

주소록 쿼리 예외: 응답 코드 NoEntryFound 발견 하 여 주소록 웹 서비스 요청이 실패 했습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트-CsAddressBookWebQuery가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 현재 Lync Server에 계정이 설정 되어 있지 않습니다. Lync Server에 대해 사용자 계정이 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.

  - 대상 사용자가 주소록에 없을 수 있습니다.

  - 주소록이 완전히 업데이트 및 복제 되지 않았을 수 있습니다. 다음 명령을 실행 하 여 조직의 모든 주소록 서버를 강제로 업데이트할 수 있습니다.
    
        Update-CsAddressBook

</div>

</div>

<span> </span>

</div>

</div>

</div>

