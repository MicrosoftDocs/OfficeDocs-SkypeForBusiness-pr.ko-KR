---
title: 백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove SQL Server instances and databases on the Back End Server
ms:assetid: 32457df9-7dd9-4fca-9362-ea4de26b0296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688016(v=OCS.15)
ms:contentKeyID: 49733606
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f03a318e81b839d5f92dbaa4ddcc70bbbc8e2e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a><span data-ttu-id="7b411-102">백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="7b411-102">Remove SQL Server instances and databases on the Back End Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b411-103">_**마지막으로 수정한 주제:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="7b411-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="7b411-104">Microsoft SQL Server 데이터베이스 및 인스턴스를 제거 하면 해당 사용자에 게 종속 된 Lync Server 2010를 실행 하는 서버를 제거한 후 또는 Lync Server 2010를 실행 하는 서버를 다시 구성 하 여 다른 데이터베이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b411-104">You remove the Microsoft SQL Server databases and instances after you remove the servers running Lync Server 2010 that are dependent on them, or after you reconfigure the servers running Lync Server 2010 to use another database.</span></span> <span data-ttu-id="7b411-105">현재 SQL Server를 중지 하거나 Lync Server 2010을 실행 하는 현재 서버를 다시 구성 하 여 데이터베이스를 더 이상 사용 하지 않거나 사용할 수 없게 되는 경우이 항목의 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b411-105">You need to perform the procedure in this topic when you retire the current SQL Server or reconfigure the current server running Lync Server 2010 in such a way that it renders the databases obsolete or unavailable.</span></span>

<span data-ttu-id="7b411-106">보관 서버 또는 모니터링 서버의 데이터베이스나 인스턴스를 제거 하려면 먼저 서버 역할을 제거 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b411-106">To remove the databases or instances for the Archiving Server or Monitoring Server, you must first remove the server role.</span></span> <span data-ttu-id="7b411-107">마찬가지로, 프런트 엔드 풀에 대 한 인스턴스 또는 데이터베이스를 제거 하려면 먼저 종속 서버 역할을 제거 하거나 다시 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b411-107">Similarly, to remove the instances or databases for Front End pool, you must first remove or reconfigure the dependent server role.</span></span> <span data-ttu-id="7b411-108">이러한 절차는 collocated 데이터베이스와 서버에 대 한 별도의 인스턴스를 구분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b411-108">These procedures make no distinction between collocated databases or separate instances for servers.</span></span> <span data-ttu-id="7b411-109">프로시저는 데이터베이스의 collocation에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b411-109">The procedures are unaffected by the collocation of databases.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7b411-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="7b411-110">In This Section</span></span>

  - [<span data-ttu-id="7b411-111">프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="7b411-111">Remove the SQL Server database for a Front End pool</span></span>](remove-the-sql-server-database-for-a-front-end-pool.md)

  - [<span data-ttu-id="7b411-112">모니터링 서버용 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="7b411-112">Remove the SQL Server database for a Monitoring server</span></span>](remove-the-sql-server-database-for-a-monitoring-server.md)

  - [<span data-ttu-id="7b411-113">보관 서버용 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="7b411-113">Remove the SQL Server database for an Archiving server</span></span>](remove-the-sql-server-database-for-an-archiving-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

