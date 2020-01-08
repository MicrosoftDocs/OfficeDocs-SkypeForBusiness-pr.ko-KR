---
title: 'Lync Server 2013: 그룹 확장을 사용 하는 방법 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f99be38a906c508346f580b36d055ccba86a168e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Lync Server 2013에서 그룹 확장을 사용 하는 테스트 기능

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 테스트-CsGroupExpansion cmdlet을 실행할 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsGroupExpansion cmdlet을 사용 하 여 조직 내에서 그룹 확장이 작동 하는지 여부를 결정할 수 있습니다. 그룹 확장을 사용 하도록 설정 하면 사용자가 메일 그룹을 연락처로 구성 합니다. 따라서 이러한 사용자는 해당 그룹의 개별 구성원 대신 그룹에 대 한 메시지를 처리 하 여 모든 그룹 구성원에 게 동일한 인스턴트 메시지를 보낼 수 있습니다. 그룹 확장을 사용 하면 모든 그룹 구성원과 해당 사용자의 현재 상태를 빠르고 쉽게 볼 수 있습니다.

테스트-CsGroupExpansion cmdlet을 사용 하 여 그룹의 전자 메일 주소를 사용 하 여 Active Directory 메일 그룹을 지정 합니다. 테스트-CsGroupExpansion은 그룹 확장을 사용 하 여 그룹 구성원을 검색 하 고 검색 된 목록을 제공 된 그룹 전자 메일 주소의 구성원으로 비교 합니다. 두 목록이 일치 하는 경우 그룹 확장이 올바르게 작동 하는 것입니다. 서비스 자체를 테스트 하거나 연결 된 웹 서비스를 테스트 하 여 두 가지 방법으로 그룹 확장을 테스트할 수 있습니다.

자세한 내용은 [테스트-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsGroupExpansion cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN과 올바른 메일 그룹의 전자 메일 주소를 지정 하기만 하면 됩니다. 예를 들면 다음과 같습니다.

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호를 포함 하는 Lync Server 자격 증명 개체를 만들어야 합니다. 그런 다음 시스템에서 테스트-CsGroupExpansion을 호출할 때 계정에 할당 된 해당 자격 증명 개체와 SIP 주소를 포함 해야 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

자세한 내용은 [테스트-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 그룹 확장을 사용할 수 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:01.1234976

오류

있게

지정 된 사용자가 그룹 확장을 사용할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetUri :https://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류

있게

테스트-CsGroupExpansion: 끝점을 등록할 수 없습니다. 오류 코드는 특정 이유를 참조 하세요.

이전 출력에서는 지정 된 사용자가 Lync Server에 등록할 수 없기 때문에 테스트가 실패 했다는 것을 설명 합니다. 일반적으로이 문제는 테스트 계정이 없거나 Lync Server에 대해 사용 하도록 설정 되지 않은 경우 발생 합니다. 계정이 있는지 확인 하 고 다음 예와 비슷한 명령을 실행 하 여 해당 계정이 nm-ocs-14-3에 대해 사용 하도록 설정 되었는지 여부를 확인 하는 방법을 알아 볼 수 있습니다.

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

테스트-CsGroupExpansion에 실패 하는 경우 자세한 정보 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Verbose 매개 변수를 포함 하는 경우 테스트-CsGroupExpansion에서 지정 된 사용자가 Lync Server에 로그온 하는 기능을 검사 한 경우 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 다음 출력은 지정 된 메일 그룹을 찾을 수 없음을 나타냅니다.

웹 티켓을 가져오려고 합니다.

웹 서비스 url:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

NTLM/Kerb 인증을 사용 합니다.

GetWebTicketActivity 완료 되었습니다.

' VerifyDistributionList ' 활동이 시작 되었습니다.

DLX 웹 서비스 응답 상태가 NotFound입니다.

' VerifyDistributionList ' 활동이 ' 0.2597923 ' 초 후에 완료 되었습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트-CsGroupExpansion 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다. 사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.

  - 그룹 확장을 사용 하지 않도록 설정 했을 수 있습니다. 그룹 확장을 해제할 수 있습니다. 그룹 확장을 사용 하지 않도록 설정한 경우 테스트-CsGroupExpansion cmdlet이 실패 합니다. 그룹 확장을 사용할 수 있는지 여부를 확인 하려면 다음과 같은 명령을 사용 합니다.
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

