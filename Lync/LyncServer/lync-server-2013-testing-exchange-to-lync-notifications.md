---
title: 'Lync Server 2013: Exchange를 Lync 알림으로 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing Exchange to Lync notifications
ms:assetid: ed2d6325-3cf5-4450-9951-03092bcb0a7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727315(v=OCS.15)
ms:contentKeyID: 63969665
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fba2f5ad22cb4a741192d5e4d51020b8c04cc39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-exchange-to-lync-notifications-in-lync-server-2013"></a>Lync Server 2013에서 Lync 알림 교환 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-11-01_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>CsExStorageNotification</strong> cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsExStorageNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**CsExStorageNotification** cmdlet은 사용자의 연락처 목록에 업데이트가 있을 때마다 Microsoft Exchange Server 2013 알림 서비스에서 Lync Server 2013에 알릴 수 있는지 확인 하는 데 사용 됩니다. 이 cmdlet은 통합 된 연락처 저장소를 사용 하는 경우에만 유효 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

예제 1에 나와 있는 명령을 사용 하 여 Lync Server 저장소 서비스에서 사용자 sip:kenmyer@litwareinc.com의 Microsoft Exchange Server 사서함 알림 서비스에 연결할 수 있는지 여부를 확인 합니다. 이 예제에서는 NetNamedPipe가 WCF 바인딩으로 사용 됩니다.

    Test-CsExStorageNotification -SipUri "sip:kenmyer@litwareinc.com" -Binding "NetNamedPipe"

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

Exchange 통합이 올바르게 구성 되어 있는 경우 결과 속성이 **성공**으로 표시 된 것과 비슷한 출력을 받게 됩니다.

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 성공

대기 시간: 00:00:00

오류 메시지:

있게

지정 된 사용자가 알림을 받을 수 없는 경우 결과가 실패로 표시 되 고 오류 및 진단 속성에 추가 정보가 기록 됩니다.

대상 Fqdn: atl-cs-001.litwareinc.com

결과: 실패

대기 시간: 00:00:00

오류 메시지: 10060, 연결 된 파티 때문에 연결 시도가 실패 했습니다.

일정 시간 후에 제대로 응답 하지 않았거나

연결 된 호스트가 다음 연결에 실패 하 여 성립

10.188.116.96에 응답 하지 못했습니다: 5061

내부 예외: 다음 이유로 인해 연결 시도가 실패 했습니다.

연결 된 상대방이 일정 기간 후에 적절 하 게 응답 하지 않았습니다.

연결 된 호스트 때문에 시간이 나 연결에 실패 했습니다.

님이 10.188.116.96에 응답 하지 못했습니다: 5061

있게

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

**테스트 CsExStorageNotification** 가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 사용 하는 경우 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - Microsoft Exchange Server가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[테스트-CsExStorageConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExStorageConnectivity)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

