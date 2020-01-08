---
title: 'Lync Server 2013: 그룹 메신저 기능 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c371db385b29f68aa8cc9280a901d095c43f2ac2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976690"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Lync Server 2013에서 그룹 메신저를 수행 하는 방법 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 테스트-CsGroupIM cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsGroupIM cmdlet은 조직의 사용자가 그룹 인스턴트 메시징 세션을 수행할 수 있는지 확인 합니다. 테스트-CsGroupIM을 실행 하는 경우 cmdlet은 테스트 사용자 쌍을 Lync Server에 로그인 하려고 합니다. 성공 하면 테스트-CsGroupIM이 첫 번째 테스트 사용자를 사용 하 여 새 회의를 만든 다음 두 번째 사용자를 초대 하 여 회의에 참가 합니다. 메시지를 교환 한 후에는 두 사용자가 모두 시스템에서 연결이 끊깁니다. 이러한 모든 작업은 사용자 조작 없이, 실제 사용자에 게는 영향을 주지 않습니다. 예를 들어 테스트 계정 sip:kenmyer@litwareinc.com 실제 Lync Server 계정이 있는 실제 사용자에 해당 한다고 가정 합니다. 이 경우 실제: 진구 Myer에 대 한 장애 없이 테스트를 수행 합니다. 예를 들어: 진구 Myer 테스트 계정이 시스템에서 로그 오프 하는 경우에도: 진구 Myer는 해당 사용자의 로그온 상태를 유지 합니다. 마찬가지로, 실제: 진구 Myer는 회의 참가 초대를 받을 수 없습니다. 해당 초대가 테스트 계정에 전송 되 고 수락 됩니다.

자세한 내용은 [CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsGroupIM cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server에 대해 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트 중인 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예를 들면 다음과 같습니다.

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대 한 두 개의 Lync Server 관리 셸 자격 증명 개체 (계정 이름과 암호를 포함 하는 개체)를 만들어야 합니다. 그런 다음 테스트-CsGroupIM을 호출할 때 다음과 같은 두 계정의 SIP 주소와 이러한 자격 증명 개체를 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

자세한 내용은 [CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

두 명의 사용자가 그룹 메신저 대화 세션을 완료할 수 있는 경우 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.3812203

오류

있게

두 명의 사용자가 인스턴트 메시징 세션을 완료할 수 없는 경우 결과는 오류로 표시 되며 추가 정보는 오류 및 진단 속성에 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 404, 찾을 수 없음

진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com,

이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음

존재.

Microsoft DiagnosticHeader

이전 출력은 계정이 없거나 사용자가 Lync Server에 대해 사용 하도록 설정 되지 않았으므로 테스트 계정 중 하나 이상이 유효 하지 않기 때문에 테스트에 실패 했음을 명시 합니다. 계정이 있는지 확인 하 고, 다음과 유사한 명령을 실행 하 여 해당 계정이 nm-ocs-14-3에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

테스트-CsGroupIM이 실패 하는 경우 다음과 같이 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수가 포함 된 경우 테스트-CsGroupIM은 지정 된 사용자가 그룹 인스턴트 메시지 세션에 참여할 수 있는 기능을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 테스트가 실패 하 고 하나 이상의 사용자 계정이 유효 하지 않은 것으로 표시 되는 경우 Verbose 매개 변수를 사용 하 여 테스트를 다시 실행 하 고 잘못 된 사용자 계정이 있는지 확인할 수 있습니다.

등록 요청 전송 중:

 대상 Fqdn = atl-cs-001.litwareinc.com

 사용자 SIP 주소 = sip:kenmyer@litwareinc.com

 포트 등록 = 5061

' IWA ' 인증 유형이 선택 되었습니다.

' 로그온이 거부 되었습니다. ' 라는 예외가 발생 했습니다. 올바른 자격 증명을 사용 하 고 있고 계정이 활성 상태 인지 확인 합니다. '

이 예제에서 SIP 주소 sip:kenmyer@litwareinc.com를 가진 사용자는 로그온 할 수 없습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트-CsGroupIM이 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 현재 Lync Server에서 계정을 사용할 수 없습니다. 사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
    Get-CsUser "sip:kenmyer@litwareinc.com" | 선택-개체 사용
    
    Enabled 속성이 False로 설정 된 경우 사용자가 현재 Lync Server에 대해 사용 하도록 설정 되어 있지 않음을 의미 합니다.

  - 메신저 서비스를 사용 하지 못할 수 있습니다. Lync Server를 사용 하 여 보관 데이터베이스에 액세스할 수 없는 경우 인스턴트 메시지를 사용할 수 없도록 시스템을 구성할 수 있습니다. 다음과 같은 명령을 실행 하 여 확인할 수 있습니다.
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    BlockOnArchiveFailure가 True로 설정 된 경우 보관 데이터베이스를 사용할 수 있는지 여부를 확인 해야 합니다. 다음 명령을 사용 하 여 보관 데이터베이스의 위치를 반환할 수 있습니다.
    
        Get-CsService -ArchivingDatabase

  - 보관 서버를 사용할 수 없는 경우일 수 있습니다. 다음 명령을 사용 하 여 보관 서버의 FQDN을 검색할 수 있습니다.
    
        Get-CsService -ArchivingServer
    
    그런 다음 적절 한 서버에 ping을 사용 하 여 사용할 수 있는지 확인할 수 있습니다. 예를 들면 다음과 같습니다.
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

