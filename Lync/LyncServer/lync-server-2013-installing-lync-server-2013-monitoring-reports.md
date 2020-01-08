---
title: 'Lync Server 2013: Lync Server 2013 모니터링 보고서 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Lync Server 2013 Monitoring Reports
ms:assetid: 6f417569-b100-442c-ad48-fdd794626cf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204989(v=OCS.15)
ms:contentKeyID: 48184445
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5908e4eb8f18ef464a4c69cc31bffdc33a10416
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983506"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-server-2013-monitoring-reports"></a>Lync Server 2013 모니터링 보고서 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2015-02-27_

Microsoft Lync Server 2013 모니터링 보고서는 조직에서 발생 하는 통신 세션의 품질과 용량에 대 한 풍부한 정보를 제공 합니다. 하지만 모니터링 보고서는 Lync Server 2013을 설치할 때 자동으로 설치 되지 않습니다. 대신, 컴퓨터에 Lync Server가 설치 된 후에만 모니터링 보고서를 별도로 설치 해야 합니다.

<div>


> [!NOTE]  
> 모니터링 데이터베이스가 설치 되어 있는 컴퓨터에 모니터링 보고서를 설치 하는 것이 좋습니다. 이렇게 하면 보고서에 액세스 하는 사용 권한을 할당 하는 프로세스를 단순화할 수 있습니다. 모니터링 저장소를 호스팅하는 컴퓨터에 모니터링 보고서를 설치 하면 한 컴퓨터의 데이터베이스가 상호 작용 하는 데 사용 되는 권한을 구성할 필요가 없다는 의미입니다. 두 번째 컴퓨터에서 실행 중인 Reporting Services를 사용 합니다.



</div>

Lync Server 모니터링 보고서에는 회의, 피어 투 피어 IM 세션, 사용자 등록, 응답 그룹 응용 프로그램 등에 대 한 자세한 정보를 제공 하도록 디자인 된 30 개 이상의 보고서가 포함 되어 있습니다. 2013 버전의 경우 Lync Server 모니터링 보고서에는 다음과 같은 여러 가지 개선 사항이 포함 되어 있습니다.

  - **새로운 음성 음질 보고서**. 이러한 새 보고서에는 다양 한 통화 유형에 대 한 품질을 비교 하는 [Lync Server 2013의 미디어 품질 비교 보고서](lync-server-2013-media-quality-comparison-report.md)가 포함 되어 있습니다 (예: 유선 통화와 무선 통화 간). [Lync Server 2013의 컨퍼런스 참가 시간 보고서](lync-server-2013-conference-join-time-report.md)는 사용자가 회의에 참가 하는 데 필요한 시간에 대 한 정보를 제공 합니다.

  - **비디오 및 응용 프로그램 공유 세션 분석 및 문제 해결을 위한 향상 된 보고서** [Lync server 2013의 미디어 품질 요약 보고서](lync-server-2013-media-quality-summary-report.md) 에서는 비디오 및 응용 프로그램 공유 호출을 분석할 수 있는 방법을 제공 하 고 [lync Server 2013의 서버 성능 보고서](lync-server-2013-server-performance-report.md) 에는 이러한 호출을 생성 하는 서버의 성능이 자세히 설명 되어 있습니다. 또한 비디오 및 응용 프로그램 공유 메트릭은 [Lync server 2013의 피어 투 피어 세션 세부 정보 보고서](lync-server-2013-peer-to-peer-session-detail-report.md) 와 [lync Server 2013의 회의 세부 정보 보고서](lync-server-2013-conference-detail-report.md)에 의해 보고 됩니다.

  - **향상 된 보고서 성능**. 여기에는 더 빠른 응답 및 데이터 검색 시간과 더욱 빠르고 간편 하 게 보고서를 탐색할 수 있습니다.

개별 보고서에 대 한 자세한 내용은 모니터링 보고서 문서에 나와 있습니다.

<div>


> [!NOTE]  
> Lync Server 2013에 포함 된 또 다른 새 보고서 (체감 품질 통화 정보 하위 보고서)가 있습니다. 그러나이 보고서는 주로 내부용으로 사용 되며 직접 액세스할 수 없습니다.



</div>

Lync server 모니터링 보고서를 설치 하는 방법은 다음과 같은 두 가지가 있습니다. Lync Server 배포 마법사를 사용 하거나 Lync Server 2013 설치 파일에 포함 된 Windows PowerShell 스크립트를 사용할 수 있습니다. 보고서를 설치 하는 데 사용 하는 방법에 관계 없이 먼저 다음을 확인 해야 합니다.

  - 모니터링 데이터베이스의 사용자 계정에 데이터베이스 역할을 추가할 수 있는 권한이 있습니다.

  - SQL Server Reporting Services에서 콘텐츠 관리자 역할을 유지 합니다. 이 역할은 SQL Server Reporting Services에 보고서를 배포할 권한을 제공 합니다.

배포 마법사를 사용 하 여 모니터링 보고서를 설치 하려면 다음 단계를 완료 합니다.

1.  **시작**을 클릭 하 고 **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 배포 마법사**를 클릭 합니다.

2.  배포 마법사에서 모니터링 보고서 배포 마법사를 시작 하려면 **모니터링 보고서 배포** 를 클릭 합니다.

3.  모니터링 보고서 배포 마법사의 모니터링 **데이터베이스 지정** 페이지에서 모니터링 저장소를 호스트 하는 컴퓨터의 정규화 된 도메인 이름이 **모니터링 데이터베이스** 드롭다운 목록에 표시 되는지 확인 합니다. 여러 모니터링 저장소가 있는 경우 드롭다운 목록에서 적절 한 서버를 선택 해야 합니다. 올바른 SQL Server 인스턴스가 **SSRS (Sql Server Reporting Services) 인스턴스** 상자에 표시 되는지 확인 하 고 (예: **atl-sql-001.litwareinc.com/archinst**) 다음을 클릭 합니다 ****.

4.  **자격 증명 지정** 페이지의 **사용자 이름** 상자에 모니터링 보고서에 액세스할 때 사용할 계정의 도메인 이름 및 사용자 이름을 입력 합니다 (예: **\\litwareinc kenmyer**). 이 형식 (도메인\\사용자 이름)을 사용 하지 않는 경우에는 오류가 발생 합니다.
    
    **암호** 상자에 사용자 계정 암호를 입력 하 고 **다음**을 클릭 합니다. 이 계정에는 특별 한 권한이 필요 하지 않습니다. 설치가 완료 되 면 계정에 필요한 로그온 및 데이터베이스 권한이 자동으로 부여 됩니다.

5.  **읽기 전용 그룹 지정** 페이지에서 사용자 그룹 상자의 SQL Server Reporting Services에 대 한 읽기 전용 액세스 권한이 부여 되는 보안 그룹의 이름을 입력 합니다. 예를 들어 읽기 전용 관리자에 게 보고서에 대 한 액세스 권한을 부여 하려면 **RTCUniversalReadOnlyAdmins**를 입력 합니다. **다음**을 클릭 합니다.

6.  **명령 실행** 페이지에서 **마침을**클릭 합니다.

스크립트 DeployReports를 실행 하 여 Lync Server 관리 셸에서 모니터링 보고서를 설치할 수도 있습니다. ps1 이 Windows PowerShell 스크립트는 Lync Server 설치 미디어의 \\Setup\\ReportingSetup 폴더에서 찾을 수 있습니다. DeployReports를 사용 하 여 모니터링 보고서를 설치 하려면 관리 셸 프롬프트에서 다음과 같이 명령을 입력 합니다.

    C:\Program Files\Microsoft Lync Server 2013\Deployment\Setup\DeployReports.ps1 -storedUserName "litwareinc\kenmyer" -storedPassword "p@ssw0rd" -readOnlyGroupName "RTCUniversalReadOnlyAdmins" -reportServerSqlInstance "atl-sql-001.litwareinc.com" -monitoringDatabaseId "MonitoringDatabase:atl-sql-001.litwareinc.com"

앞의 명령에 사용 되는 매개 변수는 다음 표에 설명 되어 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>매개 변수 이름</th>
<th>필수</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>storedUserName</p></td>
<td><p>예</p></td>
<td><p>모니터링 저장소에 액세스 하는 데 사용 되는 사용자 계정 (domain\username 형식) 예를 들어:</p>
<pre><code>-storedUserName &quot;litwareinc\kenmyer&quot;</code></pre>
<p>이 계정에는 이전에 지정 된 SQL Server 및 SQL Server Reporting Services 권한이 있어야 하며,이는 스크립트가 실패 합니다.</p></td>
</tr>
<tr class="even">
<td><p>storedPassword</p></td>
<td><p>예</p></td>
<td><p>모니터링 저장소에 액세스 하는 데 사용 되는 사용자 계정의 암호입니다.</p></td>
</tr>
<tr class="odd">
<td><p>readOnlyGroupName</p></td>
<td><p>아니요</p></td>
<td><p>해당 구성원에 게 모니터링 보고서에 대 한 읽기 전용 액세스 권한을 부여 하는 도메인 또는 로컬 보안 그룹 지정 된 그룹이 없으면 스크립트가 실패 합니다. 나중에 이러한 사용 권한을 취소 하거나 다른 사용자 또는 다른 그룹에 게 권한을 부여 하기로 결정 한 경우에는 SQL 서비스 Reporting Services 보고서 관리자를 사용 하 여 액세스할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>reportSqlServerInstance</p></td>
<td><p>아니요</p></td>
<td><p>Reporting Services를 호스트 하는 SQL Server 인스턴스입니다. 보고서 서버의 정규화 된 도메인 이름을 사용 하 여 보고 인스턴스를 지정 해야 합니다. 예를 들어:</p>
<pre><code>-reportServerSqlInstance atl-sql-001.litwareinc.com</code></pre>
<p>이 매개 변수가 포함 되지 않은 경우 스크립트는 모니터링 데이터베이스를 호스트 하는 동일한 SQL Server 인스턴스에서 reporting services를 호스트 한다고 간주 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>monitoringDatabaseId</p></td>
<td><p>아니요</p></td>
<td><p>모니터링 데이터베이스의 서비스 Id입니다. 다음 명령을 실행 하 여 모니터링 데이터베이스의 Id를 반환할 수 있습니다.</p>
<pre><code>Get-CsService -MonitoringDatabase</code></pre></td>
</tr>
</tbody>
</table>


모니터링 보고서를 설치한 후에는 CsReportingConfiguration cmdlet을 사용 하 여 이러한 보고서에 액세스 하는 데 사용 되는 URL을 구성 해야 합니다. 이 작업은 다음 Windows PowerShell 명령을 실행 하 여 Lync Server Management 셸에서 수행할 수 있습니다. 보고 URL을 구성할 때 HTTPS 프로토콜을 사용 하는 것이 좋습니다 (필수는 아님).

    Set-CsReportingConfiguration -Identity "MonitoringDatabase:atl-sql-001.litwareinc.com" -ReportingURL "https://atl-sql-001.litwareinc.com:443/Reports_ARCHINST"

앞의 명령에서 ReportingUrl 속성은 SQL Server 2008 R2 Reporting Services에서 사용 하는 보고서 관리자 URL로 설정 해야 합니다. SQL Server Reporting Services가 설치 되어 있는 컴퓨터에서 다음 단계를 완료 하 여 보고서 관리자 URL을 확인할 수 있습니다.

1.  시작을 클릭 하 고 모든 프로그램, Microsoft SQL Server 2008 R2, 구성 도구를 차례로 클릭 한 다음 Reporting Services 구성 관리자를 클릭 합니다.

2.  Reporting Services 구성 연결 대화 상자에서 서버 이름 상자에 Reporting Services 컴퓨터의 이름이 표시 되는지 확인 합니다. 보고서 서버 인스턴스 드롭다운 목록에서 SQL Server 인스턴스를 선택한 다음 연결을 클릭 합니다.

3.  Reporting Services 구성 관리자에서 보고서 관리자 URL을 클릭 합니다. 하나 이상의 Url이 보고서 관리자 URL 창에 표시 됩니다. 이러한 Url을 보고 URL로 사용할 수 있지만, 다시 ReportingUrl HTTPS 프로토콜을 사용 하는 것이 좋습니다.

모니터링 데이터베이스에 대 한 미러 데이터베이스를 설정한 경우 모니터링 보고서를 미러 데이터베이스에도 연결 해야 합니다. 자세한 내용은 [Lync Server 2013에서 모니터링 보고서와 미러 데이터베이스 연결](lync-server-2013-associating-monitoring-reports-with-a-mirror-database.md) 문서를 참조 하세요.

</div>

<span> </span>

</div>

</div>

</div>

