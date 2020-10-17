---
title: 'Lync Server 2013: 풀 장애 복구 (failback)'
description: 'Lync Server 2013: 풀 장애 복구 (failback)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back a pool
ms:assetid: 6232b644-ef57-4c9c-abec-14ff8ffc9fe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204945(v=OCS.15)
ms:contentKeyID: 48184289
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1c1fc0ea4514d2f951dd936521590d47b809db38
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567744"
---
# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="ad64e-103">Lync Server 2013에서 풀 장애 복구 (failback)</span><span class="sxs-lookup"><span data-stu-id="ad64e-103">Failing back a pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad64e-104">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ad64e-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ad64e-105">재해가 발생한 풀을 다시 온라인으로 전환한 후(이 예의 Pool1) 다음 단계에 따라 배포를 일반 작업 상태로 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="ad64e-105">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="ad64e-p101">복구(Failback) 프로세스는 완료하는 데 몇 분 정도 걸립니다. 일반적으로 사용자가 20,000명인 풀을 복구하는 데에는 최대 60분 정도 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad64e-p101">Note that the failback process takes several minute to complete.  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="ad64e-108">다음 cmdlet을 사용해서 원래 Pool1에 있다가 Pool2로 장애 조치(Failover)되었던 사용자를 복구(Failback)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad64e-108">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="ad64e-109">다른 단계는 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ad64e-109">No other steps are necessary.</span></span> <span data-ttu-id="ad64e-110">중앙 관리 서버를 장애 조치 (failover) 한 경우에는 호스트인에 그대로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad64e-110">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

