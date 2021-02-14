---
title: 백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거
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
description: 데이터베이스 및 Microsoft SQL Server 종속된 서버를 제거한 후 또는 다른 데이터베이스를 사용하기 위해 서버를 다시 구성한 후에 데이터베이스 및 인스턴스를 제거합니다. 현재 서버의 사용 중지 또는 SQL Server 다시 구성할 때 이 항목의 절차를 수행하여 데이터베이스가 더 이상 사용되지되거나 사용할 수 없게 됩니다.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752160"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="b3617-104">백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="b3617-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="b3617-105">데이터베이스 및 Microsoft SQL Server 종속된 서버를 제거한 후 또는 다른 데이터베이스를 사용하기 위해 서버를 다시 구성한 후에 데이터베이스 및 인스턴스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b3617-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="b3617-106">현재 서버의 사용 중지 또는 SQL Server 다시 구성할 때 이 항목의 절차를 수행하여 데이터베이스가 더 이상 사용되지되거나 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3617-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="b3617-107">보관 서버 또는 모니터링 서버의 데이터베이스 또는 인스턴스를 제거하려면 먼저 서버 역할을 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3617-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="b3617-108">마찬가지로 프런트 엔드 풀의 인스턴스 또는 데이터베이스를 제거하려면 먼저 종속 서버 역할을 제거하거나 다시 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3617-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="b3617-109">이러한 절차는 배치된 데이터베이스나 개별 서버 인스턴스 간에 구분되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3617-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="b3617-110">데이터베이스 배치는 절차에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b3617-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b3617-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="b3617-111">In this section</span></span>

- [<span data-ttu-id="b3617-112">프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="b3617-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="b3617-113">모니터링 서버용 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="b3617-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="b3617-114">보관 서버용 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="b3617-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

