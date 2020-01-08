---
title: 'Lync Server 2013: 모바일 사용자가 인스턴트 메시지를 교환 하는 기능 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test mobile users' ability to exchange instant messages
ms:assetid: a78a048f-d413-4bee-8626-d62b8b74f811
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767950(v=OCS.15)
ms:contentKeyID: 63969638
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7fd19f6ef2f4a44a61d56848b4bf845c79736ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-mobile-users-ability-to-exchange-instant-messages-in-lync-server-2013"></a>Lync Server 2013에서 모바일 사용자의 인스턴트 메시지 교환 기능 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-06-07_


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
<td><p>권한이 필요 함</p></td>
<td><p>Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 CsMcxP2PIM cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxP2PIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

모바일 장치 사용자는 이동성 서비스를 통해 다음과 같은 작업을 수행할 수 있습니다.

1.  인스턴트 메시지와 현재 상태 정보를 교환 합니다.

2.  무선 공급자가 아닌 내부에서 음성 메일을 저장 하 고 검색 합니다.

3.  업무 및 전화 접속 회의를 통한 통화와 같은 Lync 서버 기능을 활용할 수가 있습니다.

CsMxcP2PIM cmdlet은 사용자가 모바일 서비스를 사용 하 여 인스턴트 메시지를 교환할 수 있는지 확인 하는 빠르고 쉬운 방법을 제공 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

이 테스트를 실행 하려면 각 계정에 대해 두 개의 Windows PowerShell 자격 증명 개체 (계정 이름과 암호를 포함 하는 개체)를 만들어야 합니다. 그런 다음 Test-CsMcxP2PIM를 호출할 때 두 계정의 SIP 주소와 이러한 자격 증명 개체를 포함 해야 합니다.

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\pilar"
    
    Test-CsMcxP2PIM -TargetFqdn "atl-cs-001.litwareinc.com" -Authentication Negotiate -SenderSipAddres "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:packerman@litwareinc.com" -ReceiverCredential $credential2

자세한 내용은 [테스트 CsMcxP2PIM](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxP2PIM) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

두 테스트 사용자가 모바일 서비스를 사용 하 여 인스턴트 메시지를 교환할 수 있는 경우 CsMcxP2PIM는 테스트 결과 성공을 반환 합니다.

대상 Fqdn: atl-cs-001.litwareinc.com

대상 Uri:http://atl-cs-001.litwareinc.com:443/mcx

결과: 성공

대기 시간: 00:00:00

오류 메시지:

있게

테스트에 실패 하면 결과가 실패로 설정 되 고 자세한 오류 메시지 및 진단이 표시 됩니다.

대상 Fqdn: atl-cs-001.litwareinc.com

대상 Uri:https://atl-cs-001.litwareinc.com:443/mcx

결과: 실패

대기 시간: 00:00:00

오류 메시지: 웹 티켓 서비스에 대 한 응답을 받지 못했습니다.

내부 예외: HHTP 요청에 다음이 허용 되지 않습니다.

클라이언트 협상 구성표 ' Ntlm '. 인증

서버에서 받은 헤더가 ' 협상, NTLM '입니다.

내부 예외: 원격 서버에서 오류를 반환 했습니다.

(401) 권한이 없습니다.

있게

내부 진단: X-MS-Fqdb: atl-cs-

001.litwareinc.com

캐시 제어: 비공개

콘텐츠 형식: text/html; charset = u t f-8

서버: Microsoft-IIS/8.5

WWW-인증: 협상, NTLM

X-구동 방법: ASP.NET

X-콘텐츠 형식-옵션: nosniff 선택 합니다.

날짜: 수요일, 28 월 2014 19:16:05 GMT

콘텐츠 길이: 6305

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트-CsMcxP2PIM가 실패 하는 경우 첫 번째 단계는 모바일 서비스가 켜져 있고 실행 중인지 확인 하는 것입니다. 이 작업은 웹 브라우저를 사용 하 여 Lync Server 풀의 모바일 서비스 URL에 액세스할 수 있는지 확인 하는 데 사용할 수 있습니다. 예를 들어이 명령은 풀 atl-cs-001.litwareinc.com에 대 한 URL을 확인 합니다.

    https://atl-cs-001.litwareinc.com/mcx/mcxservice.svc

모바일 서비스가 실행 되 고 있는 것으로 보이면 두 테스트 사용자의 Lync Server 계정이 유효한 지 확인 합니다. 다음과 같은 명령을 사용 하 여 계정 정보를 검색할 수 있습니다.

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object Enabled

Enabled 속성이 True가 아니거나 명령이 실패 한 경우에는 사용자에 게 유효한 Lync Server 계정이 없음을 의미 합니다.

또한 사용자가 이동성을 사용할 수 있는지 확인 해야 합니다. 이렇게 하려면 먼저 계정에 할당 된 이동성 정책을 결정 합니다.

    Get-CsUser -Identity "sip:kenmyer@litwareinc.com" | Select-Object MobilityPolicy

정책 이름을 알고 나면 CsMobilityPolicy cmdlet을 사용 하 여 문제의 정책 (예: RedmondMobilityPolicy)에 EnableMobility 속성이 True로 설정 되어 있는지 확인 합니다.

    Get-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

인증 헤더가 포함 된 오류 메시지가 표시 되는 경우에는 종종 유효한 사용자 계정을 지정 하지 않은 것입니다. 사용자 이름 및 암호를 확인 한 후 테스트를 다시 시도 합니다. 사용자 계정이 유효한 것으로 확신 하는 경우 CsWebServiceConfiguration cmdlet을 사용 하 여 UseWindowsAuth 속성 값을 확인 합니다. 이렇게 하면 조직에서 사용할 수 있는 인증 방법을 알 수 있습니다. 모바일 서비스 문제를 해결 하는 방법에 대 한 자세한 팁은 블로그 게시물 [문제 해결 외부 Lync 모바일 연결 문제를 단계별로](http://blogs.technet.com/b/nexthop/archive/2012/02/21/troubleshooting-external-lync-mobility-connectivity-issues-step-by-step.aspx)참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

