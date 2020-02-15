---
title: 여러 사이트 및 풀 마이그레이션
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52e14cccb9856534ea9b7229fd020edc2ec21dba
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a><span data-ttu-id="59077-102">여러 사이트 및 풀 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="59077-102">Migrating multiple sites and pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59077-103">_**마지막으로 수정 된 항목:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="59077-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="59077-104">Lync Server 2013에서는 다중 사이트 및 다중 풀 배포를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="59077-104">Lync Server 2013 supports multi-site and multi-pool deployments.</span></span> <span data-ttu-id="59077-105">Lync Server 2010에서 Lync Server 2013로 여러 풀을 마이그레이션하는 프로세스를 수행 하려면 다음 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59077-105">The process of migrating multiple pools from Lync Server 2010 to Lync Server 2013 requires the following considerations:</span></span>

1.  <span data-ttu-id="59077-106">Lync Server 2013 파일럿 풀을 배포한 후에는 Lync Server 2013 풀로 이동할 파일럿 사용자의 하위 집합 및 사용자 기능의 유효성 검사 방법론을 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59077-106">After deploying a Lync Server 2013 pilot pool, you need to define a subset of pilot users that will be moved to the Lync Server 2013 pool, and a methodology for validating the functionality of the users.</span></span> <span data-ttu-id="59077-107">예를 들어 파일럿 풀로 사용자를 이동한 후에는 사용자의 회의 정책이 Lync Server 2013으로 이동 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="59077-107">For example, after moving a user to the pilot pool, verify the user’s conference policy has moved to Lync Server 2013.</span></span>

2.  <span data-ttu-id="59077-108">파일럿 풀에에 지 서버를 배포한 후에는 외부 사용자가 Lync Server 2013 풀과 통신할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59077-108">After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Lync Server 2013 pool.</span></span>

3.  <span data-ttu-id="59077-109">Lync Server 2010에 지 서버에서 파일럿 Lync Server 2013에 지 서버로 연결 된 경로를 전환 하 고 나면 페더레이션 사용자가 Lync Server 2013 풀과 통신할 수 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59077-109">After transitioning the federated routes from Lync Server 2010 Edge Servers to the pilot Lync Server 2013 Edge Servers, you need to validate that federated users can communicate with the Lync Server 2013 pool.</span></span>

4.  <span data-ttu-id="59077-110">모든 사용자와 사용자가 아닌 대화 상대 개체를 이동한 후에는 Lync Server 2010 풀이 비어 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59077-110">After moving all the users and non-user contact objects, you need to validate that the Lync Server 2010 pool is empty.</span></span>

5.  <span data-ttu-id="59077-111">Lync Server 2010 풀이 비어 있는지 확인 한 후에는 해당 풀을 비활성화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59077-111">After verifying that the Lync Server 2010 pool is empty, you can then deactivate the pool.</span></span>
    
    <span data-ttu-id="59077-112">레거시 Lync Server 2010 풀 및 서버를 비활성화 하는 방법에 대 한 자세한 내용은 [Phase 8: 레거시 풀](phase-8-decommission-legacy-pools.md)해제를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="59077-112">For details about how to deactivate the legacy Lync Server 2010 pool and servers, see [Phase 8: Decommission legacy pools](phase-8-decommission-legacy-pools.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

