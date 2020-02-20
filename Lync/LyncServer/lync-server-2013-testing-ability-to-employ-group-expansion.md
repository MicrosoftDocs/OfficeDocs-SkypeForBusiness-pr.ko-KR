---
title: 'Lync Server 2013: 그룹 확장을 사용 하는 기능 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to employ group expansion
ms:assetid: 9b0fc954-6f9c-411a-ab32-94ebabc42de2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743836(v=OCS.15)
ms:contentKeyID: 63969634
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3178b96d156b64fc55f05403d50b3f7fcaa246bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141634"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-employ-group-expansion-in-lync-server-2013"></a>Lync Server 2013에서 그룹 확장을 사용 하는 기능 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 CsGroupExpansion cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupExpansion&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsGroupExpansion cmdlet을 사용 하면 조직 내에서 그룹 확장이 작동 하는지 여부를 확인할 수 있습니다. 그룹 확장을 사용 하도록 설정 하면 사용자는 메일 그룹을 연락처로 구성 합니다. 따라서 이러한 사용자는 해당 그룹의 개별 구성원이 아니라 그룹에 대 한 메시지의 주소를 지정 하 여 모든 그룹 구성원에 게 동일한 인스턴트 메시지를 보낼 수 있습니다. 그룹 확장을 사용하면 모든 그룹 구성원과 이들의 현재 상태를 빠르고 쉽게 확인할 수 있습니다.

테스트-CsGroupExpansion cmdlet을 사용 하 여 그룹의 전자 메일 주소를 사용 하 여 Active Directory 메일 그룹을 지정할 수 있습니다. 그런 다음 테스트-CsGroupExpansion은 그룹 확장을 사용 하 여 그룹 구성원을 검색 하 고 검색 된 목록을 제공한 그룹 전자 메일 주소의 멤버 자격과 비교 합니다. 두 목록이 일치하면 그룹 확장이 제대로 작동하는 것입니다. 서비스 자체를 테스트 하거나 연결 된 웹 서비스를 테스트 하 여 두 가지 방법으로 그룹 확장을 테스트할 수 있습니다.

자세한 내용은 [테스트-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsGroupExpansion cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN과 유효한 메일 그룹의 전자 메일 주소를 지정 하기만 하면 됩니다. 예:

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호가 포함 된 Lync Server credentials 개체를 만들어야 합니다. 그런 다음 시스템에서 테스트-CsGroupExpansion을 호출할 때 해당 계정에 할당 된 자격 증명 개체 및 SIP 주소를 포함 해야 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

자세한 내용은 [테스트-CsGroupExpansion](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupExpansion) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자가 그룹 확장을 사용할 수 있는 경우 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:01.1234976

오류

진단을

지정한 사용자가 그룹 확장을 사용할 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetUrihttps://atl-cs-001.litwareinc.com:443/groupexpansion/service.svc

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류

진단을

테스트-CsGroupExpansion: 끝점을 등록할 수 없습니다. 특정 이유를 확인 하려면 ErrorCode를 참조 하세요.

이전 출력에서는 지정 된 사용자가 Lync Server에 등록할 수 없기 때문에 테스트가 실패 했다는 것을 나타냅니다. 이 오류는 일반적으로 테스트 계정이 없거나 Lync Server에 대해 사용 하도록 설정 되지 않은 경우에 발생 합니다. 계정이 존재 하는지 확인 하 고 다음과 같은 명령을 실행 하 여 계정이 nm-14-3에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

테스트-CsGroupExpansion 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsGroupExpansion -TargetFqdn "atl-cs-001.litwareinc.com" -GroupEmailAddress "Sales@litwareinc.com" -Verbose

Verbose 매개 변수를 포함 하는 경우 테스트-CsGroupExpansion은 지정 된 사용자가 Lync Server에 로그온 할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 다음 출력은 지정 된 메일 그룹을 찾을 수 없음을 나타냅니다.

웹 티켓을 가져오려고 했습니다.

웹 서비스 url:https://atl-cs-001.litwareinc.com:443/WebTicket/WebTicketService.svc

NTLM/Kerb 인증 사용

GetWebTicketActivity 완료 되었습니다.

' VerifyDistributionList ' 활동이 시작 되었습니다.

DLX Web Service 응답 상태가 NotFound입니다.

' VerifyDistributionList ' 작업이 ' 0.2597923 ' 초에 완료 되었습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

테스트-CsGroupExpansion 실패할 수 있는 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다. 사용자 계정이 Lync Server에 대해 사용 하도록 설정 되었는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.

  - 그룹 확장을 사용 하지 않도록 설정할 수 있습니다. 그룹 확장을 해제할 수 있습니다. 그룹 확장이 사용 하지 않도록 설정 된 경우에는 테스트-CsGroupExpansion cmdlet이 실패 합니다. 그룹 확장을 사용할 수 있는지 여부를 확인 하려면 다음과 같은 명령을 사용 합니다.
    
        Get-CsWebServiceConfiguration | Select-Object Identity, EnableGroupExpansion

</div>

</div>

<span> </span>

</div>

</div>

</div>

