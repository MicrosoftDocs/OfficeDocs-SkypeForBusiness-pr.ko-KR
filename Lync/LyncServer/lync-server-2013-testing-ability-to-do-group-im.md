---
title: 'Lync Server 2013: 그룹 IM을 수행 하는 기능 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eef76c8728a7b5a569efee9305505f4e19f6bceb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194321"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Lync Server 2013에서 그룹 IM을 수행 하는 기능 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 CsGroupIM cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsGroupIM cmdlet은 조직의 사용자가 그룹 인스턴트 메시징 세션을 수행할 수 있는지 확인 합니다. 테스트-CsGroupIM을 실행 하면 cmdlet이 테스트 사용자 쌍에 Lync Server로 로그인을 시도 합니다. 성공하면 Test-CsGroupIM에서 첫 번째 테스트 사용자를 사용하여 새 전화 회의를 만든 다음 두 번째 사용자를 전화 회의에 참가하도록 초대합니다. 메시지를 교환한 후 두 사용자의 시스템 연결이 모두 끊어집니다. 이러한 모든 작업은 실제 사용자에 게 영향을 주지 않고 사용자 상호 작용 없이 발생 합니다. 예를 들어 테스트 계정 sip:kenmyer@litwareinc.com 실제 Lync Server 계정을 가진 실제 사용자에 해당 한다고 가정 합니다. 이 경우 실제 Ken Myer를 방해하지 않고 테스트가 수행됩니다. 예를 들어 Ken Myer 테스트 계정이 시스템에서 로그오프된 경우에도 실제 Ken Myer는 계속 로그온되어 있습니다. 마찬가지로 실제 Ken Myer는 전화 회의 참가 초대를 받을 수 없습니다. 이 초대는 테스트 계정에 전송되고 해당 계정에 의해 수락됩니다.

자세한 내용은 [CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsGroupIM cmdlet은 미리 구성 된 테스트 계정 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 Lync Server 관리 셸 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다. 그런 다음 테스트-CsGroupIM을 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

자세한 내용은 [CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

두 사용자가 그룹 인스턴트 메시징 세션을 완료할 수 있는 경우 Result 속성이 Success로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.3812203

오류

진단을

두 사용자가 인스턴트 메시징 세션을 완료할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 404, 찾을 수 없음

진단: ErrorCode = 4005, Source = atl-cs-001.litwareinc.com

이유 = 대상 URI가 SIP에 대해 사용 하도록 설정 되지 않았거나 지원 되지 않음

가.

Microsoft DiagnosticHeader

이전 출력에서는 계정이 없거나 사용자가 Lync Server에 대해 사용 하도록 설정 되지 않았으므로 테스트 계정 중 하나 이상이 올바르지 않아 테스트가 실패 했음을 나타냅니다. 이 계정이 있는지와 이와 유사한 명령을 실행 하 여 계정이 nm-14-3에 대해 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

테스트-CsGroupIM이 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수를 포함 하는 경우 테스트-CsGroupIM은 지정 된 사용자가 그룹 인스턴트 메시징 세션에 참가할 수 있는지 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어 테스트가 실패 하 여 하나 이상의 사용자 계정이 올바르지 않은 것으로 확인 되 면 Verbose 매개 변수를 사용 하 여 테스트를 다시 실행 하 고 어떤 사용자 계정이 유효한 지 확인할 수 있습니다.

등록 요청을 보내는 중:

 대상 Fqdn = atl-cs-001.litwareinc.com

 사용자 SIP 주소 = sip:kenmyer@litwareinc.com

 포트 등록 = 5061

인증 유형 ' IWA '이 선택 됩니다.

' 로그온이 거부 되었습니다. ' 라는 예외가 발생 했습니다. 올바른 자격 증명을 사용 하 고 있는지와 계정이 활성 상태 인지 확인 합니다.

여기에서 볼 수 있듯이이 예에서는 SIP 주소 sip:kenmyer@litwareinc.com을 가진 사용자가 로그온 할 수 없습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

테스트-CsGroupIM이 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다. 사용자 계정이 Lync Server에 대해 사용 하도록 설정 되었는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-개체 사용
    
    Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.

  - 인스턴트 메시징 서비스를 사용 하지 못할 수 있습니다. Lync Server에서는 보관 데이터베이스에 액세스할 수 없는 경우 인스턴트 메시징을 사용할 수 없도록 시스템을 구성할 수 있습니다. 다음과 같은 명령을 실행 하 여이를 확인할 수 있습니다.
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    BlockOnArchiveFailure이 True로 설정 된 경우 보관 데이터베이스를 사용할 수 있는지 여부를 확인 해야 합니다. 다음 명령을 사용 하 여 보관 데이터베이스의 위치를 반환할 수 있습니다.
    
        Get-CsService -ArchivingDatabase

  - 보관 서버를 사용 하지 못할 수 있습니다. 다음 명령을 사용 하 여 보관 서버의 FQDN을 검색할 수 있습니다.
    
        Get-CsService -ArchivingServer
    
    그런 다음 적절 한 서버에 ping을 수행 하 여 해당 서버가 사용 가능한 지 확인할 수 있습니다. 예를 들면 다음과 같습니다.
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

