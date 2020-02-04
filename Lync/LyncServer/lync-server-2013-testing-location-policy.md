---
title: 'Lync Server 2013: 위치 정책 테스트'
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
ms.openlocfilehash: 2a954405cb8dbba842250e0545ac8661d4f3795c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>Lync Server 2013의 테스트 위치 정책

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 테스트-CsLocationPolicy cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsLocationPolicy cmdlet은 위치 정책이 사용자에 게 할당 되었는지 확인 합니다. 위치 정책은 E9-1-1 기능 및 클라이언트 위치와 관련 된 설정을 적용 하는 데 사용 됩니다. 위치 정책은 사용자가 E9-1-1을 사용할 수 있는지 여부를 결정 하 고, 대답이 "예" 인 경우 비상 전화의 동작을 나타냅니다. 예를 들어 위치 정책을 사용 하 여 전화를 걸 번호를 정의할 수 있습니다 (미국에서는 911), 회사 보안에서 자동으로 알림을 받을 지 여부, 통화를 라우팅하는 방법을 정의 합니다.

사용자 또는 네트워크 서브넷에 대 한 위치 정책을 테스트할 수 있습니다. 서브넷 매개 변수에 대 한 값을 지정 하 여 서브넷에 대해 테스트를 실행 하는 경우 cmdlet은 해당 서브넷에 대 한 위치 정책 확인을 시도 합니다. 서브넷에 지정 된 위치 정책이 없는 경우, 구성 된 사용자에 대 한 위치 정책이 검색 됩니다. 서브넷 정책을 성공적으로 검색 하는 경우 LocationPolicyTagID에서 tagid로 시작 하는 값이 출력에 포함 됩니다. 서브넷에 대 한 위치 정책을 찾지 못한 경우 LocationPolicyTagID는 사용자-tagid으로 시작 됩니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsLocationPolicy cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 모든 사용자의 계정을 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예를 들면 다음과 같습니다.

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 먼저 계정 이름과 암호를 포함 하는 Windows PowerShell 자격 증명 개체를 만들어야 합니다. 그런 다음 테스트-CsLocationPolicy를 호출할 때 해당 자격 증명 개체와 해당 계정에 할당 된 SIP 주소를 포함 해야 합니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

자세한 내용은 [CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

지정 된 사용자에 게 유효한 위치 정책이 있는 경우 다음과 유사한 출력을 받고 결과 속성이 성공으로 표시 됨 **:**

EnhancedEmergencyServicesEnabled: true

LocationPolicyTagID: 사용자-tagid

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.8630376

오류

있게

지정 된 사용자에 대 한 유효한 위치 정책을 찾을 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 404, 찾을 수 없음

진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,

이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음

존재.

Microsoft DiagnosticHeader

이전 출력에서는 지정 된 사용자가 유효 하지 않기 때문에 테스트 실패 됨: 계정이 없거나 사용자에 게 Lync Server에 대 한 사용이 설정 되어 있지 않은 상태입니다. 계정의 유효성을 확인 하 고 다음과 같은 명령을 실행 하 여 해당 계정이 nm-ocs-14-3에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

테스트-CsLocationPolicy에 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수가 포함 된 경우 테스트-CsLocationPolicy는 위치 정책을 확인 하는 동안 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 다음 출력은 잘못 된 비밀 번호를 제공 하 여 Lync Server에서 테스트 사용자에 게 로그온 할 수 없음을 나타냅니다.

등록 요청 전송 중:

대상 Fqdn = atl-cs-011.litwareinc.com

사용자 Sip 주소 = sip:kenmyer@litwareinc.com

등록자 포트 = 5061

' IWA ' 인증 유형이 선택 되었습니다.

Sip/atl에 대 한 등록 적중률-cs-001 litwareinc .com

' 등록 ' 활동이 완료 되었습니다 (' 0.0601795 ' 초).

' 로그온이 거부 되었습니다. ' 라는 예외가 발생 했습니다. 올바른 자격 증명을 사용 하 고 있으며 계정이 활성 상태 인지 확인 합니다. ' 워크플로를 진행 하는 동안 발생 했습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트-CsLocationPolicy에서 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 유효 하지 않은 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다. Lync Server에 대해 사용자 계정이 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

