---
title: 백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Microsoft SQL Server 데이터베이스 및 인스턴스를 제거한 후에는이를 실행 하는 서버를 제거 하거나 다른 데이터베이스를 사용 하도록 서버를 다시 구성한 후에 제거 합니다. 현재 SQL Server를 중지 하거나 현재 서버를 다시 구성 하 여 데이터베이스를 더 이상 사용 하지 않거나 사용할 수 없는 경우에는이 항목의 절차를 수행 해야 합니다.
ms.openlocfilehash: 2d0902293c675143609dd720cd33734edd538d87
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197172"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="0906b-104">백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="0906b-104">Remove SQL Server instances and databases on the Back End Server</span></span>

<span data-ttu-id="0906b-105">Microsoft SQL Server 데이터베이스 및 인스턴스를 제거한 후에는이를 실행 하는 서버를 제거 하거나 다른 데이터베이스를 사용 하도록 서버를 다시 구성한 후에 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="0906b-105">You remove the Microsoft SQL Server databases and instances after you remove the servers running that are dependent on them, or after you reconfigure the servers to use another database.</span></span> <span data-ttu-id="0906b-106">현재 SQL Server를 중지 하거나 현재 서버를 다시 구성 하 여 데이터베이스를 더 이상 사용 하지 않거나 사용할 수 없는 경우에는이 항목의 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0906b-106">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server in such a way that it renders the databases obsolete or unavailable.</span></span>
  
<span data-ttu-id="0906b-107">보관 서버 또는 모니터링 서버의 데이터베이스나 인스턴스를 제거 하려면 먼저 서버 역할을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0906b-107">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="0906b-108">마찬가지로, 프런트 엔드 풀에 대 한 인스턴스 또는 데이터베이스를 제거 하려면 먼저 종속 서버 역할을 제거 하거나 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0906b-108">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="0906b-109">이러한 절차는 collocated 데이터베이스와 서버에 대 한 별도의 인스턴스를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0906b-109">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="0906b-110">프로시저는 데이터베이스의 collocation에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0906b-110">The procedures are unaffected by the collocation of databases.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0906b-111">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="0906b-111">In this section</span></span>

- [<span data-ttu-id="0906b-112">프런트 엔드 풀에 대 한 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="0906b-112">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [<span data-ttu-id="0906b-113">모니터링 서버용 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="0906b-113">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [<span data-ttu-id="0906b-114">보관 서버용 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="0906b-114">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)
    

