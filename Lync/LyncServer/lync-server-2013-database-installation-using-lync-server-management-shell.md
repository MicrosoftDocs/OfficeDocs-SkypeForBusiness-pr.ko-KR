---
title: 'Lync Server 2013: Lync Server 관리 셸을 사용 하 여 데이터베이스 설치'
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
ms.openlocfilehash: b602e29e0f90a49a031c25d6bb919337bef87b8d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516545"
---
# <a name="database-installation-using-lync-server-management-shell-in-lync-server-2013"></a>Lync Server 2013에서 Lync Server 관리 셸을 사용 하 여 데이터베이스 설치

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-06-16_

서버 관리자와 SQL Server 관리자의 역할 및 직무를 구분하면 구현이 지연될 수 있습니다. Lync Server 2013에서는 RBAC (역할 기반 액세스 제어)를 사용 하 여 이러한 어려움을 완화 합니다. 경우에 따라 SQL Server 관리자는 RBAC 외부의 SQL Server 기반 서버에서 데이터베이스 설치를 관리해야 합니다. Lync Server 2013 관리 셸을 사용 하면 SQL Server 관리자가 올바른 데이터 및 로그 파일로 데이터베이스를 구성 하기 위해 디자인 된 Windows PowerShell cmdlet을 실행할 수 있습니다. 자세한 내용은 [Lync server 2013의 SQL Server에 대 한 배포 권한을](lync-server-2013-deployment-permissions-for-sql-server.md)참조 하십시오.

<div class=" ">


> [!IMPORTANT]  
> 다음 절차에서는 최소한 Lync Server 2013 OCSCore.msi SQL Server Native Client (sqlncli.msi) Microsoft SQL server 2012 Management Objects, Microsoft sql Server 2012 및 Microsoft SQL Server 2012 ADOMD.NET이 설치 되어 있다고 가정 합니다. OCSCore.msi는 \Setup\AMD64\Setup 디렉터리의 설치 미디어에 있습니다. 나머지 구성 요소는 \Setup\amd64.에 있습니다. 또한 Lync Server 2013에 대 한 Active Directory 준비가 성공적으로 완료 되었습니다.



</div>

**설치-CsDatabase** 는 데이터베이스를 설치 하는 데 사용 하는 Windows PowerShell cmdlet입니다. **Install-CsDatabase** cmdlet는 수많은 매개 변수를 가지며 여기에서는 그 중 몇 가지만 설명합니다. 가능한 매개 변수에 대 한 자세한 내용은 Lync Server 2013 Management Shell 설명서를 참조 하십시오.

<div class=" ">


> [!WARNING]  
> 성능 및 가능한 시간 제한 문제를 피하려면 SQL Server 기반 서버를 참조할 때 항상 FQDN(정규화된 도메인 이름)을 사용하십시오. 호스트 이름 전용 참조는 사용하지 마십시오. 예를 들어 sqlbe01.contoso.net를 사용 하 되 SQLBE01는 사용 하지 마십시오.



</div>

데이터베이스를 설치 하는 경우에는 다음 세 가지 기본 **방법을 사용 하** 여 준비 된 SQL server 기반 서버에 데이터베이스를 배치 합니다.

  - **Install-CsDatabase**를 DatabasePaths 또는 UseDefaultSqlPath 없이 실행합니다. cmdlet는 기본 제공 알고리즘을 사용하여 최적의 로그 및 데이터 파일 배치를 결정합니다. 이 알고리즘은 독립 실행형 SQL Server 구현에만 작동 합니다.

  - **Install-CsDatabase**를 DatabasePaths 매개 변수와 함께 실행합니다. DatabasePaths 매개 변수가 정의된 경우 로그 및 데이터 파일 위치를 최적화하는 기본 제공 알고리즘은 사용되지 않습니다. 이 매개 변수를 사용하면 로그 및 데이터 파일을 배포할 위치를 정의할 수 있습니다.

  - **Install-CsDatabase**를 UseDefaultSqlPaths와 함께 실행합니다. 이 옵션은 기본 제공 알고리즘을 사용하여 로그 및 데이터 파일 위치를 최적화하지 않습니다. 로그 및 데이터 파일은 SQL Server 관리자가 설정한 기본값에 따라 배포됩니다. 이러한 경로는 일반적으로 SQL Server에서 로그 및 데이터 파일을 자동으로 관리 하는 용도로 설정 되며, Lync Server 2013의 설정과는 관련이 없습니다.

  - DatabasePathMap 매개 변수를 사용 하 여 각 데이터베이스 및 해당 로그 파일에 대 한 위치를 명시적으로 지정할 수도 있습니다.

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-central-management-store"></a>Windows PowerShell cmdlet를 사용하여 SQL Server 중앙 관리 저장소를 구성하려면

1.  원하는 컴퓨터에서 SQL Server 기반 서버에 데이터베이스를 만들기 위해 관리 자격 증명을 사용하여 로그온합니다. 자세한 내용은 [Lync server 2013의 SQL Server에 대 한 배포 권한을](lync-server-2013-deployment-permissions-for-sql-server.md)참조 하십시오.

2.  Lync Server 2013 관리 셸을 엽니다. Windows PowerShell에 대 한 실행 정책을 조정 하지 않은 경우 Windows PowerShell 스크립트 실행을 허용 하도록 정책을 조정 해야 합니다. 자세한 내용은에서 "실행 정책 검사"를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=203093](https://go.microsoft.com/fwlink/p/?linkid=203093) .

3.  **설치-CsDatabase** cmdlet을 사용 하 여 중앙 관리 저장소를 설치 합니다.
    
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
    > Report 매개 변수는 선택적이지만 설치 프로세스를 문서화하는 경우에 유용합니다.

    
    </div>

4.  **설치-CsDatabase-databasepaths** 는 각각 SQL Server 데이터 및 로그 파일 배치에 정의 된 드라이브의 경로를 정의 하는 최대 6 개의 경로 매개 변수를 사용할 수 있습니다. Lync Server 2013의 데이터베이스 구성에 대 한 논리적 규칙에 따라 드라이브는 2, 4 또는 6 개 버킷으로 구문 분석 됩니다. SQL Server 구성 및 버킷 수에 따라 두 개의 경로, 즉 4 개의 경로 또는 6 개의 경로를 제공 해야 합니다.
    
    드라이브가 세 개인 경우 로그가 우선 적용되며 데이터 파일은 이후에 배포됩니다. 6 개의 드라이브로 구성 된 SQL Server 기반 서버에 대 한 예:
    ```powershell
    Install-CsDatabase -ConfiguredDatases -SqlServerFqdn sqlbe.contoso.net -DatabasePaths "D:\CSDynLogs","E:\CSRtcLogs","F:\MonCdrArcLogs","G:\MonCdrArchData","H:\AbsAppLog","I:\DynRtcAbsAppData" -Report "C:\Logs\InstallDatabases.html"
    ```
5.  데이터베이스 설치가 완료 되 면 Lync Server 2013 관리 셸을 닫거나 토폴로지 작성기에 정의 된 Lync Server 2013 구성 된 데이터베이스 설치로 진행할 수 있습니다.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-configured-databases"></a>Windows PowerShell cmdlet를 사용하여 SQL Server 토폴로지 구성 데이터베이스를 구성하려면

1.  Lync Server 2013에 대해 토폴로지 작성기 구성 데이터베이스를 설치 하려면 Lync Server 2013 관리자가 토폴로지를 게시 해야 합니다. 자세한 내용은 배포 설명서에서 [Lync Server 2013의 토폴로지 게시](lync-server-2013-publish-the-topology.md) 를 참조 하십시오.

2.  원하는 컴퓨터에서 SQL Server 기반 서버에 데이터베이스를 만들기 위해 관리 자격 증명을 사용하여 로그온합니다. [Lync server 2013의 SQL Server에 대 한 배포 권한](lync-server-2013-deployment-permissions-for-sql-server.md)항목을 참조 하십시오.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > SQL Server 기반 데이터베이스를 구성 하려면 여기에 설명 된 단계를 실행 하는 데 사용 되는 SQL Server 관리자 계정이 SQL Server를 실행 하는 서버에서 중앙 관리 서버 역할을 수행 하는 서버의 구성원 이어야 합니다. 특히 SQL Server 데이터베이스를 설치 하거나 구성 해야 하는 추가 Lync Server 2013 풀을 확인 하는 것이 중요 합니다. 예를 들어 두 번째 풀 (pool02)을 배포 하는 경우 중앙 관리 서버 역할은 pool01에서 보유 합니다. SQL Server sysadmin 그룹에는 두 SQL Server 기반 데이터베이스에 대 한 사용 권한이 있어야 합니다.

    
    </div>

3.  Lync Server 2013 관리 셸을 아직 열려 있지 않은 경우 엽니다.

4.  **설치-CsDatabase** cmdlet을 사용 하 여 토폴로지 작성기 구성 데이터베이스를 설치 합니다.
    
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
    > Report 매개 변수는 선택적이지만 설치 프로세스를 문서화하는 경우에 유용합니다.

    
    </div>

5.  데이터베이스 설치가 완료 되 면 Lync Server 2013 관리 셸을 닫습니다.

</div>

<div>

## <a name="to-use-windows-powershell-cmdlets-to-configure-the-sql-server-topology-using-the-databasepathmap-parameter"></a>Windows PowerShell cmdlet을 사용 하 여 DatabasePathMap 매개 변수를 사용 하 여 SQL Server 토폴로지를 구성 하려면 다음을 수행 합니다.

1.  Lync Server 2013에 대 한 데이터베이스를 설치 하려면 Lync Server 관리자가 경로를 만들고 미리 정의 된 규칙 집합에 따라 데이터베이스 파일 및 로그 파일을 배포 해야 합니다.

2.  원하는 컴퓨터에서 SQL Server 기반 서버에 데이터베이스를 만들기 위해 관리 자격 증명을 사용하여 로그온합니다. [Lync server 2013의 SQL Server에 대 한 배포 권한](lync-server-2013-deployment-permissions-for-sql-server.md)항목을 참조 하십시오.
    
    <div class=" ">
    

    > [!IMPORTANT]  
    > SQL Server 기반 데이터베이스를 구성 하려면 여기에 설명 된 단계를 실행 하는 데 사용 되는 SQL Server 관리자 계정이 SQL Server를 실행 하는 서버에서 중앙 관리 서버 역할을 수행 하는 서버의 구성원 이어야 합니다. 특히 SQL Server 데이터베이스를 설치 하거나 구성 해야 하는 추가 Lync Server 풀이 있는지 확인 하는 것이 중요 합니다. 예를 들어 두 번째 풀 (pool02)을 배포 하는 경우 중앙 관리 서버 역할은 pool01에서 보유 합니다. SQL Server sysadmin 그룹에는 두 SQL Server 기반 데이터베이스에 대 한 사용 권한이 있어야 합니다.

    
    </div>

3.  Lync Server Management Shell (아직 열려 있지 않은 경우)을 엽니다.

4.  DatabasePathMap 매개 변수와 PowerShell 해시 테이블을 포함 하는 **csdatabase** cmdlet을 사용 하 여 토폴로지 작성기 구성 데이터베이스를 설치 합니다.

5.  예제 코드에서 데이터베이스에 대해 정의 된 경로는 다음과 같이 – DatabasePathMap 매개 변수 및 정의 된 해시 테이블을 사용 하 여 세부적으로 결정할 수 있으며,이 예에서는 \\ 모든 데이터베이스 (.mdf) 파일에 "c: csdata"를 사용 하 고 \\ 모든 로그 파일 (.ldf)을 "c: csdata"로 지정 합니다. 설치-CsDatabase에서 필요에 따라 폴더를 만듭니다.
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
6.  데이터베이스와 로그 파일은 대상 데이터베이스 서버에서 해당 위치를 사용 하 여 명시적으로 이름이 지정 되므로 각 서비스 유형의 실제 데이터베이스 및 로그 위치에 대해 특정 위치를 정의할 수 있습니다. 다음 예에서는 각 특정 서비스 종류에 대 한 데이터베이스를 별도의 디스크에 배치 하 고 관련 로그 파일을 서로 연결 합니다. 예제:
    
      - "D: rtcdatabase"에 대 한 모든 RTC 데이터베이스 \\
    
      - "E: RTCLogs"에 대 한 모든 RTC 로그 파일 \\
    
      - 모든 응용 프로그램 저장소 데이터베이스를 "F: \\ cpsdatabases"로
    
      - 모든 응용 프로그램 저장소는 "G: \\ cpslogs"에 기록 됩니다.
    
      - 모든 응답 그룹 저장소 데이터베이스를 "H: \\ RGSDatabases"로 저장
    
      - 모든 응답 그룹 저장소가 "I: RGSLogs"에 기록 됩니다. \\
    
      - 모든 주소록 저장소 데이터베이스를 "J: \\ ABSDatabases"로
    
      - 모든 주소록 저장소 로그 파일을 "K: \\ ABSLogs"에 저장
    
      - 모든 보관 저장소 데이터베이스를 "L: \\ ArchivingDatabases"로
    
      - 모든 보관 저장소는 "M: ArchivingLogs"에 기록 됩니다. \\
    
      - "N: MonitoringDatabases"에 대 한 모든 모니터링 저장소 데이터베이스 \\
    
      - 모든 모니터링 저장소 로그 파일을 "O: \\ MonitoringLogfiles"로
    
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
    
    – DatabasePathMap 매개 변수를 사용 하면 SQL Server 성능 및 배치 요구 사항에 가장 적합 한 솔루션을 제공 하는 논리적 드라이브 문자 매핑 조합을 정의할 수 있습니다.

**Databasepathmap** 메서드를 사용 하 여 데이터베이스 데이터 파일 및 로그 파일을 구성 하는 경우에는 토폴로지 작성기를 사용할 때 일반 프로세스를 약간 변경 해야 합니다. 일반적으로 토폴로지 선택 사항을 정의 하 고, 토폴로지를 게시 하 고, 데이터베이스 선택을 배포 하도록 선택 합니다.

**Databasepathmap** 을 사용한 경우 토폴로지 작성기 프로세스의 세 번째 부분을 이미 완료 한 것입니다. 토폴로지 작성기를 실행 하기 전에 전체적으로 데이터베이스 서버를 구성 하는 경우에도 모든 서버 역할 및 옵션을 정의 하 되, 데이터베이스 만들기 옵션은 선택 취소 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

