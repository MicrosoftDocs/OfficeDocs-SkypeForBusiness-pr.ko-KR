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
ms.openlocfilehash: 853dfdd6786b4e30513cb57be219edff8d8c1b9b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530975"
---
# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="78807-102">Lync Server 2013에서 미러된 데이터베이스 장애 조치 (failover)</span><span class="sxs-lookup"><span data-stu-id="78807-102">Failing over a mirrored database in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78807-103">_**마지막으로 수정 된 항목:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="78807-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="78807-p101">미러링 모니터 서버와 동기화된 미러링을 사용하도록 백 엔드 데이터베이스를 구성한 경우 장애 조치(Failover)가 자동으로 수행됩니다. 미러링 모니터 서버 없이 동기화된 미러링을 구성한 경우 다음 절차에 따라 데이터베이스를 장애 조치(failover) 및 복구(failback)할 수 있습니다. 또한 미러링 모니터 서버를 구성한 경우에도 이러한 절차에 따라 데이터베이스를 수동으로 장애 조치(failover) 및 복구(failover)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78807-p101">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic. If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database. You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="78807-107">백 엔드 데이터베이스를 장애 조치(failover)하려면</span><span class="sxs-lookup"><span data-stu-id="78807-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="78807-108">장애 조치(failover)를 수행하기 전에 다음 cmdlet을 입력하여 백 엔드 데이터베이스 중 기본 데이터베이스와 미러 데이터베이스를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="78807-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="78807-109">중앙 관리 저장소를이 풀에서 호스트 하는 경우 다음 cmdlet을 입력 하 여 중앙 관리 저장소에 대 한 미러 인 사용자를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="78807-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="78807-110">사용자 데이터베이스의 장애 조치(failover)를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="78807-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="78807-111">기본 데이터베이스가 실패하여 미러로 장애 조치(failover)하는 경우 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="78807-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="78807-112">미러 데이터베이스가 실패하여 기본 데이터베이스로 장애 조치(failover)하는 경우 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="78807-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="78807-113">풀이 중앙 관리 서버를 호스트 하는 경우 중앙 관리 저장소의 장애 조치 (failover)를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="78807-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="78807-114">기본 데이터베이스가 실패하여 미러로 장애 조치(failover)하는 경우 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="78807-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="78807-115">미러 데이터베이스가 실패하여 기본 데이터베이스로 장애 조치(failover)하는 경우 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="78807-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

