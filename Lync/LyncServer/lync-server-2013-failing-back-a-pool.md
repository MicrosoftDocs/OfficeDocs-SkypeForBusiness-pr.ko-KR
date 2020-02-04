---
title: 'Lync Server 2013: 풀 장애 복구(failback)'
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
ms.openlocfilehash: 91e1dca7ffc210e9b44913f21846726f7a776912
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-a-pool-in-lync-server-2013"></a><span data-ttu-id="2fbd4-102">Lync Server 2013에서 풀 장애 복구(failback)</span><span class="sxs-lookup"><span data-stu-id="2fbd4-102">Failing back a pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2fbd4-103">_**마지막으로 수정한 주제:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2fbd4-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2fbd4-104">재해가 발생 한 풀이 온라인 상태가 된 후 (즉,이 예제에서 Pool1) 다음 단계를 수행 하 여 배포를 정상 작업 상태로 복원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbd4-104">After the pool that experienced the disaster is back online (that is, Pool1 in this example), take the following steps to restore your deployment to regular working status.</span></span>

<span data-ttu-id="2fbd4-105">장애 복구 프로세스가 완료 되기까지 몇 분이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fbd4-105">Note that the failback process takes several minute to complete.</span></span><span data-ttu-id="2fbd4-106">참조용으로 2만 사용자 풀에 대해 최대 60 분이 소요 될 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fbd4-106">  For reference, it is expected to take up to 60 minutes for a pool of 20,000 users.</span></span>

1.  <span data-ttu-id="2fbd4-107">Pool1에서 원래 홈 이었던 사용자와 다음 cmdlet을 입력 하 여 Pool2에 장애 조치 (Fail over)를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fbd4-107">Fail back the users who were originally homed in Pool1 and have been failed over to Pool2 by typing the following cmdlet:</span></span>
    
        Invoke-CsPoolFailback -PoolFQDN <Pool1 FQDN> -Verbose

<span data-ttu-id="2fbd4-108">다른 단계는 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2fbd4-108">No other steps are necessary.</span></span> <span data-ttu-id="2fbd4-109">중앙 관리 서버를 장애 조치 (Pool2) 한 경우에는 그대로 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fbd4-109">If you failed over the Central Management Server, you can leave it in Pool2.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

