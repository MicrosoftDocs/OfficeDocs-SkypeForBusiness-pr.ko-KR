---
title: 미러된 Enterprise Edition 백 엔드 서버 복원-기본
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a mirrored Enterprise Edition Back End Server - primary
ms:assetid: bc555b46-70c5-4eee-ae91-e195df238293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945648(v=OCS.15)
ms:contentKeyID: 51541512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbf0c8562ed4180fb14bf0bda74a03dd4ee8f746
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976208"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-mirrored-enterprise-edition-back-end-server-in-lync-server-2013---primary"></a>Lync Server 2013에서 미러된 Enterprise Edition 백 엔드 서버 복원-기본

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-17_

미러된 구성에 Enterprise Edition 백 엔드 서버가 있고 주 데이터베이스에만 오류가 있는 경우이 섹션의 절차를 따르세요. 주 데이터베이스와 미러 서버 모두에 오류가 발생 하는 경우 [에는 Lync server 2013에서 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)참조 하세요. 미러만 실패 하는 경우 [Lync server 2013-미러에서 미러된 Enterprise Edition 백 엔드 서버 복원을](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md)참조 하세요. 중앙 관리 저장소를 호스팅하는 데이터베이스에 오류가 발생 하는 경우 [Lync server 2013에서 중앙 관리 저장소를 호스팅하는 서버 복원을](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)참조 하세요. 백 엔드 서버가 아닌 Enterprise Edition 구성원 서버가 실패 하는 경우 [Lync server 2013에서 Enterprise edition 구성원 서버 복원을](lync-server-2013-restoring-an-enterprise-edition-member-server.md)참조 하세요.

복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다. 복원 중에 문제가 발생 하는 경우이 이미지를 롤백 시점으로 사용할 수 있습니다. 운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 이미지 복사본을 사용할 수 있습니다.

이 항목의 예제 기본 데이터베이스는 BE1.contoso.com의 FQDN (정규화 된 도메인 이름)을 사용 하 고 미러 데이터베이스의 FQDN은 BE2.contoso.com입니다.

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server-primary-database"></a>Enterprise Edition 백 엔드 서버 기본 데이터베이스를 복원 하려면

1.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **lync server management shell**을 클릭 합니다.

3.  구성 된 모든 데이터베이스를 강제로 미러에서 장애 조치 합니다. 이 서버에 구성한 각 데이터베이스 유형에 대해 다음 cmdlet을 입력 합니다.
    
        Invoke-CsDataBaseFailover -PoolFqdn <Pool FQDN> -DatabaseType <Configured Database Type> -NewPrincipal Mirror -Force -Verbose
    
    예를 들면 다음과 같습니다.
    
        Invoke-CsDataBaseFailover -PoolFqdn pool0.vdomain.com -DatabaseType User -NewPrincipal Mirror -Force -Verbose
    
    <div>
    

    > [!WARNING]
    > 미러링 모니터 서버와 동기화 된 미러링을 사용 하도록 백 엔드 데이터베이스를 구성한 경우 장애 조치는 자동으로 진행 됩니다.

    
    </div>

4.  장애 조치 (failover)를 완료 한 후 다음을 수행 합니다.
    
      - 토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.
    
      - 백 엔드 서버의 미러링 사용 안 함: **Enterprise Edition 프런트 엔드 풀** 에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다. **일반** 탭의 **연결**에서 **SQL Server 스토어 미러링 사용** 확인란의 선택을 취소 합니다. 필요에 따라 보관 및 모니터링에이 작업을 수행 합니다. 그런 다음 **확인을**클릭 합니다.
    
      - Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.
    
      - 계속 해 서 작동 하는 백 엔드 (BE2.contoso.com)를 새 SQL 저장소로 선택 합니다. 이렇게 하려면 **Enterprise Edition 프런트 엔드 풀** 에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다. **일반** 탭의 **연결**에서 **SQL Server store** 필드에 작동 하는 백 엔드의 FQDN (이 예제에서는 BE2.contoso.com)을 입력 합니다.
    
      - Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **게시**를 클릭 합니다.
    
      - 각 서버가 새 토폴로지를 읽을 수 있도록 서비스를 다시 시작 합니다. Lync Server Management 셸에서이 풀에 속하는 각 프런트 엔드 서버에서 다음 cmdlet을 실행 합니다.
        
            Stop-CsWindowsService
            Start-CsWindowsService

5.  미러링 제거. Lync Server Management Shell에서 다음 cmdlet을 실행 합니다.
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn <MirrorServerFqdn> -SqlInstanceName <SQLInstance> -verbose
    
    예를 들면 다음과 같습니다.
    
        Uninstall-CsMirrorDatabase -DatabaseType User -SqlServerFqdn DB2.contoso.com -SqlInstanceName rtc -verbose
    
    이 서버의 모든 데이터베이스 유형에 대해이 작업을 수행 합니다.

6.  실패 한 컴퓨터와 동일한 FQDN (이 예제에서는 DB1.contoso.com)을가지고 있는 새 서버를 만들거나, 운영 체제를 설치한 다음, 인증서를 복원 하거나 reenroll. 이 서버는 새 미러에서 작동 합니다.

7.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 새 서버에 로그온 합니다.

8.  SQL Server 2012 또는 SQL Server 2008 R2를 설치 하 고 인스턴스 이름을 오류 전과 동일 하 게 유지 합니다.

9.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 프런트 엔드 서버에 로그온 합니다.

10. 토폴로지 작성기를 사용 하 여 미러 DB를 설치 합니다. 다음 단계를 수행 합니다.
    
      - 토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.
    
      - 백 엔드 서버에서 미러링을 사용 하도록 설정 합니다. 이렇게 하려면 **Enterprise Edition 프런트 엔드 풀** 에서 풀을 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 선택 합니다. **일반** 탭의 **연결**에서 **SQL Server 스토어 미러링 사용** 확인란을 선택 합니다. 필요에 따라 보관 및 모니터링에도이 작업을 수행 합니다.
        
        그런 다음 **SQL server 저장소 미러링** 필드에 새 서버의 FQDN을 입력 합니다 (이 예에서는 BE1.contoso.com). 그런 다음 **확인을**클릭 합니다.
    
      - Lync Server 2013 노드를 마우스 오른쪽 단추로 클릭 하 고 **토폴로지**를 클릭 한 다음 **데이터베이스 설치**를 클릭 합니다.
    
      - **데이터베이스 설치** 마법사를 따릅니다. **데이터베이스 만들기** 페이지에서 다시 만들려는 데이터베이스를 선택 합니다.
    
      - 메시지가 나타날 때까지 마법사의 지시에 따라 **미러 데이터베이스를 만듭니다**. 설치 하려는 데이터베이스를 선택 하 고이 프로세스를 완료 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

