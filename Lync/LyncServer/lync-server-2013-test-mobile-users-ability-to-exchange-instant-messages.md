---
title: 'Lync Server 2013: 인스턴트 메시지를 교환 하는 모바일 사용자 기능 테스트'
description: 'Lync Server 2013: 모바일 사용자가 인스턴트 메시지를 교환 하는 기능을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 675bbeff93fed374d950b2efbdf15b4ea246f861
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558294"
---
# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Lync Server 2013에서 모바일 사용자의 인스턴트 메시지 교환 기능 테스트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsMcxP2PIM cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

모바일 장치 서비스를 사용 하면 다음과 같은 작업을 수행할 수 있습니다.

1.  인스턴트 메시지 및 현재 상태 정보를 교환 합니다.

2.  사용자의 무선 공급자가 아닌 음성 사서함을 내부적으로 저장 하 고 검색 합니다.

3.  직장 및 전화 접속 회의를 통한 통화와 같은 Lync Server 기능을 활용 합니다.

Test-CsMxcP2PIM cmdlet은 사용자가 모바일 서비스를 사용 하 여 인스턴트 메시지를 교환할 수 있는지 확인 하는 빠르고 쉬운 방법을 제공 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

이 테스트를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호가 포함 된 개체)를 만들어야 합니다. 그런 다음 Test-csmcxp2pim를 호출할 때 이러한 자격 증명 개체와 두 계정의 SIP 주소를 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

자세한 내용은 [test-csmcxp2pim](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

두 테스트 사용자가 모바일 서비스를 사용 하 여 인스턴트 메시지를 교환할 수 있으면 Test-CsMcxP2PIM에서는 테스트 결과 성공을 반환 합니다.

대상 Fqdn: atl-cs-001.litwareinc.com

대상 Uri: http://atl-cs-001.litwareinc.com:443/mcx

결과: 성공

대기 시간: 00:00:00

오류 메시지:

진단을

테스트가 실패 하면 결과가 실패로 설정 되 고 자세한 오류 메시지와 진단이 표시 됩니다.

대상 Fqdn: atl-cs-001.litwareinc.com

대상 Uri: https://atl-cs-001.litwareinc.com:443/mcx

결과: 실패

대기 시간: 00:00:00

오류 메시지: Web-Ticket 서비스에 대 한 응답이 수신 되지 않았습니다.

내부 예외: HHTP 요청에 대해 권한이 부여 되지 않음

클라이언트 협상 구성표 ' Ntlm '. 인증

서버에서 받은 헤더가 ' 협상, NTLM ' 이었습니다.

내부 예외: 원격 서버에서 오류를 반환 했습니다.

(401) 인증 되지 않음

진단을

내부 진단: X-Fqdb: atl-cs-

001.litwareinc.com

Cache-Control: private

Content-Type: text/html; charset = u t f-8

서버: Microsoft-IIS/8.5

WWW-Authenticate: 협상, NTLM

X-전원 공급: ASP.NET

X-콘텐츠 형식-옵션: noexpression

날짜: 수요일, 28 년 5 월 2014 19:16:05 GMT

콘텐츠 길이: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Test-CsMcxP2PIM에 오류가 발생 하는 경우 첫 번째 단계는 mobility service가 작동 하 고 있는지 확인 해야 합니다. 이 작업은 웹 브라우저를 사용 하 여 Lync Server 풀의 모바일 서비스 URL에 액세스할 수 있는지를 확인 하는 데 사용할 수 있습니다. 예를 들어 다음 명령은 atl-cs-001.litwareinc.com 풀에 대 한 URL을 확인 합니다.

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

모바일 서비스가 실행 되 고 있는 것 처럼 보이면 두 테스트 사용자의 Lync Server 계정이 유효한 지 확인 합니다. 다음과 같은 명령을 사용 하 여 계정 정보를 검색할 수 있습니다.

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Enabled 속성이 True가 아니거나 명령이 실패 하는 경우에는 사용자에 게 유효한 Lync Server 계정이 없음을 의미 합니다.

또한 사용자가 모바일 기능을 사용할 수 있도록 설정 되어 있는지도 확인 해야 합니다. 이 작업을 수행 하려면 먼저 계정에 할당 된 모바일 정책을 결정 합니다.

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

정책 이름을 확인 한 후에 Get-CsMobilityPolicy cmdlet을 사용 하 여 문제의 정책 (예: RedmondMobilityPolicy)이 EnableMobility 속성을 True로 설정 했는지 확인 합니다.

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

인증 헤더와 함께 오류 메시지가 표시 되는 경우에는 종종 유효한 사용자 계정을 지정 하지 않은 것입니다. 사용자 이름 및 암호를 확인 한 후 테스트를 다시 시도 합니다. 사용자 계정이 유효한 것으로 확신 하면 Get-CsWebServiceConfiguration cmdlet을 사용 하 여 UseWindowsAuth 속성의 값을 확인 합니다. 그러면 조직에서 사용 하도록 설정 된 인증 방법을 확인할 수 있습니다. 모바일 서비스 문제를 해결 하는 방법에 대 한 자세한 내용은 블로그 게시물 [문제 해결 외부 Lync Mobility Connectivity 문제 단계별](https://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)설명을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

