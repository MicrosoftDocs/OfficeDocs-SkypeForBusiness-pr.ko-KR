---
title: 'Lync Server 2013: 데이터베이스 구성 테스트'
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
ms.openlocfilehash: 6fcf6679481d4f35a457eb72960a8ae999b004d3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-database-configuration-in-lync-server-2013"></a>Lync Server 2013에서 데이터베이스 구성 테스트

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-07-07_


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
<td><p>Lync Server Management Shell을 사용 하 여 로컬에서 실행 되는 경우 사용자는 RTCUniversalServerAdmins 보안 그룹의 구성원 이어야 하 고 SQL Server에 대 한 관리자 권한이 있어야 합니다.</p>
<p>Windows PowerShell의 원격 인스턴스를 사용 하 여 실행 하는 경우 <strong>테스트 CsDatabase</strong> cmdlet을 실행할 권한이 있는 RBAC 역할을 사용자에 게 할당 해야 합니다. 이 cmdlet을 사용할 수 있는 모든 RBAC 역할 목록을 보려면 Windows PowerShell 프롬프트에서 다음 명령을 실행 합니다.</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsDatabase&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>설명

**테스트-csdatabase** cmdlet은 하나 이상의 Lync Server 2013 데이터베이스에 대 한 연결을 확인 합니다. 실행 되 면 **테스트 CsDatabase** Cmdlet이 Lync Server 토폴로지를 읽고 관련 데이터베이스에 연결을 시도한 다음 각 시도의 성공 또는 실패를 보고 합니다. 연결을 설정할 수 있는 경우에는 cmdlet에서 데이터베이스 이름, SQL Server 버전 정보, 설치 된 미러 데이터베이스의 위치 등의 정보를 함께 보고 합니다.

</div>

<div>

## <a name="running-the-test"></a>테스트 실행

예제 1에 표시 된 명령은 중앙 관리 데이터베이스의 구성을 확인 합니다.

    Test-CsDatabase -CentralManagementDatabase

예제 2는 컴퓨터 atl-sql-001.litwareinc.com에 설치 된 모든 Lync Server 데이터베이스를 확인 합니다.

    Test-CsDatabase -ConfiguredDatabases -SqlServerFqdn "atl-sql-001.litwareinc.com"

예제 3에서는 컴퓨터 atl-sql-001.litwareinc.com에 설치 된 보관 데이터베이스에 대해서만 확인이 수행 됩니다. SqlInstanceName 매개 변수는 보관 데이터베이스가 있는 Archinst (SQL Server 인스턴스)를 지정 하기 위해 포함 되어 있습니다.

    Test-CsDatabase -DatabaseType "Archiving" -SqlServerFqdn "atl-sql-001.litwareinc.com" -SqlInstanceName "archinst"

예제 4에 나와 있는 명령은 로컬 컴퓨터에 설치 된 데이터베이스를 확인 합니다.

    Test-CsDatabase -LocalService

</div>

<div>

## <a name="determining-success-or-failure"></a>성공 또는 실패 확인

데이터베이스 연결이 올바르게 구성 되 면 다음과 비슷한 출력이 표시 되며 성공 속성은 **True**로 표시 됩니다.

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: xds

원본은

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

성공: True

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: lis

원본은

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

성공: True

데이터베이스가 올바르게 구성 되었지만 계속 사용할 수 있는 경우에는 성공 필드가 **False**로 표시 되 고 추가 경고 및 정보가 제공 됩니다.

SqlServerFqdn: atl-sql-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: xds

원본은

SQLServerVersion :

ExpectedVersion : 10.13.2

InstalledVersion :

성공: False

SqlServerFqdn: atl-cs-001.litwareinc.com

SqlInstanceName: rtc

MirrorSqlServerFqdn :

MirrorSqlInstanceName :

DatabaseName: lis

원본은

SQLServerVersion :

ExpectedVersion : 3.1.1

InstalledVersion :

성공: False

경고: 테스트 CsDatabase에 오류가 발생 했습니다. 로그 파일을 참조 하세요.

자세한 분석 및 모든 오류 (2) 및 경고 (0)가 처리 되었는지 확인

계속 하십시오.

경고: 자세한 결과는 다음에서 찾을 수 있습니다.

"C:\\AppData\\\\\\Local\\\Temp\\2\\테스트-csdatabase를 테스트 하는 사용자-b18d488a-8044-4679-bbf2-

04d593cce8e6 ".

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>테스트가 실패할 수 있는 이유

**테스트 CsDatabase에** 실패할 수 있는 몇 가지 일반적인 이유는 다음과 같습니다.

  - 잘못 된 매개 변수 값이 제공 되었습니다. 사용 하는 경우 선택적 매개 변수를 올바르게 구성 하거나 테스트에 실패 합니다. 선택적 매개 변수 없이 명령을 다시 실행 하 여 성공 여부를 확인 합니다.

  - 데이터베이스가 잘못 구성 되었거나 아직 배포 되지 않은 경우에는이 명령이 실패 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Get-CsDatabaseMirrorState](https://docs.microsoft.com/powershell/module/skype/Get-CsDatabaseMirrorState)  
[Get-CsService](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[Get-Csuserdatabasedatabasestate](https://docs.microsoft.com/powershell/module/skype/Get-CsUserDatabaseState)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

