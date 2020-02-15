---
title: 'Lync Server 2013: 두 사용자 간의 IM 기능 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing ability to IM between two users
ms:assetid: a0f3f5c6-f115-4c3f-90ac-5fdc932b417e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743838(v=OCS.15)
ms:contentKeyID: 63969635
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d08627842b5a58a72801a018e8e8da49fcdeb249
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42015371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-im-between-two-users-in-lync-server-2013"></a>Lync Server 2013에서 두 사용자 간의 IM 기능 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우에는 사용자에 게 CsIM cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

CsIM cmdlet은 테스트 사용자 쌍이 인스턴트 메시지를 교환할 수 있는지 확인 합니다. 호출 되 면 test users 쌍을 Lync Server에 로그온 하 여 CsIM cmdlet이 시작 되지 않습니다. 두 로그온이 성공 했다고 가정 하면 cmdlet은 두 테스트 사용자 간에 IM 세션을 시작 합니다. (사용자 1이 IM 세션에 2 사용자를 초대 하 고, 사용자 2가 초대를 수락 합니다.) 두 사용자 간에 메시지를 교환할 수 있는지 확인 한 후에는 Test-CsIM이 IM 세션을 종료 하 고 시스템에서 두 사용자를 모두 기록 합니다.

자세한 내용은 [CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

테스트-CsIM cmdlet은 미리 구성 된 테스트 계정 쌍 (Lync Server 테스트 실행을 위한 테스트 계정 설정 참조) 또는 Lync Server를 사용 하도록 설정 된 두 사용자의 계정 중 하나를 사용 하 여 실행할 수 있습니다. 테스트 계정을 사용 하 여이 검사를 실행 하려면 테스트할 Lync Server 풀의 FQDN만 지정 하면 됩니다. 예:

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com"

실제 사용자 계정을 사용 하 여이 검사를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다. 그런 다음 Test-CsIM을 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

자세한 내용은 [CsIM](https://docs.microsoft.com/powershell/module/skype/Test-CsIM) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

두 사용자가 인스턴트 메시징 세션을 완료할 수 있으면 결과 속성이 성공으로 표시 된 것과 비슷한 출력을 받게 됩니다 **.**

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:06.6630911

오류

진단을

테스트 사용자가 세션을 완료할 수 없으면 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류: 504, 서버 제한 시간

진단: ErrorCode = 2, Source = atl-cs-litwareinc, Reason = 참고

응답 코드 및 이유 구입니다.

Microsoft DiagnosticHeader

예를 들어 위의 출력에서는 지정 된 사용자를 찾을 수 없기 때문에 테스트가 실패 했다는 것을 나타냅니다. 다음 명령을 실행 하 여 SIP 주소가 유효한 지 여부와 해당 SIP 주소를 할당 한 사용자가 Lync Server를 사용 하도록 설정 되었는지 여부를 확인할 수 있습니다.

    Get-CsUser "Ken Myer" | Select-Object SipAddress, Enabled

Test-CsIM이 실패 하면 다음 시간에 Verbose 매개 변수를 포함 하 여 테스트를 다시 실행할 수 있습니다.

    Test-CsIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Verbose 매개 변수가 포함 된 경우 Test-CsIM은 두 테스트 사용자가 IM 세션에 참가 하는 기능을 확인할 때 시도한 각 작업의 단계별 계정을 반환 합니다. 예를 들어, 다음은 Test-CsIM에 잘못 된 사용자 자격 증명 집합 (이 경우 잘못 된 암호)을 제공 했을 때 발생 하는 예제 출력입니다.

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

Test-CsIM이 실패할 수 있는 일반적인 이유는 다음과 같습니다.

  - 잘못 된 사용자 계정을 지정 했습니다. 다음과 같은 명령을 실행 하 여 사용자 계정이 있는지 확인할 수 있습니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - 사용자 계정이 올바르지만 해당 계정이 Lync Server에 대해 현재 사용 하도록 설정 되어 있지 않습니다. 사용자 계정이 Lync Server에 대해 사용 하도록 설정 되어 있는지 확인 하려면 다음과 같은 명령을 실행 합니다.
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Enabled 속성을 False로 설정 하면 사용자가 현재 Lync Server를 사용할 수 없습니다.

  - 인스턴트 메시징 서비스를 사용 하지 못할 수 있습니다. Lync Server에서는 보관 데이터베이스에 액세스할 수 없는 경우 IM을 사용할 수 없도록 시스템을 구성할 수 있습니다. 다음과 같은 명령을 실행 하 여이를 확인할 수 있습니다.
    
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

