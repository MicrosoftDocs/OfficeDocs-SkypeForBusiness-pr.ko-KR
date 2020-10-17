---
title: 풀에서 프런트 엔드 서버 제거
description: 풀에서 프런트 엔드 서버를 제거 합니다.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45560a6f43288b47c0f85f880a190e31f2c8c04d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551304"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="a6d72-103">풀에서 프런트 엔드 서버 제거</span><span class="sxs-lookup"><span data-stu-id="a6d72-103">Remove a Front End Server from a pool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a6d72-104">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="a6d72-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="a6d72-105">Microsoft Lync Server 2010 Enterprise Edition 프런트 엔드 서버는 독립 실행형 컴퓨터로 존재할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d72-105">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="a6d72-106">풀에 컴퓨터가 하나만 있는 경우에도 프런트 엔드 풀로 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d72-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="a6d72-107">이 항목에서는 기존 프런트 엔드 풀에서 개별 프런트 엔드 서버를 제거 하는 프로세스를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d72-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="a6d72-108">프런트 엔드 서버가 풀의 마지막 서버 이거나 풀을 완전히 제거 하는 경우에는 [Remove 프런트 엔드 풀 또는 Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a6d72-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="a6d72-109">프런트 엔드 풀을 제거 하기 전에 개별 프런트 엔드 서버를 제거할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a6d72-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="a6d72-110">풀을 제거 하면 각 프런트 엔드 서버가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d72-110">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="a6d72-111">풀에서 프런트 엔드 서버를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="a6d72-111">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="a6d72-112">Lync Server 2013 프런트 엔드 서버를 열고 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a6d72-112">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="a6d72-113">Lync Server 2010 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d72-113">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="a6d72-114">**Enterprise Edition 프런트 엔드 풀**을 확장 하 고, 제거할 프런트 엔드 서버를 사용 하 여 프런트 엔드 풀을 확장 하 고, 제거할 프런트 엔드 서버를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d72-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

