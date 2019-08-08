---
title: 풀에서 프런트 엔드 서버 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 프런트 엔드 서버는 독립 실행형 컴퓨터로 존재할 수 없습니다. 풀에 하나의 컴퓨터만 있는 경우에도 프런트 엔드 풀로 정의 되어야 합니다.
ms.openlocfilehash: 64f0c4134f690005815591bce88b8d058c1bd007
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244531"
---
# <a name="remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="a98ea-104">풀에서 프런트 엔드 서버 제거</span><span class="sxs-lookup"><span data-stu-id="a98ea-104">Remove a Front End Server from a pool</span></span>

<span data-ttu-id="a98ea-105">프런트 엔드 서버는 독립 실행형 컴퓨터로 존재할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a98ea-105">The Front End Server cannot exist as a stand-alone computer.</span></span> <span data-ttu-id="a98ea-106">풀에 하나의 컴퓨터만 있는 경우에도 프런트 엔드 풀로 정의 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98ea-106">It must be defined as a Front End pool, even if there is only a single computer in the pool.</span></span>
  
<span data-ttu-id="a98ea-107">이 항목에서는 기존 프런트 엔드 풀에서 개별 프런트 엔드 서버를 제거 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98ea-107">This topic guides you through the process of removing an individual Front End Server from an existing Front End pool.</span></span> <span data-ttu-id="a98ea-108">프런트 엔드 서버가 풀의 마지막 서버 이거나 풀을 완전히 제거 하는 경우 [프런트 엔드 풀 또는 Standard Edition 서버 제거](remove-front-end-pool-or-standard-edition-server.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a98ea-108">If the Front End Server is the last server in the pool or if you are removing the pool completely, see [Remove Front End pool or Standard Edition server](remove-front-end-pool-or-standard-edition-server.md).</span></span> <span data-ttu-id="a98ea-109">프런트 엔드 풀을 제거 하기 전에 개별 프런트 엔드 서버를 제거할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a98ea-109">There is no need to remove the individual Front End Servers before you remove the Front End pool.</span></span> <span data-ttu-id="a98ea-110">풀을 제거 하면 각 프런트 엔드 서버를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98ea-110">When you remove the pool, you remove each Front End Server.</span></span>
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a><span data-ttu-id="a98ea-111">풀에서 프런트 엔드 서버 제거</span><span class="sxs-lookup"><span data-stu-id="a98ea-111">To remove a Front End Server from a pool</span></span>

1. <span data-ttu-id="a98ea-112">비즈니스용 Skype 서버 2019 프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a98ea-112">On the Skype for Business Server 2019 Front End Server, open Topology Builder.</span></span>
    
2. <span data-ttu-id="a98ea-113">레거시 설치 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98ea-113">Navigate to the legacy install node.</span></span>
    
3. <span data-ttu-id="a98ea-114">**Enterprise Edition 프런트 엔드 풀**을 확장 하 고 제거할 프런트 엔드 서버를 사용 하 여 프런트 엔드 풀을 확장 한 다음 제거 하려는 프런트 엔드 서버를 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a98ea-114">Expand **Enterprise Edition Front End pools**, expand the Front End pool with the Front End Server that you want to remove, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    

