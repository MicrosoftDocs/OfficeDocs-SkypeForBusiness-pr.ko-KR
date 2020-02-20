---
title: 미러된 Enterprise Edition 백 엔드 서버 복원-기본
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6dfc3f9a44adbd4967e3d32ac7a515a55bc5d974
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-기본

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-17_

미러된 구성에 Enterprise Edition 백 엔드 서버가 있고 주 데이터베이스만 오류가 발생 하는 경우이 섹션의 절차를 따르세요. 주 데이터베이스와 미러 서버에 모두 오류가 발생 하면 [Lync server 2013에서 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)참조 하세요. 미러만 실패 하는 경우 [Lync server 2013-mirror에서 미러된 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)참조 하세요. 중앙 관리 저장소를 호스트 하는 데이터베이스가 실패 하면 [Lync server 2013에서 중앙 관리 저장소를 호스트 하는 서버 복원을](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)참조 하세요. 백 엔드 서버가 아닌 Enterprise Edition 구성원 서버가 실패 하면 [Lync server 2013에서 Enterprise edition 구성원 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-member-server.md)참조 하십시오.

복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다. 복원 중에 문제가 발생 하는 경우를 대비 하 여이 이미지를 롤백 지점으로 사용할 수 있습니다. 운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 후 이미지 복사본을 사용할 수 있습니다.

이 항목에서는 기본 데이터베이스 예제에 BE1.contoso.com의 FQDN (정규화 된 도메인 이름)이 있고 미러 데이터베이스에는 BE2.contoso.com의 FQDN이 있습니다.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>Enterprise Edition 백 엔드 서버 기본 데이터베이스를 복원 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.

2.  **시작**, **모든 프로그램**, **Microsoft Lync Server 2013** 및 **Communications Server 관리 셸**을 차례로 클릭하여 Communications Server 관리 셸을 시작합니다.

3.  구성 된 모든 데이터베이스를 강제로 미러 서버로 장애 조치 (failover) 합니다. 이 서버에 구성한 각 데이터베이스 유형에 대해 다음 cmdlet을 입력 합니다.
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    예:
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > 미러링 모니터 서버와 동기화된 미러링을 사용하도록 백 엔드 데이터베이스를 구성한 경우 장애 조치(Failover)가 자동으로 수행됩니다.

    
    </div>

4.  장애 조치 (failover)를 완료 한 후 다음을 수행 합니다.
    
      - 토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.
    
      - 백 엔드 서버에서 미러링 사용 안 함: **Enterprise Edition 프런트 엔드 풀** 아래에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다. **일반** 탭의 **연결**에서 **SQL Server 저장소 미러링 사용** 확인란의 선택을 취소 합니다. 필요에 따라 보관 및 모니터링을 위해이 작업을 수행 합니다. 그런 다음 **확인**을 클릭합니다.
    
      - Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.
    
      - BE2.contoso.com (계속 작동 하는 백엔드)를 새 SQL 저장소로 선택 합니다. 이 작업을 수행 하려면 **Enterprise Edition 프런트 엔드 풀** 아래의 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다. **일반** 탭의 **연결**에서 **SQL Server 저장소** 필드에 작동 하는 백 엔드의 FQDN (예: BE2.contoso.com)을 입력 합니다.
    
      - Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.
    
      - 서비스를 다시 시작 하 여 각 서버에서 새 토폴로지를 읽을 수 있도록 합니다. Lync Server 관리 셸에서이 풀에 속하는 각 프런트 엔드 서버에서 다음 cmdlet을 실행 합니다.
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  미러링을 제거 합니다. Lync Server 관리 셸에서 다음 cmdlet을 실행 합니다.
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    예:
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    이 서버의 모든 데이터베이스 유형에 대해이 작업을 수행 합니다.

6.  오류가 발생 한 컴퓨터와 동일한 FQDN (이 예제에서는 DB1.contoso.com)을 가진 깨끗 한 서버나 새 서버를 만들고, 운영 체제를 설치한 후 인증서를 복원 하거나 reenroll 합니다. 이 서버는 새 미러에서 작동 합니다.

7.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 새 서버에 로그온 합니다.

8.  SQL Server 2012 또는 SQL Server 2008 r 2를 설치 하 고 인스턴스 이름을 오류 이전과 동일 하 게 유지 합니다.

9.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.

10. 토폴로지 작성기를 사용 하 여 미러 DB를 설치 합니다. 다음 단계를 수행하십시오.
    
      - 토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.
    
      - 백 엔드 서버에서 미러링을 사용 하도록 설정 합니다. 이 작업을 수행 하려면 **Enterprise Edition 프런트 엔드 풀** 아래의 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다. **일반** 탭의 **연결**에서 **SQL Server 저장소 미러링 사용** 확인란을 선택 합니다. 필요한 경우 보관 및 모니터링에도이 작업을 수행 합니다.
        
        그런 다음 **SQL server 저장소 미러링** 필드에 새 서버의 FQDN (이 예에서는 BE1.contoso.com)을 입력 합니다. 그런 다음 **확인**을 클릭합니다.
    
      - Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **데이터베이스 설치**를 클릭 합니다.
    
      - **데이터베이스 설치** 마법사를 따릅니다. **데이터베이스 만들기** 페이지에서 다시 만들 데이터베이스를 선택 합니다.
    
      - 메시지가 표시 될 때까지 마법사의 지시에 따라 **미러 데이터베이스를 만듭니다**. 설치 하려는 데이터베이스를 선택 하 고이 프로세스를 완료 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

