---
title: 'Lync Server 2013: 복제본 서비스 테스트'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing the replica service
ms:assetid: 4ff2cc91-0036-4c5a-9792-7bf43d8ce18d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727303(v=OCS.15)
ms:contentKeyID: 63969600
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b1a9dca37c30231a2f0f297e94321dfc12405d0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-replica-service-in-lync-server-2013"></a>Lync Server 2013에서 복제본 서비스 테스트

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
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 사용자에 게는 <strong>테스트 CsReplica</strong> cmdlet을 실행할 권한이 있는 RBAC 역할을 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsReplica&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**테스트-csreplica** Cmdlet는 Lync Server 2013 복제본 서비스가 로컬 컴퓨터에서 실행 중인지 확인 합니다. **테스트-CsReplica** cmdlet은 다음과 같은 작업을 수행 합니다.

  - 복제기 에이전트 및 중앙 로깅 에이전트 서비스의 상태 확인

  - Windows 방화벽에서 필요한 포트가 열려 있는지 확인

  - 필요한 Active Directory 및 로컬 컴퓨터 보안 그룹이 존재 하는지 확인 합니다.

이 cmdlet은 로컬로 실행 되어야 합니다. 즉, 복제본 서비스를 실행 중인 컴퓨터에서 실행 해야 합니다. 원격 서버에 대해 **테스트 CsReplica** cmdlet을 실행 하는 옵션은 없습니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

예제 1에 표시 된 명령은 로컬 컴퓨터에서 Lync Server 2013 복제 서비스를 테스트 합니다. 이 예제에서 Verbose 매개 변수는 테스트에 대 한 정보 (예: 테스트에 대 한 성공 또는 실패)와 테스트에서 생성 된 보고서의 위치를 포함 하 여 화면에 표시 되도록 하는 데 사용 됩니다.

    Test-CsReplica -Verbose

예제 2는 예제 1에 표시 된 명령의 변형입니다. 이 경우 보고서 매개 변수는 테스트에서 생성 된 보고서의 폴더 경로와 이름을 지정 하는 데 포함 됩니다. 보고서 경로를 지정 하지 않으면 다음과 같은 자동 생성 이름이 보고서에 제공 됩니다.

C:\\사용자\\관리자. Litwareinc\\AppData\\Local\\\temp\\1\\테스트-Cs-복제본-3db40ee0-4b5d-4f58-8d3d-b1e61253129e .html

    Test-CsReplica -Verbose -Report C:\Logs\ReplicaTest.html

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

여기에 섹션 본문을 삽입 합니다.

VERBOSE: 새 로그 파일 만들기 "C:\\사용자\\테스트\\AppData\\로컬\\임시\\테스트-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c".

VERBOSE: 새 로그 파일 만들기 "C:\\사용자\\테스트\\AppData\\로컬\\임시\\테스트-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c".

자세한 정보: "테스트-CsReplica" 처리가 성공적으로 완료 되었습니다.

자세한 정보: 자세한 결과는 "\\C: 사용자\\테스트\\AppData\\로컬\\임시\\테스트-csreplica-3cb066b3-dd23-411a-8932-99f01c0f940c" .xml "에 나와 있습니다.

VERBOSE: 새 로그 파일 만들기

"C:\\사용자\\테스트\\AppData\\로컬\\임시\\2\\테스트-csreplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083 ".

VERBOSE: 새 로그 파일 만들기

"C:\\사용자\\테스트\\AppData\\로컬\\임시\\2\\테스트-csreplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083 ".

경고: 테스트-CsReplica이 실패 했습니다.

경고: 자세한 결과는 다음에서 찾을 수 있습니다.

"C:\\사용자\\테스트\\AppData\\로컬\\임시\\2\\테스트-csreplica-29fddb35-f56e-4e3c-8f4c-e

d3bd0e4a083 ".

테스트-CsReplica: 명령 실행 실패: 요청 된 레지스트리 액세스 권한 없음

허용.

줄: 1 char: 1

\+테스트-CsReplica-세부 정보 표시

\+ ~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: InvalidOperation: (:) \[테스트-csreplica\], Security

발생

\+FullyQualifiedErrorId: ProcessingFailed, Microsoft. .Deploy

주석. TestReplicaCmdlet

PS C:\\사용자\\테스트\>

PS C:\\\\\> CsUcwaConference-Targetfqdn "LSelfHost ctest.. M t e

icrosoft.com "

경고: 정규화 된 정식 #b0에 대 한 등록자 포트 번호를 읽지 못했습니다.

도메인 이름 (FQDN). 기본 등록자 포트 번호를 사용 합니다. 발생

InvalidOperationException: 토폴로지에서 일치 하는 클러스터를 찾을 수 없습니다.

배포자

SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

CsUcwaConference: 지정 된 테스트 사용자가 없습니다.

\[LyncTest.SelfHost.Corp.Microsoft.com\]. 테스트 사용자 구성을 확인 합니다.

줄: 1 char: 1

\+테스트-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable 사용할 수 없음: (:) \[테스트-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. m m/. 신시사이저

eticTransactions

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

**테스트-CsReplica** 가 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 복제기 에이전트 및 중앙 로깅 에이전트 서비스에 더 많은 문제가 있을 수 있습니다.

  - 필요한 포트가 Windows 방화벽에서 열리지 않을 수 있음

  - 필요한 Active Directory 및 로컬 컴퓨터 보안 그룹이 없을 수 있습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

