---
title: 'Lync Server 2013: 미러된 데이터베이스 장애 조치(failover)'
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
ms.openlocfilehash: 822a7a2fa13ce444bbaf590ee0d8ba2144debcc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a><span data-ttu-id="3c312-102">Lync Server 2013에서 미러된 데이터베이스 장애 조치(failover)</span><span class="sxs-lookup"><span data-stu-id="3c312-102">Failing over a mirrored database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c312-103">_**마지막으로 수정한 주제:** 2014-03-14_</span><span class="sxs-lookup"><span data-stu-id="3c312-103">_**Topic Last Modified:** 2014-03-14_</span></span>

<span data-ttu-id="3c312-104">미러링 모니터 서버와 동기화 된 미러링을 사용 하도록 백 엔드 데이터베이스를 구성한 경우 장애 조치는 자동으로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c312-104">If you have configured your back-end database to use synchronized mirroring with a witness, failover is automatic.</span></span> <span data-ttu-id="3c312-105">미러링 모니터 서버 없이 동기화 된 미러링을 구성한 경우 다음 절차를 사용 하 여 데이터베이스의 장애 조치 및 복구를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c312-105">If you have configured synchronized mirroring without a witness, you can use the following procedures to failover and failback your database.</span></span> <span data-ttu-id="3c312-106">또한 미러링 모니터 서버를 구성 하는 경우에도 이러한 절차를 사용 하 여 데이터베이스의 장애 조치 및 장애 복구를 수동으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c312-106">You can also use these procedures to manually failover and failback your databases even if you have configured a witness.</span></span>

<div>

## <a name="to-fail-over-your-back-end-database"></a><span data-ttu-id="3c312-107">백 엔드 데이터베이스를 장애 조치 하려면</span><span class="sxs-lookup"><span data-stu-id="3c312-107">To fail over your back-end database</span></span>

1.  <span data-ttu-id="3c312-108">장애 조치를 수행 하기 전에 다음 cmdlet을 입력 하 여 기본으로 사용할 백 엔드 데이터베이스와 미러를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c312-108">Before failing over, determine which back-end database is the principal and which is the mirror by typing the following cmdlet:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  <span data-ttu-id="3c312-109">중앙 관리 저장소가이 풀에서 호스트 되는 경우 다음 cmdlet을 입력 하 여 중앙 관리 저장소의 미러에 사용할 미러 서버를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c312-109">If the Central Management store is hosted in this pool, type the following cmdlet to determine which is the principal and which is the mirror for the Central Management store:</span></span>
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  <span data-ttu-id="3c312-110">사용자 데이터베이스의 장애 조치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c312-110">Perform the failover of the user database:</span></span>
    
      - <span data-ttu-id="3c312-111">주에 실패 하 여 미러에서 장애 조치를 수행 하는 경우 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c312-111">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="3c312-112">미러가 실패 하 고 주 서버로 장애 조치 되는 경우 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c312-112">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  <span data-ttu-id="3c312-113">풀이 중앙 관리 서버를 호스트 하는 경우 중앙 관리 저장소의 장애 조치를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c312-113">If the pool hosts the Central Management Server, perform the failover of the Central Management store.</span></span>
    
      - <span data-ttu-id="3c312-114">주에 실패 하 여 미러에서 장애 조치를 수행 하는 경우 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c312-114">If the primary has failed and you are failing over to the mirror, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - <span data-ttu-id="3c312-115">미러가 실패 하 고 주 서버로 장애 조치 되는 경우 다음을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c312-115">If the mirror has failed and you are failing over to the primary, type:</span></span>
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

