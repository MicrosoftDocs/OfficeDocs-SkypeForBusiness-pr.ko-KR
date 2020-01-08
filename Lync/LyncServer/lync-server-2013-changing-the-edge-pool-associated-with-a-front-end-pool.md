---
title: 'Lync Server 2013: 프런트 엔드 풀과 연결된 에지 풀 변경'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0bbb2e6ffdaa238dcbd4a184c8db890c26dd6340
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978705"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="f9092-102">Lync Server 2013에서 프런트 엔드 풀과 연결된 에지 풀 변경</span><span class="sxs-lookup"><span data-stu-id="f9092-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9092-103">_**마지막으로 수정한 주제:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="f9092-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="f9092-104">Edge 풀이 작동 하지 않지만 같은 사이트의 프런트 엔드 풀은 계속 실행 되는 경우에는 프런트 엔드 풀을 설정 하 여 실패 한도 풀이 복원 될 때까지 다른 사이트의 Edge 풀을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9092-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="f9092-105">프런트 엔드 풀에 연결 된 Edge 풀 변경</span><span class="sxs-lookup"><span data-stu-id="f9092-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="f9092-106">토폴로지 작성기에서 변경 해야 하는 프런트 엔드 풀의 이름으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9092-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="f9092-107">풀을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9092-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="f9092-108">**연결** 섹션의 **Edge 풀 연결 (미디어 구성 요소)** 에서 드롭다운 상자를 사용 하 여이 프론트 엔드 풀을 연결할 edge 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="f9092-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="f9092-109">**확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f9092-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f9092-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f9092-110">See Also</span></span>


[<span data-ttu-id="f9092-111">Lync Server 2013의 에지 서버 재해 복구</span><span class="sxs-lookup"><span data-stu-id="f9092-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

