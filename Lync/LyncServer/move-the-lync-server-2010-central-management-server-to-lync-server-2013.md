---
title: Lync Server 2010 중앙 관리 서버를 Lync Server 2013로 이동
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
ms.openlocfilehash: 5f301c8f6e11ca3c8f19ed167489bb3fbf51fc63
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-the-lync-server-2010-central-management-server-to-lync-server-2013"></a>Lync Server 2010 중앙 관리 서버를 Lync Server 2013로 이동

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-25_

Lync Server 2010에서 Lync Server 2013으로 마이그레이션한 후에는 lync server 2010 중앙 관리 서버를 Lync Server 2013 프런트 엔드 서버 또는 풀로 이동 해야 레거시 Lync Server 2010 서버를 제거할 수 있습니다.

중앙 관리 서버는 중앙 관리 서버를 포함 하는 프런트 엔드 서버에서 데이터베이스의 읽기/쓰기 복사본을 보유 하 고 있는 단일 마스터/다중 복제 시스템입니다. 중앙 관리 서버를 포함 하는 프런트 엔드 서버를 포함 하 여 토폴로지의 각 컴퓨터에는 설치 하는 동안 컴퓨터에 설치 된 SQL Server 데이터베이스 (기본적으로 RTCLOCAL 이라는)의 중앙 관리 저장소 데이터에 대 한 읽기 전용 복사본이 있습니다. 배포가. 로컬 데이터베이스는 모든 컴퓨터에서 서비스로 실행 되는 Lync Server 복제본 복제기 에이전트를 통해 복제본 업데이트를 받습니다. 중앙 관리 서버 및 로컬 복제본의 실제 데이터베이스 이름은 xds, xds .mdf 파일로 구성 되는 XDS입니다. Active Directory 도메인 서비스의 SCP (서비스 제어 지점)에서 마스터 데이터베이스 위치를 참조 합니다. 중앙 관리 서버를 사용 하 여 Lync Server를 관리 하 고 구성 하는 모든 도구는 SCP를 사용 하 여 중앙 관리 저장소를 찾습니다.

중앙 관리 서버를 성공적으로 이동한 후에는 원래 프런트 엔드 서버에서 중앙 관리 서버 데이터베이스를 제거 해야 합니다. 중앙 관리 서버 데이터베이스를 제거 하는 방법에 대 한 자세한 내용은 [프런트 엔드 풀의 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-a-front-end-pool.md)를 참조 하세요.

Lync server 관리 셸에서 Windows PowerShell cmdlet **CsManagementServer** 을 사용 하 여 lync SERVER 2010 sql server 데이터베이스에서 lync SERVER 2013 sql server 데이터베이스로 데이터베이스를 이동한 다음 lync Server 2013 중앙 관리 서버 위치를 가리키도록 SCP를 업데이트 합니다.

<div>

## <a name="preparing-lync-server-2013front-end-servers-before-moving-the-central-management-server"></a>중앙 관리 서버를 이동 하기 전에 Lync Server 2013 프런트 엔드 서버 준비

Lync server 2010 중앙 관리 서버를 이동 하기 전에이 섹션의 절차를 사용 하 여 Lync Server 2013 프런트 엔드 서버를 준비 합니다.

<div>

## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Enterprise Edition 프런트 엔드 풀을 준비 하려면

1.  중앙 관리 서버를 재배치할 Lync Server 2013 Enterprise Edition 프런트 엔드 풀에서 Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다. 또한 중앙 관리 저장소를 설치 하려는 데이터베이스에 대 한 SQL Server 데이터베이스 sysadmin 사용자 권한 및 사용 권한도 있어야 합니다.

2.  Lync Server 관리 셸을 엽니다.

3.  Lync server 2013 SQL Server 데이터베이스에서 새 중앙 관리 저장소를 만들려면 Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>

4.  **Lync Server 프런트 엔드** 서비스의 상태가 **시작**되었는지 확인 합니다.

</div>

<div>

## <a name="to-prepare-a-standard-edition-front-end-server"></a>Standard Edition 프런트 엔드 서버를 준비 하려면

1.  중앙 관리 서버를 재배치할 Lync Server 2013 Standard Edition 프런트 엔드 서버: Lync Server 관리 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다.

2.  Lync 서버 배포 마법사를 엽니다.

3.  Lync Server 배포 마법사에서 **첫 번째 Standard Edition Server 준비**를 클릭 합니다.

4.  **명령 실행** 페이지에서 SQL Server Express가 중앙 관리 서버로 설치 됩니다. 필요한 방화벽 규칙이 생성 됩니다. 데이터베이스 설치 및 필수 소프트웨어 소프트웨어가 완료 되 면 **마침을**클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > 초기 설치에는 명령 출력 요약 화면에 표시 되는 업데이트 없이 시간이 걸릴 수 있습니다. 이는 SQL Server Express의 설치 때문입니다. 데이터베이스 설치를 모니터링 해야 하는 경우 작업 관리자를 사용 하 여 설정을 모니터링 합니다.

    
    </div>

5.  Lync server 2013 Standard Edition 프런트 엔드 서버에서 새 중앙 관리 저장소를 만들려면 Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>

6.  **Lync Server 프런트 엔드** 서비스의 상태가 **시작**되었는지 확인 합니다.

</div>

</div>

<div>

## <a name="to-move-the-lync-server-2010central-management-server-to-lync-server-2013"></a>Lync Server 2010 중앙 관리 서버를 Lync Server 2013로 이동 하려면

1.  중앙 관리 서버가 되는 Lync Server 2013 서버에서 Lync Server Management 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다. 또한 SQL Server 데이터베이스 관리자의 사용자 권한 및 권한도 있어야 합니다.

2.  Lync Server Management Shell을 엽니다.

3.  Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Enable-CsTopology
    
    <div>
    

    > [!WARNING]  
    > 이 <CODE>Enable-CsTopology</CODE> 실패할 경우, 계속 하기 전에 명령이 완료 되지 않도록 하는 문제를 해결 합니다. <STRONG>Enable-CsTopology</STRONG> 가 실패 하면 이동이 실패 하 고 중앙 관리 저장소가 없는 상태로 토폴로지가 유지 될 수 있습니다.

    
    </div>

4.  Lync server 2013 프런트 엔드 서버 또는 프런트 엔드 풀의 Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Move-CsManagementServer

5.  Lync Server 관리 셸에서는 서버, 파일 저장소, 데이터베이스 저장소, 현재 상태의 서비스 연결 지점 및 제안 된 상태를 표시 합니다. 이 정보를 주의깊게 읽고이 대상이 의도 한 원본 및 대상 인지 확인 합니다. 계속 하려면 **Y** 를 입력 하 고, 이동을 중지 하려면 **N을 누르십시오** .

6.  **이동-CsManagementServer** 명령으로 생성 된 경고나 오류를 검토 하 고이를 해결 합니다.

7.  Lync Server 2013 서버에서 Lync Server 배포 마법사를 엽니다.

8.  Lync Server 배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 하 고 **2 단계: Lync Server 구성 요소 설정 또는 제거**에서 **다음**을 클릭 하 고 요약을 검토 한 다음 **마침을**클릭 합니다.

9.  Lync Server 2010 서버에서 Lync Server 배포 마법사를 엽니다.

10. Lync Server 배포 마법사에서 **Lync Server 시스템 설치 또는 업데이트**를 클릭 하 고 **2 단계: Lync Server 구성 요소 설정 또는 제거**에서 **다음**을 클릭 하 고 요약을 검토 한 다음 **마침을**클릭 합니다.

11. Lync Server 2013 서버를 다시 부팅 합니다. 이는 그룹 구성원 자격이 access 중앙 관리 서버 데이터베이스로 변경 되었기 때문에 필요 합니다.

12. 새 중앙 관리 저장소와의 복제가 진행 중인지 확인 하려면 Lync Server 관리 셸에서 다음을 입력 합니다.
    
        Get-CsManagementStoreReplicationStatus
    
    <div>
    

    > [!NOTE]  
    > 복제는 현재 모든 복제본을 업데이트 하는 데 시간이 걸릴 수 있습니다.

    
    </div>

</div>

<div>

## <a name="to-remove-lync-server-2010central-management-store-files-after-a-move"></a>이동 후 Lync Server 2010 중앙 관리 저장소 파일을 제거 하려면

1.  Lync Server 2010 서버: Lync Server Management 셸이 **RTCUniversalServerAdmins** 그룹의 구성원으로 설치 된 컴퓨터에 로그온 합니다. 또한 SQL Server 데이터베이스 관리자의 사용자 권한 및 권한도 있어야 합니다.

2.  Lync Server 관리 셸 열기
    
    <div>
    

    > [!WARNING]  
    > 복제가 완료 되 고 안정적이 지 않아도 이전 데이터베이스 파일을 제거 하는 것을 진행 하지 마세요. 복제를 완료 하기 전에 파일을 제거 하면 복제 프로세스가 중단 되 고 새로 이동한 중앙 관리 서버가 알 수 없는 상태로 유지 됩니다. Cmdlet <STRONG>Get-CsManagementStoreReplicationStatus</STRONG> 을 사용 하 여 복제 상태를 확인 합니다.

    
    </div>

3.  Lync Server 2010 중앙 관리 서버에서 중앙 관리 저장소 데이터베이스 파일을 제거 하려면 다음을 입력 합니다.
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
    
    예를 들면 다음과 같습니다.
    
        Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
    
    여기서 SQL \<Server\> 의 fqdn은 엔터프라이즈 버전 배포의 Lync Server 2010 백 엔드 서버 이거나 STANDARD edition Server의 fqdn입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

