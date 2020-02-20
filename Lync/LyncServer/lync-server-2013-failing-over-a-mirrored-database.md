---
title: 'Lync Server 2013: 미러된 데이터베이스 장애 조치 (Failover)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a02b82757f3754bd792e18f89f9133a764dc3341
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145877"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Lync Server 2013에서 미러된 데이터베이스 장애 조치 (failover)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-03-14_

미러링 모니터 서버와 동기화된 미러링을 사용하도록 백 엔드 데이터베이스를 구성한 경우 장애 조치(Failover)가 자동으로 수행됩니다. 미러링 모니터 서버 없이 동기화된 미러링을 구성한 경우 다음 절차에 따라 데이터베이스를 장애 조치(failover) 및 복구(failback)할 수 있습니다. 또한 미러링 모니터 서버를 구성한 경우에도 이러한 절차에 따라 데이터베이스를 수동으로 장애 조치(failover) 및 복구(failover)할 수 있습니다.

<div>

## <a name="to-fail-over-your-back-end-database"></a>백 엔드 데이터베이스를 장애 조치(failover)하려면

1.  장애 조치(failover)를 수행하기 전에 다음 cmdlet을 입력하여 백 엔드 데이터베이스 중 기본 데이터베이스와 미러 데이터베이스를 확인합니다.
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  중앙 관리 저장소를이 풀에서 호스트 하는 경우 다음 cmdlet을 입력 하 여 중앙 관리 저장소에 대 한 미러 인 사용자를 확인 합니다.
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  사용자 데이터베이스의 장애 조치(failover)를 수행합니다.
    
      - 기본 데이터베이스가 실패하여 미러로 장애 조치(failover)하는 경우 다음을 입력합니다.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - 미러 데이터베이스가 실패하여 기본 데이터베이스로 장애 조치(failover)하는 경우 다음을 입력합니다.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  풀이 중앙 관리 서버를 호스트 하는 경우 중앙 관리 저장소의 장애 조치 (failover)를 수행 합니다.
    
      - 기본 데이터베이스가 실패하여 미러로 장애 조치(failover)하는 경우 다음을 입력합니다.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - 미러 데이터베이스가 실패하여 기본 데이터베이스로 장애 조치(failover)하는 경우 다음을 입력합니다.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

