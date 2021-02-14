---
title: 풀에서 프런트 엔드 서버 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 프런트 엔드 서버는 독립 실행형 컴퓨터로 존재할 수 없습니다. 풀에 컴퓨터가 하나만 있는 경우에도 프런트 엔드 풀로 정의해야 합니다.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752320"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="4c26c-104">풀에서 프런트 엔드 서버 제거</span><span class="sxs-lookup"><span data-stu-id="4c26c-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="4c26c-105">프런트 엔드 서버는 독립 실행형 컴퓨터로 존재할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c26c-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="4c26c-106">풀에 컴퓨터가 하나만 있는 경우에도 프런트 엔드 풀로 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4c26c-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="4c26c-107">이 항목에서는 기존 프런트 엔드 풀에서 개별 프런트 엔드 서버를 제거하는 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4c26c-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="4c26c-108">프런트 엔드 서버가 풀의 마지막 서버 또는 풀을 완전히 제거하는 경우 프런트 엔드 풀 또는 Standard Edition 서버 제거를 [참조합니다.](remove-front-end-pool-or-standard-edition-server.md)</span><span class="sxs-lookup"><span data-stu-id="4c26c-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="4c26c-109">프런트 엔드 풀을 제거하기 전에는 개별 프런트 엔드 서버를 제거할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4c26c-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="4c26c-110">풀을 제거하면 각 프런트 엔드 서버가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="4c26c-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="4c26c-111">풀에서 프런트 엔드 서버를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="4c26c-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="4c26c-112">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기 를 여는 경우</span><span class="sxs-lookup"><span data-stu-id="4c26c-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="4c26c-113">레거시 설치 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4c26c-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="4c26c-114">**Enterprise Edition 프런트** 엔드 풀을 확장하고, 제거할 프런트 엔드 서버가 있는 프런트 엔드 풀을 확장하고, 제거할 프런트 엔드 서버를 마우스 오른쪽 단추로 클릭한 다음 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="4c26c-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

