---
title: 프런트 엔드 풀 또는 Standard Edition 서버 제거
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
description: 이 항목에서는 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 제거하는 프로세스를 안내합니다. 프런트 엔드 풀을 제거하면 풀 제거 프로세스의 일부로 풀에 속하는 각 프런트 엔드 서버를 제거합니다. Standard Edition 프런트 엔드 서버를 제거할 때 토폴로지 작성기에서 SQL 저장소 정의를 제거해야 합니다.
ms.openlocfilehash: 305a353ced45fe7e21ba479c0c3571df236aa09b
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752280"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="15f36-105">프런트 엔드 풀 또는 Standard Edition 서버 제거</span><span class="sxs-lookup"><span data-stu-id="15f36-105">Remove Front End pool or Standard Edition server</span></span>

<span data-ttu-id="15f36-106">이 문서에서는 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 제거하는 프로세스를 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="15f36-106">This article guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="15f36-107">프런트 엔드 풀을 제거하면 풀 제거 프로세스의 일부로 풀에 속하는 각 프런트 엔드 서버를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="15f36-107">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="15f36-108">Standard Edition 프런트 엔드 서버를 제거할 때 토폴로지 작성기에서 SQL 저장소 정의를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15f36-108">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>
  
## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="15f36-109">프런트 엔드 서버 풀을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="15f36-109">To remove a Front End Server pool</span></span>

1. <span data-ttu-id="15f36-110">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="15f36-110">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="15f36-111">레거시 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15f36-111">Navigate to the legacy node.</span></span>
    
3. <span data-ttu-id="15f36-112">**Enterprise Edition 프런트 엔드** 풀을 확장하고, 프런트 엔드 풀을 확장하고, 제거할 프런트 엔드 풀을 마우스 오른쪽 단추로 클릭한 다음 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="15f36-112">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="15f36-113">토폴로지 게시, 복제 상태 확인 및 필요한 경우 레거시 배포 마법사를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="15f36-113">Publish the topology, check replication status, and then run the legacy Deployment Wizard as needed.</span></span> 
    
## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="15f36-114">Standard Edition 프런트 엔드 서버를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="15f36-114">To remove a Standard Edition Front End server</span></span>

1. <span data-ttu-id="15f36-115">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="15f36-115">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="15f36-116">레거시 설치 노드로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="15f36-116">Navigate to the legacy installs node.</span></span>
    
3. <span data-ttu-id="15f36-117">Standard Edition 프런트 엔드 서버를 **확장하고** 제거할 프런트 엔드 서버를 마우스 오른쪽 단추로 클릭한 다음 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="15f36-117">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="15f36-118">저장소 **SQL** 확장하고 Standard Edition 프런트 엔드 서버와 SQL Server 데이터베이스를 마우스 오른쪽 단추로 클릭한 다음 삭제를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="15f36-118">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="15f36-119">Standard Edition 프런트 엔드 서버에서는 SQL Server 데이터베이스의 정의를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15f36-119">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span> 
  
5. <span data-ttu-id="15f36-120">토폴로지 게시, 복제 상태 확인 및 필요한 경우 배포 마법사를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="15f36-120">Publish the topology, check replication status, and then run the Deployment Wizard as needed.</span></span> 
    

