---
title: 'Lync Server 2013: 테스트 위치 정책'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c676247eabbce1d6453308bdbba5a7df0754caf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194111"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>Lync Server 2013의 테스트 위치 정책

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 CsLocationPolicy cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsLocationPolicy cmdlet은 위치 정책이 사용자에 게 할당 되었는지 확인 합니다. 위치 정책은 E9-1-1 기능 및 클라이언트 위치와 관련된 설정을 적용하는 데 사용됩니다. 위치 정책은 사용자가 E9-1-1을 사용할 수 있는지 여부를 결정 하 고, 대답이 "예" 인 경우 긴급 통화의 동작을 나타냅니다. 예를 들어 위치 정책을 사용 하 여 긴급 통화를 구성 하는 번호 (미국에서는 911), 회사 보안에 자동으로 알릴지 여부 및 통화를 라우팅하는 방법을 정의할 수 있습니다.

사용자나 네트워크 서브넷에 대해 위치 정책을 테스트할 수 있습니다. Subnet 매개 변수의 값을 지정하여 서브넷에 대해 테스트를 실행하는 경우 이 cmdlet은 해당 서브넷에 대한 위치 정책을 확인하려고 합니다. 서브넷에 위치 정책이 할당되어 있지 않으면 구성된 사용자에 대한 위치 정책이 검색됩니다. 서브넷 정책을 성공적으로 검색 하면 LocationPolicyTagID 값이 서브넷-tagid로 시작 하는 출력에 포함 됩니다. 서브넷에 대한 위치 정책을 찾을 수 없는 경우 LocationPolicyTagID가 user-tagid로 시작합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsLocationPolicy cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호가 포함 된 Windows PowerShell 자격 증명 개체를 만들어야 합니다. 그런 다음 테스트-CsLocationPolicy를 호출할 때 해당 계정에 할당 된 자격 증명 개체 및 SIP 주소를 포함 해야 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

자세한 내용은 [CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자에 게 유효한 위치 정책이 있으면 결과 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

EnhancedEmergencyServicesEnabled: true

LocationPolicyTagID: 사용자-tagid

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.8630376

오류

진단을

지정 된 사용자에 대해 유효한 위치 정책을 찾을 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 404, 찾을 수 없음

진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com

이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음

가.

Microsoft DiagnosticHeader

이전 출력에서는 지정 된 사용자가 유효 하지 않거나 사용자가 Lync Server에 대해 사용 하도록 설정 되지 않아 테스트가 실패 했음을 나타냅니다. 계정의 유효성을 확인 하 고 다음과 같은 명령을 실행 하 여 해당 계정이 nm-14-3 세 번째에 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

테스트-CsLocationPolicy가 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수가 포함 된 경우 테스트-CsLocationPolicy는 위치 정책을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 다음과 같은 출력은 잘못 된 암호가 제공 되었기 때문일 수 있습니다.

등록 요청을 보내는 중:

대상 Fqdn = atl-cs-011.litwareinc.com

사용자 Sip 주소 = sip:kenmyer@litwareinc.com

등록자 포트 = 5061

인증 유형 ' IWA '이 선택 됩니다.

Sip/atl-litwareinc에 대 한 등록 적중

' 등록 ' 활동이 완료 되었습니다 (' 0.0601795 ' 초).

' 로그온이 거부 되었습니다. ' 라는 예외가 발생 했습니다. 올바른 자격 증명을 사용 하 고 있으며 계정이 활성 상태 인지 확인 합니다. ' 워크플로 중에 발생 했습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

테스트-CsLocationPolicy에 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다. 사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

