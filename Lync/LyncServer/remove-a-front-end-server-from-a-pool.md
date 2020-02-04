---
title: 풀에서 프런트 엔드 서버 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0637754c6e7b1a03c233025703297c182dc3099
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="f1e8d-102">풀에서 프런트 엔드 서버 제거</span><span class="sxs-lookup"><span data-stu-id="f1e8d-102">Remove a Front End Server from a pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1e8d-103">_**마지막으로 수정한 주제:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="f1e8d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="f1e8d-104">Microsoft Lync Server 2010 Enterprise Edition 프런트 엔드 서버는 독립 실행형 컴퓨터로 존재할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1e8d-104">The Microsoft Lync Server 2010 Enterprise Edition Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="f1e8d-105">풀에 하나의 컴퓨터만 있는 경우에도 프런트 엔드 풀로 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e8d-105">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>

<span data-ttu-id="f1e8d-106">이 항목에서는 기존 프런트 엔드 풀에서 개별 프런트 엔드 서버를 제거 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e8d-106">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="f1e8d-107">프런트 엔드 서버가 풀의 마지막 서버 이거나 풀을 완전히 제거 하는 경우 [프런트 엔드 풀 또는 Standard Edition 서버 제거](remove-front-end-pool-or-standard-edition-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f1e8d-107">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="f1e8d-108">프런트 엔드 풀을 제거 하기 전에 개별 프런트 엔드 서버를 제거할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f1e8d-108">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="f1e8d-109">풀을 제거 하면 각 프런트 엔드 서버를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e8d-109">When you remove the pool, you remove each Front End Server.</span></span>

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="f1e8d-110">풀에서 프런트 엔드 서버 제거</span><span class="sxs-lookup"><span data-stu-id="f1e8d-110">To remove a Front End Server from a pool</span></span>

1.  <span data-ttu-id="f1e8d-111">Lync Server 2013 프런트 엔드 서버를 열고 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f1e8d-111">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="f1e8d-112">Lync Server 2010 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e8d-112">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="f1e8d-113">**Enterprise Edition 프런트 엔드 풀**을 확장 하 고 제거할 프런트 엔드 서버를 사용 하 여 프런트 엔드 풀을 확장 한 다음 제거 하려는 프런트 엔드 서버를 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1e8d-113">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

