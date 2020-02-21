---
title: 'Lync Server 2013: 복제본 서비스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cae11cce4d4214f0392304823710fe1f02a36f7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193791"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>Lync Server 2013에서 복제본 서비스 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-11-03_


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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 <strong>CsReplica</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할이 할당 되어야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**테스트-csreplica** cmdlet은 로컬 컴퓨터에서 Lync Server 2013 복제본 서비스가 실행 되 고 있는지 확인 합니다. **테스트-CsReplica** cmdlet은 다음과 같은 작업을 수행 합니다.

  - 복제기 에이전트 및 중앙 로깅 에이전트 서비스의 상태 확인

  - Windows 방화벽에서 필요한 포트가 열려 있는지 확인

  - 필요한 Active Directory 및 로컬 컴퓨터 보안 그룹이 있는지 확인

이 cmdlet은 로컬로 실행 해야 합니다. 즉, 복제 서비스가 실행 되 고 있는 동일한 컴퓨터에서 실행 되어야 합니다. 원격 서버에 대해 **CsReplica** cmdlet을 실행 하기 위한 옵션은 없습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

예제 1에 표시 된 명령은 로컬 컴퓨터에서 Lync Server 2013 복제본 서비스를 테스트 합니다. 이 예제에서는 Verbose 매개 변수를 사용 하 여 테스트에 대 한 성공 또는 실패를 비롯 하 여 테스트를 통해 생성 된 보고서의 위치와 화면에 표시 되는 결과를 확인 합니다.

    Test-CsReplica -Verbose

예제 2는 예제 1에 표시된 명령의 변형입니다. 이 경우 Report 매개 변수는 테스트에서 생성 된 보고서의 폴더 경로와 이름을 지정 하는 데 포함 됩니다. 보고서 경로를 지정 하지 않으면 보고서에 다음과 유사한 자동 생성 이름이 지정 됩니다.

C:\\사용자\\관리자. Litwareinc\\AppData\\Local\\Temp\\1\\Test-.cs-3db40ee0-4b5d-4f58-8d3d-b1e61253129e .html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

여기에 섹션 본문을 삽입합니다.

VERBOSE: 새 로그 파일 만들기 "C:\\사용자\\테스트\\AppData\\Local\\Temp\\테스트-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c" .xml "을 만듭니다.

VERBOSE: 새 로그 파일 만들기 "C:\\사용자\\테스트\\AppData\\Local\\Temp\\테스트-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c" .xml "을 만듭니다.

VERBOSE: "테스트-CsReplica" 처리가 완료 되었습니다.

VERBOSE: 자세한 결과는 "C\\: 사용자\\테스트\\AppData\\Local\\Temp\\Test-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c)에서 찾을 수 있습니다.

VERBOSE: 새 로그 파일 만들기

"C:\\사용자\\테스트\\AppData\\로컬\\온도\\2\\테스트-csreplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083 ".

VERBOSE: 새 로그 파일 만들기

"C:\\사용자\\테스트\\AppData\\로컬\\온도\\2\\테스트-csreplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083 "

경고: 테스트-CsReplica에 오류가 발생 했습니다.

경고: 자세한 결과는 다음 위치에서 찾을 수 있습니다.

"C:\\사용자\\테스트\\AppData\\로컬\\온도\\2\\테스트-csreplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083 "

테스트-CsReplica: 명령 실행 실패: 요청 된 레지스트리 액세스 권한 없음

있도록.

줄: 1 문자: 1

\+테스트-CsReplica-자세한 정보 표시

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: InvalidOperation: (:) \[테스트-csreplica\], Security

오류

\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. .Deploy

주석. TestReplicaCmdlet

PS C:\\사용자\\테스트\>

PS C:\\Test-csucwaconference\\-\> Targetfqdn "lynctest"를 테스트 하는 사용자

icrosoft.com "

경고: 지정한 정규화 된 자격에 대 한 등록자 포트 번호를 읽지 못했습니다.

FQDN (도메인 이름) 기본 등록자 포트 번호 사용 오류

InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

구독자

SyntheticTransactions SipSyntheticTransaction TryRetri를 관리 합니다.

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-csucwaconference: 할당 된 테스트 사용자가 없습니다.

\[LyncTest.SelfHost.Corp.Microsoft.com\] 테스트 사용자 구성을 확인 합니다.

줄: 1 문자: 1

\+Test-csucwaconference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable 사용할 수 없음: (:) \[Test-csucwaconference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft.

eticTransactions

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

**테스트-CsReplica** 가 실패할 수 있는 일반적인 이유는 다음과 같습니다.

  - 복제기 에이전트 및 중앙 로깅 에이전트 서비스에 더 이상 문제가 있을 수 있습니다.

  - 필요한 포트가 Windows 방화벽에서 열리지 않을 수 있습니다.

  - 필요한 Active Directory 및 로컬 컴퓨터 보안 그룹이 존재 하지 않을 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

