---
title: 비즈니스용 Skype SQL 백 엔드 서버 고가용성을 위한 미러링 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: SQL 미러링을 배포할 수 있으려면 서버에서 최소한 SQL Server 2008 R2를 실행해야 합니다. 이 버전은 기본, 미러 및 미러링 모니터 서버 등 모든 관련 서버에서 실행해야 합니다. 자세한 내용은 SQL Server 2008 서비스 팩 1용 누적 업데이트 패키지 9를 참조합니다.
ms.openlocfilehash: 8a546f65d8ad5c701eea20fb2c9c3bf0e026ff1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830558"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>비즈니스용 Skype SQL 백 엔드 서버 고가용성을 위한 미러링 배포


SQL 미러링을 배포할 수 있으려면 서버에서 최소한 SQL Server 2008 R2를 실행해야 합니다. 이 버전은 기본, 미러 및 미러링 모니터 서버 등 모든 관련 서버에서 실행해야 합니다. 자세한 내용은 SQL Server [2008 서비스 팩 1용 누적 업데이트 패키지 9를 참조합니다.](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)

일반적으로 미러링 모니터 서버가 포함된 두 개의 백 엔드 서버 사이에 SQL 미러링을 설정하려면 다음이 필요합니다.

- 기본 서버의 서버 버전은 SQL Server 미러링을 SQL 합니다.

- 기본, 미러, 미러링 모니터 서버(배포된 경우)는 모두 SQL Server 버전이 동일해야 합니다.

- 기본 및 미러는 SQL Server의 에디션이 동일해야 합니다. 미러링 모니터 서버는 에디션이 다를 수 있습니다.

미러링 SQL 지원되는 버전과 SQL 모범 사례에 대한 자세한 내용은 데이터베이스 미러링 지원 [서버(Database Mirroring Witness)를 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=247345)

토폴로지 작성기에서 미러링을 배포할 SQL 있습니다. 토폴로지 작성기에서 데이터베이스를 미러링할 옵션을 선택하고, 토폴로지 작성기에서 토폴로지 게시 시 미러링을 설정(원하는 경우 미러링 서버 설정 포함)을 설치합니다. 미러를 설정하거나 제거하는 것과 동시에 미러링 모니터 서버도 설정하거나 제거합니다. 미러링 모니터 서버만 배포하거나 제거할 수 있는 별도의 명령은 없습니다.

서버 미러링을 구성하려면 먼저 SQL 데이터베이스 권한을 올바르게 설정해야 합니다. 자세한 내용은 데이터베이스 미러링 또는 AlwaysOn 가용성 그룹에 대한 로그인 계정 [설정(SQL Server)을 참조합니다.](https://go.microsoft.com/fwlink/p/?LinkId=268454)

SQL 미러링을 사용할 경우 데이터베이스 복구 모드는 항상 **전체** 로 설정되므로 트랜잭션 로그 크기를 자세히 모니터링하고 백 엔드 서버의 디스크 공간이 부족해지지 않도록 정기적으로 트랜잭션 로그를 백업해야 합니다. 트랜잭션 로그 백업의 빈도는 로그 증가 속도에 따라 달라지며, 이는 다시 프런트 엔드 풀에서의 사용자 활동으로 인해 발생하는 데이터베이스 트랜잭션에 따라 달라집니다. 그에 따라 계획을 수립할 수 있도록 배포 작업 부하에 대해 트랜잭션 로그 증가가 예상되는 정도를 결정하는 것이 좋습니다. 다음 문서에서는 SQL 백업 및 로그 관리에 대한 추가 정보를 제공합니다.

- [데이터베이스 복구 모델](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [백업 개요](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [백업 트랜잭션 로그](https://go.microsoft.com/fwlink/p/?LinkId=268452)

SQL 미러링을 사용하면 풀을 만들 때 또는 풀이 이미 만들어진 후에 미러링에 대한 토폴로지를 구성할 수 있습니다.

> [!IMPORTANT]
> 토폴로지 작성기 또는 cmdlet을 사용하여 SQL 미러링을 설정 및 제거하는 것은 기본 서버, 미러 및 미러링 서버(필요한 경우)가 모두 동일한 도메인에 속하는 경우만 지원됩니다. 다른 도메인에 있는 서버 간에 SQL 미러링을 설정하려는 경우에는 SQL Server 설명서를 참조하십시오.

> [!IMPORTANT]
> 백 엔드 데이터베이스 미러링 관계를 변경할 때마다 풀에서 모든 프런트 엔드 서버를 다시 시작해야 합니다. > 미러링 변경(예: 미러 위치 변경)의 경우 토폴로지 작성기에서 다음 세 단계를 수행해야 합니다.

1. 이전 미러 서버에서 미러링을 제거합니다.

2. 새 미러 서버에 미러링을 추가합니다.

3. 토폴로지를 게시합니다.

> [!NOTE]
> 미러 파일을 기록하려면 파일 공유를 만들어야 합니다. 에이전트 및 SQL Server SQL 실행 중인 서비스에는 읽기/쓰기 액세스 권한이 필요합니다. SQL Server 서비스가 네트워크 서비스의 컨텍스트에서 실행되는 경우 공유 권한에<및 Mirror SQL 서버의 \<Domain\> \\ SQLSERVERNAME $을 추가할 \> 수 있습니다. $는 컴퓨터 계정으로 식별하는 데 중요합니다.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>토폴로지 SQL 풀을 만드는 동안 미러링을 구성합니다.

1. **SQL 저장소 정의** 페이지에서 **SQL 저장소** 상자 옆에 있는 **다음** 을 클릭합니다.

2. **새 SQL 저장소 정의** 페이지에서 기본 저장소를 지정하고 **이 SQL 인스턴스가 미러링 관계에 있음** 을 선택하고, SQL 미러링 포트 번호(기본값 5022)를 지정한 후 **확인** 을 클릭합니다.

3. 다시 **SQL 저장소 정의** 페이지에서 **SQL 저장소 미러링 사용** 을 선택합니다.

4. **새 SQL 저장소 정의** 페이지에서 미러로 사용할 SQL 저장소를 지정합니다. **이 SQL 인스턴스가 미러링 관계에 있음** 을 선택하고 포트 번호(기본값 5022)를 지정한 후 **확인** 을 클릭합니다.

5. 이 미러에 대해 미러링 모니터 서버를 사용하려는 경우 다음을 수행합니다.

    a. **SQL 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용** 을 선택합니다.

    b. **SQL 저장소 정의** 페이지에서 **SQL 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용** 을 선택하고 미러링 모니터 서버로 사용할 SQL 저장소를 지정합니다.

    c. 포트 번호(기본값 7022)를 지정하고 **확인** 을 클릭합니다.

6. 프런트 엔드 풀 및 토폴로지의 다른 모든 역할 정의를 완료한 후 토폴로지 작성기에서 토폴로지 게시를 합니다. 토폴로지가 게시되면 중앙 관리 저장소를 호스팅하는 프런트 엔드 풀에 SQL 미러링을 사용하도록 설정한 경우 기본 및 미러 저장소 데이터베이스를 SQL 옵션이 표시됩니다.

    **설정** 을 클릭하고 미러링 백업에 대한 파일 공유로 사용할 경로를 입력합니다.

    **확인** 을 클릭한 후 **다음** 을 클릭하여 데이터베이스를 만들고 토폴로지를 게시합니다. 미러링 및 미러링 모니터 서버(지정된 경우)가 배포됩니다.

토폴로지 작성기에서 기존 풀의 속성을 편집하여 기존 미러링을 사용하도록 SQL 있습니다.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>토폴로지 SQL 기존 프런트 엔드 풀에 미러링을 추가합니다.

1. 토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 클릭합니다.**

2. **SQL 저장소 미러링 사용** 을 선택한 후 **미러링 SQL 저장소** 옆에서 **새로 만들기** 를 클릭합니다.

3. 미러로 사용하려는 SQL 저장소를 지정합니다.

4. **이 SQL 인스턴스가 미러링 관계에 있음** 을 선택하고 SQL 미러링 포트 번호(기본 포트는 5022)를 지정한 후 **확인** 을 클릭합니다.

5. 미러링 모니터 서버를 구성하려면 **SQL 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용** 을 선택하고 **새로 만들기** 를 클릭합니다.

6. 미러링 모니터 서버로 사용하려는 SQL 저장소를 지정합니다.

7. **이 SQL 인스턴스가 미러링 관계에 있음** 을 선택하고 SQL 미러링 포트 번호(기본 포트는 7022)를 지정한 후 **확인** 을 클릭합니다.

8. **확인** 을 클릭합니다.

9. 토폴로지를 게시합니다. 이렇게 하면 데이터베이스를 설치하라는 메시지가 표시됩니다.

    토폴로지 게시 프로세스 중에 파일 공유 경로를 정의할지 묻는 요청이 표시됩니다. 미러링에 SQL 서버에 미러를 설정하려면 이 파일 공유에 대한 읽기/쓰기 권한이 있어야 합니다.

그런 후 다음 절차로 이동하려면 먼저 데이터베이스를 설치해야 합니다.

SQL 미러링을 설정할 때는 다음 사항에 주의해야 합니다.

- 미러링 끝점이 존재하는 경우 해당 위치에 정의된 포트를 사용하여 다시 사용되며, 사용자가 토폴로지에 지정한 포트는 무시합니다.

- 다른 SQL 인스턴스에 대한 포트를 포함하여 동일 서버의 다른 응용 프로그램에 이미 할당된 포트는 설치된 현재 SQL 인스턴스에 대해 사용하지 않아야 합니다. 이러한 제한은 동일한 서버에 SQL 인스턴스를 두 개 이상 설치한 경우 이러한 인스턴스가 미러링에 대해 동일한 포트를 사용하지 않아야 함을 의미합니다. 자세한 내용은 다음 문서를 참조하십시오.

  - [서버 네트워크 주소 지정(데이터베이스 미러링)](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [데이터베이스 미러링 끝점(SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>비즈니스용 Skype 서버 2015 관리 셸 cmdlet을 사용하여 미러링 SQL 설정

미러링을 설정하는 가장 쉬운 방법은 토폴로지 작성기 사용이지만 cmdlet을 사용하여 설정할 수 있습니다.

1. 비즈니스용 Skype 서버 2015 관리 셸 창을 열고 다음 cmdlet을 실행합니다.

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    예:

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    다음과 같이 표시됩니다.

   <pre>
   Database Name:rtcxds
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcxds.mdf
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcxds.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rtcshared
        Data File:D:\CsData\BackendStore\rtc\DbPath\rtcshared.mdf
         Log File:D:\CsData\BackendStore\rtc\LogPath\rtcshared.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rtcab
        Data File:D:\CsData\ABSStore\rtc\DbPath\rtcab.mdf
         Log File:D:\CsData\ABSStore\rtc\LogPath\rtcab.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rgsconfig
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsconfig.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsconfig.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:rgsdyn
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\rgsdyn.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\rgsdyn.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:cpsdyn
        Data File:D:\CsData\ApplicationStore\rtc\DbPath\cpsdyn.mdf
         Log File:D:\CsData\ApplicationStore\rtc\LogPath\cpsdyn.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:xds
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\xds.mdf
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\xds.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
    Database Name:lis
        Data File:D:\CsData\CentralMgmtStore\rtc\DbPath\lis.mdf
         Log File:D:\CsData\CentralMgmtStore\rtc\LogPath\lis.ldf
      Primary SQL: e04-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\e04-ocs$
       Mirror SQL: K16-ocs.los_a.lsipt.local\rtc
          Account: LOS_A\K16-ocs$
     Witness SQL : AB14-lct.los_a.lsipt.local\rtc
          Account: LOS_A\AB14-lct$
   [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):
   </pre>

2. 다음을 확인합니다.

    - Windows 방화벽이 기본 SQL Server e04-ocs.los_a.lsipt.local\rtc에서 사용하도록 설정된 경우 방화벽을 통해 포트 5022에 액세스할 수 있어야 합니다.

    - Windows 방화벽이 미러 SQL Server K16-ocs.los_a.lsipt.local\rtc에서 사용하도록 설정된 경우 방화벽을 통해 포트 5022에 액세스할 수 있어야 합니다.

    - Windows 방화벽이 미러링 모니터 서버 AB14-lct.los_a.lsipt.local\rtc에서 사용하도록 설정된 경우 방화벽을 통해 포트 7022에 액세스할 수 있어야 합니다.

   - 모든 기본 SQL 미러 서버의 SQL 계정을 실행하는 계정에 파일 공유 \\ E04-OCS\csdatabackup에 대한 읽기/쓰기 권한이 있습니다.

   - WMI(Windows Management Instrumentation) 공급자가 이러한 모든 서버에서 실행되고 있는지 확인합니다. 이 cmdlet은 이 공급자를 사용해서 모든 기본, 미러 및 미러링 모니터 서버에서 실행되는 SQL Server 서비스에 대한 계정 정보를 찾습니다.

   - 이 cmdlet을 실행 중인 계정에 모든 미러 서버에 대한 데이터 및 로그 파일의 폴더를 만들 수 있는 권한이 있는지 확인합니다.

   - SQL 인스턴스가 실행을 위해 사용하는 사용자 계정에 파일 공유에 대한 읽기/쓰기 권한이 있어야 합니다. 파일 공유가 다른 서버에 있고 SQL 인스턴스가 로컬 시스템 계정으로 실행되는 경우에는 해당 SQL 인스턴스를 호스팅하는 서버에 파일 공유 권한을 부여해야 합니다.

3. A를 입력한 후 Enter 키를 누릅니다.

    미러링이 구성됩니다.

    **Install-CsMirrorDatabase는** 미러를 설치하고 기본 데이터베이스 저장소에 있는 모든 데이터베이스에 SQL 구성합니다. 특정 데이터베이스에만 미러링을 구성하려는 경우 -DatabaseType 옵션을 사용할 수 있습니다. 또는 일부를 제외한 모든 데이터베이스에 대해 미러링을 구성하려는 경우 제외할 데이터베이스 이름 목록과 함께 -ExcludeDatabaseList 옵션을 사용할 수 있습니다.

    예를 들어 **Install-CsMirrorDatabase** 에 다음 옵션을 추가하면 rtcab 및 rtcxds를 제외한 모든 데이터베이스가 미러링됩니다.

    `-ExcludeDatabaseList rtcab,rtcxds`

   예를 들어 **Install-CsMirrorDatabase** 에 다음 옵션을 추가하면 rtcab, rtcshared 및 rtcxds 데이터베이스만 미러링됩니다.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>SQL 미러링 제거 또는 변경

토폴로지 작성기에서 풀에 대한 SQL 미러링을 제거하려면 먼저 SQL Server에서 미러를 제거하는 cmdlet을 사용해야 합니다. 그런 후 토폴로지 작성기를 사용해서 토폴로지에서 미러를 제거할 수 있습니다. SQL Server에서 미러를 제거하려면 다음 cmdlet을 사용합니다.

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

예를 들어 User 데이터베이스에 대한 미러링을 제거하고 데이터베이스를 삭제하려면 다음을 입력합니다.

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

이 옵션을 사용하면 영향을 받는 데이터베이스가 미러에서  `-DropExistingDatabasesOnMirror` 삭제됩니다.

그런 후 토폴로지에서 미러를 제거하려면 다음을 수행합니다.

1. 토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭하고 **속성 편집** 을 클릭합니다.

2. **SQL 저장소 미러링 사용** 의 선택을 취소하고 **확인** 을 클릭합니다.

3. 토폴로지를 게시합니다.

## <a name="removing-a-mirroring-witness"></a>미러링 모니터 서버 제거

백 엔드 서버 미러링 구성에서 미러링 서버를 제거해야 하는 경우 이 절차를 사용합니다.

1. 토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭하고 **속성 편집** 을 클릭합니다.

2. **SQL Server 미러링 모니터 서버를 사용하여 자동 장애 조치(Failover) 사용** 의 선택을 취소하고 **확인** 을 클릭합니다.

3. 토폴로지를 게시합니다.

    토폴로지 게시 후 토폴로지 작성기에서 다음을 포함하는 메시지가 표시됩니다.

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    그러나 이 단계를 수행하지 말고 전체 미러링 구성을 제거하기 위해  `Uninstall-CsMirrorDatabase` 입력하지 않습니다.

4. 서버 구성에서 미러링 SQL Server 제거하려면 데이터베이스 미러링 [세션(SQL Server)에서](https://go.microsoft.com/fwlink/p/?LinkId=268456)미러링 SQL Server.


