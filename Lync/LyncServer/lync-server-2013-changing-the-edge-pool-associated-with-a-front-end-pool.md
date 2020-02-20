---
title: 'Lync Server 2013: 프런트 엔드 풀과 연결 된에 지 풀 변경'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eeee8715996d5242cf61964b397af23886b5a31f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150997"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="373f3-102">Lync Server 2013의 프런트 엔드 풀과 연결 된에 지 풀 변경</span><span class="sxs-lookup"><span data-stu-id="373f3-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="373f3-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="373f3-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="373f3-104">에지 풀이 다운되었는데 동일 사이트의 프런트 엔드 풀은 계속 실행되는 경우에는 오류가 발생한 에지 풀을 복원하는 동안 다른 사이트의 에지 풀을 사용하도록 프런트 엔드 풀을 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="373f3-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="373f3-105">프런트 엔드 풀과 연결된 에지 풀 변경</span><span class="sxs-lookup"><span data-stu-id="373f3-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="373f3-106">토폴로지 작성기에서 변경해야 하는 프런트 엔드 풀의 이름을 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="373f3-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="373f3-107">풀을 마우스 오른쪽 단추로 클릭한 다음 **속성 편집**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="373f3-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="373f3-108">**연결** 섹션의 **에지 풀 연결(미디어 구성 요소)** 에서 드롭다운 상자를 사용하여 이 프런트 엔드 풀과 연결할 에지 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="373f3-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="373f3-109">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="373f3-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="373f3-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="373f3-110">See Also</span></span>


[<span data-ttu-id="373f3-111">Lync Server 2013의에 지 서버 재해 복구</span><span class="sxs-lookup"><span data-stu-id="373f3-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

