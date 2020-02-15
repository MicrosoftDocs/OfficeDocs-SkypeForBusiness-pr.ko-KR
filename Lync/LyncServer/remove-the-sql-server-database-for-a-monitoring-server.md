---
title: 모니터링 서버에 대 한 SQL Server 데이터베이스 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove the SQL Server database for a Monitoring server
ms:assetid: aed5e394-d63e-4ad4-af40-f12d3a044344
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721848(v=OCS.15)
ms:contentKeyID: 49733781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5485f957bf0f172b52db602fba84819f493bc817
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-sql-server-database-for-a-monitoring-server"></a><span data-ttu-id="369fc-102">모니터링 서버에 대 한 SQL Server 데이터베이스 제거</span><span class="sxs-lookup"><span data-stu-id="369fc-102">Remove the SQL Server database for a Monitoring server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="369fc-103">_**마지막으로 수정 된 항목:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="369fc-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="369fc-104">Microsoft Lync Server 2010 모니터링 서버를 제거한 후에는 서버 데이터를 호스트 하는 SQL Server 데이터베이스를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="369fc-104">After you remove a Microsoft Lync Server 2010 Monitoring Server, you can remove the SQL Server databases that hosted the server data.</span></span> <span data-ttu-id="369fc-105">다음 절차에 따라 토폴로지 작성기에서 정의를 제거 하 고 데이터베이스 서버에서 데이터베이스 및 로그 파일을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="369fc-105">Use the following procedures to remove the definitions from Topology Builder, and then remove the database and log files from the database server.</span></span>

<div>

## <a name="to-remove-the-sql-server-database-using-topology-builder"></a><span data-ttu-id="369fc-106">토폴로지 작성기를 사용 하 여 SQL Server 데이터베이스를 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="369fc-106">To remove the SQL Server database using Topology Builder</span></span>

1.  <span data-ttu-id="369fc-107">Lync Server 2013 프런트 엔드 서버에서 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="369fc-107">On the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="369fc-108">토폴로지 작성기에서 **공유 구성 요소** 를 탐색 하 고 **SQL server 저장소**로 이동한 다음, 제거 되거나 다시 구성 된 모니터링 서버에 연결 된 SQL Server 인스턴스를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="369fc-108">In Topology Builder, navigate to **Shared Components** and then **SQL Server Stores**, right-click the SQL Server instance associated with the removed or reconfigured Monitoring Server, and then click **Delete**.</span></span>

3.  <span data-ttu-id="369fc-109">토폴로지를 게시한 후 복제 상태를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="369fc-109">Publish the topology, and then check replication status.</span></span>

</div>

<div>

## <a name="to-remove-the-database-files-from-the-sql-server"></a><span data-ttu-id="369fc-110">SQL Server에서 데이터베이스 파일을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="369fc-110">To remove the database files from the SQL Server</span></span>

1.  <span data-ttu-id="369fc-111">SQL Server 기반 서버에서 데이터베이스를 제거 하려면 데이터베이스 파일을 제거 하려는 SQL Server 서버에 대해 SQL Server sysadmins 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="369fc-111">To remove the databases on the SQL Server-based server, you must be a member of the SQL Server sysadmins group for the SQL Server server where you are removing the database files.</span></span>

2.  <span data-ttu-id="369fc-112">Lync Server 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="369fc-112">Open the Lync Server Management Shell.</span></span>

3.  <span data-ttu-id="369fc-113">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="369fc-113">At the command line, type the following:</span></span>
    
        Uninstall-CsDataBase -DatabaseType Monitoring -SqlServerFqdn <FQDN> [-SqlInstanceName <instance>]
    
    <span data-ttu-id="369fc-114">여기서 \<FQDN\> 은 데이터베이스 서버의 FQDN (정규화 된 도메인 이름)이 고 \<인스턴스\> 는 선택적 명명 된 데이터베이스 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="369fc-114">Where \<FQDN\> is the fully qualified domain name (FQDN) of the database server, and \<instance\> is the optional named database instance.</span></span>

4.  <span data-ttu-id="369fc-115">**Uninstall-CsDataBase** cmdlet에서 작업을 확인하라는 메시지가 표시되면 해당 정보를 읽고, 계속하려면 **Y**(또는 Enter 키)를 누르고, cmdlet을 중지하려면 **N**을 누른 후 Enter 키를 누릅니다(즉, 오류가 있을 경우에 대비하여).</span><span class="sxs-lookup"><span data-stu-id="369fc-115">When the **Uninstall-CsDataBase** cmdlet prompts you to confirm actions, read the information, and then press **Y** (or press Enter) to proceed, or press **N** and then Enter if you want to stop the cmdlet (that is, in case there errors).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

