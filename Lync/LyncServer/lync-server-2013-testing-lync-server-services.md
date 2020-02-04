---
title: 'Lync Server 2013: Lync Server 서비스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing Lync Server services
ms:assetid: b564b450-a746-4ec9-aabb-e076309ccd5f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn689119(v=OCS.15)
ms:contentKeyID: 63969644
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdafd84f5a8edd21d6e62433d028ed735e37a37d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745658"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-lync-server-services-in-lync-server-2013"></a>Lync server 2013에서 Lync Server 서비스 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-06-05_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 테스트 CsComputer cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsComputer&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

테스트-CsComputer는 로컬 컴퓨터에서 실행 중인 모든 Lync Server 2013 서비스의 상태를 확인 합니다. (테스트 CsComputer는 로컬 에서만 실행할 수 있으며, Windows PowerShell의 원격 인스턴스에서는 실행할 수 없습니다.) 또한 cmdlet은 컴퓨터에서 적절 한 방화벽 포트가 열려 있는지 확인 하 고 Lync Server 2013을 설치할 때 만든 Active Directory 그룹이 해당 로컬 그룹에 추가 되었는지 여부를 확인 합니다. 예를 들어 테스트-CsComputer는 Active Directory 그룹 RTCUniversalUserAdmins 관리자 그룹에 추가 되었는지 확인 합니다.

자세한 내용은 [CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

로컬 컴퓨터 에서만 테스트 CsComputer cmdlet을 실행할 수 있으며, Windows PowerShell의 원격 인스턴스에서는 테스트 CsComputer를 호출할 수 없습니다. 기본적으로 테스트 CsComputer는 화면에 매우 적은 양의 출력을 표시 하며,이 경우 cmdlet에서 반환 되는 정보는 HTML 파일에 기록 됩니다. 이 때문에 테스트-CsComputer를 실행할 때마다 Verbose 매개 변수와 Report 매개 변수를 포함 하는 것이 좋습니다. Verbose 매개 변수는 cmdlet이 실행 되는 동안 약간 더 자세한 출력을 화면에 제공 합니다. Report 매개 변수를 사용 하면 테스트-CsComputer에서 생성 된 HTML 파일의 파일 경로와 파일 이름을 지정할 수 있습니다. 보고서 매개 변수를 포함 하지 않는 경우 HTML 파일은 사용자 폴더에 자동으로 저장 되 고 다음과 비슷한 이름이 지정 됩니다. ce84964a-c4da-4622-ad34-c54ff3ed36-1.html.

다음 샘플 명령은 테스트 CsComputer를 실행 하 고 출력을 C:\\Logs\\computertest. l l l: 이라는 파일에 저장 합니다.

    Test-CsComputer -Report "C:\Logs\ComputerTest.html" -Verbose

자세한 내용은 [CsComputer](https://docs.microsoft.com/powershell/module/skype/Test-CsComputer) cmdlet에 대 한 도움말 문서를 참조 하세요.

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

확인 검사의 수가 다르기 때문에 테스트-CsComputer가 간단한 **예, 테스트 성공** 또는 아니요를 다시 보고 하지 않으므로 **테스트가 실패**합니다. 대신 Internet Explorer를 사용 하 여 각 테스트의 성공 또는 실패 여부를 확인 하 여 생성 된 HTML 파일을 확인 해야 합니다.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

테스트 CsComputer가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 테스트 컴퓨터를 Lync Server에서 사용할 수 있도록 설정 하지 않았을 수 있습니다. 이 문제는 컴퓨터의 Lync Server 서비스 또는 서버 역할이 변경 되었고 CsComputer cmdlet을 실행 하지 않은 경우에 발생할 수 있습니다. 이 문제를 해결 하려면 다음 명령을 실행 합니다.
    
        Enable-CsComputer

  - 테스트 컴퓨터에서 복제가 최신 상태가 아닐 수 있습니다. Get-CsManagementStoreReplicationStatus cmdlet을 실행 하 여 컴퓨터에 대 한 현재 복제 상태를 확인할 수 있습니다.
    
        Get-CsManagementStoreReplicationStatus -ReplicaFqdn "atl-cs-001.litwareinc.com"
    
    복제 상태가 최신이 아닌 경우 다음과 같은 명령을 사용 하 여 복제를 수동으로 수행할 수 있습니다.
    
        Invoke-CsManagementStoreReplication -ReplicaFqdn "atl-cs-001.litwareinc.com"

  - 토폴로지를 사용 하도록 설정 해야 할 수 있습니다. Lync Server 토폴로지 (로컬 컴퓨터에 영향을 줄 수 있는 변경 내용)를 변경 하는 경우 새 토폴로지를 사용 하도록 설정 해야 합니다. 다음 명령을 실행 하 여 언제 든 지 토폴로지를 사용 하도록 설정할 수 있습니다.
    
        Enable-CsTopology

</div>

</div>

<span> </span>

</div>

</div>

</div>

