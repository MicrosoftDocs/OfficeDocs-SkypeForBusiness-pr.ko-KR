---
title: 중앙 관리 서버 이동
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 비즈니스용 Skype 서버 2019로 마이그레이션한 후 레거시 서버를 제거하려면 먼저 중앙 관리 서버를 비즈니스용 Skype 서버 2019 프런트 엔드 서버 또는 풀로 이동해야 합니다.
ms.openlocfilehash: 0c5ee756a52d61008498e50df5d3bf64fbe20f8c4ef1ee96e4e7528c2a3bd820
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300604"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>레거시 중앙 관리 서버를 2019년 비즈니스용 Skype 서버 이동

비즈니스용 Skype 서버 2019로 마이그레이션한 후 레거시 서버를 제거하려면 먼저 중앙 관리 서버를 비즈니스용 Skype 서버 2019 프런트 엔드 서버 또는 풀로 이동해야 합니다. 
  
중앙 관리 서버는 데이터베이스의 읽기/쓰기 복사본이 중앙 관리 서버를 포함하는 프런트 엔드 서버에 의해 저장되는 단일 마스터/다중 복제본 시스템입니다. 중앙 관리 서버가 포함된 프런트 엔드 서버를 포함하여 토폴로지의 각 컴퓨터에는 설치 및 배포 중에 컴퓨터에 설치된 SQL Server 데이터베이스(기본적으로 RTCLOCAL)에 중앙 관리 저장소 데이터의 읽기 전용 복사본이 있습니다. 로컬 데이터베이스는 모든 컴퓨터에서 서비스로 실행되는 비즈니스용 Skype 서버 Replica Replicator 에이전트를 통해 복제본 업데이트를 수신합니다. 중앙 관리 서버 및 로컬 복제 데이터베이스의 실제 데이터베이스 이름은 xds.mdf 및 xds.ldf 파일로 구성되는 XDS입니다. 마스터 데이터베이스 위치는 Active Directory 도메인 서비스의 SCP(서비스 제어 지점)에서 참조됩니다. 중앙 관리 서버를 사용하여 관리 및 구성하는 모든 비즈니스용 Skype 서버 SCP를 사용하여 중앙 관리 저장소를 찾습니다.
  
중앙 관리 서버를 이동한 후 원래 프런트 엔드 서버에서 중앙 관리 서버 데이터베이스를 제거해야 합니다. 중앙 관리 서버 데이터베이스를 제거하는 데 대한 자세한 내용은 [Remove the SQL Server database for a Front End pool를 참조하십시오.](remove-the-sql-server-database-for-a-front-end-pool.md)
  
비즈니스용 Skype 서버 관리 셸에서 Windows PowerShell cmdlet **Move-CsManagementServer를** 사용하여 레거시 설치 SQL Server 데이터베이스에서 비즈니스용 Skype 서버 2019 SQL Server 데이터베이스로 데이터베이스를 이동한 다음 비즈니스용 Skype 서버 2019 중앙 관리 서버 위치를 지점하도록 SCP를 업데이트합니다. 
  
중앙 관리 서버를 이동하기 전에 이 섹션의 절차에 따라 비즈니스용 Skype 서버 2019 프런트 엔드 서버를 준비합니다.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>프런트 엔드 Enterprise Edition 준비

1. 비즈니스용 Skype 서버 2019 Enterprise Edition 중앙 관리 서버를 재배치할 프런트 엔드 풀에서 비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 **RTCUniversalServerAdmins** 그룹의 구성원으로 로그온합니다. 또한 중앙 관리 저장소를 SQL Server 데이터베이스에 대한 데이터베이스 sysadmin 사용자 권한 및 사용 권한도 있어야 합니다. 
    
2. 관리 비즈니스용 Skype 서버 셸을 열 수 있습니다.
    
3. 비즈니스용 Skype 서버 2019 SQL Server 데이터베이스에서 새 중앙 관리 저장소를 만들하려면 비즈니스용 Skype 서버 관리 셸에서 다음을 입력합니다.
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. 프런트 엔드 서비스의 비즈니스용 Skype 서버 **시작** **상태인지 확인**
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>프런트 엔드 Standard Edition 준비

1. 중앙 관리 서버를 재배치하려는 비즈니스용 Skype 서버 2019 Standard Edition 프런트 엔드 서버에서 비즈니스용 Skype 서버 관리 **셸이 RTCUniversalServerAdmins** 그룹의 구성원으로 설치된 컴퓨터에 로그온합니다. 
    
2. 비즈니스용 Skype 서버 배포 마법사를 열 수 있습니다.
    
3. 비즈니스용 Skype 서버 배포 마법사에서 첫 번째 Standard Edition **준비를 클릭합니다.**
    
4. 명령 **실행** 페이지에서 SQL Server Express 중앙 관리 서버로 설치됩니다. 또한 필요한 방화벽 규칙이 만들어집니다. 데이터베이스 및 필수 구성 요소 소프트웨어 설치가 완료되면 **마침** 을 클릭합니다.
    
    > [!NOTE]
    > 초기 설치는 시간이 오래 걸릴 수 있으며 명령 출력 요약 화면에 업데이트가 표시되지 않을 수 있습니다. 이는 설치 시 SQL Server Express. 데이터베이스 설치를 모니터링해야 하는 경우 작업 관리자를 사용하여 설치를 모니터링합니다. 
  
5. 비즈니스용 Skype 서버 2019 Standard Edition 프런트 엔드 서버에 새 중앙 관리 저장소를 만들 비즈니스용 Skype 서버 셸에 다음을 입력합니다. 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. 프런트 엔드 서비스의 비즈니스용 Skype 서버 **시작** **상태인지 확인**
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>레거시를 이동하려면 2019년 8월에 중앙 관리 비즈니스용 Skype 서버 설치

1. 중앙 관리 서버가 될 비즈니스용 Skype 서버 2019 서버에서 비즈니스용 Skype 서버 관리 **셸이 RTCUniversalServerAdmins** 그룹의 구성원으로 설치된 컴퓨터에 로그온합니다. SQL Server 데이터베이스 관리자 사용자 권한 및 사용 권한도 있어야 합니다. 
    
2. 관리자 비즈니스용 Skype 서버 셸을 열고(관리자 권한으로 실행).
    
3. 관리 비즈니스용 Skype 서버 셸에 다음을 입력합니다. 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > 성공하지 못하면 계속하기 전에 명령이 완료되지 못하게 하는 문제를 `Enable-CsTopology` 해결합니다. **Enable-CsTopology가** 실패하면 이동이 실패하고 중앙 관리 저장소가 없는 상태로 토폴로지가 남을 수 있습니다. 
  
4. 비즈니스용 Skype 서버 2019 프런트 엔드 서버 또는 프런트 엔드 풀의 비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다. 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. 비즈니스용 Skype 서버 관리 셸에는 현재 상태 및 제안된 상태의 서버, 파일 저장소, 데이터베이스 저장소 및 서비스 연결 지점이 표시됩니다. 정보를 주의해서 읽고 원래 의도된 원본과 대상인지 확인합니다. 계속하려면 **Y** 를 입력하고 이동을 중지하려면 **N** 을 입력합니다. 
    
6. **Move-CsManagementServer** 명령으로 생성된 경고 또는 오류를 검토하고 해결합니다. 
    
7. 비즈니스용 Skype 서버 2019 서버에서 비즈니스용 Skype 서버 실행합니다. 
    
8. 비즈니스용 Skype 서버 배포 마법사에서 비즈니스용 Skype 서버 **시스템** 설치 또는 업데이트를 **클릭하고, 2단계:** 비즈니스용 Skype 서버 구성 요소 설치 또는 제거를 클릭하고, 다음, 요약을 검토한 다음 마친을 **클릭합니다.** 
    
9. 레거시 설치 서버에서 배포 마법사를 니다. 
    
10. 비즈니스용 Skype 서버 배포 마법사에서 비즈니스용 Skype 서버 **시스템** 설치 또는 업데이트를 **클릭하고, 2단계:** 비즈니스용 Skype 서버 구성 요소 설치 또는 제거를 클릭하고, 다음, 요약을 검토한 다음 마친을 **클릭합니다.** 
    
11. 2019 비즈니스용 Skype 서버 다시 시작하십시오. 이 설정은 중앙 관리 서버 데이터베이스에 액세스하기 위한 그룹 구성원 자격 변경 때문에 필요합니다.
    
12. 새 중앙 관리 저장소와의 복제가 발생하고 비즈니스용 Skype 서버 관리 셸에 다음을 입력합니다. 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > 복제로 모든 현재 복제본을 업데이트하려면 시간이 다소 걸릴 수 있습니다. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>이동 후 레거시 중앙 관리 저장소 파일을 제거하려면

1. 레거시 설치 서버에서 비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 **RTCUniversalServerAdmins** 그룹의 구성원으로 로그온합니다. SQL Server 데이터베이스 관리자 사용자 권한 및 사용 권한도 있어야 합니다. 
    
2. Open 비즈니스용 Skype 서버 관리 셸
    
    > [!CAUTION]
    > 복제가 완료되고 안정화되기 전까지는 이전 데이터베이스 파일의 제거를 진행하지 마십시오. 복제를 완료하기 전에 파일을 제거하면 복제 프로세스가 중단된 후 새로 이동된 중앙 관리 서버를 알 수 없는 상태로 떠날 수 있습니다. **Get-CsManagementStoreReplicationStatus** cmdlet을 사용하여 복제 상태를 확인합니다. 
  
3. 레거시 설치 중앙 관리 서버에서 중앙 관리 저장소 데이터베이스 파일을 제거하려면 다음을 입력합니다.
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    예:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    여기서 는 Enterprise Edition 배포에 레거시 백 엔드 서버를 설치하거나 Standard Edition _\<FQDN of SQL Server\>_ 서버의 FQDN입니다. 
    

