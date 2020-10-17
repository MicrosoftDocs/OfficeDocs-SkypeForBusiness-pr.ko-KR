---
title: 'Lync Server 2013: 서비스 활성화 및 그룹 권한 테스트'
description: 'Lync Server 2013: 서비스 활성화 및 그룹 권한을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing service activation and group permissions
ms:assetid: 2c59e603-ba85-40ba-91a7-51c6fd39472e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743833(v=OCS.15)
ms:contentKeyID: 63969594
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 116cf939f3110616ce395eb14c7945890bdb89b7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556264"
---
# <a name="testing-service-activation-and-group-permissions-in-lync-server-2013"></a>Lync Server 2013에서 서비스 활성화 및 그룹 사용 권한 테스트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게 Test-CsTopology cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsTopology&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

Test-CsTopology cmdlet을 사용 하면 Lync Server 2013이 전역 범위에서 올바르게 작동 하 고 있는지 확인할 수 있습니다. 기본적으로 cmdlet은 전체 Lync Server 인프라를 검사 하 여 필요한 서비스가 실행 되 고 있는지 확인 하 고 이러한 서비스에 대 한 적절 한 권한이 설정 되어 있으며 Lync Server를 설치할 때 생성 되는 유니버설 보안 그룹을 확인 합니다.

Test-CsTopology에서는 Lync Server 설치의 유효성을 확인 하는 것 외에도 특정 서비스의 유효성을 확인할 수 있습니다. 예를 들어이 명령은 atl-cs-001.litwareinc.com 풀에서 A/V 회의 서버의 상태를 확인 합니다.

    Test-CsTopology -Service "ConferencingServer:atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

기본적으로 Test-CsTopology는 화면에 출력이 거의 표시 되지 않습니다. 대신, cmdlet에서 반환 된 정보가 HTML 파일에 기록 됩니다. Report 매개 변수를 사용 하면 Enable-cstopology에서 생성 되는 HTML 파일의 파일 경로와 파일 이름을 지정할 수 있습니다. Report 매개 변수를 포함 하지 않으면 HTML 파일이 사용자 폴더에 자동으로 저장 되 고 ce84964a-c4da-4622-ad34-c54ff3ed361f.html과 같은 이름이 지정 됩니다.

다음 예제 명령은 Test-CsTopology를 실행 하 고 출력을 C: \\ LogsComputerTest.html 이라는 파일에 저장 합니다 \\ .

    Test-CsTopology -Report "C:\Logs\ComputerTest.html" -Verbose

자세한 내용은 [enable-cstopology](https://docs.microsoft.com/powershell/module/skype/Test-CsTopology) cmdlet에 대 한 도움말 설명서를 참조 하십시오.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

대부분의 테스트 cmdlet과 달리, Test-CsTopology는 다시 성공 또는 실패를 보고 합니다. 예를 들어 많은 확인 검사로 인해 cmdlet이 실행 될 때마다이 작업을 수행 해야 합니다. 대신, 데이터를 HTML 보고서에 저장 한 후 Internet Explorer를 사용 하 여 볼 수 있습니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

Test-CsTopology 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 테스트 컴퓨터에서 복제가 최신 상태로 나타나지 않을 수 있습니다. Get-CsManagementStoreReplicationStatus cmdlet을 실행 하 여 컴퓨터의 현재 복제 상태를 확인할 수 있습니다.
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    복제 상태가 최신이 아닌 경우에는 다음과 같은 명령을 사용 하 여 수동으로 복제를 수행할 수 있습니다.
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - 토폴로지를 사용 하도록 설정 해야 할 수 있습니다. Lync Server 토폴로지를 변경 하는 경우 (로컬 컴퓨터에 영향을 줄 수 있는 변경 내용) 새 토폴로지를 사용 하도록 설정 해야 합니다. 다음 명령을 실행 하 여 언제 든 지 토폴로지를 사용 하도록 설정할 수 있습니다.
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

