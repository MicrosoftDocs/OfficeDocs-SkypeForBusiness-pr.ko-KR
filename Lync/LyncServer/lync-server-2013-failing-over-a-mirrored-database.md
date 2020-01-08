---
title: 'Lync Server 2013: 미러된 데이터베이스 장애 조치(failover)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a943705f13cff4f015285b1ef74feb11dc540091
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978922"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Lync Server 2013에서 미러된 데이터베이스 장애 조치(failover)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-03-14_

미러링 모니터 서버와 동기화 된 미러링을 사용 하도록 백 엔드 데이터베이스를 구성한 경우 장애 조치는 자동으로 진행 됩니다. 미러링 모니터 서버 없이 동기화 된 미러링을 구성한 경우 다음 절차를 사용 하 여 데이터베이스의 장애 조치 및 복구를 수행할 수 있습니다. 또한 미러링 모니터 서버를 구성 하는 경우에도 이러한 절차를 사용 하 여 데이터베이스의 장애 조치 및 장애 복구를 수동으로 수행할 수 있습니다.

<div>

## <a name="to-fail-over-your-back-end-database"></a>백 엔드 데이터베이스를 장애 조치 하려면

1.  장애 조치를 수행 하기 전에 다음 cmdlet을 입력 하 여 기본으로 사용할 백 엔드 데이터베이스와 미러를 결정 합니다.
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  중앙 관리 저장소가이 풀에서 호스트 되는 경우 다음 cmdlet을 입력 하 여 중앙 관리 저장소의 미러에 사용할 미러 서버를 결정 합니다.
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  사용자 데이터베이스의 장애 조치를 수행 합니다.
    
      - 주에 실패 하 여 미러에서 장애 조치를 수행 하는 경우 다음을 입력 합니다.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - 미러가 실패 하 고 주 서버로 장애 조치 되는 경우 다음을 입력 합니다.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  풀이 중앙 관리 서버를 호스트 하는 경우 중앙 관리 저장소의 장애 조치를 수행 합니다.
    
      - 주에 실패 하 여 미러에서 장애 조치를 수행 하는 경우 다음을 입력 합니다.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - 미러가 실패 하 고 주 서버로 장애 조치 되는 경우 다음을 입력 합니다.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

