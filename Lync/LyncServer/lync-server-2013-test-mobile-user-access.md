---
title: 'Lync Server 2013: 모바일 사용자 액세스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile user access
ms:assetid: 81d97420-428b-41b7-91ef-185d572d3456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767947(v=OCS.15)
ms:contentKeyID: 63969624
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8afea8450df1533928a0407fb81866351705186e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-mobile-user-access-in-lync-server-2013"></a>Lync Server 2013에서 모바일 사용자 액세스 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-06-07_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>확인 일정</p></td>
<td><p>월간</p></td>
</tr>
<tr class="even">
<td><p>테스트 도구</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>필요한 권한</p></td>
<td><p>Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 CsMcxConference cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할이 할당 되어야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

모바일 장치 서비스를 사용 하면 다음과 같은 작업을 수행할 수 있습니다.

1.  인스턴트 메시지 및 현재 상태 정보를 교환 합니다.

2.  사용자의 무선 공급자가 아닌 음성 사서함을 내부적으로 저장 하 고 검색 합니다.

3.  직장 및 전화 접속 회의를 통한 통화와 같은 Lync Server 기능을 활용 합니다. CsMcxConference cmdlet은 사용자가 모바일 장치를 사용 하 여 Lync Server 회의에 참가 하 고 참가할 수 있는지 확인 하는 빠르고 쉬운 방법을 제공 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

이 검사를 실행 하려면 각 계정에 대해 세 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다. 그런 다음 다음 예와 같이 Test-CsMcxConference를 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.

    $organizerCred = Get-Credential "litwareinc\kenmyer"
    $user1Cred = Get-Credential "litwareinc\packerman"
    $user2Cred = Get-Credential "litwareinc\adelaney"
    
    Test-CsMcxConference -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -OrganizerSipAddress "sip:kenmyer@litwareinc.com" -OrganizerCredential $organizerCred -UserSipAddress "sip:pilar@litwareinc.com" -UserCredential $user1Cred -User2SipAddress "sip:adelaney@litwareinc.com" -User2Credential $user2Cred

자세한 내용은 [CsMcxConference](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxConference) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

확인에 성공 하면 Test-CsMcxConference는 테스트 결과의 성공 여부를 보고 합니다.

대상 Fqdn: atl-cs-001.litwareinc.com

대상 Uri:http://atl-cs-001.litwareinc.com:443/mcx

결과: 성공

대기 시간: 00:00:00

오류 메시지:

진단을

확인이 실패 하면 Test-CsMcxConference는 실패의 테스트 결과를 보고 합니다. 이 테스트 결과에는 일반적으로 자세한 오류 메시지와 진단이 수반 됩니다. 예:

대상 Fqdn: atl-cs-001.litwareinc.com

대상 Uri:https://atl-cs-001.litwareinc.com:443/mcx

결과: 실패

대기 시간: 00:00:00

오류 메시지: 웹 티켓 서비스에 대 한 응답이 수신 되지 않습니다.

내부 예외: 클라이언트를 사용 하 여 HHTP 요청에 대 한 권한이 없습니다.

협상 구성표 ' Ntlm '. 수신 된 인증 헤더

서버에서 ' 협상 ' 되었습니다.

내부 예외: 원격 서버에서 오류를 반환 했습니다. (401)

권한.

진단을

내부 진단: X-Fqdb: atl-cs-001.litwareinc.com

Cache-컨트롤: private

Content-Type: text/html; charset = u t f-8

서버: Microsoft-IIS/8.5

WWW-인증: 협상, NTLM

X-전원 공급: ASP.NET

X-콘텐츠 형식-옵션: noexpression

날짜: 수요일, 28 년 5 월 2014 19:22:19 GMT

콘텐츠 길이: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Test-CsMcxConference 실패 하면 모바일 서비스가 실행 중이 고 액세스할 수 있는지 확인 하는 것으로 시작 해야 합니다. 이 작업은 웹 브라우저를 사용 하 여 Lync Server 풀의 모바일 서비스 URL에 액세스할 수 있는지를 확인 하는 데 사용할 수 있습니다. 예를 들어 다음 명령은 atl-cs-001.litwareinc.com 풀에 대 한 URL을 확인 합니다.

`https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc`

모바일 서비스에 액세스할 수 있는 경우 테스트 사용자에 게 유효한 Lync Server 계정이 있는지 확인 해야 합니다. 다음과 같은 명령을 사용 하 여 계정 정보를 검색할 수 있습니다.

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Enabled 속성이 True가 아니거나 명령이 실패 하는 경우에는 사용자에 게 유효한 Lync Server 계정이 없음을 의미 합니다. 또한 각 사용자 계정이 모바일 기능을 사용할 수 있는지 확인 해야 합니다. 이 작업을 수행 하려면 먼저 계정에 할당 된 모바일 정책을 결정 합니다.

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

정책 이름을 확인 한 후 Get-csmobilitypolicy cmdlet을 사용 하 여 문제의 정책 (예: RedmondMobilityPolicy)에 EnableMobility 속성이 True로 설정 되어 있는지 확인 합니다.

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

유효한 사용자 계정을 지정 하지 않은 것을 의미 하는 테스트-CsMcxConference를 실행할 때 "인증 헤더" 오류 메시지가 표시 되 면 사용자 이름 및 암호를 확인 한 후 테스트를 다시 시도 합니다. 사용자 계정이 유효한 것으로 확신 하는 경우 Set-cswebserviceconfiguration cmdlet을 사용 하 여 UseWindowsAuth 속성의 값을 확인 합니다. 그러면 조직에서 사용 하도록 설정 된 인증 방법을 확인할 수 있습니다.

모바일 서비스 문제를 해결 하는 방법에 대 한 자세한 내용은 블로그 게시물 [문제 해결 외부 Lync Mobility Connectivity 문제 단계별](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)설명을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

