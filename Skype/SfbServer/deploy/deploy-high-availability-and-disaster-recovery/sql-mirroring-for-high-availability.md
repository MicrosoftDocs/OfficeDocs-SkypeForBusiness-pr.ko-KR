---
title: 비즈니스용 Skype 서버 2015에서 백 엔드 서버에 대 한 SQL 미러링 배포 높은 가용성을 제공 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 70224520-b5c8-4940-a08e-7fb9b1adde8d
description: SQL 미러링을 배포할 수 있으려면 서버에서 최소 SQL Server 2008 R2를 실행 해야 합니다. 이 버전은 모든 관련 서버 (기본, 미러, 미러링 모니터)에서 실행 되어야 합니다. 자세한 내용은 SQL Server 2008 서비스 팩 1에 대 한 누적 업데이트 패키지 9를 참조 하세요.
ms.openlocfilehash: 19f315d643ea5b9379445bf7571e49e7d658f5ab
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003588"
---
# <a name="deploy-sql-mirroring-for-back-end-server-high-availability-in-skype-for-business-server-2015"></a>비즈니스용 Skype 서버 2015에서 백 엔드 서버에 대 한 SQL 미러링 배포 높은 가용성을 제공 합니다.


SQL 미러링을 배포할 수 있으려면 서버에서 최소 SQL Server 2008 R2를 실행 해야 합니다. 이 버전은 모든 관련 서버 (기본, 미러, 미러링 모니터)에서 실행 되어야 합니다. 자세한 내용은 [SQL Server 2008 서비스 팩 1에 대 한 누적 업데이트 패키지 9](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=2083921)를 참조 하세요.

일반적으로 미러링 모니터로 두 백 엔드 서버 간에 SQL 미러링을 설정 하려면 다음이 필요 합니다.

- 주 서버의 SQL Server 버전은 SQL 미러링을 지원 해야 합니다.

- 기본, 미러, 미러링 모니터 (배포 된 경우)는 동일한 버전의 SQL Server를 사용 해야 합니다.

- 기본 및 미러에는 동일한 버전의 SQL Server가 있어야 합니다. 미러링 모니터 서버에 다른 버전이 있을 수 있습니다.

미러링 모니터 역할에 대해 지원 되는 SQL 버전에 대 한 SQL 모범 사례는 [데이터베이스 미러링 감시](https://go.microsoft.com/fwlink/p/?LinkId=247345)를 참조 하세요.

토폴로지 작성기를 사용 하 여 SQL 미러링을 배포 합니다. 토폴로지 작성기에서 데이터베이스를 미러링 하는 옵션을 선택 하면 토폴로지를 게시할 때 토폴로지 작성기에서 미러링 (미러링 모니터 서버 설정 포함)을 설정 합니다. 미러를 설정 하거나 제거할 때와 동시에 미러링 모니터를 설정 하거나 제거할 수 있습니다. 미러링 모니터만 배포 하거나 제거 하는 별도의 명령은 없습니다.

서버 미러링을 구성 하려면 먼저 SQL 데이터베이스 권한을 올바르게 설정 해야 합니다. 자세한 내용은 [데이터베이스 미러링 또는 AlwaysOn 가용성 그룹 (SQL Server)에 대 한 로그인 계정 설정을](https://go.microsoft.com/fwlink/p/?LinkId=268454)참조 하세요.

SQL 미러링에서는 데이터베이스 복구 모드가 항상 **Full**로 설정 되며,이는 백 엔드 서버의 디스크 공간 부족을 방지 하기 위해 트랜잭션 로그 크기를 면밀 하 게 모니터링 하 고 트랜잭션 로그를 정기적으로 백업 해야 한다는 것입니다. 트랜잭션 로그 백업의 빈도는 로그 증가 속도에 따라 다르며,이는 프런트 엔드 풀의 사용자 활동에서 발생 하는 데이터베이스 트랜잭션에 따라 달라 집니다. 계획을 적절 하 게 수행할 수 있도록 배포 작업 부하에 예상 되는 트랜잭션 로그 성장이 얼마나 되는지 결정 하는 것이 좋습니다. 다음 문서는 SQL 백업 및 로그 관리에 대 한 추가 정보를 제공 합니다.

- [데이터베이스 복구 모델](https://go.microsoft.com/fwlink/p/?LinkId=268446)

- [백업 개요](https://go.microsoft.com/fwlink/p/?LinkId=268449)

- [트랜잭션 로그 백업](https://go.microsoft.com/fwlink/p/?LinkId=268452)

SQL 미러링을 사용 하면 풀을 만들 때 또는 풀이 이미 만들어진 후에 미러링에 대 한 토폴로지를 구성할 수 있습니다.

> [!IMPORTANT]
> 토폴로지 작성기 또는 cmdlet을 사용 하 여 SQL 미러링을 설정 및 제거 하는 것은 주, 미러, 미러링 모니터 (원하는 경우) 서버가 모두 동일한 도메인에 속해 있는 경우에만 지원 됩니다. 다른 도메인의 서버 간에 SQL 미러링을 설정 하려면 SQL Server 설명서를 참조 하세요.

> [!IMPORTANT]
> 백 엔드 데이터베이스 미러링 관계를 변경할 때마다 풀의 모든 프런트 엔드 서버를 다시 시작 해야 합니다. 미러링 변경 내용에 대 한 > (예: 미러 위치 변경) 토폴로지 작성기를 사용 하 여 다음 세 단계를 수행 해야 합니다.

1. 이전 미러 서버에서 미러링을 제거 합니다.

2. 새 미러 서버에 미러링을 추가 합니다.

3. 토폴로지를 게시 합니다.

> [!NOTE]
> 쓰기 파일에 대 한 파일 공유를 만들어야 하며, SQL Server 및 SQL 에이전트에서 실행 중인 서비스에 읽기/쓰기 권한이 필요 합니다. Sql Server 서비스가 네트워크 서비스의 컨텍스트에서 실행 되는 경우 주 서버와 미러 SQL server \<의\> \\ 도메인<sqlservername\>$을 공유 사용 권한으로 추가할 수 있습니다. $는 컴퓨터 계정 임을 식별 하는 데 중요 합니다.

## <a name="to-configure-sql-mirroring-while-creating-a-pool-in-topology-builder"></a>토폴로지 작성기에서 풀을 만드는 동안 SQL 미러링을 구성 하려면

1. **Sql 저장소 정의** 페이지에서 **sql 스토어** 상자 옆에 있는 **새로 만들기** 를 클릭 합니다.

2. **새 SQL Store 정의** 페이지에서 기본 저장소를 지정 하 고, **이 sql 인스턴스가 미러링 관계에 있는 경우**를 선택 하 고, sql 미러링 포트 번호 (기본값 5022)를 지정한 다음 **확인**을 클릭 합니다.

3. 다시 **sql 저장소 정의** 페이지에서 **Sql 저장소 미러링 사용**을 선택 합니다.

4. **새 Sql 저장소 정의** 페이지에서 미러로 사용할 SQL 저장소를 지정 합니다. **이 SQL 인스턴스는 미러링 관계에 있으며**, 포트 번호 (기본값 5022)를 지정한 다음 **확인**을 클릭 합니다.

5. 이 미러에 미러링 모니터를 원하는 경우 다음을 수행 합니다.

    에서. **SQL 미러링 감시 사용을 선택 하 여 자동 장애 조치를 사용**합니다.

    b. **Sql Store 정의** 페이지에서 **sql 미러링 미러링 모니터 사용을 선택 하 여 자동 장애 조치 (failover)를 설정 하**고 미러링 모니터로 사용할 sql 저장소를 지정 합니다.

    c. 포트 번호 (기본값 7022)를 지정 하 고 **확인**을 클릭 합니다.

6. 프런트 엔드 풀 및 다른 모든 역할을 토폴로지에 대해 정의한 후 토폴로지 작성기를 사용 하 여 토폴로지를 게시 합니다. 토폴로지가 게시 되 면 중앙 관리 저장소를 호스트 하는 프런트 엔드 풀에 SQL 미러링이 설정 되어 있는 경우 기본 및 미러 SQL 저장소 데이터베이스를 모두 만드는 옵션이 표시 됩니다.

    **설정을**클릭 하 고 미러링 백업에 대 한 파일 공유로 사용할 경로를 입력 합니다.

    **확인** 을 클릭 한 후 **다음** 을 클릭 하 여 데이터베이스를 만들고 토폴로지를 게시 합니다. 미러링과 미러링 모니터 (지정 된 경우)가 배포 됩니다.

토폴로지 작성기를 사용 하 여 이미 존재 하는 풀의 속성을 편집 하 여 SQL 미러링을 사용할 수 있습니다.

## <a name="to-add-sql-mirroring-to-an-existing-front-end-pool-in-topology-builder"></a>토폴로지 작성기에서 기존 프런트 엔드 풀에 SQL 미러링을 추가 하려면

1. 토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.

2. **Sql 저장소 미러링 사용**을 선택 하 고 **sql 저장소 미러링**옆에 있는 **새로 만들기** 를 클릭 합니다.

3. 미러로 사용할 SQL 저장소를 지정 합니다.

4. **이 sql 인스턴스는 미러링 관계에 있으며**, 기본 포트가 5022 인 sql 미러링 포트 번호를 지정한 다음 **확인**을 클릭 합니다.

5. 미러링 모니터를 구성 하려면 **SQL 미러링 미러링 모니터 사용을 선택 하 여 자동 장애 조치 (failover)를 사용 하도록 설정**하 고 **새로 만들기**를 클릭 합니다.

6. 미러링 모니터로 사용할 SQL 저장소를 지정 합니다.

7. **이 sql 인스턴스는 미러링 관계에 있으며**, sql 미러링 포트 번호 (기본 포트는 7022)를 지정한 다음 **확인**을 클릭 합니다.

8. **확인**을 클릭합니다.

9. 토폴로지를 게시 합니다. 이렇게 하면 데이터베이스를 설치 하 라는 메시지가 표시 됩니다.

    토폴로지 게시 프로세스 중에 파일 공유 경로를 정의 하 라는 메시지가 표시 됩니다. 미러링에 참여 하는 SQL 서버는 미러를 설정 하기 위해이 파일 공유에 대 한 읽기/쓰기 액세스 권한이 있어야 합니다.

다음 절차를 진행 하기 전에 데이터베이스를 설치 해야 합니다.

SQL 미러링을 설정할 때 다음 사항에 유의 해야 합니다.

- 미러링 끝점이 이미 있으면이 끝점을 정의한 포트를 사용 하 여 다시 사용할 수 있으며 토폴로지에 지정 된 것을 무시 하 게 됩니다.

- 다른 SQL 인스턴스에 대 한 다른 응용 프로그램에 이미 할당 된 모든 포트는 설치 된 SQL 인스턴스에 직접 사용할 수 없습니다. 이는 같은 서버에 둘 이상의 SQL 인스턴스가 설치 되어 있는 경우 미러링에 동일한 포트를 사용 하지 않아야 한다는 것을 의미 합니다. 자세한 내용은 다음 문서를 참조 하세요.

  - [서버 네트워크 주소 (데이터베이스 미러링) 지정](https://go.microsoft.com/fwlink/p/?LinkId=247346)

  - [데이터베이스 미러링 끝점 (SQL Server)](https://go.microsoft.com/fwlink/p/?LinkId=247347)

## <a name="using-skype-for-business-server-2015-management-shell-cmdlets-to-set-up-sql-mirroring"></a>비즈니스용 Skype Server 2015 관리 셸 Cmdlet을 사용 하 여 SQL 미러링 설정

미러링을 설정 하는 가장 쉬운 방법은 토폴로지 작성기를 사용 하는 것 이지만, 이렇게 하면 cmdlet을 사용할 수도 있습니다.

1. 비즈니스용 Skype Server 2015 관리 셸 창을 열고 다음 cmdlet을 실행 합니다.

   ```powershell
   Install-CsMirrorDatabase [-ConfiguredDatabases] [-ForInstance] [-ForDefaultInstance] [-DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance >] -FileShare <fileshare> -SqlServerFqdn <primarySqlserverFqdn> [-SqlInstanceName] [-DatabasePathMap] [-ExcludeDatabaseList] [-DropExistingDatabasesOnMirror] -Verbose
   ```

    예를 들면 다음과 같습니다.

   ```powershell
   Install-CsMirrorDatabase -ConfiguredDatabases -FileShare \\PRIMARYBE\csdatabackup -SqlServerFqdn primaryBE.contoso.com -DropExistingDatabasesOnMirror -Verbose
   ```

    다음이 표시 됩니다.

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

2. 다음을 확인 합니다.

    - 기본 SQL Server los_a e04에서 Windows 방화벽을 사용 하는 경우 방화벽을 통해 포트 5022에 액세스할 수 있습니다. local\rtc.

    - 미러 SQL Server K16에서 Windows 방화벽을 사용 하는 경우 방화벽을 통해 포트 5022에 액세스할 수 있습니다. local\rtc.. los_a

    - Los_a AB14에서 Windows 방화벽을 사용 하는 경우 방화벽을 통해 포트 7022에 액세스할 수 있습니다. local\rtc.

   - 모든 기본 및 미러 SQL server에서 SQL Server를 실행 하는 계정에는 파일 공유 \\E04-OCS\csdatabackup에 대 한 읽기/쓰기 권한이 있습니다.

   - 이러한 모든 서버에서 WMI (Windows Management Instrumentation) 공급자가 실행 중인지 확인 합니다. Cmdlet은이 공급자를 사용 하 여 모든 주 미러 및 미러링 모니터 서버에서 실행 되는 SQL Server 서비스에 대 한 계정 정보를 찾습니다.

   - 이 cmdlet을 실행 하는 계정에 모든 미러 서버의 데이터 및 로그 파일에 대 한 폴더를 만들 수 있는 권한이 있는지 확인 합니다.

   - SQL 인스턴스에서 실행 하는 데 사용 하는 사용자 계정에는 파일 공유에 대 한 읽기/쓰기 권한이 있어야 합니다. 파일 공유가 다른 서버에 있고 SQL 인스턴스가 로컬 시스템 계정을 실행 하는 경우에는 SQL 인스턴스를 호스트 하는 서버에 파일 공유 권한을 부여 해야 합니다.

3. A를 입력 하 고 enter 키를 누릅니다.

    미러링이 구성 됩니다.

    **설치-CsMirrorDatabase** 는 미러를 설치 하 고 기본 SQL 저장소에 있는 모든 데이터베이스에 대해 미러링을 구성 합니다. 특정 데이터베이스에 대해서만 미러링을 구성 하려는 경우-DatabaseType 옵션을 사용 하거나, 몇 개를 제외한 모든 데이터베이스에 대 한 미러링을 구성 하려는 경우 쉼표로 구분 된 데이터베이스 목록과 함께-ExcludeDatabaseList 옵션을 사용할 수 있습니다. 제외할 이름입니다.

    예를 들어, **설치-CsMirrorDatabase**에 다음 옵션을 추가 하는 경우 rtcab 및 rtcxds를 제외한 모든 데이터베이스가 미러 됩니다.

    `-ExcludeDatabaseList rtcab,rtcxds`

   예를 들어, **설치-CsMirrorDatabase**에 다음 옵션을 추가 하면 rtcab, rtcshared 및 rtcxds 데이터베이스만 미러링됩니다.

    `-DatabaseType User`

## <a name="removing-or-changing-sql-mirroring"></a>SQL 미러링 제거 또는 변경

토폴로지 작성기에서 풀의 SQL 미러링을 제거 하려면 먼저 cmdlet을 사용 하 여 SQL Server에서 미러를 제거 해야 합니다. 그런 다음 토폴로지 작성기를 사용 하 여 토폴로지에서 미러를 제거할 수 있습니다. SQL Server에서 미러를 제거 하려면 다음 cmdlet을 사용 합니다.

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]
```

예를 들어 미러링을 제거 하 고 사용자 데이터베이스용 데이터베이스를 삭제 하려면 다음을 입력 합니다.

```powershell
Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror
```

이 `-DropExistingDatabasesOnMirror` 옵션을 선택 하면 해당 데이터베이스가 미러에서 삭제 됩니다.

그런 다음 토폴로지에서 미러를 제거 하려면 다음을 수행 합니다.

1. 토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.

2. **SQL 저장소 미러링 사용** 을 선택 취소 하 고 **확인**을 클릭 합니다.

3. 토폴로지를 게시 합니다.

## <a name="removing-a-mirroring-witness"></a>미러링 모니터 제거

백 엔드 서버 미러링 구성에서 미러링 모니터를 제거 해야 하는 경우이 절차를 사용 합니다.

1. 토폴로지 작성기에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.

2. **SQL Server 미러링 모니터 사용을 선택 취소 하 여 자동 장애 조치를 활성화 하** 고 **확인**을 클릭 합니다.

3. 토폴로지를 게시 합니다.

    토폴로지를 게시 한 후 토폴로지 작성기에는 다음이 포함 된 메시지가 표시 됩니다.

   ```console
   Run the Uninstall-CsMirrorDatabase cmdlet to remove databases that are paired with following primary databases.
   ```

    그러나이 단계를 따르지 말고 전체 미러링 구성을 제거 하는 `Uninstall-CsMirrorDatabase` 것으로 입력 하지 마세요.

4. SQL Server 구성에서 미러링 모니터만 제거 하려면 [데이터베이스 미러링 세션 (SQL Server)에서 미러링 모니터 제거](https://go.microsoft.com/fwlink/p/?LinkId=268456)의 지침을 따릅니다.


