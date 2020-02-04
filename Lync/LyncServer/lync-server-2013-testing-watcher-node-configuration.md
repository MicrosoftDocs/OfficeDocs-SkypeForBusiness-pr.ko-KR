---
title: 'Lync Server 2013: 감시자 노드 구성 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing watcher node configuration
ms:assetid: f9ecd85c-0ae9-4906-b786-6b002b5a77c6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn751537(v=OCS.15)
ms:contentKeyID: 63969667
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 920fc39d3800f83a2d40a613c391b2f0c93e4dac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745268"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-watcher-node-configuration-in-lync-server-2013"></a>Lync Server 2013에서 감시자 노드 구성 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-11-03_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>CsWatcherNodeConfiguration</strong> cmdlet을 실행 하는 데 필요한 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot; Test-CsWatcherNodeConfiguration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Microsoft System Center Operations Manager를 사용 하 여 Lync Server 2013을 모니터링 하는 경우 "감시자 노드": 정기적으로 자동으로 실행 되는 컴퓨터를 설정 하 여 Lync Server가 작동 하는지 확인 하는 옵션을 선택할 수 있습니다. 예상. 감시자 노드는 풀에 할당 되며 **CsWatcherNodeConfiguration** cmdlet을 사용 하 여 관리 됩니다. System Center Operations Manager를 사용 하는 경우 감시자 노드를 설치할 필요가 없습니다. 감시자 노드를 사용 하지 않고 계속 시스템을 모니터링할 수 있습니다. 유일한 차이점은 실행 하려는 모든 가상 트랜잭션은 Operations Manager에서 자동으로 호출 되지 않고 수동으로 호출 되어야 한다는 것입니다.

**CsWatcherNodeConfiguration** cmdlet을 사용 하면 감시자 노드가 올바르게 구성 되어 있고 유효한 Lync Server 2013 풀에 할당 되어 있는지 확인할 수 있습니다. **CsWatcherNodeConfiguration** cmdlet은 감시자 노드 자체에서 실행 되어야 한다는 점에 유의 하세요. 원격 컴퓨터에 대해 cmdlet을 실행할 수 없습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

다음 명령은 조직에서 사용 중인 각 감시자 노드에 대 한 구성 설정을 확인 합니다.

    Test-CsWatcherNodeConfiguration

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

다음의 성공한 예제 출력에서는 edge 서버가 4 개 있는 시스템을 보여 줍니다.

토폴로지에 대해 대상 풀 atl-cs-001.litwareinc.com 유효성 검사.

성공: 대상 풀 atl-cs-001.litwareinc.com 토폴로지에 있습니다.

성공: 대상 풀 atl-cs-001.litwareinc.com에 등록자 역할이 설치 되어 있습니다.

성공: 대상 풀 atl-cs-001.litwareinc.com가 지원 되는 버전입니다.

성공: 5061 대상 풀 atl-cs-001.litwareinc.com의 포트 번호가 올바릅니다.

감시자 노드 구성의 누락 된 풀에 대 한 확인이 시작 되었습니다. 오류가 발견 되 면 인쇄 됩니다.

감시자 노드 구성의 누락 된 풀에 대 한 검사가 완료 되었습니다.

감시자 노드 설치에서 만든 감시자 노드 레지스트리 키에 대 한 확인이 시작 됩니다. 오류가 발견 되 면 인쇄 됩니다.

감시자 노드 설치에서 만든 감시자 노드 레지스트리 키를 확인 하는 작업이 완료 되었습니다. 인증 유형이 협상 됨을 감지 했습니다.

테스트 사용자의 자격 증명 sip (자격 증명 관리 저장소의 user1@ atl-cs-001.litwareinc.com의 유효성을 검사 했습니다.

테스트 사용자의 자격 증명 sip (자격 증명 관리 저장소의 user2@ atl-cs-001.litwareinc.com의 유효성을 검사 했습니다.

감시자 노드 구성의 누락 된 풀에 대 한 확인이 시작 되었습니다. 오류가 발견 되 면 인쇄 됩니다.

경고: 풀 atl-cs-001.litwareinc.com에 등록 자가 있습니다.

역할이 설치 되었지만 테스트 사용자가 구성 되어 있지 않습니다.

감시자 노드 구성의 누락 된 풀에 대 한 검사가 완료 되었습니다.

감시자 노드 설치에서 만든 감시자 노드 레지스트리 키를 확인 하는 중

했. 오류가 발견 되 면 인쇄 됩니다.

테스트-CsWatcherNodeConfiguration:에서 상태 레지스트리 키를 찾을 수 없음

소프트웨어\\Microsoft\\실시간 통신. 감시자 노드일 수 있는지 확인 합니다. msi

제대로 설치 되어 있습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

**테스트 CsWatcherNodeConfiguration** 가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 감시자 노드가 올바르게 설치 되지 않았습니다.

  - 구성 된 테스트 사용자가 없습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsWatcherNodeConfiguration)  
[New-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsWatcherNodeConfiguration)  
[제거-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsWatcherNodeConfiguration)  
[Set-CsWatcherNodeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsWatcherNodeConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

