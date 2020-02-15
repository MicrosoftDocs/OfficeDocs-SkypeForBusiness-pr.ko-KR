---
title: Lync server 2010 중앙 관리 서버를 Lync Server 2013로 이동
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move the Lync Server 2010 Central Management Server to Lync Server 2013
ms:assetid: 30cc98f2-1916-4dbe-99d0-8df5368ed3ec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688013(v=OCS.15)
ms:contentKeyID: 49733602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29bdf9a5956dfec0dd35703aaf7a7606da63595b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034468"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Lync server 2010 중앙 관리 서버를 Lync Server 2013로 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-25_

Lync Server 2010에서 Lync Server 2013로 마이그레이션한 후에는 레거시 Lync Server 2010 서버를 제거 하기 전에 Lync server 2010 중앙 관리 서버를 Lync Server 2013 프런트 엔드 서버 또는 풀로 이동 해야 합니다.

중앙 관리 서버는 단일 마스터/다중 복제본 시스템으로, 중앙 관리 서버를 포함 하는 프런트 엔드 서버에서 데이터베이스의 읽기/쓰기 복사본을 보유 하 고 있습니다. 중앙 관리 서버를 포함 하는 프런트 엔드 서버를 포함 하 여 토폴로지의 각 컴퓨터에는 설치 하는 동안 컴퓨터에 설치 된 SQL Server 데이터베이스 (기본적으로 RTCLOCAL)의 중앙 관리 저장소 데이터에 대 한 읽기 전용 복사본이 포함 됩니다. 배포. 로컬 데이터베이스는 모든 컴퓨터에서 서비스로 실행 되는 Lync Server 복제본 복제기 에이전트를 통해 복제 데이터베이스 업데이트를 수신 합니다. 중앙 관리 서버 및 로컬 복제본의 실제 데이터베이스 이름은 xds로, xds로, xds로 구성 됩니다. Active Directory 도메인 서비스의 SCP (서비스 제어 지점)에서 마스터 데이터베이스 위치를 참조 합니다. 중앙 관리 서버를 사용 하 여 Lync Server를 관리 및 구성 하는 모든 도구는 SCP를 사용 하 여 중앙 관리 저장소를 찾습니다.

중앙 관리 서버를 성공적으로 이동한 후에는 원래 프런트 엔드 서버에서 중앙 관리 서버 데이터베이스를 제거 해야 합니다. 중앙 관리 서버 데이터베이스를 제거 하는 방법에 대 한 자세한 내용은 [Remove THE SQL Server database for a 프런트 End pool](remove-the-sql-server-database-for-a-front-end-pool.md)을 참조 하십시오.

Lync server 관리 셸에서 Windows PowerShell cmdlet **move-csmanagementserver** 를 사용 하 여 lync SERVER 2010 sql server 데이터베이스에서 lync SERVER 2013 sql server 데이터베이스로 데이터베이스를 이동한 다음 lync Server 2013 중앙 관리 서버 위치를 가리키도록 SCP를 업데이트 합니다.

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>중앙 관리 서버를 이동 하기 전에 Lync Server 2013 프런트 엔드 서버 준비

Lync server 2010 중앙 관리 서버를 이동 하기 전에이 섹션의 절차를 사용 하 여 Lync Server 2013 프런트 엔드 서버를 준비 합니다.

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Enterprise Edition 프런트 엔드 풀을 준비 하려면

1.  중앙 관리 서버를 재배치할 Lync Server 2013 Enterprise Edition 프런트 엔드 풀에서 Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다. 또한 중앙 관리 저장소를 설치 하려는 데이터베이스에 대 한 SQL Server 데이터베이스 sysadmin 사용자 권한 및 사용 권한이 있어야 합니다.

2.  Lync Server 관리 셸을 엽니다.

3.  Lync server 2013 SQL Server 데이터베이스에서 새 중앙 관리 저장소를 만들려면 Lync 서버 관리 셸에서 다음을 입력 합니다.
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  **Lync Server 프런트 엔드** 서비스의 상태가 **시작됨**인지 확인합니다.

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>Standard Edition 프런트 엔드 서버를 준비 하려면

1.  중앙 관리 서버를 재배치할 Lync Server 2013 Standard Edition 프런트 엔드 서버에서 Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  Lync Server 배포 마법사를 엽니다.

3.  Lync Server 배포 마법사에서 **첫 번째 Standard Edition Server 준비**를 클릭 합니다.

4.  **명령 실행** 페이지에서 SQL Server Express는 중앙 관리 서버로 설치 됩니다. 또한 필요한 방화벽 규칙이 만들어집니다. 데이터베이스 및 필수 구성 요소 소프트웨어 설치가 완료되면 **마침**을 클릭합니다.
    
    <div>
    

    > [!NOTE]  
    > 초기 설치는 시간이 오래 걸릴 수 있으며 명령 출력 요약 화면에 업데이트가 표시되지 않을 수 있습니다. SQL Server Express가 설치 되었기 때문입니다. 데이터베이스 설치를 모니터링해야 하는 경우 작업 관리자를 사용하여 설치를 모니터링합니다.

    
    </div>

5.  Lync server 2013 Standard Edition 프런트 엔드 서버에서 새 중앙 관리 저장소를 만들려면 Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  **Lync Server 프런트 엔드** 서비스의 상태가 **시작됨**인지 확인합니다.

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>Lync server 2010 중앙 관리 서버를 Lync Server 2013로 이동 하려면

1.  중앙 관리 서버가 되는 Lync Server 2013 서버에서 Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다. SQL Server 데이터베이스 관리자 사용자 권한 및 사용 권한도 있어야 합니다.

2.  Lync Server 관리 셸을 엽니다.

3.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > 이 <CODE>Enable-CsTopology</CODE> 실패할 경우 계속 하기 전에 명령을 완료 하지 못하게 하는 문제를 해결 합니다. <STRONG>Enable-enable-cstopology</STRONG> 가 실패 하면 이동이 실패 하 고 중앙 관리 저장소가 없는 상태로 토폴로지가 나갈 수 있습니다.

    
    </div>

4.  Lync server 2013 프런트 엔드 서버 또는 프런트 엔드 풀의 Lync 서버 관리 셸에서 다음을 입력 합니다.
    
        Move-CsManagementServer

5.  Lync Server 관리 셸에서는 현재 상태와 제안 된 상태의 서버, 파일 저장소, 데이터베이스 저장소 및 서비스 연결 지점을 표시 합니다. 정보를 주의해서 읽고 원래 의도된 원본과 대상인지 확인합니다. 계속하려면 **Y**를 입력하고 이동을 중지하려면 **N**을 입력합니다.

6.  **Move-CsManagementServer** 명령으로 생성된 경고 또는 오류를 검토하고 해결합니다.

7.  Lync Server 2013 서버에서 Lync Server 배포 마법사를 엽니다.

8.  Lync Server 배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 하 고 **2 단계: Lync Server 구성 요소 설치 또는 제거**를 클릭 한 후 **다음**을 클릭 하 고 요약을 검토 한 후 **마침을**클릭 합니다.

9.  Lync Server 2010 서버에서 Lync Server 배포 마법사를 엽니다.

10. Lync Server 배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 하 고 **2 단계: Lync Server 구성 요소 설치 또는 제거**를 클릭 한 후 **다음**을 클릭 하 고 요약을 검토 한 후 **마침을**클릭 합니다.

11. Lync Server 2013 서버를 다시 부팅 합니다. 이는 액세스 중앙 관리 서버 데이터베이스에 대 한 그룹 구성원 자격을 변경 했기 때문에 필요 합니다.

12. 새 중앙 관리 저장소를 사용한 복제가 진행 되 고 있는지 확인 하려면 Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > 복제로 모든 현재 복제본을 업데이트하려면 시간이 다소 걸릴 수 있습니다.

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>이동 후 Lync Server 2010 중앙 관리 저장소 파일을 제거 하려면

1.  Lync Server 2010 서버: Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다. SQL Server 데이터베이스 관리자 사용자 권한 및 사용 권한도 있어야 합니다.

2.  Lync Server 관리 셸 열기
    
    <div>
    

    > [!WARNING]  
    > 복제가 완료되고 안정화되기 전까지는 이전 데이터베이스 파일의 제거를 진행하지 마십시오. 복제를 완료 하기 전에 파일을 제거 하면 복제 프로세스를 중단 하 고 새로 이동한 중앙 관리 서버를 알 수 없는 상태로 유지 합니다. <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> cmdlet을 사용하여 복제 상태를 확인합니다.

    
    </div>

3.  Lync Server 2010 중앙 관리 서버에서 중앙 관리 저장소 데이터베이스 파일을 제거 하려면 다음을 입력 합니다.
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    예:
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    여기서 SQL \<Server\> 의 fqdn은 Enterprise Edition 배포의 Lync Server 2010 백 엔드 서버 또는 STANDARD edition Server의 fqdn 중 하나입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

