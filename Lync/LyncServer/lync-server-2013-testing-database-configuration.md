---
title: 'Lync Server 2013: 데이터베이스 구성 테스트'
description: 'Lync Server 2013: 데이터베이스 구성을 테스트 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing database configuration
ms:assetid: 60f7fcd2-5efe-4791-b159-b0f9bf39a41b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727307(v=OCS.15)
ms:contentKeyID: 63969606
ms.date: 07/07/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b9f88eee99c4a2d523cc84df401dcc1d7b9fe59
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560684"
---
# <a name="testing-database-configuration-in-lync-server-2013"></a>Lync Server 2013의 데이터베이스 구성 테스트

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-07-07_


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
<td><p>Lync Server 관리 셸을 사용 하 여 로컬로 실행 하는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 하며 SQL Server에 대 한 관리자 권한이 있어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우, 사용자에 게는 <strong>CsDatabase</strong> cmdlet을 실행 하는 권한이 있는 RBAC 역할을 할당 받아야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할의 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**테스트-CsDatabase** cmdlet은 하나 이상의 Lync Server 2013 데이터베이스에 대 한 연결을 확인 합니다. 실행 하는 경우, **테스트-CsDatabase** Cmdlet은 Lync Server 토폴로지를 읽고 관련 데이터베이스에 대 한 연결을 시도한 다음 각 시도의 성공 또는 실패를 보고 합니다. 연결이 가능한 경우 이 cmdlet은 데이터베이스 이름, SQL Server 버전 정보 및 설치된 미러 데이터베이스의 위치와 같은 정보도 보고합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

예제 1에 표시된 명령은 중앙 관리 데이터베이스의 구성을 확인합니다.

    Test-CsDatabase -CentralManagementDatabase

예제 2에서는 atl-sql-001.litwareinc.com 컴퓨터에 설치 된 모든 Lync Server 데이터베이스를 확인 합니다.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

예제 3에서는 atl-sql-001.litwareinc.com 컴퓨터에 설치된 보관 데이터베이스에 대해서만 확인을 수행합니다. 보관 데이터베이스가 있는 SQL Server 인스턴스(Archinst)를 지정하기 위해 SqlInstanceName 매개 변수가 포함되었습니다.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

예제 4에 표시된 명령은 로컬 컴퓨터에 설치된 데이터베이스를 확인합니다.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

데이터베이스 연결이 올바르게 구성 되 면 다음과 비슷한 출력이 표시 되며 성공 속성은 **True**로 표시 됩니다.

변수와 sqlserverfqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: xds

아닙니다

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

성공: True

변수와 sqlserverfqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: lis

아닙니다

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

성공: True

데이터베이스가 올바르게 구성 되었지만 계속 사용할 수 있는 경우 성공 필드는 **False**로 표시 되 고 다음과 같은 추가 경고 및 정보가 제공 됩니다.

변수와 sqlserverfqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: xds

아닙니다

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

성공: False

변수와 sqlserverfqdn: atl-cs-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: lis

아닙니다

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

성공: False

경고: Test-CsDatabase에서 오류가 발생 했습니다. 자세한 내용은 로그 파일을 참조 하십시오.

자세한 분석 및 모든 오류 (2) 및 경고 (0)가 처리 되는지 확인

를 계속 합니다.

경고: 자세한 결과는 다음 위치에서 찾을 수 있습니다.

"C: \\ 사용자 \\ 테스트 \\ AppData \\ 로컬 \\ 온도 \\ 2 \\ 테스트-csdatabase-b18d488a-8044-4679-bbf2-

04d593cce8e6.html ")

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패 한 이유

**테스트 CsDatabase에** 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 사용 하는 경우 선택적 매개 변수를 올바르게 구성 해야 하며 그렇지 않으면 테스트가 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - 데이터베이스가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-csdatabasemirrorstate](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-CsUserDatabaseState](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

