---
title: 풀에서 프런트 엔드 서버 제거
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
ms.openlocfilehash: 0ef9df56c094bb5d7a3972a7c062905cbc4a844a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="03e3a-102">풀에서 프런트 엔드 서버 제거</span><span class="sxs-lookup"><span data-stu-id="03e3a-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03e3a-103">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="03e3a-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="03e3a-104">Microsoft Lync Server 2010 Enterprise Edition 프런트 엔드 서버는 독립 실행형 컴퓨터로 존재할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="03e3a-105">풀에 컴퓨터가 하나만 있는 경우에도 프런트 엔드 풀로 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="03e3a-106">이 항목에서는 기존 프런트 엔드 풀에서 개별 프런트 엔드 서버를 제거 하는 프로세스를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="03e3a-107">프런트 엔드 서버가 풀의 마지막 서버 이거나 풀을 완전히 제거 하는 경우에는 [Remove 프런트 엔드 풀 또는 Standard Edition Server](remove-front-end-pool-or-standard-edition-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03e3a-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="03e3a-108">프런트 엔드 풀을 제거 하기 전에 개별 프런트 엔드 서버를 제거할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="03e3a-109">풀을 제거 하면 각 프런트 엔드 서버가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="03e3a-110">풀에서 프런트 엔드 서버를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="03e3a-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="03e3a-111">Lync Server 2013 프런트 엔드 서버를 열고 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="03e3a-112">Lync Server 2010 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="03e3a-113">**Enterprise Edition 프런트 엔드 풀**을 확장 하 고, 제거할 프런트 엔드 서버를 사용 하 여 프런트 엔드 풀을 확장 하 고, 제거할 프런트 엔드 서버를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03e3a-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

