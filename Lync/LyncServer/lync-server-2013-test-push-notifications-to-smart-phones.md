---
title: 'Lync Server 2013: 스마트 전화로 푸시 알림 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653becc1cc22abc8b3c04e0ab3d2a2d1260a98d9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Lync Server 2013에서 스마트 전화로 푸시 알림 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2017-03-15_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsMcxPushNotification cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

푸시 알림 서비스 (Apple 푸시 알림 서비스 및 Microsoft 푸시 알림 서비스)는 Lync 클라이언트가 Iphone, Windows phone 등의 모바일 장치에 대 한 새 인스턴트 메시지 또는 새 음성 메일과 같은 이벤트에 대 한 알림을 보낼 수 있습니다. 이러한 장치는 현재 일시 중지 되었거나 백그라운드에서 실행 되 고 있습니다. 푸시 알림 서비스는 Microsoft 서버에서 실행 되는 클라우드 기반 서비스입니다. 푸시 알림을 활용 하려면 푸시 알림 clearinghouse에 연결 하 고 인증할 수 있어야 합니다. 관리자는 테스트-CsMcxPushNotification cmdlet을 사용 하 여 푸시 알림 요청이 Edge 서버를 통해 푸시 알림 clearinghouse에 라우팅되도록 할 수 있는지 확인 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

푸시 알림 서비스를 테스트 하려면 Test-CsMcxPushNotification cmdlet을 호출 합니다. Edge 서버의 정규화 된 도메인 이름을 지정 했는지 확인 합니다.

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

자세한 내용은 [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

테스트-CsMcxPushNotification이 성공 하면 cmdlet이 테스트 결과 성공을 반환 합니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:00

오류

있게

테스트-CsMcxPushNotification이 푸시 알림 clearinghouse에 연결할 수 없는 경우 일반적으로 cmdlet은 실패의 테스트 결과를 반환 하지 않습니다. 대신 명령이 완전 하 게 실패 합니다. 예를 들면 다음과 같습니다.

테스트-CsMcxPushNotification: 네트워크에서 504 (서버 시간 초과) 응답을 받았으며 작업이 실패 했습니다. 자세한 내용은 예외 정보를 참조 하세요.

줄: 1 char: 27

\+테스트-csmcxpushnotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+CategoryInfo: OperationStopped 됨: (:) \[테스트-CsMcxPushNotification\], FailureResponseException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft SyntheticTransactions. TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

일반적으로 Edge 서버와 통신 하는 데 문제가 있거나 푸시 알림 클리어 링 하우스와 통신 하는 데 문제가 있는 경우 푸시 알림 서비스에 실패 합니다. Test-CsMcxPushNotification 실행할 때 문제가 발생 하는 경우에는 Edge 서버가 올바르게 작동 하는지 확인 하는 것이 가장 좋습니다. 이 작업을 수행 하는 한 가지 방법은 테스트 CsAVEdgeConnectivity cmdlet을 사용 하는 것입니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

이 검사는 지정 된 사용자가 Edge 서버에 연결할 수 있는지 확인 합니다.

Edge 서버가 올바르게 작동 하는 것 처럼 보이면이는 푸시 알림 clearinghouse에 연결할 수 없음을 의미 합니다. 즉, 일반적으로 clearinghouse URI를 올바르게 구성 하지 않았거나이 URL을 가리키는 DNS SRV 레코드가 없다는 의미입니다. 다음 명령을 실행 하 여 URI가 올바른 값 (sip:push@push.lync.com)으로 설정 되어 있는지 확인할 수 있습니다.

    Get-CsMcxConfiguration

PushNotificationProxyUri 속성이 sip:push@push.lync.com 이외의 다른 값으로 설정 된 경우 Set-McxConfiguration cmdlet을 사용 하 여 해당 문제를 해결할 수 있습니다. 예를 들어 다음 명령을 실행 하면 조직 전체에서 URI가 올바르게 설정 됩니다.

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

자세한 내용은 [Set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet에 대 한 도움말 항목을 참조 하세요.

URI가 올바르게 구성 되어 있는 경우 다음 단계는 SIP 도메인 및 Edge 서버로 확인 되는 DNS SRV 레코드가 있는지 확인 하는 것입니다. 이러한 레코드를 구성 하는 방법에 대 한 자세한 내용은 도움말 항목인 이동성에 대 한 DNS 요구 사항 항목을 참조 하세요. 일반적으로 다음 오류 메시지는 DNS 레코드에 문제가 있음을 나타냅니다.

네트워크에서 504 (서버 시간 초과) 응답이 수신 되어 작업이 실패 했습니다. 자세한 내용은 예외 정보를 참조 하세요.

또한이 오류 메시지와 함께 테스트-CsMcxConfiguration이 실패할 수 있습니다.

테스트-CsMcxPushNotification: 푸시 알림 요청이 거부 되었습니다.

줄: 1 char: 27

\+테스트-CsMcxPushNotification\<\<\<\<

\+CategoryInfo: OperationStopped 됨: (:) \[테스트-CsMcxPushNotification\], SyntheticTransactionException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft SyntheticTransactions. TestMcxPushNotificationCmdlet

"푸시 알림 요청이 거부 되었습니다." 메시지는 일반적으로 URL 필터링을 사용 하도록 설정 하 고 http: 및 https: 접두사를 차단 하는 경우에 발생 합니다. 다음과 같은 명령을 사용 하 여 차단 되는 접두 번호를 확인할 수 있습니다.

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

Http: 또는 https:가 결과에 표시 되는 경우 푸시 알림이 작동 하도록 차단 된 접두사 목록에서 제거 해야 합니다. 다음과 같은 명령을 사용 하 여이 작업을 수행할 수 있습니다.

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

자세한 내용은 [Set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

