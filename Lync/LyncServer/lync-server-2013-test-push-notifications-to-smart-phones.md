---
title: 'Lync Server 2013: smart 전화로 푸시 알림 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01d3eaa5ffc629b194cea469949bf614cb42f696
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Lync Server 2013에서 smart 전화로 푸시 알림 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2017-03-15_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 CsMcxPushNotification cmdlet을 실행할 수 있는 권한이 있는 RBAC 역할이 할당 되어야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

푸시 알림 서비스 (Apple Push Notification Service 및 Microsoft Push Notification Service)는 Lync 클라이언트를 사용할 경우에도 새 인스턴트 메시지 또는 새 음성 메일과 같은 이벤트에 대 한 알림을 Iphone 및 Windows phone과 같은 모바일 장치에 보낼 수 있습니다. 이러한 장치는 현재 일시 중단 되었거나 백그라운드에서 실행 되 고 있습니다. 푸시 알림 서비스는 Microsoft 서버에서 실행 되는 클라우드 기반 서비스입니다. 푸시 알림을 사용 하려면 푸시 알림 clearinghouse에 연결 하 고 인증을 받을 수 있어야 합니다. 관리자는 CsMcxPushNotification cmdlet을 사용 하 여 푸시 알림 요청이에 지 서버를 통해 푸시 알림 clearinghouse로 라우팅되도록 할 수 있는지 확인 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

푸시 알림 서비스를 테스트 하려면 Test-CsMcxPushNotification cmdlet을 호출 합니다. 에 지 서버의 fqdn (정규화 된 도메인 이름)을 지정 했는지 확인 합니다.

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

자세한 내용은 [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

Test-CsMcxPushNotification가 성공한 경우 cmdlet은 테스트 결과 성공을 반환 합니다.

TargetFqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:00

오류

진단을

Test-CsMcxPushNotification이 푸시 알림 clearinghouse에 연결할 수 없는 경우 cmdlet은 일반적으로 실패의 테스트 결과를 반환 하지 않습니다. 대신 명령이 완전히 실패 하 게 됩니다. 예:

Test-CsMcxPushNotification: 네트워크에서 504 (서버 시간 초과) 응답이 수신 되었으며 작업이 실패 했습니다. 자세한 내용은 예외 정보를 참조 하세요.

줄: 1 문자: 27

\+Test-csmcxpushnotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+CategoryInfo: OperationStopped 됨: (:) \[Test-CsMcxPushNotification\], FailureResponseException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. SyntheticTransactions. TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

에 지 서버와 통신 하는 데 문제가 있거나 푸시 알림 클리어 링 하우스와 통신 하는 데 문제가 있는 경우 푸시 알림 서비스에서 오류가 발생 합니다. Test-CsMcxPushNotification를 실행할 때 문제가 발생 하는 경우에는에 지 서버가 올바르게 작동 하는지 확인 해야 합니다. 이 작업을 수행 하는 한 가지 방법은 Test-csavedgeconnectivity cmdlet을 사용 하는 것입니다.

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

이 검사는 지정 된 사용자가에 지 서버에 연결할 수 있는지 확인 합니다.

에 지 서버가 정상적으로 작동 하는 것 처럼 보이면 대개 푸시 알림 clearinghouse에 연결할 수 없다는 것을 의미 합니다. 이는 일반적으로 clearinghouse URI를 올바르게 구성 하지 않았거나이 URL을 가리키는 DNS SRV 레코드가 없는 것을 의미 합니다. 다음 명령을 실행 하 여 URI가 올바른 값 (sip:push@push.lync.com)으로 설정 되어 있는지 확인할 수 있습니다.

    Get-CsMcxConfiguration

PushNotificationProxyUri 속성이 sip:push@push.lync.com 이외의 다른 값으로 설정 된 경우에는 집합-McxConfiguration cmdlet을 사용 하 여 해당 문제를 해결할 수 있습니다. 예를 들어이 명령은 조직 전체에서 URI를 올바르게 설정 합니다.

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

자세한 내용은 [CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.

URI가 올바르게 구성 된 경우 다음 단계는 SIP 도메인 및에 지 서버로 확인 되는 DNS SRV 레코드가 있는지 확인 하는 것입니다. 이러한 레코드를 구성 하는 방법에 대 한 자세한 내용은 모바일 기능에 대 한 DNS 요구 사항 항목을 참조 하십시오. 일반적으로 다음 오류 메시지는 DNS 레코드에 문제가 있음을 나타냅니다.

네트워크에서 504 (서버 시간 초과) 응답이 수신 되었으며 작업에 실패 했습니다. 자세한 내용은 예외 정보를 참조 하세요.

또한이 오류 메시지와 함께 CsMcxConfiguration이 실패할 수도 있습니다.

Test-CsMcxPushNotification: 푸시 알림 요청이 거부 되었습니다.

줄: 1 문자: 27

\+Test-CsMcxPushNotification\<\<\<\<

\+CategoryInfo: OperationStopped 됨: (:) \[Test-CsMcxPushNotification\], SyntheticTransactionException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. SyntheticTransactions. TestMcxPushNotificationCmdlet

"푸시 알림 요청이 거부 되었습니다." 메시지는 일반적으로 URL 필터링을 사용 하도록 설정 하 고 http: 및 https: 접두사를 차단 하는 경우에 발생 합니다. 다음과 같은 명령을 사용 하 여 차단 되는 접두사를 확인할 수 있습니다.

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

Http: 또는 https:가 결과에 표시 되는 경우 푸시 알림이 작동 하려면 차단 된 접두사 목록에서 제거 해야 합니다. 다음과 같은 명령을 사용 하 여이 작업을 수행할 수 있습니다.

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

자세한 내용은 [CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration)cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

