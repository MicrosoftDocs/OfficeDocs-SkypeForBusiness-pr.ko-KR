---
title: 프런트 엔드 풀 또는 Standard Edition 서버 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8628f883285eec61a179c27d5dfda16b8c9b51d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-front-end-pool-or-standard-edition-server"></a><span data-ttu-id="94192-102">프런트 엔드 풀 또는 Standard Edition 서버 제거</span><span class="sxs-lookup"><span data-stu-id="94192-102">Remove Front End pool or Standard Edition server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94192-103">_**마지막으로 수정한 주제:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="94192-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="94192-104">이 항목에서는 프런트 엔드 풀 또는 Standard Edition 프런트 엔드 서버를 제거 하는 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="94192-104">This topic guides you through the process of removing a Front End pool or a Standard Edition Front End Server.</span></span> <span data-ttu-id="94192-105">프런트 엔드 풀을 제거 하면 풀에 속한 각 프런트 엔드 서버를 그룹 제거 프로세스의 일부로 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="94192-105">When you remove a Front End pool, you remove each Front End Server that belongs to the pool as a part of the pool removal process.</span></span> <span data-ttu-id="94192-106">Standard Edition 프런트 엔드 서버를 제거 하는 경우 토폴로지 작성기에서 SQL 스토어 정의를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94192-106">When you remove a Standard Edition Front End Server, you must remove the SQL Store definition from Topology Builder.</span></span>

<div>

## <a name="to-remove-a-front-end-server-pool"></a><span data-ttu-id="94192-107">프런트 엔드 서버 풀을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="94192-107">To remove a Front End Server pool</span></span>

1.  <span data-ttu-id="94192-108">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="94192-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="94192-109">Lync Server 2010 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="94192-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="94192-110">**Enterprise Edition 프런트 엔드 풀**을 확장 하 고 프런트 엔드 풀을 확장 한 다음 제거 하려는 프런트 엔드 풀을 마우스 오른쪽 단추로 클릭 하 고 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="94192-110">Expand **Enterprise Edition Front End pools**, expand the Front End pool, right-click the Front End pool that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="94192-111">토폴로지를 게시 하 고, 복제 상태를 확인 한 다음 필요에 따라 Lync Server 배포 마법사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="94192-111">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a><span data-ttu-id="94192-112">Standard Edition 프런트 엔드 서버를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="94192-112">To remove a Standard Edition Front End server</span></span>

1.  <span data-ttu-id="94192-113">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="94192-113">Open Topology Builder.</span></span>

2.  <span data-ttu-id="94192-114">Lync Server 2010 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="94192-114">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="94192-115">**Standard Edition 프런트 엔드 서버**를 확장 하 고 제거 하려는 프런트 엔드 서버를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="94192-115">Expand **Standard Edition Front End servers**, right-click the Front End Server that you want to remove, and then click **Delete**.</span></span>

4.  <span data-ttu-id="94192-116">**Sql 저장소**를 확장 하 고 Standard Edition 프런트 엔드 서버와 연결 된 sql Server 데이터베이스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="94192-116">Expand **SQL stores**, right-click the SQL Server database that is associated with the Standard Edition Front End Server, and then click **Delete**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="94192-117">스탠더드 버전의 프런트 엔드 서버에서 collocated SQL Server 데이터베이스의 정의를 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94192-117">You must remove the definition of the collocated SQL Server databases from the Standard Edition Front End Server.</span></span>

    
    </div>

5.  <span data-ttu-id="94192-118">토폴로지를 게시 하 고, 복제 상태를 확인 한 다음 필요에 따라 Lync Server 배포 마법사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="94192-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

