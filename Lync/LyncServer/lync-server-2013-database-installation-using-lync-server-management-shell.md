---
title: 'Lync Server 2013: Lync Server 관리 셸을 사용하여 데이터베이스 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database installation using Lync Server Management Shell
ms:assetid: c90a6449-4dd5-4b18-b21c-ea2c2a64dc3c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398832(v=OCS.15)
ms:contentKeyID: 48185401
ms.date: 06/16/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c617d323eb00476b53677b670c8cc6db0b8d05c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Lync Server 2013에서 Lync Server 관리 셸을 사용하여 데이터베이스 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-06-16_

서버 관리자와 SQL Server 관리자 간에 역할과 책임을 분리 하면 구현 지연이 발생할 수 있습니다. Lync Server 2013는 RBAC (역할 기반 액세스 제어)를 사용 하 여 이러한 문제를 완화 합니다. 어떤 경우에는 SQL Server 관리자가 RBAC 외부의 SQL Server 기반 서버에서 데이터베이스의 설치를 관리 해야 합니다. Lync Server 2013 관리 셸은 SQL Server 관리자가 올바른 데이터 및 로그 파일을 사용 하 여 데이터베이스를 구성 하도록 디자인 된 Windows PowerShell cmdlet을 실행할 수 있는 방법을 제공 합니다. 자세한 내용은 [Lync server 2013에서 SQL Server에 대 한 배포 권한을](lync-server-2013-deployment-permissions-for-sql-server.md)참조 하세요.

<div class=" ">


> [!IMPORTANT]  
> 다음 절차에서는 최소한 Lync Server 2013 OCSCore, SQL Server Native Client (sqlncli) Microsoft sql server 2012 관리 개체, microsoft sql Server 2012 및 Microsoft SQL Server 2012 ADOMD.NET에 대 한 CLR 유형이 설치 되어 있다고 가정 합니다. OCSCore는 \Setup\AMD64\Setup 디렉터리의 설치 미디어에 있습니다. 나머지 구성 요소는 \Setup\amd64.에 있습니다. 또한 Lync Server 2013에 대 한 Active Directory 준비가 성공적으로 완료 되었습니다.



</div>

**설치-CsDatabase** 는 데이터베이스를 설치 하는 데 사용 하는 Windows PowerShell cmdlet입니다. **설치-CsDatabase** cmdlet에는 많은 매개 변수가 있지만 여기에서 설명 하는 값 중 몇 가지만 나와 있습니다. 사용할 수 있는 매개 변수에 대 한 자세한 내용은 Lync Server 2013 관리 셸 설명서를 참조 하세요.

<div class=" ">


> [!WARNING]  
> 성능 및 가능성 있는 시간 문제를 방지 하려면 SQL Server 기반 서버를 언급할 때 항상 Fqdn (정규화 된 도메인 이름)을 사용 합니다. 호스트 이름 전용 참조는 사용 하지 마세요. 예를 들어 sqlbe01.contoso.net를 사용 하 되 SQLBE01을 사용 하지 마세요.



</div>

데이터베이스를 설치 하는 경우 **설치-CsDatabase** 는 다음 세 가지 기본 메서드를 사용 하 여 데이터베이스를 준비 된 SQL server 기반 서버에 배치 합니다.

  - DatabasePaths 또는 UseDefaultSqlPath 없이 **설치-CsDatabase** 를 실행 합니다. Cmdlet은 기본 제공 알고리즘을 사용 하 여 로그 및 데이터 파일에 가장 적합 한 배치를 결정 합니다. 이 알고리즘은 독립 실행형 SQL Server 구현에 대해서만 작동 합니다.

  - DatabasePaths 매개 변수를 사용 하 여 **설치-CsDatabase** 를 실행 합니다. DatabasePaths 매개 변수가 정의 되어 있는 경우 로그 및 데이터 파일 위치를 최적화 하는 기본 제공 알고리즘이 사용 되지 않습니다. 이 매개 변수를 사용 하면 로그 및 데이터 파일을 배포할 위치를 정의할 수 있습니다.

  - UseDefaultSqlPaths를 사용 하 여 **설치 CsDatabase** 를 실행 합니다. 이 옵션은 기본 제공 알고리즘을 사용 하 여 로그 및 데이터 파일 위치를 최적화 하지 않습니다. 로그 및 데이터 파일은 SQL Server 관리자가 설정한 기본값에 따라 배포 됩니다. 이러한 경로는 일반적으로 SQL Server에서 로그 및 데이터 파일의 자동 관리를 위해 설정 되며, Lync Server 2013의 설정에는 연결 되지 않습니다.

  - DatabasePathMap 매개 변수를 사용 하 여 각 데이터베이스 및 해당 로그 파일의 위치를 명시적으로 지정할 수도 있습니다.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Windows PowerShell cmdlet을 사용 하 여 SQL Server 중앙 관리 저장소를 구성 하려면

1.  모든 컴퓨터에서 SQL Server 기반 서버에 데이터베이스를 만들기 위해 관리 자격 증명을 사용 하 여 로그온 합니다. 자세한 내용은 [Lync server 2013에서 SQL Server에 대 한 배포 권한을](lync-server-2013-deployment-permissions-for-sql-server.md)참조 하세요.

2.  Lync Server 2013 관리 셸을 엽니다. Windows PowerShell에 대 한 실행 정책을 조정 하지 않은 경우 Windows PowerShell 스크립트 실행을 허용 하도록 정책을 조정 해야 합니다. 자세한 내용은에서 [http://go.microsoft.com/fwlink/p/?linkId=203093](http://go.microsoft.com/fwlink/p/?linkid=203093)"실행 정책 살펴보기"를 참조 하세요.

3.  중앙 관리 저장소를 설치 하려면 **설치-CsDatabase** cmdlet을 사용 합니다.
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn <fully qualified domain name of SQL Server> 
        -SqlInstanceName <named instance> -DatabasePaths <logfile path>,<database file path> 
        -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -CentralManagementDatabase -SqlServerFqdn sqlbe.contoso.net -SqlInstanceName rtc -DatabasePaths "C:\CSDB-Logs","C:\CSDB-CMS" -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Report 매개 변수는 선택 사항 이지만 설치 프로세스를 문서화 하는 경우에 유용 합니다.

    
    </div>

4.  **설치-CsDatabase – databasepaths** 는 SQL Server 데이터 및 로그 파일 배치에 정의 된 대로 드라이브의 경로를 정의 하는 최대 6 개의 경로 매개 변수를 사용할 수 있습니다. Lync Server 2013의 데이터베이스 구성에 대 한 논리 규칙에 따라 드라이브가 2, 4 또는 6의 버킷으로 구문 분석 됩니다. SQL Server 구성 및 버킷 수에 따라 두 개의 경로, 4 개 경로 또는 6 개의 경로를 제공 합니다.
    
    드라이브가 세 개 있는 경우 로그는 우선 순위를 사용 하 고 데이터 파일은 다음에 배포 됩니다. 6 개의 드라이브로 구성 된 SQL Server 기반 서버의 예:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  데이터베이스 설치가 완료 되 면 Lync Server 2013 관리 셸을 닫거나 토폴로지 작성기에 정의 된 Lync Server 2013에서 구성한 데이터베이스의 설치로 진행할 수 있습니다.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Windows PowerShell cmdlet을 사용 하 여 SQL Server 토폴로지 구성 된 데이터베이스를 구성 하려면

1.  Lync Server 2013에 대 한 토폴로지 작성기 구성 데이터베이스를 설치 하려면 Lync Server 2013 관리자가 토폴로지를 게시 해야 합니다. 자세한 내용은 배포 설명서의 [Lync Server 2013에서 토폴로지 게시](lync-server-2013-publish-the-topology.md) 를 참조 하세요.

2.  모든 컴퓨터에서 SQL Server 기반 서버에 데이터베이스를 만들기 위해 관리 자격 증명을 사용 하 여 로그온 합니다. [Lync server 2013에서 SQL Server에 대 한 배포 권한](lync-server-2013-deployment-permissions-for-sql-server.md)항목을 참조 하세요.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > SQL Server 기반 데이터베이스를 구성 하려면 여기에 설명 된 단계를 실행 하는 데 사용 되는 SQL Server 관리자 계정이 SQL Server를 실행 하는 서버에 대 한 sysadmins 그룹 (또는 동등한)의 구성원 이기도 하 고 중앙 관리를 보유 하 고 있는지 확인 합니다. 서버 역할. 이는 SQL Server 데이터베이스를 설치 또는 구성 해야 하는 추가 Lync Server 2013 풀을 확인 하는 데 특히 중요 합니다. 예를 들어 두 번째 풀 (pool02)을 배포 하는 경우 중앙 관리 서버 역할은 pool01에서 보유 합니다. SQL Server sysadmin 그룹 (또는 동등한)은 SQL Server 기반 데이터베이스 모두에 대 한 사용 권한이 있어야 합니다.

    
    </div>

3.  Lync Server 2013 관리 셸이 아직 열려 있지 않으면 엽니다.

4.  **설치-CsDatabase** cmdlet을 사용 하 여 토폴로지 작성기가 구성 된 데이터베이스를 설치 합니다.
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <fully qualified domain name of SQL Server> 
         -DatabasePaths <logfile path>,<database file path> -Report <path to report file>
       ```
    
       ```powershell
        Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe.contoso.net 
        -Report "C:\Logs\InstallDatabases.html"
       ```
    
    <div class=" ">
    

    > [!TIP]  
    > Report 매개 변수는 선택 사항 이지만 설치 프로세스를 문서화 하는 경우에 유용 합니다.

    
    </div>

5.  데이터베이스 설치가 완료 되 면 Lync Server 2013 관리 셸을 닫습니다.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Windows PowerShell cmdlet을 사용 하 여 DatabasePathMap 매개 변수를 사용 하 여 SQL Server 토폴로지를 구성 하려면

1.  Lync server 2013의 데이터베이스를 설치 하려면 Lync Server 관리자가 경로를 만들고 미리 정의 된 규칙 집합에 따라 데이터베이스 파일 및 로그 파일을 배포 해야 합니다.

2.  모든 컴퓨터에서 SQL Server 기반 서버에 데이터베이스를 만들기 위해 관리 자격 증명을 사용 하 여 로그온 합니다. [Lync server 2013에서 SQL Server에 대 한 배포 권한](lync-server-2013-deployment-permissions-for-sql-server.md)항목을 참조 하세요.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > SQL Server 기반 데이터베이스를 구성 하려면 여기에 설명 된 단계를 실행 하는 데 사용 되는 SQL Server 관리자 계정이 SQL Server를 실행 하는 서버에 대 한 sysadmins 그룹 (또는 동등한)의 구성원 이기도 하 고 중앙 관리를 보유 하 고 있는지 확인 합니다. 서버 역할. 이는 SQL Server 데이터베이스를 설치 또는 구성 해야 하는 추가 Lync Server 풀을 확인 하는 데 특히 중요 합니다. 예를 들어 두 번째 풀 (pool02)을 배포 하는 경우 중앙 관리 서버 역할은 pool01에서 보유 합니다. SQL Server sysadmin 그룹 (또는 동등한)은 SQL Server 기반 데이터베이스 모두에 대 한 사용 권한이 있어야 합니다.

    
    </div>

3.  Lync Server Management Shell (아직 열려 있지 않은 경우)을 엽니다.

4.  DatabasePathMap 매개 변수와 PowerShell 해시 테이블과 함께 **설치-csdatabase** cmdlet을 사용 하 여 토폴로지 작성기가 구성 된 데이터베이스를 설치 합니다.

5.  예제 코드에서는 다음과 같이 – DatabasePathMap 매개 변수 및 정의 된 해시 테이블을 사용 하 여 세부적인 방식으로 데이터베이스에 정의 된 경로를 결정할 수 있습니다 (예제에서는 모든 데이터베이스 (.mdf)\\파일에 "c: csdata" 사용) 및 모든 로그 (.ldf)\\파일에 대 한 "c: csdata 로그"가 있습니다. 설치-CsDatabase에 의해 필요에 따라 폴더가 생성 됩니다.
    ```powershell
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="C:\CsData";"BackendStore:BlobStore:LogPath"="C:\CsLogFiles"
    "BackendStore:RtcSharedDatabase:DbPath"="C:\CsData";"BackendStore:RtcSharedDatabase:LogPath"="C:\CsLogFiles"
    "ABSStore:AbsDatabase:DbPath"="C:\CsData";"ABSStore:AbsDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsConfigDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsConfigDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:RgsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:RgsDynDatabase:LogPath"="C:\CsLogFiles"
    "ApplicationStore:CpsDynDatabase:DbPath"="C:\CsData";"ApplicationStore:CpsDynDatabase:LogPath"="C:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="C:\CsData";"ArchivingStore:ArchivingDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:MonitoringDatabase:DbPath"="C:\CsData";"MonitoringStore:MonitoringDatabase:LogPath"="C:\CsLogFiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="C:\CsData";"MonitoringStore:QoEMetricsDatabase:LogPath"="C:\CsLogFiles"
    }
    Install-CsDatabase -ConfigureDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
6.  데이터베이스 및 로그 파일은 대상 데이터베이스 서버의 위치를 사용 하 여 명시적으로 명명 되므로 각 서비스 유형의 실제 데이터베이스 및 로그 위치에 대해 특정 위치를 정의할 수 있습니다. 다음 예에서는 각 특정 서비스 종류에 대 한 데이터베이스를 별도의 디스크에 배치 하 고 연결 된 로그 파일을 다른 컴퓨터에 저장 합니다. 예를 들면 다음과 같습니다.
    
      - "D:\\rtcdatabase"에 대 한 모든 RTC 데이터베이스
    
      - 모든 RTC 로그 파일을 "E:\\RTCLogs"에 추가
    
      - 모든 응용 프로그램 저장소 데이터베이스를 "F\\: cpsdatabases"로
    
      - 모든 응용 프로그램 스토어는 "G:\\cpslogs"로 기록 됩니다.
    
      - "H:\\RGSDatabases"에 대 한 모든 응답 그룹 저장소 데이터베이스
    
      - 모든 응답 그룹 저장소가 "I: RGSLogs"\\에 기록 됩니다.
    
      - 모든 주소록이 "J: ABSDatabases"로 데이터베이스\\를 저장 합니다.
    
      - 모든 주소록 저장소 로그 파일을 "K:\\ABSLogs"로
    
      - 모든 보관 저장소 데이터베이스를 "L:\\ArchivingDatabases"로
    
      - 모든 보관 저장소는 "M: ArchivingLogs\\"에 기록 됩니다.
    
      - "N:\\MonitoringDatabases"에 대 한 모든 모니터링 저장소 데이터베이스
    
      - 모든 모니터링 저장소 로그 파일을 "O:\\MonitoringLogfiles"로
    
    <!-- end list -->
    
    ```powershell    
    $pathmap = @{
    "BackendStore:BlobStore:DbPath"="D:\RTCDatabase";"BackendStore:BlobStore:LogPath"="E:\RTCLogs"
    "BackendStore:RtcSharedDatabase:DbPath"="D:\RTCDatabase";"BackendStore:RtcSharedDatabase:LogPath"="E:\RTCLogs"
    "ABSStore:AbsDatabase:DbPath"="J:\ABSDatabases";"ABSStore:AbsDatabase:LogPath"="K:\ABSLogs"
    "ApplicationStore:RgsConfigDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsConfigDatabase:LogPath"="G:\CPSLogs"
    "ApplicationStore:RgsDynDatabase:DbPath"="H:\RGSDatabases";"ApplicationStore:RgsDynDatabase:LogPath"="I:\RGSLogs"
    "ApplicationStore:CpsDynDatabase:DbPath"="F:\CPSDatabases";"ApplicationStore:CpsDynDatabase:LogPath"="G:\CsLogFiles"
    "ArchivingStore:ArchivingDatabase:DbPath"="M:\ArchivingLogs";"ArchivingStore:ArchivingDatabase:LogPath"="N:\MonitoringDatabases"
    "MonitoringStore:MonitoringDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:MonitoringDatabase:LogPath"="O:\MonitoringLogfiles"
    "MonitoringStore:QoEMetricsDatabase:DbPath"="N:\MonitoringDatabases";"MonitoringStore:QoEMetricsDatabase:LogPath"="O:\MonitoringLogfiles"
    }
    
    Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn sqlbe01.contoso.net -DatabasePathMap $pathmap
    ```
    
    – DatabasePathMap 매개 변수를 사용 하 여 SQL Server 성능 및 배치 요구 사항에 가장 적합 한 솔루션을 제공 하는 논리 드라이브 문자 매핑 조합을 정의할 수 있습니다.

**Databasepathmap** 메서드를 사용 하 여 데이터베이스 데이터 파일 및 로그 파일을 구성 하는 경우 토폴로지 작성기를 사용 하는 경우 일반적인 프로세스를 약간 변경 해야 합니다. 일반적으로 토폴로지 선택 항목을 정의 하 고 토폴로지를 게시 한 다음 데이터베이스 선택 영역 배포를 선택 합니다.

**Databasepathmap** 을 사용한 경우 토폴로지 작성기 프로세스의 세 번째 부분이 이미 수행 되었습니다. 토폴로지 작성기를 실행 하기 전에 완벽 하 게 구성 된 데이터베이스 서버를 보유 하 고 있는 경우에도 모든 서버 역할 및 옵션을 정의할 수 있지만, 데이터베이스 만들기 옵션의 선택을 취소 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

